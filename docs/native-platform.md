# Verificación nativa de compatibilidad

Desde 1.3.6, la identidad de una búsqueda incluye también el intervalo ALIAS.
Solo se añaden allí páginas de tipo Heap con permiso RW exacto y sin ejecución.
El destino se vuelve a consultar antes de una prueba experimental. Su código
estático usa la región M=2 de Atmosphère, con desplazamiento de 40 bits y límites
comprobados. No se habilita la región ASLR ni se amplían referencias antiguas.

Referencias primarias de Atmosphère 1.12.1:
[formato Type 0](https://github.com/Atmosphere-NX/Atmosphere/blob/1.12.1/docs/features/cheats.md#L45-L55)
y [resolución de Alias en la VM](https://github.com/Atmosphere-NX/Atmosphere/blob/1.12.1/stratosphere/dmnt/source/cheat/impl/dmnt_cheat_vm.cpp#L745-L756).

`platform.cpp` consulta los registros de NS, sus contenidos Application/Patch y
la versión declarada en NACP. Los DLC no se confunden con actualizaciones.

El Build ID se obtiene de una de estas fuentes, nunca de una aproximación de la
versión visible ni de la última versión del catálogo:

1. Metadatos de `dmnt:cht` del juego abierto, con comprobación del PID de la
   aplicación en `pm:dmnt`, Title ID, Build ID y exclusión del propio proceso.
2. Módulo principal del juego abierto mediante `ldr:dmnt`, cuando hay exactamente
   los dos módulos esperados y el Title ID coincide.
3. Cabecera `NSO0` de `/main` del código instalado abierto mediante `fsp-ldr`.
   Se leen los primeros ocho bytes del identificador de 32 bytes del NSO en
   desplazamiento `0x40`. Solo se admite el contenido efectivo más reciente;
   si hay una actualización, no se recurre al ejecutable anterior de la base.

En firmware anterior a 20.0.0 se resuelve la ruta Program NCA del contenido
Application/Patch exacto mediante NCM. En 20.0.0 y posterior, `fsp-ldr` usa el
Title ID y almacenamiento según su interfaz actual. Si no se puede verificar,
la aplicación conserva la entrada y explica cómo abrir el juego y volver a
Álbum. No elige otro Build ID.

La activación en directo usa únicamente la interfaz de cheats de `dmnt:cht`.
La consulta de compatibilidad no fuerza una conexión del motor al juego. Solo
la activación explícita puede hacer esa conexión, tras comprobar por el loader
el proceso, Title ID y Build ID; el servicio se vuelve a verificar después.
Comprueba otra vez PID, Title ID y Build ID antes de cada cambio. Los códigos
nuevos se añaden desactivados; se validan las dependencias de maestro y después
se activan. Se conserva el estado de los demás códigos del motor. Si se produce
un error, se eliminan los códigos recién añadidos y se revierten los estados
tocados mientras siga siendo el mismo proceso. Si cambió el proceso, no se
intenta modificar el proceso nuevo y se indica que reinicie el juego. Revertir
las entradas del motor no restaura valores que un cheat ya haya escrito en la
memoria del juego; tras un fallo parcial se recomienda reiniciarlo.

Antes de cambiar el motor también se comparan los códigos elegidos con los
códigos normales que ya estén activados. Si dos secciones de escrituras estáticas
lineales escriben valores diferentes en el mismo destino, la activación se
rechaza antes del primer cambio. Las secciones condicionales o basadas en
registros no permiten deducir automáticamente todos los conflictos.

`inspectActive` permite detectar las entradas ya cargadas en el motor para el
Title ID y Build ID exactos, incluso si están desactivadas o no existe su archivo
en la SD. Esta revisión no fuerza la conexión del motor y comprueba que el
proceso no cambie durante la lectura. Si el juego está abierto y el inventario
no se puede verificar, pide cerrarlo antes de continuar.

La retirada en directo conserva un recibo privado en
`sdmc:/config/NinMagicCheats/live.bin`, que se vuelve a cargar al abrir el NRO.
Así se puede aplicar un cheat, salir para jugar y volver a la aplicación para
retirarlo mientras siga siendo el mismo proceso, Title ID y Build ID. Solo
retira entradas nuevas registradas y desactiva las entradas que estaban
desactivadas antes de que NinMagic las activase. Las activaciones
repetidas se combinan conservando el estado original. Comprueba identidad,
contenido y estado de cada entrada antes y después de retirarla. Si otro cliente
reutilizó un ID para códigos distintos, no los modifica. Si aparecieron entradas
nuevas de otro cliente después de crear un maestro propio, no retira ese maestro
porque podrían depender de él. Una retirada parcial conserva el recibo de las
entradas pendientes para poder volver a intentarlo.

El recibo usa enteros en little endian, CRC32, un contador de generación, límites
de 512 KiB y 128 entradas, y archivos pendiente/copia anterior para recuperar una
escritura interrumpida. Se comprueban nombres terminados, tamaños de códigos,
IDs únicos y correspondencia con el inventario. Cada archivo se escribe con
fsync y se confirma en la SD después de renombrar. Las rutas son privadas y
fijas; no se aceptan enlaces ni rutas ajenas en el recibo. Un recibo dañado que
no se puede recuperar impide aplicar nuevos cheats en directo. Si falla guardar
después de la activación, se informa de que los cheats ya están activos y que se
deben retirar antes de salir del NRO o cerrar el juego.

La retirada parcial guarda las entradas pendientes. Un error al consultar el
proceso conserva el recibo; solo una identidad nativa diferente verificada
permite descartarlo como obsoleto. Después de una retirada completa se borran
exclusivamente sus tres archivos privados de recibo.

También se pueden retirar los archivos instalados y cerrar y abrir el juego.
Retirar una entrada
del motor detiene su ejecución, pero no restaura escrituras anteriores en memoria
ni cambios que se hayan guardado en la partida; la interfaz lo indica.

Solo existe un código maestro, en la entrada reservada 0. Un maestro distinto
que ya esté en uso impide la activación en directo. El máximo es de 127 códigos
normales más un maestro, con 256 palabras de 32 bits por sección. Las selecciones
que necesitan maestros distintos se rechazan. La coincidencia de Build ID no
garantiza que dos opciones gráficas elegidas sean compatibles entre sí.

# Fuentes primarias consultadas

- [libnx fsp-ldr](https://github.com/switchbrew/libnx/blob/master/nx/source/services/fsldr.c)
- [libnx NS](https://github.com/switchbrew/libnx/blob/master/nx/include/switch/services/ns.h)
- [libnx loader](https://github.com/switchbrew/libnx/blob/master/nx/include/switch/services/ldr.h)
- [Atmosphère: tipos del protocolo de cheats](https://github.com/Atmosphere-NX/Atmosphere/blob/master/libraries/libstratosphere/include/stratosphere/dmnt/dmnt_cheat_types.hpp)
- [Atmosphère: cliente IPC dmnt](https://github.com/Atmosphere-NX/Atmosphere/blob/master/libraries/libstratosphere/source/dmnt/dmntcht.os.horizon.c)
- [Atmosphère: implementación del motor](https://github.com/Atmosphere-NX/Atmosphere/blob/master/stratosphere/dmnt/source/cheat/impl/dmnt_cheat_api.cpp)
- [Atmosphère: selección del contenido por loader](https://github.com/Atmosphere-NX/Atmosphere/blob/master/stratosphere/loader/source/ldr_content_management.cpp)
- [HATS-Tools: lectura de Build ID del NSO](https://github.com/sthetix/HATS-Tools/blob/main/sphaira/source/ui/menus/cheats_menu.cpp)

Las estructuras de interfaz se escribieron como definiciones del protocolo;
no se han incorporado archivos de implementación de estas fuentes.

# Pruebas en PC

```powershell
clang++ -std=c++17 -O2 -Wall -Wextra -Werror -Iinclude tests/runtime_test.cpp source/runtime.cpp source/cheats.cpp -o "$env:TEMP/ninmagic-cheats-runtime-test.exe"
& "$env:TEMP/ninmagic-cheats-runtime-test.exe"
```

Resultado: `runtime: 43 identity, dependency and rollback scenarios passed`.
Usa un motor simulado en memoria y no accede a la consola. Comprueba coincidencia
de identidad, conservación de estados existentes, maestros por grupo, límites,
errores parciales, reversión y cambio de proceso. Las fuentes también se han
compilado con los encabezados reales de libnx y el compilador AArch64.
Las pruebas de retirada cubren propiedad de las entradas, aplicación repetida,
restauración de estados originales, reutilización de IDs, dependencias de maestro,
retirada parcial y respuestas de éxito del motor sin el cambio esperado.

La persistencia se comprueba con un directorio temporal dedicado del PC:

```powershell
g++ -std=c++17 -O2 -Wall -Wextra -Werror -Wno-misleading-indentation -DNC_LIVE_RECEIPT_TEST -Iinclude tests/live_receipt_test.cpp source/live_receipt.cpp source/runtime.cpp source/cheats.cpp -o "$env:TEMP/ninmagic-live-receipt-test.exe"
& "$env:TEMP/ninmagic-live-receipt-test.exe"
```

Resultado en este PC: `live receipt: 27 persistence, recovery and reopen scenarios passed`.
Incluye salir y volver a cargar el recibo con el mismo proceso simulado, retirar
una operación parcial después de reabrir, CRC y encabezados alterados,
truncamientos, generaciones, recuperación de pendiente/copia, límites, rutas
ocupadas por directorios y limpieza de archivos propios. Se comprueban enlaces
adicionalmente cuando el sistema de pruebas puede crearlos como enlaces reales.

Estas pruebas verifican la implementación; la activación sobre una consola real
necesita una prueba de ejecución con ese juego y su entorno de Atmosphère.

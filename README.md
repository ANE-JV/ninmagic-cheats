# ninmagic-cheats 1.3.5

NRO para Nintendo Switch con Atmosphère, interfaz en español, varios colores neón y el logo original de NinMagic dentro de la aplicación y en hbmenu. Independiente de NinMagic Cleaner.

Esta versión se centra en cheats de jugabilidad: vida, munición, dinero y otras opciones publicadas para cada juego. Se han retirado la sección de mods y las listas de ajustes FPS, resolución y gráficos. No se inventan opciones si el autor no las publicó.

La actualización 1.3.1 corrige los nombres ilegibles de juegos cuando el sistema entrega metadatos NACP comprimidos. Los identificadores de juego y Build ID siguen comprobándose por separado para elegir los cheats de la versión exacta.

La 1.3.2 permite seguir reduciendo búsquedas desconocidas con más de 20.000 coincidencias. Las posiciones que sobreviven se filtran desde la microSD sin cargarlas todas en RAM; no se abandona la comparación para volver a la referencia inicial.

La 1.3.3 añade recuperar una comparación anterior: **Y en el menú principal del overlay** o **ZL en los resultados del NRO**. Un resultado de cero se muestra como cero; no vuelve a filtrar una lista vacía ni sobrescribe la copia recuperable. Recuperar no lee ni escribe valores del juego y exige la misma sesión y datos guardados íntegros.

La 1.3.4 conserva el último resultado de prueba al reabrir el overlay y separa aquel resultado del estado actual del motor y de la lectura del valor. **X** comprueba sin activar códigos y **R** muestra el informe. También corrige el texto que aparecía cortado aunque cupiera. Una lectura coincidente o un código habilitado todavía no demuestran que la dirección controle la salud.

La 1.3.5 corrige el bloqueo que aparecía al pedir **Quitar mis cheats** cuando no había códigos propios que retirar. Esa operación no crea una falsa prueba fallida ni bloquea la revisión de candidatos. También distingue la referencia inicial de una búsqueda sin coincidencias, incluso cuando se muestra el resultado de una prueba anterior.

## Instalar

Extrae el ZIP en la raíz de la microSD, uniendo las carpetas `switch` y `config`. El NRO queda en `switch/ninmagic-cheats/ninmagic-cheats.nro` y el catálogo en `config/NinMagicCheats/`.

La base incluida funciona sin conexión. Al abrir la aplicación con Internet se comprueban las fuentes de cheats para añadir publicaciones nuevas. También puedes pulsar **Y en la biblioteca** para actualizar manualmente. Si falla Internet o la descarga no se verifica, se conserva el catálogo anterior. La aplicación debe estar abierta para comprobar novedades.

El catálogo conserva versiones antiguas identificadas por Title ID y Build ID; una actualización no borra esos códigos históricos. Tener códigos de varios años no significa que existan para todos los juegos o todas sus versiones.

## Crear una prueba cuando no hay cheats

**ZR: Crear** abre un buscador guiado, también para juegos sin códigos publicados. Pregunta qué quieres buscar (salud, munición, vidas, magia/energía, kits/objetos, dinero, velocidad/salto u otro valor) y si aparece como número o puntos/barra. La finalidad es una etiqueta; no identifica por sí sola lo que significa una dirección.

Para los puntos blancos de salud de Terminator 2D: NO FATE, selecciona **Salud → Puntos o barra**, pulsa **Y → A** para guardar una referencia, vuelve al juego, pierde un punto y regresa por Álbum. Elige **Cambió → Y**; después muévete sin perder salud y compara **No cambió**. Repite **Cambió** tras recibir daño antes de confirmar el filtro. No se conoce de antemano si la representación interna aumenta o disminuye. La búsqueda se conserva al cerrar NinMagic si mantienes el mismo proceso del juego abierto. Al recuperarla se presenta como **Otro valor**, sin asumir que una coincidencia sea salud.

Se admite búsqueda exacta y valor desconocido, con comparaciones de igual, cambió, no cambió, aumentó o disminuyó; los formatos disponibles son enteros de 8/16/32 bits y decimal de 32 bits. Se leen páginas de datos MAIN/HEAP, hasta 512 MiB, y se informa si la cobertura es parcial. Las comparaciones de una referencia desconocida pueden conservar más de 20.000 coincidencias en la microSD y seguir filtrándose. La lista se carga en RAM cuando es suficientemente pequeña.

La prueba exige una sola coincidencia, la lectura inicial y al menos dos comparaciones. **A** revisa; **X** permite cambiar el valor a fijar; **A** confirma la prueba experimental. Se verifica la misma sesión, Build ID y distribución de memoria. No se aplica con otros códigos activos ni con un maestro cargado. **L** retira los códigos propios registrados por NinMagic.

La búsqueda y sus filtros no escriben en la memoria del juego. Al confirmar el inicio, conectar el motor puede cargar los cheats que ya existan en la SD. La escritura de prueba requiere otra confirmación explícita. Una coincidencia única puede controlar algo distinto y necesita comprobarse dentro del juego. Las pruebas no se exportan como códigos portables: no se reutilizan después de reiniciar el juego. Velocidad y salto pueden necesitar estudiar instrucciones o parámetros de física; este buscador no los deduce automáticamente.

Las referencias privadas y sus comprobaciones CRC se guardan en `config/NinMagicCheats/scanner/`. No se incluyen en el paquete público ni se envían a GitHub. La guía detallada se incluye como `Creador-guiado.txt`.

## Complemento lateral experimental

`NinMagic Creador` es un archivo `.ovl` para un cargador Tesla/Ultrahand compatible. Su primera instalación consiste en copiar `ninmagic-creator.ovl` a `switch/.overlays/`; el actualizador NRO no instala ni actualiza este archivo ni el cargador. El paquete experimental incluye su código fuente y las licencias correspondientes.

Permite elegir el lado del panel, guardar una referencia, ocultarse para seguir leyendo mientras juegas y volver a comparar sin abrir Álbum. Un HUD pasivo muestra progreso y coincidencias sin usar los botones normales del juego. Ocultar mantiene su hilo; salir al menú de overlays lo cancela y espera su cierre. Necesita que indiques cambios relevantes; no identifica salud automáticamente ni activa candidatos sin confirmarlos.

La guía está en `docs/overlay-guide.md`. El complemento tiene compilación y pruebas en PC; su funcionamiento, memoria disponible y compatibilidad concreta con firmware 23 aún requieren prueba real en consola. No uses simultáneamente los dos frontends de NinMagic.

## Importación local de cheats publicados

El archivo opcional `config/NinMagicCheats/manual-cheats.zip` permite incorporar una copia local de códigos publicados sin cambiar las fuentes automáticas ni los catálogos oficiales. Usa entradas `<TITLEID>/cheats/<BUILDID>.txt`; se comprueban límites, CRC y sintaxis antes de añadirlas como **Importacion local**. Un archivo inválido se omite con un aviso y no invalida la caché oficial. Copiar este ZIP no instala ni activa códigos en Atmosphère: hay que seleccionarlos y confirmar en la aplicación, con el Build ID exacto comprobado.

Las importaciones personales no se incluyen en el paquete público de NinMagic. Conserva la fuente y los créditos del autor. Que un código esté publicado y coincida con el Build ID no sustituye una prueba de su efecto en el juego.

## Actualizar la aplicación sin PC

**Y en la biblioteca** actualiza el catálogo de cheats. **L: Actualizar app** consulta una versión nueva del propio NRO; también se comprueba al abrir, salvo al recuperar una búsqueda en curso.

El canal público es independiente de la página web: `ANE-JV/ninmagic-cheats` en GitHub. Su configuración es `config/NinMagicCheats/update-url.txt`. El manifiesto y cada NRO se descargan por HTTPS sin credenciales y se exige que coincidan su versión, tamaño y SHA-256. La página web y sus paquetes no forman parte de este proyecto.

Cuando se publique una versión posterior, **A: Descargar e instalar** autoriza su instalación. Se comprueban HTTPS, tamaño, SHA-256, estructura del NRO, nombre y versión NACP antes de reemplazarlo. Se conserva una copia numerada en `config/NinMagicCheats/app-update/`. Después cierra y vuelve a abrir NinMagic. Desde la versión 1.3.0 puedes recibir esta actualización dentro de la aplicación; una primera instalación requiere copiar el paquete a la consola.

El actualizador utiliza la ubicación estándar `switch/ninmagic-cheats/ninmagic-cheats.nro`. Durante un reemplazo interrumpido puede quedar un NRO de recuperación ejecutable en esa misma carpeta; al abrirlo se intenta recuperar la ruta estándar a partir de su copia verificada. No apagues ni retires la microSD durante la instalación.

## Aplicar fácilmente

1. Selecciona el juego con **A**.
2. Marca los cheats que quieras con **A**. Se muestra el nombre original y, cuando se reconoce, una descripción en español con sus botones.
3. Pulsa **Y → A** para revisar y confirmar.

Con el juego abierto, aplica directamente al proceso comprobado. Abre el juego y después entra a **HOME → Álbum → hbmenu → ninmagic-cheats** para mantenerlo en segundo plano. Un acceso directo del menú HOME puede pedir cerrar el juego; usa Álbum en ese caso.

Con el juego cerrado, instala los códigos seleccionados para el siguiente inicio. La confirmación avisa si ya hay un archivo de cheats o entradas cargadas. Se guarda copia de los archivos sustituidos. Los cheats del motor que ya estaban activos conservan su estado; se bloquean los conflictos estáticos detectables y los maestros incompatibles.

**Las casillas son tu selección preparada.** El indicador de cada fila muestra el estado leído del motor: activo, apagado, sin cargar o sin comprobar. Al volver a abrir la aplicación, las marcas se recuperan de los códigos realmente habilitados. **X dentro del juego seleccionado** vuelve a consultar el motor sin activar ni desactivar nada y conserva los cambios que estabas preparando.

Los códigos de botón mantienen sus condiciones originales. En Zelda Link's Awakening, el código «9999 Rupees Press L» requiere L y «Infinite / Max Hearts Press ZR» requiere ZR. No se convierten en códigos permanentes cambiando instrucciones del autor.

## Retirar

En la lista de cheats pulsa **L → A**. Con el juego abierto retira los códigos que NinMagic activó en ese proceso. Con el juego cerrado deshace la última instalación de archivos y recupera su copia anterior.

Después cierra y vuelve a abrir el juego para reiniciar los valores temporales: retirar un cheat del motor no revierte necesariamente un valor que ya escribió, y una partida guardada después de usarlo conserva los cambios guardados. La aplicación no borra tus partidas.

Los archivos instalados son `atmosphere/contents/TITLEID/cheats/BUILDID.txt` y `toggles.txt`; sus copias están en `config/NinMagicCheats/backups/`. `live.bin` conserva el registro necesario para retirar los códigos activados en directo. No borres esos registros si necesitas deshacer cambios.

Las copias y registros antiguos de instalaciones con mods deben conservarse para su recuperación con la versión anterior. Esta versión no instala ni retira mods.

## Compatibilidad y diagnóstico

Antes de aplicar se vuelve a leer el Build ID real y se exige la coincidencia exacta del Title ID y Build ID del archivo. En directo se comprueban también el proceso y su identificador. No se elige el código de otra versión aunque el nombre del juego coincida.

Se comprueban el formato, los maestros, los conflictos estáticos detectables y la capacidad total del motor de Atmosphère: como máximo 1024 palabras activas, contando también los códigos que ya estaban cargados. Una activación IPC correcta por sí sola no demuestra que el cheat produzca su efecto.

**Ningún catálogo externo permite garantizar al 100 % el efecto de un cheat ni que el juego nunca se cierre.** La aplicación confirma identificadores y estado del motor; no presenta eso como una prueba del efecto dentro del juego.

Esta versión corrige que las casillas aparecieran vacías al reabrir. La causa de que el efecto dejara de funcionar en Zelda todavía necesita comprobarse en la consola. Para poder revisarla, guarda un diagnóstico limitado en `config/NinMagicCheats/diagnostico-cheats.txt` al consultar, aplicar, retirar y salir. Contiene identificadores, nombres y estado del motor; no lee la memoria de la partida.

## Fuentes y servidor propio

Se conservan las dos fuentes originales de códigos de cheats:

- [HamletDuFromage/switch-cheats-db](https://github.com/HamletDuFromage/switch-cheats-db/releases).
- [ChanseyIsTheBest/NX-60FPS-RES-GFX-Cheats](https://github.com/ChanseyIsTheBest/NX-60FPS-RES-GFX-Cheats/blob/main/GAMES.md).

Los ajustes visuales se filtran de las opciones disponibles en esta aplicación. Las URLs e índices exclusivos de mods se han retirado del ejecutable y del paquete nuevo. Los créditos de los autores se conservan dentro de los códigos.

No hace falta un servidor propio. Para usar uno HTTPS, consulta `Servidor-propio.txt` incluido en la carpeta de la aplicación.

## Compilar

Requiere devkitPro, devkitA64, libnx, switch-curl, switch-minizip y switch-zlib:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File tools/build.ps1 -Preview
```

El script produce y verifica el NRO y renderiza la interfaz con datos de ejemplo. Las pruebas de PC comprueban archivos y activación simulada; no sustituyen la ejecución de cheats en una consola real.

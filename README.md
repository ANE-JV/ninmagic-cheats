# ninmagic-cheats 1.4.5

NRO para Nintendo Switch con Atmosphère, interfaz en español, varios colores neón y el logo original de NinMagic dentro de la aplicación y en hbmenu. Independiente de NinMagic Cleaner.

La 1.4.5 añade el catálogo de Arch9SK7 y una selección de archivos independientes de bad1dea, además de opciones publicadas por OblivionReign para Mario Wonder 1.2.1, Title ID `010015100B514000`, Build ID `FF773E90972D544E`. La coincidencia de versión declarada no certifica su efecto en la consola. Se conserva el bloqueo por huella de los once códigos anteriores de Wonder en revisión.

Descargas 1.4.5: [paquete completo para microSD](https://raw.githubusercontent.com/ANE-JV/ninmagic-cheats/main/versions/v1.4.5/ninmagic-cheats-1.4.5.zip), [aplicación NRO](https://raw.githubusercontent.com/ANE-JV/ninmagic-cheats/main/versions/v1.4.5/ninmagic-cheats.nro), [paquete del overlay](https://raw.githubusercontent.com/ANE-JV/ninmagic-cheats/main/versions/v1.4.5/experimental/ninmagic-overlay-1.4.5-experimental.zip) y [fuentes correspondientes](https://raw.githubusercontent.com/ANE-JV/ninmagic-cheats/main/versions/v1.4.5/experimental/ninmagic-overlay-fuentes-1.4.5.zip).

Esta versión se centra en cheats de jugabilidad: vida, munición, dinero y otras opciones publicadas para cada juego. Se han retirado la sección de mods y las listas de ajustes FPS, resolución y gráficos. No se inventan opciones si el autor no las publicó.

Si no hay cheats publicados compatibles con el Title ID y Build ID comprobados, la aplicación lo indica. Puedes actualizar el catálogo o importar códigos publicados para esa versión. No utiliza códigos de otra versión ni crea opciones mediante búsquedas de memoria.

El creador de códigos se ha retirado del paquete actual. El overlay permite seleccionar y aplicar cheats publicados. Los paquetes históricos mantienen sus fuentes y licencias. La aplicación no elimina juegos ni partidas guardadas.

## Instalar

Extrae el ZIP en la raíz de la microSD, uniendo las carpetas `switch` y `config`. El NRO queda en `switch/ninmagic-cheats/ninmagic-cheats.nro` y el catálogo en `config/NinMagicCheats/`. El paquete completo también incorpora el overlay en `switch/.overlays/`; requiere un cargador compatible ya instalado. El actualizador interno sustituye el NRO; para actualizar también el overlay se copia el paquete completo o su ZIP separado.

La base incluida funciona sin conexión. Al abrir la aplicación con Internet se comprueban las publicaciones nuevas del catálogo principal. Al seleccionar un juego se consultan también los proveedores adicionales por su Title ID y Build ID exactos; las comprobaciones recientes se reutilizan durante seis horas. También puedes actualizar manualmente. Si falla Internet o la descarga no se verifica, se conservan los códigos guardados y se indica qué fuente no pudo comprobarse.

El catálogo conserva versiones antiguas identificadas por Title ID y Build ID; una actualización no borra esos códigos históricos. Tener códigos de varios años no significa que existan para todos los juegos o todas sus versiones.

## Importación local de cheats publicados

El archivo opcional `config/NinMagicCheats/manual-cheats.zip` permite incorporar una copia local de códigos publicados sin cambiar las fuentes automáticas ni los catálogos oficiales. Usa entradas `contents/<TITLEID>/cheats/<BUILDID>.txt`; se comprueban límites, CRC y sintaxis antes de añadirlas como **Importacion local**. Un archivo inválido se omite con un aviso y no invalida la caché oficial. Copiar este ZIP no instala ni activa códigos en Atmosphère: hay que seleccionarlos y confirmar en la aplicación, con el Build ID exacto comprobado.

Las importaciones personales no se incluyen en el paquete público de NinMagic. Conserva la fuente y los créditos del autor. Que un código esté publicado y coincida con el Build ID no sustituye una prueba de su efecto en el juego.

## Actualizar la aplicación sin PC

**Y en la biblioteca** actualiza el catálogo de cheats. **L: Actualizar app** consulta una versión nueva del propio NRO; también se comprueba al abrir.

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

## Seleccionar desde el overlay

Con el juego abierto, entra en **NinMagic Cheats** desde tu menú de overlays y pulsa **X: Buscar online**. Consulta las fuentes admitidas para el Title ID y Build ID reales de ese juego; no necesitas abrir antes el NRO. Buscar sólo descarga y prepara opciones. Marca con **A**, revisa con **Y** y confirma para aplicarlas. Los controles y requisitos de Tesla están en `Overlay-publicados.txt`.

Al abrir el overlay carga primero su copia local exacta y no activa nada. **X** vuelve a comprobar las fuentes por Internet; durante la consulta puedes seguir jugando con **B** o cancelarla con **X**. Si falla una fuente se conserva la copia comprobada. Una consulta completa sin opciones compatibles puede guardar una lista vacía. Las listas que superan los límites del overlay se gestionan desde el NRO. El overlay no recupera códigos de otra versión ni del antiguo creador.

## Retirar

En la lista de cheats pulsa **L → A**. Con el juego abierto retira los códigos que NinMagic activó en ese proceso. Con el juego cerrado deshace la última instalación de archivos y recupera su copia anterior.

Después cierra y vuelve a abrir el juego para reiniciar los valores temporales: retirar un cheat del motor no revierte necesariamente un valor que ya escribió, y una partida guardada después de usarlo conserva los cambios guardados. La aplicación no borra tus partidas.

Los archivos instalados son `atmosphere/contents/TITLEID/cheats/BUILDID.txt` y `toggles.txt`; sus copias están en `config/NinMagicCheats/backups/`. `live.bin` conserva el registro necesario para retirar los códigos activados en directo. No borres esos registros si necesitas deshacer cambios.

Las copias y registros antiguos de instalaciones con mods deben conservarse para su recuperación con la versión anterior. Esta versión no instala ni retira mods.

## Compatibilidad y diagnóstico

Antes de aplicar se vuelve a leer el Build ID real y se exige la coincidencia exacta del Title ID y Build ID del archivo. En directo se comprueban también el proceso y su identificador. No se elige el código de otra versión aunque el nombre del juego coincida.

Se comprueban el formato, los maestros, los conflictos estáticos detectables y la capacidad total del motor de Atmosphère: como máximo 1024 palabras activas, contando también los códigos que ya estaban cargados. Una activación IPC correcta por sí sola no demuestra que el cheat produzca su efecto.

**Ningún catálogo externo permite garantizar al 100 % el efecto de un cheat ni que el juego nunca se cierre.** La aplicación confirma identificadores y estado del motor; no presenta eso como una prueba del efecto dentro del juego.

La aplicación guarda un diagnóstico limitado en `config/NinMagicCheats/diagnostico-cheats.txt` al consultar, aplicar, retirar y salir. Contiene identificadores, nombres y estado del motor; no lee la memoria de la partida.

## Fuentes y servidor propio

Se utilizan estas fuentes de cheats publicados:

- [HamletDuFromage/switch-cheats-db](https://github.com/HamletDuFromage/switch-cheats-db/releases).
- [Tomvita/NXCheatCode](https://github.com/tomvita/NXCheatCode): catálogo publicado `titles.zip`, compilado a partir de aportaciones de GBATemp.
- [sthetix/nx-cheats-db](https://github.com/sthetix/nx-cheats-db): catálogo general `contents_complete.zip`, consultado tanto por el NRO como por el overlay.
- [Tomvita/MyNXCheats](https://github.com/tomvita/MyNXCheats): archivo canónico publicado como `<TID>/<BID>.txt` en los lanzamientos del autor.
- [Arch9SK7/MyNXCheats](https://github.com/Arch9SK7/MyNXCheats): ZIP pequeño del autor, lectura sólo del archivo con TID/BID exactos. Un paquete que incorpore dependencias de parches se rechaza; no se instalan mods.
- [bad1dea/NXCheats](https://github.com/bad1dea/NXCheats): selección fijada a una revisión de 22 archivos para 20 juegos, sin los parches IPS ni archivos comprimidos acompañantes. Se actualiza al revisar una nueva versión de NinMagic; no se anuncia como seguimiento automático de todos los cambios del autor.
- [OblivionReign en GBATemp](https://gbatemp.net/posts/10902179/): selección documentada exclusivamente para Mario Wonder `FF773E90972D544E`. [Procedencia, prueba y retirada](docs/wonder-1.2.1.md).
- [ibnux/switch-cheat](https://github.com/ibnux/switch-cheat): fuente histórica, con archivos por Title ID y Build ID.
- [OldManKain/Switch-Cheats-Mods-Saves](https://github.com/OldManKain/Switch-Cheats-Mods-Saves): se consultan sólo sus archivos de cheats por Title ID/Build ID; no se descargan mods ni partidas.

La fuente específica de FPS, resolución y gráficos se ha retirado de las consultas. Los ajustes visuales que aparezcan en una base general también se filtran de las opciones disponibles. Los códigos idénticos con los mismos maestros se muestran una vez, conservando sus orígenes. Las variantes con maestros distintos permanecen separadas.

[CheatSlips](https://www.cheatslips.com/homebrews/aio-switch-updater) exige una cuenta y un token personal para su API; no se presenta como una integración automática. Los códigos obtenidos legalmente pueden incorporarse mediante importación local. GBATemp se utiliza a través del catálogo publicado NXCheatCode y de la selección documentada de OblivionReign; no se rastrean sus páginas en la consola ni se eluden sus protecciones.

No hace falta un servidor propio. Para usar uno HTTPS, consulta `Servidor-propio.txt` incluido en la carpeta de la aplicación.

## Compilar

Requiere devkitPro, devkitA64, libnx, switch-curl, switch-minizip y switch-zlib:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File tools/build.ps1 -Preview
```

El script produce y verifica el NRO y renderiza la interfaz con datos de ejemplo. Las pruebas de PC comprueban archivos y activación simulada; no sustituyen la ejecución de cheats en una consola real.

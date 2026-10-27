# Fuentes de cheats publicados

NinMagic exige Title ID y Build ID exactos. No elige otra versión por parecido del nombre. La selección se limita a cheats de jugabilidad; no hay un proveedor activo de mods, FPS, resolución o gráficos. La coincidencia de identificadores y formato no demuestra el efecto del código dentro del juego.

La 1.4.4 añade una revisión por huella SHA-256 de las once definiciones de Wonder FF773E90972D544E que coincidían con las publicadas para CD6E42AEE7934F4D y dieron lugar a un cierre reportado. Permanecen visibles con el motivo y la referencia 1.0.0 según la fuente, pero se rechazan antes de activar o instalar, incluso desde una caché antigua. No se cambian sus instrucciones ni sus identificadores para intentar hacerlas funcionar. La revisión no declara defectuosos todos los códigos de una fuente ni todos los juegos.

Cuando una consulta completa no encuentra opciones para el BID actual, la aplicación NRO puede mostrar otros Build ID publicados para el mismo Title ID. No convierte esos identificadores en versiones numéricas sin información explícita de la fuente. NIFM se utiliza como diagnóstico; la consulta real sigue exigiendo una respuesta HTTPS verificada del servidor.

## Proveedores automáticos

| Fuente primaria | Consulta | Alcance |
| --- | --- | --- |
| [HamletDuFromage/switch-cheats-db](https://github.com/HamletDuFromage/switch-cheats-db/releases) | Lanzamientos `contents.zip` y `contents_complete.zip` | Catálogo principal con historial y comprobación al abrir el NRO. |
| [Tomvita/NXCheatCode](https://github.com/tomvita/NXCheatCode) | Asset `titles.zip` del último lanzamiento | Catálogo compilado de aportaciones de GBATemp, utilizado también por Breeze/EdiZon SE. Rutas TID/BID exactas. |
| [sthetix/nx-cheats-db](https://github.com/sthetix/nx-cheats-db) | Asset `contents_complete.zip` del último lanzamiento | Catálogo general con rutas TID/BID exactas. Se utiliza el archivo completo: `contents.zip` puede omitir códigos incluidos en el completo. |
| [Tomvita/MyNXCheats](https://github.com/tomvita/MyNXCheats) | Asset canónico `<BID>.txt` del lanzamiento cuyo tag es `<TID>` | Consulta directa del juego. No se descarga el repositorio completo ni se infiere el TID por nombre. Tags con otros nombres y variantes `.v1`, `.v2`… no se seleccionan automáticamente. |
| [ibnux/switch-cheat](https://github.com/ibnux/switch-cheat) | `atmosphere/titles/<TID>/cheats/<bid>.txt` | Fuente histórica. Última modificación comprobada el 26 de octubre de 2026: 26 de abril de 2024. No se anuncia como reciente. |
| [OldManKain/Switch-Cheats-Mods-Saves](https://github.com/OldManKain/Switch-Cheats-Mods-Saves) | Exclusivamente `Titles/<TID>/cheats/<BID>.txt` | Fuente histórica, modificada por última vez el 21 de octubre de 2024. Tras un HTTP404 se prueba únicamente el mismo BID en minúsculas. No se descargan su repositorio, mods, partidas ni imágenes. |

Direcciones utilizadas, sustituyendo los campos entre ángulos por los identificadores reales:

```text
https://github.com/HamletDuFromage/switch-cheats-db/releases/latest/download/contents_complete.zip
https://github.com/HamletDuFromage/switch-cheats-db/releases/latest/download/contents.zip
https://github.com/tomvita/NXCheatCode/releases/latest/download/titles.zip
https://github.com/sthetix/nx-cheats-db/releases/latest/download/contents_complete.zip
https://github.com/tomvita/MyNXCheats/releases/download/<TID>/<BID>.txt
https://raw.githubusercontent.com/ibnux/switch-cheat/master/atmosphere/titles/<TID>/cheats/<bid>.txt
https://raw.githubusercontent.com/OldManKain/Switch-Cheats-Mods-Saves/main/Titles/<TID>/cheats/<BID>.txt
```

Los códigos pertenecen a sus autores. Se conservan nombres, condiciones y palabras originales. Opciones con instrucciones idénticas y maestros equivalentes se reúnen conservando sus orígenes; maestros distintos mantienen las opciones separadas. Las descargas adicionales son caché personal y no se incorporan automáticamente a los paquetes públicos del proyecto.

La comprobación del archivo completo de sthetix del 26 de septiembre de 2026 admitió 5.328 identidades TID/BID de aplicaciones de usuario. Para Wonder, `010015100B514000/FF773E90972D544E` contiene once opciones publicadas, 281 palabras de código; se verificaron CRC, sintaxis e identidad, sin probar su efecto en una consola. Esto no autoriza a sustituir ese Build ID por `CD6E42AEE7934F4D` ni al contrario.

## Consulta y caché

Al seleccionar un juego en el NRO se consultan únicamente estos proveedores. Las consultas por juego se reutilizan durante seis horas. El ZIP de NXCheatCode se comparte entre juegos y usa ETag/Last-Modified para evitar descargas sin cambios. La actualización manual vuelve a comprobar los proveedores.

Cada fuente distingue comprobación por Internet, copia local y archivo exacto encontrado. HTTP404 significa que no existe el asset o la ruta canónicos. Un corte de red, una limitación del servicio o un archivo inválido se indican como fallo y conservan los códigos guardados. Un resultado vacío describe las fuentes consultadas; no demuestra que no exista ningún código en Internet.

Los registros de frescura y ETag pertenecen a su archivo vigente. Si éste está dañado o falta y sólo puede recuperarse `.previous`, se descarga una copia nueva para completar la comprobación; no se usan los validadores del archivo perdido para dar por actualizada otra copia anterior.

La caché adicional está en `sdmc:/config/NinMagicCheats/published-sources/`. Los textos se vinculan a proveedor, URL, TID y BID y llevan CRC. Se comprueba la sintaxis antes de sustituir la copia vigente y se conserva una anterior. El NRO valida y combina los catálogos completos para conservar BID históricos. El overlay comprueba los encabezados del ZIP y el CRC y sintaxis del miembro solicitado, sin descomprimir los demás; conserva los códigos ya consultados en archivos por juego y Build ID. No se extraen rutas del ZIP.

El overlay permite una consulta directa con **X: Buscar online** sin abrir previamente el NRO. Comprueba el juego abierto y consulta sus rutas exactas en las mismas fuentes. No carga el índice completo del catálogo en memoria: lee únicamente los miembros TID/BID correspondientes de los ZIP. La conexión HTTPS utiliza el servicio SSL de la consola con validación del certificado y del nombre del servidor.

NRO y overlay comparten una caché compacta por TID y Build ID completo en `config/NinMagicCheats/published/`. Una consulta fallida o cancelada no sustituye una lista previa por una vacía. El overlay limita el tamaño del texto y las definiciones que admite; una fuente que supera esos límites se rechaza entera y puede consultarse desde el NRO. Buscar nunca activa códigos; la selección se revisa y confirma aparte. El registro `published-sources/last-query.txt` permite distinguir identidad sin comprobar, HTTP404 y errores de conexión o formato.

## Historial principal

El historial preparado en el PC inspeccionó **223 lanzamientos y 423 ZIP**, desde abril de 2020 hasta septiembre de 2026: 3.773 combinaciones TID/BID para 2.491 títulos. Se conservan las identidades encontradas; no significa que todos sus archivos sean válidos. Los defectuosos se rechazan al analizarlos. Para una misma identidad gana el lanzamiento más reciente y, dentro de él, el archivo completo.

Al abrir con Internet se consulta el índice público de lanzamientos y se procesan publicaciones nuevas en lotes limitados. Su registro se confirma en la misma transacción que los archivos: una descarga fallida no marca un lanzamiento como procesado. Si queda historial pendiente se avisa. Las actualizaciones conservan BID antiguos.

El catálogo principal utiliza `catalog-a`/`catalog-b` y `active.txt`; sólo necesita `general.zip` y `complete.txt`. Las cachés anteriores siguen siendo legibles aunque incluyan `graphics.zip`, pero ese archivo y su fuente retirada no se consultan ni indexan. La opción heredada `graphics_url` se ignora. No se borran archivos personales del usuario.

## Fuentes con restricciones

[CheatSlips](https://www.cheatslips.com/homebrews/aio-switch-updater) requiere una cuenta y un token personal de API. Esta aplicación no solicita ese token ni presenta el servicio como proveedor automático. Se pueden importar códigos descargados con autorización mediante `manual-cheats.zip`, con créditos y estructura TID/BID.

GBATemp se utiliza a través del [paquete publicado NXCheatCode](https://github.com/tomvita/NXCheatCode). No se rastrea todo el foro ni se eluden sus protecciones. Aportaciones no cubiertas por los proveedores admitidos pueden importarse manualmente con identificadores exactos. No se garantiza cobertura de todos los juegos ni versiones.

## Servidor propio

No hace falta un servidor propio. Para reflejar el catálogo principal, conserva el ZIP completo y crea `sdmc:/config/NinMagicCheats/sources.ini`:

```ini
general_url=https://tu-servidor.example/cheats/general.zip
```

Opcionalmente `raw_url=https://tu-servidor.example/cheats/contents.zip` añade otro archivo general publicado. Se combina con la copia anterior. El certificado HTTPS debe ser válido. Cada ZIP admite hasta 64 MiB y cada archivo hasta 2 MiB. Rutas aceptadas: `contents/<TID>/cheats/<BID>.txt` o `titles/<TID>/cheats/<BID>.txt`, con una carpeta raíz adicional opcional.

Los proveedores adicionales tienen direcciones oficiales fijas y no requieren cuenta de GitHub. Si quedan limitados o inaccesibles se utiliza su caché.

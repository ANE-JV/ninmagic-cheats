# ninmagic-cheats

Aplicación independiente de NinMagic para Nintendo Switch con Atmosphère. Versión de prueba 1.3.0.

Incluye catálogo de cheats por Title ID y Build ID, creador guiado de búsquedas de memoria y actualización del NRO por HTTPS.

El creador compara lecturas del mismo proceso; una coincidencia no demuestra que sea salud, munición u otra variable. Sus pruebas son experimentales y solo sirven en esa sesión. No se ha verificado un cheat real de Terminator 2D: NO FATE.

La actualización se describe en `update.txt`; los ejecutables se guardan bajo `versions/`. Este repositorio tiene su propio paquete y no depende de una página web.

## Primera instalación

[Descargar NRO 1.3.0](https://raw.githubusercontent.com/ANE-JV/ninmagic-cheats/main/versions/v1.3.0/ninmagic-cheats.nro) · [Guía del creador](Creador-guiado.md)

El canal público de actualizaciones está verificado: manifiesto y NRO se descargan sin autenticación. Después de la primera instalación, la aplicación puede comprobar nuevas versiones y pedir confirmación para instalarlas.

Copia el NRO en `switch/ninmagic-cheats/ninmagic-cheats.nro`. La configuración del canal HTTPS es `config/NinMagicCheats/update-url.txt` con:

```
https://raw.githubusercontent.com/ANE-JV/ninmagic-cheats/main/update.txt
```

Para jugar y buscar valores, entra por Álbum manteniendo el juego abierto. ZR abre el creador. La aplicación pedirá confirmar las lecturas y cualquier prueba de escritura.

Las bibliotecas y la fuente conservan sus avisos en `LICENSES/`.

# NinMagic Cheats sobre el juego

La 1.4.5 añade las fuentes Arch9SK7, la selección revisada de bad1dea y las opciones de OblivionReign para Mario Wonder FF773E90972D544E. Se consultan también desde **X**, sin abrir antes el NRO. Los archivos ya verificados se reutilizan seis horas salvo actualización forzada. [Procedencia y retirada de las opciones de Wonder](wonder-1.2.1.md).

El complemento `ninmagic-cheats.ovl` se coloca en `sdmc:/switch/.overlays/`. Requiere Tesla o Ultrahand y un `nx-ovlloader` compatible ya instalado. La aplicación no instala ni cambia ese loader. La combinación que tengas configurada para abrir los overlays se conserva; la predeterminada de libtesla es **L + abajo de la cruceta + pulsar el stick derecho**.

1. Abre el juego real y después **NinMagic Cheats** desde el menú de overlays, manteniendo el juego abierto.
2. Pulsa **X: Buscar/actualizar cheats**. El overlay consulta online los cheats publicados para el **Title ID y Build ID comprobados**, sin abrir la aplicación NRO. La consulta prepara una lista; no activa códigos.
3. Durante la consulta puedes usar **B** para seguir jugando o **X** para cancelarla. Al abrir el overlay se lee primero la lista local disponible; la búsqueda online se solicita con X.
4. **Arriba/abajo** mueve la selección. **A** marca o desmarca una casilla. **R: Detalle** muestra el nombre original y sus condiciones, incluidos los botones del autor.
5. **Y: Revisar** muestra el número de cheats marcados y los primeros nombres. **A** en esa confirmación solicita habilitarlos para el juego abierto; **B** vuelve a la lista sin aplicar.

Las casillas representan la próxima selección. **ON**, **OFF**, **SIN CARGAR** y **SIN COMPROBAR** muestran por separado el estado que se pudo leer del motor. Marcar no activa y desmarcar no apaga un código que ya estaba habilitado. Al confirmar se habilitan los marcados y los demás conservan su estado.

**L: Quitar mis cheats** abre otra confirmación; **A** retira las entradas registradas por NinMagic y recupera los estados anteriores que consten en su recibo. No borra otros cheats ni sus archivos de la SD. Retirar un código no restaura necesariamente valores ya cambiados ni una partida guardada; reinicia el juego si hace falta.

El informe de aplicación o retirada se muestra al terminar. Conserva los botones y condiciones del autor dentro del juego: tener el código habilitado no garantiza que su efecto sea permanente ni que no requiera pulsar un botón.

**B** oculta el overlay y devuelve el mando al juego desde la lista; desde una confirmación, detalle o ayuda, vuelve primero a la lista. **ZL** cambia el panel entre izquierda y derecha. **-** abre la ayuda. **+** sale al menú de overlays cuando termina la operación en curso.

La lista guardada permite volver a consultar los cheats aunque no haya conexión. Si una actualización online falla y existe una copia válida del mismo juego y Build ID, se conserva como alternativa; revisa el aviso que aparece en pantalla. La lista no se adapta a otra actualización del juego. Si no se encuentran cheats publicados compatibles con esa versión, puedes repetir la consulta con X.

**Consulta incompleta** significa que no se pudieron comprobar todas las fuentes. Un error de conexión no demuestra que falten cheats; las opciones guardadas válidas siguen disponibles. **Sin cheats compatibles** sólo se muestra después de una consulta completa, guardada y verificada. Una lista local vacía sin esa comprobación aparece como **Sin comprobar**.

La 1.4.4 registra el servidor, la etapa y el código de error de conexión en `config/NinMagicCheats/published-sources/last-query.txt`. Ese diagnóstico no incluye rutas de descarga firmadas ni datos de la partida. La causa concreta de una conexión fallida depende del resultado registrado; la coincidencia de identificadores no demuestra el efecto de un código.

Si no se pudo verificar el Build ID, se muestra **Build ID sin comprobar** y el error de la comprobación. Eso todavía no determina si hay cheats compatibles. X permite reintentar la consulta del juego.

La aplicación NRO es opcional para importar `config/NinMagicCheats/manual-cheats.zip` y gestionar listas demasiado grandes para la memoria del overlay. Selecciona el juego y entra a sus cheats desde la aplicación para preparar esa copia local. Después regresa al overlay; al abrirse comprueba la lista guardada. La consulta online directa no requiere este paso.

La aplicación y el overlay comparten el recibo de retirada. Usa un solo frontend de NinMagic cada vez. Cerrar el overlay espera a que termine su hilo de trabajo antes de descargar el código. El logo es el mismo original de la aplicación; las vistas del PC son ejemplos de interfaz, no pruebas de ejecución en hardware.

## Códigos en revisión y versiones

La aplicación compara el Title ID y el Build ID reales antes de aplicar. Si no coinciden, se rechaza la asignación. En la aplicación NRO, una consulta completa sin códigos puede mostrar otros Build ID publicados para ese mismo juego. No se infiere una versión numérica si la fuente no la identifica.

Los once códigos de la lista reportada de Mario Wonder FF773E90972D544E quedan en revisión por huella exacta. También aparecen publicados para CD6E42AEE7934F4D (1.0.0 según la fuente). No se permite volver a marcarlos ni aplicarlos en FF77, incluso desde cachés antiguas o con otro nombre. Si ya figuraban ON se conserva ese estado visible; bloquear una nueva activación no retira por sí solo lo que estuviera cargado. L → A permite retirar los códigos registrados por NinMagic.

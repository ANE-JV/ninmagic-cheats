# NinMagic Cheats sobre el juego

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

Si no se pudo verificar el Build ID, se muestra **Build ID sin comprobar** y el error de la comprobación. Eso todavía no determina si hay cheats compatibles. X permite reintentar la consulta del juego.

La aplicación NRO es opcional para importar `config/NinMagicCheats/manual-cheats.zip` y gestionar listas demasiado grandes para la memoria del overlay. Selecciona el juego y entra a sus cheats desde la aplicación para preparar esa copia local. Después regresa al overlay; al abrirse comprueba la lista guardada. La consulta online directa no requiere este paso.

La aplicación y el overlay comparten el recibo de retirada. Usa un solo frontend de NinMagic cada vez. Cerrar el overlay espera a que termine su hilo de trabajo antes de descargar el código. El logo es el mismo original de la aplicación; las vistas del PC son ejemplos de interfaz, no pruebas de ejecución en hardware.

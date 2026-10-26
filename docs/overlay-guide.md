# NinMagic Creador sobre el juego

El archivo `ninmagic-creator.ovl` se coloca en `sdmc:/switch/.overlays/`. Necesita un menú Tesla o Ultrahand y un `nx-ovlloader` ya instalado y compatible con tu sistema. Este archivo no instala ni actualiza el loader; la compatibilidad concreta con firmware 23 debe comprobarse en la consola.

Abre un juego real y luego el menú de overlays. La combinación predeterminada de libtesla es **L + abajo de la cruceta + pulsar el stick derecho**; si configuraste otra combinación, usa la tuya. Elige **NinMagic Creador**.

En el panel, **arriba/abajo** mueve la selección y **A** elige. **B** vuelve; desde el menú principal oculta el panel y devuelve el mando al juego. **-** abre la ayuda. **X** en el menú principal cancela una lectura en curso o vuelve a consultar el juego cuando está libre.

1. Elige **Preparar nueva búsqueda**. Puedes cambiar la finalidad, puntos/barra o número visible y el tipo de dato. Las finalidades son etiquetas: no identifican automáticamente vida, munición, dinero o movimiento.
2. **Revisar e iniciar** abre una confirmación. Al conectar el motor, Atmosphère puede cargar cheats que ya existan en la SD. Solo tras pulsar **A** empieza la lectura y se oculta el panel. El hilo continúa mientras juegas.
3. Abre de nuevo NinMagic y elige **Comparar lo que cambió**. Para puntos blancos de salud, prueba *Cambió* después de recibir daño, luego *No cambió* mientras conservas la salud y otra vez *Cambió* después de recibir daño. *Disminuyó* supone que el valor interno baja; algunos juegos lo representan de otra manera.
4. Una sola coincidencia tras al menos tres lecturas permite **Revisar candidato**. **X** edita el valor a fijar: izquierda/derecha mueve el cursor, arriba/abajo cambia el carácter, X añade un dígito, Y borra, A guarda y B cancela.
5. **A** revisa la prueba experimental y otro **A** la confirma. Se bloquea con otros cheats activos o un código maestro cargado. Comprueba dentro del juego qué modifica; una dirección única no demuestra que controle la función buscada.

**Panel a la izquierda/derecha** cambia el lado con A. **Mostrar HUD y seguir jugando** mantiene un indicador pequeño y devuelve el mando al juego; los botones normales no ejecutan acciones de NinMagic. La combinación del overlay oculta el HUD; repítela para volver al panel interactivo.

**Quitar mis cheats** pide confirmar antes de retirar los códigos registrados por NinMagic en esa sesión. No restaura necesariamente los valores que ya cambiaron ni una partida guardada; reinicia el juego si hace falta. Las pruebas son solo de esa sesión y no se exportan como cheats portables.

Ocultar el panel conserva el hilo. Para salir al menú de overlays, cancela primero con X y espera a que termine la lectura. Al cerrar, el hilo se cancela y se espera su salida antes de descargar el overlay. Mantén el mismo juego y la misma sesión: reiniciarlo invalida las direcciones.

La pantalla muestra progreso y cobertura parcial; una gran cantidad de coincidencias puede continuar filtrándose desde la SD. El overlay usa una carpeta de búsqueda independiente del NRO y comparte el recibo de retirada. Usa un solo frontend de NinMagic cada vez. El logo es el mismo original de la aplicación.

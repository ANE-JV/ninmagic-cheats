# NinMagic Creador sobre el juego

El archivo `ninmagic-creator.ovl` se coloca en `sdmc:/switch/.overlays/`. Necesita un menú Tesla o Ultrahand y un `nx-ovlloader` ya instalado y compatible con tu sistema. Este archivo no instala ni actualiza el loader; la compatibilidad concreta con firmware 23 debe comprobarse en la consola.

Abre un juego real y luego el menú de overlays. La combinación predeterminada de libtesla es **L + abajo de la cruceta + pulsar el stick derecho**; si configuraste otra combinación, usa la tuya. Elige **NinMagic Creador**.

En el panel, **arriba/abajo** mueve la selección y **A** elige. **B** vuelve; desde el menú principal oculta el panel y devuelve el mando al juego. **-** abre la ayuda. **X** en el menú principal cancela una lectura en curso o comprueba el motor y el valor actual cuando está libre, sin habilitar códigos ni escribir en el juego. **Y: Recuperar paso anterior** está disponible cuando hay una búsqueda y más de una lectura, sin otra operación en curso.

1. Elige **Preparar nueva búsqueda**. Puedes cambiar la finalidad, puntos/barra o número visible y el tipo de dato. Las finalidades son etiquetas: no identifican automáticamente vida, munición, dinero o movimiento.
2. **Revisar e iniciar** abre una confirmación. Al conectar el motor, Atmosphère puede cargar cheats que ya existan en la SD. Solo tras pulsar **A** empieza la lectura y se oculta el panel. El hilo continúa mientras juegas.
3. **Recibe el daño o cambia el valor antes de abrir el panel y pulsar A para comparar.** Después espera a que termine la lectura. Para puntos blancos de salud, prueba *Cambió* después de recibir daño, luego *No cambió* mientras conservas la salud y otra vez *Cambió* después de recibir daño. *Disminuyó* supone que el valor interno baja; algunos juegos lo representan de otra manera.
4. Una sola coincidencia tras al menos tres lecturas permite **Revisar candidato**. **X** edita el valor a fijar: izquierda/derecha mueve el cursor, arriba/abajo cambia el carácter, X añade un dígito, Y borra, A guarda y B cancela.
5. **A** revisa la prueba experimental y otro **A** la confirma. Se bloquea con otros cheats activos o un código maestro cargado. Comprueba dentro del juego qué modifica; una dirección única no demuestra que controle la función buscada.

Desde 1.3.6, una búsqueda nueva empieza en 8 bits y puede incluir Heap verificado en ALIAS, además de MAIN/HEAP. Los otros tipos siguen disponibles como ajuste avanzado. Inicia una referencia nueva para aprovechar esa cobertura: las referencias antiguas no se amplían automáticamente ni recuperan las direcciones que ya habían descartado. Mantén el juego en pausa y la salud estable hasta que aparezca **Referencia guardada**. Una lectura amplia puede tardar varios minutos; B oculta el panel y permite volver a consultarlo con la combinación habitual.

El límite es **4 GiB menos 64 KiB** por referencia, compatible con FAT32; se muestra la cobertura parcial. Los bloques se guardan en la microSD y, en el caso máximo, las referencias anteriores y temporales pueden necesitar unos 14 GiB libres.

El menú conserva **Última prueba: aplicada / error / retirada** aunque al reabrir recupere la búsqueda. Ese resultado histórico se muestra separado de **Motor: habilitado / deshabilitado / sin cargar / sin comprobar** y de **Lectura: coincide / no coincide / sin comprobar**. También aparecen el valor solicitado y el leído completos. **R: Informe** muestra el detalle; **X** repite la comprobación actual. Que el motor tenga un código habilitado o que un número coincida no demuestra que represente salud. Si la sesión no coincide o no se puede confirmar, la lectura se muestra sin comprobar. Al recargar el overlay desde su menú puede recuperarse el código del recibo sin que se conserve el resultado del A anterior; se indica como código registrado.

Si un filtro pasa de dos coincidencias a cero, el cero se conserva y se muestra. Vuelve al menú principal y pulsa **Y** para recuperar explícitamente el paso anterior, si su copia corresponde a la misma sesión y supera la comprobación de integridad. Esto solo recupera los datos de búsqueda: no cambia la memoria del juego, no recupera salud y no identifica aquellas dos direcciones. Después puedes elegir otra comparación. En el creador del NRO, el mismo control es **ZL: Deshacer**.

**Panel a la izquierda/derecha** cambia el lado con A. **Mostrar HUD y seguir jugando** mantiene un indicador pequeño y devuelve el mando al juego; los botones normales no ejecutan acciones de NinMagic. La combinación del overlay oculta el HUD; repítela para volver al panel interactivo.

**Quitar mis cheats** pide confirmar antes de retirar los códigos registrados por NinMagic en esa sesión. No restaura necesariamente los valores que ya cambiaron ni una partida guardada; reinicia el juego si hace falta. Las pruebas son solo de esa sesión y no se exportan como cheats portables.

Si no hay códigos propios que retirar, se indica sin crear una prueba fallida ni bloquear la búsqueda. La referencia inicial se muestra como **Referencia guardada**, aunque exista un informe de una prueba anterior; el contador de coincidencias empieza a ser útil después de la primera comparación.

Ocultar el panel conserva el hilo. Para salir al menú de overlays, cancela primero con X y espera a que termine la lectura. Al cerrar, el hilo se cancela y se espera su salida antes de descargar el overlay. Mantén el mismo juego y la misma sesión: reiniciarlo invalida las direcciones.

La pantalla muestra progreso y cobertura parcial; una gran cantidad de coincidencias puede continuar filtrándose desde la SD. El overlay usa una carpeta de búsqueda independiente del NRO y comparte el recibo de retirada. Usa un solo frontend de NinMagic cada vez. El logo es el mismo original de la aplicación.

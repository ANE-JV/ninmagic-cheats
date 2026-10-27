# Wonder 1.2.1: procedencia y uso

Estas opciones proceden de [OblivionReign, publicación original del 30 de agosto de 2026](https://gbatemp.net/posts/10902179/), número 74069 del hilo y **ID real 10902179**. También puede consultarse la [página pública con el mensaje señalado](https://gbatemp.net/threads/cheat-codes-ams-and-sx-os-add-and-request.520293/page-3704#post-10902179).

El autor declara **Super Mario Bros. Wonder + Meetup in Bellabel Park**, versión **1.2.1**, Title ID **010015100B514000** y Build ID **FF773E90972D544E**. La coincidencia de esos identificadores permite ofrecer las opciones publicadas para esta actualización; **NinMagic no ha comprobado su efecto en una consola**.

El [TXT curado](../catalog/oblivionreign/contents/010015100B514000/cheats/FF773E90972D544E.txt) ofrece **God Mode** y **Max/ Infinite Bellabel Water**, conservando todas sus palabras de código originales. Sólo se añadieron comentarios de procedencia y corchetes al título de Bellabel Water. No contiene maestros ni activa opciones automáticamente. Ambas definiciones son distintas de las once que siguen en revisión.

1. Mantén abierto Wonder con la versión indicada. Retira los códigos anteriores de NinMagic con **L → A** y cierra y vuelve a abrir el juego antes de probar estas opciones.
2. Consulta sus cheats y marca **God Mode** por separado. La casilla sólo prepara la selección. Pulsa **Y para revisar** y después **A para confirmar**. Respeta el resultado que muestre la aplicación y el estado que pueda leer del motor.
3. **Max/ Infinite Bellabel Water** corresponde al recurso de **Bellabel Park** del contenido mencionado por el autor. No es vida ni agua genérica para cualquier fase. **Si ese contenido no está activo o no reconoces el recurso, no la actives.** Su escritura utiliza una cadena de punteros; que el archivo se lea correctamente no demuestra que su efecto sea correcto. God Mode es la única opción propuesta para una primera prueba separada.

## Retirar y restaurar

**L → A** retira las entradas que NinMagic pueda identificar como propias. El recibo conserva estados del motor, pero no los bytes originales de la memoria del juego. God Mode modifica una instrucción; **cerrar y volver a abrir el juego después de retirarlo es la vía recomendada para deshacer ese parche**. Los valores que ya se hayan guardado en una partida no se revierten.

El mensaje original también incluye **Restore code** para esa única instrucción. Se conserva como referencia en la fuente y **no se ofrece como una opción de la lista normal**, para evitar confundir la activación con su restauración. God Mode y Restore escriben valores distintos en el mismo destino; la revisión de conflictos de NinMagic rechaza que se seleccionen juntos. Restore tampoco recuperaría los valores de Bellabel Water ni cambios guardados en la partida.

Para volver al estado inicial del programa, utiliza la retirada y el reinicio del juego indicados arriba. Ninguna de estas opciones autoriza reutilizar los códigos con otro Build ID.

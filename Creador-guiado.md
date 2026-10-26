# Creador guiado de NinMagic 1.3.0

El creador compara valores de la memoria del juego. Las finalidades —salud, munición, vidas, magia/energía, kits/objetos, dinero y velocidad/salto— son etiquetas para organizar la búsqueda. No identifican automáticamente qué controla una dirección. Velocidad/salto requiere estudiar un valor numérico; no genera un parche de física.

1. Abre el juego real y entra a NinMagic desde **Álbum**, dejándolo en segundo plano. En la biblioteca o en sus cheats, pulsa **ZR: Crear**. Funciona también cuando no hay cheats publicados para esa versión.
2. Usa **R** para elegir la finalidad y **L** para indicar si ves puntos/barra o un número. **A** introduce un número visible. **X** cambia el tipo de dato como ajuste avanzado: entero de 8, 16 o 32 bits, o decimal de 32 bits.
3. Pulsa **Y: Revisar inicio** y confirma con **A**. Al conectar el motor, Atmosphère puede cargar los cheats existentes en la SD. La búsqueda y los filtros leen datos; no escriben ni pausan la memoria del juego.
4. Vuelve al juego con **HOME**, cambia el valor y abre NinMagic otra vez desde Álbum. Mantén el mismo juego y la misma sesión: no lo cierres ni reinicies. Una búsqueda guardada se recupera si corresponde a esa misma sesión; su finalidad vuelve a mostrarse como **Otro valor** porque esa etiqueta no se guarda con los datos.
5. En resultados, **izquierda/derecha** elige *Disminuyó*, *Aumentó*, *Cambió*, *No cambió* o *Igual al valor escrito*. **X** edita el valor exacto y **Y** compara.

Para salud representada por puntos blancos, elige **Salud → Puntos o barra**; no inventes un número para esos puntos. Guarda la referencia, pierde un punto y filtra con **Disminuyó**. Vuelve a jugar, pierde otro y compara otra vez. Esta secuencia es una hipótesis: algunos juegos representan la salud de otra manera.

La prueba exige **una sola coincidencia y al menos tres lecturas**: la inicial y dos comparaciones. Se muestran direcciones cuando quedan veinte o menos. Una coincidencia única todavía puede controlar algo diferente.

Pulsa **A** para revisar el candidato. En la confirmación, **X: Valor a fijar** permite cambiar el valor que se intentará mantener; **A** confirma la prueba experimental. Se bloquea si hay otros cheats activos o un código maestro cargado. Comprueba el efecto dentro del juego. Desde los resultados, **L** retira los códigos registrados por NinMagic.

La prueba sirve solo para esa sesión; no se exporta como cheat portable. Retirar el código no restaura necesariamente los valores que ya cambió, ni los cambios guardados en la partida. Reinicia el juego si hace falta.

La pantalla informa de la cobertura parcial: se examinan páginas de datos MAIN/HEAP con lectura y escritura, hasta **512 MiB**. El límite de candidatos es **20.000**; una operación rechazada conserva la búsqueda anterior. Un tipo de dato incorrecto o memoria no examinada puede dejar fuera el valor buscado.

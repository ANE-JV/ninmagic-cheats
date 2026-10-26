# Creador guiado de NinMagic 1.3.6

El creador compara valores de la memoria del juego. Las finalidades —salud, munición, vidas, magia/energía, kits/objetos, dinero y velocidad/salto— son etiquetas para organizar la búsqueda. No identifican automáticamente qué controla una dirección. Velocidad/salto requiere estudiar un valor numérico; no genera un parche de física.

1. Abre el juego real y entra a NinMagic desde **Álbum**, dejándolo en segundo plano. En la biblioteca o en sus cheats, pulsa **ZR: Crear**. Funciona también cuando no hay cheats publicados para esa versión.
2. Usa **R** para elegir la finalidad y **L** para indicar si ves puntos/barra o un número. **A** introduce un número visible. **X** cambia el tipo de dato como ajuste avanzado: entero de 8, 16 o 32 bits, o decimal de 32 bits.
3. Pulsa **Y: Revisar inicio** y confirma con **A**. Al conectar el motor, Atmosphère puede cargar los cheats existentes en la SD. La búsqueda y los filtros leen datos; no escriben ni pausan la memoria del juego.
4. Vuelve al juego con **HOME**, cambia el valor y abre NinMagic otra vez desde Álbum. Mantén el mismo juego y la misma sesión: no lo cierres ni reinicies. Una búsqueda guardada se recupera si corresponde a esa misma sesión; su finalidad vuelve a mostrarse como **Otro valor** porque esa etiqueta no se guarda con los datos.
5. En resultados, **izquierda/derecha** elige *Disminuyó*, *Aumentó*, *Cambió*, *No cambió* o *Igual al valor escrito*. **X** edita el valor exacto y **Y** compara.

Para salud representada por puntos blancos, elige **Salud → Puntos o barra**; no inventes un número para esos puntos. Guarda la referencia, pierde un punto y filtra con **Cambió**. Muévete sin perder salud y compara **No cambió**. Repite **Cambió** después de otro daño. El cambio debe haber ocurrido antes de confirmar la comparación; el buscador no espera al daño posterior. **Disminuyó/Aumentó** supone conocer la dirección de la representación interna y puede descartar candidatos útiles.

Las búsquedas nuevas empiezan en **8 bits** para comparar bytes separados. Puedes elegir otro tipo en el ajuste avanzado si el juego lo necesita. No se cambia el tipo de una búsqueda que ya estaba guardada. Mantén el valor estable hasta que termine la referencia inicial; en una lectura amplia puedes dejar el juego en pausa.

Si una comparación deja cero resultados, vuelve a resultados y pulsa **ZL: Deshacer**; en el overlay, pulsa **Y en el menú principal**. Se comprueba y recupera un único paso anterior de la misma sesión sin leer ni escribir la memoria del juego. Puede recuperar las dos coincidencias previas, pero no las identifica como salud. Si ya se sobrescribió aquel paso en una versión antigua o reiniciaste el juego, la recuperación se rechaza. Con cero resultados no se permite guardar otro filtro vacío.

La prueba exige **una sola coincidencia y al menos tres lecturas**: la inicial y dos comparaciones. Se muestran direcciones cuando quedan veinte o menos. Una coincidencia única todavía puede controlar algo diferente.

Pulsa **A** para revisar el candidato. En la confirmación, **X: Valor a fijar** permite cambiar el valor que se intentará mantener; **A** confirma la prueba experimental. Se bloquea si hay otros cheats activos o un código maestro cargado. Comprueba el efecto dentro del juego. Desde los resultados, **L** retira los códigos registrados por NinMagic.

La prueba sirve solo para esa sesión; no se exporta como cheat portable. Retirar el código no restaura necesariamente los valores que ya cambió, ni los cambios guardados en la partida. Reinicia el juego si hace falta.

La pantalla informa de la cobertura parcial: se examinan páginas de datos MAIN/HEAP y páginas Heap verificadas en ALIAS con lectura y escritura sin ejecución, hasta **4 GiB menos 64 KiB**. La identidad incluye también los límites ALIAS. Las comparaciones grandes se conservan por bloques en la microSD; no se abandonan al superar 20.000 candidatos. Cada comparación usa los valores supervivientes de la lectura anterior y no reincorpora los descartados. Una operación cancelada o fallida conserva la búsqueda anterior. Un tipo de dato incorrecto o memoria no examinada puede dejar fuera el valor buscado.

La primera lectura puede tardar varios minutos. En el caso máximo, las referencias y archivos temporales necesitan unos 14 GiB libres en la microSD. El límite individual es compatible con FAT32. El formato NMCSCN3 guarda la identidad ALIAS; una referencia antigua que carezca de esa identidad no se trata como una búsqueda amplia y requiere iniciar otra, conservando sus archivos hasta que decidas hacerlo.

El complemento lateral experimental usa su propia carpeta `config/NinMagicCheats/scanner-overlay/`. Permite realizar las lecturas mientras el juego sigue funcionando y ocultar el panel sin detener su hilo. Cerrar el overlay sí detiene el trabajo; todavía no es un servicio independiente. El panel no deduce automáticamente qué dirección significa «vida»: hace falta indicar cambios relevantes y comprobar una prueba explícita dentro del juego.

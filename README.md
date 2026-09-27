# Shin Megami Tensei — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Traducción al **español de España** de *Shin Megami Tensei* (真・女神転生, PlayStation, 2001), la
versión de PlayStation del RPG de Atlus de 1992: Tokio, 199X, un programa de invocación de
demonios llega por la red y la ciudad se hunde entre la Ley y el Caos. Esta versión nunca salió
de Japón.

La traducción se distribuye como **parche**. No incluye el juego: necesitas tu propia copia
japonesa para aplicarlo.

## Estado

Última versión: **[v1.0](../../releases/tag/v1.0)**.

| Parte | Estado |
|---|---|
| Guion de la historia | 1.936 mensajes traducidos |
| Conversación con demonios | 798 textos traducidos |
| Tiendas, bares, iglesias y hospital | Traducidos |
| Combate, menús, ayudas, estado y tarjeta de memoria | Traducidos |
| Demonios, razas, objetos, magias y lugares | Traducidos (glosario de 823 nombres) |
| Pantalla de nombre | Rótulos en castellano; letras, hiragana y katakana como el original |
| Vídeos (rótulo de la introducción y fin de partida) | Texto en castellano |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ü Ñ ¡ ¿ « »** |
| Revisión durante una partida | Parcial (ver abajo) |

Detalles técnicos:

- Fuente latina nueva de dos letras por carácter, con el mismo color y sombra que la original.
- El rótulo «Kichijoji, Tokio, 199X» de la introducción y el texto del fin de partida se han
  vuelto a componer en castellano, con los mismos fundidos que el original.

Se quedan como en el original:

- El logotipo y los rótulos gráficos en inglés que forman parte de la imagen del juego
  («NEW GAME», «COMP», «SUMMON», «STATUS», las fases de la luna…).
- Los menús y opciones que el original ya escribe en inglés (MESSAGE SPEED, AUTO BATTLE…) y los
  estados alterados (POISON, PALYZE, STONE…).
- En la pantalla de nombre, los nombres escritos con letras latinas se ven con la fuente ancha
  del original.

### Comprobaciones y trabajo pendiente

Se ha jugado en emulador desde una partida nueva. Se han comprobado:

- La pantalla de título, el sueño del laberinto, la pantalla de nombre y el reparto de puntos.
- La casa del protagonista y la conversación con la madre.
- La pantalla de estado, el menú del COMP y la tarjeta de memoria: cargar una partida y
  suspender y reanudar desde la versión traducida.
- El vídeo de la introducción con su rótulo.

El texto de todo el juego se ha comprobado automáticamente: controles, anchura de línea y
caracteres. La imagen construida se ha contrastado mensaje a mensaje con el texto traducido. El
parche se ha aplicado sobre el BIN japonés original y el resultado se ha comparado byte a byte con
la imagen probada.

**No se ha jugado una partida completa de principio a fin** ni se ha probado en consola real.
**Los combates no se han visto en pantalla**: sus mensajes se han revisado en los datos del disco.
Tampoco se han recorrido dentro de una partida la conversación con demonios, las tiendas, la
Catedral de las Sombras ni los tramos avanzados del guion. El vídeo de fin de partida se ha
comprobado decodificándolo. Unos cuarenta mensajes, casi todos gritos en mayúsculas, dejan un
pequeño hueco entre dos letras. La traducción y su revisión se han hecho con asistencia de IA,
sin revisores humanos independientes. Si encuentras un error, abre una incidencia con una captura.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia de **Shin Megami Tensei (Japón)**, SLPS-03170, en formato BIN/CUE de una sola
   pista.
3. **Comprueba que tu copia es la correcta** antes de nada:

   | | |
   |---|---|
   | Archivo | `Shin Megami Tensei (Japan).bin` |
   | Tamaño | 132.443.472 bytes |
   | MD5 | `59e8eb95e20c5d65dd1158d5a43c850c` |

   ```bash
   md5sum "Shin Megami Tensei (Japan).bin"                 # Linux
   md5 "Shin Megami Tensei (Japan).bin"                    # macOS
   CertUtil -hashfile "Shin Megami Tensei (Japan).bin" MD5   # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto.
4. Aplica el parche con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "Shin Megami Tensei (Japan).bin" parche.xdelta "Shin Megami Tensei (ES).bin"`
5. Comprueba que el BIN resultante mide 134.061.648 bytes y tiene el MD5
   **`0b49fa387aae7c302154b7d17b2b3283`** (v1.0). Es algo más grande que el original: es normal.
6. Crea un CUE para el nuevo BIN, por ejemplo `Shin Megami Tensei (ES).cue`:

   ```
   FILE "Shin Megami Tensei (ES).bin" BINARY
     TRACK 01 MODE2/2352
       INDEX 01 00:00:00
   ```

7. Carga el CUE en tu emulador y empieza una partida nueva.

Aplica cada versión sobre el **BIN japonés original**, no sobre una copia ya traducida.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin relación alguna con
Atlus ni Sega. Aquí no se distribuye el juego ni ninguna parte de él: solo un parche que
modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia y lo hago.

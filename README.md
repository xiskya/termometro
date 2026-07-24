[README-termometro-de-la-escucha.md](https://github.com/user-attachments/files/30332642/README-termometro-de-la-escucha.md)
# Termómetro de la escucha

Autoevaluación interactiva sobre la calidad de la escucha —personal y comunitaria—, pensada para formación en comunicación interna. Es **un espejo, no un examen**: cada persona responde y el termómetro marca su «temperatura» de escucha, con una lectura formativa desde la que crecer.

Archivo: `termometro-de-la-escucha.html` · Herramienta web autónoma (un solo archivo, sin dependencias que instalar).

---

## Qué es

Un cuestionario de **18 frases** que la persona valora según con qué frecuencia le ocurren. A medida que responde, el mercurio del termómetro sube en vivo. Al completar las 18, obtiene:

- Una **lectura** en una de cuatro zonas: *helada → tibia → cálida → ardiente*.
- Una **interpretación formativa** (invitación a crecer, no una nota).
- El **desglose por dimensión**, para ver dónde está más cálida y dónde más fría.
- Su **punto más frío** con una pregunta para llevarse.
- **El contraste real:** la invitación a preguntar a una hermana «¿Te sientes escuchada por mí?».

## Para quién

Formación en comunicación interna, comunidades y equipos. Funciona en dos modos:

- **Individual:** cada persona lo rellena en su móvil o portátil.
- **En grupo:** proyectado, como punto de partida para el diálogo.

## Cómo usarlo

- **Abrir en local:** doble clic en `termometro-de-la-escucha.html` → se abre en el navegador.
- **En una sesión:** publícalo en línea (ver más abajo) y comparte el enlace o un código QR.
- **Da un minuto antes de empezar:** las frases piden recordar hechos concretos y recientes, así que ayuda que hagan memoria de su semana.
- **Guardar el resultado:** el botón *Imprimir / Guardar PDF* deja constancia de la lectura y el desglose. Útil, además, porque el punto más frío se reutiliza en el contrato final.

> **URL publicada:** `https://xiskya.github.io/termometro/`
> Publicada en GitHub Pages. Si algún día cambias esa dirección, habrá que regenerar su QR.

## Estructura del instrumento

Dos bloques y seis dimensiones (tres frases cada una):

**Mi escucha** (personal e interpersonal)
1. Presencia y atención plena
2. Empatía y acogida
3. Apertura y no-juicio

**Nuestra escucha** (comunitaria)
4. Voces diversas y participación
5. Escucha y discernimiento comunes
6. De la escucha a la acción

Escala de frecuencia por frase: *Casi nunca · Rara vez · A veces · A menudo · Casi siempre* (valores 1 a 5).

## Cómo está diseñado para ser honesto

Toda autoevaluación de la escucha tiene el mismo problema: quien peor escucha suele puntuarse alto, porque cada una se juzga por su intención y las demás la viven por sus gestos. Tres decisiones lo corrigen:

- **Frases ancladas a hechos, no a autoimagen.** No «¿con qué frecuencia escuchas sin interrumpir?», sino «en tu última conversación de ayer, escuchaste hasta el final». Recordar es más difícil de maquillar que opinar sobre una misma.
- **Seis frases en negativo**, una por dimensión, repartidas sin patrón. Rompen el piloto automático de contestar todo alto. La cabecera avisa de que las hay, pero no de cuáles.
- **El contraste real al final.** La lectura solo está a medias hasta que se pregunta a otra persona. La distancia entre la propia nota y su respuesta enseña más que el cuestionario entero.

## Cómo se calcula la lectura

Conviene conocerlo para poder explicarlo en clase —y **es imprescindible antes de editar las frases**:

- Las frases marcadas con `rev:true` están redactadas **en negativo** y se puntúan **al revés**: `6 − respuesta`. Así una respuesta alta en «saltaste a dar consejo antes de que terminara» baja la lectura, como debe ser.
- La **lectura** es la media de todas las respuestas ya corregidas (de 1 a 5). Mientras el cuestionario está incompleto, se calcula sobre lo respondido hasta ese momento.
- **Zonas** según esa media:
  - menos de 2,5 → **Escucha helada**
  - 2,5 – 3,4 → **Escucha tibia**
  - 3,5 – 4,2 → **Escucha cálida**
  - 4,3 o más → **Escucha ardiente / plena**
- El **llenado del termómetro** mapea la media al alto del tubo: `(media − 1) / 4`.
- Cada **dimensión** se puntúa como la media de sus tres frases (también con la corrección) y se colorea según la misma escala.

Efecto práctico de las frases invertidas: quien contesta «casi siempre» a todo sin leer no saca 5, sino unos 3,7.

No hay respuestas «correctas»: el valor está en la conversación que abre, no en la cifra.

## Personalizar

Todo el contenido vive en el bloque `<script>` del propio archivo:

- **Frases:** array `ITEMS`. Cada una indica su dimensión (`dim`) y, si está redactada en negativo, lleva **`rev:true`**. ⚠️ Si añades una frase en negativo sin ese flag, el cálculo saldrá al revés; y si quitas el flag de una existente, también.
- **Dimensiones y su pregunta de reflexión:** array `DIMS`.
- **Bloques (Mi escucha / Nuestra escucha):** array `BLOCKS`.
- **Escala:** array `SCALE`.
- **Zonas, textos formativos y colores:** array `ZONES`; los umbrales están en `zoneOf(avg)`.
- **El contraste final:** en el HTML, bloque `<div class="contrast">`.
- **Colores y tipografía:** variables `:root` al principio del CSS (`--cold`, `--cool`, `--warm`, `--hot`, `--accent`, etc.).

Al mantener tres frases por dimensión, el desglose sigue funcionando sin tocar nada más. Y conviene conservar al menos una frase invertida por dimensión.

## Publicar y compartir

Rápido y gratis con **Netlify Drop**: arrastra el archivo a `app.netlify.com/drop` y obtienes una URL al instante. También sirven GitHub Pages, Cloudflare Pages o tu propio WordPress. Con la URL, genera un **código QR** para proyectar en la sesión.

## Privacidad

La herramienta **no guarda ni envía ninguna respuesta**. Todo el cálculo ocurre en el navegador de cada persona; al cerrar o recargar la página, los datos desaparecen. No hay servidor, cuentas ni registro. Puedes decírselo a las participantes con tranquilidad: nadie verá sus respuestas salvo ellas mismas.

## Uso

Libre para formación. Adáptalo, tradúcelo o intégralo en tus materiales según lo necesites.

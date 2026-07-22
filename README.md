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

## Para quién

Formación en comunicación interna, comunidades y equipos. Funciona en dos modos:

- **Individual:** cada persona lo rellena en su móvil o portátil.
- **En grupo:** proyectado, como punto de partida para el diálogo.

## Cómo usarlo

- **Abrir en local:** doble clic en `termometro-de-la-escucha.html` → se abre en el navegador.
- **En una sesión:** publícalo en línea (ver más abajo) y comparte el enlace o un código QR para que cada participante lo abra en su dispositivo.
- **Guardar el resultado:** el botón *Imprimir / Guardar PDF* deja constancia de la lectura y el desglose.

> URL publicada actual: `https://cheery-basbousa-c606e3.netlify.app/`
> Si cambias el nombre del proyecto en Netlify o lo vuelves a desplegar, la URL cambia y habrá que regenerar el QR.

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

## Cómo se calcula la lectura

Conviene conocerlo para poder explicarlo en clase:

- La **lectura** es la media de las respuestas (de 1 a 5). Mientras el cuestionario está incompleto, se calcula sobre lo respondido hasta ese momento.
- **Zonas** según esa media:
  - menos de 2,5 → **Escucha helada**
  - 2,5 – 3,4 → **Escucha tibia**
  - 3,5 – 4,2 → **Escucha cálida**
  - 4,3 o más → **Escucha ardiente / plena**
- El **llenado del termómetro** mapea la media al alto del tubo: `(media − 1) / 4`. Así una media de 1 deja el tubo casi vacío (frío) y una media de 5 lo llena del todo (cálido).
- Cada **dimensión** se puntúa como la media de sus tres frases y se colorea según la misma escala de zonas.

No hay respuestas «correctas»: el valor está en la conversación que abre, no en la cifra.

## Personalizar

Todo el contenido vive en el bloque `<script>` del propio archivo. Para adaptarlo:

- **Frases:** edita el array `ITEMS` (cada frase indica a qué dimensión `dim` pertenece).
- **Dimensiones y su pregunta de reflexión:** array `DIMS`.
- **Bloques (Mi escucha / Nuestra escucha):** array `BLOCKS`.
- **Escala:** array `SCALE`.
- **Zonas, textos formativos y colores:** array `ZONES`; los umbrales están en la función `zoneOf(avg)`.
- **Colores y tipografía generales:** variables `:root` al principio del CSS (`--cold`, `--cool`, `--warm`, `--hot`, `--accent`, etc.).

Al mantener tres frases por dimensión, el desglose sigue funcionando sin tocar nada más. Si cambias el número de frases, revisa que cada dimensión siga teniendo las suyas.

## Publicar y compartir

Rápido y gratis con **Netlify Drop**: arrastra el archivo a `app.netlify.com/drop` y obtienes una URL al instante. También sirven GitHub Pages, Cloudflare Pages o tu propio WordPress. Con la URL, genera un **código QR** para proyectar en la sesión.

## Privacidad

La herramienta **no guarda ni envía ninguna respuesta**. Todo el cálculo ocurre en el navegador de cada persona; al cerrar o recargar la página, los datos desaparecen. No hay servidor, cuentas ni registro. Puedes decírselo a las participantes con tranquilidad: nadie verá sus respuestas salvo ellas mismas.

## Uso

Libre para formación. Adáptalo, tradúcelo o intégralo en tus materiales según lo necesites.

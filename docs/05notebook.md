# 🧠 NotebookLM

> Documento actualizado a **julio de 2026**.

Herramienta de inteligencia artificial desarrollada por **Google** que actúa como un asistente personal basado en tus propios documentos. A diferencia de otros chatbots de IA (como ChatGPT o Gemini), NotebookLM no responde desde su conocimiento general sino **exclusivamente desde los documentos que tú le proporcionas**. Esto lo hace ideal para estudiar, investigar y trabajar con apuntes propios.

![NotebookLM](https://play-lh.googleusercontent.com/qWDLmYCI4Lqzq8J-LhtvWvp1HIPkJb2lqkHjduXM7tnCo7N1tmKxnYdaX7CS2_5pkDuW=w240-h480-rw)

!!! note "NotebookLM no \"inventa\" a partir de la nada"

    Cuando le pides algo, NotebookLM basa su respuesta en las fuentes que hayas subido a ese cuaderno (*notebook*): PDF, Google Docs, presentaciones, páginas web, vídeos de YouTube o incluso audios. Si le preguntas algo que no está en esas fuentes, te lo indica en vez de inventar una respuesta — esto reduce mucho las alucinaciones típicas de un chatbot generalista.

## ¿Qué es un "cuaderno" (notebook)?

Un **cuaderno** es el espacio de trabajo de NotebookLM: agrupa un conjunto de fuentes (documentos, enlaces, vídeos) sobre un mismo tema y, a partir de ellas, puedes pedirle generar resúmenes, preguntas de estudio, audio (podcast), vídeo o incluso un mapa mental. Puedes tener tantos cuadernos como temas distintos trabajes, por ejemplo uno por cada unidad de trabajo del ciclo.

!!! tip "Organización recomendada para un docente"

    Crea un cuaderno por tema o unidad didáctica (ej. "UT03 Virtualización") y sube ahí todos los apuntes, diapositivas y enlaces relacionados. Así, cuando generes un podcast o un cuestionario, NotebookLM solo mezclará información de ese tema concreto y no de todo tu Google Drive.

## Cómo subir fuentes

1. Entra en [notebooklm.google](https://notebooklm.google/){target="_blank"} y crea un cuaderno nuevo o abre uno existente.
2. Pulsa **Añadir fuente**.
3. Elige el origen: subir archivo (PDF, .docx, .txt, audio), pegar un enlace de Google Docs/Slides, pegar la URL de un sitio web, o pegar el enlace de un vídeo de YouTube.
4. Repite para cada documento relacionado con el tema del cuaderno.

![Fuentes NotebookLM](https://chatpdf.com/apple-touch-icon.png)

!!! warning "Límite de fuentes"

    Cada cuaderno admite un número limitado de fuentes (varía según el plan: Free vs. NotebookLM Plus, incluido en Google AI Pro/Ultra). Si tu tema es muy amplio, agrupa el contenido en varios cuadernos temáticos en lugar de intentar meterlo todo en uno solo.

![Google AI](https://wpforms.com/wp-content/uploads/2024/08/google-ai-studio-logo.png)

## Qué se puede generar a partir de un cuaderno

| Formato de salida | Para qué sirve |
|---|---|
| **Audio Overview (podcast)** | Conversación entre dos voces sintéticas que comentan las fuentes; ideal para repasar en el coche o mientras haces otra tarea. |
| **Video Overview** | Versión con diapositivas generadas automáticamente, sincronizadas con una narración. |
| **Guía de estudio** | Resumen estructurado con conceptos clave, términos y preguntas de autoevaluación. |
| **Mapa mental** | Esquema visual interactivo con las ideas principales y sus relaciones. |
| **Cronología / Informe** | Ordena los hechos o datos de las fuentes en una línea temporal o en un informe formal. |
| **Chat con citas** | Preguntas y respuestas directas sobre las fuentes, cada respuesta con la cita exacta de dónde sale la información. |

---

## Prompts propios (se mantienen)

Los siguientes prompts son los que ya usaba el autor de este documento; se mantienen tal cual, cada uno como sección de nivel 2 (`##`) para que sigan apareciendo en el menú de navegación de la página.

## Generar podcast largo

- La duración final debe ser superior a 10 minutos (al menos 600 segundos). Calcula la duración estimando una velocidad media de locución de 150 palabras por minuto, por lo que el guion debe contener un mínimo de 1.500 palabras.
- Si el resultado es más corto de esa duración estimada, vuelve a generarlo automáticamente añadiendo más explicaciones, ejemplos, contexto histórico, anécdotas y comparaciones hasta superar el mínimo.
- Mantén un tono cercano, claro y ameno, como si estuvieras hablando con una audiencia general interesada en el tema.
- No omitas detalles relevantes y añade información complementaria para facilitar la comprensión, incluso si no está presente en el texto original.
- Organiza el guion con un ritmo natural, transiciones suaves y un desarrollo fluido.
- Si no alcanza los 10 minutos, no entregues el resultado y repite el proceso hasta que sí lo cumpla.
- Asegúrate de que el audio generado tenga un nivel de volumen alto y consistente, optimizado para escucharse claramente en un coche con ruido ambiente, incluso con la radio al máximo.

## NotebookLM presentaciones (básico)

Crea una presentación con fondo blanco para principiantes con un estilo llamativo y divertido. Céntrate en las instrucciones paso a paso y sé profesional. Presentación con fondo blanco.

## Resumir canal de YouTube

Añade como fuente los vídeos más relevantes de un canal de YouTube (pegando sus enlaces uno a uno) y pide un resumen conjunto: qué temas trata el canal, qué enfoque tiene, y un listado de los 5-10 vídeos más útiles para el tema que estás preparando, con el motivo por el que cada uno es relevante.

---

## Prompts más famosos de la comunidad (añadidos)

Búsqueda realizada en julio de 2026 sobre los prompts de NotebookLM más compartidos en comunidades como r/notebooklm y guías especializadas. Se han adaptado al español manteniendo la misma estructura de nivel 2 (`##`) para que aparezcan igual en el menú.

## Cinco preguntas esenciales

Fuerza a NotebookLM a extraer una estructura pedagógica en vez de un resumen superficial:

```text
Analiza todas las fuentes de este cuaderno y genera 5 preguntas esenciales
que, al responderlas, capturen las ideas principales y el sentido central de
todas las fuentes. Después responde tú mismo a cada una de esas 5 preguntas
de forma clara y concisa.
```

Convierte una clase de 2 horas en una guía de estudio enfocada en lo importante, en lugar de un resumen genérico.

## Detección de huecos y contradicciones

Actúa como un auditor: identifica qué falta y dónde las fuentes no están de acuerdo entre sí.

```text
Actúa como un auditor crítico de estas fuentes. Indica: (1) qué información
importante parece faltar o quedar sin resolver, (2) en qué puntos las fuentes
se contradicen entre sí o parten de supuestos distintos, y (3) qué preguntas
de investigación quedarían abiertas si solo tuviera estas fuentes disponibles.
```

Ideal para investigación de mercado, memorias de proyectos, o para detectar apuntes desactualizados antes de dar una clase con ellos.

## Audio Overview enfocado (versión corta)

El formato de prompt para "Audio Overview" (podcast corto) más compartido en la comunidad:

```text
Genera un Audio Overview breve, de unos 3 minutos, centrado únicamente en
[tema concreto, ej. "la diferencia entre RAID 1 y RAID 5"]. Sáltate la
introducción genérica y ve directamente a los puntos principales. Prioriza
ejemplos prácticos sobre la teoría.
```

Muy útil cuando el cuaderno es muy amplio pero solo quieres repasar un subtema concreto antes de clase, sin escuchar 15-20 minutos de introducción general.

## Concurso de preguntas con dos presentadores

Un formato de podcast "gamificado" muy compartido, pensado para repasar antes de un examen:

```text
Genera un Audio Overview en formato "concurso": dos presentadores, donde el
primero examina al segundo sobre [TEMA] con un total de 10 preguntas,
mezclando opción múltiple y verdadero/falso. El segundo presentador falla
alguna respuesta de vez en cuando, y el primero le corrige explicando por qué
la respuesta correcta es esa.
```

Funciona muy bien para que el alumnado repase de forma amena un tema antes de un examen, escuchándolo como si fuera un podcast real.

## Síntesis a través de las contradicciones

Para temas donde las fuentes no están de acuerdo entre sí (por ejemplo, comparativas de tecnologías o metodologías):

```text
Sintetiza todas las fuentes de este cuaderno: (1) indica cuál es la postura
mayoritaria y qué fuentes la respaldan, (2) enumera los puntos de desacuerdo
y qué fuente defiende cada postura, (3) señala qué huecos no aborda ninguna
fuente, y (4) resume cuál sería la respuesta más sólida a la pregunta de
investigación, basándote solo en la evidencia disponible en este cuaderno.
```

## Mapa mental de repaso rápido

```text
Genera un mapa mental de este cuaderno con un máximo de 3 niveles de
profundidad. El nivel 1 debe tener como mucho 6 ramas principales, cada una
correspondiente a un bloque temático distinto de las fuentes. No incluyas
detalles menores que no aparezcan explícitamente en las fuentes.
```

El mapa mental generado por NotebookLM es interactivo y sirve como esquema visual de repaso rápido antes de un examen o de una exposición oral.

## Guía de estudio con autoevaluación

```text
A partir de todas las fuentes de este cuaderno, genera una guía de estudio
con tres partes: (1) un resumen de los conceptos clave organizado por
apartados, (2) una lista de términos importantes con su definición breve,
y (3) 10 preguntas tipo test de autoevaluación con la respuesta correcta
marcada al final del documento, no junto a cada pregunta.
```

## Cronología para repasar la evolución de una tecnología

```text
A partir de las fuentes de este cuaderno, genera una cronología de la
evolución de [tecnología/tema] ordenada por fecha, indicando en cada hito el
año, el cambio concreto que se produjo y qué fuente lo respalda. Si dos
fuentes dan fechas distintas para el mismo hito, señálalo explícitamente en
vez de elegir una al azar.
```

## Casos de uso concretos en el aula

![Casos de uso](https://play-lh.googleusercontent.com/qWDLmYCI4Lqzq8J-LhtvWvp1HIPkJb2lqkHjduXM7tnCo7N1tmKxnYdaX7CS2_5pkDuW=w240-h480-rw)

- **Preparación de clase:** sube el temario oficial y tus apuntes propios; pide un mapa mental para estructurar la pizarra y una guía de estudio para no dejarte ningún punto clave.
- **Repaso para el alumnado:** comparte un cuaderno de solo lectura con los apuntes de la unidad y sugiéreles generar su propio Audio Overview para repasar de camino a casa.
- **Corrección de coherencia:** sube varias fuentes sobre el mismo procedimiento técnico (por ejemplo, distintas guías de instalación de un servicio) y usa el prompt de "detección de huecos y contradicciones" para detectar si alguna está desactualizada.
- **Preparación de documentación técnica:** si estás migrando tus apuntes a Markdown para tu web de MkDocs, sube el documento original como fuente y pide un resumen estructurado en apartados como primer borrador antes de reescribirlo tú mismo.

## Extensión y aplicación móvil

NotebookLM está disponible como aplicación independiente en Android/iOS y como acceso web. También se integra con **Google Drive**, de forma que puedes añadir directamente un documento o una carpeta compartida como fuente sin tener que descargarla y volver a subirla.

![NotebookLM app](https://play-lh.googleusercontent.com/qWDLmYCI4Lqzq8J-LhtvWvp1HIPkJb2lqkHjduXM7tnCo7N1tmKxnYdaX7CS2_5pkDuW=w240-h480-rw)

!!! note "Actualización automática de fuentes de Drive"

    Si añades un Google Doc o una Google Slides como fuente (en vez de subir un archivo suelto), NotebookLM detecta cuando actualizas ese documento en Drive y ofrece **resincronizar** la fuente, así no tienes que volver a subirla manualmente cada vez que corriges tus apuntes.

## Resumen ejecutivo para reuniones de departamento

Otro formato muy compartido, pensado para llevar una propuesta a una reunión de equipo docente sin que nadie tenga que leerse todo el documento original:

```text
Genera un resumen ejecutivo de una página a partir de estas fuentes, con la
siguiente estructura: (1) contexto en 2-3 frases, (2) la propuesta o
conclusión principal destacada en negrita, (3) tres argumentos clave que la
respaldan, cada uno con su fuente, y (4) los riesgos o puntos a decidir en
la reunión. No superes las 300 palabras en total.
```

---

## Cómo elegir el prompt adecuado

!!! example "Prompt para pedirle ayuda a NotebookLM sobre sí mismo"

    ```text
    Actúa como experto en NotebookLM de Google. Explícame qué tipos de fuentes
    admite este cuaderno, cuántas fuentes puedo añadir en mi plan actual, y qué
    diferencia hay entre generar un "Audio Overview", un "Video Overview" y un
    mapa mental a partir de las mismas fuentes. Recomiéndame cuál usar para
    repasar antes de un examen y cuál para preparar una clase.
    ```

!!! tip "Combina varios formatos para la misma unidad didáctica"

    Un flujo habitual para un docente: sube los apuntes de la unidad → genera primero una **guía de estudio** para revisar que no falte nada → genera un **mapa mental** para la pizarra el primer día de clase → genera un **Audio Overview** para que el alumnado repase de camino a casa antes del examen.

## Preguntas frecuentes

!!! question "¿NotebookLM sustituye a Gemini o a ChatGPT?"

    No, son complementarios. Gemini/ChatGPT responden con conocimiento general (y pueden inventar si no saben algo); NotebookLM responde solo con lo que hay en tus fuentes, lo que lo hace mucho más fiable para trabajar con apuntes propios, pero no sirve para preguntas generales fuera de esas fuentes.

!!! question "¿Puedo compartir un cuaderno con mis compañeros de departamento?"

    Sí, igual que un documento de Drive: desde el cuaderno, usa la opción de compartir y añade las cuentas de correo de las personas con las que quieras colaborar, o genera un enlace.

!!! question "¿El plan gratuito tiene límites?"

    Sí. NotebookLM Plus (incluido en Google AI Pro/Ultra) amplía el número de cuadernos, de fuentes por cuaderno y de generaciones de Audio/Video Overview al día respecto al plan gratuito.

!!! question "¿Puedo cambiar el idioma del Audio Overview?"

    Sí, se puede generar en varios idiomas distintos al de las fuentes originales; es útil si tus apuntes están en español pero quieres un repaso en inglés para practicar vocabulario técnico, o al revés.

## Limitaciones a tener en cuenta

- **No sustituye la verificación humana.** Aunque cita las fuentes, conviene revisar que la cita es fiel al documento original, especialmente en temas técnicos donde un matiz mal interpretado puede llevar a un error de procedimiento.
- **Los Audio/Video Overview son generados, no grabados por personas.** El tono es natural pero las voces son sintéticas; avisa a tu alumnado de esto si vas a compartir el audio como material oficial.
- **Los cuadernos compartidos heredan los permisos de Drive.** Si revocas el acceso a un documento de Drive usado como fuente, la fuente deja de actualizarse en el cuaderno, aunque el contenido ya generado (resúmenes, audio) puede seguir existiendo.

## Recursos

- [NotebookLM (web oficial)](https://notebooklm.google/){target="_blank"}
- [15 prompts de NotebookLM que funcionan de verdad (God of Prompt)](https://godofprompt.ai/blog/15-notebooklm-prompts-that-actually-work-copy-paste-done/){target="_blank"}
- [30 mejores prompts de NotebookLM 2026 (Techpresso)](https://academy.techpresso.co/prompts/notebooklm-prompts){target="_blank"}
- [10 super prompts de NotebookLM para productividad (Analytics Vidhya)](https://www.analyticsvidhya.com/blog/2026/01/notebooklm-super-prompts-for-pro-level-productivity/){target="_blank"}

# 🎓 Moodle

> Documento actualizado a **julio de 2026**.

**Moodle** es la plataforma de aprendizaje (LMS, *Learning Management System*) de código abierto más usada en Formación Profesional y en la universidad española. En este documento se recogen prompts propios para generar contenido y cuestionarios compatibles con Moodle, además de la herramienta de bloqueo de examen que impide al alumnado salir del cuestionario mientras lo realiza.

![Moodle](https://commons.wikimedia.org/wiki/Special:FilePath/Moodle-logo.svg)

!!! note "Estos prompts no sustituyen la revisión del profesorado"

    Los cuestionarios generados con IA (sobre todo los de opción múltiple) pueden contener errores sutiles de contenido técnico o distractores mal calibrados. Revisa siempre el resultado antes de importarlo a un cuestionario que cuente para nota.

## Prompt básico

Plantilla de partida para pedirle a cualquier IA (Claude, Gemini, ChatGPT) que explique un tema con el nivel y el contexto adecuados antes de generar cualquier otro material:

```text
Actúa como un profesional del sector de la informática especializado en
sistemas y aplicaciones. En estos momentos estás impartiendo clases a un
grupo de 30 alumnos de edades entre 20 y 30 años. Este alumnado parte de un
curso de Formación Profesional de la rama de informática y tiene un nivel
avanzado de conocimientos.

A continuación, quiero que me detalles información y explicación sobre:
[TEMA CONCRETO]
```

!!! tip "Por qué funciona"

    Fijar el rol ("profesional del sector"), la audiencia (30 alumnos, nivel avanzado de FP) y el contexto (estás dando clase) hace que la explicación salga con el tono y la profundidad adecuados sin tener que repetirlo cada vez — puedes guardar esta plantilla como instrucción persistente en un Proyecto de Claude, un Gem de Gemini o un GPT.

## Generador de cuestionarios GIFT (opción múltiple)

**GIFT** es el formato de texto plano que usa Moodle para importar preguntas al Banco de preguntas sin tener que crearlas una a una desde la interfaz web. Este prompt genera un cuestionario completo de opción múltiple directamente en ese formato:

```text
Realiza un cuestionario de 20 preguntas de selección múltiple en formato
GIFT en un solo archivo con las siguientes características:
- Las preguntas están enumeradas a partir del número 100, y el número se
  indica antes del enunciado de la pregunta con ::Número::
- Cada pregunta tiene cuatro opciones, y las opciones deben estar entre
  llaves {}.
- Solo una de las opciones es verdadera y está marcada al inicio por el
  texto "="
- El resto de opciones son falsas y están marcadas al inicio por el texto
  "~%-33.33333%"
- No se deben enumerar las opciones, es decir, no aparecerá a) b) c) o d)
- Un ejemplo del formato de las preguntas es el siguiente, entre comillas
  dobles:
"
::Número::este será el enunciado de la pregunta {
~%-33.33333% opción 1 falsa
~%-33.33333% opción dos falsa
= opción tres verdadera
~%-33.33333% opción 4 falsa
}
"
Los temas de las preguntas son: [LISTA DE TEMAS]
```

!!! example "Por qué el porcentaje es -33,33333%"

    En GIFT, el signo `~` marca una opción incorrecta y el número que sigue es la penalización en porcentaje si el alumno la marca. Con 4 opciones y una sola correcta, `-33.33333%` reparte la penalización de forma que marcar cualquiera de las 3 incorrectas reste lo mismo, mientras que la opción marcada con `=` vale el 100% de la pregunta.

## Otros tipos de preguntas en formato GIFT

Además de opción múltiple, GIFT admite otros formatos de pregunta muy útiles para variar un cuestionario:

### Verdadero / Falso

```text
Genera 10 preguntas de verdadero/falso en formato GIFT sobre [TEMA], con
esta sintaxis exacta:
::Número::enunciado de la pregunta {TRUE}
o
::Número::enunciado de la pregunta {FALSE}
Numera las preguntas a partir de 200.
```

### Respuesta corta

```text
Genera 10 preguntas de respuesta corta en formato GIFT sobre [TEMA], donde
el alumno debe escribir una palabra o un comando exacto (por ejemplo, un
comando de Linux). Usa esta sintaxis:
::Número::enunciado de la pregunta {=respuesta correcta =sinónimo aceptado}
Numera las preguntas a partir de 300.
```

### Emparejamiento (matching)

```text
Genera 5 preguntas de emparejamiento en formato GIFT sobre [TEMA] (por
ejemplo, "asocia cada comando con su función"), con esta sintaxis:
::Número::enunciado de la pregunta {
=elemento 1 -> pareja 1
=elemento 2 -> pareja 2
=elemento 3 -> pareja 3
=elemento 4 -> pareja 4
}
Numera las preguntas a partir de 400.
```

!!! warning "Comprueba los acentos y comillas antes de importar"

    Moodle es sensible a caracteres especiales mal codificados. Si al importar aparecen símbolos extraños en vez de tildes, guarda el archivo `.txt` con codificación **UTF-8** antes de subirlo.

## Cómo usar estos prompts para generar un cuestionario en Moodle

1. Copia el prompt del tipo de pregunta que necesites (opción múltiple, verdadero/falso, respuesta corta o emparejamiento) y sustituye `[TEMA]` por el contenido real de tu unidad.
2. Pégalo en Claude, Gemini o ChatGPT y genera el cuestionario.
3. Copia la respuesta completa y pégala en un archivo de texto plano (`.txt`), guardado con codificación **UTF-8**.
4. En tu curso de Moodle, entra en **Banco de preguntas → Importar**.
5. Elige el formato **"formato GIFT"** en el desplegable de formato de archivo.
6. Selecciona el archivo `.txt` y pulsa **Importar**.
7. Revisa el resumen de preguntas importadas correctamente (y los errores, si los hay) antes de añadirlas a un cuestionario.

![Banco de preguntas](https://commons.wikimedia.org/wiki/Special:FilePath/Moodle-logo.svg)

!!! example "Prompt para pedirle a una IA que te explique el proceso de importación"

    ```text
    Actúa como administrador experto de Moodle. Tengo un archivo de texto con
    preguntas en formato GIFT (opción múltiple). Explícame paso a paso cómo
    importarlas al Banco de preguntas de mi curso, qué categoría te recomiendas
    crear para organizarlas, y cómo puedo después añadir un subconjunto
    aleatorio de esas preguntas a un cuestionario cronometrado.
    ```

## Safe Exam Browser: bloquear la salida durante el examen

**Safe Exam Browser (SEB)** es una aplicación de navegador "en modo kiosco", de código abierto, que se integra de forma nativa con los cuestionarios de Moodle para realizar exámenes vigilados online. Mientras el alumno hace el examen, SEB bloquea la posibilidad de cambiar de aplicación, abrir otras pestañas, buscar en internet fuera del cuestionario o cerrar la ventana hasta que el examen se entrega.

![Safe Exam Browser](https://commons.wikimedia.org/wiki/Special:FilePath/Safe-exam-browser-logo.png)

### Qué hace exactamente

- Abre una ventana de navegador **a pantalla completa**, sin barra de direcciones ni botones de navegación (atrás/adelante/recargar pueden desactivarse).
- **No se puede cerrar** la ventana hasta que el cuestionario se entrega (o hasta que se introduce una contraseña de salida configurada por el profesorado).
- Por defecto **bloquea cambiar a otras aplicaciones**, aunque el profesorado puede permitir explícitamente el uso de aplicaciones concretas durante el examen (por ejemplo, una calculadora).
- Se puede exigir que el alumno **descargue e instale SEB** antes de acceder al cuestionario: si no usa SEB, Moodle no le deja empezar el intento.

### Cómo activarlo en un cuestionario de Moodle

1. Entra en el cuestionario y ve a **Ajustes → Restricciones adicionales en el intento**.
2. En el desplegable **"Requerir el navegador de examen seguro"**, elige una de las opciones:
      - **No requerido.**
      - **Sí, requerir que se use el navegador de examen seguro** (el alumno debe abrir el cuestionario desde la propia app SEB).
      - **Sí, usar el navegador de examen seguro sin una configuración de plantilla adicional.**
3. Si tu centro tiene plantillas de configuración SEB predefinidas (gestionadas por el administrador de la plataforma), selecciona la que corresponda a tu tipo de examen.
4. Guarda los cambios. A partir de ese momento, el enlace del cuestionario solo funcionará si el alumno accede desde la aplicación **Safe Exam Browser**, previamente instalada en su equipo.

!!! warning "El alumnado necesita instalar SEB antes del examen"

    Avisa con antelación de que deben descargar Safe Exam Browser (disponible para Windows y macOS) desde [safeexambrowser.org](https://safeexambrowser.org/){target="_blank"} e instalarlo antes del día del examen, para evitar problemas de última hora por bloqueos de antivirus o permisos de administrador en equipos gestionados por el centro.

!!! example "Prompt para preguntarle a una IA cómo configurar Safe Exam Browser"

    ```text
    Actúa como administrador de Moodle experto en Safe Exam Browser. Quiero
    configurar un cuestionario de 20 preguntas, cronometrado a 45 minutos, que
    solo se pueda realizar desde Safe Exam Browser y que impida al alumno salir
    de la ventana del examen o cambiar de aplicación. Explícame paso a paso qué
    opciones debo activar en "Restricciones adicionales en el intento" y si
    necesito pedirle algo al administrador de la plataforma antes de poder
    usarlo en mi curso.
    ```

## Otros prompts útiles para el profesorado

Estos prompts no son específicos de Moodle, pero se usan habitualmente junto con los cuestionarios generados arriba, por ejemplo para preparar el material teórico antes de convertirlo en preguntas.

### Generador de prompts profesionales

Un "meta-prompt" que ayuda a construir otro prompt bien estructurado a partir de una conversación guiada:

```text
Vas a crear un generador de prompts profesionales tomando el rol de un
ingeniero de prompt. Tu objetivo es crear el mejor prompt para escribir un
texto haciéndome las preguntas correctas. Hazme 1 pregunta y no sigas hasta
que responda, de forma corta y concisa. No enumeres tus preguntas. Para
conseguirlo vas a seguir estos pasos:

- En primer lugar, pregúntame por la temática sobre la que quiero crear el
  texto.
- Cuando sepas la temática, muéstrame 3 posibles roles profesionales que
  puedan redactar este texto.
- Cuando sepas el rol profesional, dame 3 posibles contenidos del texto, de
  forma breve, concisa y clara.
- Cuando sepas el contenido del texto, dame 3 posibles tipos de redacción
  que encajen con todas las órdenes que te he dado hasta ahora.
- Cuando sepas el tipo de redacción, dame 3 opciones para mejorar la
  estructura del texto.
- Finalmente, cuando sepas la estructura del texto, dame 3 posibles
  detalles que puedan mejorarlo.
- Analiza toda la información recibida y muéstrame el formato final del
  prompt, con órdenes claras y concisas, incluyendo tablas de varias filas,
  listas y diferentes tipos de encabezados.
```

### 12 peticiones complejas para tu profesión

```text
Siendo yo (tu profesión), prepárame 12 peticiones complejas y útiles que yo
le pueda formular a la IA.

En una columna el título corto de cada petición, y en otra la petición
desarrollada.

Recuerda redactar cada petición con los suficientes detalles para obtener
una respuesta completa.

Que el desarrollo de las peticiones en la segunda columna comience con:
"Quiero que actúes como... (experto en el tema de la petición)".

Entrégalo en formato de tabla: una columna con el título corto y otra con
la petición desarrollada para la IA.
```

### Generador de prompts para Leonardo AI (imágenes)

```text
You will now act as a prompt generator for a generative AI called "Leonardo
AI". Leonardo AI generates images based on given prompts. I will provide
you basic information required to make a Stable Diffusion prompt; you will
never alter the structure in any way and will obey the following
guidelines.

Prompt structure:
- Photorealistic images: "Subject description in detail, type of image,
  art styles, art inspirations, camera, shot, render related information."
- Artistic images: "Type of image, subject description, art styles, art
  inspirations, camera, shot, render related information."

Word order and effective adjectives matter. Describe the environment,
specify the exact type of image, include art-style keywords, and list any
art inspirations (platforms or named artists) to combine styles. Include
lighting, camera angle, lens and render information at the end of the
prompt. Use (((keyword))) to increase the weight of a specific keyword.

Realistic concepts should not be labelled "real" or "photograph" if they
cannot exist in reality (fantasy or paper-craft scenes). Provide one
prompt per concept in a realistic photographic style, choosing a lens type
and size, without naming an artist for that one.

Rules:
1. I will provide a keyword and you will generate three different prompt
   types with full detail, following the structure above.
2. Provide each prompt inside its own code block for easy copy-paste.
3. Separate different prompts with two blank lines.

Are you ready?
```

## Preguntas frecuentes

!!! question "¿Puedo mezclar preguntas de varios tipos GIFT en el mismo archivo?"

    Sí. Un mismo archivo `.txt` puede contener preguntas de opción múltiple, verdadero/falso, respuesta corta y emparejamiento a la vez; Moodle detecta el tipo de cada una por su sintaxis al importar.

!!! question "¿Safe Exam Browser funciona en tablets o Chromebooks?"

    SEB tiene versión para Windows, macOS e iOS. En Chromebooks, muchos centros usan en su lugar la extensión de Chrome de Google Workspace for Education con restricciones similares (bloqueo de pestañas durante un formulario/examen), que es una alternativa distinta a SEB.

!!! question "¿Qué pasa si a un alumno se le cierra SEB por un corte de luz o fallo del equipo?"

    El profesorado puede configurar una **contraseña de salida de cuestionario** (distinta de la contraseña de acceso) para casos de incidencia, y también puede reiniciar manualmente el intento del alumno desde los ajustes del cuestionario en Moodle.

![Moodle en el aula](https://commons.wikimedia.org/wiki/Special:FilePath/Moodle-icon.png)

![Safe Exam Browser en uso](https://commons.wikimedia.org/wiki/Special:FilePath/Safe-exam-browser-logo.png)

## Recursos

- [Documentación oficial del formato GIFT (MoodleDocs)](https://docs.moodle.org/en/GIFT_format){target="_blank"}
- [Documentación oficial de Safe Exam Browser en Moodle](https://docs.moodle.org/en/Safe_exam_browser){target="_blank"}
- [Descarga oficial de Safe Exam Browser](https://safeexambrowser.org/download_en.html){target="_blank"}

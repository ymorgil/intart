- [PROMPT básico](#prompt-básico)
- [PROMPT para cuestionarios](#prompt-para-cuestionarios)

# PROMPT básico
Actúa como un profesional del sector de la informática especializado en sistemas y aplicaciones. En estos momentos estas impartiendo clases a un grupo de 30 alumnos de edades entre 20 y 30 años. Este alumnado parte de un curso de formación profesional de la rama de informática y tienen un nivel avanzado de conocimientos.
A continuación, quiero que me detalles información y explicación sobre: 

# PROMPT para cuestionarios
Realizar un cuestionario de 20 preguntas de selección múltiple en formato gift en un solo archivo con las siguientes características:
- Las preguntas están enumeradas a partir del número 100 se enumera antes del enunciado de la pregunta con :: Número::
- Cada pregunta tiene cuatro opciones y las opciones deben de estar entre llaves {}.
- Solo una de las opciones es verdadera y está marcada al inicio por el texto "=".
- El resto de opciones son falsas y están marcadas al inicio por el texto "~%-33.33333%"
- No se deben enumeran, es decir, no aparecerá a) b) c) o d)
- Un ejemplo del formato de las preguntas es el siguiente que esta entre comillas dobles:
"
::Número::este será el enunciado de la pregunta {
~%-33.33333% opción 1 falsa
~%-33.33333% opción dos falsa
= opción tres verdadera
~%-33.33333% opción 4 falsa
}
"
Los temas de las preguntas son:















Vas a crear un generador de prompts profesionales para ChtaGPT tomando el rol de un ingeniero de prompt. Tu objetivo es crear el mejor prompt para escribir un texto haciéndome preguntas correctas. Hazme 1 pregunta y no sigas hasta que responda, de forma corta y concisa. No enumeres tus preguntas. Para conseguirlo vas a seguir estos pasos:

- En primer lugar vas a preguntarme por la temática sobre la que quiero crear el texto.
- Cuando sepas la temática, quiero que me muestres 3 posibles roles profesionales que puedan redactar este texto.
- Cuando sepas el rol profesional, quiero que me des 3 posibles contenidos del texto, de forma breve, concisa y clara.
- Cuando sepas el contenido del texto, quiero que me des 3 posibles tipos de redacción que encajen con todas las ordenes que te he dado hasta ahora.
- Cuando sepas el tipo de redacción, vas a darme 3 opciones para mejorar la estructura del texto.
- Finalmente cuando sepas la estructura del texto, vas a darme 3 posibles detalles que puedan mejorar el texto.
- Ahora tienes que analizar toda la información recibida y mostrarme el formato final del prompt, deben ser ordenes claras y concisas, incluyendo que en el texto introduzca tablas de varias filas, listas y diferentes tipos de encabezados.


Siendo yo (tu profesión), Prepárame 12 peticiones complejas y útiles, que yo le pueda formular a la ia.

En una columna el título corto de preguntas y en otra las preguntas desarrolladas.

Recuerda hacer la petición con los sufientes detalles para una respuesta completa, que se le puede realizar a la IA.

Que el desarrollo de las preguntas en la segunda columna comiencen con: “quiero que actúes como… (experto en el tema de la pregunta)»

En formato de tabla, en una columna  solo el título corto de la pregunta y en otra la pregunta desarrollada para la ia


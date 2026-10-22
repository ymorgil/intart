# Cuestionario GIFT para Moodle

## Antes de empezar

Pregúntame: "¿Cuál es el número de la primera pregunta?" y espera mi respuesta. Si digo 100, generarás 100 preguntas numeradas del 100 al 199, todas seguidas en un único bloque de código GIFT, sin dividirlas en partes ni detenerte a mitad.

## Fuentes

* Usa exclusivamente las fuentes de este cuaderno. No inventes comandos, opciones, valores ni conceptos que no aparezcan en ellas.
* Una fuente es un .txt con preguntas existentes: puedes reutilizarlas, corregirlas o mejorarlas, adaptándolas a estas reglas.

## Contenido

1. Dificultad media-alta: casos prácticos, interpretar comandos o configuraciones, distinguir conceptos parecidos. Evita definiciones directas.
2. Cuatro opciones por pregunta, todas de longitud y estructura similar, para que la correcta no destaque.
3. Distractores creíbles del mismo tema; nada de "todas las anteriores" ni "ninguna de las anteriores".
4. Varía la posición de la respuesta correcta y reparte las preguntas por igual entre los contenidos de las fuentes.
5. Sin preguntas repetidas ni casi idénticas.

## Retroalimentación (obligatoria en todas las preguntas)

* Debe tener dos partes: primero indica cuál es la opción correcta y después explica el motivo técnico por el que es verdadera, usando la información de las fuentes.
* La explicación debe aportar información nueva: qué hace, para qué sirve o por qué funciona así. No basta con repetir la opción correcta.
* Mínimo dos frases.
* Incorrecto: "La respuesta correcta es chmod 750."
* Correcto: "La respuesta correcta es chmod 750\. El 7 da lectura, escritura y ejecución al propietario, el 5 lectura y ejecución al grupo y el 0 ningún permiso al resto, que es justo lo que pide el enunciado."

## Formato GIFT

* Título `::Número::` y el número repetido al inicio del enunciado seguido de punto.
* Una opción verdadera con `=` y tres falsas con `~%-33.33333%`.
* Retroalimentación con `####` justo antes de cerrar la llave.
* No enumeres las opciones (sin a, b, c, d).
* Una línea en blanco entre preguntas.
* Escapa con `\` los caracteres `~ = # { } :` cuando aparezcan dentro de enunciados, opciones o retroalimentación.
* No incluyas citas a las fuentes como [1], ni negritas, ni texto fuera del bloque de código.

## Ejemplo

::100::100\. Enunciado de la pregunta { \~%-33.33333% opción falsa = opción verdadera \~%-33.33333% opción falsa \~%-33.33333% opción falsa ####La respuesta correcta es "opción verdadera". Explicación del motivo técnico basada en las fuentes, en al menos dos frases. }

## Comprobación final

Antes de responder, verifica que hay exactamente 100 preguntas correlativas, cada una con un `=`, tres `~%-33.33333%`, llaves bien cerradas y una retroalimentación que explique el porqué, no solo cuál es la correcta.
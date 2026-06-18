# prompts
> Un prompt es una instrucción que le damos a una inteligencia artificial para indicarle qué queremos que haga. Puede ser una pregunta, una orden o una descripción de una tarea. La calidad de la respuesta dependerá en gran medida de la claridad de la instrucción proporcionada. No tiene por qué ser complejo. De hecho, muchos de los problemas al utilizar una IA aparecen porque la instrucción es demasiado vaga, incompleta o ambigua.

## Crear prompts
Para crear buenos prompts basta con responder a cuatro preguntas:

**1. ¿Qué quieres que haga la IA?**
Define la tarea de forma clara. Ejemplo:

> Explica qué es una máquina virtual.

**2. ¿Para quién va dirigida la respuesta?**
Indica el nivel de conocimiento o el público objetivo.
Ejemplo:

> Explica qué es una máquina virtual para alumnado de primer curso de informática.

**3. ¿Cómo quieres recibir la respuesta?**
Especifica el formato deseado.
Ejemplo:

> Explica qué es una máquina virtual para alumnado de primer curso de informática en dos párrafos.

**4. ¿Qué condiciones debe cumplir?**
Añade restricciones, requisitos o detalles importantes.
Ejemplo:

> Explica qué es una máquina virtual para alumnado de primer curso de informática en dos párrafos utilizando un lenguaje sencillo y añadiendo un ejemplo relacionado con Proxmox.

## Estructura
La mayoría de los buenos prompts pueden construirse con esta plantilla:

> Actúa como [rol]. Realiza [tarea]. Está dirigido a [público objetivo]. Genera la respuesta en formato [formato deseado]. Ten en cuenta las siguientes condiciones: [requisitos adicionales].

## Ejemplos prácticos

### Crear contenido teórico

Prompt:

> Actúa como profesor de informática. Explica qué es Docker para alumnado de ASIR. Genera la respuesta en formato Markdown, utilizando lenguaje sencillo y ejemplos prácticos.

### Crear una actividad

Prompt:

> Actúa como profesor de informática. Diseña una actividad sobre máquinas virtuales para alumnado de SMR. Incluye objetivos, instrucciones, recursos necesarios y criterios de evaluación.

### Crear preguntas tipo test

Prompt:

> Actúa como profesor de informática. Genera diez preguntas tipo test sobre Linux con cuatro opciones de respuesta e indica la solución correcta.

### Corregir un trabajo

Prompt:

> Actúa como profesor de informática. Corrige el siguiente trabajo utilizando la rúbrica proporcionada. Asigna una puntuación de 0 a 10 y proporciona un feedback final indicando fortalezas y aspectos de mejora.

### Resumir información

Prompt:

> Resume el siguiente texto en un máximo de 200 palabras utilizando un lenguaje sencillo.

### Generar código

Prompt:

> Actúa como desarrollador Python. Crea un programa que gestione una agenda de contactos utilizando funciones y almacenamiento en un fichero JSON. Comenta el código.

## Errores habituales

### Dar instrucciones demasiado genéricas

Mal prompt:

> Háblame de Linux.

La respuesta puede ser demasiado amplia o no centrarse en lo que realmente necesitas.

Mejor prompt:

> Explica qué es Linux para alumnado de CFGM de Sistemas Microinformáticos y Redes en tres párrafos y compara Linux con Windows.

### No indicar el público objetivo

Mal prompt:

> Explícame Kubernetes.

La IA no sabe si la explicación debe ser para principiantes o expertos.

Mejor prompt:

> Explica Kubernetes para alumnado de ASIR que nunca ha trabajado con contenedores.

### No indicar el formato

Mal prompt:

> Crea información sobre Proxmox.

Mejor prompt:

> Crea una guía sobre Proxmox en formato Markdown utilizando títulos y subtítulos.

## ¿Es necesario usar metodologías de prompting?

No. Las metodologías son simplemente plantillas para organizar información. Lo importante no es memorizar nombres, sino asegurarte de que la IA entiende:

- Qué debe hacer.
- Para quién lo hace.
- Cómo debe responder.
- Qué requisitos debe cumplir.

Si proporcionas esos cuatro elementos, normalmente obtendrás resultados de gran calidad.

## Plantilla universal

Puedes reutilizar esta plantilla para casi cualquier tarea:

> Actúa como [rol]. Realiza [tarea]. Está dirigido a [destinatario]. Genera la respuesta en formato [formato]. Ten en cuenta las siguientes condiciones: [restricciones o requisitos].

## Ejemplo completo

> Actúa como profesor de sistemas informáticos. Explica qué es Proxmox para alumnado de ASIR. Genera la respuesta en formato Markdown. Utiliza un lenguaje sencillo, incluye ejemplos prácticos y limita la explicación a una página.

## Conclusión

Crear un buen prompt no consiste en aprender decenas de metodologías diferentes. Consiste en comunicar claramente qué quieres obtener. Si especificas la tarea, el contexto, el formato y las condiciones, estarás utilizando una técnica de prompting eficaz en la mayoría de situaciones.
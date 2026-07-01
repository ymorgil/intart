# Prompting
Un **prompt** es la instrucción que le das a una IA para indicarle qué quieres que haga. Puede ser una pregunta, una orden o la descripción de una tarea. La calidad de la respuesta depende, sobre todo, de lo clara que sea esa instrucción. La mayoría de los problemas al usar una IA no vienen del modelo, sino de prompts vagos, incompletos o ambiguos. A continuación, se muestran los **elementos clave** que ha de tener un buen prompt:

1. 🎭**ROL** Asignar un rol o persona ayuda a fijar el tono, el punto de vista y el nivel de detalle de la respuesta.  (ej., "Actúa como un experto en marketing...").
2. 📋**Contexto**: Añade detalles sobre tu público, tu objetivo o la situación (ej., "Dirigido a jóvenes emprendedores...").
3. 🎯**Tarea/Objetivo**: Define qué tiene que hacer de forma concisa y directa (ej., "Redacta un post para LinkedIn...").
4. 📊**Formato**: Indica cómo quieres la salida (ej., "Entrégalo en una lista con viñetas y negritas").
5. ⚙️**Restricciones**: Limita el resultado (ej., "Máximo 3 párrafos, tono persuasivo, sin usar lenguaje técnico").
   

        Actúa como [ROL]. 
        Está dirigido a [CONTEXTO].
        Realiza [TAREA].
        Genera la respuesta en formato [FORMATO]. 
        Ten en cuenta las siguientes condiciones: [RESTRICCIONES].

**OTROS COMPONENTES**

- **Dar ejemplos (few-shot)**: mostrar 1-2 ejemplos de lo que esperas como respuesta mejora mucho la precisión, sobre todo en tareas de clasificación, extracción de datos o formatos muy concretos. (ej., "Clasifica el sentimiento de estas frases como positivo o negativo. Ejemplo: "Me encantó el servicio" → positivo.)
- **Pedir razonamiento paso a paso**: en tareas complejas (cálculos, análisis, decisiones con varios factores), pedir que la IA explique su razonamiento antes de dar la respuesta final reduce errores. (ej., "Antes de responder, enumera los factores a tener en cuenta y luego da tu conclusión.")
- **Dividir tareas complejas en partes**: si la tarea es muy grande (un informe largo, un proyecto completo), es mejor pedirla en pasos en lugar de en un único prompt gigante.
- **Iterar**: rara vez el primer prompt es el definitivo. Si la respuesta no es la esperada, ajusta el prompt en lugar de descartar la herramienta.

**ERRORES HABITUALES**

- **Instrucciones demasiado genéricas**
    - ❌ "Háblame de Linux."
    - ✅ "Explica qué es Linux en tres párrafos y compáralo con Windows, para alguien que solo ha usado Windows."
  
- **No indicar el público objetivo**
    - ❌ "Explícame Kubernetes."
    - ✅ "Explica Kubernetes para alguien que nunca ha trabajado con contenedores."

- **No especificar el formato**
    - ❌ "Crea información sobre Proxmox."
    - ✅ "Crea una guía sobre Proxmox en Markdown, con títulos y subtítulos."

## Trucos
**Reglas de oro:** cuanto más específico seas en *qué*, *cómo* y *en qué formato* querés la respuesta, menos vueltas y menos tokens necesitarás `(token: unidad mínima de texto que un modelo de lenguaje procesa; el uso y costo se miden en tokens)`. Para reducir el gasto de tokens debes cumplir:

1. **Sé breve en el prompt y pedí brevedad en la respuesta.** Frases como "responde en máximo 3 líneas" o "sin introducción ni conclusión" evitan relleno.
2. **No pegues documentos enteros si solo necesitás una parte.** Recortá el fragmento relevante antes de pegarlo.
3. **Evitá pedir que el modelo repita tu pregunta o el contexto** antes de responder.
4. **Usá listas/tablas en vez de prosa** cuando el contenido es comparativo o enumerable: una tabla suele ocupar menos tokens que párrafos explicando lo mismo.
5. **Desactivá el "modo pensamiento extendido" (thinking/reasoning) cuando no lo necesites.** Sirve para matemáticas o lógica compleja, pero en tareas simples solo añade tokens de razonamiento que no ves pero que sí se cobran/consumen cuota.
6. **Aprovechá las instrucciones persistentes (system prompt / "Preferencias" / "Proyectos").** Si siempre pedís el mismo tono o formato, configuralo una vez en los ajustes en lugar de repetirlo en cada mensaje.
7. **Empezá un chat nuevo cuando cambies de tema.** El historial de la conversación se reenvía completo en cada turno; una conversación muy larga hace que cada respuesta nueva sea más cara en tokens, aunque tu pregunta sea corta.
8. **Subí el archivo en vez de pegar el texto copiado**, cuando la plataforma lo permita: muchas herramientas procesan el archivo de forma más eficiente que un bloque de texto pegado.
9. **Pedí una sola iteración bien especificada** en vez de "dame algo y lo vamos afinando": cada ida y vuelta de corrección consume tokens nuevos sobre todo el historial anterior.
10. **Usá el modelo más liviano disponible para tareas simples** (clasificar, traducir, resumir cortito) y reservá el modelo más potente solo para lo que realmente lo necesita.

|Ejemplo de prompt "caro" (evitar)|Versión "barata" equivalente|
|||
|Hola, quería pedirte por favor si podrías ayudarme a resumir este texto tan largo que te voy a pegar a continuación, no hace falta que sea muy formal, gracias de antemano: [texto pegado completo de 5 páginas]|Resume en 5 viñetas, sin introducción: [solo el párrafo o sección relevante]|

**PLANES GRATUITOS**

1. **Reservá el modelo "grande/pro" del plan gratuito para lo que realmente lo necesita.** Casi todas las plataformas dan acceso limitado al modelo top y acceso más amplio al modelo liviano (ej. Haiku, Flash, Instant). Usá el liviano para tareas rutinarias y guardá las consultas al modelo potente para lo complejo.
2. **Planificá el prompt antes de enviarlo.** En el plan gratuito, cada mensaje cuenta; escribir el prompt completo (rol + tarea + formato) de una sola vez evita "gastar" 3-4 mensajes corrigiendo lo que pediste mal.
3. **Dividí tareas grandes en partes chicas y bien delimitadas**, en lugar de pedir "hazme todo el proyecto" en un solo mensaje: las respuestas gigantes consumen más cuota y tienen más probabilidad de cortarse.
4. **Aprovechá los reinicios de cuota.** Los planes gratuitos suelen restablecer el límite de mensajes cada pocas horas o cada día: organizá las tareas que más importan para el momento justo después del reinicio.
5. **Limpiá o iniciá conversaciones nuevas seguido.** Un chat que arrastra mucho historial consume más "presupuesto" por turno que uno corto y enfocado.
6. **Combiná herramientas gratuitas según la tarea**, ya que cada plataforma reparte distinto el acceso a sus modelos: por ejemplo, usar una para borradores rápidos y otra para la versión final, repartiendo el consumo entre ambas.
7. **Guardá plantillas propias** (en notas, en un documento, o en la función de "instrucciones personalizadas" si la plataforma la ofrece) para no reescribir cada vez el mismo contexto.

**Checklist rápida antes de enviar un prompt**

    [ ] ¿Definí el rol o contexto necesario?
    [ ] ¿La tarea está en un verbo claro (resume, clasifica, genera, ...)?
    [ ] ¿Especifiqué el formato de salida (lista, tabla, JSON, párrafo corto)?
    [ ] ¿Puse un límite de longitud?
    [ ] ¿Pegué solo el fragmento de texto necesario, no todo el documento?
    [ ] ¿Elegí el modelo más liviano que pueda cumplir la tarea?

## Plantilla y ejemplos
A continuación una plantilla base para estructurar prompts de forma clara y efectiva. No es una fórmula rígida: se puede adaptar a estilo y necesidades. Luego algunos ejemplos prompts


**Rol:** Actúa como [rol/experto específico, ej. "editor técnico con 10 años de experiencia"].

**Contexto:** [Breve descripción de la situación, proyecto o antecedentes relevantes].

**Audiencia:** Está dirigido a [público objetivo, ej. "clientes sin conocimientos técnicos"]

**Objetivo:** Quiero que [petición u objetivo principal] con los siguientes requisitos:
- [Requisito 1]
- [Requisito 2]
- [Requisito 3]

**Tono y estilo:** [Ej. formal, cercano, técnico, persuasivo].

**Formato de salida:** Genera la respuesta en formato [markdown / tabla / lista / código, etc.]. [Especificar si se permiten tablas, imágenes, longitud aproximada, etc.].

**Restricciones:** [Qué evitar, límites de extensión, cosas que NO debe incluir].

**Reglas de interacción:**

1. Antes de responder, hazme preguntas si falta información o hay dudas, no asumas datos: pregunta primero.
3. Si hay más de una interpretación posible, solicita aclaraciones.
4. No generes una solución definitiva hasta que no confirmes las restricciones.

<hr style="height: 1px; background-color: #3aa">

Diseña un menú semanal vegetariano. Está dirigido a una persona que empieza a cocinar. Genera la respuesta en una tabla por días. Ten en cuenta que debe incluir ingredientes fáciles de encontrar y tiempos de preparación cortos.
<hr style="height: 1px; background-color: #3aa">


Analiza la situación desde múltiples perspectivas, identifica oportunidades, riesgos, errores potenciales y aspectos que podría no haber considerado. Si existen varias soluciones, compáralas y clasifícalas de mejor a peor explicando sus ventajas, desventajas y probabilidad de éxito. 
 
Recomienda la mejor opción y desarrolla un plan de acción paso a paso con ejemplos concretos, recomendaciones prácticas y mejoras avanzadas. Prioriza la precisión, la claridad y la utilidad. No te limites a responder lo que se solicita; añade información relevante que aporte más valor al resultado final. Si falta información importante, realiza las preguntas mínimas necesarias; en caso contrario, haz las suposiciones más razonables e indícalas antes de continuar.
<hr style="height: 1px; background-color: #3aa">

A partir de ahora, deja de ser complaciente y actúa como mi asesor brutalmente honesto, de alto nivel, y como mi espejo. No me valides. No endulces la verdad. No me halagues. Desafía mi forma de pensar, cuestiona mis suposiciones y expón los puntos ciegos que estoy evitando. Sé directo, racional y sin filtros. Si mi razonamiento es débil, desmenúzalo y muéstrame por qué. Si me estoy engañando o mintiéndome a mí mismo, señálalo. Si estoy evitando algo incómodo o perdiendo el tiempo, dilo y explícame el costo de oportunidad. Mira mi situación con total objetividad y profundidad estratégica. Muéstrame dónde estoy poniendo excusas, jugando a lo pequeño o subestimando riesgos/esfuerzos. Luego dame un plan preciso y priorizado sobre qué cambiar en mi pensamiento, acciones o mentalidad para llegar al siguiente nivel. No te guardes nada. Trátame como alguien cuyo crecimiento depende de escuchar la verdad, no de sentirse cómodo. Cuando sea posible, fundamenta tus respuestas en la verdad personal que percibas entre mis palabras.

## Mis prompts


### Creador de contenido Big Data Aplicado
````
# 1. Rol del modelo
Actúa como un Asistente Académico Senior experto en Big Data y Pedagogía para Educación Superior Técnica. 
Tu perfil combina un conocimiento técnico profundo sobre arquitecturas de datos, procesamiento masivo y analítica, con la capacidad de estructurar clases magistrales. 
Tu objetivo es ayudarme a preparar material docente de alto nivel.

# 2. Contexto
Soy profesor de informática especializado en Big Data.
- **La asignatura:** "Big Data Aplicado" dentro de un Curso de Especialización.
- **La audiencia:** Estudiantes adultos que ya poseen títulos de Técnico Superior en Informática.Tienen base técnica y están aprendiendo a aplicar tecnologías de Big Data en entornos productivos.
- **Entrada:** Te proporcionaré un tema específico, un listado de puntos clave o subiré un documento/presentación técnica (PDF/PPT).
- **Uso:** El texto generado será el contenido de una presentación de clase (formato 16:9).

# 3. Tareas específicas
Debes seguir este flujo de trabajo estrictamente:

1.  **Análisis preliminar:** Si te adjunto un documento, léelo en su totalidad. Realiza un resumen mental (interno, no me lo muestres) para asegurar que comprendes la totalidad del tema.
2.  **Validación (Paso Crítico):** Antes de generar cualquier diapositiva, si detectas lagunas en la información o ambigüedades en mi petición, **hazme las preguntas necesarias**. Si no hay dudas, procede al paso 3.
3.  **Estructuración:** Organiza la información en exactamente **7 diapositivas** lógicas que cubran todo el contenido del documento o tema proporcionado.
4.  **Generación de contenido:** Redacta el título y el cuerpo de texto para cada diapositiva. El texto debe ser explicativo y denso, diseñado para ser leído y estudiado, no solo como soporte visual.

# 4. Formato de salida
La respuesta debe seguir estrictamente esta estructura para cada una de las 7 diapositivas:

---
**Diapositiva [N]**
**Título:** [Título técnico y descriptivo]
**Contenido:**
[Párrafos de texto explicativo, si fuese necesario añadir alguna lista. Aquí debes desarrollar los conceptos con profundidad técnica. El espacio está pensado para formato 16:9, así que aprovecha el ancho para explicar el "porqué" y el "cómo".]
---

# 5. Restricciones y estilo
- **Longitud:** Cada diapositiva debe tener un contenido de texto en torno a las **100 palabras**.
- **Profundidad:** Evita frases sueltas, eslóganes. Redactados con vocabulario técnico preciso.
- **Consistencia:** Si te paso un documento, asegúrate de que el esquema de las 7 diapositivas abarca todos los puntos clave del archivo original.
- **Estilo visual:** Ten en cuenta que algunas diapositivas llevarán fotos, así que el texto debe complementar la parte visual sin depender de ella.
- **Tono:** Académico, profesional y dirigido a colegas técnicos (adultos), no a niños.
````

### Resolución de dudas BIU
````
# 1. Rol del modelo
Actúa como un Arquitecto de Datos Senior y compañero docente. Eres un experto en Big Data que habla "de tú a tú" con otro experto (yo). 
No necesitas explicarme conceptos básicos de informática, pero sí profundizar en matices complejos de arquitecturas o herramientas específicas. 
Además, tienes una gran capacidad de síntesis pedagógica para traducir esos conceptos complejos en material didáctico.

# 2. Contexto
Yo soy profesor de informática (especialista en Big Data).
- **Situación:** Estoy preparando una clase y tengo una duda específica o quiero refinar cómo explicar un concepto complejo.
- **Audiencia final:** Mis alumnos del curso de especialización (adultos con titulación técnica previa). Entienden código y sistemas, pero están aprendiendo la aplicación específica en Big Data.
- **Entrada:** Te escribiré una duda, un concepto o una comparativa técnica.

# 3. Tareas específicas
1.  **Resolución de la duda (Nivel Experto):** Explícame el concepto como lo harías con un compañero de trabajo. Ve al grano, usa terminología técnica precisa y, si aporta valor, incluye pequeños ejemplos de código (Python/Scala/SQL) o esquemas en texto.
2.  **Generación de recurso didáctico:** Una vez aclarada la duda, redacta el contenido para **UNA sola diapositiva** que yo pueda proyectar en clase para explicar este concepto a los alumnos de forma comprensible pero rigurosa.

# 4. Formato de salida
Estructura la respuesta en dos bloques claramente diferenciados:

---
### 💬 Aclaración entre colegas
[Aquí tu explicación técnica para mí. Tono profesional, directo y colaborativo. Incluye ejemplos breves si son necesarios.]

### 🖥️ Diapositiva para clase
**Título:** [Título atractivo y descriptivo del concepto]
**Texto de la diapositiva:**
[Redacción del contenido para la diapositiva. Debe ser un texto cohesionado (aprox. 100 palabras) que explique el concepto, el caso de uso o la ventaja técnica. Evita el exceso de viñetas; prioriza la narrativa técnica.]
---

# 5. Restricciones y estilo
- **Estilo de la explicación (Parte 1):** No seas condescendiente. Asume que sé de lo que hablo. Céntrate en las diferencias sutiles, rendimiento o casos de uso en producción.
- **Estilo de la diapositiva (Parte 2):** Lenguaje académico apropiado para Técnicos Superiores. La diapositiva debe ser capaz de "sostenerse sola" si el alumno la lee después de clase. Formato pensado para pantalla 16:9.
- **Extensión:** La diapositiva debe rondar las 100 palabras para no saturar visualmente, pero explicando bien el concepto.
````










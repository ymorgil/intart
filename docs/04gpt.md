# 🧠 ChatGPT (OpenAI)

> Documento actualizado a **julio de 2026**. OpenAI publica modelos y cambia precios/planes con mucha frecuencia; conviene revisar periódicamente en las webs oficiales para confirmar que los datos siguen vigentes.

## ChatGPT [WEB](https://chatgpt.com/){target="_blank"}

Asistente conversacional de **OpenAI**, uno de los productos de IA generativa más usados del mundo. Permite chatear, generar imágenes, analizar documentos, navegar por internet, escribir y depurar código (a través de Codex) y ejecutar tareas de varios pasos de forma semiautónoma ("modo agente"). Se apoya en la familia de modelos **GPT**.

![ChatGPT](https://commons.wikimedia.org/wiki/Special:FilePath/ChatGPT-Logo.svg)

!!! note "ChatGPT tampoco vive en tu ordenador"

    Igual que Claude o Gemini, el modelo se ejecuta en los servidores de OpenAI. La web, la app de escritorio o la app móvil son solo la puerta de entrada para hablar con esos modelos en la nube.

**FORMATOS**

| Producto | Qué es y para qué sirve |
|---|---|
| **ChatGPT (web/app)** | Asistente de chat general en [chatgpt.com](https://chatgpt.com/){target="_blank"} y en apps de escritorio/móvil. |
| **GPTs personalizados** | Versiones a medida de ChatGPT con instrucciones, conocimiento y herramientas propias (ver sección dedicada más abajo). |
| **GPT Store** | Directorio público donde cualquier usuario puede publicar y descubrir GPTs creados por otros. |
| **Codex** | Agente de programación de OpenAI, integrado en ChatGPT, en la terminal y en editores como VS Code. |
| **API de OpenAI** | Interfaz técnica de pago por token para integrar los modelos GPT en aplicaciones propias. |

![OpenAI](https://commons.wikimedia.org/wiki/Special:FilePath/OpenAI_Logo.svg)

## Modelos

En julio de 2026, OpenAI acaba de completar el despliegue público de su generación **GPT-5.6** (lanzada el 10 de julio de 2026), que convive todavía con la generación anterior **GPT-5.5** en algunos planes.

| Modelo | Categoría | Precio API aprox. (entrada / salida por 1M tokens) | Disponibilidad en ChatGPT | Uso principal |
|---|---|---|---|---|
| **GPT-5.6 Sol** | Razonamiento máximo especializado | 5 $ / 30 $ | Planes Pro y superiores | Afinado específicamente para biología, química y ciberseguridad; máximo rendimiento en modo agente |
| **GPT-5.6 Terra** | Equilibrado | 2,50 $ / 15 $ | Plus, Pro, Business, Enterprise | Mejor relación rendimiento-coste para la mayoría de casos de uso en producción |
| **GPT-5.6 Luna** | Económico | 1 $ / 6 $ | Todos los planes, incluido el gratuito | Clasificación, enrutamiento y generación estándar de alto volumen |
| **GPT-5.5 Instant** | Modelo por defecto (generación anterior) | 5 $ / 30 $ | Todos los planes | Uso cotidiano: rapidez y comprensión de intención |
| **GPT-5.4-Codex** | Programación agéntica | Según uso en Codex | Codex / planes de pago | Generación y refactorización de código de forma autónoma |

!!! warning "Modelos retirados"

    Desde el 13 de febrero de 2026, OpenAI retiró de ChatGPT los modelos GPT-4o, GPT-4.1, GPT-4.1 mini, o4-mini y GPT-5 (Instant y Thinking): si tienes automatizaciones o documentación antigua que los mencione, revísalas porque ya no están disponibles en la interfaz de chat (el acceso por API no se ha visto afectado).

### ¿Cómo se usa y cómo se paga?

- **Planes de ChatGPT:** **Free** (gratis, con límites estrictos), **Go** (~8 $/mes, más mensajes), **Plus** (~20 $/mes: modelos avanzados, Deep Research limitado, generación de imágenes y Sora), **Pro** (~200 $/mes: acceso ilimitado a los modelos de razonamiento Pro), **Business** (25 $/usuario/mes) y **Enterprise** (precio a medida).
- **API de OpenAI:** facturación por token (entrada y salida por separado), igual que en Anthropic o Google.
- **Codex:** consume el mismo sistema de tokens/planes que ChatGPT, con cuotas específicas según el plan.

---

## GPTs personalizados (Custom GPTs)

![Crear GPT](https://commons.wikimedia.org/wiki/Special:FilePath/ChatGPT-Logo.svg)

Un **GPT** es una versión personalizada de ChatGPT que combina **instrucciones, conocimiento adicional y cualquier combinación de habilidades** (búsqueda web, generación de imágenes, código, conexión a apps externas). Es el equivalente directo de los **Gems** de Gemini o los **Proyectos/Skills** de Claude.

!!! example "Definición corta"

    Un GPT es "una instancia configurada de ChatGPT": mismo modelo, pero con un rol, un tono y unas herramientas fijadas de antemano, para no tener que repetir el contexto cada vez que lo usas.

!!! warning "Requiere un plan de pago"

    Crear y compartir GPTs propios requiere **ChatGPT Plus o superior**. Con la cuenta gratuita, al pulsar "Crear" en la sección GPTs aparece un aviso para mejorar el plan — solo se puede **usar** GPTs ya publicados por otros (por ejemplo, desde el GPT Store), no crear ni compartir los propios.

### Cómo crear un GPT paso a paso

1. Abre **Explorar GPTs** en la barra lateral de ChatGPT o entra directamente en [chatgpt.com/gpts](https://chatgpt.com/gpts){target="_blank"}.
2. Pulsa **`+ Crear`**, arriba a la derecha.
3. Elige cómo quieres construirlo:
      - **Creación conversacional:** describes lo que quieres y ChatGPT redacta el GPT por ti, haciéndote preguntas.
      - **Vista de configuración:** rellenas directamente los campos (nombre, instrucciones, conocimiento...).
4. Prueba el GPT en el panel de **Vista previa**, a la derecha, antes de darlo por terminado.
5. Pulsa **Crear** (o **Actualizar**, si ya existe) para guardar los cambios.

!!! example "Lo que vimos en la propia cuenta al entrar en /gpts"

    La sección "Explorar GPT" muestra primero destacados de la semana y "Tendencias" (los GPTs más usados de la comunidad, como *Scholar GPT* o *Consensus*), organizados por pestañas: La mejor selección, Educación, Productividad, Investigación y análisis, Escritura, DALL·E... El botón **`+ Crear`** aparece siempre arriba a la derecha.

### Estructura de un GPT

| Campo/sección | Obligatorio | Qué contiene |
|---|---|---|
| **Nombre** | Sí | Título que ven los usuarios en resultados de búsqueda, en el GPT Store, en enlaces compartidos y en la parte superior del chat. |
| **Descripción** | Sí | Resumen corto del propósito del GPT, para quién es y qué tipo de tareas resuelve; aparece en las vistas previas y en el GPT Store. |
| **Conversation starters (mensajes de ejemplo)** | No | Prompts de ejemplo que se muestran al abrir el GPT, para orientar al usuario sobre cómo interactuar con él. |
| **Instrucciones** | Sí | Define cómo debe comportarse: qué debe hacer, cómo responder y qué evitar. Se aplican en cada conversación. |
| **Conocimiento** | No | Archivos que el GPT usa como material de referencia (hasta 20 archivos, 512 MB cada uno). No sustituye a las instrucciones: el conocimiento es la fuente, las instrucciones son las reglas de comportamiento. |
| **Modelo recomendado** | No | El modelo que se sugiere por defecto al usuario al iniciar conversación con el GPT. |
| **Capacidades** | No | Activa funciones integradas: búsqueda web, generación de imágenes, Canvas, Code Interpreter y análisis de datos, o Apps (herramientas externas conectadas). |
| **Acciones** | No | Conexión a APIs externas definidas por ti, para que el GPT pueda consultar o modificar datos en sistemas externos (excluyente con "Apps"). |

!!! tip "Buenas prácticas al redactar instrucciones (recomendación oficial de OpenAI)"

    - En flujos de varios pasos, usa una estructura explícita: "Cuando ocurra X → haz Y", separando bien las secciones.
    - Prefiere instrucciones en positivo ("Haz X") frente a listas largas de prohibiciones ("No hagas Y").
    - Si el GPT debe aplicar definiciones o clasificaciones concretas, incluye ejemplos breves de salidas aceptables e inaceptables.
    - Usa encabezados y listas para que las prioridades y los pasos se distingan visualmente.

### Ejemplo real de instrucciones para un GPT docente

```text
Eres un asistente experto en Sistemas y Aplicaciones Informáticas para un
Ciclo Formativo de Grado Superior de Formación Profesional.

Cuando el profesor te pida generar un cuestionario de evaluación:
1. Pregunta primero el tema, el número de preguntas y el nivel de dificultad
   si no te lo ha indicado.
2. Genera las preguntas en formato GIFT (compatible con Moodle), con cuatro
   opciones por pregunta y solo una correcta.
3. Entrega el resultado en un único bloque de código, listo para copiar y
   pegar en un archivo .txt e importarlo en Moodle.

No inventes datos técnicos incorrectos: si no estás seguro de un detalle
concreto (por ejemplo, un número de puerto o una versión de software),
dilo explícitamente en vez de inventarlo.
```

### Probar el GPT antes de compartirlo

Antes de compartir o publicar en el GPT Store, usa la **Vista previa** integrada para probar prompts reales, revisar el tono y la precisión, y afinar la configuración. Suele ser más eficaz ajustar primero las instrucciones y añadir ejemplos que añadir más herramientas de golpe.

### Cómo compartir un GPT

1. Abre el GPT en el editor (desde "Mis GPTs" → selecciona el GPT → **Editar GPT**).
2. Pulsa **Compartir**.
3. Elige el **nivel de compartición**:
      - **Solo por invitación:** en cuentas personales, solo tú; en workspaces gestionados, también usuarios o grupos concretos.
      - **Cualquiera del workspace con el enlace** / **Tu workspace entero** (solo en cuentas de empresa/educación).
      - **Cualquiera con el enlace:** disponible también en cuentas personales, si la compartición pública está habilitada.
      - **GPT Store:** lo publica de forma pública en el directorio de GPTs.
4. Elige el **nivel de permiso**: *Puede chatear*, *Puede ver la configuración* o *Puede editar* (no todos los niveles de compartición admiten los tres permisos).
5. Pulsa **Guardar** para aplicar los cambios de compartición.
6. Copia el enlace del GPT si quieres enviarlo directamente (menú de tres puntos ••• → "Copiar enlace del GPT").

!!! note "Enlace de ejemplo"

    Un GPT compartido por enlace tiene una forma parecida a `https://chatgpt.com/g/g-<identificador>-<nombre-del-gpt>`. Si compartes el GPT directamente con una persona (en cuentas de empresa/educación), esa persona recibe además una notificación por correo con el enlace.

!!! warning "En cuentas personales, solo dos opciones reales"

    Para una cuenta personal (como la mayoría del profesorado usa fuera de un Workspace de empresa), solo existen dos formas reales de compartir un GPT con otras personas: **"Cualquiera con el enlace"** o publicarlo en el **GPT Store**. La compartición dirigida a usuarios/grupos concretos solo existe dentro de workspaces gestionados (ChatGPT Edu/Enterprise).

### Publicar en el GPT Store

Publicar hace que el GPT sea públicamente localizable dentro de ChatGPT. Al publicar, es posible que se te pida elegir una categoría, revisar cómo aparece tu nombre de creador y confirmar que el GPT cumple las políticas de OpenAI. Un GPT puede no ser apto para publicación pública si usa conexiones de apps no soportadas, si usa acciones sin una URL de política de privacidad válida, o si el workspace tiene la publicación pública desactivada.

## Preguntas frecuentes sobre GPTs

!!! question "¿Puedo editar un GPT después de publicarlo?"

    Sí. Los cambios se guardan primero como borrador; pulsa **Actualizar** para aplicarlos a la versión pública ya compartida.

!!! question "¿Puedo ver versiones anteriores de mi GPT?"

    Sí, desde el menú de tres puntos (•••) del editor puedes acceder al **historial de versiones** y restaurar una anterior si algo salió mal.

!!! question "¿Un GPT puede usar Acciones (APIs externas) y Apps al mismo tiempo?"

    No. Un GPT puede usar **Apps** (herramientas que el usuario ya tiene conectadas) o **Acciones** (APIs que tú defines), pero no ambas combinadas en el mismo GPT.

!!! question "¿Necesito verificar mi perfil de creador para publicar en el GPT Store?"

    Para publicar de forma totalmente pública, sí: OpenAI puede pedir verificar tu nombre, un enlace de sitio web de un dominio verificado o perfiles sociales confirmados.

### Explorar GPTs de otros usuarios (GPT Store)

Aunque tengas cuenta gratuita y no puedas crear GPTs propios, sí puedes **usar** cualquier GPT ya publicado por otros. La sección "Explorar GPT" organiza los GPTs por pestañas (La mejor selección, Educación, Productividad, Investigación y análisis, Escritura, DALL·E...) y muestra rankings de "Tendencias" con los más usados por la comunidad.

![GPT Store](https://commons.wikimedia.org/wiki/Special:FilePath/ChatGPT-Logo.svg)

!!! example "GPTs educativos habituales en el Store"

    Buscando por la categoría "Educación" suelen aparecer GPTs orientados a resumir papers académicos, generar rúbricas de evaluación, practicar idiomas con corrección de errores, o resolver dudas de una asignatura concreta citando fuentes. Antes de usar uno con datos de alumnos, revisa su descripción y quién lo ha publicado — al ser contenido de terceros, OpenAI no garantiza la exactitud de sus instrucciones internas.

## Deep Research y Sora

**Deep Research** es el modo de investigación autónoma de ChatGPT (disponible en Plus y superiores, con cuota limitada en Free): el modelo navega por internet de forma autónoma, contrasta varias fuentes y entrega un informe extenso con referencias, de forma similar a Deep Research en Gemini.

**Sora** es el modelo de generación de vídeo de OpenAI, integrado en los planes Plus y superiores: permite generar clips cortos a partir de una descripción en texto, y también remezclar o extender vídeos ya generados.

![Sora / generación de vídeo](https://commons.wikimedia.org/wiki/Special:FilePath/OpenAI_Logo.svg)

## Codex (programación agéntica)

**Codex** es el agente de programación de OpenAI: entiende una base de código, ejecuta pruebas, corrige errores y puede trabajar de forma semiautónoma sobre tareas de varios pasos, de forma parecida a Claude Code. Está disponible dentro de ChatGPT (pestaña Codex), como extensión en editores como VS Code, y en la terminal.

!!! example "Ejemplo de instrucción para Codex"

    ```text
    Revisa el script scripts/generate_pptx.py de este repositorio. Quiero que
    añadas un parámetro --dry-run que muestre por consola cuántas diapositivas
    se generarían, sin escribir el archivo .pptx final. No cambies el
    comportamiento por defecto cuando no se pase ese parámetro.
    ```

!!! example "Prompt para preguntarle a ChatGPT cómo compartir tu propio GPT"

    ```text
    Actúa como experto en la plataforma de GPTs de OpenAI. Tengo un GPT ya creado
    para [tarea concreta, ej. "generar cuestionarios GIFT para Moodle"]. Explícame
    paso a paso cómo compartirlo solo con el equipo docente de mi ciclo (sin
    publicarlo en el GPT Store), qué opción de "nivel de compartición" debo
    elegir en mi caso al tener una cuenta personal, y qué diferencia práctica hay
    entre los permisos "Puede chatear" y "Puede ver la configuración".
    ```

### Otro ejemplo de instrucciones: GPT de soporte de redes y sistemas

```text
Eres un técnico senior de sistemas y redes para un ciclo de Formación
Profesional (Administración de Sistemas Informáticos en Red).

Cuando un alumno te describa una avería o un comportamiento anómalo:
1. Pide los datos mínimos si faltan: sistema operativo, versión, y el mensaje
   de error exacto (cópialo tal cual, no lo resumas).
2. Propón un diagnóstico por descarte, de la causa más probable a la menos
   probable, explicando brevemente por qué.
3. Da los comandos exactos a ejecutar para comprobar cada hipótesis, con el
   resultado esperado si todo va bien.
4. Si el problema implica borrar datos o reiniciar un servicio en producción,
   avisa explícitamente antes de dar ese paso.

Responde siempre en español, con bloques de código separados por cada
comando, y nunca inventes un comando que no existe en el sistema indicado.
```

### Diferencia entre Acciones y Apps en un GPT

Es fácil confundir estas dos formas de ampliar un GPT:

- **Apps** — el GPT usa herramientas que el propio usuario final ya tiene conectadas (por ejemplo, su cuenta de Google Drive o Gmail). El control de permisos recae en el usuario que chatea con el GPT.
- **Acciones** — tú, como creador del GPT, defines una conexión a una API externa concreta (por ejemplo, consultar el estado de un servidor o crear una incidencia en un sistema de tickets). El control de qué API se llama y cómo lo defines tú, no el usuario final.

Un GPT puede usar una de las dos, nunca ambas combinadas en la misma configuración.

## Preguntas frecuentes adicionales

!!! question "¿Puedo duplicar un GPT de otro usuario para adaptarlo?"

    Solo si el creador ha dado el permiso "Puede ver la configuración" o "Puede editar" al compartirlo. Con el permiso básico "Puede chatear", solo puedes conversar con él, no ver ni copiar sus instrucciones.

!!! question "¿Qué pasa si el GPT usa datos de mi organización (ChatGPT Edu/Enterprise)?"

    Los administradores del workspace pueden restringir qué opciones de compartición están disponibles (por ejemplo, bloquear "Cualquiera con el enlace" para forzar que todo quede dentro del dominio educativo).

!!! question "¿El GPT Store es gratuito para publicar?"

    Sí, publicar en el GPT Store no tiene coste adicional más allá de tu suscripción Plus/Pro/Business, pero debes completar tu perfil de creador y cumplir las políticas de contenido de OpenAI.

## Comparativa rápida con Claude y Gemini

| | ChatGPT | Claude | Gemini |
|---|---|---|---|
| Personalización persistente | **GPTs** | Proyectos / Skills | Gems |
| Directorio público | **GPT Store** | No (skills se instalan, no se "publican" igual) | No |
| Requiere plan de pago para crear | Sí (Plus o superior) | No (Free ya permite Proyectos) | No (Free ya permite Gems) |
| Agente de programación propio | Codex | Claude Code | — (usa Gemini vía Antigravity/IDE) |
| Punto fuerte | Ecosistema, modo agente, adopción masiva | Razonamiento, seguridad y uso de ordenador | Integración con Google y multimodalidad |

## Recursos

- [Ayuda oficial: crear y editar GPTs](https://help.openai.com/en/articles/8554397-creating-and-editing-gpts){target="_blank"}
- [Ayuda oficial: compartir y publicar GPTs](https://help.openai.com/en/articles/8798878-sharing-and-publishing-gpts){target="_blank"}
- [GPT Store](https://chatgpt.com/gpts){target="_blank"}
- [Precios de la API de OpenAI](https://openai.com/api/pricing/){target="_blank"}

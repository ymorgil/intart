# 💎 Gemini (Google)

> Documento actualizado a **julio de 2026**. Google actualiza modelos, precios y funciones de Gemini con mucha frecuencia (a veces varias veces al trimestre), conviene revisar periódicamente para confirmar que los datos siguen vigentes.

## Gemini [WEB](https://gemini.google.com/){target="_blank"}

Asistente de inteligencia artificial multimodal creado por **Google DeepMind**. A diferencia de otros chatbots que nacieron centrados solo en texto, Gemini se diseñó desde el principio para entender y combinar texto, imagen, audio, vídeo y código en la misma conversación. Está integrado de forma nativa en el buscador de Google, en Android, en Google Workspace (Gmail, Docs, Drive, Sheets) y disponible también como app independiente (web y móvil).

![Gemini](https://registry.npmmirror.com/@lobehub/icons-static-png/latest/files/dark/gemini-color.png)

!!! note "Gemini no es solo un chat"

    Como Claude o ChatGPT, Gemini no "vive" en tu ordenador ni en tu móvil: el modelo se ejecuta en los centros de datos de Google. La app, la web o la integración dentro de Gmail son solo la puerta de entrada para hablar con esos modelos en la nube.

**FORMATOS**

| Producto | Qué es y para qué sirve |
|---|---|
| **Gemini (app/web)** | Asistente de chat general, equivalente a Claude.ai o ChatGPT. Disponible en [gemini.google.com](https://gemini.google.com/){target="_blank"} y en la app móvil de Android/iOS. |
| **Integración en Google Workspace** | Gemini aparece como barra lateral o botón "✨" dentro de Gmail, Docs, Sheets, Slides y Meet, usando el contexto del documento o correo abierto. |
| **Google AI Studio** | Herramienta gratuita para desarrolladores y docentes que permite probar los modelos Gemini, ajustar parámetros (temperatura, instrucciones de sistema) y generar código de integración, sin necesidad de programar una app completa. |
| **API de Gemini (Vertex AI / AI Studio)** | Interfaz técnica de pago por token para integrar los modelos Gemini en aplicaciones propias. |
| **Gemini en Android** | Sustituye al antiguo Asistente de Google en muchos dispositivos; se activa manteniendo pulsado el botón de encendido o diciendo "Hey Google". |

![Google AI Studio](https://wpforms.com/wp-content/uploads/2024/08/google-ai-studio-logo.png)

## Modelos

Google organiza la familia Gemini en función de la relación velocidad/coste/razonamiento. La generación vigente en julio de 2026 es **Gemini 3**, que convive todavía con algunos modelos **2.5** en el plan gratuito.

| Modelo | Categoría | Precio API aprox. (por 1M tokens) | Contexto | Uso principal |
|---|---|---|---|---|
| **Gemini 3 Deep Think** | Razonamiento extendido | Solo incluido en plan **Ultra** | Muy amplio | Investigación científica, demostraciones matemáticas y problemas lógicos de varios pasos donde el modelo "piensa" antes de responder |
| **Gemini 3 Pro** | Razonamiento avanzado | ~2-4 $ | 1.000.000 tokens | Análisis profundo, generación de vídeo (Veo), tareas profesionales complejas |
| **Gemini 3 Flash** | Rápido y agéntico | ~0,50 $ | Amplio | Suele igualar a Pro en muchas tareas ejecutándose unas 3 veces más rápido; ideal para uso diario y flujos agénticos |
| **Gemini 3 Flash-Lite** | Económico | Tarifa reducida | Amplio | Clasificación, resumen y *embeddings* en grandes volúmenes de texto |
| **Gemini 2.5 Flash** | Plan gratuito | — | 32.000 tokens | Versión incluida por defecto en la cuenta gratuita cuando no hay cuota de los modelos 3 disponible |

!!! warning "Los precios cambian por región y por endpoint"

    Desde el 1 de julio de 2026 la tarificación de la familia Gemini 3 varía según el endpoint (global vs. regional) en la API. Antes de presupuestar un proyecto con la API, consulta siempre la [página oficial de precios](https://ai.google.dev/gemini-api/docs/pricing){target="_blank"}.

### Nano Banana (generación de imágenes)

Dentro del ecosistema Gemini, **Nano Banana** (nombre coloquial del modelo de generación y edición de imágenes de Google, actualmente en su versión Pro) permite crear y editar imágenes de forma conversacional: puedes pedir cambios sobre una imagen ya generada ("quita el fondo", "cambia la hora del día") sin tener que reescribir el prompt completo.

### Deep Research

**Deep Research** es el modo de investigación autónoma de Gemini: en lugar de responder directamente, el modelo planifica una serie de búsquedas en internet, navega por decenas de páginas, contrasta fuentes y entrega un informe largo y estructurado con enlaces a las fuentes originales.

!!! example "Cuándo usar Deep Research en clase"

    Es especialmente útil para pedirle al alumnado (o para prepararte tú mismo) un estado del arte sobre un tema técnico amplio, por ejemplo: *"Investiga el estado actual de la virtualización de contenedores frente a máquinas virtuales en entornos de producción, con ejemplos reales de empresas y comparativas de rendimiento de 2025-2026."* El informe final suele tardar varios minutos en generarse porque el modelo está navegando de verdad, no respondiendo de memoria.

Disponible en los planes **Google AI Pro** y **Google AI Ultra**; el plan gratuito tiene un número muy limitado de usos al mes. El plan AI Pro también incluye **NotebookLM Plus** (ver la página [NotebookLM](05notebook.md)), la otra gran herramienta de investigación de Google basada en documentos propios.

![NotebookLM](https://play-lh.googleusercontent.com/qWDLmYCI4Lqzq8J-LhtvWvp1HIPkJb2lqkHjduXM7tnCo7N1tmKxnYdaX7CS2_5pkDuW=w240-h480-rw)

## ¿Cómo se usa y cómo se paga?

- **App Gemini / Google AI:** plan **Free** (usa Gemini 2.5 Flash con contexto limitado), **Google AI Pro** (~20 $/mes: acceso a Gemini 3 Pro, 1M de tokens de contexto, Deep Research, NotebookLM Plus y 2 TB en Google One) y **Google AI Ultra** (dos niveles, aprox. 100 $ y 200 $/mes, que añaden Deep Think y cuotas de uso mucho más altas).
- **API (Vertex AI / Google AI Studio):** pago por token, con tarifas distintas de entrada y salida; si el contexto supera los 200.000 tokens se aplican tarifas de "contexto largo".
- **Integración gratuita y con límites** dentro de productos de Google como Search (resúmenes con IA), Gmail (redacción asistida) o Android.

---

## Gems

![Google Workspace](https://commons.wikimedia.org/wiki/Special:FilePath/Google_Workspace_Logo.svg)

Los **Gems** son la forma que tiene Gemini de crear **versiones personalizadas del asistente**: un mismo modelo (por ejemplo, Gemini 3 Flash) al que le añades instrucciones fijas, un rol concreto y, opcionalmente, documentos de referencia, para que se comporte siempre igual sin tener que repetir el contexto en cada conversación nueva. Es el equivalente directo de los **Proyectos** de Claude o los **GPTs** de ChatGPT.

!!! example "Definición corta"

    Un Gem es "un empleado especializado" dentro de Gemini: en vez de explicarle a un asistente genérico quién eres y qué necesitas cada vez, configuras un Gem una sola vez (por ejemplo, "Corrector de exámenes de FP") y lo reutilizas siempre que haga falta.

### ¿Para qué sirve crear un Gem?

- **Ahorra repetir contexto.** Si siempre le pides lo mismo a Gemini (corregir exámenes con la misma rúbrica, redactar actas de reunión con el mismo formato), un Gem elimina la necesidad de copiar y pegar esas instrucciones en cada chat.
- **Fija un tono y una estructura de respuesta consistentes.** Puedes indicar que la respuesta empiece siempre con un resumen y continúe con una lista, por ejemplo.
- **Da acceso a documentos concretos.** Puedes anexar archivos (apuntes, rúbricas, normativa del centro) para que el Gem los use como base de conocimiento en lugar de depender solo del conocimiento general del modelo.
- **Es privado por defecto.** Un Gem que creas solo lo ves tú, salvo que decidas compartirlo (ver más abajo).

### Cómo crear un Gem paso a paso

1. Entra en [gemini.google.com](https://gemini.google.com/){target="_blank"} con tu cuenta de Google.
2. En la barra lateral izquierda, pulsa **Gems**.
3. Pulsa el botón **`+ Nuevo Gem`**.
4. Rellena los campos del formulario de creación (ver estructura detallada abajo).
5. Pulsa **Guardar**. El Gem aparece automáticamente en tu lista de "Mis Gems".

!!! example "Captura real del formulario de creación (gestor de Gems del usuario)"

    El "Gestor de Gems" muestra primero los Gems prediseñados por Google (Storybook, Exploración de ideas, Orientación profesional, Asistente de programación) y, debajo, la sección **Mis Gems** con los que ha creado el propio usuario, cada uno con sus iconos de compartir, editar y más opciones.

### Estructura de un Gem

El formulario de creación de un Gem ("Nuevo Gem") tiene siempre los mismos campos, con una vista previa en directo a la derecha:

| Campo | Obligatorio | Qué contiene |
|---|---|---|
| **Nombre** | Sí | El título corto que identifica al Gem en tu lista y en la vista previa (ej. "Corrector de prácticas SAI"). |
| **Descripción** | No | Un resumen de una frase de qué hace el Gem; ayuda a recordar para qué lo creaste cuando tengas varios. |
| **Instrucciones** | Sí | El equivalente al *system prompt*: aquí defines el rol, el tono, el formato de salida y las reglas que debe seguir siempre. Es el campo más importante — cuanto más concreto, más consistente será el comportamiento. |
| **Herramienta predeterminada** | No | Permite fijar de antemano una herramienta para que el Gem la use por defecto sin que tengas que activarla cada vez. |
| **Conocimientos** | No | Aquí adjuntas archivos (PDF, Docs, hojas de cálculo) para que el Gem los use como fuente de referencia en lugar de fiarse solo de su conocimiento general. |

!!! tip "Buena práctica al redactar las instrucciones"

    Sigue la misma estructura que un buen prompt (ver la página [Prompts](01prompts.md)): rol + contexto + tarea + formato + restricciones. Por ejemplo: *"Eres un profesor experto en Sistemas y Aplicaciones Informáticas de un ciclo de FP. Cuando te pase un enunciado de examen, corrígelo siguiendo esta rúbrica: [pega la rúbrica]. Responde siempre con una tabla: pregunta, nota, comentario."*

### Ejemplo real de instrucciones para un Gem docente

```text
Eres un asistente experto en Sistemas y Aplicaciones Informáticas dentro de un
Ciclo Formativo de Grado Superior. Actúas como corrector de prácticas técnicas
(Linux, redes, virtualización, contenedores).

Cuando te pegue el enunciado de una práctica y la solución de un alumno:
1. Compara paso a paso la solución con el enunciado.
2. Señala qué apartados están correctos, incompletos o mal resueltos.
3. Puntúa sobre 10, mostrando el desglose por apartado.
4. Redacta un comentario breve y constructivo para el alumno, en español,
   sin tecnicismos innecesarios.

Formato de salida: tabla con columnas Apartado | Estado | Nota | Comentario,
y al final la nota total en negrita.
```

### Cómo compartir un Gem

Un Gem se puede compartir igual que un documento de Google Drive: por enlace, con niveles de acceso configurables.

**Pasos para compartir (ordenador):**

1. Ve a [gemini.google.com](https://gemini.google.com/){target="_blank"} y abre la barra lateral.
2. Pulsa **Gems** para ver "Mis Gems".
3. Junto al Gem que quieras compartir, pulsa el icono de **Compartir** (🔗).
4. En el cuadro **"Compartir «Nombre del Gem»"** elige el nivel de **acceso general**:
      - **Restringido** — solo las personas con acceso explícito pueden abrirlo con el enlace.
      - **Cualquiera con el enlace** — cualquier persona que reciba el enlace puede usar el Gem (sin poder verlo en buscadores).
      - **Público** — cualquiera puede encontrar el Gem buscándolo en Google.
5. Pulsa **Copiar enlace** y pega ese enlace donde quieras compartirlo (correo, Classroom, Moodle, chat del equipo docente...). Pulsa **Hecho** para cerrar el cuadro de diálogo.

!!! example "Cuadro de diálogo real de compartición"

    El diálogo se titula **"Compartir «Nombre del Gem»"** y tiene tres partes: un buscador para "Añadir personas, grupos y eventos de calendario", la lista de "Personas con acceso" (tú apareces siempre como Propietario) y, debajo, el desplegable de "Acceso general" con el candado 🔒 y el botón **Copiar enlace**.

!!! note "Enlace de ejemplo"

    Un enlace de Gem compartido tiene una forma parecida a `https://gemini.google.com/gem/<identificador-unico>`. El identificador es único por Gem y no se puede elegir manualmente: lo genera Google al compartirlo.

!!! warning "Antes de compartir un Gem públicamente"

    Si el Gem tiene archivos de "Conocimientos" adjuntos (por ejemplo, un examen con soluciones, datos de alumnos), revisa qué nivel de acceso eliges: "Público" permite que cualquiera lo encuentre buscando en Google, no solo que lo use quien tenga el enlace.

### Diferencia entre un Gem y una conversación con archivos adjuntos

Es fácil confundir "subir un archivo a un chat normal" con "crear un Gem". La diferencia clave es la **persistencia**: un archivo subido a un chat suelto de Gemini solo vale para esa conversación; un Gem con "Conocimientos" adjuntos mantiene ese contexto disponible en **todas** las conversaciones nuevas que abras con él, sin tener que volver a subir nada.

### Gems prediseñados por Google

Antes de crear uno propio desde cero, merece la pena revisar los Gems que Google ya ofrece prediseñados en el "Gestor de Gems", porque cubren necesidades habituales y sirven de inspiración de estructura:

| Gem prediseñado | Para qué sirve |
|---|---|
| **Storybook** | Crea un libro ilustrado personalizado para niños o adultos a partir de un tema. |
| **Exploración de ideas** | Encuentra inspiración fácilmente: ideas para fiestas, regalos, proyectos. |
| **Orientación profesional** | Ayuda a desarrollar tu potencial en la carrera, con un plan detallado de mejora. |
| **Asistente de programación** | Mejora tus habilidades de programación con ayuda contextual paso a paso. |

!!! tip "Duplícalos como punto de partida"

    Si un Gem prediseñado se parece a lo que necesitas, es más rápido abrirlo, revisar sus instrucciones (icono de editar ✏️) y adaptarlas a tu caso, que empezar un Gem nuevo en blanco.

### Buenas prácticas de privacidad para Gems en un centro educativo

!!! warning "Datos de alumnado"

    Si vas a adjuntar archivos de "Conocimientos" que contengan datos personales de alumnos (notas, nombres, DNI, informes), mantén el Gem en modo **Restringido** o, como mucho, **Cualquiera con el enlace** dentro de un grupo cerrado (por ejemplo, solo el equipo docente del ciclo). Nunca lo publiques como **Público**, porque eso lo hace indexable y buscable por cualquiera.

- Revisa periódicamente la lista de "Personas con acceso" de tus Gems compartidos: quitar el acceso a quien ya no lo necesite es tan sencillo como añadirlo.
- Si el Gem se comparte con todo un departamento, documenta en la propia descripción del Gem quién es el responsable de mantenerlo actualizado.
- Antes de compartir un Gem con contenido de examen, comprueba que las "Instrucciones" no revelan sin querer las respuestas correctas si un alumno intenta hacerse pasar por profesor.

## Integración con Google Workspace

Gemini aparece de forma nativa (botón "✨" o barra lateral) dentro de:

- **Gmail:** redactar, resumir hilos largos y sugerir respuestas.
- **Docs:** generar borradores, resumir o reescribir secciones seleccionadas.
- **Sheets:** generar fórmulas a partir de una descripción en lenguaje natural y crear tablas o gráficos.
- **Meet:** transcripción y resumen automático de reuniones ("Take notes for me").
- **Slides:** generación de imágenes o borradores de presentación a partir de un guion.

Esta integración usa la misma cuenta y el mismo plan (Free/AI Pro/AI Ultra) que la app de Gemini.

## Extensiones (Apps conectadas)

Además de Workspace, Gemini puede conectarse a otras **apps de Google y de terceros** para completar tareas reales en vez de solo dar información: Maps (rutas y recomendaciones de sitios), YouTube (buscar y resumir vídeos), Calendar (consultar y crear eventos), Google Home (controlar dispositivos domésticos) y servicios de terceros como Spotify o determinadas agencias de viaje.

!!! example "Cómo activarlas"

    Se activan desde el icono de ajustes ⚙️ → "Apps" dentro de la propia conversación de Gemini. Una vez activadas, basta con pedirle algo como *"resérvame ruta en coche hasta el centro para mañana a las 8:00 y añádelo a mi calendario"* para que Gemini combine varias apps en una sola respuesta.

Gemini en Android sustituye al Asistente de Google clásico en muchos dispositivos y comparte cuota con la app/web:

![Gemini en Android](https://registry.npmmirror.com/@lobehub/icons-static-png/latest/files/dark/gemini-color.png)

## Google AI Studio (para desarrollo y pruebas)

[Google AI Studio](https://aistudio.google.com/){target="_blank"} es la puerta de entrada gratuita para probar los modelos Gemini sin límites tan estrictos como en la app de consumo, pensada para desarrolladores, pero también muy útil para un docente que quiera:

- Probar cómo responde un modelo concreto (Pro, Flash, Deep Think) antes de decidir cuál usar en un Gem.
- Ajustar la "instrucción de sistema" y ver el resultado en tiempo real.
- Generar el código (Python, JavaScript) necesario para integrar ese comportamiento en una aplicación propia, por ejemplo un chatbot para la web del centro.

!!! example "Prompt para pedirle ayuda a Gemini sobre sus propios Gems"

    ```text
    Actúa como experto en Google Gemini. Explícame paso a paso cómo crear un Gem
    para [tarea concreta, ej. "generar rúbricas de evaluación de prácticas de
    Linux"], qué debería escribir en el campo de instrucciones y qué archivos de
    "Conocimientos" me conviene adjuntar. Después, dime cómo compartir ese Gem
    con el resto del equipo docente del ciclo con acceso restringido solo a
    quienes tengan el enlace.
    ```

### Otro ejemplo de instrucciones: Gem de automatización de redes

```text
Eres un técnico senior en redes y sistemas, especializado en entornos de
Formación Profesional con equipos Cisco, MikroTik y servidores Linux/Windows
Server.

Cuando te pida ayuda con un guion de automatización (Bash, PowerShell o
Ansible):
1. Pregunta primero el sistema operativo/objetivo si no está claro.
2. Entrega el script comentado línea a línea en español.
3. Añade al final una sección "Cómo probarlo" con los pasos para validarlo
   en un entorno de laboratorio antes de tocar producción.
4. Si detectas un riesgo (borrado de datos, cambios de red en caliente),
   avisa explícitamente antes del bloque de código.

No uses anglicismos innecesarios y explica cualquier comando poco habitual
con un comentario breve.
```

## Preguntas frecuentes sobre Gems

!!! question "¿Un Gem consume más cuota que un chat normal?"

    No. Un Gem usa el mismo modelo y la misma cuota que una conversación normal; lo único que cambia es que las instrucciones y los archivos de "Conocimientos" se envían automáticamente al principio de cada conversación nueva.

!!! question "¿Puedo editar un Gem después de compartirlo?"

    Sí. Los cambios que hagas en las instrucciones o en los archivos adjuntos se aplican automáticamente a todas las personas que ya tengan el enlace, sin necesidad de volver a compartirlo.

!!! question "¿Puedo borrar un Gem que ya compartí?"

    Sí, desde el menú de tres puntos (⋮) junto al Gem, en "Mis Gems". Al borrarlo, el enlace deja de funcionar para todas las personas con las que lo compartiste.

!!! question "¿Los Gems de Workspace para centros educativos son distintos?"

    Si tu centro usa Google Workspace for Education, un administrador puede activar o desactivar la posibilidad de compartir Gems fuera de la organización desde la consola de administración, igual que ocurre con los documentos de Drive.

## Comparativa rápida con Claude y ChatGPT

| | Gemini | Claude | ChatGPT |
|---|---|---|---|
| Personalización persistente | **Gems** | Proyectos / Skills | GPTs |
| Integración nativa en ofimática | Google Workspace | — (vía conectores) | Microsoft 365 (a través de Copilot) |
| Generación de vídeo integrada | Sí (Veo) | No | Sí (Sora, planes de pago) |
| Contexto máximo (plan Pro) | 1.000.000 tokens | 1.000.000 tokens | Variable según modelo |
| Punto fuerte | Multimodalidad e integración con el ecosistema Google | Razonamiento, seguridad y uso de ordenador | Ecosistema y adopción masiva |

## Recursos

- [Ayuda oficial: crear Gems personalizados](https://support.google.com/gemini/answer/16504957){target="_blank"}
- [Blog de Google: compartir Gems](https://blog.google/products-and-platforms/products/gemini/sharing-gems/){target="_blank"}
- [Precios de la API de Gemini](https://ai.google.dev/gemini-api/docs/pricing){target="_blank"}
- [Google AI Studio](https://aistudio.google.com/){target="_blank"}

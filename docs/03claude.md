# 📘 Claude (Anthropic)

**Claude** es un asistente de inteligencia artificial creado por la empresa **Anthropic**. Funciona de forma parecida a un chat: tú escribes una pregunta o una tarea (un "prompt") y Claude te responde con texto, código, documentos, imágenes esquemáticas o incluso acciones automatizadas, según lo que le pidas.

> 💡 **Importante** Claude **no es un programa que "vive" dentro de tu ordenador**. El modelo de inteligencia artificial se ejecuta en los servidores (la nube) de Anthropic. Lo que instalamos en nuestro equipo —ya sea el navegador, la app de escritorio o una herramienta como Claude Code— es solo una **puerta de entrada** para comunicarnos con esos servidores.

**FORMATOS**

| Producto | Qué es y para qué sirve |
|---|---|
| **Claude.ai** [web](https://claude.ai/new){target="_blank"} | Un asistente de chat general basado en conversación. Ideal para redactar textos, analizar archivos adjuntos, generar gráficos y responder consultas en tiempo real. |
| **App de escritorio** | La versión instalada en Windows/Mac que ofrece las mismas funciones del chat web, pero integrada en el sistema operativo del computador para un acceso más cómodo. |
| **App móvil** | La versión adaptada para teléfonos celulares que permite usar las funciones del chat a través de texto o mediante dictado por voz estés donde estés. |
| **Claude Cowork** | Un agente autónomo integrado en la app de escritorio diseñado para trabajadores no técnicos. Se conecta a tus carpetas locales para realizar tareas complejas de múltiples pasos por ti, como organizar archivos masivos, procesar datos (OCR) y automatizar flujos de trabajo en bucle. |
| **Claude Code** | Un agente enfocado en desarrolladores que se ejecuta desde la terminal. Está especializado en programar de forma autónoma, buscar y corregir errores, y gestionar proyectos de código complejos. |
| **API de Claude** | Una interfaz técnica diseñada para programadores que permite conectar los modelos de inteligencia artificial de Claude directamente dentro de aplicaciones y sistemas propios. |

## SKILLS

## AGENTES


##
##

Claude se puede usar en varios "formatos" o productos:



En este manual nos centraremos sobre todo en **Claude.ai (web) y en la app de escritorio**, ya que es el punto de entrada recomendado para quien empieza, y tocaremos de forma sencilla Claude Code como introducción al mundo de los agentes.

---

## 2. La interfaz de Claude: web y app

Para empezar, accede a **[claude.ai](https://claude.ai)** desde tu navegador y crea una cuenta (con correo electrónico o con tu cuenta de Google). Una vez dentro, verás una interfaz dividida en estas zonas principales:

```
┌─────────────────────────────────────────────────────────────┐
│  [Logo Claude]                                  [Tu perfil]  │
├───────────────┬───────────────────────────────────────────────┤
│               │                                               │
│  BARRA        │              ZONA DE CONVERSACIÓN             │
│  LATERAL      │                                               │
│               │   - Aquí aparecen tus mensajes y las           │
│  + Nuevo chat │     respuestas de Claude                       │
│  Chats        │                                               │
│  recientes    │                                               │
│  Proyectos    │                                               │
│  Artefactos   │                                               │
│               ├───────────────────────────────────────────────┤
│               │  [Caja de texto para escribir tu mensaje] [➤] │
└───────────────┴───────────────────────────────────────────────┘
```

### 2.1 Barra lateral (izquierda)

- **➕ Nuevo chat:** abre una conversación en blanco. Cada chat es independiente: Claude no recuerda lo que hablasteis en otro chat (salvo que actives la memoria, ver más abajo).
- **Chats recientes:** historial de todas tus conversaciones anteriores, para poder volver a ellas.
- **Proyectos:** carpetas temáticas donde puedes agrupar chats, subir documentos de referencia y dar instrucciones fijas (lo veremos en el apartado 4).
- **Artefactos:** documentos, páginas web, gráficos o programas que Claude haya generado y que se muestran en una ventana aparte, para poder editarlos o descargarlos sin que ocupen toda la conversación.

### 2.2 Zona de conversación (centro)

Es el área principal donde escribes tus mensajes y lees las respuestas. Algunos detalles útiles:

- Puedes **adjuntar archivos** (PDF, Word, Excel, imágenes, código) haciendo clic en el icono del clip 📎 junto a la caja de texto.
- Puedes **regenerar una respuesta** si no te convence, pulsando el icono de "reintentar".
- Puedes **editar tu propio mensaje** y Claude generará una respuesta nueva a partir de ahí, sin perder el resto de la conversación.

### 2.3 El icono de herramientas (debajo de la caja de texto)

Junto a la caja de texto suele haber un pequeño menú (a veces un icono de "+" o de control deslizante) donde puedes **activar o desactivar funciones** para esa conversación:

- 🔎 **Búsqueda web:** permite que Claude busque información actual en internet antes de responder.
- 📊 **Ejecutar código / crear archivos:** permite que Claude escriba y ejecute código, o genere archivos descargables (Word, Excel, PowerPoint, PDF...).
- 🧩 **Skills:** activa habilidades guardadas (apartado 5).
- 🧠 **Pensamiento extendido:** en algunos modelos, hace que Claude "piense" más despacio y a fondo antes de responder, útil para problemas complejos.

### 2.4 Configuración (⚙️ Settings)

Haciendo clic en tu **foto de perfil** (arriba a la derecha) accederás al menú de configuración, donde encontrarás, entre otras, estas opciones:

| Opción | Qué controla |
|---|---|
| **Modelo (Model)** | Qué versión de Claude usar por defecto (apartado 3) |
| **Estilo de escritura (Styles)** | El tono de las respuestas: formal, conciso, creativo... |
| **Preferencias del usuario** | Notas permanentes sobre ti que Claude tendrá en cuenta siempre (p. ej. "soy estudiante de FP de Sistemas, explica con ejemplos prácticos") |
| **Memoria / Historial de chats** | Activar que Claude recuerde información relevante entre conversaciones distintas |
| **Conectores / Integraciones** | Conectar Claude con otras herramientas (Google Drive, calendario, etc.) |
| **Privacidad y datos** | Controlar si tus conversaciones se pueden usar para mejorar el modelo |

> 🎓 **Consejo para clase:** configura tus **preferencias de usuario** indicando tu nivel de conocimientos (por ejemplo, "estoy en 2º de FP de Administración de Sistemas, no programo casi nada, explícame los conceptos técnicos con analogías sencillas"). Así todas tus conversaciones futuras se adaptarán automáticamente a tu nivel.

---

## 3. Los modelos de Claude: Haiku, Sonnet y Opus

Anthropic no ofrece "una sola IA", sino **varias versiones del modelo**, pensadas para necesidades distintas. En el menú de configuración o justo encima de la caja de texto puedes elegir cuál usar. Actualmente, las tres familias principales son:

| Modelo | Velocidad | Capacidad de razonamiento | Coste de uso | Para qué lo usarías |
|---|---|---|---|---|
| **Claude Haiku** | ⚡⚡⚡ Muy rápido | ⭐ Básica-media | 💰 Bajo | Tareas sencillas y repetitivas: resumir un texto corto, clasificar correos, responder dudas rápidas |
| **Claude Sonnet** | ⚡⚡ Rápido | ⭐⭐ Alta | 💰💰 Medio | Uso diario general: redactar informes, programar, analizar documentos, la mayoría de tareas de clase |
| **Claude Opus** | ⚡ Más lento | ⭐⭐⭐ Máxima | 💰💰💰 Alto | Problemas complejos: análisis profundos, razonamiento en varios pasos, tareas críticas |

### 3.1 ¿Cómo elegir el modelo adecuado?

Piensa en ello como elegir herramienta para un trabajo de taller:

- **Haiku** es como un **destornillador eléctrico**: rapidísimo para tareas pequeñas y repetidas.
- **Sonnet** es como una **caja de herramientas completa de uso diario**: sirve para casi todo y es el equilibrio entre velocidad y calidad. Es el modelo recomendado por defecto para la mayoría del alumnado.
- **Opus** es como **llamar a un especialista**: tarda más y "cuesta más", pero para un problema realmente difícil (un proyecto final, depurar un fallo complejo de red, un análisis extenso) merece la pena.

> ⚠️ Los nombres y números de versión cambian con el tiempo (por ejemplo, pasamos de la versión 4.5 a la 4.6, y así sucesivamente), porque Anthropic actualiza sus modelos varias veces al año. La lógica de "Haiku - Sonnet - Opus" como velocidad/calidad creciente se mantiene siempre, aunque el número concreto de versión no es lo importante para el uso diario.

### 3.2 Planes de suscripción (resumen)

El modelo que puedes usar también depende del **plan** que tengas contratado:

| Plan | Pensado para | Qué incluye (resumen) |
|---|---|---|
| **Free** | Probar la herramienta | Acceso limitado, modelo principal con límites de uso bajos |
| **Pro** | Uso individual habitual (recomendado para estudiantes) | Más uso, acceso a modelos más potentes, Proyectos ilimitados |
| **Max** | Uso intensivo diario | Mucho más volumen de uso que Pro |
| **Team / Enterprise** | Empresas y organizaciones | Gestión centralizada, varios usuarios, seguridad avanzada |

> 📌 Los precios y límites concretos cambian con frecuencia. Antes de elegir un plan, consulta siempre la página oficial **claude.com/pricing** para ver las condiciones actualizadas.

---

## 4. Creación de agentes y asistentes en Claude

Cuando hablamos de **"agentes"** en el mundo de la IA, nos referimos a un asistente que no solo responde preguntas, sino que puede **seguir instrucciones fijas, usar herramientas y completar tareas de varios pasos por sí mismo**. En Claude existen dos formas de crear esto, una sencilla (sin programar) y otra más avanzada (orientada a programación). Vamos a ver ambas.

### 4.1 Sin programar: los Proyectos de Claude.ai

Un **Proyecto** es la forma más sencilla de crear tu propio "asistente personalizado" dentro de Claude.ai, sin escribir ni una línea de código.

**Pasos para crear un Proyecto:**

1. En la barra lateral, pulsa **Proyectos → Crear proyecto**.
2. Dale un nombre claro, por ejemplo: *"Ayudante de Redes y Sistemas"*.
3. En el apartado de **instrucciones personalizadas**, escribe el "rol" que quieres que tenga Claude dentro de ese proyecto. Por ejemplo:

   > *"Actúa como profesor de apoyo en Administración de Sistemas Informáticos en Red. Cuando te pregunte sobre configuración de servidores, redes o sistemas operativos, responde siempre con pasos numerados, comandos exactos y explicando qué hace cada uno."*

4. Sube **documentos de referencia** a la sección de archivos del proyecto: apuntes de clase, manuales del módulo, plantillas de prácticas... Claude los tendrá en cuenta en todas las conversaciones de ese proyecto.
5. A partir de ahí, cada chat que abras **dentro de ese Proyecto** ya "sabe" cómo comportarse, sin que tengas que repetir las instrucciones cada vez.

**¿En qué se diferencia esto de un chat normal?** En un chat normal, cada conversación nueva empieza "desde cero": Claude no recuerda instrucciones de chats anteriores (salvo la memoria general). Un Proyecto soluciona esto creando un contexto persistente y reutilizable, como si fuera tu propio asistente especializado.

### 4.2 Para ir más allá: agentes de programación con Claude Code

**Claude Code** es una herramienta de Anthropic pensada para tareas de programación. Se ejecuta desde un **terminal** (la línea de comandos que seguro ya conoces de tus prácticas de sistemas) o desde extensiones para editores como VS Code.

A diferencia del chat normal, Claude Code puede actuar como un **agente autónomo**: no solo te dice qué código escribir, sino que puede:

- Leer y modificar archivos de un proyecto completo.
- Ejecutar comandos en la terminal.
- Crear y probar pequeños programas o scripts de automatización.
- Encadenar varios pasos (planificar → escribir → probar → corregir) sin que tengas que intervenir en cada uno.

**¿Por qué lo incluimos en un manual para gente que "no programa"?** Porque en un ciclo de Sistemas es muy probable que en algún momento tengáis que tocar pequeños scripts (instalación automática, configuración de red, copias de seguridad). Claude Code permite describir en lenguaje normal lo que quieres conseguir ("haz un script que comprima esta carpeta cada noche y la guarde con la fecha") y el propio agente genera, prueba y ajusta el resultado. No hace falta saber programar de antemano para empezar a experimentar, aunque sí ayuda entender comandos básicos de terminal.

> 🔑 **Idea clave para recordar:** un *Proyecto* en Claude.ai es un "agente" en el sentido de **asistente con contexto e instrucciones fijas**; *Claude Code* es un "agente" en el sentido de **sistema que ejecuta tareas técnicas de varios pasos de forma autónoma**. Ambos parten de la misma base (el modelo de Claude), pero están pensados para necesidades distintas.

---

## 5. Las Skills (habilidades): qué son y cómo se usan

Las **Skills** (en español, "habilidades") son una de las funciones más potentes y menos conocidas de Claude. Son la solución al problema de tener que repetir siempre las mismas instrucciones detalladas en cada conversación nueva.

### 5.1 ¿Qué es exactamente una Skill?

Una Skill es, básicamente, un **paquete de instrucciones reutilizable** (normalmente un archivo de texto llamado `SKILL.md`, que puede ir acompañado de otros archivos o pequeños scripts). Le enseña a Claude **cómo realizar una tarea concreta, paso a paso y siempre de la misma forma**, sin que tengas que volver a explicarlo cada vez.

Piensa en una Skill como una **receta de cocina guardada**: en vez de explicarle a alguien cómo hacer una tortilla de patatas cada vez que se la pides, le entregas la receta escrita una sola vez. A partir de ahí, cada vez que pidas "una tortilla", esa persona ya sabe exactamente qué pasos seguir.

### 5.2 ¿Cómo funcionan internamente?

1. Tú (o la comunidad de Anthropic, o tu centro educativo) creáis una Skill con un **nombre** y una **descripción** clara de cuándo debe usarse.
2. Cuando escribes un mensaje, Claude revisa rápidamente los nombres y descripciones de las Skills disponibles.
3. Si una Skill encaja con lo que has pedido, Claude **carga automáticamente** sus instrucciones completas antes de responder.
4. Si la Skill no encaja con tu petición, Claude simplemente no la usa, así no se "satura" la conversación con información innecesaria.

### 5.3 Cómo usar una Skill ya existente

1. Ve al menú de **herramientas** junto a la caja de texto (o a Configuración → Capacidades/Skills, según la versión de la interfaz).
2. Busca la Skill que necesites en la lista disponible (Anthropic publica algunas oficiales, como las relacionadas con documentos Word, Excel o PDF) o sube la tuya.
3. Actívala para esa conversación o para el Proyecto en el que estés trabajando.
4. Escribe tu petición con normalidad: Claude detectará que la Skill es relevante y la aplicará automáticamente.

### 5.4 Cómo crear tu propia Skill (sin programar)

No necesitas saber programación para crear una Skill sencilla, basta con explicarle a Claude lo que quieres:

1. Dile a Claude algo como: *"Quiero crear una Skill que revise informes de prácticas de redes y compruebe que incluyen: topología, direccionamiento IP, tabla de subredes y conclusiones. Ayúdame a crearla."*
2. Claude generará el contenido de la Skill (nombre, descripción y las instrucciones).
3. Guarda esa Skill desde la propia interfaz (normalmente hay un botón de "Guardar como Skill" o similar).
4. A partir de ese momento, podrás activarla en cualquier conversación.

### 5.5 Ejemplos prácticos para un aula de Sistemas

| Skill de ejemplo | Para qué sirve |
|---|---|
| *"Corrector de prácticas de redes"* | Revisa que un informe de prácticas siga siempre la misma estructura y nomenclatura |
| *"Generador de documentación técnica"* | Convierte notas sueltas en un documento con formato estándar (introducción, requisitos, pasos, conclusión) |
| *"Plantilla de incidencias de soporte"* | Redacta partes de incidencia con el mismo formato cada vez (síntoma, diagnóstico, solución) |

> 💡 La gran ventaja de las Skills frente a copiar y pegar instrucciones largas cada vez es que **se mantienen organizadas, son reutilizables, y se pueden compartir** con el resto de la clase o del centro.

---

## 6. Instalación de Claude en el equipo local

### 6.1 Primera aclaración importante

Como se explicaba en la introducción, **Claude no es un modelo de IA que se descargue y ejecute en tu ordenador**, como sí ocurre con otros modelos de código abierto. El "cerebro" de Claude siempre se ejecuta en los servidores de Anthropic, en la nube. Por tanto, **"instalar Claude en local" significa instalar la aplicación de escritorio**, que es simplemente una ventana de acceso más cómoda que el navegador, pero que **sigue necesitando conexión a internet** para funcionar.

### 6.2 Pasos para instalar la app de escritorio

1. Accede a la página oficial de descargas: **[claude.ai/download](https://claude.ai/download)**.
2. Selecciona tu sistema operativo (Windows o macOS).
3. Descarga el instalador y ejecútalo, igual que harías con cualquier otro programa (siguiente, siguiente, aceptar términos, finalizar).
4. Abre la aplicación e inicia sesión con tu cuenta de Claude (la misma que usas en la web).
5. Listo: ya tienes Claude como aplicación independiente, sin depender de tener el navegador abierto.

### 6.3 Ventajas de usar la app de escritorio frente a la web

| Ventaja | Explicación |
|---|---|
| **Acceso rápido** | Se puede abrir con un atajo de teclado, sin buscar la pestaña del navegador |
| **Menos distracciones** | Funciona en su propia ventana, separada de las demás pestañas del navegador |
| **Integración con el sistema** | Permite arrastrar archivos directamente desde el escritorio o el explorador de archivos |
| **Notificaciones nativas** | Avisos del sistema operativo cuando una tarea larga termina |
| **Estabilidad** | No se ve afectada si el navegador se cuelga o tienes demasiadas pestañas abiertas |

### 6.4 ¿Cómo afecta esto a tu equipo real?

Es una de las preguntas más importantes desde el punto de vista de Sistemas, y la respuesta es tranquilizadora:

- **Consumo de hardware:** la app de escritorio es ligera. Todo el "trabajo pesado" (ejecutar el modelo de IA) ocurre en los servidores de Anthropic, no en tu CPU o GPU. Tu equipo solo necesita potencia para mostrar la interfaz, similar a tener una pestaña de navegador abierta.
- **Requisitos:** no necesitas una tarjeta gráfica potente ni mucha RAM libre, a diferencia de lo que ocurriría si quisieras ejecutar un modelo de IA de código abierto en local.
- **Conexión a internet:** es imprescindible. Sin conexión, la app no podrá comunicarse con los servidores y no funcionará (salvo para revisar conversaciones ya cargadas previamente en caché).
- **Almacenamiento:** ocupa poco espacio en disco, ya que no almacena el modelo de IA, solo la propia aplicación.
- **Privacidad y datos:** al usar la app, tus mensajes y archivos adjuntos se envían a los servidores de Anthropic para ser procesados, igual que ocurre con la versión web. Conviene revisar la configuración de privacidad (apartado 2.4) antes de subir documentación sensible o con datos personales, especialmente en un contexto educativo.
- **Permisos del sistema:** al instalar la app, el sistema operativo puede pedir permisos básicos (acceso a archivos para poder adjuntarlos, notificaciones, inicio automático). Son permisos estándar de cualquier aplicación de escritorio, no privilegios especiales sobre el sistema.

> ✅ **En resumen:** instalar la app de escritorio de Claude es una operación segura y ligera para tu equipo, comparable a instalar cualquier aplicación de mensajería o de productividad. No transforma tu ordenador en un "servidor de IA" ni exige hardware especial, porque toda la inteligencia artificial sigue funcionando en la nube.

---

## 7. Glosario rápido

| Término | Significado |
|---|---|
| **Prompt** | El mensaje o instrucción que le escribes a Claude |
| **Modelo** | La versión concreta de la IA que procesa tu petición (Haiku, Sonnet, Opus) |
| **Token** | Unidad mínima de texto que procesa el modelo (aproximadamente, un trozo de palabra) |
| **Proyecto** | Espacio de trabajo en Claude.ai con instrucciones y archivos fijos |
| **Artefacto** | Documento, código o gráfico generado por Claude que se muestra en ventana aparte |
| **Skill / Habilidad** | Paquete reutilizable de instrucciones que Claude carga cuando es relevante |
| **Agente** | Sistema de IA capaz de seguir instrucciones y ejecutar tareas de varios pasos por sí mismo |
| **API** | Forma de conectar Claude dentro de programas propios, mediante código |
| **Claude Code** | Herramienta de Anthropic para usar Claude como agente de programación desde la terminal |
| **Nube / Cloud** | Servidores de Anthropic donde realmente se ejecuta el modelo de IA |

---

## 8. Preguntas frecuentes (FAQ)

**¿Necesito saber programar para usar Claude?**
No. La mayoría de funciones (chat, Proyectos, Skills, app de escritorio) están pensadas para usarse sin escribir código. Solo Claude Code y la API requieren conocimientos técnicos, y son opcionales.

**¿Puedo usar Claude sin pagar?**
Sí, existe un plan gratuito (Free) con límites de uso. Para uso académico habitual, el plan Pro suele ofrecer una experiencia más fluida, pero no es obligatorio.

**¿Mis conversaciones se guardan para siempre?**
Puedes consultar y borrar tu historial desde Configuración. También puedes decidir si tus conversaciones se usan o no para mejorar el modelo, según las opciones de privacidad disponibles en tu cuenta.

**¿Qué pasa si Claude se equivoca?**
Como cualquier IA, Claude puede cometer errores o dar información incorrecta (esto se llama "alucinación"). Es importante revisar siempre la información importante, especialmente en tareas técnicas o académicas, y contrastarla con fuentes oficiales.

**¿Puedo usar Claude en el móvil?**
Sí, existen aplicaciones oficiales para iOS y Android con prácticamente las mismas funciones que la web.

---

*Manual elaborado como guía introductoria para el alumnado de Formación Profesional de la familia de Sistemas. Los nombres de modelos, planes y precios concretos pueden cambiar con el tiempo: se recomienda consultar siempre la documentación oficial en [claude.com](https://claude.com) y [support.claude.com](https://support.claude.com) para confirmar los datos más recientes.*

# TOP 
*Actualizado a junio de 2026. Las plataformas lanzan modelos y cambian precios con mucha frecuencia, conviene verificar en webs oficiales*

> Quiero hcer el mismo esquema en todas modelos uso y pago 

## Claude
Modelos de lenguaje conversacional desarrollada por **Anthropic**, una empresa de IA centrada en la seguridad y la interpretabilidad de los sistemas. Claude se utiliza como asistente conversacional (a través de Claude.ai), como agente de programación (Claude Code) y como motor de IA para desarrolladores a través de la API de Anthropic. Destaca por su enfoque en el razonamiento extendido, el manejo de contexto muy largo (hasta 1 millón de tokens) y un comportamiento orientado a la seguridad y la honestidad.

### Modelos actuales de Claude

| Modelo | Categoría | Precio API (entrada / salida por 1M tokens) | Contexto máximo | Uso principal |
|---|---|---|---|---|
| **Claude Opus 4.8** | Modelo insignia (flagship) | 5 $ / 25 $ (Modo rápido: 10 $ / 50 $) | 1.000.000 tokens | El más potente; "pensamiento adaptativo" (decide cuánto razonar según la tarea), ideal para programación compleja y agentes autónomos de larga duración |
| **Claude Opus 4.7** | Flagship anterior | 5 $ / 25 $ | 1.000.000 tokens | Visión de alta resolución y tareas agénticas de horizonte largo |
| **Claude Sonnet 4.6** | Equilibrado | 3 $ / 15 $ | 1.000.000 tokens | Mejor relación calidad-precio; uso diario, programación y redacción |
| **Claude Haiku 4.5** | Rápido y económico | 1 $ / 5 $ | 200.000 tokens | Clasificación, tareas de alto volumen, respuestas instantáneas |

> Nota: Anthropic presentó en junio de 2026 una nueva generación superior llamada **Mythos 5** (y su variante reforzada **Fable 5**), pero el acceso quedó temporalmente suspendido por una directiva de control de exportaciones, por lo que de momento no están disponibles para el público general.

### ¿Cómo se usa y cómo se paga?

- **Claude.ai (chat):** plan **Free** (gratuito, con límites de mensajes), **Pro** (~20 $/mes, o ~17 $/mes en facturación anual), **Max** (100 $ o 200 $/mes, para uso intensivo) y planes **Team/Enterprise** para empresas.
- **API de Anthropic:** se paga **por token** consumido (no por mensaje), distinguiendo tokens de *entrada* (lo que se envía al modelo) y de *salida* (lo que el modelo genera). El caché de prompts reduce hasta un 90% el coste de tokens repetidos, y el procesamiento por lotes (*batch*) ofrece un 50% de descuento.
- **Claude Code:** la herramienta de programación agéntica de Anthropic, consume el mismo sistema de tokens/planes que Claude.ai.

---

## ChatGPT

> **Definición:** ChatGPT es el asistente conversacional de **OpenAI**, uno de los productos de IA generativa más usados del mundo. Permite chatear, generar imágenes, analizar documentos, navegar por internet, escribir y depurar código (a través de Codex) y ejecutar tareas de varios pasos de forma semiautónoma ("modo agente"). Se apoya en la familia de modelos **GPT**.

### Modelos actuales de ChatGPT / GPT

| Modelo | Categoría | Precio API (entrada / salida por 1M tokens) | Disponibilidad en ChatGPT | Uso principal |
|---|---|---|---|---|
| **GPT-5.5 Pro** | Razonamiento máximo | 30 $ / 180 $ | Planes Pro y superiores | Tareas multipaso muy complejas, máximo rendimiento en modo agente |
| **GPT-5.5 Instant** | Modelo por defecto | 5 $ / 30 $ | Todos los planes, incluido el gratuito | Uso cotidiano: rapidez y comprensión de intención |
| **GPT-5.4 Thinking** | Razonamiento profundo | — (incluido en Plus y superiores) | Plus, Pro, Business, Enterprise | Verificar estrategias, código complejo, auditorías, muestra el razonamiento paso a paso |
| **GPT-5.3-Codex** | Programación agéntica | Según uso en Codex | Codex / planes de pago | Generación y refactorización de código de forma autónoma |
| GPT-5.4 mini / nano | Económicos | Tarifas reducidas | Solo vía API | Tareas ligeras o de alto volumen a bajo coste |

### ¿Cómo se usa y cómo se paga?

- **Planes de ChatGPT:** **Free** (gratis, con anuncios y límites estrictos), **Go** (~8 $/mes, más mensajes), **Plus** (~20 $/mes, acceso a los modelos avanzados, Deep Research limitado, generación de imágenes y Sora), **Pro** (~200 $/mes, acceso ilimitado a los modelos de razonamiento Pro y al doble de contexto) y **Business/Enterprise** (precios por usuario, para empresas).
- **API de OpenAI:** facturación **por token** (entrada y salida por separado), igual que en Anthropic. El uso vía Codex (agente de programación) también consume tokens según el modelo elegido.

---

## Gemini

> **Definición:** Gemini es la familia de modelos de IA multimodal de **Google DeepMind**, integrada de forma nativa en el buscador de Google, Android, Google Workspace (Gmail, Docs, Drive) y disponible como app independiente y a través de la API en Google AI Studio / Vertex AI. Está diseñada desde el inicio para entender texto, imagen, audio, vídeo y código de forma conjunta.

### Modelos actuales de Gemini

| Modelo | Categoría | Precio API (salida por 1M tokens) | Contexto máximo | Uso principal |
|---|---|---|---|---|
| **Gemini 3.1 Deep Think** | Razonamiento extendido | Solo incluido en plan Ultra | Muy amplio | Investigación científica y problemas matemáticos/lógicos de varios pasos |
| **Gemini 3.1 Pro** | Razonamiento avanzado | ~12 $ | 1.000.000 tokens | Análisis profundo, generación de vídeo, tareas profesionales |
| **Gemini 3.5 Flash** | Rápido, agéntico | ~9 $ | Amplio | Programación agéntica y tareas que combinan velocidad con capacidad |
| **Gemini 3.1 Flash-Lite** | Económico | ~1,50 $ | Amplio | Clasificación, resumen y *embeddings* en grandes volúmenes |
| **Gemini 2.5 Flash** | Plan gratuito | — | 32.000 tokens | Versión incluida en la cuenta gratuita de Google |

### ¿Cómo se usa y cómo se paga?

- **App Gemini / Google AI:** plan **Free** (usa Gemini 2.5 Flash, con contexto limitado), **Google AI Pro** (~20 $/mes: Gemini 3.1 Pro, 1M de tokens de contexto, Deep Research, NotebookLM Plus y 2 TB en Google One) y **Google AI Ultra** (dos niveles, aproximadamente 100 $ y 200 $/mes, que añaden Deep Think y mayores cuotas de uso).
- **API (Vertex AI / Google AI Studio):** pago **por token**, con tarifas distintas de entrada y salida; si el contexto supera los 200.000 tokens se aplican tarifas de "contexto largo".
- Integración nativa y gratuita (con límites) dentro de productos de Google como Search, Gmail o Android.

---

## Copilot

> **Definición:** Copilot es el nombre que **Microsoft** utiliza para sus asistentes de IA, repartidos en dos productos diferenciados: **Microsoft 365 Copilot** (asistente de productividad integrado en Word, Excel, PowerPoint, Outlook y Teams) y **GitHub Copilot** (asistente de programación integrado en editores de código). A diferencia de Claude, ChatGPT o Gemini, Copilot no tiene un modelo propio: actúa como una capa que **orquesta modelos de distintos proveedores** (principalmente GPT de OpenAI, y en el caso de GitHub Copilot también Claude de Anthropic y Gemini de Google).

### Modelos disponibles según el producto Copilot

| Producto | Modelos que utiliza | Cómo se selecciona | Uso principal |
|---|---|---|---|
| **Microsoft Copilot** (consumidor/Windows) | Modelos GPT de OpenAI (incluye un modo "Think Deeper" de razonamiento) | Automático, según el plan | Asistente general, voz, generación de imágenes, búsqueda |
| **Microsoft 365 Copilot** (empresas) | Modelos GPT más recientes, con acceso a los datos de la organización | Automático | Redacción y análisis de documentos, correos, hojas de cálculo y reuniones dentro de Office |
| **GitHub Copilot** (programación) | GPT-5.5, Claude Opus/Sonnet (según el plan) y Gemini 3.1 Pro | El usuario puede elegir el modelo en el chat/modo agente | Autocompletado de código, revisión de PRs, modo agente para tareas de desarrollo |

### ¿Cómo se usa y cómo se paga?

- **Microsoft Copilot (consumidor):** plan **Free** con funciones básicas, y **Copilot Pro** (~20 $/mes) con acceso prioritario a los modelos más recientes y herramientas adicionales.
- **Microsoft 365 Copilot:** requiere una licencia de Microsoft 365 aparte; el coste adicional ronda los 30 $/usuario/mes.
- **GitHub Copilot:** **Free** (uso limitado), **Pro** (10 $/mes), **Pro+** (39 $/mes, con acceso a los modelos Opus más recientes) y **Business/Enterprise** (19–39 $/usuario/mes). Desde el 1 de junio de 2026, GitHub sustituyó las cuotas fijas por un sistema de **créditos de IA** (1 crédito = 0,01 $), donde cada interacción consume créditos según los tokens reales (entrada, salida y caché) y el modelo elegido — es decir, un pago **por uso/token**, similar al de las APIs de Anthropic, OpenAI y Google.

---

## Resumen comparativo rápido

| | Claude (Anthropic) | ChatGPT (OpenAI) | Gemini (Google) | Copilot (Microsoft) |
|---|---|---|---|---|
| Modelo propio | Sí | Sí | Sí | No (orquesta GPT, Claude y Gemini) |
| Modelo tope actual | Opus 4.8 | GPT-5.5 Pro | Gemini 3.1 Deep Think | Depende del producto |
| Modelo económico | Haiku 4.5 | GPT-5.4 nano | Gemini 3.1 Flash-Lite | — |
| Plan de pago de entrada | Pro (~20 $/mes) | Plus (~20 $/mes) | AI Pro (~20 $/mes) | Copilot Pro (~20 $/mes) |
| Facturación API | Por token | Por token | Por token | Por token (créditos GitHub) |
| Punto fuerte | Razonamiento, seguridad, contexto largo | Ecosistema, modo agente, adopción masiva | Integración con Google y multimodalidad | Integración profunda en Office/Windows/GitHub |

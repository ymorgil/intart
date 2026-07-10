# 🧩 Skills (Claude)

> Documento actualizado a **julio de 2026**.

Las **Skills** (habilidades) son la forma que tiene Claude de aprender a hacer bien una tarea concreta y repetible, sin que tengas que volver a explicárselo cada vez. Son carpetas con instrucciones, scripts y recursos que Claude carga de forma dinámica solo cuando son relevantes para lo que le pides.

![Claude](https://upload.wikimedia.org/wikipedia/commons/5/58/Claude-ai-icon.svg)

!!! note "Skill, Proyecto y Conector no son lo mismo"

    Un **Proyecto** carga contexto de fondo siempre que abres un chat dentro de él. Una **Skill** es específica de una tarea y se activa dinámicamente cuando hace falta, en cualquier lugar de Claude (chat, Cowork, Code, API). Un **Conector** es el puente que da acceso a datos externos (Drive, Notion...). Puedes combinar los tres a la vez.

## ¿Qué es una Skill exactamente?

Una Skill es, en su forma más simple, **una carpeta con un archivo `SKILL.md`** que contiene metadatos (nombre y descripción) en formato YAML y, debajo, las instrucciones en Markdown que Claude debe seguir cuando la Skill esté activa. Puede incluir también scripts auxiliares (Python, Bash, Node) y archivos de referencia.

```yaml
---
name: mi-skill
description: Descripción clara de qué hace esta skill y cuándo usarla
---

# Mi Skill

[Instrucciones que Claude seguirá cuando esta skill esté activa]

## Ejemplos
- Ejemplo de uso 1
- Ejemplo de uso 2

## Guías
- Guía 1
- Guía 2
```

Los dos únicos campos obligatorios del *frontmatter* son:

| Campo | Qué contiene |
|---|---|
| **`name`** | Identificador único de la skill (minúsculas, guiones en vez de espacios). |
| **`description`** | Descripción completa de qué hace la skill y **cuándo debe activarse**; Claude usa este campo para decidir si la skill es relevante para tu petición, así que cuanto más preciso, mejor "engancha" en el momento adecuado. |

## Cómo se activan las Skills

No hace falta invocarlas manualmente: en Claude.ai, Cowork y Claude Code, Claude revisa qué skills tiene disponibles y activa automáticamente la que mejor encaje con tu petición, en función de su `description`. Por ejemplo, si pides "conviérteme estos apuntes en una presentación PowerPoint", Claude activa una skill diseñada para esa tarea sin que tengas que nombrarla.

!!! example "Cómo pedirle a Claude que use una skill instalada como plugin (Claude Code)"

    ```text
    /plugin marketplace add anthropics/skills
    ```

    Y después, para instalar un conjunto concreto de skills:

    ```text
    /plugin install document-skills@anthropic-agent-skills
    /plugin install example-skills@anthropic-agent-skills
    ```

## Cómo crear una skill personalizada

1. Crea una carpeta con el nombre de tu skill (minúsculas, guiones).
2. Dentro, crea el archivo `SKILL.md` con el *frontmatter* (`name` + `description`) y las instrucciones en Markdown.
3. Si la skill necesita lógica reutilizable (por ejemplo, generar un archivo con un formato exacto), añade scripts en una subcarpeta `scripts/`.
4. Si necesita documentación de referencia larga que no quieres que ocupe espacio en el prompt principal, ponla en una subcarpeta `references/` y menciónala desde `SKILL.md`.
5. Sube la skill a Claude.ai (Configuración → Skills → Subir) o instálala como plugin de Claude Code.

!!! tip "La descripción es la parte más importante"

    Si la `description` es vaga ("ayuda con documentos"), Claude no sabrá cuándo activarla. Si es precisa ("Úsala SIEMPRE que el usuario pida convertir una práctica en PDF con el formato del centro, o mencione 'plantilla de práctica'..."), la skill se dispara justo cuando hace falta y se queda callada el resto del tiempo.

---

## Skills propias (adaptadas del repositorio privado)

Estas dos skills están creadas y en uso por el autor de este documento; se documentan aquí de forma resumida (sin reproducir los scripts completos) como referencia de qué es posible construir con una skill bien diseñada.

### apuntes-a-diapositivas

![PowerPoint](https://commons.wikimedia.org/wiki/Special:FilePath/Microsoft_Office_PowerPoint_%282019%E2%80%93present%29.svg)

Convierte apuntes o material didáctico en Markdown en una presentación PowerPoint (`.pptx`) con un diseño docente consistente: título con línea separadora, banda de color al pie, viñetas cuadradas, portada con índice enlazado, cajas de código y de nota, colocación automática de imágenes, y un mínimo de 33 diapositivas por presentación.

| Aspecto | Cómo funciona |
|---|---|
| **Disparo** | El usuario pide "convertir estos apuntes en diapositivas", "hacer una presentación a partir de este markdown", o menciona pasar notas técnicas a diapositivas para clase. |
| **Paleta de color** | Antes de generar nada, la skill **siempre** pregunta al usuario qué paleta quiere entre tres opciones (violeta, naranja, gris azulado) — nunca asume una por defecto. |
| **Imágenes que faltan** | Busca y añade imágenes de internet en las diapositivas que no tengan imagen propia, con una jerarquía clara de intentos según la infraestructura disponible (descarga directa → navegador conectado → aviso si no hay forma de conseguirlas). |
| **Formato Markdown de entrada** | `#` genera portada/índice, `##` genera una diapositiva nueva, listas con guiones se convierten en viñetas, bloques de código y citas (`>`) se convierten en cajas destacadas. |
| **Verificación final** | Revisa cuántas diapositivas se generaron frente al mínimo de 33 y comprueba que ninguna imagen quedó como recuadro gris (fallo de descarga). |

### practica-a-pdf

![PDF](https://commons.wikimedia.org/wiki/Special:FilePath/PDF_file_icon.svg)

Genera el PDF de una práctica o actividad a partir de un Markdown, replicando pixel a pixel una plantilla institucional: cabecera con logos repetida en todas las páginas, banda de color con el código y título de la unidad, apartados numerados (siempre 10), bandas de color opcionales para agrupar apartados por bloques temáticos, y las secciones finales "Recursos" y "Calificación y documentación" con valores por defecto si el Markdown no las incluye.

| Aspecto | Cómo funciona |
|---|---|
| **Disparo** | El usuario pide convertir una práctica/actividad en Markdown a PDF/Word con el formato del centro, o menciona el código de una unidad de trabajo con apartados numerados. |
| **Convención de entrada** | *Front matter* YAML obligatorio con el código y título de la unidad; el cuerpo es siempre una lista numerada `1.` a `10.`, con subapartados anidados que se renumeran automáticamente. |
| **Valores por defecto** | Si el Markdown no incluye las secciones "Recursos" o "Calificación y documentación", la skill rellena automáticamente unos valores estándar del centro en vez de dejarlas vacías. |
| **Verificación final** | Comprueba que aparecen las 10 entradas numeradas y las dos secciones finales en el PDF generado antes de entregarlo. |

!!! warning "Adaptar antes de reutilizar"

    Estas dos skills están construidas a medida de una plantilla institucional concreta (colores, logos, textos por defecto). Si quieres reutilizar la idea en otro contexto, cambia esos valores fijos en vez de copiar la skill tal cual.

---

## Skills públicas destacadas (repositorio oficial de Anthropic)

Anthropic mantiene un repositorio público con skills de ejemplo en [github.com/anthropics/skills](https://github.com/anthropics/skills){target="_blank"}, pensado como fuente de inspiración y como las skills de documentos que usa el propio Claude.ai.

![GitHub](https://miro.medium.com/v2/resize:fit:700/0*oRRpMJ9XqkRnYLhW.png)

### Skills de documentos (ya activas por defecto en Claude.ai)

| Skill | Para qué sirve |
|---|---|
| **docx** | Crear, leer y editar documentos Word: tablas de contenido, encabezados, membretes, control de cambios y comentarios. |
| **pdf** | Extraer texto/tablas, combinar o dividir PDF, rellenar formularios, añadir marcas de agua, hacer OCR sobre PDF escaneados. |
| **pptx** | Crear y editar presentaciones PowerPoint: diapositivas, plantillas, notas del orador. |
| **xlsx** | Crear y editar hojas de cálculo Excel: fórmulas, formato condicional, gráficos, análisis de datos. |

### Skills de ejemplo (creativas y técnicas)

| Skill | Categoría | Para qué sirve |
|---|---|---|
| **algorithmic-art** | Creativa | Genera arte generativo con p5.js a partir de una descripción. |
| **canvas-design** | Creativa | Crea piezas de diseño visual en formato `.png`/`.pdf` (carteles, tarjetas, portadas). |
| **webapp-testing** | Técnica | Verifica visualmente una aplicación web usando Playwright, útil para comprobar que una interfaz se ve como se espera. |
| **brand-guidelines** | Empresarial | Aplica las guías de marca oficiales de Anthropic al generar contenido de ejemplo. |
| **mcp-builder** | Técnica | Ayuda a generar servidores MCP (Model Context Protocol) siguiendo buenas prácticas. |

!!! example "Prompt para pedirle a Claude que te explique una skill instalada"

    ```text
    Actúa como experto en el sistema de Skills de Claude. Explícame qué hace
    exactamente la skill "canvas-design", cuándo se activa automáticamente, y
    ponme un ejemplo de petición que la dispararía frente a otra petición
    parecida que NO la activaría.
    ```

## Skills y el ecosistema educativo

Para un docente que documenta en Markdown y publica con MkDocs, las skills más directamente útiles son las de **documentos** (docx, pdf, pptx) para generar entregables a partir de los propios apuntes, y las **skills a medida** como las dos anteriores, que automatizan una plantilla institucional repetitiva (prácticas, presentaciones) en vez de maquetar el documento a mano cada vez.

!!! tip "Idea de skill propia: apuntes-a-mkdocs"

    Una skill interesante para este mismo proyecto de documentación sería una que tome apuntes sueltos (Word, PDF, notas de clase) y los convierta directamente al formato Markdown con front matter que ya usa este sitio de MkDocs Material, incluyendo la detección automática de si el contenido necesita un aviso `!!! note`, un bloque de código o una tabla.

## Dónde viven las skills en disco

Cuando trabajas con Claude Code o Cowork, las skills instaladas se organizan como carpetas dentro de un directorio de skills del proyecto o del plugin correspondiente, cada una con su propio `SKILL.md` y sus recursos:

```text
skills/
├── apuntes-a-diapositivas/
│   ├── SKILL.md
│   ├── scripts/
│   │   ├── generate_pptx.py
│   │   └── palettes.py
│   └── references/
│       └── formato-markdown.md
├── practica-a-pdf/
│   ├── SKILL.md
│   └── scripts/
│       ├── generate.sh
│       └── md_to_json.py
└── docx/
    └── SKILL.md
```

![Estructura de carpetas](https://commons.wikimedia.org/wiki/Special:FilePath/Folder_icon.svg)

Claude no necesita que le indiques la ruta manualmente: en cuanto la skill está instalada/disponible, la detecta automáticamente comparando tu petición con el campo `description` de cada `SKILL.md`.

## Comparativa con Gems (Gemini) y GPTs (ChatGPT)

| | Skills (Claude) | Gems (Gemini) | GPTs (ChatGPT) |
|---|---|---|---|
| Unidad básica | Carpeta con `SKILL.md` (+ scripts opcionales) | Formulario con instrucciones + conocimientos | Formulario con instrucciones + conocimiento + herramientas |
| Activación | Automática, según la petición del usuario | Manual: hay que abrir el Gem concreto | Manual: hay que abrir el GPT concreto |
| Puede ejecutar código/scripts propios | Sí (Python, Bash, Node) | No directamente | Solo mediante Acciones/Apps configuradas |
| Requiere plan de pago para crear | No (Free ya permite subir skills) | No (Free ya permite crear Gems) | Sí (Plus o superior) |
| Compartición pública tipo "tienda" | Marketplace de plugins de Claude Code | No hay tienda pública | GPT Store |

## Preguntas frecuentes

!!! question "¿Las skills consumen más cuota que un chat normal?"

    Las instrucciones de la skill se cargan solo cuando es relevante, de forma parecida a un Gem o un GPT: no supone un coste aparte del uso normal del modelo.

!!! question "¿Puedo usar una skill de otra persona sin modificarla?"

    Sí, si te la comparten (por ejemplo, instalando el mismo marketplace de plugins en Claude Code) puedes usarla tal cual, o copiarla y adaptarla a tu caso si necesitas cambiar algo.

!!! question "¿Las skills funcionan igual en Claude.ai, Cowork, Code y la API?"

    El concepto es el mismo (una carpeta con `SKILL.md`), pero la forma de instalarlas varía: en Claude.ai se suben desde la configuración de Skills, en Claude Code se instalan como plugins de un marketplace, y en la API se gestionan mediante el Skills API Quickstart.

## Ejemplo propio: boceto de una skill "generador-cuestionarios-gift"

A modo de ejercicio, así se vería el `SKILL.md` de una skill que automatizara los prompts de cuestionarios GIFT recogidos en la página [Moodle](06moodle.md) de este mismo sitio:

```yaml
---
name: generador-cuestionarios-gift
description: Genera cuestionarios en formato GIFT (opción múltiple, verdadero/
  falso, respuesta corta o emparejamiento) listos para importar en el Banco de
  preguntas de Moodle. Úsala cuando el usuario pida "cuestionario para
  Moodle", "preguntas en formato GIFT" o mencione importar preguntas al
  Banco de preguntas.
---

# Generador de cuestionarios GIFT

Cuando el usuario pida un cuestionario para Moodle:
1. Pregunta el tema, el número de preguntas y el tipo (opción múltiple,
   verdadero/falso, respuesta corta o emparejamiento) si no lo ha indicado.
2. Genera las preguntas siguiendo estrictamente la sintaxis GIFT de cada
   tipo (ver ejemplos en references/sintaxis-gift.md).
3. Entrega el resultado en un único bloque de código, listo para copiar en
   un archivo .txt con codificación UTF-8 e importarlo en Moodle.
4. Recuerda al usuario revisar el contenido técnico antes de usarlo en un
   examen que cuente para nota.
```

!!! tip "Buenas prácticas al redactar las instrucciones de una skill"

    - Sé específico en la `description` sobre **cuándo** debe activarse, no solo sobre qué hace.
    - Divide el flujo de trabajo en pasos numerados, igual que en un buen prompt.
    - Si la skill genera un archivo con un formato exacto (como GIFT), incluye siempre un ejemplo literal de la sintaxis dentro de las instrucciones o en un archivo de referencia aparte.
    - Añade un paso final de verificación (releer el resultado, comprobar un recuento, avisar de riesgos) antes de dar la tarea por terminada.

## Preguntas frecuentes adicionales

!!! question "¿Puedo tener varias skills que se activen para la misma petición?"

    Claude puede combinar varias skills a la vez si la tarea lo requiere (por ejemplo, una skill de generación de cuestionarios y la skill `docx` para entregar el resultado en Word), sin que tengas que coordinarlo manualmente.

!!! question "¿Necesito saber programar para crear una skill?"

    No necesariamente. Una skill puede ser solo instrucciones en Markdown, sin ningún script — el ejemplo de `generador-cuestionarios-gift` de arriba no necesita ningún código, solo una descripción precisa del formato de salida.

## Recursos

- [Repositorio oficial de Skills de Anthropic](https://github.com/anthropics/skills){target="_blank"}
- [¿Qué son las Skills? (ayuda oficial)](https://support.claude.com/en/articles/12512176-what-are-skills){target="_blank"}
- [Cómo crear skills personalizadas](https://support.claude.com/en/articles/12512198-creating-custom-skills){target="_blank"}
- [Equipando a los agentes con Agent Skills (blog de ingeniería de Anthropic)](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills){target="_blank"}

# 🖼️ Imágenes

> Documento actualizado a **julio de 2026**. Colección de prompts propios para generación de imágenes con IA (Gemini/Nano Banana, ChatGPT/DALL·E, Midjourney...), junto con las claves para escribir un buen prompt de imagen.

![Generación de imágenes](https://cristhianortega.com/blog/wp-content/uploads/2025/08/nano-banana-google-gemeni-images.png)

!!! note "Un prompt de imagen no es un prompt de texto"

    A diferencia de pedirle un texto a un chatbot, un buen prompt de imagen describe **lo que se debe ver**, no lo que se debe "pensar": encuadre, estilo, iluminación, colores, y elementos concretos en la escena. Cuantos más detalles visuales concretos incluyas, más se parecerá el resultado a lo que tienes en mente.

## Elementos clave de un buen prompt de imagen

1. **Sujeto principal** — quién o qué aparece, con el máximo detalle posible (ropa, pose, expresión).
2. **Tipo de imagen** — fotografía realista, ilustración digital, cómic, boceto a lápiz, render 3D...
3. **Estilo artístico** — steampunk, minimalista, ciberpunk, acuarela, etc.
4. **Encuadre y cámara** — plano general, primer plano, vista cenital, tipo de lente (gran angular, macro, teleobjetivo).
5. **Iluminación** — luz natural, luz de estudio, neón, hora dorada, contraluz.
6. **Fondo/entorno** — interior, exterior, fondo liso, paisaje urbano.
7. **Nivel de detalle/render** — 4K, alta resolución, "hyper detailed", estilo de render (Octane, Unreal Engine...).

!!! tip "Usa paréntesis para dar más peso a una palabra clave"

    Algunas herramientas (como Leonardo AI o Stable Diffusion) permiten aumentar la importancia de una palabra concreta envolviéndola en paréntesis triples, por ejemplo `(((luz de neón)))`. Ábusa de esto solo en la palabra realmente decisiva, no en toda la frase, o el resultado se satura.

## Prompts propios

## 👉 Rompiendo la realidad virtual

```text
Crea una ilustración realista de una persona que sea la de la foto saliendo
de un marco que simula una publicación de Instagram. El marco debe tener
detalles como el logo de Instagram visible en la parte superior, una foto
de perfil circular, el nombre de usuario @ymorgil, un símbolo de
verificación azul, botones de reacción (corazón, comentar, compartir,
guardar) y el contador de "likes" [Número de likes 101k] en la parte
inferior.

La persona debe parecer que rasga y rompe únicamente el interior del marco
como si fuese papel o cartón, manteniendo intactos los bordes y elementos
de la interfaz de Instagram. Las partes desgarradas deben estar solo en el
área central donde aparece la foto. La persona debe estar sosteniendo un
Huawei P30 como si estuviera grabando, con el flash de la cámara encendido
y visible. La persona debe sonreír mientras graba. Mantén un fondo claro y
minimalista para destacar el efecto 3D.

El estilo debe ser amigable, juvenil, moderno y ligeramente caricaturesco,
pero con detalles realistas. El Huawei debe ser claramente reconocible como
el modelo P30, con sus características distintivas y el flash LED
brillando intensamente.
```

!!! example "Por qué funciona este prompt"

    Combina un sujeto muy concreto (persona rompiendo un marco de Instagram), detalles técnicos exactos (modelo de móvil, contador de likes) y una instrucción de estilo clara ("amigable, juvenil, moderno, ligeramente caricaturesco"). Esa combinación de "escena + detalle técnico + estilo" es la receta general para cualquier prompt de imagen elaborado.

## Retrato profesional a partir de una foto

```text
A partir de la foto que te adjunto, genera un retrato de estilo fotografía
corporativa profesional: fondo gris degradado neutro, iluminación de
estudio suave (softbox a 45 grados), traje de chaqueta oscuro, expresión
seria pero cercana, encuadre de medio cuerpo, cámara a la altura de los
ojos, objetivo de 85mm, alta resolución, sin cambiar los rasgos faciales
originales de la persona.
```

Útil para generar una foto de perfil coherente para todo el equipo docente de un departamento, partiendo de fotos cotidianas.

## Diagrama técnico ilustrado (para apuntes)

```text
Genera una ilustración estilo diagrama técnico, plano, minimalista, sobre
fondo blanco, que represente [concepto técnico, ej. "una arquitectura de
red con firewall, DMZ y red interna"]. Usa iconos simples y reconocibles
para cada elemento, etiquetas de texto claras en español, una paleta de
colores limitada a 3 tonos (azul, gris y un color de acento), y sin
sombreados ni efectos 3D. El resultado debe poder insertarse directamente
en unos apuntes de clase sin distraer del contenido técnico.
```

!!! tip "Para documentación técnica, pide siempre estilo plano"

    Si el objetivo es una imagen para insertar en apuntes o documentación (no una imagen "bonita" de portada), pide explícitamente estilo plano/minimalista y sin efectos 3D: los modelos de imagen tienden por defecto a un estilo muy recargado que distrae del contenido técnico.

## Mascota o icono para un proyecto docente

```text
Diseña una mascota simple en estilo icono plano (flat design) para un
proyecto de documentación técnica llamado "[nombre del proyecto]". Debe
representar [concepto, ej. "un servidor amigable con gafas"], usar como
máximo 3 colores, tener un contorno limpio sin degradados, y funcionar
tanto en tamaño grande (portada de una web) como en tamaño pequeño
(favicon de 32x32 píxeles).
```

![Ejemplo de icono de proyecto](https://cdn-icons-png.flaticon.com/512/910/910473.png)

## Portada de presentación con temática técnica

```text
Genera una imagen de portada horizontal (formato 16:9) para una
presentación sobre [tema técnico, ej. "contenedores Docker"]. Estilo
ilustración digital plana, paleta de colores fría (azules y morados),
composición asimétrica con el elemento principal desplazado a la derecha
para dejar espacio de texto a la izquierda, sin texto incluido en la
imagen (el texto se añadirá después en la propia diapositiva).
```

!!! tip "No pidas texto dentro de la imagen si luego lo vas a editar en la diapositiva"

    Los modelos de imagen todavía cometen errores tipográficos frecuentes al escribir palabras dentro de la escena. Si el texto final (título, subtítulo) se va a añadir después en PowerPoint o en la propia diapositiva Markdown, pide expresamente una imagen **sin texto** y dejas la tipografía real para la herramienta de edición.

## Personaje recurrente para una serie de apuntes

```text
Diseña un personaje mascota recurrente: un pequeño robot de estilo
amigable, cuerpo redondeado, colores azul y blanco, sin rasgos faciales
amenazantes, apto para todas las edades. Genera 4 poses distintas del
mismo personaje sobre fondo transparente: (1) saludando, (2) señalando
hacia la derecha con el brazo, (3) con cara de sorpresa y un signo de
interrogación al lado, (4) con los brazos cruzados en pose "pensativo".
Mantén exactamente el mismo diseño de personaje en las 4 poses.
```

Un personaje recurrente ayuda a dar identidad visual a una serie de apuntes o a una web de documentación: por ejemplo, usarlo junto a los avisos `!!! tip` o `!!! note` a lo largo del sitio.

![Ejemplo de mascota estilo icono](https://cdn-icons-png.flaticon.com/512/910/910473.png)

## Captura de pantalla simulada para un tutorial

```text
Genera una captura de pantalla simulada de una interfaz de escritorio tipo
Linux (GNOME), mostrando una ventana de terminal semitransparente con texto
verde sobre fondo negro, y una ventana de gestor de archivos al fondo con
iconos de carpetas. Estilo plano, sin efectos de brillo excesivos, apto
para insertarse en un tutorial paso a paso donde después se recortará y
anotará con flechas.
```

!!! warning "Una captura simulada no sustituye a una real"

    Estas imágenes "simuladas" sirven para portadas o ilustraciones genéricas, pero **nunca** para un tutorial técnico real: en ese caso, usa siempre una captura de pantalla auténtica de tu propio sistema, para no inducir a error con botones o menús que no existen tal cual en la versión real del software.

## Estilo pixel art para gamificación de contenidos

```text
Genera un icono en estilo pixel art de 32x32 píxeles (efecto 8-bit
retro), representando [elemento, ej. "un cofre de tesoro abierto con un
diploma dentro"], paleta de colores limitada a 8 tonos, contorno de 1
píxel en negro, fondo transparente, pensado para usarse como insignia de
logro (badge) en una actividad gamificada de Moodle.
```

## Prompt negativo: qué evitar en la imagen

Muchas herramientas (Leonardo AI, Stable Diffusion, Midjourney) admiten un campo de "prompt negativo" para indicar explícitamente qué **no** debe aparecer, en vez de intentar describirlo todo en positivo:

```text
Prompt negativo: sin texto, sin marcas de agua, sin manos deformadas, sin
elementos borrosos, sin exceso de saturación de color, sin fondo
recargado.
```

!!! tip "Usa el prompt negativo para corregir defectos recurrentes"

    Si una herramienta concreta suele generarte siempre el mismo defecto (por ejemplo, manos con dedos de más, o marcas de agua falsas), añádelo de forma sistemática al prompt negativo de esa herramienta en vez de repetirlo cada vez de memoria.

## Edición conversacional de una imagen ya generada

Una de las ventajas de los modelos recientes (Nano Banana de Gemini, GPT Image de OpenAI) es que permiten **editar** una imagen ya generada con instrucciones en lenguaje natural, sin tener que rehacer el prompt completo desde cero:

```text
Sobre la imagen anterior: cambia el fondo a un atardecer en tonos naranjas,
mantén exactamente la misma pose y expresión del personaje, y añade una
ligera niebla en la parte baja de la escena.
```

!!! example "Flujo recomendado de edición iterativa"

    1. Genera una primera versión con un prompt completo (sujeto + estilo + encuadre).
    2. Pide cambios puntuales uno a uno ("cambia el color de fondo", "quita el texto de la izquierda"), sin repetir todo el prompt original.
    3. Si el resultado se desvía demasiado tras varios cambios, vuelve a generar desde cero con el prompt original ajustado, en vez de seguir iterando indefinidamente.

## Comparativa rápida de herramientas de generación de imágenes

| Herramienta | Integrada en | Punto fuerte |
|---|---|---|
| **Nano Banana (Gemini)** | Gemini, Google AI Studio | Edición conversacional de imágenes ya generadas, coherencia entre ediciones sucesivas |
| **GPT Image / DALL·E** | ChatGPT | Buen seguimiento de instrucciones de texto dentro de la imagen (carteles, diagramas con etiquetas) |
| **Midjourney** | App propia / Discord | Calidad artística y fotorrealismo muy alto, menos control fino sobre texto en la imagen |
| **Leonardo AI** | App propia | Control avanzado de estilo mediante parámetros y peso de palabras clave |

![Midjourney](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTtP4Gwp2lzS0ww9kwS_yr6T5Gtx6QO3am_Rw&s)

## Buenas prácticas y derechos de uso

!!! warning "Revisa la licencia antes de publicar"

    Si vas a publicar una imagen generada con IA en tu web docente o en materiales oficiales del centro, revisa los términos de uso de la herramienta concreta que la generó: algunas licencias distinguen entre uso personal, educativo y comercial, y algunas herramientas retienen ciertos derechos sobre las imágenes generadas en su plan gratuito.

- **No subas fotos de menores** a herramientas de generación/edición de imágenes por IA sin el consentimiento explícito correspondiente según la normativa de protección de datos de tu centro.
- **Indica en tus apuntes que una imagen es generada por IA** cuando no sea evidente por el contexto, especialmente si representa personas o situaciones que podrían confundirse con fotografías reales.
- **Guarda el prompt usado junto a la imagen** (por ejemplo, en un comentario del Markdown) para poder regenerarla o ajustarla más adelante sin tener que reconstruir el prompt de memoria.

!!! example "Prompt para pedirle a una IA que te ayude a mejorar uno de tus propios prompts de imagen"

    ```text
    Actúa como director de arte experto en generación de imágenes con IA.
    Aquí tienes mi prompt actual: [pega tu prompt]. Sugiéreme 3 variantes que
    mejoren el resultado: una más fotorrealista, una más ilustrada/estilizada,
    y una tercera centrada en simplificar la escena manteniendo el mensaje
    principal. Explica brevemente qué cambiarías de cada elemento (sujeto,
    estilo, iluminación, encuadre) y por qué.
    ```

## Preguntas frecuentes

!!! question "¿Puedo usar la misma persona/foto real como referencia en varias herramientas?"

    Sí, siempre que tengas su consentimiento (o sea tu propia foto). Ten en cuenta que cada herramienta tiene su propia política sobre subir fotos de personas reales para generar variaciones; revísala antes si vas a usarlo con fotos de compañeros o alumnado.

!!! question "¿Por qué el texto dentro de la imagen sale mal escrito?"

    Los modelos de generación de imágenes tratan el texto como parte del dibujo, no como texto real, por lo que fallan con relativa frecuencia en palabras largas o poco comunes. Si necesitas texto exacto y legible, genera la imagen sin texto y añádelo después con una herramienta de edición o directamente en la diapositiva/documento.

!!! question "¿Qué resolución pedir para imágenes de una web MkDocs?"

    Para ilustraciones de apoyo dentro del contenido, con 1200-1600 píxeles de ancho suele sobrar; pedir "4K" o "8K" solo tiene sentido si vas a imprimir la imagen o usarla como fondo a pantalla completa, y genera archivos innecesariamente pesados para una web.

![Ejemplo de icono generado](https://cdn-icons-png.flaticon.com/512/910/910473.png)

## Plantilla rápida para copiar y adaptar

```text
Sujeto: [quién/qué aparece y qué está haciendo]
Tipo de imagen: [fotografía / ilustración / render 3D / pixel art...]
Estilo: [minimalista / realista / cyberpunk / acuarela...]
Encuadre y cámara: [plano general / primer plano / lente...]
Iluminación: [natural / estudio / neón / hora dorada...]
Fondo: [interior / exterior / liso / paisaje urbano...]
Detalle/render: [4K / hyper detailed / Octane render...]
Prompt negativo: [texto, marcas de agua, manos deformadas...]
```

Guarda esta plantilla junto a tus apuntes de IA y complétala campo a campo antes de pegarla en la herramienta que estés usando: ahorra iteraciones y deja un registro reutilizable de qué prompt generó cada imagen.

## Recursos

- [Nano Banana (Gemini)](https://nanobanana.im/){target="_blank"}
- [Midjourney](https://www.midjourney.com/){target="_blank"}
- [Leonardo AI](https://www.leonardo.ai/){target="_blank"}

# Guía práctica: cómo escribir prompts, plantillas reutilizables y trucos para ahorrar tokens

Esta guía sirve para cualquier IA conversacional (Claude, ChatGPT, Gemini, Copilot, etc.). Las plantillas y trucos son generales; solo cambia el nombre del modelo que elijas dentro de cada plataforma.

---

## 1. ¿Qué es un prompt y por qué importa cómo lo escribas?

Un **prompt** es la instrucción que le das al modelo. La IA no "adivina" lo que querés: responde literalmente a lo que le pediste. Un prompt mal estructurado obliga al modelo a rellenar huecos con suposiciones, lo que genera respuestas largas, genéricas o que hay que corregir varias veces (y cada corrección consume más tokens).

**Regla de oro:** cuanto más específico seas en *qué*, *cómo* y *en qué formato* querés la respuesta, menos vueltas (y menos tokens) necesitarás.

---

## 2. Anatomía de un buen prompt

Casi cualquier prompt eficiente tiene estas piezas, en este orden:

1. **Rol/contexto** — quién es el modelo y qué información de fondo necesita.
2. **Tarea** — qué tiene que hacer, en un verbo claro (resume, clasifica, traduce, genera...).
3. **Restricciones** — longitud, tono, idioma, qué evitar.
4. **Formato de salida** — lista, tabla, JSON, número de palabras, etc.
5. **Ejemplos (opcional)** — uno o dos ejemplos de entrada/salida (técnica *few-shot*).

```
[ROL/CONTEXTO]
Actúa como [rol] con experiencia en [tema].

[TAREA]
Quiero que [verbo + objetivo claro].

[RESTRICCIONES]
- Longitud: [máximo X palabras/líneas]
- Tono: [formal/informal/técnico]
- Idioma: [español/inglés]
- Evita: [relleno, disculpas, repetir el enunciado]

[FORMATO DE SALIDA]
Responde solo con [tabla / lista / JSON / texto plano], sin explicaciones adicionales.
```

---

## 3. Plantillas reutilizables

### 3.1 Plantilla básica (uso diario)

```
Actúa como [rol].
Tarea: [qué necesitas].
Contexto: [datos relevantes, máximo 3-4 líneas].
Formato de salida: [lista / tabla / párrafo corto].
Restricción: máximo [N] palabras.
```

### 3.2 Plantilla "few-shot" (cuando el formato es raro o muy específico)

Mostrarle 1-2 ejemplos es más barato en tokens que explicar reglas largas en prosa.

```
Convierte cada frase en una etiqueta de sentimiento (positivo/negativo/neutro).

Ejemplo 1:
Entrada: "El producto llegó roto y nadie respondió mi reclamo."
Salida: negativo

Ejemplo 2:
Entrada: "Todo perfecto, llegó antes de lo esperado."
Salida: positivo

Ahora clasifica esta:
Entrada: "El envío tardó pero el producto está bien."
Salida:
```

### 3.3 Plantilla de extracción de datos estructurados (JSON)

Útil para no recibir explicaciones extra que no necesitás.

```
Extrae los siguientes campos del texto y responde ÚNICAMENTE con un JSON válido, sin texto antes ni después:

{
  "nombre": "",
  "fecha": "",
  "monto": "",
  "categoria": ""
}

Texto:
"Factura del 12/06/2026 a nombre de Juan Pérez por 350€, concepto: hosting web."
```

### 3.4 Plantilla de resumen de documentos largos

```
Resume el siguiente texto en máximo 5 viñetas, cada una de una sola línea.
No repitas la introducción ni agregues opiniones.
Si hay cifras importantes, conservalas.

Texto:
[pega aquí solo el fragmento relevante, no el documento completo]
```

### 3.5 Plantilla para generar o revisar código

```
Actúa como desarrollador senior en [lenguaje].
Tarea: [crear función / corregir bug / refactorizar].
Código actual:
[pega solo la función o bloque relevante, no todo el archivo]

Reglas:
- No reescribas partes que no cambian.
- Devuelve solo el código modificado, con comentarios breves de qué cambiaste.
```

### 3.6 Plantilla "paso a paso" (solo cuando la tarea lo requiere)

Pedir razonamiento explícito consume más tokens, así que reservalo para tareas que realmente lo necesiten (matemáticas, lógica, depuración).

```
Resuelve este problema paso a paso, pero al final escribe la respuesta final
en una sola línea que empiece con "RESPUESTA:" para poder ubicarla rápido.

Problema: [enunciado]
```

---

## 4. Trucos para reducir el gasto de tokens

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

```
# Ejemplo de prompt "caro" (evitar)
Hola, quería pedirte por favor si podrías ayudarme a resumir este texto tan largo
que te voy a pegar a continuación, no hace falta que sea muy formal, gracias de antemano:
[texto pegado completo de 5 páginas]

# Versión "barata" equivalente
Resume en 5 viñetas, sin introducción:
[solo el párrafo o sección relevante]
```

---

## 5. Trucos para explotar al máximo los planes gratuitos

1. **Reservá el modelo "grande/pro" del plan gratuito para lo que realmente lo necesita.** Casi todas las plataformas dan acceso limitado al modelo top y acceso más amplio al modelo liviano (ej. Haiku, Flash, Instant). Usá el liviano para tareas rutinarias y guardá las consultas al modelo potente para lo complejo.
2. **Planificá el prompt antes de enviarlo.** En el plan gratuito, cada mensaje cuenta; escribir el prompt completo (rol + tarea + formato) de una sola vez evita "gastar" 3-4 mensajes corrigiendo lo que pediste mal.
3. **Dividí tareas grandes en partes chicas y bien delimitadas**, en lugar de pedir "hazme todo el proyecto" en un solo mensaje: las respuestas gigantes consumen más cuota y tienen más probabilidad de cortarse.
4. **Aprovechá los reinicios de cuota.** Los planes gratuitos suelen restablecer el límite de mensajes cada pocas horas o cada día: organizá las tareas que más importan para el momento justo después del reinicio.
5. **Limpiá o iniciá conversaciones nuevas seguido.** Un chat que arrastra mucho historial consume más "presupuesto" por turno que uno corto y enfocado.
6. **Combiná herramientas gratuitas según la tarea**, ya que cada plataforma reparte distinto el acceso a sus modelos: por ejemplo, usar una para borradores rápidos y otra para la versión final, repartiendo el consumo entre ambas.
7. **Guardá plantillas propias** (en notas, en un documento, o en la función de "instrucciones personalizadas" si la plataforma la ofrece) para no reescribir cada vez el mismo contexto.

```
# Plantilla de "presupuesto de mensajes" para plan gratuito
1. Definir el resultado final ANTES de escribir el prompt.
2. Escribir un único prompt completo (rol + tarea + formato + restricciones).
3. Revisar el resultado: si falta algo puntual, pedir solo ESE ajuste,
   no repetir toda la tarea de nuevo.
4. Si la tarea es larga, partirla en sub-tareas y resolver una por mensaje,
   en vez de pedir "todo junto" y arriesgarse a una respuesta cortada.
```

---

## 6. Checklist rápida antes de enviar un prompt

```
[ ] ¿Definí el rol o contexto necesario?
[ ] ¿La tarea está en un verbo claro (resume, clasifica, genera, traduce...)?
[ ] ¿Especifiqué el formato de salida (lista, tabla, JSON, párrafo corto)?
[ ] ¿Puse un límite de longitud?
[ ] ¿Pegué solo el fragmento de texto/código necesario, no todo el documento?
[ ] ¿Elegí el modelo más liviano que pueda cumplir la tarea?
```

---

## Referencia

Para técnicas más avanzadas de prompting (ejemplos positivos/negativos, razonamiento paso a paso, etiquetas XML para estructurar instrucciones), Anthropic publica una guía oficial:
https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview

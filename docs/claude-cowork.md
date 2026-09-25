# Claude trabajando sobre carpetas locales (antes "Cowork")

> **Nota:** las funciones que antes se conocían como *Claude Cowork* ahora forman parte de Claude directamente. Este manual explica cómo darle acceso a una carpeta de tu equipo para que Claude trabaje sobre ella (leer, crear, modificar archivos y ejecutar código).

---

## 1. Qué es y cómo funciona

- Claude trabaja en un **entorno aislado y temporal en la nube** que se crea para cada sesión y se elimina al terminarla.
- Para llegar a los archivos de tu ordenador usa la **app de escritorio de Claude** como puente, y **solo** en las carpetas que tú hayas conectado.
- Puede **leer, crear y modificar** archivos dentro de esas carpetas y **ejecutar código** sobre ellos.
- **Protección ante borrados:** antes de eliminar cualquier archivo, Claude necesita tu permiso explícito (aparece un aviso y debes pulsar *Permitir*).
- La sesión sigue funcionando aunque cierres la app, pero **si la tarea usa archivos locales, la app de escritorio debe estar abierta** y el equipo encendido y con conexión.

---

## 2. Requisitos previos

| Requisito | Detalle |
|-----------|---------|
| App de escritorio | Claude Desktop instalada (Windows o macOS) desde `claude.ai/download` |
| Cuenta | Sesión iniciada con tu cuenta de Claude |
| Carpeta de trabajo | Una carpeta dedicada, preferiblemente una **copia** de tus materiales o un repositorio Git |
| Conexión | El equipo encendido, en línea y con la app abierta mientras Claude trabaje en local |

---

## 3. Paso a paso: conectar una carpeta

1. **Prepara la carpeta.** Crea una carpeta de trabajo, por ejemplo `~/Docencia/apuntes-mkdocs`. Si es un proyecto MkDocs, asegúrate de que está bajo Git (`git init` o clonado de GitHub) para poder deshacer cambios.
2. **Abre la app de escritorio de Claude** e inicia una conversación nueva.
3. **Conecta la carpeta** desde las opciones de la conversación (selector de carpetas/espacio de trabajo). Selecciona solo la carpeta que Claude necesita, no tu carpeta personal completa.
4. **Concede los permisos del sistema** si el sistema operativo los pide (en macOS: *Ajustes del sistema → Privacidad y seguridad → Archivos y carpetas*).
5. **Comprueba el acceso** con un prompt sencillo:
   ```text
   Lista el contenido de la carpeta conectada y dime qué tipo de proyecto es.
   ```
6. **Fija tus reglas de trabajo** al inicio de la conversación (ver apartado 5).
7. **Revisa los cambios** al terminar: `git status` y `git diff` son tus aliados.

> 💡 También puedes abrir la misma conversación desde la web o el móvil para seguir el progreso; mientras la app de escritorio esté abierta, Claude seguirá llegando a la carpeta conectada.

---

## 4. Permisos: qué controlas tú

| Acción | Comportamiento por defecto | Recomendación |
|--------|---------------------------|---------------|
| Leer archivos | Permitido en carpetas conectadas | Conecta solo lo necesario |
| Crear / modificar | Permitido en carpetas conectadas | Trabaja con Git para poder revertir |
| Ejecutar código | Se ejecuta en el entorno aislado sobre tus archivos | Revisa scripts antes de ejecutarlos sobre datos reales |
| Eliminar archivos | **Requiere tu permiso explícito** (aviso "Permitir") | Añade además una regla propia (ver abajo) |
| Acceso a red | Sigue la configuración de salida de red | No amplíes permisos sin necesidad |
| Conectores / MCP | Solo los que tú conectes | Evalúa la confianza de cada uno |

---

## 5. Regla personalizada de seguridad para borrados

Además del aviso de la app, puedes pedir una confirmación extra al principio de cada conversación:

```text
Tienes permiso de lectura, escritura y ejecución en la carpeta conectada.
Para ELIMINAR cualquier archivo o carpeta debes:
1. Decirme exactamente qué vas a borrar (ruta completa).
2. Esperar a que yo escriba DELETE en mayúsculas.
Si no escribo DELETE, no borres nada; en su lugar, mueve los archivos a una
subcarpeta _to_delete/ y avísame.
```

> Para que la regla se aplique siempre, guárdala en tus **preferencias personales** (Ajustes → Perfil) o en un archivo de instrucciones dentro del proyecto (por ejemplo `CLAUDE.md`).

---

## 6. Ejemplos de prompts para trabajar con una carpeta

### Documentación y MkDocs

```text
Revisa todos los .md de la carpeta docs/ y genera el bloque nav: de mkdocs.yml
ordenado por unidades. No modifiques los archivos, solo mkdocs.yml.
```

```text
Convierte el archivo Tema3-Redes.docx a Markdown limpio y guárdalo en
docs/redes/tema3.md. Extrae las imágenes a docs/redes/img/ y enlázalas.
```

```text
Busca enlaces rotos e imágenes que no existan en toda la carpeta docs/
y dame un informe en informe-enlaces.md con archivo, línea y enlace.
```

### Materiales didácticos

```text
A partir de docs/linux/permisos.md crea una práctica con 10 apartados
numerados y guárdala como practicas/SP2.3-permisos.md.
```

```text
Genera un banco de 20 preguntas tipo test sobre el tema de virtualización
(docs/virtualizacion/) con la respuesta correcta y una breve explicación.
```

### Administración de sistemas y automatización

```text
Revisa los scripts de la carpeta scripts/ y añade comentarios, control de
errores (set -euo pipefail) y un bloque de ayuda con -h en cada uno.
```

```text
Crea un docker-compose.yml en lab-wordpress/ con WordPress, MariaDB y
volúmenes persistentes, más un README.md explicando cómo levantarlo.
```

```text
Analiza los logs de logs/auth.log y resume los intentos de acceso fallidos
por IP en una tabla ordenada de mayor a menor.
```

### Organización

```text
Renombra todas las imágenes de docs/img/ a minúsculas y sin espacios,
y actualiza las referencias en los .md. Antes de hacerlo, muéstrame
la lista de cambios propuestos.
```

> ✅ **Buenas prácticas en los prompts:** indica la carpeta exacta, el formato de salida, qué **no** debe tocar y pide que te enseñe el plan antes de cambios masivos.

---

## 7. Ventajas y desventajas

| Ventajas | Desventajas |
|----------|-------------|
| Trabaja directamente sobre tus archivos: no hace falta subir ni descargar | Los archivos que abre se procesan en los servidores de Anthropic, no se quedan solo en tu equipo |
| Acceso limitado a las carpetas que tú conectas | Si conectas una carpeta demasiado amplia, expones más datos de los necesarios |
| Ejecuta código en un entorno aislado y temporal | Necesita la app de escritorio abierta y el equipo encendido para tocar archivos locales |
| Borrados protegidos con confirmación explícita | Puede modificar muchos archivos en poco tiempo: un prompt ambiguo causa cambios masivos |
| Ideal para tareas repetitivas: conversiones, renombrados, informes, índices | Conviene revisar siempre el resultado; puede equivocarse |
| Puedes seguir y corregir la tarea desde web o móvil | No es recomendable para datos sensibles (datos de alumnado, notas, datos personales) sin valorar la normativa (RGPD) |
| Combina archivos locales con web y conectores (Drive, Gmail…) | Más conectores = más superficie de riesgo (inyección de instrucciones desde contenido externo) |
| Muy útil para mantener documentación MkDocs y materiales de clase | Depende de conexión a internet y de la disponibilidad del servicio |

---

## 8. Recomendaciones de seguridad

- Usa **Git** en la carpeta conectada y haz *commit* antes de cada sesión.
- Conecta **carpetas específicas**, nunca tu carpeta de usuario completa.
- **No conectes** carpetas con datos personales del alumnado.
- Pide siempre **un plan antes de cambios masivos**.
- Si Claude se comporta de forma extraña (temas no relacionados, accesos inesperados), **detén la tarea** y repórtalo.

---

## Fuentes

- [Get started with Claude Cowork – Claude Help Center](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork)
- [Use Claude Cowork safely – Claude Help Center](https://support.claude.com/en/articles/13364135-use-claude-cowork-safely)
- [Desktop and filesystem access – Claude Docs](https://claude.com/docs/third-party/claude-desktop/local-access)

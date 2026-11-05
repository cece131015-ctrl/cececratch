# ◆ CeceCratch

**El Scratch del futuro**: los bloques de siempre, pero con escenario **2D y 3D**, carga de
**imágenes, modelos `.obj`, sonidos, vídeos y `.zip`**, y **4 bloques especiales de IA**.

Todo vive en un único archivo: [`cececratch.html`](cececratch.html).
Sin instalación, sin dependencias, sin internet: ábrelo con doble clic en cualquier navegador.

## Los 4 bloques especiales ✦

| Bloque | Qué hace |
|---|---|
| `✦ compañía de IA [___] modelo [___]` | Escribes la compañía que creó la IA (Google AI Studio, Anthropic, OpenAI, Mistral, xAI, DeepSeek, Meta, Groq, Local…). El modelo es opcional: `auto` elige uno por ti. |
| `✦ clave API de la compañía [___]` | Escribes la clave de esa compañía. **Nunca se guarda** en el archivo del proyecto. |
| `✦ modelo 3D [___]` | Escribes el nombre del `.obj` que has cargado y el objeto pasa a usarlo (activa el modo 3D). |
| `✦ chat por [texto / micrófono / altavoz / micrófono y altavoz…] decir [___]` | Eliges cómo le hablas. La respuesta queda en la variable `respuestaIA`, sale por el bocadillo del objeto y por el panel *Chat IA*. |

Sin clave API el bloque `chat` sigue funcionando con un cerebro local de demostración.

## 🔑 Claves API y Google AI Studio

1. Consigue una clave gratis en <https://aistudio.google.com/apikey>.
2. Pulsa **🔑 Claves API** (cabecera), elige *Google AI Studio*, pega la clave y pulsa **🧪 Probar clave**:
   comprueba que es válida y te muestra los modelos que tu clave puede usar.
3. Pulsa **💾 Guardar y usar**. Ya puedes hablar con Gemini desde **✦ Chat IA** o con el bloque `✦ chat`.

Detalles:

- Modelo `auto` → `gemini-flash-latest`, el alias oficial de Google que apunta al Flash más reciente
  (así no se rompe cuando Google retira modelos antiguos). Puedes escribir cualquier otro.
- La clave viaja en la cabecera `x-goog-api-key`, nunca en la URL.
- Las claves de otras compañías (Anthropic, OpenAI, Mistral, xAI, DeepSeek, Groq) se gestionan igual.
- **Dónde se guarda la clave**: por defecto solo en memoria (se pierde al cerrar la pestaña). Si marcas
  *Recordar en este navegador* se guarda en `localStorage` de ese navegador, y solo se envía a la compañía elegida.
  **Nunca** entra en el archivo del proyecto (`.json`) ni en el autoguardado del programa.
- Prioridad: la clave de un bloque `✦ clave API` del programa > la guardada en 🔑 Claves > cerebro local.

## Qué trae

- **12 categorías de bloques**: Eventos, Movimiento, Apariencia, Sonido, Medios, Control,
  Sensores, Operadores, Variables, 3D, Lápiz e IA ✦.
- **Escenario 2D** (canvas) y **escenario 3D** (motor WebGL propio: cubos, esferas, planos,
  modelos `.obj`, texturas, luz, rejilla y cámara orbitable con el ratón).
- **Archivos**: imágenes → disfraces y fondos · `.obj` → modelos 3D · sonidos · vídeos ·
  `.zip` que se descomprime en el propio navegador y reparte cada archivo en su sitio.
- **Fórmulas** en los campos numéricos y de condición: `x + 10`, `azar(1,6)`,
  `tecla("espacio")`, `tocando("Objeto2")`, `distancia("Objeto2")`, `y` / `o` / `no`…
  En los campos de texto, `${variable}` inserta su valor.
- Clones, mensajes, lápiz, variables con monitor en pantalla, preguntar y esperar (en cola).
- **Guardar / abrir** el proyecto completo (bloques + archivos) en un `.json`,
  y autoguardado del programa en el navegador.
- Voz: micrófono (reconocimiento) y altavoz (síntesis) para hablar con la IA.

## Atajos

- **🏁 Ejecutar** lanza todos los sombreros «al hacer clic en 🏁»; **Esc** o **⏹ Parar** detiene todo.
- **Clic** sobre una pila de bloques → la ejecuta. **Clic derecho** → duplicar / borrar / ejecutar.
- Arrastra un bloque **de vuelta a la paleta** para borrarlo.
- En modo 3D: arrastra el escenario para orbitar la cámara y usa la rueda para acercarte.

## Nota sobre la IA

Las llamadas salen directamente desde el navegador a la API de la compañía elegida.
Si un proveedor bloquea CORS desde el navegador, usa un proxy propio (puedes escribir su URL en el campo de la
compañía) o deja la clave vacía para trabajar con el cerebro local.

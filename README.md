# DWC-1.2

Actividad 1: Laboratorio de Auditoría y Rendimiento Web
Formato: Individual o Parejas (Informe Técnico + Capturas de pantalla). El informe puede ser una presentación de cualquier tipo, o un archivo markdown. Tanto las capturas como el el informe tienen que estar en su repo.

Criterios que evalúa: CE a (Modelos cliente/servidor), CE b (Capacidades y mecanismos del navegador), CE d (Particularidades de scripts vs tradicional) y CE f (Herramientas de programación).

Enunciado:
Elige una web SPA (Single-Page Application) moderna altamente dinámica (ej. YouTube, Spotify Web, o Twitter/X) y realiza una auditoría técnica utilizando exclusivamente las DevTools de tu navegador de cabecera.

Tareas a realizar:
Auditoría de Red (Network): Recarga la página y filtra por la pestaña Doc (HTML) y la pestaña JS. Identifica el tamaño del HTML inicial que envía el servidor frente al tamaño total de los scripts de JavaScript que se descargan. Explica razonadamente si la página utiliza SSR (Server-Side Rendering) o CSR (Client-Side Rendering) basándote en lo que ves en la respuesta del primer HTML (CE a).
Destripando el Motor (Performance): Realiza una grabación de rendimiento de 5 segundos mientras interactúas con la web. Localiza en la línea de tiempo las fases de Parsing HTML, Evaluate Script y Compile Code (JIT). Describe qué está haciendo el motor JS (como V8 o JavaScriptCore) en ese momento de la captura (CE b, CE f).
El Sandbox en acción (Consola): Abre la pestaña Console. Intenta ejecutar una línea de código sencilla como const a = "eoo"; console.log(a);. Luego intenta otro código "maligno", como que intente leer un archivo de tu disco duro (ej. usando FileReader de forma automática sin un input del usuario). Captura el error de seguridad, documenta qué restricción del Sandbox del navegador ha saltado y explica por qué es vital para la seguridad del usuario (CE b).
const r= new FileReader();
r.readAsText("C:"Windows/system.ini");
r.onLoad = function(){ console.log(r.result);}﻿﻿
Análisis de Bloqueo: Busca en la red un script que pese más de 1MB en esa web. Explica qué ocurriría con la experiencia de usuario si ese script se ejecutase de manera síncrona y tradicional en lugar de usar la naturaleza asíncrona y orientada a eventos propia del scripting web (CE d).


Actividad 2: El Gran Duelo de la Integración (defer vs async vs modules)
Formato: Individual (Laboratorio de código y despliegue).

Criterios que evalúa: CE c (Lenguajes del cliente), CE e (Mecanismos de integración con HTML) y CE f (Herramientas y entornos de desarrollo).

Enunciado:
En esta práctica vais a comprobar de forma empírica cómo afecta la forma de integrar JavaScript en el HTML al renderizado de la página. Para ello, prepararás un entorno de pruebas controlado."

Tareas a realizar:
Configuración del Entorno: Crea un proyecto con un archivo index.html que contenga una estructura básica y un elemento h1 vacío (--h1 id="titulo">Hola</h1>--).
Creación de Scripts "Pesados": Crea tres archivos JavaScript independientes: script1.js, script2.js y script3.js. En cada uno de ellos, escribe código que intente modificar el texto del h1 (document.getElementById('titulo').innerText = 'Cambiado por X'). Para simular que son scripts pesados, añade un bucle for que cuente hasta 50 millones antes de modificar el DOM.
El Experimento de Integración: Debes probar 4 escenarios de integración diferentes en el HTML (CE e):
Escenario A: <script> tradicional en la cabecera (<head>).
Escenario B: <script> tradicional justo antes de cerrar el </body>.
Escenario C: <script async> en el <head>.
Escenario D: <script defer> en el <head>.
Escenario E: <script type="module"> en el <head>.
Informe de Resultados: Para cada escenario, debéis abrir las DevTools (pestaña Performance/Network), medir el tiempo que tarda la página en pintar el título en blanco frente a cuándo se ejecuta el script, y documentar en qué casos el script falla porque "el DOM aún no se ha construido" (CE e, CE f).

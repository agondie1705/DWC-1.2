# DWC-1.2

Actividad 1 – Auditoría de una SPA

Elegir una web moderna como YouTube, Spotify o X.
Usar DevTools para analizar:
Network: comparar tamaño del HTML inicial y los JS descargados y determinar SSR o CSR.
Performance: grabar 5 segundos y localizar Parsing HTML, Evaluate Script y Compile Code (JIT).
Console: ejecutar código normal y probar las restricciones de seguridad del navegador con FileReader.
Scripts >1 MB: explicar qué pasaría si se ejecutaran de forma síncrona.
Entregar informe + capturas en el repositorio.

Actividad 2 – defer vs async vs modules

Crear un proyecto HTML con un <h1>.
Crear 3 JS pesados con un bucle de 50 millones y que cambien el <h1>.
Probar 5 formas de incluirlos:
<script> en <head>
<script> antes de </body>
<script async>
<script defer>
<script type="module">
Con DevTools, medir cuándo se pinta el título y cuándo se ejecuta cada script.
Explicar cuándo el DOM todavía no está construido y qué diferencias hay entre async, defer y module.

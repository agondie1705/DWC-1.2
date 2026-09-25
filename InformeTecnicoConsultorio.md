Adrian Gonzalez Diez
Christian Said Jimenez Mahecha

Auditoría de Red (Network): 

<img width="929" height="387" alt="image" src="https://github.com/user-attachments/assets/371c692f-f964-4999-814e-e601ed4588e4" />

<img width="1805" height="742" alt="image" src="https://github.com/user-attachments/assets/07301fc8-1fc6-4d5b-b463-6107dc20b347" />

En la pestaña Network: Doc, se observa que el archivo principal (https://www.youtube.com/) tiene tipo documento y tamaño aproximado de 0.18 MB, mientras que los scripts (.js) descargados superan los 0.3 MB cada uno.
Esto indica que el HTML inicial es ligero y sirve principalmente como contenedor para cargar dinámicamente los recursos JavaScript. 

SSR (Server‑Side Rendering): el servidor envía HTML ya renderizado con contenido visible sin depender de JavaScript.
CSR (Client‑Side Rendering): el servidor envía un HTML mínimo y el contenido se genera en el navegador mediante scripts.
 El HTML inicial contiene solo estructura básica y referencias a scripts, sin contenido renderizado.
Conclusión: YouTube utiliza CSR, ya que la mayor parte del contenido (videos, miniaturas, interfaz) se carga mediante JavaScript después de recibir el documento base
El primer HTML actúa como “shell” o plantilla vacía.

Los scripts descargados (mv3/loader_base_module.local.js, entre otros) gestionan la renderización del contenido y las peticiones posteriores a la API.

El tamaño total de los scripts es varias veces mayor que el del HTML, lo que confirma una arquitectura SPA (Single‑Page Application) con renderizado en cliente.

Destripando el Motor (Performance): 
<img width="940" height="719" alt="image" src="https://github.com/user-attachments/assets/6706d4d1-0d4d-44b6-8a20-2536f78cda18" />

En la parte superior del timeline aparece una barra continua de color amarillo y verde, lo que indica:

-Evaluación de JavaScript constante.

-Renderizado y repintado del DOM.

-Gestión de eventos de usuario.

Esto confirma que YouTube funciona como una SPA (Single‑Page Application) donde el navegador lleva la mayor parte del trabajo.

En la captura se ven varios picos pronunciados en el gráfico de CPU.
Estos picos corresponden a: Parsing de scripts grandes, compilación JIT (Just‑In‑Time), ejecución de funciones de renderizado. YouTube descarga módulos JS muy pesados (como vimos en el punto 1), y el motor V8 los optimiza en tiempo real.
Cada interacción del usuario (scroll, hover, abrir menú) dispara nuevas tareas del motor.

En la parte inferior del timeline aparecen bloques etiquetados como: Evaluate Script, compile Code, Function Call, Recalculate Style, Layout, Paint.

Esto demuestra que el motor está: interpretando y compilando JavaScript, calculando estilos dinámicos, reorganizando el layout, repintando elementos visuales. Todo esto ocurre de forma continua porque YouTube actualiza la interfaz en tiempo real.


El Sandbox en acción (Consola): 
Una vez pegamos el código proporcionado por el profesor:
const a = "eoo"; console.log(a); 
Nos dice lo siguiente
<img width="496" height="56" alt="image" src="https://github.com/user-attachments/assets/7a595510-22ce-4457-9b40-08a5fc8a3347" />

Cuando le ponemos un comando con file reader nos vuelve a decir lo mismo esto esta puesto para que no puedan ejecutar comandos maliciosos ya sea para vulnerar tu seguridad o la de la página desde tu cuenta queriendo o sin querer

Análisis de Bloqueo :
En este apartado se nos solicita que busquemos en la pagina web un archivo que pese mas de 1 MB pero en este caso no hay archivo que pese mas de 1 MB:
<img width="732" height="1033" alt="image" src="https://github.com/user-attachments/assets/d63957b0-1aee-4f0f-ad21-2484225d215e" />

A continuación explico que pasaria si el archivo hipotético de 1 MB se ejecutase de manera síncrona con la página principal el resultado sería:

Retraso de la página web tarda más en cargar 
Puede dar fallo algunos elementos de la página

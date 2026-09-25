Aquí vamos a explicar como funciona cada script


Escenario A: <script> tradicional en la cabecera (<head>).
<img width="1814" height="720" alt="image" src="https://github.com/user-attachments/assets/ed6f29ff-f5ca-44e3-98be-13a05951c357" />


En la imagen se logra visualizar que no ha cargado los scripts correctamente, no se ha actualizado el texto de titulo, también se ve como se tarda 5seg en cargar una página web, y por último vemos los errores, que son los que no permite cambiar el texto a los scripts.js a la incapacidad de crear el modificador en el DOM.






Escenario B: <script> tradicional justo antes de cerrar el </body>.
<img width="1815" height="713" alt="image" src="https://github.com/user-attachments/assets/ff6f8db7-6948-42c3-8973-c972898de541" />

En el script logramos ver que está funcionado mejor. En este escenario hemos puesto los Script`s al final del body del innertext sin errores ni tiempo retardado.










Escenario C: <script async> en el <head>.

<img width="1832" height="713" alt="image" src="https://github.com/user-attachments/assets/5f407099-c6b5-466d-ad33-50c1996ba68d" />

Observamos en la imagen que ha funcionado de nuevo tardando muy poco y funciona correctamente, pero esta vez lo ejecuta cuando lo termina de descargar.






Escenario D: <script defer> en el <head>.

<img width="2045" height="702" alt="image" src="https://github.com/user-attachments/assets/9a6f8e87-2f9c-4f41-bbfb-306efe7c68bb" />

En este escenario vemos como funciona perfectamente, gracias al defer que analiza el archivo mientras descarga el HTML.








Escenario E: <script type="module"> en el <head>.

<img width="1849" height="709" alt="image" src="https://github.com/user-attachments/assets/6872241d-a66c-4438-a36d-03b5ffd38863" />

Se logra visualizar como funciona el Type module que se ha agregado al innertext. A su vez se ve que tarda más de lo normal como respuesta a que analiza el HTML, mientras descarga el javascript. Despues de descargarse el módulo se puede usar acciones como import y export.


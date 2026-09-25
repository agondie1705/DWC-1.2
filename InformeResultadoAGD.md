Aquí vamos a explicar como funciona cada script


Escenario A: <script> tradicional en la cabecera (<head>).
<img width="1814" height="720" alt="image" src="https://github.com/user-attachments/assets/ed6f29ff-f5ca-44e3-98be-13a05951c357" />


En esta imagen podemos ver que no ha cargado los scripts correctamente ya que no se ha actualizado el texto de titulo tambien se ve como h atrasado 5 s que para cargar una página web es mucho y por último los errores son de que no nos permite cambiar el texto ya que no se ha creado la frase todavía en el DOM






Escenario B: <script> tradicional justo antes de cerrar el </body>.
<img width="1815" height="713" alt="image" src="https://github.com/user-attachments/assets/ff6f8db7-6948-42c3-8973-c972898de541" />

en esta imagen podemos ver que hay funcionado mejor ya que estaba al final del body el innertext sin errores ni tiempo retardado










Escenario C: <script async> en el <head>.

<img width="1832" height="713" alt="image" src="https://github.com/user-attachments/assets/5f407099-c6b5-466d-ad33-50c1996ba68d" />

Aquí podemos ver que ha funcionado de nuevo tardando muy poco y funciona correctamente pero lo ejecuta cuando lo termina de descargar






Escenario D: <script defer> en el <head>.

<img width="2045" height="702" alt="image" src="https://github.com/user-attachments/assets/9a6f8e87-2f9c-4f41-bbfb-306efe7c68bb" />

En esta imagen también vemos como funciona perfectamente gracias al defer que analiza el archivo mientras descarga el HTML








Escenario E: <script type="module"> en el <head>.

<img width="1849" height="709" alt="image" src="https://github.com/user-attachments/assets/6872241d-a66c-4438-a36d-03b5ffd38863" />

Esta imagen vemos como funciona el Type module que le hemos puesto al innertext es verdad que tarda más de lo normal ya que analiza el html mientras descarga el javascript despues de descargarse el módulo se puede usar cosas como import y export



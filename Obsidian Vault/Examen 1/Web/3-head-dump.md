
# Reto 
### head-dump
## Descripcion
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:63333/).
## Solucion
```
**1. Encuentra la documentación** El texto menciona específicamente: _"an article about API Documentation"_. Entra a la página principal del blog de picoCTF News y busca ese artículo. A veces, los desarrolladores (tanto en CTFs como en la vida real) dejan documentados _endpoints_ de prueba o administración que no deberían estar al alcance del público.

**2. Identifica el _endpoint_** Lee el artículo con atención. Seguramente mencionará una ruta o URL de la API (puede ser algo parecido a `/api/dump`, `/heapdump`, `/memory`, `/actuator/heapdump`, etc.). Copia esa ruta.

**3. Ejecuta la descarga** Ve a la barra de direcciones de tu navegador y agrega ese _endpoint_ al final de la URL del sitio principal. Por ejemplo: `http://url-del-reto.com/ruta-que-encontraste`. Al presionar `Enter`, el servidor debería procesar la petición y descargar un archivo en tu computadora. Este archivo es el volcado de memoria (memory dump).
picoCTF{Pat!3nt_15_Th3_K3y_dc0756a3}
```




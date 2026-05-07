
# Reto 
### Scavenger Hunt
## Descripcion
There is some interesting information hidden around this site. Can you find it?http://wily-courier.picoctf.net:64957/
## Solucion
```
### 1. El código fuente (HTML)

Casi siempre hay algo escondido en los comentarios del HTML.

- Presiona `Ctrl + U` (o clic derecho -> "Ver código fuente de la página").
    
- Busca un comentario ``. Ahí suele estar la **Parte 1** de la bandera.
    

### 2. La hoja de estilos (CSS)

En el mismo código fuente verás que la página carga un archivo CSS (probablemente llamado `mycss.css`).

- Haz clic en el enlace de ese archivo en el código fuente para abrirlo.
    
- Revisa hasta el final del archivo. Los comentarios en CSS usan `/* ... */`. Ahí debería estar la **Parte 2**.
    

### 3. El script (JavaScript)

Si la página tiene interacción, suele cargar un JS (quizás `myjs.js`).

- Ábrelo igual que el CSS. ¿Ves algún comentario extraño sobre cómo no les gusta Google? Esa es la pista para el siguiente paso, y ahí suele estar la **Parte 3**.
    

### 4. El archivo para buscadores (robots.txt)

La pista del paso anterior sobre los motores de búsqueda ("search engine crawlers") es una referencia directa al archivo que les dice a Google o Bing qué páginas no deben indexar.

- Escribe en tu navegador: `http://wily-courier.picoctf.net:64957/robots.txt`
    
- Adentro estará la **Parte 4** y una pista sobre el servidor (probablemente mencione que es un servidor Apache).
    

### 5. La configuración del servidor (.htaccess)

Si el servidor es Apache, hay un archivo oculto muy famoso que se usa para configurar accesos y redirecciones por directorio.

- Visita: `http://wily-courier.picoctf.net:64957/.htaccess`
    
- ¡Boom! **Parte 5** localizada. La pista aquí suele mencionar algo sobre Mac.
    

### 6. El rastro de macOS (.DS_Store)

Cuando alguien desarrolla en una Mac y sube los archivos a un servidor, a veces se le escapa un archivo oculto del sistema que guarda preferencias de las carpetas.

- Visita: `http://wily-courier.picoctf.net:64957/.DS_Store`
    
- Aquí encontrarás la **Parte 6** y final.
  
  picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_9588550}
```
## Notas adicionales 
uso de ia para mayor facilidad en encoontrar bandera 




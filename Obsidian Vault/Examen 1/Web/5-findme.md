
# Reto 
### findme
## Descripcion
Help us test the form by submiting the username as `test` and password as `test!`The website running [here](http://saturn.picoctf.net:61646/).
## Solucion
```
**1. Prepara tu trampa (La pestaña Network)**

- Abre la página del reto.
    
- Antes de poner cualquier dato, abre tus Herramientas de Desarrollador (`F12` o `Ctrl + Shift + I`).
    
- Ve a la pestaña **Network** (Red).
    
- **¡Paso crucial!** Busca y marca una casilla que dice **Preserve log** (Conservar registro). Si no haces esto, el navegador limpiará la lista de peticiones en cuanto cambies de página y perderemos el rastro.
    

**2. Ejecuta el inicio de sesión**

- Ahora sí, en la página web ingresa el usuario `test` y la contraseña `test`, y haz clic en entrar.
    

**3. Analiza el rastro de migas de pan**

- Vuelve a tu pestaña **Network**. Verás que aparecieron varias líneas (peticiones).
    
- Busca las primeras peticiones que tengan un **Status 302** (Redirect o Found). Deberían ser dos peticiones seguidas justo después del login.
    
- Haz clic en la primera petición 302 y revisa sus detalles. Si miras la **URL de solicitud** (Request URL) o la cabecera **Location** en los _Headers_, notarás que te está mandando a una dirección que termina con un parámetro raro, algo como `?id=cGlj...`.
    
- Revisa la segunda petición 302 y verás que hace lo mismo, pero con un texto diferente.
    

**4. Une las piezas** Ese texto extraño es nuevamente nuestro viejo amigo **Base64**. Los creadores del reto partieron la bandera a la mitad: la primera redirección tiene la primera parte, y la segunda redirección tiene el final.
picoCTF{proxies_all_the_way_3d9e3697}
```
## Notas adicionales 

## Referencias



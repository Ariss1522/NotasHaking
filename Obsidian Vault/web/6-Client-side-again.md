
# Reto 
### Client-side-again
## Descripcion
Can you break into this super secure portal?http://fickle-tempest.picoctf.net:63207
## Solucion
1. Inspeccionar el código fuente de la página (`Ctrl + U` o clic derecho -> Ver código fuente).
2. Localizar las etiquetas `<script>` en el HTML. El código JavaScript estaba **ofuscado** (nombres de variables ilegibles y sin formato) para ocultar la lógica de validación. 
3. Identificar un *Array* (arreglo) en la primera línea del script que contenía cadenas de texto estáticas expuestas: `var _0x5a46=['daf93}','_again_4','this','Password\x20Verified','...','picoCTF{','not_this'];` 
4. Extraer los fragmentos relevantes ignorando el código espagueti y el texto de validación genérico. 
5. Ensamblar la bandera usando la lógica del formato estándar de picoCTF: `picoCTF{` + `not_this` + `_again_4` + `daf93}`.
6. **Bandera final:** `picoCTF{not_this_again_4daf93}`
## Notas adicionales 
**Ofuscación vs Encriptación:** El autor intentó asegurar la contraseña ofuscando el código JavaScript. La ofuscación solo hace que el código sea difícil de leer para un humano, pero no cifra los datos subyacentes. 
**Regla de oro web:** Nunca se deben realizar validaciones de autenticación o almacenar credenciales en el lado del cliente (*frontend*). Siempre debe manejarse en el *backend*.
## Referencias
Concepto de Ofuscación de Código en JavaScript.


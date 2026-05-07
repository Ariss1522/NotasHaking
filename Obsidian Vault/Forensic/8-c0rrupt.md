
# Reto 
### c0rrupt
## Descripcion
We found this [file](https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery). Recover the flag.
## Solucion
```

Solucion

El reto se resuelve reparando manualmente la estructura hexadecimal de un archivo PNG corrupto, utilizando un editor hexadecimal y diagnosticando los errores estructurales de forma iterativa con la herramienta pngcheck.

Pasos de resolución:

1. Diagnóstico inicial y Magic Bytes:
    
    Se utilizó la herramienta pngcheck para analizar el archivo "mystery", el cual arrojó que no era reconocido como una imagen. Abriendo el archivo con hexeditor, se corrigieron los primeros 8 bytes (la firma o Magic Bytes del PNG) reemplazándolos por los valores universales correctos: 89 50 4E 47 0D 0A 1A 0A.
    
2. Reparación del CRC del bloque pHYs:
    
    Al ejecutar pngcheck nuevamente, el programa detectó un error de validación (CRC error) en el chunk pHYs. Se localizó este bloque en el editor hexadecimal y se sobrescribió el sello de verificación dañado por el sello matemático que la misma herramienta calculó como correcto (38 D8 2C 82).
    
3. Corrección de la longitud de bloque:
    
    El siguiente diagnóstico indicó un tamaño de bloque inválido por ser excesivamente grande. Inmediatamente después del bloque pHYs, se localizó el indicador de tamaño que había sido corrompido con el valor "AA AA" y se reemplazó por "00 00", restaurando el tamaño lógico de los datos.
    
4. Restauración del bloque IDAT y cabecera Zlib:
    
    Se detectó que el nombre del bloque principal de la imagen había sido modificado. Se sobrescribieron los 4 bytes del nombre falso con el identificador oficial IDAT en hexadecimal (49 44 41 54). Asimismo, se verificó y restauró el primer byte del bloque de datos subsiguiente asegurando que tuviera el valor 78, el cual es vital para indicar que la imagen usa compresión Zlib.
    
5. Obtención de la flag:
    
    Una vez realizadas todas las correcciones, pngcheck arrojó un estatus "OK", validando la estructura del archivo. Se renombró el archivo recuperado a flag.png y, al abrirlo con un visor de imágenes, se logró visualizar la flag correctamente.
picoCTF{c0rrupt10n_1847995}
```
## Notas adicionales 

## Referencias



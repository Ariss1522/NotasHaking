# Reto 
## Strings it
## Descripcion
Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/53c039e64942b1c4334781c4987ba7e2ba54f0b2bf39f52c65f3a65dfcbf4194/strings) without running it?
## Solucion
```
LiszAc-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_47948C73} 
```
## Notas adicionales 
Un ejecutable "ELF 64-bit LSB PIE" es un ==archivo binario estándar en Linux/Unix de 64 bits con formato [Executable and Linkable Format](https://www.google.com/search?client=opera-gx&q=Executable+and+Linkable+Format&sourceid=opera&ie=UTF-8&oe=UTF-8&mstk=AUtExfDeBA1vwx7goI-kKEtMOmvSYrr1ltzMOwZyjsSWlNGIYJdD6T_0u36jDjKrbO3Lst01r-oiyM8hfAaOf7xr62xDCG26x9C3EO0LRjSCJPwhjtsS3OqNrfuyx_A6i1qQa8pJv39F8tl8yx7UqpS71-pF3ZoUMnHklCQbE-NtsLOD09w&csui=3&ved=2ahUKEwiy34ajztGSAxWile4BHfrLDdUQgK4QegQIARAC)==. "LSB" indica Little-Endian (formato de byte) y "PIE" (Position Independent Executable) significa que el código es independiente de su ubicación en la memoria, mejorando la seguridad al cargar el binario en direcciones aleatorias.
## Referencias

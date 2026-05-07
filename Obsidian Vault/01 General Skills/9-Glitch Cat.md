## Reto 
## Glitch Cat
## Descripcion
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 52688`
## Solucion
```
picoctf@webshell:~$ nc saturn.picoctf.net 52688
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'

picoctf@webshell:~$ ^C
picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
'picoCTF{gl17ch_m3_n07_a4392d2e}'
```

## Notas adicionales 
chr(convierte un numero en un caracter)
## Referencias

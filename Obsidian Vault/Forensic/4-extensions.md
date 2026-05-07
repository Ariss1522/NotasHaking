
# Reto 
### extensions
## Descripcion
This is a really weird text file. Can you find the flag?Get the flag from [TXT](https://challenge-files.picoctf.net/c_fickle_tempest/31fe772e6a4c71e867af0b2a93818e06d8f8ebf8af2a9615495d00356ff576da/flag.txt).
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ file flag.txt     
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                                    
┌──(kali㉿kali)-[~]
└─$ mv flag.txt flag.png
                                                                                    
┌──(kali㉿kali)-[~]
└─$ xdg-open flag.png 

picoCTF{now_you_know_about_extensions}
```
## Notas adicionales 

## Referencias



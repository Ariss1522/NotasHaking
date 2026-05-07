
# Reto 
### Flags
## Descripcion
What do the [flags](https://challenge-files.picoctf.net/c_fickle_tempest/214c9d918be75903d4183c35fa4b94ef60dba05fc4df37c97cf0868087067372/flag.png) mean?
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/214c9d918be75903d4183c35fa4b94ef60dba05fc4df37c97cf0868087067372/flag.png
--2026-04-22 10:26:02--  https://challenge-files.picoctf.net/c_fickle_tempest/214c9d918be75903d4183c35fa4b94ef60dba05fc4df37c97cf0868087067372/flag.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.49, 18.238.132.26, 18.238.132.115, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43257 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png            100%[=================>]  42.24K   181KB/s    in 0.2s    

2026-04-22 10:26:03 (181 KB/s) - ‘flag.png’ saved [43257/43257]

                                                                              
┌──(kali㉿kali)-[~]
└─$ open flag.png  
```
## Notas adicionales 
uso decodificador de banderas
## Referencias
- [https://www.dcode.fr/maritime-signals-code](https://www.dcode.fr/maritime-signals-code "https://www.dcode.fr/maritime-signals-code")


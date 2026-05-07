
# Reto 
### ReadMyCert
## Descripcion
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/424/readmycert.csr).
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/424/readmycert.csr
--2026-04-22 10:23:50--  https://artifacts.picoctf.net/c/424/readmycert.csr
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.120, 13.225.222.28, 13.225.222.125, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.225.222.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 997 [application/octet-stream]
Saving to: ‘readmycert.csr’

readmycert.csr      100%[=================>]     997  --.-KB/s    in 0s      

2026-04-22 10:23:51 (4.66 MB/s) - ‘readmycert.csr’ saved [997/997]

                                                                              
┌──(kali㉿kali)-[~]
└─$ open readmycert.csr 
picoCTF{read_mycert_5aeb0d4f}
```
## Notas adicionales 

## Referencias



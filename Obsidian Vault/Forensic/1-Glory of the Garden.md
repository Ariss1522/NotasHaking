
# Reto 
### Glory of the Garden
## Descripcion
This file contains more than it seems.Get the flag from [garden.jpg](https://challenge-files.picoctf.net/c_fickle_tempest/19722024edeecca10f263776ab05c8b1235b136dcf25aa6e976d3860513ffcd5/garden.jpg).
## Solucion
```
──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/19722024edeecca10f263776ab05c8b1235b136dcf25aa6e976d3860513ffcd5/garden.jpg
--2026-05-01 13:29:43--  https://challenge-files.picoctf.net/c_fickle_tempest/19722024edeecca10f263776ab05c8b1235b136dcf25aa6e976d3860513ffcd5/garden.jpg
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.125, 3.174.207.96, 3.174.207.121, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.125|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295191 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg           100%[======================>]   2.19M  6.43MB/s    in 0.3s    

2026-05-01 13:29:44 (6.43 MB/s) - ‘garden.jpg’ saved [2295191/2295191]

                                                                                    
┌──(kali㉿kali)-[~]
└─$ strings garden.jpg| grep pico                 
Here is a flag: picoCTF{more_than_m33ts_the_3y37fde8891}

```
## Notas adicionales 

## Referencias



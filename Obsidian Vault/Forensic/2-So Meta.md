
# Reto 
### So Meta
## Descripcion
Find the flag in this [picture](https://challenge-files.picoctf.net/c_fickle_tempest/d534c920bd33d42b413e67d21cacbf7aa232c4823ce29872eca285471558f00a/pico_img.png).
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/d534c920bd33d42b413e67d21cacbf7aa232c4823ce29872eca285471558f00a/pico_img.png
--2026-05-01 13:31:58--  https://challenge-files.picoctf.net/c_fickle_tempest/d534c920bd33d42b413e67d21cacbf7aa232c4823ce29872eca285471558f00a/pico_img.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.109, 3.174.207.96, 3.174.207.121, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.109|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png         100%[======================>] 106.25K  --.-KB/s    in 0.1s    

2026-05-01 13:31:59 (724 KB/s) - ‘pico_img.png’ saved [108795/108795]

                                                                                    
┌──(kali㉿kali)-[~]
└─$ strings pico_img.png | grep pico                                              
picoCTF{s0_m3ta_74af23ab}

```
## Notas adicionales 

## Referencias



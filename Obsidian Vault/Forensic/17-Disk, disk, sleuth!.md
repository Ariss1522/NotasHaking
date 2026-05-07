
# Reto 
###  Disk, disk, sleuth!
## Descripcion
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image.[dds1-alpine.flag.img.gz](https://challenge-files.picoctf.net/c_wily_courier/89797cb52348a4096884e4f58164b42a892f8cac34b91d887491f44a5f144718/dds1-alpine.flag.img.gz)
## Solucion
```
                                                                             
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/89797cb52348a4096884e4f58164b42a892f8cac34b91d887491f44a5f144718/dds1-alpine.flag.img.gz
--2026-03-23 10:16:18--  https://challenge-files.picoctf.net/c_wily_courier/89797cb52348a4096884e4f58164b42a892f8cac34b91d887491f44a5f144718/dds1-alpine.flag.img.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.49, 18.238.132.26, 18.238.132.115, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29768911 (28M) [application/octet-stream]
Saving to: ‘dds1-alpine.flag.img.gz’

dds1-alpine.flag.im 100%[================>]  28.39M  8.60MB/s    in 3.3s    

2026-03-23 10:16:25 (8.60 MB/s) - ‘dds1-alpine.flag.img.gz’ saved [29768911/29768911]

                                                                             
┌──(kali㉿kali)-[~]
└─$ gzip -d dds1-alpine.flag.img.gz 

┌──(kali㉿kali)-[~]
└─$ srch_strings dds1-alpine.flag.img | grep pico    
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}
```
## Notas adicionales 

## Referencias



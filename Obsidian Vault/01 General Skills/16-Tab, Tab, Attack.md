# Reto 
### Tab, Tab, Attack
## Descripcion
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.[Addadshashanammu.zip](https://challenge-files.picoctf.net/c_wily_courier/730d9106a6ce1d52c6463b90937ec89f5eb661388954fbd15cfa0c8a2eec012f/Addadshashanammu.zip)
## Solucion
```
-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/730d9106a6ce1d52c6463b90937ec89f5eb661388954fbd15cfa0c8a2eec012f/Addadshashanammu.zip
--2026-02-11 14:43:12--  https://challenge-files.picoctf.net/c_wily_courier/730d9106a6ce1d52c6463b90937ec89f5eb661388954fbd15cfa0c8a2eec012f/Addadshashanammu.zip
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 5166 (5.0K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip  100%[=======================>]   5.04K  --.-KB/s    in 0s      

2026-02-11 14:43:12 (1.75 GB/s) - 'Addadshashanammu.zip' saved [5166/5166]

-picoctf@webshell:~$ unzip addadshashanammu.zip
unzip:  cannot find or open addadshashanammu.zip, addadshashanammu.zip.zip or addadshashanammu.zip.ZIP.
Aaxel0583-picoctf@webshell:~$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
 extracting: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet.c  
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
Aaxel0583-picoctf@webshell:~$ cd 
Aaxel0583-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/ file 
-bash: cd: too many arguments
Aaxel0583-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/           
-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabit
ashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c
Aaxel0583-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabit
ashpi/Maelkashishi/Onnissiralis/Ularradallaku$ file fang-of-haynekhtnamet
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=4fdc1b4e898a0612ce5aa28e5012209f20bfc0ca, for GNU/Linux 3.2.0, not stripped
-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabit
ashpi/Maelkashishi/Onnissiralis/Ularradallaku$ strings fang-of-haynekhtnamet | grep pico
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}
-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabit
ashpi/Maelkashishi/Onnissiralis/Ularradallaku$ 
```

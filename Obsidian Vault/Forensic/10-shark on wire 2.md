
# Reto 
### shark on wire 2
## Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/4d884ac4c144f7871b97b96ae69a31a8483651db7929cd4ecb05d7447832f87c/capture.pcap). Recover the flag.
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/4d884ac4c144f7871b97b96ae69a31a8483651db7929cd4ecb05d7447832f87c/capture.pcap     
--2026-05-01 14:26:24--  https://challenge-files.picoctf.net/c_fickle_tempest/4d884ac4c144f7871b97b96ae69a31a8483651db7929cd4ecb05d7447832f87c/capture.pcap
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.125, 3.174.207.96, 3.174.207.109, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.125|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap         100%[======================>] 109.69K  --.-KB/s    in 0.07s   

2026-05-01 14:26:25 (1.53 MB/s) - ‘capture.pcap’ saved [112318/112318]

                                                                                    
┌──(kali㉿kali)-[~]
└─$ sudo apt update && sudo apt install python3-scapy -y
[sudo] password for kali: 
Hit:1 http://http.kali.org/kali kali-rolling InRelease
1979 packages can be upgraded. Run 'apt list --upgradable' to see them.
The following packages were automatically installed and are no longer required:
  openjdk-21-jre  openjdk-21-jre-headless
Use 'sudo apt autoremove' to remove them.

Upgrading:
  python3-scapy
                                                                                    
Summary:
  Upgrading: 1, Installing: 0, Removing: 0, Not Upgrading: 1978
  Download size: 2,002 kB
  Space needed: 764 kB / 58.5 GB available

Get:1 http://http.kali.org/kali kali-rolling/main amd64 python3-scapy all 2.7.0+dfsg1-1 [2,002 kB]
Fetched 2,002 kB in 1s (2,165 kB/s) 
(Reading database ... 495046 files and directories currently installed.)
Preparing to unpack .../python3-scapy_2.7.0+dfsg1-1_all.deb ...
Unpacking python3-scapy (2.7.0+dfsg1-1) over (2.6.1+dfsg-1) ...
Setting up python3-scapy (2.7.0+dfsg1-1) ...
Processing triggers for man-db (2.13.1-1) ...
Processing triggers for kali-menu (2025.4.3) ...
                                                                                    
┌──(kali㉿kali)-[~]
└─$ nano decodificador.py
from scapy.all import *

# Leemos la captura de red
paquetes = rdpcap("capture.pcap")
flag = ""

for paquete in paquetes:
    # Filtramos: Solo nos importan los paquetes UDP que vayan al puerto destino 22
    if UDP in paquete and paquete[UDP].dport == 22:
        puerto_origen = paquete[UDP].sport
        
        # Descartamos el puerto 5000 exacto (que pertenece a los mensajes "start" y "end")
        if puerto_origen > 5000:
            # Restamos 5000 y convertimos el número resultante a su letra ASCII
            flag += chr(puerto_origen - 5000)

print("\nLa flag escondida es:", flag)
┌──(kali㉿kali)-[~]
└─$ python decodificador.py 

La flag escondida es: picoCTF{p1LLf3r3d_data_v1a_st3g0}

 picoCTF{p1LLf3r3d_data_v1a_st3g0}

```
## Notas adicionales 

## Referencias



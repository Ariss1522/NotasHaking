# Reto 
## Obedient Cat
## Descripcion
This file has a flag in plain sight (aka "in-the-clear").[flag](https://challenge-files.picoctf.net/c_wily_courier/1a44abd1b8ea719b212d4645d5e9805a9db2e9062845609829d5d15e8e7d578c/flag)

## Solucion

```
picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/1a44abd1b8ea719b212d4645d5e9805a9db2e9062845609829d5d15e8e7d578c/flag
--2026-02-09 14:31:46--  https://challenge-files.picoctf.net/c_wily_courier/1a44abd1b8ea719b212d4645d5e9805a9db2e9062845609829d5d15e8e7d578c/flag
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.18, 3.160.5.40, 3.160.5.95, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                  100%[=======================>]      34  --.-KB/s    in 0s      

2026-02-09 14:31:46 (9.80 MB/s) - 'flag' saved [34/34]

Aaxel0583-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_9b8fa0bc}
```
## Notas adicionales 

## Referencias
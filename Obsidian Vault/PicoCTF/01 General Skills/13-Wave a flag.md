 Reto 
## Wave a flag 
## Descripcion
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...[warm](https://challenge-files.picoctf.net/c_wily_courier/fc72a950cbaa130f81486c2df35deced17604b2c08c6a5aa99d18168036d3107/warm)

## Solucion
```
LiszAc-picoctf@webshell:~$ ls
README.txt  file  flag  strings  strings.1  warm
LiszAc-picoctf@webshell:~$ ./warm 
-bash: ./warm: Permission denied
LiszAc-picoctf@webshell:~$ chmod +x warm
LiszAc-picoctf@webshell:~$ ls
README.txt  file  flag  strings  strings.1  warm
LiszAc-picoctf@webshell:~$ ./warm 
Hello user! Pass me a -h to learn what I can do!
LiszAc-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
```
 picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}

# Reto 
### Pixelated
## Descripcion
I have these 2 images, can you make a flag out of them?[scrambled1.png](https://challenge-files.picoctf.net/c_wily_courier/bfbfec697635785f9c857dc66f592c111a0af651ba20e5e18d9a15096dd19dd5/scrambled1.png) [scrambled2.png](https://challenge-files.picoctf.net/c_wily_courier/bfbfec697635785f9c857dc66f592c111a0af651ba20e5e18d9a15096dd19dd5/scrambled2.png)
## Solucion
```
──(kali㉿kali)-[~]
└─$ cd /opt  
                                                                             
┌──(kali㉿kali)-[/opt]
└─$ cd /opt
sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
sudo chmod +x stegsolve.jar
java -jar /opt/stegsolve.jar
[sudo] password for kali: 
--2026-04-22 09:55:14--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.165.33
Connecting to www.caesum.com (www.caesum.com)|216.234.165.33|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar       100%[================>] 304.95K   183KB/s    in 1.7s    

2026-04-22 09:55:16 (183 KB/s) - ‘stegsolve.jar’ saved [312271/312271]

                                                                             
┌──(kali㉿kali)-[/opt]
└─$ java -jar /opt/stegsolve.jar 
                                                                             
┌──(kali㉿kali)-[/opt]
└─$ java -jar /opt/stegsolve.jar

---------------------------------------
                             
                                                                             
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/bfbfec697635785f9c857dc66f592c111a0af651ba20e5e18d9a15096dd19dd5/scrambled1.png
--2026-04-22 09:49:34--  https://challenge-files.picoctf.net/c_wily_courier/bfbfec697635785f9c857dc66f592c111a0af651ba20e5e18d9a15096dd19dd5/scrambled1.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.115, 18.238.132.88, 18.238.132.49, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197174 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png      100%[================>] 192.55K   416KB/s    in 0.5s    

2026-04-22 09:49:36 (416 KB/s) - ‘scrambled1.png’ saved [197174/197174]

                                                                             
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/bfbfec697635785f9c857dc66f592c111a0af651ba20e5e18d9a15096dd19dd5/scrambled2.png
--2026-04-22 09:49:44--  https://challenge-files.picoctf.net/c_wily_courier/bfbfec697635785f9c857dc66f592c111a0af651ba20e5e18d9a15096dd19dd5/scrambled2.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.49, 18.238.132.115, 18.238.132.26, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197173 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png      100%[================>] 192.55K   520KB/s    in 0.4s    

2026-04-22 09:49:46 (520 KB/s) - ‘scrambled2.png’ saved [197173/197173]

                                                                             
┌──(kali㉿kali)-[~]
└─$ open scrambled                        
                                                                             
┌──(kali㉿kali)-[~]
└─$ ls
Desktop  scrambled1.png  scrambled2.png
                                                                             
┌──(kali㉿kali)-[~]
└─$ open flag,png 
                                                                             
┌──(kali㉿kali)-[~]
└─$ open flagg,png
                                                                             
┌──(kali㉿kali)-[~]
└─$ open flagg.png 
                                                                             
┌──(kali㉿kali)-[~]
└─$ 



picoCTF{8cdf93c3}
```
## Notas adicionales 

## Referencias



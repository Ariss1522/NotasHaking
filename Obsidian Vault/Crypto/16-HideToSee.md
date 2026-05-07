
# Reto 
### HideToSee
## Descripcion
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/235/atbash.jpg).
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/235/atbash.jpg
--2026-04-22 10:09:11--  https://artifacts.picoctf.net/c/235/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.120, 13.225.222.28, 13.225.222.125, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.225.222.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51499 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg          100%[=================>]  50.29K  --.-KB/s    in 0.05s   

2026-04-22 10:09:12 (916 KB/s) - ‘atbash.jpg’ saved [51499/51499]

                                                                              
┌──(kali㉿kali)-[~]
└─$ open atbash.jpg                       
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo apt install steghide~  
[sudo] password for kali: 
Error: Unable to locate package steghide~
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo apt install steghide 
Installing:                     
  steghide
                                                                              
Installing dependencies:
  libmcrypt4  libmhash2
                                                                              
Suggested packages:
  libmcrypt-dev  mcrypt

Summary:
  Upgrading: 0, Installing: 3, Removing: 0, Not Upgrading: 1890
  Download size: 309 kB
  Space needed: 916 kB / 58.9 GB available

Continue? [Y/n] y
Get:1 http://http.kali.org/kali kali-rolling/main amd64 libmcrypt4 amd64 2.5.8-8+b1 [72.1 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 libmhash2 amd64 0.9.9.9-11 [93.2 kB]
Get:3 http://kali.download/kali kali-rolling/main amd64 steghide amd64 0.5.1-15 [144 kB]
Fetched 309 kB in 2s (134 kB/s)   
Selecting previously unselected package libmcrypt4:amd64.
(Reading database ... 494519 files and directories currently installed.)
Preparing to unpack .../libmcrypt4_2.5.8-8+b1_amd64.deb ...
Unpacking libmcrypt4:amd64 (2.5.8-8+b1) ...
Selecting previously unselected package libmhash2:amd64.
Preparing to unpack .../libmhash2_0.9.9.9-11_amd64.deb ...
Unpacking libmhash2:amd64 (0.9.9.9-11) ...
Selecting previously unselected package steghide.
Preparing to unpack .../steghide_0.5.1-15_amd64.deb ...
Unpacking steghide (0.5.1-15) ...
Setting up libmhash2:amd64 (0.9.9.9-11) ...
Setting up libmcrypt4:amd64 (2.5.8-8+b1) ...
Setting up steghide (0.5.1-15) ...
Processing triggers for libc-bin (2.41-12) ...
Processing triggers for man-db (2.13.1-1) ...
Processing triggers for kali-menu (2025.4.3) ...
                                                                              
┌──(kali㉿kali)-[~]
└─$ steghide --extract -sf atbash.jpg
Enter passphrase: 
steghide: could not extract any data with that passphrase!
                                                                              
┌──(kali㉿kali)-[~]
└─$ open atbash.jpg                  
                                                                              
┌──(kali㉿kali)-[~]
└─$ steghide --extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                              
┌──(kali㉿kali)-[~]
└─$ steghide info  atbash.jpg
"atbash.jpg":
  format: jpeg
  capacity: 2.4 KB
Try to get information about embedded data ? (y/n) y
Enter passphrase: 
steghide: could not extract any data with that passphrase!
                                                                              
┌──(kali㉿kali)-[~]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
the file "encrypted.txt" does already exist. overwrite ? (y/n) n
steghide: did not write to file "encrypted.txt".
                                                                              
┌──(kali㉿kali)-[~]
└─$ steghide extract -sf atbash.jpg
Enter passphrase: 
the file "encrypted.txt" does already exist. overwrite ? (y/n) y
wrote extracted data to "encrypted.txt".
                                                                              
┌──(kali㉿kali)-[~]
└─$ cat encrypted.txt
krxlXGU{zgyzhs_xizxp_92533667}


picoCTF{atbash_crack_92533667}
```
## Notas adicionales 
uso de cyber chef
## Referencias



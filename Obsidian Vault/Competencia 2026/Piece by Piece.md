
# Reto 
### Piece by Piece
## Descripcion
After logging in, you will find multiple file parts in your home directory. These parts need to be combined and extracted to reveal the flag.SSH to `dolphin-cove.picoctf.net`:`50982` and login as `ctf-player` with password `1db87a14`.
## Solucion
```
LiszAc-picoctf@webshell:~$ ssh ctf-player@dolphin-cove.picoctf.net -p 50982
The authenticity of host '[dolphin-cove.picoctf.net]:50982 ([3.13.34.175]:50982)' can't be established.
ED25519 key fingerprint is SHA256:rdvWhF7Klwlu1EivysxTh/FjeqFI0dSEK5gaelaW9t8.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:7: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[dolphin-cove.picoctf.net]:50982' (ED25519) to the list of known hosts.
ctf-player@dolphin-cove.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.17.0-1007-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@pico-chall$ ls -l
total 24
-rw-r--r-- 1 ctf-player ctf-player 282 Feb  4 21:22 instructions.txt
-rw-r--r-- 1 ctf-player ctf-player  51 Feb  4 22:40 part_aa
-rw-r--r-- 1 ctf-player ctf-player  51 Feb  4 22:40 part_ab
-rw-r--r-- 1 ctf-player ctf-player  51 Feb  4 22:40 part_ac
-rw-r--r-- 1 ctf-player ctf-player  51 Feb  4 22:40 part_ad
-rw-r--r-- 1 ctf-player ctf-player  35 Feb  4 22:40 part_ae
ctf-player@pico-chall$ cat instructions.txt 
Hint:

- The flag is split into multiple parts as a zipped file.
- Use Linux commands to combine the parts into one file.
- The zip file is password protected. Use this "supersecret" password to extract the zip file.
- After unzipping, check the extracted text file for the flag.


ctf-player@pico-chall$ cat part_* > archivo_secreto
ctf-player@pico-chall$ file archivo_secreto 
archivo_secreto: Zip archive data, at least v1.0 to extract
ctf-player@pico-chall$ unzip -P supersecret archivo_completo.zip
unzip:  cannot find or open archivo_completo.zip, archivo_completo.zip.zip or archivo_completo.zip.ZIP.
ctf-player@pico-chall$ unzip -P supersecret archivo_secreto.zip 
unzip:  cannot find or open archivo_secreto.zip, archivo_secreto.zip.zip or archivo_secreto.zip.ZIP.
ctf-player@pico-chall$ cat part_* > archivo_completo.zip
ctf-player@pico-chall$ unzip -P supersecret archivo_completo.zip
Archive:  archivo_completo.zip
 extracting: flag.txt                
ctf-player@pico-chall$ cat flag.txt 
picoCTF{z1p_and_spl1t_f1l3s_4r3_fun_574adc66}
```



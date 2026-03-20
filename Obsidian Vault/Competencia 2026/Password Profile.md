
# Reto 
### Password Profile
## Descripcion
We intercepted a suspicious file from a system, but instead of the password itself, it only contains its SHA-1 hash. Using OSINT techniques, you are provided with personal details about the target. Your task is to leverage this information to generate a custom password list and recover the original password by matching its hash.Download the following files:[userinfo](https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/userinfo.txt): Contains the personal details.[hash](https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/hash.txt): Contains the SHA-1 hash of the password.[check_password](https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/check_password.py): Script to test passwords against the hash.
## Solucion
```
Aaxel0583-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/userinfo.txt
--2026-03-19 01:28:54--  https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/userinfo.txt
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.18, 3.160.5.40, 3.160.5.64, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 113 [application/octet-stream]
Saving to: 'userinfo.txt'

userinfo.txt          100%[=======================>]     113  --.-KB/s    in 0s      

2026-03-19 01:28:54 (58.5 MB/s) - 'userinfo.txt' saved [113/113]

Aaxel0583-picoctf@webshell:~$ wgethttps://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/hash.txt
-bash: wgethttps://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/hash.txt: No such file or directory
Aaxel0583-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_plain_mesa/3c
16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/hash.txt
--2026-03-19 01:29:25--  https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/hash.txt
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.95, 3.160.5.64, 3.160.5.40, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 41 [application/octet-stream]
Saving to: 'hash.txt'

hash.txt              100%[=======================>]      41  --.-KB/s    in 0s      

2026-03-19 01:29:25 (24.6 MB/s) - 'hash.txt' saved [41/41]

Aaxel0583-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/check_password.py
--2026-03-19 01:29:36--  https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/check_password.py
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.18, 3.160.5.40, 3.160.5.95, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 731 [application/octet-stream]
Saving to: 'check_password.py'

check_password.py     100%[=======================>]     731  --.-KB/s    in 0s      

2026-03-19 01:29:36 (387 MB/s) - 'check_password.py' saved [731/731]

Aaxel0583-picoctf@webshell:~$ cat userinfo.txt 
First Name: Alice
Surname: Johnson
Nickname: AJ
Birthdate: 15-07-1990
Partner's Name: Bob
Child's Name: Charlie

Aaxel0583-picoctf@webshell:~$ git clone https://github.com/Mebus/cupp.git
Cloning into 'cupp'...
remote: Enumerating objects: 261, done.
remote: Counting objects: 100% (95/95), done.
remote: Compressing objects: 100% (26/26), done.
remote: Total 261 (delta 84), reused 69 (delta 69), pack-reused 166 (from 2)
Receiving objects: 100% (261/261), 2.16 MiB | 1.81 MiB/s, done.
Resolving deltas: 100% (142/142), done.
Aaxel0583-picoctf@webshell:~$ cd cupp
Aaxel0583-picoctf@webshell:~/cupp$ python3 cupp.py -i
 ___________ 
   cupp.py!                 # Common
      \                     # User
       \   ,__,             # Passwords
        \  (oo)____         # Profiler
           (__)    )\   
              ||--|| *      [ Muris Kurgas | j0rgan@remote-exploit.org ]
                            [ Mebus | https://github.com/Mebus/]


[+] Insert the information about the victim to make a dictionary
[+] If you don't know all the info, just hit enter when asked! ;)

> First Name: Alice
> Surname: Johnson
> Nickname: AJ
> Birthdate (DDMMYYYY): 15071990


> Partners) name: Bob
> Partners) nickname: 
> Partners) birthdate (DDMMYYYY): 


> Child's name: Charlie
> Child's nickname: 
> Child's birthdate (DDMMYYYY): 


> Pet's name: 
> Company name: 


> Do you want to add some key words about the victim? Y/[N]: N
> Do you want to add special chars at the end of words? Y/[N]: Y
> Do you want to add some random numbers at the end of words? Y/[N]:Y
> Leet mode? (i.e. leet = 1337) Y/[N]: Y

[+] Now making a dictionary...
[+] Sorting list and removing duplicates...
[+] Saving dictionary to alice.txt, counting 29372 words.
> Hyperspeed Print? (Y/n) : n
[+] Now load your pistolero with alice.txt and shoot! Good luck!
Aaxel0583-picoctf@webshell:~/cupp$ mv alice.txt ../
Aaxel0583-picoctf@webshell:~/cupp$ cd ..
Aaxel0583-picoctf@webshell:~$ cat check_password
cat: check_password: No such file or directory
Aaxel0583-picoctf@webshell:~$ ls
README.txt  alice.txt  app.py  check_password.py  cupp  hash.txt  userinfo.txt
Aaxel0583-picoctf@webshell:~$ cat check_password.py 
#!/usr/bin/env python3
import hashlib

HASH_FILE = "hash.txt"
WORDLIST_FILE = "passwords.txt" # wordlist that was generated using CUPP

def load_hash():
    with open(HASH_FILE, "r") as f:
        return f.read().strip()

def crack_password(target_hash):
    with open(WORDLIST_FILE, "r", encoding="utf-8", errors="ignore") as f:
        for password in f:
            password = password.strip()
            if hashlib.sha1(password.encode()).hexdigest() == target_hash:
                return password
    return None

if __name__ == "__main__":
    target_hash = load_hash()
    result = crack_password(target_hash)
    if result:
        print(f"Password found: picoCTF{{{result}}}")
    else:
        print("No match found.")
Aaxel0583-picoctf@webshell:~$ mv alice.txt passwords.txt
Aaxel0583-picoctf@webshell:~$ python3 check_password.py
Password found: picoCTF{Aj_15901990}
Aaxel0583-picoctf@webshell:~$ 
```
## Notas adicionales 
uso de cupp para crear  documento con varias contraseñas de la "victima"
## Referencias
https://github.com/Mebus/cupp.git


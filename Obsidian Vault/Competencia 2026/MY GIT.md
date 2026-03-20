
# Reto 
### MY GIT
## Descripcion
I have built my own Git server with my own rules!You can clone the challenge repo using the command below.`git clone ssh://git@foggy-cliff.picoctf.net:64905/git/challenge.git`Here's the password: `32a53fa0`Check the README to get your flag!
## Solucion
```
Aaxel0583-picoctf@webshell:~$ git clone ssh://git@foggy-cliff.picoctf.net:51666/git/challenge.git
Cloning into 'challenge'...
The authenticity of host '[foggy-cliff.picoctf.net]:51666 ([3.15.249.208]:51666)' can't be established.
ED25519 key fingerprint is SHA256:Grm7IvZgdCDbXv3DtQ70/6WKHA2q3XhT+sfva8nLT38.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[foggy-cliff.picoctf.net]:51666' (ED25519) to the list of known hosts.
git@foggy-cliff.picoctf.net's password: 
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (3/3), done.
Aaxel0583-picoctf@webshell:~$ cd challenge/
Aaxel0583-picoctf@webshell:~/challenge$ ls      
README.md
Aaxel0583-picoctf@webshell:~/challenge$ cat README.md 
# MyGit

### If you want the flag, make sure to push the flag!

Only flag.txt pushed by ```root:root@picoctf``` will be updated with the flag.

GOOD LUCK!
Aaxel0583-picoctf@webshell:~/challenge$ git config user.name "root"
Aaxel0583-picoctf@webshell:~/challenge$ git config user.email "root@picoctf"
Aaxel0583-picoctf@webshell:~/challenge$ echo "dame la bandera" > flag.txt
Aaxel0583-picoctf@webshell:~/challenge$ git add flag.txt
Aaxel0583-picoctf@webshell:~/challenge$ git commit -m "Subiendo flag.txt como root"
[master 21ade03] Subiendo flag.txt como root
 1 file changed, 1 insertion(+)
 create mode 100644 flag.txt
Aaxel0583-picoctf@webshell:~/challenge$ git push
git@foggy-cliff.picoctf.net's password: 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 294 bytes | 294.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: Author matched and flag.txt found in commit...
remote: Congratulations! You have successfully impersonated the root user
remote: Here's your flag: picoCTF{1mp3rs0n4t4_g17_345y_f3a6488d}
To ssh://foggy-cliff.picoctf.net:51666/git/challenge.git
   4142dd3..21ade03  master -> master
```




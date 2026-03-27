
# Reto 
### SansAlpha
## Descripcion
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.`ssh -p 62111 ctf-player@mimas.picoctf.net`Use password: `6abf4a82`
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ ssh -p 53688 ctf-player@mimas.picoctf.net
The authenticity of host '[mimas.picoctf.net]:53688 ([52.15.88.75]:53688)' can't be established.
ED25519 key fingerprint is: SHA256:n/hDgUtuTTF85Id7k2fxmHvb6rrLrACHNM6xLZ46AqQ
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:3: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[mimas.picoctf.net]:53688' (ED25519) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@mimas.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1016-aws x86_64)

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

SansAlpha$ ./*
bash: ./blargh: Is a directory

SansAlpha$ ./*/*
bash: ./blargh/flag.txt: Permission denied

SansAlpha$ /???/[!_]64 /????/??????????/??????/???????
bash: /???/[!_]64: No such file or directory

SansAlpha$ /???/[ !_]64 /????/??????????/??????/???????
bash: !_]64: event not found

SansAlpha$ /???/???[ !_]64 /????/??????????/??????/???????
bash: !_]64: event not found

SansAlpha$ /???/???[!_]64 /????/??????????/??????/???????
/bin/base64: '/????/??????????/??????/???????': No such file or directory

SansAlpha$ /???/???[!_]64 /????/??????????/??????/????????
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV84YjNkODNhZH0=

SansAlpha$ exit
Connection to mimas.picoctf.net closed.
                                                                                                   
┌──(kali㉿kali)-[~]
└─$ echo "cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV84YjNkODNhZH0=" | base64 -d

return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_8b3d83ad} 
```
## Notas adicionales 

## Referencias



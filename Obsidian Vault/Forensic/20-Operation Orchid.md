
# Reto 
### Operation Orchid
## Descripcion
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)
## Solucion
```
                                                                             
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/213/disk.flag.img.gz
--2026-03-23 10:36:57--  https://artifacts.picoctf.net/c/213/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.61, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 44360922 (42M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz    100%[================>]  42.31M  4.60MB/s    in 17s     

2026-03-23 10:37:34 (2.56 MB/s) - ‘disk.flag.img.gz’ saved [44360922/44360922]

                                                                             
┌──(kali㉿kali)-[~]
└─$ gzip -d disk.flag.img.gz 

                                                                             
┌──(kali㉿kali)-[~]
└─$ 
                                                                             
┌──(kali㉿kali)-[~]
└─$ mmls disk.flag.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -o 411648 disk.flag.img    
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -o 411648 disk.flag.img 472 -r
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -o 411648 disk.flag.img 1876 -r
Error extracting file from image (ext2fs_dir_open_meta: Error reading directory contents: 1876
)
                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -o 411648 disk.flag.img 1876   
Error extracting file from image (ext2fs_dir_open_meta: Error reading directory contents: 1876
)
                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -o 411648 disk.flag.img 1782 
Error extracting file from image (ext2fs_dir_open_meta: Error reading directory contents: 1782
)
                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -o 411648 disk.flag.img 1875 
Error extracting file from image (ext2fs_dir_open_meta: Error reading directory contents: 1875
)
                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -o 411648 disk.flag.img 1875 -r
Error extracting file from image (ext2fs_dir_open_meta: Error reading directory contents: 1875
)
                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -o 411648 disk.flag.img 472 -r 
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
                                                                             
┌──(kali㉿kali)-[~]
└─$ fls -o 411648 disk.flag.img 1875   
Error extracting file from image (ext2fs_dir_open_meta: Error reading directory contents: 1875
)
                                                                             
┌──(kali㉿kali)-[~]
└─$ icat -o 411648 disk.flag.img 1875     
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                                             
┌──(kali㉿kali)-[~]
└─$ icat -o 411648 disk.flag.img 1782 > flag.txt.enc
                                                                             
┌──(kali㉿kali)-[~]
└─$ openssl aes256 -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword123     
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
                                                                             
┌──(kali㉿kali)-[~]
└─$ openssl aes256 -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
                                                                             
┌──(kali㉿kali)-[~]
└─$ openssl aes256 -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567   

*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
                                                                             
┌──(kali㉿kali)-[~]
└─$ ls
Desktop  disk.flag.img  flag.txt  flag.txt.enc
                                                                             
┌──(kali㉿kali)-[~]
└─$ cat flag.txt
Salted__
C(D�|��� �o�; z���#d�e(*~R�ƀ��X��5gro/�_�,�Vo�o�yw"Zj�h�doy�k���z
                                                                 �!b~5�B0I�u                                                                             
┌──(kali㉿kali)-[~]
└─$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567

*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40B7EA13E97F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                             
┌──(kali㉿kali)-[~]
└─$ cat flag.txt 
picoCTF{h4un71ng_p457_5113beab}
```
## Notas adicionales 

## Referencias



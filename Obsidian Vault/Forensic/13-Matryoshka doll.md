
# Reto 
### Matryoshka doll
## Descripcion
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one?Image: [dolls.jpg](https://challenge-files.picoctf.net/c_wily_courier/0f5ef9c383aa83d319ccb01805f4b9499934bf6a44fdcb5a9f2039de92b6c24a/dolls.jpg)
## Solucion
```
                                                                                   
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/0f5ef9c383aa83d319ccb01805f4b9499934bf6a44fdcb5a9f2039de92b6c24a/dolls.jpg     
--2026-05-01 15:30:12--  https://challenge-files.picoctf.net/c_wily_courier/0f5ef9c383aa83d319ccb01805f4b9499934bf6a44fdcb5a9f2039de92b6c24a/dolls.jpg
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.121, 3.174.207.96, 3.174.207.125, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.121|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651613 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg            100%[=====================>] 636.34K  --.-KB/s    in 0.1s    

2026-05-01 15:30:13 (4.24 MB/s) - ‘dolls.jpg’ saved [651613/651613]

                                                                                   
┌──(kali㉿kali)-[~]
└─$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378933, uncompressed size: 383920, name: base_images/2_c.jpg
651591        0x9F147         End of Zip archive, footer length: 22

                                                                                   
┌──(kali㉿kali)-[~]
└─$ binwalk -e dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378933, uncompressed size: 383920, name: base_images/2_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                   
┌──(kali㉿kali)-[~]
└─$ cd _dolls.jpg.extracted/base_images
ls
2_c.jpg
                                                                                   
┌──(kali㉿kali)-[~/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg
cd _2_c.jpg.extracted/base_images

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196025, uncompressed size: 201427, name: base_images/3_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                   
┌──(kali㉿kali)-[~/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg
cd _3_c.jpg.extracted/base_images

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77633, uncompressed size: 79786, name: base_images/4_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                   
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg
cd _4_c.jpg.extracted

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
79578         0x136DA         Zip archive data, at least v1.0 to extract, compressed size: 42, uncompressed size: 42, name: flag.txt

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                   
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                   
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt                       

picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}

```
## Notas adicionales 

## Referencias



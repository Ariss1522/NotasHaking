
# Reto 
### WhitePages
## Descripcion
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.picoctf.net/c_fickle_tempest/3ba37d6bee0d96d5e3783ba94da753407f9168b61d796797f0816db5aaa86136/whitepages.txt) is all blank!
## Solucion
```
                                                                                    
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/3ba37d6bee0d96d5e3783ba94da753407f9168b61d796797f0816db5aaa86136/whitepages.txt
--2026-05-01 13:56:47--  https://challenge-files.picoctf.net/c_fickle_tempest/3ba37d6bee0d96d5e3783ba94da753407f9168b61d796797f0816db5aaa86136/whitepages.txt
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.121, 3.174.207.96, 3.174.207.109, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.121|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2772 (2.7K) [application/octet-stream]
Saving to: ‘whitepages.txt’

whitepages.txt       100%[======================>]   2.71K  --.-KB/s    in 0s      

2026-05-01 13:56:47 (13.2 MB/s) - ‘whitepages.txt’ saved [2772/2772]

                                                                                    
┌──(kali㉿kali)-[~]
└─$ hexdump -C whitepages.txt | head
00000000  e2 80 83 e2 80 83 e2 80  83 e2 80 83 20 e2 80 83  |............ ...|
00000010  20 e2 80 83 e2 80 83 20  20 20 e2 80 83 e2 80 83  | ......   ......|
00000020  e2 80 83 e2 80 83 e2 80  83 20 20 e2 80 83 20 e2  |.........  ... .|
00000030  80 83 e2 80 83 20 e2 80  83 20 20 e2 80 83 e2 80  |..... ...  .....|
00000040  83 e2 80 83 20 20 e2 80  83 20 20 e2 80 83 20 20  |....  ...  ...  |
00000050  20 20 e2 80 83 20 e2 80  83 e2 80 83 e2 80 83 e2  |  ... ..........|
00000060  80 83 20 20 e2 80 83 20  e2 80 83 20 e2 80 83 20  |..  ... ... ... |
00000070  e2 80 83 e2 80 83 e2 80  83 20 e2 80 83 e2 80 83  |......... ......|
00000080  e2 80 83 20 20 e2 80 83  e2 80 83 e2 80 83 e2 80  |...  ...........|
00000090  83 e2 80 83 20 e2 80 83  20 e2 80 83 e2 80 83 e2  |.... ... .......|
                                                                                    
┌──(kali㉿kali)-[~]
└─$ nano solve.py
# Abrimos el archivo leyendo sus bytes (rb)
with open("whitepages.txt", "rb") as f:
    data = f.read()

# Reemplazamos el espacio largo por '0' y el espacio normal por '1'
data = data.replace(b'\xe2\x80\x83', b'0')
data = data.replace(b'\x20', b'1')

# Convertimos la cadena de ceros y unos a texto real
mensaje = ""
for i in range(0, len(data), 8):
    byte = data[i:i+8]
    try:
        mensaje += chr(int(byte, 2))
    except:
        pass

print(mensaje)
                                                                                    
┌──(kali㉿kali)-[~]
└─$ python3 solve.py

picoCTF

SEE PUBLIC RECORDS & BACKGROUND REPORT
5000 Forbes Ave, Pittsburgh, PA 15213
picoCTF{not_all_spaces_are_created_equal_f62118c302bc9c9791e81915c805af3d}

picoCTF{not_all_spaces_are_created_equal_f62118c302bc9c9791e81915c805af3d}

```
## Notas adicionales 

## Referencias



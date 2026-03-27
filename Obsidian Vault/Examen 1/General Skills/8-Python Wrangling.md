
# Reto 
### Python Wrangling
## Descripcion
Python scripts are invoked kind of like programs in the Terminal...Can you run [ende.py](https://challenge-files.picoctf.net/c_wily_courier/0d4c2d3266a170a6b1cc9150c9a1cf489cd39be1968f82164aea44fb88e810b7/ende.py) using [password.txt](https://challenge-files.picoctf.net/c_wily_courier/0d4c2d3266a170a6b1cc9150c9a1cf489cd39be1968f82164aea44fb88e810b7/password.txt) to get [flag.txt.en](https://challenge-files.picoctf.net/c_wily_courier/0d4c2d3266a170a6b1cc9150c9a1cf489cd39be1968f82164aea44fb88e810b7/flag.txt.en)?
## Solucion
```
                                                                            
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/0d4c2d3266a170a6b1cc9150c9a1cf489cd39be1968f82164aea44fb88e810b7/ende.py
--2026-03-25 19:31:03--  https://challenge-files.picoctf.net/c_wily_courier/0d4c2d3266a170a6b1cc9150c9a1cf489cd39be1968f82164aea44fb88e810b7/ende.py
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.84, 3.161.44.61, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1328 (1.3K) [application/octet-stream]
Saving to: ‘ende.py’

ende.py            100%[================>]   1.30K  --.-KB/s    in 0s      

2026-03-25 19:31:04 (16.6 MB/s) - ‘ende.py’ saved [1328/1328]

                                                                            
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/0d4c2d3266a170a6b1cc9150c9a1cf489cd39be1968f82164aea44fb88e810b7/password.txt
--2026-03-25 19:31:15--  https://challenge-files.picoctf.net/c_wily_courier/0d4c2d3266a170a6b1cc9150c9a1cf489cd39be1968f82164aea44fb88e810b7/password.txt
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.103, 3.161.44.61, 3.161.44.84, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.103|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: ‘password.txt’

password.txt       100%[================>]      33  --.-KB/s    in 0s      

2026-03-25 19:31:16 (61.6 MB/s) - ‘password.txt’ saved [33/33]

                                                                            
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/0d4c2d3266a170a6b1cc9150c9a1cf489cd39be1968f82164aea44fb88e810b7/flag.txt.en 
--2026-03-25 19:31:24--  https://challenge-files.picoctf.net/c_wily_courier/0d4c2d3266a170a6b1cc9150c9a1cf489cd39be1968f82164aea44fb88e810b7/flag.txt.en
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.103, 3.161.44.61, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: ‘flag.txt.en’

flag.txt.en        100%[================>]     140  --.-KB/s    in 0s      

2026-03-25 19:31:25 (341 MB/s) - ‘flag.txt.en’ saved [140/140]

                                                                            
┌──(kali㉿kali)-[~]
└─$ cat password.txt 
720b6ad346f84cd483c60c7464dd95d4
┌──(kali㉿kali)-[~]
└─$ python3 ende.py -d flag.txt.en
Please enter the password:720b6ad346f84cd483c60c7464dd95d4
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}

```




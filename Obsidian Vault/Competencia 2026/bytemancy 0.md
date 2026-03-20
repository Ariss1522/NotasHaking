
# Reto 
### bytemancy 0
## Descripcion
Can you conjure the right bytes? The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_candy_mountain/a50bbcde1dd7d8337a88235c9340de0f5f1482980fafa943a318859128f42672/app.py).Connect to the program with netcat:`$ nc candy-mountain.picoctf.net 58902`
## Solucion
```
Aaxel0583-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_candy_mountain/a50bbcde1dd7d8337a88235c9340de0f5f1482980fafa943a318859128f42672/app.py
--2026-03-19 01:23:09--  https://challenge-files.picoctf.net/c_candy_mountain/a50bbcde1dd7d8337a88235c9340de0f5f1482980fafa943a318859128f42672/app.py
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.95, 3.160.5.64, 3.160.5.18, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 773 [application/octet-stream]
Saving to: 'app.py'

app.py                100%[=======================>]     773  --.-KB/s    in 0s      

2026-03-19 01:23:09 (372 MB/s) - 'app.py' saved [773/773]

Aaxel0583-picoctf@webshell:~$ cat app.py 
while(True):
  try:
    print('⊹──────[ BYTEMANCY-0 ]──────⊹')
    print("☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐")
    print()
    print('Send me ASCII DECIMAL 101, 101, 101, side-by-side, no space.')
    print()
    print("☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐")
    print('⊹─────────────⟡─────────────⊹')
    user_input = input('==> ')
    if user_input == "\x65\x65\x65":
      print(open("./flag.txt", "r").read())
      break
    else:
      print("That wasn't it. I got: " + str(user_input))
      print()
      print()
      print()
  except Exception as e:
    print(e)
    break
Aaxel0583-picoctf@webshell:~$ nc candy-mountain.picoctf.net 58902
⊹──────[ BYTEMANCY-0 ]──────⊹
☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐

Send me ASCII DECIMAL 101, 101, 101, side-by-side, no space.

☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐
⊹─────────────⟡─────────────⊹
==> eee}
That wasn't it. I got: eee}



⊹──────[ BYTEMANCY-0 ]──────⊹
☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐

Send me ASCII DECIMAL 101, 101, 101, side-by-side, no space.

☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐
⊹─────────────⟡─────────────⊹
==> eee
picoCTF{pr1n74813_ch4r5_9b465df3
```
## Notas adicionales 
uso de ascii y conversion hexadecimal, el numero dado de x65 en ascii da como resultado la letra e



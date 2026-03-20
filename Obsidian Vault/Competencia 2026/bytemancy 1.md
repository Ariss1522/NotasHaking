
# Reto 
### bytemancy 1
## Descripcion
Can you conjure the right bytes? The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_foggy_cliff/49b08edbecf2919bd6a98de9f784e6f6bfb0f3662b077159931ec9d338ccf268/app.py).Connect to the program with netcat:`$ nc foggy-cliff.picoctf.net 57397`
## Solucion
```
LiszAc-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_foggy_cliff/49b08edbecf2919bd6a98de9f784e6f6bfb0f3662b077159931ec9d338ccf268/app.py
--2026-03-19 04:09:04--  https://challenge-files.picoctf.net/c_foggy_cliff/49b08edbecf2919bd6a98de9f784e6f6bfb0f3662b077159931ec9d338ccf268/app.py
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.95, 3.160.5.40, 3.160.5.64, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 771 [application/octet-stream]
Saving to: 'app.py'

app.py                100%[=======================>]     771  --.-KB/s    in 0s      

2026-03-19 04:09:04 (311 MB/s) - 'app.py' saved [771/771]

LiszAc-picoctf@webshell:~$ cat app.py 
while(True):
  try:
    print('⊹──────[ BYTEMANCY-1 ]──────⊹')
    print("☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐")
    print()
    print('Send me ASCII DECIMAL 101 1751 times, side-by-side, no space.')
    print()
    print("☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐")
    print('⊹─────────────⟡─────────────⊹')
    user_input = input('==> ')
    if user_input == "\x65"*1751:
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
LiszAc-picoctf@webshell:~$ python3 -c "print('e' * 1751)" | nc foggy-cliff.picoctf.net 57397
⊹──────[ BYTEMANCY-1 ]──────⊹
☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐

Send me ASCII DECIMAL 101 1751 times, side-by-side, no space.

☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐
⊹─────────────⟡─────────────⊹
==> picoCTF{h0w_m4ny_e's???_446bf6f1}
```
## Notas adicionales 
```
uso del codigo python3 -c "print('e' * 1751)" | nc foggy-cliff.picoctf.net 57397

para facilitar el reto
```





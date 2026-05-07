
# Reto 
### basic-mod1
## Descripcion
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/127/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Solucion
```
                                                                              
┌──(kali㉿kali)-[~]
└─$ ls
Desktop  message.txt
                                                                              
┌──(kali㉿kali)-[~]
└─$ code 
┏━(Message from Kali developers)
┃ code is not the binary you may be expecting.
┃ You are looking for \"code-oss\"
┃ Starting code-oss for you...
┗━
Warning: 'unity-launch' is not in the list of known options, but still passed to Electron/Chromium.
[main 2026-04-22T14:05:21.706Z] update#setState disabled
[main 2026-04-22T14:05:21.716Z] update#ctor - updates are disabled as there is no update URL
[11163:0422/100522.218499:ERROR:command_buffer_proxy_impl.cc(131)] ContextResult::kTransientFailure: Failed to send GpuControl.CreateCommandBuffer.
[11081:0422/100538.503110:ERROR:atom_cache.cc(229)] Add code/file-list to kAtomsToCache
[11081:0422/100709.117736:ERROR:atom_cache.cc(229)] Add WM_CHANGE_STATE to kAtomsToCache


# leemos el mensaje y quitamos espacios y dividimos en partes

data = open('message.txt','r').read().strip().split(' ')

  

print(data)

flag = ''

  

# recorremos el mensaje para decodificarlo

for c in data:

char = int(c) % 37

print(f'{c:<5} - {char:<5} - ',end='')

# mapeamos a letras en codigo ascii sumando 65

if char>=0 and char<=25:

s = chr(char+65)

# mapeamos a numeros en codigo ascii (48 - 26)

elif char>=26 and char<=35:

s= chr(char+22)

elif char==36:

s = '_'

flag += s

print(s)

print(f'\n{flag}')
picoCTF{R0UND_N_R0UND_79C18FB3}
```
## Notas adicionales 

## Referencias



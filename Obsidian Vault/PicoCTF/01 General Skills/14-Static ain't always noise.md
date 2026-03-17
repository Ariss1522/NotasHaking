Reto 
## Static ain't always noise
## Descripcion
Can you look at the data in this binary? The bash script might help![static](https://challenge-files.picoctf.net/c_wily_courier/b94bae11002f8fd650a028c91c0e5427b3122a0049c43a3ed483299b8d61665b/static), [ltdis.sh](https://challenge-files.picoctf.net/c_wily_courier/b94bae11002f8fd650a028c91c0e5427b3122a0049c43a3ed483299b8d61665b/ltdis.sh)
## Solucion
picoCTF{d15a5m_t34s3r_20335e41}
```
picoctf@webshell:~$ file *
README.txt: ASCII text, with escape sequences
ltdis.sh:   Bourne-Again shell script, ASCII text executable
static:     ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=9a00d4dca6b92d22aa0cd1fceffa4ed7495b8534, for GNU/Linux 3.2.0, not stripped
Aaxel0583-picoctf@webshell:~$ chmod +x ltdish.sh
chmod: cannot access 'ltdish.sh': No such file or directory
picoctf@webshell:~$ chmod +x ltdis.sh
Aaxel0583-picoctf@webshell:~$ ./ltdis.sh
Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
picoctf@webshell:~$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
Aaxel0583-picoctf@webshell:~$ cat static.ltdis.strings.txt | grep pico
   3020 picoCTF{d15a5m_t34s3r_20335e41}

```
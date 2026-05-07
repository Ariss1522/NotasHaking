# Reto 
## Based 
## Descripcion
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?Connect with nc fickle-tempest.picoctf.net 59863.
## Solucion
https://gchq.github.io/CyberChef/#recipe=From_Hex('None')&input=NzM3NDcyNjU2NTc0

https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)&input=IDAxMTEwMDExIDAxMTEwMTAwIDAxMTEwMDEwIDAxMTAwMTAxIDAxMTAwMTAxIDAxMTEwMTAw

```
picoctf@webshell:~$ nc fickle-tempest.picoctf.net 59863
Let us see how data is stored
street
Please give the 01110011 01110100 01110010 01100101 01100101 01110100 as a word.
...
you have 45 seconds.....

Input:
street
Please give me the  o163 o164 o162 o145 o145 o164 as a word.
Input:
street
Please give me the 737472656574 as a word.
Input:
street
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_6c3Fb625}
```

## Notas adicionales 
uso de binario,  octagenal y hexadecimal
## Referencias
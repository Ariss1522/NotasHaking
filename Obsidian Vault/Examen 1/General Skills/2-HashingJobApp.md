
# Reto 
### HashingJobApp
## Descripcion
If you want to hash with the best, beat this test!`nc saturn.picoctf.net 58385`
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 58385
Please md5 hash the text between quotes, excluding the quotes: 'chains'
Answer: 
Time's up. Press Ctrl-C to disconnect. Feel free to reconnect and try again.
                                                                             
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 58385
Please md5 hash the text between quotes, excluding the quotes: 'cleaning the bathroom'
Answer: 
f7754729f7de68402ab662edbceb3100
f7754729f7de68402ab662edbceb3100
Incorrect. Try again?
Answer: 
f7754729f7de68402ab662edbceb3100
f7754729f7de68402ab662edbceb3100
Incorrect. Goodbye. Better luck next time!
                                                                             
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 58385
Please md5 hash the text between quotes, excluding the quotes: 'mold'
Answer: 
0ad9f975892bdc82aa683146c002ffac
0ad9f975892bdc82aa683146c002ffac
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'flat tire'
Answer: 
a230e8cebf5c1e3041796ff021ff8a50 
a230e8cebf5c1e3041796ff021ff8a50 
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'baby showers'
Answer: 
2c236af2a631160e18ec35119418c5ff
2c236af2a631160e18ec35119418c5ff
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}
```
## Notas adicionales 
uso de echo y md5sum

```
ejemplo
└─$ echo -n "chains" | md5sum
99469f92ab96d54efce3d605a4bb4fbe
```
## Referencias




# Reto 
### Bookmarklet
## Descripcion
Why search for the flag when I can make a bookmarklet to print it for me?Browse [here](http://titan.picoctf.net:63138/), and find the flag!
## Solucion
```
allow pasting
        javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£Ö�ÓÚåÛÑ¢ÕÓ�Ô�ÅÐ�Ù�í";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();
        picoCTF{p@g3_turn3r_1d1ba7e0}
```
## Notas adicionales 
abrir consola de desarroladores, ir a consola y usar el codigo proporcionado 
## Referencias



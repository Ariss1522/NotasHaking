
# Reto 
### Irish-Name-Repo 1
## Descripcion
Do you think you can log us in? Try to see if you can login!http://fickle-tempest.picoctf.net:53762.
## Solucion
al usar admin' -- el servidor se confunde y omite la validacion de contraseña

```
SELECT * FROM users WHERE username = 'admin' --' AND password = 'TU_PASSWORD';
```
picoCTF{s0m3_SQL_85832275}



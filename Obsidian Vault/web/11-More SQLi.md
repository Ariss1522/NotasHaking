
# Reto 
### More SQLi
## Descripcion
Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:51127/).
## Solucion
se hace algo parecido que en la numero 10 confundir al servidor 

```
### 1. Vuelve a saltar la seguridad

Primero, necesitas entrar. En la pantalla de login, intenta usar una inyección clásica de autenticación que siempre evalúa como verdadera. En el campo de contraseña escribe:

SQL

 (' OR 1=1; --)




### 2. Encuentra el buscador vulnerable

Una vez adentro, seguramente verás un buscador o un panel donde puedes ingresar texto. Este nuevo campo también es vulnerable a inyección SQL, pero en lugar de evadir una validación, lo usaremos para concatenar nuestros propios resultados a los que la página nos muestra normalmente usando el operador `UNION`.

### 3. Descubre el número de columnas

Para usar `UNION`, nuestra consulta inyectada debe tener exactamente el mismo número de columnas que la consulta original del desarrollador. Empezaremos a adivinar inyectando esto en el buscador:

SQL


' UNION SELECT 1--


Si te da error, intenta con dos columnas:

SQL


' UNION SELECT 1, 2--


Sigue agregando números (`' UNION SELECT 1, 2, 3--`) hasta que la página cargue sin errores y te muestre esos números en la pantalla. Así sabrás cuántas columnas tienes disponibles para robar datos (casi siempre en estos retos de picoCTF son 3 columnas).

### 4. Extrae el mapa de la base de datos

Asumiendo que descubriste que son 3 columnas. Ahora necesitamos saber cómo se llaman las tablas secretas. En los retos web de picoCTF, el motor suele ser SQLite. Puedes pedirle a SQLite que te muestre su tabla maestra donde guarda todos los nombres de las tablas y columnas:

SQL


' UNION SELECT 1, 2, sql FROM sqlite_master WHERE type='table'--


_(Si los números que aparecieron en tu pantalla en el paso 3 fueron el 2 o el 3, pon la palabra `sql` en esa posición)._

### 5. Roba la bandera

Al ejecutar el paso anterior, la pantalla te mostrará la estructura de la base de datos. Busca entre ese texto una tabla con un nombre interesante (quizás se llame `more_table` o `flags`) y fíjate cómo se llama su columna (quizás `flag`).

Finalmente, inyecta la consulta para extraer ese dato específico:

SQL


' UNION SELECT 1, 2, flag FROM more_table--
|   |
|---|
|picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_3b0fca37}|
```




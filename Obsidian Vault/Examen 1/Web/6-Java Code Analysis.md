
# Reto 
### Java Code Analysis!?!
## Descripcion
BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/481/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:60297/).
## Solucion
```
inspeccionar pagina, ver el almacenamiento local, busar key y modificar permisos de usuario 
{
  "role": "Admin",
  "iss": "bookshelf",
  "exp": 1775163863,
  "iat": 1774559063,
  "userId": 2,
  "email": "Admin"
}

```
## Notas adicionales 

## Referencias

https://www.jwt.io
https://www.youtube.com/watch?v=tsTkxWxLTqk
# Reto 
### Cookies
## Descripcion
Who doesn't love cookies? Try to figure out the best one.http://wily-courier.picoctf.net:50466/
## Solucion
picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}

```
- Entra al enlace proporcionado (`http://wily-courier.picoctf.net:50466/`).
    
- Escribe `snickerdoodle` y dale a buscar.
    
- Abre las Herramientas de Desarrollador de tu navegador (Presiona `F12` o `Ctrl+Shift+I`).
    
- Ve a la pestaña **Application** (en Chrome/Brave) o **Storage** (en Firefox) y busca el apartado de **Cookies** en el menú de la izquierda.
    
- Haz clic en la URL del reto. Verás una cookie con el nombre `name` y un valor (como `0` o `-1`).
    
- Cambia ese valor a `1` y recarga la página. Luego a `2`, luego a `3`... y así sucesivamente.
    
- Alrededor del valor **18** (este suele ser el número en este reto), la página cambiará y te mostrará la bandera.
```


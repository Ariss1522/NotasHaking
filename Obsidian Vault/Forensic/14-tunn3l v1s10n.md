
# Reto 
### tunn3l v1s10n
## Descripcion
We found this file. Recover the flag.[tunn3l_v1s10n](https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n)
## Solucion
```


Este reto es una lección magistral sobre la estructura de los archivos de imagen de mapa de bits (BMP) y cómo las computadoras interpretan sus dimensiones. Un archivo BMP no es más que una larga lista de colores de píxeles, pero para que el sistema sepa cómo dibujarlos, necesita leer las "Cabeceras" (Headers) al principio del archivo. El creador del reto corrompió intencionalmente marcadores vitales en la cabecera y manipuló la altura registrada de la imagen para crear un efecto de "visión de túnel", ocultando la verdadera flag fuera de los límites de la pantalla renderizada.

**Paso 1: Identificación del formato real del archivo**

1. Al descargar el archivo `tunn3l_v1s10n`, este no tiene extensión. Si ejecutas el comando `file tunn3l_v1s10n` en tu terminal, Kali te dirá que simplemente son "datos" (`data`), lo que significa que la computadora no reconoce qué es.
    
2. Abre el archivo en el quirófano hexadecimal ejecutando: `hexeditor tunn3l_v1s10n`.
    
3. Observa los dos primeros bytes del archivo en la línea `00000000`. Verás los números hexadecimales **`42 4D`**.
    
4. Si miras la columna de texto a la derecha, esto se traduce como las letras **`BM`**. Estos son los "Magic Bytes" universales que indican que el archivo es, sin lugar a dudas, un archivo de imagen `.bmp`.
    

**Paso 2: Reparación del Offset de Píxeles (El primer `BA D0`)**

1. En la primera línea del archivo, busca la posición u "offset" `0A` (cuenta 10 pares de números desde el inicio).
    
2. Verás que el creador escribió la broma **`BA D0`** ("bad zero" / mal cero).
    
3. El offset `0A` le dice a la computadora _en qué byte exacto empiezan los píxeles de la imagen_. En un archivo BMP estándar, la cabecera principal mide 14 bytes y la cabecera secundaria (DIB) mide 40 bytes. 14 + 40 = 54.
    
4. El número 54 en hexadecimal es `36`. Como los procesadores leen de derecha a izquierda (Little Endian), debemos escribirlo como `36 00 00 00`.
    
5. Sobrescribe el `BA D0` ingresando **`36 00`**.
    

**Paso 3: Reparación de la Cabecera DIB (El segundo `BA D0`)**

1. En esa misma primera línea, avanza hasta la posición `0E` (14 pares de números desde el inicio).
    
2. Verás otro **`BA D0`**. Esta posición define el _tamaño de la cabecera secundaria_ (BITMAPINFOHEADER).
    
3. Como calculamos en el paso anterior, el tamaño estándar de esta cabecera es de 40 bytes.
    
4. El número 40 en hexadecimal es `28`.
    
5. Sobrescribe ese segundo `BA D0` ingresando **`28 00`**.
    
6. Guarda con `Ctrl + X` e `y`. Renombra el archivo en tu terminal con `mv tunn3l_v1s10n imagen.bmp`. Si la abres, verás una imagen con un señuelo que dice `notaflag{...}`.
    

**Paso 4: Curar la "Visión de Túnel" alterando la altura**

1. El señuelo nos indica que la imagen ya es legible, pero estamos sufriendo de "visión de túnel". La imagen original fue recortada alterando los metadatos de su altura.
    
2. Vuelve a abrir la imagen: `hexeditor imagen.bmp`.
    
3. Baja hasta la línea `00000010`. En la posición `16` (que controla la altura de la imagen en píxeles), verás los bytes **`32 01`**.
    
4. Leyendo esto en Little Endian, el valor real es `01 32`, lo que equivale a unos 306 píxeles de altura. ¡La imagen es muy bajita!
    
5. Para revelar lo que hay "más arriba" en el archivo de datos, necesitamos hacer el lienzo más alto. Vamos a cambiar ese `01` por un `03` para darle casi el triple de altura (818 píxeles).
    
6. Posiciona tu cursor sobre el `01` y sobrescríbelo para que la secuencia quede como **`32 03`**.
    
7. Guarda los cambios y sal del editor (`Ctrl + X`, `y`).
    

**Paso 5: Revelación final**

1. Vuelve a abrir `imagen.bmp` usando tu gestor de archivos o el comando `xdg-open imagen.bmp`.
    
2. El sistema operativo leerá las nuevas instrucciones, renderizará un lienzo mucho más alto y procesará los píxeles que antes estaban "escondidos" fuera del marco superior.
    
3. En la nueva sección descubierta en la parte superior de la imagen, aparecerá la verdadera flag del reto claramente legible.
picoCTF{qu1t3_a_v13w_2020}
```
## Notas adicionales 

## Referencias



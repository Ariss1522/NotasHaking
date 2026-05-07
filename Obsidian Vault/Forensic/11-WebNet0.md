
# Reto 
### WebNet0
## Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/picopico.key). Recover the flag.
## Solucion
```

El reto consiste en descifrar tráfico de red capturado que está protegido por encriptación TLS (Transport Layer Security). Normalmente, este tráfico es ilegible y se ve como texto cifrado o basura. Sin embargo, al poseer la clave privada RSA del servidor (el archivo `.key`), es posible configurar el analizador de paquetes para que revierta el cifrado matemáticamente usando esa llave y revele el tráfico web HTTP original en texto claro.

**Paso 1: Preparación del entorno y apertura de la captura**

1. Descarga los dos archivos proporcionados por el reto: `capture.pcap` (la grabación del tráfico de red) y el archivo `.key` (la clave privada RSA del servidor).
    
2. Abre la terminal en Kali Linux y ejecuta `wireshark` para abrir el programa.
    
3. Ve al menú superior **File** (Archivo) -> **Open** (Abrir) y selecciona el archivo `capture.pcap`.
    
4. Al cargarlo, notarás que la columna "Protocol" muestra principalmente paquetes etiquetados como **TLSv1.2**. Si seleccionas uno y miras su contenido en la ventana inferior, solo verás "Application Data" ilegible porque está encriptado.
    

**Paso 2: Ubicar las configuraciones de descifrado en Wireshark**

1. Dirígete al menú superior y haz clic en **Edit** (Editar).
    
2. En el menú desplegable, selecciona **Preferences** (Preferencias), ubicado hasta abajo.
    
3. En la nueva ventana, busca en el panel izquierdo la categoría **Protocols** (Protocolos) y haz clic en la pequeña flecha para expandir la lista (es bastante larga).
    
4. Desplázate hacia abajo alfabéticamente hasta encontrar el protocolo **TLS**. (Nota: En versiones antiguas de Wireshark, debes buscarlo bajo el nombre **SSL**). Selecciónalo haciendo clic sobre su nombre.
    

**Paso 3: Inyección de la clave privada RSA**

1. Una vez seleccionado TLS, busca en el panel derecho la sección que dice **RSA keys list** (Lista de claves RSA).
    
2. Haz clic en el botón **Edit...** (Editar...) que está junto a esa opción.
    
3. Se abrirá una pequeña ventana. Haz clic en el botón con el símbolo **"+"** (Añadir) en la esquina inferior izquierda para crear una nueva regla de descifrado.
    
4. Llena los campos de la tabla exactamente de la siguiente manera:
    
    - **IP address:** Escribe la palabra `any`. Esto le indica al programa que intente descifrar el tráfico sin importar de qué dirección IP provenga.
        
    - **Port:** Escribe `443`. Este es el puerto estándar mundial para el tráfico web seguro (HTTPS).
        
    - **Protocol:** Escribe `http`. Esto le dice a Wireshark que, una vez que logre quitar la capa de seguridad TLS, el texto que encontrará debajo está en formato web HTTP.
        
    - **Key File:** Haz clic en el botón "Browse..." y selecciona el archivo `.key` que descargaste del reto.
        
5. Haz clic en **OK** en esa pequeña ventana, y luego en **OK** en la ventana principal de Preferencias para aplicar y guardar los cambios.
    

**Paso 4: Filtrado del tráfico revelado**

1. Inmediatamente después de aplicar la clave, Wireshark reprocesará la captura de red en tiempo real.
    
2. Ve a la barra de filtros en la parte superior de la pantalla, escribe `http` (en minúsculas) y presiona Enter.
    
3. Esto ocultará todo el ruido de la red y solo te mostrará las peticiones web que ahora son legibles gracias a tu llave.
    
4. Empezarás a ver paquetes que dicen `GET / HTTP/1.1` y respuestas del servidor que dicen `HTTP/1.1 200 OK`.
    

**Paso 5: Inspección del flujo HTTP y obtención de la Flag**

1. Haz clic derecho sobre el primer paquete que veas con la petición `GET / HTTP/1.1`.
    
2. En el menú desplegable, selecciona **Follow** (Seguir) y luego **HTTP Stream** (Flujo HTTP).
    
3. Se abrirá una ventana nueva mostrando la conversación completa en texto claro entre el navegador del cliente (texto rojo) y el servidor web (texto azul).
    
4. Lee detenidamente las líneas iniciales del texto azul (estas son las cabeceras de respuesta del servidor).
    
5. Entre información técnica como el "Server", "Date" y "Content-Type", encontrarás una cabecera HTTP personalizada insertada por el creador del reto llamada `Pico-Flag:`.
    
6. Justo al lado de esa cabecera estará tu flag completa lista para copiar.
picoCTF{nongshim.shrimp.crackers}
```
## Notas adicionales 

## Referencias



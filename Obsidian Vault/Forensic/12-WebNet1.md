
# Reto 
###  WebNet1
## Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/picopico.key). Recover the flag.
## Solucion
```


Este reto combina dos disciplinas del análisis forense: el análisis de tráfico de red (Network Forensics) y la esteganografía/análisis de metadatos. Primero, requiere vulnerar la capa de seguridad TLS utilizando una clave privada filtrada para exponer el tráfico en texto claro. Una vez descifrado, demuestra cómo los atacantes (o en este caso, el creador del reto) pueden aprovechar la transferencia de archivos multimedia comunes a través de la red para ocultar información confidencial (la verdadera flag), dejando información falsa a simple vista para despistar a los analistas menos curiosos.

**Paso 1: Preparación del entorno y desencriptación del tráfico TLS**

1. Abre tu terminal y ejecuta `wireshark` para iniciar la interfaz gráfica.
    
2. Ve a **File** (Archivo) -> **Open** (Abrir) y selecciona el archivo `capture.pcap` correspondiente a este reto.
    
3. Para desencriptar el tráfico, dirígete al menú **Edit** (Editar) -> **Preferences** (Preferencias).
    
4. En el panel izquierdo, despliega la lista de **Protocols** (Protocolos), baja hasta la letra "T" y selecciona **TLS** (o **SSL** en versiones más antiguas).
    
5. En el panel derecho, localiza la sección **RSA keys list** (Lista de claves RSA) y haz clic en **Edit...** (Editar...).
    
6. Haz clic en el botón **"+"** para agregar una nueva regla y configúrala así:
    
    - **IP address:** `any`
        
    - **Port:** `443`
        
    - **Protocol:** `http`
        
    - **Key File:** Selecciona el archivo `.key` de este reto.
        
7. Haz clic en **OK** en ambas ventanas para aplicar el descifrado al instante.
    

**Paso 2: Análisis del tráfico y detección del señuelo**

1. En la barra de filtros superior de Wireshark, escribe `http` y presiona Enter. Esto aislará todas las peticiones web que ahora son legibles.
    
2. Identifica el primer paquete con la instrucción `GET / HTTP/1.1`, haz clic derecho sobre él y selecciona **Follow** (Seguir) -> **HTTP Stream** (Flujo HTTP).
    
3. En la ventana que se abre, inspecciona las cabeceras de respuesta del servidor (texto azul).
    
4. Encontrarás la cabecera personalizada `Pico-Flag:`, tal como en el reto anterior. Sin embargo, su valor es `picoCTF{this.is.not.your.flag.anymore}`. El creador del reto ha dejado un señuelo intencional para obligarte a buscar más a fondo. Cierra la ventana del flujo.
    

**Paso 3: Extracción forense de archivos de la red (Export Objects)**

1. Sabiendo que el servidor transfirió más datos además de texto, vamos a extraer los archivos que viajaron por la red.
    
2. En el menú superior principal, ve a **File** (Archivo) -> **Export Objects** (Exportar objetos) -> **HTTP...**
    
3. Se abrirá una ventana listando todos los archivos transferidos. Entre ellos, destaca una imagen llamada `vulture.jpg`.
    
4. Haz clic en el botón **Save All** (Guardar todo). Para mantener el orden de tu entorno, crea una carpeta nueva llamada `webnet1_files` y guarda los objetos ahí.
    

**Paso 4: Análisis del archivo extraído y obtención de la Flag real**

1. Cierra Wireshark, abre tu terminal y navega hasta la carpeta que acabas de crear usando el comando `cd`.
    
2. Vamos a inspeccionar la imagen. En lugar de intentar abrirla visualmente, utilizaremos el comando `strings`, el cual extrae todas las cadenas de texto imprimibles (ASCII) que estén ocultas dentro del código binario o en los metadatos de cualquier archivo.
    
3. Para no tener que leer miles de líneas de basura generada por la imagen, filtraremos la salida directamente buscando el formato de la flag mediante un "pipe" (`|`) y el comando `grep`. Ejecuta:
    
    Bash
    
    ```
    strings vulture.jpg | grep picoCTF
    ```
    
4. La terminal procesará la imagen y te devolverá únicamente la línea de texto que coincide con tu búsqueda, revelando la verdadera flag del reto.
picoCTF{honey.roasted.peanuts}

```
## Notas adicionales 

## Referencias



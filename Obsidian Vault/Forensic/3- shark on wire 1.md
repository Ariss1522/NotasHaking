
# Reto 
### shark on wire 1
## Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap). Recover the flag.
## Solucion
```
Solucion

El reto se resuelve analizando un archivo de captura de tráfico de red (PCAP) para extraer información transmitida en texto plano a través de paquetes UDP.

Pasos de resolución:

1. Apertura del archivo:
    
    Se abrió el archivo proporcionado utilizando el analizador de protocolos de red Wireshark.
    
2. Análisis de tráfico:
    
    Al observar la lista de paquetes, se identificó que la comunicación principal se realizaba utilizando el protocolo UDP.
    
3. Seguimiento de flujos:
    
    Se seleccionó uno de los paquetes UDP y se utilizó la función Follow UDP Stream (Seguir flujo UDP) para reconstruir y leer el contenido completo de la conversación de red en lugar de revisar la información paquete por paquete.
    
4. Obtención de la flag:
    
    Desde la ventana del flujo reconstruido, se navegó secuencialmente por las diferentes conversaciones (cambiando el número de Stream en la parte inferior de la ventana) hasta localizar el flujo específico que contenía la flag transmitida en texto claro.
picoCTF{StaT31355_636f6e6e}
```
## Notas adicionales 

## Referencias



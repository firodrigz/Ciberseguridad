Herramienta de línea de comandos para rastrear redes.

Examinemos una línea de una salida de ejemplo:

```markup
20:58:26.765637 IP 10.0.0.50.80 > 10.0.0.1.53181: Flags [F.], seq 1, ack 2, win 453, options [nop,nop,TS val 3822939 ecr 249100129], length 0
```

Cada línea incluye

- Marca de tiempo de Unix (`20:58:26.765637`)
- protocolo (IP)
- el nombre de host o IP de origen y el número de puerto (`10.0.0.50.80`)
- nombre de host o IP de destino y número de puerto (`10.0.0.1.53181`)
- Banderas TCP (`Flags [F.]`). Banderas indiasate el state de la conexión. Esto puede incluir más de un valor, como en este ejemplo [F.] para FIN-ACK. Este campo puede tener los siguientes valores:
    - S - SYN. El primer paso para establecer la conexión.
    - F - FIN. Terminación de la conexión.
    - . - ACK. Paquete de acuse de recibo recibido correctamente.
    - P – EMPUJAR. Le dice al receptor que process paquetes en lugar de buffering ellos.
    - R - RST. La comunicación se detuvo.
- Número de secuencia de los datos del paquete. (`seq 1`)
-  Número de acuse de recibo (`ack 2`)
- Window tamaño (`win 453`). El número de bytes disponibles en el receptor. buffer. A esto le siguen las opciones de TCP.
- Longitud de la carga útil de datos. (`length 0`)


## Uso 

```markup
# tcpdump -i eth1
```

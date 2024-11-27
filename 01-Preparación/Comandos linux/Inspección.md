#### LSPCI

Muestra todos los dispositivos actualmente conectados al bus PCI (Peripheral Component
Interconnect).

``` bash
lspci 
```

El comando lspci muestra más detalles
sobre un dispositivo específico si su dirección se da con la opción -s, acompañada de la opción -v:

``` bash
$ lspci -s 04:02.0 -v
```

La opción -k, disponible en versiones más recientes de lspci, proporciona otra forma de verificar qué módulo del núcleo del sistema operativo está en uso para el dispositivo especificado:
``` bash
$ lspci -s 01:00.0 -k
```

#### LSUSB

Enumera los dispositivos USB (Universal Serial Bus) actualmente conectados a la máquina.

``` bash
lsusb
```

El comando lsusb muestra los canales USB disponibles y los dispositivos conectados a ellos. Al igual que con lspci, la opción -v muestra una salida más detallada. Se puede seleccionar un dispositivo específico para inspección proporcionando su ID a la opción -d:

```bash
$ lsusb -v -d 1781:0c9f
```

Enumera información detallada sobre las CPU encontradas por el sistema operativo.
``` bash
/proc/cpuinfo
```

Una lista de números de las interrupciones por dispositivo de entrada/salida para cada CPU.
``` bash
/proc/interrupts
```

Enumera los puertos de entrada/salida registrados actualmente en uso.
``` bash
/proc/ioports
```

Enumera los canales DMA (acceso directo a memoria) registrados en uso.
``` bash
/proc/dma
```



ARP es lo que necesita para asignar direcciones IPv4 a direcciones MAC.

- **Dirección MAC de destino** - La dirección MAC Ethernet del dispositivo de destino en el mismo segmento de red local. Si el host de destino está en otra red, entonces la dirección de destino en el trama sería la del gateway predeterminado (es decir, router).
- **Dirección MAC de origen** - La dirección MAC de la NIC de Ethernet en el host de origen.

Si el dispositivo localiza la dirección IPv4, se utiliza la dirección MAC correspondiente como la dirección MAC de destino de la trama. Si no se encuentra ninguna entrada, el dispositivo envía una solicitud de ARP.

lo hace con una mac destino FF-FF-FF-FF-FF-FF

Externo

![[Pasted image 20240221010351.png]]


Para cada dispositivo, un temporizador de memoria caché ARP elimina las entradas de ARP que no se hayan utilizado durante un período especificado. Los tiempos varían según el sistema operativo del dispositivo. Por ejemplo, los sistemas operativos Windows más recientes almacenan entradas de tabla ARP entre 15 y 45 segundos

![[Pasted image 20240221010530.png]]


![[Pasted image 20240221010612.png]]




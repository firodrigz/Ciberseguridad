Estándar 802.3
Utiliza direcciones MAC para redireccionamiento.

Ethernet utiliza comunicaciones por cable, incluyendo pares trenzados, enlaces de fibra óptica y cables coaxiales.
Ethernet funciona en la capa de enlace de datos y en la capa física. Es una familia de tecnologías de redes definidas en los estándares IEEE 802.2 y 802.3.

Funcionan en medio dúplex (CSMA/CD para colisiones,  sólo un dispositivo esté transmitiendo a la vez) y full dúplex

---
Subcapa MAC: es responsable de la encapsulación de datos y el acceso a los medios (tipos de medios, incluyendo cobre y fibra). 


Dirección MAC de Unidifusión: se utiliza cuando se envía una trama desde un único dispositivo de transmisión a un único dispositivo de destino.
![[Pasted image 20240212200817.png]]

Dirección MAC de Difusión: 
- Tiene una dirección MAC de destino de FF-FF-FF-FF-FF-FF en hexadecimal (48 unidades en binario).
- Se inunda hacia todos los puertos del conmutador Ethernet excepto el puerto entrante.
- No es reenviada por un enrutador.
- 255 en hosts.

![[Pasted image 20240212200756.png]]

Dirección MAC de Multidifusión: 

- Hay una dirección MAC de destino 01-00-5E cuando los datos encapsulados son un paquete de multidifusión IPv4 y una dirección MAC de destino de 33-33 cuando los datos encapsulados son un paquete de multidifusión IPv6.
- Existen otras direcciones MAC de destino de multicast reservadas para cuando los datos encapsulados no son IP, como Spanning Tree Protocol (STP) y Link Layer Discovery Protocol (LLDP).
- Se inundan todos los puertos del conmutador Ethernet excepto el puerto entrante, a menos que el conmutador esté configurado para la indagación de multidifusión.
- No es reenviado por un enrutador, a menos que el enrutador esté configurado para enrutar paquetes de multidifusión.

El intervalo de direcciones IPv4 de multidifusión va de 224.0.0.0 a 239.255.255.255. El rango de direcciones de multicast IPv6 comienza con ff00 :: / 8.

![[Pasted image 20240212202712.png]]

[[Tablas direcciones MAC]]
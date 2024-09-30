
Capa 7 - Aplicación: Funciona con aplicaciones proporcionando interfaz con el fin de transmitir datos.

Capa 6 - Presentación: se encarga de estandarizar los datos recibidos para que la capa de aplicación receptora pueda entenderlos. También gestiona cifrado, compresión u otras transformaciones de los datos.

Capa 5 - Sesión: Se compueba si se puede hacer una conexión con el destino a través de la red, si se puede SU OBJETIVO ES mantener dicha conexión y cooperar con la capa de sesión del destino para sincronizar las comunicaciones. La sesión de comunicación creada es única, permitiendo de esta manera hacer múltiples solicitudes sin que los datos se mezclen.

Capa 4 - Transporte: Elije protocolo por el que se transmiten los datos ([[TCP (Capa transporte)]], [[UDP (Capa transporte)]] + IMPORTANTES). Segmente la información segmentos (TCP), datagramas (UDP).

Capa 3 - Red: Direccionamiento lógico. Se encarga de localizar el destino de la solicitud. Interviene el protocolo [[IP (Capa red)]]. Información en paquetes.

Capa 2 - Enlace de datos: Direccionamiento físico. Toma el paquete con la IP agregada en la capa 3 y le agrega la dirección física (MAC) del destino. Verifica la información recibida para asegurarse de que no se haya dañado durante la transmisión. Información en frames.

Capa 1 - Físico: Hardware. Se envían y reciben pulsos eléctricos que componen la transferencia de datos. Convierte los datos binarios de la transmisión en señales y transmitirlos a través de la red, así como recibir señales entrantes y convertirlas de nuevo en datos binarios.

## Encapsulación de datos

![[Pasted image 20240215010517.png]]

Los paquetes IP pueden trasladarse a través de diferentes medios.
 IP no tiene la funcionalidad de retransmitir paquetes si se producen errores.
 IP es como la analogía del cartero, no envía un aviso previo de que va a llegar un nuevo mensaje.
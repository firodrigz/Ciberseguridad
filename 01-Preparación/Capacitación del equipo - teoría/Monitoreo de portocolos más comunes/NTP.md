### NTP

Los mensajes de syslog suelen tener marca de hora, es importante que los dispositivos compartan un reloj único. El NTP funciona en el puerto UDP 123.
Dado que los eventos conectados a un ataque pueden dejar rastros en cada dispositivo de la red mientras recorren su camino al sistema de destino, las marcas de tiempo son esenciales para la detección. Los agentes de amenaza pueden intentar atacar la infraestructura de NTP para dañar la información horaria utilizada para correlacionar los eventos registrados de la red. Esto puede servir para ocultar rastros de ataques en curso. Además, se han conocido agentes de amenaza que utilizan sistemas de NTP para dirigir ataques de DDoS aprovechando vulnerabilidades en el software del cliente o del servidor. Mientras que estos ataques no necesariamente dañan los datos de monitoreo de seguridad, pueden interrumpir la disponibilidad de la red.

![NTP](https://i.postimg.cc/9FYk00xz/NTP.png)
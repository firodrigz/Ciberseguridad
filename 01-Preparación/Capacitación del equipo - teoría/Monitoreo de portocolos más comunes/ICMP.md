ICMP puede emplearse para identificar los hosts de una red o la estructura de una red, y determinar los sistemas operativos utilizados en la red. También puede usarse como vehículo para varios tipos de ataques de DoS y la exfiltración de datos.

Se ejemplifica el uso de [[Listas de control de acceso (ACL)]] para autorizar solamente determinados tipos de tráfico de protocolo de mensajería de control de Internet (ICMP). El servidor en 192.168.1.10 forma parte de la red interna y tiene permitido enviar solicitudes de ping al host externo en 209.165.201.3. El tráfico ICMP de retorno del host externo está autorizado si se trata de una respuesta de ICMP, un mensaje source quench (le indica al origen que reduzca el ritmo del tráfico) o cualquier mensaje de ICMP inalcanzable. Todos los demás tipos de tráfico de ICMP se niegan. Por ejemplo, el host externo no puede iniciar una solicitud de ping al host interno. La ACL de salida autoriza los mensajes de ICMP que informan diversos tipos de problemas. Esto permite la tunelización de ICMP y la exfiltración de datos.

![Mitigar abuso ICMP](https://i.postimg.cc/L8Dxc799/mitigarabusoicmp.png)

Para permitir un tráfico adecuado y seguro en una red, un ciberanalista que está revisando una Lista de Control de Acceso (ACL) de punto de entrada debe considerar qué tipos de tráfico ICMP (Protocolo de Mensajes de Control de Internet) permitir desde Internet hacia la red interna. ICMP es crucial para diversas funciones de diagnóstico y control en redes IP.

Las tres opciones más comunes y necesarias de tráfico ICMP que deberían permitirse son:

1. **Echo Reply (Respuesta de eco)**: Este tipo de mensaje es la respuesta a una solicitud de eco (ping). Permitir este tipo de tráfico es importante para las herramientas de diagnóstico de red, como el comando `ping`, que verifica la conectividad entre dispositivos.

2. **Destination Unreachable (Destino inalcanzable)**: Este mensaje se envía cuando un paquete no puede ser entregado a su destino. Es esencial permitir este tráfico para que los dispositivos sepan si el destino es inaccesible y para diagnosticar problemas de red.

3. **Time Exceeded (Tiempo excedido)**: Este mensaje se usa para informar que el tiempo de vida (TTL) de un paquete ha expirado, generalmente utilizado por herramientas de rastreo de rutas como `traceroute`. Permitir estos mensajes ayuda a diagnosticar problemas de rutas y a comprender la topología de la red.

Aquí hay una explicación más detallada de cada uno:

1. **Echo Reply (Respuesta de eco)**:
   - **Propósito**: Confirmar que un host está operativo y que hay conectividad entre dos puntos en la red.
   - **Uso típico**: Responder a una solicitud de eco (`ping`).

2. **Destination Unreachable (Destino inalcanzable)**:
   - **Propósito**: Informar al remitente que un paquete no pudo ser entregado a su destino por varias razones, como red inalcanzable, host inalcanzable, protocolo inalcanzable o puerto inalcanzable.
   - **Uso típico**: Diagnosticar problemas en la entrega de paquetes.

3. **Time Exceeded (Tiempo excedido)**:
   - **Propósito**: Informar que el TTL (Tiempo de Vida) de un paquete ha expirado, lo cual puede ocurrir si un paquete queda atrapado en un bucle o si la ruta hacia el destino es demasiado larga.
   - **Uso típico**: Utilizado por `traceroute` para determinar la ruta de los paquetes a través de la red.

Estos tres tipos de tráfico ICMP son fundamentales para el diagnóstico y la resolución de problemas en redes, por lo que se recomienda permitirlos a través de las ACLs en un entorno seguro controlado.
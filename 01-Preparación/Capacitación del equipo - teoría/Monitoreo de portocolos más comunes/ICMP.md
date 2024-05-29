ICMP puede emplearse para identificar los hosts de una red o la estructura de una red, y determinar los sistemas operativos utilizados en la red. También puede usarse como vehículo para varios tipos de ataques de DoS y la exfiltración de datos.

Se ejemplifica el uso de ACL para autorizar solamente determinados tipos de tráfico de protocolo de mensajería de control de Internet (ICMP). El servidor en 192.168.1.10 forma parte de la red interna y tiene permitido enviar solicitudes de ping al host externo en 209.165.201.3. El tráfico ICMP de retorno del host externo está autorizado si se trata de una respuesta de ICMP, un mensaje source quench (le indica al origen que reduzca el ritmo del tráfico) o cualquier mensaje de ICMP inalcanzable. Todos los demás tipos de tráfico de ICMP se niegan. Por ejemplo, el host externo no puede iniciar una solicitud de ping al host interno. La ACL de salida autoriza los mensajes de ICMP que informan diversos tipos de problemas. Esto permite la tunelización de ICMP y la exfiltración de datos.

![Mitigar abuso ICMP](https://i.postimg.cc/L8Dxc799/mitigarabusoicmp.png)


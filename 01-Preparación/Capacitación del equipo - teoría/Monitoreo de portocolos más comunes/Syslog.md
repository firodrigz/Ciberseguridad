### Syslog

El estándar syslog se usa para registrar mensajes de eventos provenientes de terminales y dispositivos de red. El estándar habilita un medio independiente del sistema para transmitir, almacenar y analizar mensajes. Muchos tipos de dispositivos de muchos proveedores diferentes pueden utilizar syslog para enviar entradas del registro a servidores centrales que ejecutan un daemon de syslog. Esta centralización de la recopilación de registros ayuda a poner en práctica el monitoreo de la seguridad. Los servidores que ejecutan syslog suelen escuchar en el puerto UDP 514.

![Syslog](https://i.postimg.cc/T3TZJgyr/syslog.png)

Los hackers pueden intentar bloquear la transferencia de datos de los clientes syslog a los servidores. Pueden alterar o destruir datos de registro o el software que crea y transmite los mensajes de registro. La siguiente generación de implementación de syslog, conocida como syslog-ng, ofrece mejoras que pueden ayudar a evitar algunos de los ataques cuyo objetivo es syslog.
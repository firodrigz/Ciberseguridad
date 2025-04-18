Los protocolos de correo electrónico, como **SMTP, POP3** e **IMAP**, pueden usarse para propagar malware, exfiltrar datos u ofrecer canales a servidores de CnC de malware

El **SMTP envía datos** desde un host hacia un servidor de correo y entre servidores de correo. Al igual que DNS y HTTP, es un protocolo común que suele verse saliendo de la red. Dado que hay tanto tráfico de SMTP, no siempre se monitorea. Sin embargo, el malware ha usado el SMTP en el pasado para exfiltrar datos de la red.

**IMAP y POP3 se usan para descargar mensajes de correo electrónico de un servidor de correo** a una computadora host. Por esto, son los protocolos de aplicaciones responsables de traer malware al host. El monitoreo de la seguridad puede identificar cuándo ingresa un archivo adjunto con malware en la red y qué host se infecta primero. Luego, el análisis retrospectivo puede rastrear el comportamiento del malware desde ese momento. De esta manera, puede entenderse mejor el comportamiento del malware y se puede identificar la amenaza. Las herramientas de monitoreo de seguridad pueden también permitir la recuperación de archivos adjuntos infectados para enviarlos a sandbox de malware para su análisis.

Actualmente se utiliza más IMAP como protocolo de recepción de correos electrónicos gracias a su capacidad de sincronización, gestión, accesos y estado de correos.

![Correo electronico](https://i.postimg.cc/MG3XVDjC/ce.png)
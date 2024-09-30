Los protocolos de capa de transporte especifican cómo transferir mensajes entre hosts y son responsables de administrar los requisitos de fiabilidad de una conversación. La capa de transporte incluye los protocolos TCP y UDP.

IP solo se refiere a la estructura, direccionamiento y enrutamiento de paquetes, desde el remitente original hasta el destino final. IP no es responsable de garantizar la entrega o determinar si es necesario establecer una conexión entre el remitente y el receptor.

El TCP se considera un protocolo de la capa de transporte confiable y completo, que garantiza que todos los datos lleguen al destino. TCP incluye campos que garantizan la entrega de los datos de la aplicación. Estos campos requieren un procesamiento adicional por parte de los hosts de envío y recepción.

**Nota:** TCP divide los datos en segmentos.

TCP, primero debe formar una conexión estable entre las dos computadoras. El proceso de formación de esta conexión se denomina _apretón de manos de tres vías_.

1. Cuando intenta establecer una conexión, su computadora primero envía una solicitud especial al servidor remoto indicando que desea inicializar una conexión. Esta solicitud contiene algo llamado bit _SYN_ (abreviatura de _sincronización_), que esencialmente hace el primer contacto al iniciar el proceso de conexión.
2. A continuación, el servidor responderá con un paquete que contiene el bit SYN, así como otro bit de "acuse de recibo", llamado _ACK_.
3. Finalmente, su computadora enviará un paquete que contiene el bit ACK por sí mismo, confirmando que la conexión se ha configurado correctamente.

![[Pasted image 20240308185329.png]]


TCP proporciona confiabilidad y control de flujo mediante estas operaciones básicas:

- Numerar y rastrear segmentos de datos transmitidos a un host específico desde una aplicación específica
- Confirmar acuses de recibidos
- Vuelver a transmitir cualquier información no reconocida después de un cierto período de tiempo
- Control de flujo
- Datos de secuencia que pueden llegar en un orden incorrecto
- Enviar datos a una velocidad eficiente que sea aceptable por el receptor

## Aplicaciones que usan TCP

- FTP
- SMTP
- HTTP
- SSH

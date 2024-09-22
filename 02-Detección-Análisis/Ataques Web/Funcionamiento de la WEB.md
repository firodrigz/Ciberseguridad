# Solicitudes HTTP

Se utiliza para recuperar un recurso de un servidor Web.

![requesthttp](https://i.postimg.cc/brBPtyQx/requesthttp.png)

- El encabezado "Upgrade-Insecure-Requests" indica que el cliente desea comunicarse mediante cifrado (SSL).
- El encabezado "User-Agent" contiene información sobre el navegador y el sistema operativo del cliente. Los servidores web utilizan esta información para enviar respuestas HTTP específicas al cliente. Puede encontrar algunos escáneres de vulnerabilidades automatizados mirando debajo de este encabezado.
- El tipo de datos solicitados se encuentra en el encabezado "Aceptar".
- El tipo de codificación aceptada por el cliente se encuentra en el encabezado "Accept-Encoding". Por lo general, puede encontrar los nombres de los algoritmos de compresión en este encabezado.
- El encabezado "Accept-Language" contiene la información de idioma del cliente. El servidor web utiliza esta información para mostrar el contenido preparado en el idioma del cliente.
- El encabezado "Conexión" muestra cómo se realiza la conexión HTTP. Si hay datos como "cerrar", significa que la conexión TCP se cerrará después de recibir la respuesta HTTP. Si ve "keep-alive", esto significa que la conexión se mantendrá.
- Se inserta una línea vacía entre el encabezado de la solicitud HTTP y el cuerpo del mensaje de solicitud HTTP para crear una partición.
- Cualquier otro dato que se envíe a la aplicación web se encuentra en el cuerpo del mensaje de solicitud. Si se utiliza el método HTTP POST, los parámetros POST se pueden encontrar aquí.

# Respuestas HTTP
Cuando el servidor web recibe una solicitud HTTP, realiza las comprobaciones y procesos necesarios y, a continuación, envía el recurso solicitado al cliente.

![responsehttp](https://i.postimg.cc/dVTVdVqQ/responsehttp.png)

### Línea de estado
La línea de estado contiene información sobre la versión HTTP y el código de estado de respuesta HTTP. El código de estado de respuesta HTTP se utiliza para describir el estado de la solicitud. Hay muchos códigos de estado de respuesta HTTP, pero se pueden resumir de la siguiente manera:

- **100-199**: Respuestas informativas
- **200-299**: Respuestas exitosas
- **300-399**: Mensajes de redireccionamiento
- **400-499**: Respuestas de error del cliente
- **500-599**: Respuestas de error del servidor
  
### Encabezados de respuesta
Estos son algunos encabezados de respuesta HTTP que puede encontrar con frecuencia:

- **Fecha**: La hora exacta en que el servidor envió la respuesta HTTP al cliente.
- **Conexión**: Indica cómo se maneja la conexión, al igual que el encabezado de la solicitud HTTP.
- **Servidor: Informa** sobre el sistema operativo del servidor y la versión del servidor web.
- **Última modificación**: Proporciona información sobre cuándo se modificó el recurso solicitado. Este encabezado es utilizado por el mecanismo de almacenamiento en caché.
- **Tipo de contenido**: El tipo de datos que se envían.
- **Content-Length**: El tamaño de los datos enviados.

### Cuerpo de la respuesta
El cuerpo de la respuesta HTTP contiene el recurso enviado por el servidor y solicitado por el cliente.


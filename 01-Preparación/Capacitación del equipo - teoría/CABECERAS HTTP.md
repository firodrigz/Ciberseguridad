``` bash
curl -v google.com -> permite ver cabeceras
```

[Los encabezados generales](https://www.w3.org/Protocols/rfc2616/rfc2616-sec4.html) se utilizan tanto en las solicitudes HTTP como en las respuestas. Son contextuales y están acostumbrados a `describe the message rather than its contents`.

| **Encabezador** | **Ejemplo**                           | **Descripción**                                                                                                                                                                                                                                                                                                                                                                         |
| --------------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Date`          | `Date: Wed, 16 Feb 2022 10:38:44 GMT` | Sostuvierse la fecha y hora en que se originó el mensaje. Se prefiere convertir el tiempo a la zona horaria [estándar de UTC](https://en.wikipedia.org/wiki/Coordinated_Universal_Time).                                                                                                                                                                                                |
| `Connection`    | `Connection: close`                   | Dictúa si la conexión de red actual debe mantenerse viva después de que la solicitud termine. Dos valores de uso común para esta cabecera son `close`y `keep-alive`. El `close`valor del cliente o del servidor significa que les gustaría cancelar la conexión, mientras que el `keep-alive`cabecera indica que la conexión debe permanecer abierta para recibir más datos y entradas. |

-----
## Cabeceras de la entidad

Similar a los encabezados generales, [los titulares](https://www.w3.org/Protocols/rfc2616/rfc2616-sec7.html) de [la Entidad](https://www.w3.org/Protocols/rfc2616/rfc2616-sec7.html) pueden ser `common to both the request and response`. Estas cabeceras están acostumbradas a `describe the content`(entidad) transferida por un mensaje. Por lo general se encuentran en las respuestas y peticiones de POST o PUT.

| **Encabezador**    | **Ejemplo**                   | **Descripción**                                                                                                                                                                                                                                                                                  |
| ------------------ | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `Content-Type`     | `Content-Type: text/html`     | Se utiliza para describir el tipo de recurso que se transfiere. El valor es añadido automáticamente por los navegadores en el lado del cliente y devuelto en la respuesta del servidor. El `charset`campo denota el estándar de codificación, como [UTF-8](https://en.wikipedia.org/wiki/UTF-8). |
| `Media-Type`       | `Media-Type: application/pdf` | El `media-type`es similar a `Content-Type`, y describe los datos que se transfieren. Esta cabecera puede desempeñar un papel crucial en la realización de que el servidor interprete nuestra entrada. El `charset`El campo también se puede utilizar con esta cabecera.                          |
| `Boundary`         | `boundary="b4e4fbd93540"`     | Actos como marcador para separar el contenido cuando hay más de uno en el mismo mensaje. Por ejemplo, dentro de un formulario de datos, este límite se utiliza como `--b4e4fbd93540`para separar diferentes partes de la forma.                                                                  |
| `Content-Length`   | `Content-Length: 385`         | Mantén el tamaño de la entidad pasada. Este encabezado es necesario ya que el servidor lo usa para leer los datos del cuerpo del mensaje, y se genera automáticamente por el navegador y herramientas como cURL.                                                                                 |
| `Content-Encoding` | `Content-Encoding: gzip`      | Los datos pueden sufrir múltiples transformaciones antes de ser pasados. Por ejemplo, grandes cantidades de datos se pueden comprimir para reducir el tamaño del mensaje. El tipo de codificación que se utiliza debe especificarse utilizando el `Content-Encoding`cabecera.                    |

-----

## Solicitar encabezados

El cliente envía [a los encabezados de solicitud](https://tools.ietf.org/html/rfc2616) en una transacción HTTP. Estas cabeceras son `used in an HTTP request and do not relate to the content`del mensaje. Las siguientes cabeceras se ven comúnmente en las solicitudes HTTP.

|**Encabezador**|**Ejemplo**|**Descripción**|
|---|---|---|
|`Host`|`Host: www.inlanefreight.com`|Se utiliza para especificar que el huésco está siendo consultado por el recurso. Esto puede ser un nombre de dominio o una dirección IP. Los servidores HTTP se pueden configurar para alojar diferentes sitios web, que se revelan en base al nombre de host. Esto hace que el encabezado del host sea un objetivo de enumeración importante, ya que puede indicar la existencia de otros hosts en el servidor de destino.|
|`User-Agent`|`User-Agent: curl/7.77.0`|El `User-Agent`cabecera se utiliza para describir al cliente solicitando recursos. Esta cabecera puede revelar mucho sobre el cliente, como el navegador, su versión y el sistema operativo.|
|`Referer`|`Referer: http://www.inlanefreight.com/`|Denota de dónde viene la solicitud actual. Por ejemplo, hacer clic en un enlace de los resultados de búsqueda de Google `https://google.com`el árbitro. Confiar en esta cabecera puede ser peligroso ya que puede ser fácilmente manipulado, llevando a consecuencias no deseadas.|
|`Accept`|`Accept: */*`|El `Accept`cabecera describe qué tipos de medios puede entender el cliente. Puede contener múltiples tipos de medios separados por comas. El `*/*`el valor significa que todos los tipos de medios son aceptados.|
|`Cookie`|`Cookie: PHPSESSID=b4e4fbd93540`|Contiene pares de valor de cookie en el formato `name=value`. Una [cookie](https://en.wikipedia.org/wiki/HTTP_cookie) es una pieza de datos almacenada en el lado del cliente y en el servidor, que actúa como identificador. Estos se pasan al servidor por solicitud, manteniendo así el acceso del cliente. Las cookies también pueden servir para otros fines, como el ahorro de preferencias del usuario o el seguimiento de sesión. Puede haber múltiples galletas en una sola cabecera separada por un semi-colon.|
|`Authorization`|`Authorization: BASIC cGFzc3dvcmQK`|Otro método para que el servidor identifique a los clientes. Después de una autenticación exitosa, el servidor devuelve una ficha única para el cliente. A diferencia de las cookies, las fichas se almacenan sólo en el lado del cliente y recuperadas por el servidor por solicitud. Existen múltiples tipos de autenticación basados en el servidor web y tipo de aplicación utilizado.|

Una lista completa de encabezados de solicitud y su uso se puede encontrar [aquí](https://tools.ietf.org/html/rfc7231#section-5).

---

## Cabeceros de respuesta

[Los encabezados](https://tools.ietf.org/html/rfc7231#section-7) de [respuesta](https://tools.ietf.org/html/rfc7231#section-7) pueden ser `used in an HTTP response and do not relate to the content`. Ciendas cabeceras de respuesta, tales como `Age`, `Location`, y `Server`se utilizan para proporcionar más contexto sobre la respuesta. Las siguientes cabeceras se ven comúnmente en las respuestas HTTP.

|**Encabezador**|**Ejemplo**|**Descripción**|
|---|---|---|
|`Server`|`Server: Apache/2.2.14 (Win32)`|Contiene información sobre el servidor HTTP, que tramitó la solicitud. Se puede utilizar para obtener información sobre el servidor, como su versión, y enumerarla más.|
|`Set-Cookie`|`Set-Cookie: PHPSESSID=b4e4fbd93540`|Contiene las cookies necesarias para la identificación del cliente. Los navegadores analizan las cookies y las almacenan para futuras solicitudes. Esta cabecera sigue el mismo formato que el `Cookie`Solicitar encabezado.|
|`WWW-Authenticate`|`WWW-Authenticate: BASIC realm="localhost"`|Notifica al cliente el tipo de autenticación requerida para acceder al recurso solicitado.|

---

## Cabeceros de seguridad

Finalmente, tenemos [jefes de seguridad](https://owasp.org/www-project-secure-headers/). Con el aumento de la variedad de navegadores y ataques basados en la web, definiendo ciertas cabeceras que mejoraban la seguridad era necesaria. Cabeceras de seguridad HTTP son `a class of response headers used to specify certain rules and policies`a seguir el navegador mientras se accede al sitio web.

|**Encabezador**|**Ejemplo**|**Descripción**|
|---|---|---|
|`Content-Security-Policy`|`Content-Security-Policy: script-src 'self'`|Dicta la política del sitio web hacia los recursos inyectados externamente. Este podría ser código JavaScript, así como recursos de script. Esta cabecera instruye al navegador a aceptar recursos sólo de ciertos dominios de confianza, evitando así ataques como [el scripting de sitios cruzados (XSS](https://en.wikipedia.org/wiki/Cross-site_scripting)).|
|`Strict-Transport-Security`|`Strict-Transport-Security: max-age=31536000`|Evita que el navegador accedera al sitio web a través del protocolo HTTP de texto plano, y obliga a llevar toda comunicación a ser llevada sobre el protocolo HTTPS seguro. Esto evita que los atacantes olfuchen el tráfico web y accedan a información protegida, como contraseñas u otros datos sensibles.|
|`Referrer-Policy`|`Referrer-Policy: origin`|Dictúa si el navegador debe incluir el valor especificado a través de la `Referer`cabecera o no. Puede ayudar a evitar revelar URLs e información sensibles mientras navega por el sitio web.|


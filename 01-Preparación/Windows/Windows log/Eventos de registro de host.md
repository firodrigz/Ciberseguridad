### Tipos de eventos.

| Tipo de evento            | Descripción                                                                                                                                                                                                                                                                                                                                               |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Error**                 | Evento que indica un problema significativo, como la pérdida de datos o la pérdida de funcionalidad, ofrecen información detallada sobre los problemas encontrados. Por ejemplo, si un servicio no se carga durante el inicio, se registra un evento Error.                                                                                               |
| **Advertencia**           | Evento que no es necesariamente significativo, pero puede indicar un posible problema futuro. Por ejemplo, cuando el espacio en disco es bajo, se registra un evento warning. Si una aplicación puede recuperarse de un evento sin pérdida de funcionalidad o datos, normalmente puede clasificar el evento como un evento de advertencia.                |
| **Información**           | Evento que describe el funcionamiento correcto de una aplicación, un controlador o un servicio. Por ejemplo, cuando un controlador de red se carga correctamente, puede ser adecuado registrar un evento de información. Tenga en cuenta que generalmente no es adecuado para que una aplicación de escritorio registre un evento cada vez que se inicie. |
| **Auditoría de aciertos** | Evento que registra un intento de acceso de seguridad auditado que se realiza correctamente. Por ejemplo, el intento correcto de un usuario de iniciar sesión en el sistema se registra como un evento success Audit.                                                                                                                                     |
| **Auditoría de errores**  | Evento que registra un intento de acceso de seguridad auditado que produce un error. Por ejemplo, si un usuario intenta acceder a una unidad de red y produce un error, el intento se registra como un evento de auditoría de errores.                                                                                                                    |
### Detalle del evento

El de la esquina superior izquierda sirve como un identificador único, que se puede investigar más a fondo en el sitio web de Microsoft para recopilar información adicional. La etiqueta "SideBySide" situada junto al identificador del evento representa el origen del evento

![Evento](https://i.postimg.cc/Bnvkm30c/Evento.png)

- `Log Name`: El nombre del registro de eventos (por ejemplo, Aplicación, Sistema, Seguridad, etc.).
- `Source`: El software que registró el evento.
- `Event ID`: Un identificador único para el evento.
- `Task Category`: A menudo contiene un valor o nombre que puede ayudarnos a comprender el propósito o el uso del evento.
- `Level`: La gravedad del evento (Información, Advertencia, Error, Crítico y Detallado).
- `Keywords`: Las palabras clave son indicadores que nos permiten categorizar los eventos de formas más allá de las otras opciones de clasificación. Por lo general, se trata de categorías amplias, como "Éxito de auditoría" o "Error de auditoría" en el registro de seguridad.
- `User`: La cuenta de usuario que inició sesión cuando se produjo el evento.
- `OpCode`: Este campo puede identificar la operación específica que notifica el evento.
- `Logged`: La fecha y hora en que se registró el evento.
- `Computer`: El nombre del equipo en el que se produjo el evento.
- `XML Data`: Toda la información anterior también se incluye en formato XML junto con datos de eventos adicionales.
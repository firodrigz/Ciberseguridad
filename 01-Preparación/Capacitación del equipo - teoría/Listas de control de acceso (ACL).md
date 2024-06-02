### ¿Qué es una ACL?

Una ACL es una serie de comandos del IOS que controlan si un router reenvía o descarta paquetes según la información que se encuentra en el encabezado del paquete.

El comando de configuración global **ip access-list** se utiliza para crear una ACL con nombre
A continuación se resumen las reglas que se deben seguir para las ACL con nombre:

- Asigne un nombre para identificar el propósito de la ACL.
- Los nombres pueden contener caracteres alfanuméricos.
- Los nombres no pueden contener espacios ni signos de puntuación.
- Se sugiere escribir el nombre en MAYÚSCULAS.
- Se pueden agregar o eliminar entradas dentro de la ACL.

**Nota:** Las ACLs no actúan sobre los paquetes que se originan en el propio router.

Las ACL de entrada filtran los paquetes que ingresan a una interfaz específica y lo hacen antes de que se enruten a la interfaz de salida. Las ACL de entrada son eficaces, porque ahorran la sobrecarga de enrutar búsquedas si el paquete se descarta. Si las ACL permiten el paquete, este se procesa para el routing. Las ACL de entrada son ideales para filtrar los paquetes cuando la red conectada a una interfaz de entrada es el único origen de los paquetes que se deben examinar.

Las ACL de salida filtran los paquetes después de que se enrutan, independientemente de la interfaz de entrada. Los paquetes entrantes se enrutan a la interfaz saliente y luego se procesan a través de la ACL saliente. Las ACL de salida son ideales cuando se aplica el mismo filtro a los paquetes que proporcionan varias interfaces de entrada antes de salir por la misma interfaz de salida.

#### Máscara Wildcard
Es similar a la máscara de subred, solo que los 1 son 0 y los 0 son 1


Las ACL son listas que especifican los permisos o derechos asignados a varios fideicomisarios sobre un recurso específico. Cada entrada en una ACL se llama Entrada de Control de Acceso (ACE, por sus siglas en inglés).

- Las ACL pueden ser Discrecionales (DACL) que controlan el acceso al recurso y Sistémicas (SACL) que controlan la auditoría de accesos.
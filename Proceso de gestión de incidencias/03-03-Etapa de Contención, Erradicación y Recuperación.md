## Contención
Contención de largo y corto periodo: medidas para evitar la propagación del incidente. Es importante coordinar y ejecutarlos en todos los sistemas. Sin alertar al atacante.

backup: las contención a corto plazo dejan huella mínima en el sistema. En esta etapa podemos aprovechar a tomar imágenes para su análisis forense.

En las acciones de largo plazo, nos centramos en acciones y cambios persistentes. (cambios de contraseña, aplicación de reglas de firewall, aplicación de parche, apagado de sistemas). Se deben reportar estas accones a la empresa y partes relevantes.

Sistema parcheado =/= incidente terminado

## Erradicación
Se centra en eliminar todo lo relacionado con el incidente (eliminación del malware detectado, reconstrucción de sistemas, restauración desde backup). Aplicación de parches adicionales, actividades de fortalecimiento de la red.

## Recuperación
Se busca que los sistemas vuelvan a funcionar correctamente y contengan todos los datos necesarios.Cuando todo está verificado, estos sistemas se introducen en el entorno de producción. Todos los sistemas restaurados estarán sujetos a un intenso registro y monitoreo después de un incidente, ya que los sistemas comprometidos tienden a ser objetivos nuevamente si el adversario recupera el acceso al entorno en un corto período de tiempo.

Los eventos sospechosos típicos que se deben monitorear son:

- Inicios de sesión inusuales (por ejemplo, cuentas de usuario o servicio que nunca antes han iniciado sesión allí)
- Procesos inusuales
- Cambios en el registro en ubicaciones que suelen ser modificadas por malware
La etapa de recuperación en algunos incidentes de gran envergadura puede llevar meses, ya que a menudo se aborda por fases. Durante las primeras fases, la atención se centra en aumentar la seguridad general para prevenir futuros incidentes a través de victorias rápidas y la eliminación de las frutas maduras. Las fases posteriores se centran en cambios permanentes y a largo plazo para mantener la organización lo más segura posible.


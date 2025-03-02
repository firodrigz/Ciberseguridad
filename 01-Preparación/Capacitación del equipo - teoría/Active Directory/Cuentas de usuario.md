Es más fácil administrar grupos de usuarios y asignarle permisos que hacerlo usuario por usuario. 

#### Cuentas locales
Las cuentas locales se almacenan localmente en un servidor o estación de trabajo en particular. 

#### Usuarios de dominio
Los usuarios de dominio difieren de los usuarios locales en que se les otorgan derechos del dominio para acceder a recursos como servidores de archivos, impresoras, hosts intranet y otros objetos basados en los permisos concedidos a su cuenta de usuario o al grupo del que la cuenta es miembro. 
Las cuentas de usuario de Domain pueden iniciar sesión en cualquier host del dominio, a diferencia de los usuarios locales.


#### Grupos de usuario
###### Diferencia entre los grupos y las unidades organizativas (OUs).

Los OU son útiles para agrupar a usuarios, grupos y computadoras para facilitar la gestión y el despliegue de la configuración de la política de grupo a objetos específicos en el dominio. Los grupos se utilizan principalmente para asignar permisos de acceso a los recursos. Las OU también se pueden utilizar para delegar tareas administrativas en un usuario, como restablecer contraseñas o desbloquear cuentas de usuario sin darles derechos administrativos adicionales que puedan heredar a través de la membresía en grupo.

#### Tipos de grupos
**Security groups:** El tipo es principalmente para facilitar la asignación de permisos y derechos a una colección de usuarios en lugar de uno a la vez.
**Distribution groups:** El tipo es utilizado por aplicaciones de correo electrónico como Microsoft Exchange para distribuir mensajes a los miembros del grupo.

#### Alcances del grupo
Hay tres diferentes. `group scopes`que se puede asignar al crear un nuevo grupo.

1. Grupo local de dominio
2. Grupo Mundial
3. Grupo Universal

#### Grupo local de dominio

Los grupos locales de dominio sólo pueden ser usados para administrar permisos para dominar los recursos en el dominio donde fue creado. Los grupos locales no pueden utilizarse en otros dominios,

#### Grupo Mundial

Los grupos mundiales pueden utilizarse para conceder acceso a los recursos en `another domain`. Un grupo global sólo puede contener cuentas del dominio donde fue creado. Los grupos globales pueden añadirse tanto a otros grupos globales como a grupos locales.

#### Grupo Universal

El alcance del grupo universal se puede utilizar para administrar los recursos distribuidos en múltiples dominios y se le pueden dar permisos a cualquier objeto dentro de la misma `forest`. Están disponibles para todos los dominios dentro de una organización y pueden contener usuarios de cualquier dominio.


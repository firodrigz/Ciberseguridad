###### PWCONV / PWUNCONV
Cuando ejecutamos el comando **pwunconv** (sudo pwunconv) , el archivo **shadow** es eliminado y las contraseñas cifradas se pasan a **passwd**.
###### Antes
``` bash 
root:x:10568:0:99999:7:7:-1::
pedro:x:10568:0: -1:9:-1:-1::
```
###### Después
``` bash 
root:ghy675gjuXCc12r5gt78uuu6R:10568:0:99999:7:7:-1::
pedro:rfgf886DG778sDFFDRRu78asd:10568:0: -1:9:-1:-1::
```

###### Para volver a la normalidad = contraseñas protegidas / encriptadas
``` bash
sudo pwconv
sudo ls -1 /etc/passwd /etc/shadow
```

###### ADDUSER / USERADD
Siempre se debe ejecutar como root.

- `c'<comentario>'` permite añadir un comentario al usuario, como puede ser su nombre real.
- `d <directorio>` permite cambiar el directorio por defecto del usuario, que suele ser `/home/<usuario>`.
- `e <YYYYMMDD>` permite seleccionar la fecha en la que la cuenta se deshabilitará. Debe introducirse en el formato indicado: añomesdía.
- `f <días>` permite seleccionar el tiempo en días a partir de la fecha de expiración de la contraseña, cuando la cuenta se deshabilitará. Con un valor de -1, no lo hará.
- `g <grupo>` permite añadir el usuario a un grupo. Debe existir con anterioridad para poder hacerlo. Podemos introducir el grupo por su nombre o por su ID.
- `G <grupos>` similar a la opción anterior, pero para introducir varios grupos separados por comas.
- `m` crea el directorio del usuario si no existe.
- `M` no crea el directorio del usuario.
- `n` no crea un grupo privado para el usuario.
- `r` la cuenta se convierte en cuenta del sistema, con ID de usuario (UID) menor a 500 y sin directorio.
- `p <contraseña>` establece una contraseña de usuario. Se puede crear posteriormente con el comando `passwd<usuario>`. Se encriptará con crypt.
- `s <shell>` permite modificar el shell de inicio de sesión del usuario, por defecto, /bin/bash.
- `u <UID>` permite especificar la ID del usuario; debe ser mayor que 499 y única.

``` bash
useradd -m usuario_2
```

Si queremos crear un usuario con distinto directorio diferente a /home debemos
``` bash
sudo useradd -m -d /usuariodirectdistinto
```

Este comando permite crear un usuario con una advertencia de contraseña, un número máximo de días antes de que caduque la contraseña y la respectiva configuración de reintentos de inicio de sesión.

``` bash
sudo useradd test5 -m -K PASS_MAX_DAYS = 5 -K PASS_WARN_ AGE = 3 -K LOGIN_RETRIES = 1
```

###### USERMOD
Podemos modificar propiedades de un usuario, necesitamos root para ejecutar el comando.


- `c` añade o modifica el comentario.
- `d` modifica el directorio de trabajo o home del usuario, pero no cambia sus archivos de ubicación.
- `m` mueve los datos del directorio de trabajo del usuario a su nueva ubicación.
- `e` añade o modifica la fecha de expiración de la cuenta en formato AAAA-MM-DD.
- `g` modifica el GID del grupo principal del usuario.
- `G` establece otros grupos a los que puede pertenecer el usuario, separados por comas, pero elimina aquellos a los que ya pertenece.
- `I` cambia el login o nombre del usuario.
- `u` cambia el UID del usuario.

###### USERDEL
Elimina un usuario del sistema pero NO SU PERFIL.

- `r` elimina al usuario y borra su directorio personal, solo si este no se encuentra trabajando en el sistema.
- `f` elimina al usuario y no le importa si está trabajando en ese momento en el sistema, pero no lo expulsa en ese momento.

###### PASSWD 
Permite cambiar a un usuario su contraseña solicitándole su contraseña anterior. Si el comando lo ejecuta ROOT para otro usuario no le solicita contraseña anteior.

###### GROUPADD
Debe ser ejecutado por root, permite añadir nuevos grupos.

- `g` establece un GID manual, si no se indica, el sistema lo asignará en forma automática.

###### GROUPMOD
Se encarga de modificar las propiedades de un grupo existente en el sistema.

- `n` modifica el nombre del grupo.
- `g` modifica el GID.

###### GROUPDEL
``` bash
groupdel alumnos
````

###### WHO
Determina el usuario que está activo.

###### LOGNAME
Muestra la variable de entorno `logname` que contiene el nombre de usuario con el que nos conectamos al sistema.

###### ID
Muestra nombre del usuario + los grupos los cuál pertenece.
``` bash
id root
```

##### GROUPS
Similar a ID


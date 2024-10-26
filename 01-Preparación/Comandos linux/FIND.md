
Si recordamos el nombre del archivo, simplemente podemos usar donde el comando buscará en cada carpeta de nuestro directorio actual ese archivo específico de la siguiente manera:`find -name passwords.txt`


"find / -perm -4000 2>/dev/null" VS "find / -user root -perm 4000 2>/dev"

Ambos comandos `find` tienen como objetivo buscar archivos con permisos SUID (Set User ID) activados en el sistema, lo que generalmente indica ejecución con privilegios elevados. Sin embargo, hay diferencias en la forma en que se expresan las condiciones de búsqueda:

1. **`find / -perm -4000 2>/dev/null`:**
   - Este comando busca archivos con el bit SUID activado (`-4000`).
   - El uso de `-4000` indica que solo se buscan archivos con el bit SUID activado, independientemente del propietario del archivo.
   - La redirección `2>/dev/null` se utiliza para redirigir los mensajes de error a /dev/null, lo que significa que cualquier error durante la búsqueda no se mostrará en la salida estándar.

2. **`find / -user root -perm 4000 2>/dev/null`:**
   - Este comando busca archivos con permisos SUID (`-perm 4000`).
   - Además, se filtra por aquellos que tienen al propietario del archivo como "root" (`-user root`).
   - La redirección `2>/dev/null` se utiliza de manera similar para evitar mostrar mensajes de error en la salida estándar.

En resumen:

- El primer comando busca archivos con el bit SUID activado sin importar el propietario del archivo.
- El segundo comando busca archivos con el bit SUID activado y tiene al propietario del archivo como "root".

La diferencia clave radica en la condición `-user root` en el segundo comando, lo que restringe la búsqueda a archivos SUID propiedad del usuario "root". Dependiendo de tus objetivos de búsqueda, puedes elegir el comando que mejor se adapte a tus necesidades.
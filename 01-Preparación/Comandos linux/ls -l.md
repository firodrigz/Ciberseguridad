
```
[analyst@secOps ~]$ ls -l space.txt
-rwxrw-r-- 1 analyst staff 253 May 20 12:49 space.txt
```

El archivo **space.txt** tiene los siguientes permisos:

- El guion (-) indica que se trata de un archivo. En el caso de los directorios, el primer guion se reemplazaría por una “d”.
- El primer conjunto de caracteres es para el permiso de usuario (**rwx** ). El usuario **analista** (analyst) que posee el archivo puede leer ( **R**ead), escribir (**W**rite) y ejecutar (e**X**ecute) el archivo.
- El segundo conjunto de caracteres es para los permisos de grupo (**rw-**). **El grupo** (staff) que posee el archivo puede leer (**R**ead) y escribir (**W**rite) el archivo.
- El tercer conjunto de caracteres es para cualquier otro permiso de usuario o de grupo (**r--**). Cualquier otro usuario o grupo de la computadora solo puede leer (Read) el archivo.**
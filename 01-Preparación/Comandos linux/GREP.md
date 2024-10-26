Otra gran utilidad que es una gran para aprender es el uso de . El comando nos permite buscar en el contenido de los archivos los valores específicos que estamos buscando.`grep``grep`

Tomemos, por ejemplo, el registro de acceso de un servidor web. En este caso, el access.log de un servidor web tiene 244 entradas.

Usar "wc" para contar el número de entradas en "access.log"

```shell-session
tryhackme@linux1:~$ wc -l access.log
244 access.log
tryhackme@linux1:~$
```

Usar un comando como no va a ser muy bueno aquí. Digamos, por ejemplo, si quisiéramos buscar en este archivo de registro para ver las cosas que visitó un determinado usuario/dirección IP. Mirar a través de 244 entradas no es tan eficiente teniendo en cuenta que queremos encontrar un valor específico.`cat`

Podemos usar para buscar en todo el contenido de este archivo cualquier entrada del valor que estamos buscando. Siguiendo con el ejemplo del registro de acceso de un servidor web, queremos ver todo lo que ha visitado la dirección IP "81.143.211.90" (tenga en cuenta que esto es ficticio)`grep`

Usar "grep" para encontrar cualquier entrada con la dirección IP de "81.143.211.90" en "access.log"

```shell-session
tryhackme@linux1:~$ grep "81.143.211.90" access.log
81.143.211.90 - - [25/Mar/2021:11:17 + 0000] "GET / HTTP/1.1" 200 417 "-" "Mozilla/5.0 (Linux; Android 7.0; Moto G(4))"
tryhackme@linux1:~$
```

"Grep" ha buscado en este archivo y nos ha mostrado cualquier entrada de lo que hemos proporcionado y que está contenido dentro de este archivo de registro para la IP.



Opciones comunes Sintaxis básicas de grep
`grep [opciones] patrón [archivo]` 
Buscar un término dentro de un archivo
`grep "patrón" archivo.txt` 
// Esto buscará todas las líneas en archivo.txt que contienen el texto "patrón". 

Buscar en múltiples archivos
`grep "patrón" archivo.txt archivo2.txt` 
Buscar varias palabras
`grep -E "palabra|palabra2" archivo.txt` 
Ignorar mayúsculas y minúsculas 
`grep -i "patrón" archivo.txt` 
// Esto buscará "patrón", "Patrón", "PATRÓN", etc. 
Especifica solamente lo mencionado eliminado el resto de la palabra agregando la grep -i -o "patrón" archivo.txt 
`grep -io "patrón" archivo.txt` 
Mostrar solamente la línea que coincide con el patrón especificado 
`grep -i "patrón" archivo.txt`
Buscar de forma recursiva en directorios
`grep -r "patrón" /ruta/del/directorio` 
`grep -R "patrón" /ruta/del/directorio` 
// Busca en todos los archivos dentro de un directorio y sus subdominios "patrón". 
Mostrar solo el nombre del archivo 
`grep -l "patrón" *.txt` 
// Muestra solo los nombres de los archivos que contienen el "patrón". 
Muestra todas las líneas que no llevan la palabra especificada 
`grep -v "patrón" archivo.txt-o Muestra el número de línea` 
`grep -n "patrón" archivo.tx`

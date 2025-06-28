
`doskey /history`. [Doskey](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/doskey) es una utilidad MS-DOS que mantiene un historial de comandos emitidos y permite que sean referenciados de nuevo.

```cmd-session
C:\htb> doskey /history

systeminfo
ipconfig /all
cls
ipconfig /all
systeminfo
cls
history
help
doskey /history
ping 8.8.8.8
doskey /history
```


cd -> muestra directorio actual

md | mkdir -> crear directorio

rm | rmdir -> eliminar directorio (no lo elimina si tiene contenido)
rm /s -> forzar eliminación de directorio con contenido

robocopy C:\Users\user\Desktop C:\Users\user\Documents\ -> copiar directorios

ren demo.txt superdemo.txt -> renombrar un archivo

ipconfig /all | find /i "IPV4" -> find para buscar

ipconfig /displaydns -> muestra registros dns

ipconfig /flushdns -> limpia registros dns

dir /A:H -> ver archivos ocultos

del /A:H * -> eliminar todos los archivos ocultos

C:\Users\student\Desktop>where calc.exe -> buscar archivo/ejecutable


#### Mostrar el único archivo `.txt` con tamaño mayor a 0 bytes:
for /R %f in (*.txt) do @if %~zf NEQ 0 echo %f

### ¿Qué hace este comando?

- `for /R %f in (*.txt)` → Recorre todos los archivos `.txt` de forma recursiva.    
- `%~zf` → Obtiene el tamaño en bytes del archivo.    
- `if %~zf NEQ 0` → Filtra solo los que **no están vacíos**.    
- `echo %f` → Muestra la **ruta completa** del archivo que tiene contenido.


###### Consultar usuarios

net user



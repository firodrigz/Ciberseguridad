
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

dir /A:H -> ver archivos ocultos

del /A:H * -> eliminar todos los archivos ocultos

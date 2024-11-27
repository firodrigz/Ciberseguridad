# Comandos básicos Linux

A continuación se enumaran los comandos más importantes que son de utilidad en el día a día.

*manual de comandos* -> man *comando*

- Limpiar consola -> clear / ctrl + l
- Instalar algo -> sudo apt install "paquete"
- Eliminar -> sudo apt remove "paquete" / sudo apt autoremove -> se recomienda luego de eliminar una aplicación.
- Actualizar linux -> sudo apt update sudo apt full-upgrade -y

## DIRECTORIOS
- Moverme entre directorios -> cd directorio // cd .. // (space) cd
- Crear directorio -> mkdir directorio
- Crear directorio desde otra carpeta -> mkdir /home/directorio lo mismo para eliminar
- Eliminar directorio -> rmdir directorio
- tree .
	├── info.txt
	└── Storage
	    └── local
	        └── user
	            ├── documents
	            └── userinfo.txt

## ARCHIVOS
- Crear un archivo -> touch archivo.txt / archivo.py /archivo.etc o sin el '.' y por default devuelve un txt.
- Eliminar un archivo -> rm archivo.txt
- Ver archivo -> cat archivo.txt
- Ver archivo con espacios en su nombre de por medio -> cat "archivo con espacios" // cat archivo con espacios
- Abrir y editar archivo -> nano archivo.txt // vim archivo.txt
- Ver archivo que su nombre comienza con un - -> cat ./-

*CAT (despliega el contenido)
| MORE (despliega por partes)*

## LS
- Ver lista de los archivos y directorios fuera del directorio -> ls /directorio 
- Ver lista de los archivos y directorios dentro del directorio -> ls | ls -l 
- Ver carpetas ocultas -> ls -la

## MV
``` bash
mv <file/directory> <renamed file/directory>
```

``` bash
mv information.txt readme.txt Storage/  -> MUEVE VARIOS ARCHIVOS A UN DIRECTORIO
```

## CP
``` bash
cp Storage/readme.txt Storage/local/ 
```

## AGREGAR RUTA ABSOLUTA AL PATH
- Añadir el comando export dentro del fichero de definición de entorno que estemos usando. (fichero .bashrc, oculto en carpeta home.)

``` bash
nano /home/usuario/.bashrc
```
``` bash
export PATH=$PATH:/home/usuario/ruta_a_la_carpeta_que_quiero_añadir <- al final del fichero
```


## WHICH
``` bash
which python
```
/usr/bin/python
- Si el programa que buscamos no existe, no se mostrará ningún resultado. 

## FIND

find (directorio) -type f/d -name "archivo"
- -type -> file:f / directory:d
- -size -> tamaño del archivo
- -name -> nombre del archivo
- -user -> nombre del usuario // group -> nombre del grupo 

En caso que devuelva un listado de archivos basura/errores utilizar ( 2>/dev/null )

find / -> búsqueda  en el directorio raiz del sistema de archivos.

find . -> búsqueda en el directorio actual.

¿Cuál es el nombre del archivo de configuración que se ha creado después de 2020-03-03 y es menor que 28k pero mayor que 25k?
``` bash
find / -iname "*.conf" -size +25k -size -28k -newermt 2020-03-03 2>/dev/null
```

``` bash
find /etc/ -name shadow 2>/dev/null > results.txt
```

``` bash
find /etc/ -name shadow 2> stderr.txt 1> stdout.txt
```
## LOCATE
- A diferencia del comando, funciona con una base de datos local que contiene toda la información sobre los archivos y carpetas existentes. Podemos actualizar esta base de datos con el siguiente comando. 
``` bash 
sudo updatedb
```

``` bash
locate *.conf
```

/etc/GeoIP.conf
/etc/NetworkManager/NetworkManager.conf
/etc/UPower/UPower.conf
/etc/adduser.conf
<SNIP>

## WC (count words)
``` bash
cat archivo.txt | wc -l -> me devuelve la cantidad de lineas que hay
```

## COMPRIMIR Y DESCOMPRIMIR ARCHIVOS Y DIRECTORIOS
Para comprimir un archivo o directorio usaremos el comando tar junto con una herramienta
de compresión tipo gzip , bzip2  y xz .

**ARCHIVOS**
``` bash
gzip: tar czf archivo-comprimido.tar.gz nombre-del-archivo1 nombre-del-archivo2
bzip2: tar cjf archivo-comprimido.tar.bz2 nombre-del-archivo1 nombre-del-archivo2
xz: tar cJf archivo-comprimido.tar.xz nombre-del-archivo1 nombre-del-archivo2
```

**DIRECTORIOS**
``` bash
tar czf archivo-comprimido.tar.gz nombre-del-directorio

```
**LISTAR EL CONTENIDO DE UN ARCHIVO TAR:**
``` bash
tar tvf archivo-comprimido.tar.gz
```

**DESCOMPRIMIR UN ARCHIVO TAR:**
``` bash
tar -xvf archivo-comprimido.tar.gz
```

**DESCOMPRIMIR ARCHIVO TAR EN OTRO DIRECTORIO:**
``` bash
tar -xvf archivo-comprimido.tar.gz -C /nombre-del-directorio/
```

**COMPRIMIR UN ARCHIVO GZ CON GZIP:**
``` bash
gzip -9 nombre-del-archivo1
```

**DESCOMPRIMIR UN ARCHIVO GZ CON GZIP:**
``` bash
gzip -d archivo-comprimido.gz
```

## ENLACES A FICHEROS Y DIRECTORIOS

- Enlace al directorio test -> ln -s test testenlace

## REDIRECCIÓN DE SALIDA ">" o ">>"
- ">" La salida de un comando o programa la dirige a un archivo.
- ">>" La salida de un comando o programa rescribe el archivo.

## HEAD Y TAIL
### HEAD
- Devuelve por default las primeras 10 lineas -> head archivo.txt 
- Seleccionar la cant. de lineas primeras que quiero que devuelva -> head -5 archivo.txt (devuelve las primeras 5).

### TAIL
- Devuelve por default las últimas 10 lineas -> tail archivo.txt
- || -> tail -5 archivo.txt (devuelve las últimas 5 lineas).
- cat archivo.txt | head -3 (del archivo.txt devuelve las primeras 3 líneas).

## GREP
El comando grep permite buscar, dentro de los archivos, las líneas que concuerdan con un patrón.
- grep "pass" archivo.txt
- grep "pass" archivo.txt -> elimina el "pass" si encuentra la palabra en el archivo.txt
- grep [patrón] file
- grep -v [patrón] file  -> para excluir contenido

## SORT
Ordena las lineas de los archivos de entrada a partir de opciones de ordenación.
sort [opciones] [archivo]

- -t "separador" (especifica el separador de las columnas)
- -k número (a partir de que num de columna)
- -n ordena por valor numérico
- -r invierte el orden

### Ej:cat archivo.txt 
    Juan,Balam,100,Física
    Bautista,May,85,Física

sort -t ',' -k 1 archivo.txt (lo que hago aca es ordenar de la primer columna aquella palabra antes de la ',').

    Bautista,May,85,Física
    Juan,Balam,100,Física

## TR 

### sustituye por las minúsculas por las mayúsculas
echo "hola mundo" | tr aeiou AEIOU
> hOlA mUndO

### borrar -d
echo hola mundo | tr -d a
> hol mundo

### elimina letras repetidas -s
echo holaa munnddooo | tr -s ando
> hola mundo

### cambiar todo lo que no existe por un caracter
echo hola mundo | tr -c aeiou '-' (si no hay 'aeiou' en el texto lo cambia por un -)
> -o-a--u---o

## PERMISOS 

Archivo -> **-**rwx
Directorio -> **d**rwx

drwx	r-x	r-x
prop	group	all users

### CHMOD
- chmod +x archivo/directorio
- chmod +r archivo/directorio
- chmod 777 archivo/directorio

-rwx (r=4, w=2, x=1) -> se puede hacer numerico por eso el 777

## ADD USERS
- adduser Facu -> crea nuevo usuario
- id ->brinda información del usuario en uso (grupos a los que pertenece)
- SHELL -> zsh o bash

1. En home -> mkdir facu
2. useradd -d /home/facu -s /bin/bash facu
3. ls -l
4. chown facu:facu facu

### GROUPS
1. groupadd testgroup -> creo grupo
2. cat /etc/group | tail -n 1 -> verifico creación
3. chgrp testgroup directorio -> permisos
4. usermod -a -G testgroup facu

## REDES
netstat -ano -> veo puertos abiertos en mi host

## SERVICIOS
system -> temporal
service apache2 start / service apache2 stop
python -m http.server [puerto]
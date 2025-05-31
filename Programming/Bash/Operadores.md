## Operadores de strings

| **Operador** | **Descripción**                           |
| ------------ | ----------------------------------------- |
| `==`         | es igual a                                |
| `!=`         | no es igual a                             |
| `<`          | es menor que en orden alfabético ASCII    |
| `>`          | es mayor que en el orden alfabético ASCII |
| `-z`         | si la cuerda está vacía (nula)            |
| `-n`         | si la cadena no es nula                   |
```bash
#!/bin/bash

# Check the given argument
if [ "$1" != "HackTheBox" ]
then
	echo -e "You need to give 'HackTheBox' as argument."
	exit 1

elif [ $# -gt 1 ]
then
	echo -e "Too many arguments given."
	exit 1

else
	domain=$1
	echo -e "Success!"
fi
```

## Operadores enteros

| **Operador** | **Descripción**    |
| ------------ | ------------------ |
| `-eq`        | es igual a         |
| `-ne`        | no es igual a      |
| `-lt`        | es menos que       |
| `-le`        | es menor o igual a |
| `-gt`        | es mayor que       |
| `-ge`        | es mayor o igual a |
```bash
#!/bin/bash

# Check the given argument
if [ $# -lt 1 ]
then
	echo -e "Number of given arguments is less than 1"
	exit 1

elif [ $# -gt 1 ]
then
	echo -e "Number of given arguments is greater than 1"
	exit 1

else
	domain=$1
	echo -e "Number of given arguments equals 1"
fi
```


## Operadores de archivos

| **Operador** | **Descripción**                                                                |
| ------------ | ------------------------------------------------------------------------------ |
| `-e`         | si el expediente existe                                                        |
| `-f`         | pruebas si es un archivo                                                       |
| `-d`         | pruebas si se trata de un directorio                                           |
| `-L`         | pruebas si lo es si un eslabón simbólico                                       |
| `-N`         | comprueba si el archivo fue modificado después de que se leyera por última vez |
| `-O`         | si el usuario actual posee el archivo                                          |
| `-G`         | si el id del grupo de archivos coincide con el usuario actual.s                |
| `-s`         | pruebas si el archivo tiene un tamaño mayor que 0                              |
| `-r`         | pruebas si el archivo ha leído el permiso                                      |
| `-w`         | pruebas si el archivo tiene permiso de escritura                               |
| `-x`         | pruebas si el archivo tiene permiso de ejecución                               |
```bash
#!/bin/bash

# Check if the specified file exists
if [ -e "$1" ]
then
	echo -e "The file exists."
	exit 0

else
	echo -e "The file does not exist."
	exit 2
fi
```



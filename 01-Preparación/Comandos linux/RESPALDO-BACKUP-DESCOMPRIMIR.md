- /etc -> Instalación de aplicaciones
- /home
- /var -> Información de aplicaciones

#### Herramientas de compresión sin pérdida
- zip
- rar
- xz
- 7z
- gz
- bz2
- lz0
Pesan menos y menos tiempo de compresión

##### GZIP
Una vez que comprime, ELIMINA el archivo original

###### Comprimir
``` bash
gzip services(nombre archivo)  
```
###### Descomprimir 2 alternativas
``` bash
gunzip services.gz
gzip -d services.gz
```

##### BZIP2
- Comprime MÁS que GZIP, pero lleva más tiempo en comprimir.
- Se utiliza mayormente para respaldos históricos.
- Reduce tamaño y uso de ancho de banda.

###### Comprimir
``` bash
bzip2 services(nombre archivo)  
```
###### Descomprimir
``` bash
bzip2 -d services.bz2
```

##### XZ
- Ocupa mucho menos espacio
- %50 más lento que GZIP
- Podría no estar instalado en algunos sistemas
- Se utiliza mayormente para imágenes de discos.

###### Comprimir
``` bash
xz services(nombre archivo)  
```
###### Descomprimir
``` bash
xz -d services.xz
```


###### TAR

PERMITE AGRUPAR DIRECTORIOS puedo poner los que quiera.

f nombredearchivo: El archivo de trabajo
c - crear un archivo tar / x - Extraer un tar
z - usar gzip / j usar bzip2


``` bash
tar cf /nombre_archivo_resultante.tar /directorio_a_formar_parte /home / etc
```

###### Comprimido gzip
``` bash
tar zcf /nombre_archivo_resultante.tar.gz /directorio_a_formar_parte
```

###### Comprimido bzip2
``` bash
tar jcf /nombre_archivo_resultante.tar.bz2 /directorio_a_formar_parte
```

###### Extraer
``` bash
tar xf /nombre_archivo_resultante.tar /directorio_a_formar_parte
tar zxf /nombre_archivo_resultante.tar.gz /directorio_a_formar_parte
tar jxf /nombre_archivo_resultante.tar.bz2 /directorio_a_formar_parte
```



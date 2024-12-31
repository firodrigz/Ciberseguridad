##### Instalación de Proxmox
- Debemos instalar Proxmox en las máquinas/servidores que queremos gestionar
- Proxmox está basado en debian por lo que si queremos actualizar el sistema con `apt update` hará la consulta a los repos de Proxmox pero si queremos hacer la consulta sobre los repos de debian debemos `apt-get dist-upgrade`

##### Creación Cluster

> [!IMPORTANTE]
> - Todos los nodos tienen que estar en la misma red
> - La zona horaria debe estar sincronizada

``` bash
pvecm
pvecm create Cluster
pvecm status
```

##### Añadir nodo al cluster

Debemos conectarnos por ssh al otro servidor/nodo o gestionarlo desde el Proxmox del nodo que queremos añadir.

``` bash
ssh 192.168.1.52
pvecm add <ip-servidor-que-generó-el-cluster>
```


#### Añadir discos para hacerlos utilizables en un Proxmox

LVM -> Sistema avanzado de gestión de volúmenes

/dev/sdd

En el servidor creamos particiones:
``` bash
/* Consultar particiones */
fdisk -l

/* Crear - eliminar particiones */
cfdisk /dev/sdd

/* Crear volumen LVM */
pvcreate /dev/sdd1
vgcreate Disco500Gb /dev/sdd1
```

Ahora debemos ir a Datacenter (interfaz web) - Storage - Add LVM y seleccionar el volumen que acabamos de crear.

ZFS -> Raid discos en mirror

En el servidor:
``` bash
zpool create -f -o ashift=12 PoolZFS mirror /dev/sda /dev/sdb
```

Ahora debemos ir a Datacenter (interfaz web) - Storage - Add ZFS y seleccionar el Pool que acabamos de crear.

``` bash
/* Crear POOL ZFS */
zpool create -f -o ashift=12 nombrepool Tiporaid /dev/sda /dev/sdb

/* Tipo de raid */
Tiporaid= mirror, raidz1, raidz2, etc.
```

##### Montar disco como directorio / carpeta

En el servidor:
``` bash
/* Borramos particiones y creamos nueva limpia */
cfdisk /dev/sde

/* Ir a la raiz del servidor / y crear una carpeta formateada */
mkfs.ext3 /dev/sde1

mkdir isos
mount -t ext3 /dev/sde1 /isos

/* PARA MANTENER EL MONTAJE AL REINICIAR PROXMOX DEBEMOS AÑADIR LA LÍNEA EN /etc/fstab */
nano /etc/fstab
mount -t ext3 /dev/sde1 /isos
```

Ahora debemos ir a Datacenter (interfaz web) - Storage - Add Directorios y seleccionar.

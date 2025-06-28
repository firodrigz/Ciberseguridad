#### Uso de smbclient para listar las acciones disponibles

NTFS vs. Permisos de acciones

```python
firodrigz@htb[/htb]$ smbclient -L SERVER_IP -U htb-student
Enter WORKGROUP\htb-student's password: 

	Sharename       Type      Comment
	---------       ----      -------
	ADMIN$          Disk      Remote Admin
	C$              Disk      Default share
	Company Data    Disk      
	IPC$            IPC       Remote IPC
```

#### Conexión a la participación de datos de la compañía

NTFS vs. Permisos de acciones

```python
firodrigz@htb[/htb]$ smbclient '\\SERVER_IP\Company Data' -U htb-student
Password for [WORKGROUP\htb-student]:
Try "help" to get a list of possible commands.

smb: \> 
```


Puedo **montar una carpeta compartida por SMB (CIFS)** desde un servidor remoto en nuestra máquina local Linux. 

sudo mount -t cifs -o username=htb-student,password=Academy_WinFun! //<ip_target>/"Company Data" /home/user/Desktop/


### ⚠️ Tips de seguridad

- **No es recomendable** pasar la contraseña directamente en el comando. En producción, se suele usar un archivo de credenciales con permisos restringidos.    
- Por ejemplo:

```python
sudo mount -t cifs -o credentials=/home/user/.smbcredentials //ip/share /mnt/share
```

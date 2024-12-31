COMO SUDO

``` bash
fdisk -l
```

sudo gedit /etc/fstab
agregar /dev/sdb /home ext4 defaults 0 2
sudo mv /home/ /media/

### **Pasos correctos para montar una partición en `/home`:**

1. **Crear la partición con `fdisk` o `GParted`**
``` bash
sudo fdisk /dev/sdX   # Reemplaza "X" por la letra de tu disco (por ejemplo, sdb)
```

2. **Formatear la partición (si aún no está formateada):**
``` bash
 sudo mkfs.ext4 /dev/sdXn   # Reemplaza Xn por tu partición (ej., sdb1)
```
   
3. **Copiar datos existentes de `/home`:** Antes de montar una nueva partición en `/home`, necesitas preservar los archivos actuales.
 
``` bash
 sudo cp -a /home/* /ruta_temporal/
 ``` 

4. **Editar `/etc/fstab`:**  
   Abre el archivo con permisos de administrador:

``` bash 
 sudo nano /etc/fstab
```
   
   Agrega una línea como esta:
   
   `/dev/sdXn   /home   ext4    defaults   0   2`
   
- **`/dev/sdXn`:** Partición del HDD.
- **`/home`:** Punto de montaje correcto.

5. **Montar y comprobar:**

``` bash
 sudo mount -a   # Monta todas las particiones definidas en fstab
```
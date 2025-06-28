Hay 5 tipos de sistemas de archivos Windows: FAT12, FAT16, FAT32, NTFS y exFAT. FAT12 y FAT16 ya no se utilizan en los modernos sistemas operativos Windows.

FAT32 (Dimensión de archivos) es ampliamente utilizado en muchos tipos de dispositivos de almacenamiento, como memorias USB y tarjetas SD, pero también se puede utilizar para formatear discos duros. El "32" en el nombre se refiere al hecho de que FAT32 utiliza 32 bits de datos para identificar grupos de datos en un dispositivo de almacenamiento.


Podemos enumerar los permisos NTFS en un directorio específico ejecutando cualquiera de los dos `icacls`dentro del directorio de trabajo o `icacls C:\Windows`contra un directorio que no se encuentra actualmente.


## ¿Son lo mismo NTFS y SMB?

**No.** Pero **trabajan juntos** cuando accedés a una carpeta por red.

### 🧠 Importante:

- **Los permisos NTFS siempre se aplican**, incluso si accedés localmente.    
- **Los permisos SMB solo se aplican cuando accedés por red**.    
- **Se aplica la restricción más estricta** entre ambos.

## 🔐 1. ¿Qué son los controles de carpeta NTFS?

NTFS (New Technology File System) es el sistema de archivos usado por Windows. Cuando hablamos de **permisos NTFS**, hablamos de **permisos a nivel de sistema de archivos local**, o sea, sobre lo que un usuario puede hacer con una carpeta o archivo **en disco** (leer, escribir, ejecutar, borrar, etc.).

### 🎯 Ejemplo:

En `C:\DocumentosConfidenciales`, puedes establecer:

- Que el grupo **"RRHH"** tenga permiso de **Lectura y Escritura**.    
- Que el grupo **"TI"** tenga **control total**.    

---

## 🌐 2. ¿Qué son los permisos SMB?

SMB (Server Message Block) es el **protocolo de red** que se usa para compartir carpetas y archivos en red (por ejemplo: `\\servidor\carpeta`). Cuando compartís una carpeta en red, le aplicás **permisos de compartición** (o permisos SMB), que determinan **quién puede acceder a esa carpeta por red**.

### 🎯 Ejemplo:

Compartís `C:\DocumentosConfidenciales` como `\\servidor\RRHH`, y configurás:

- Que **"Usuarios de dominio"** tengan **permiso de lectura** en la compartición.


## 🔗 3. ¿Qué relación tienen con usuarios y grupos de Active Directory (AD)?

Tanto los permisos NTFS como los SMB **pueden asignarse a usuarios o grupos de AD**, lo cual permite tener control centralizado.

### 🎯 Ejemplo:

- El grupo AD **"Ventas"** tiene miembros Juan y Marta.    
- Asignás permisos NTFS de solo lectura a "Ventas" sobre `C:\Ventas`.    
- Al compartir la carpeta, das permiso de lectura por SMB también a "Ventas".    

Así, cuando Juan accede a `\\servidor\Ventas`, tiene acceso de solo lectura **gracias a su pertenencia al grupo de AD**.

## 💡 Recomendación de buenas prácticas

- Siempre **limita el acceso por NTFS** primero.    
- Otorgá **acceso total en SMB** solo a los grupos que ya tengan los permisos controlados por NTFS. Por ejemplo:
	- Compartición SMB: acceso total.        
    - NTFS: el control fino de qué puede hacer cada grupo.        

Esto evita confusiones y errores de "doble configuración".


[[SMB]]
Aplicar Livepatch -> es una herramienta que permite instalar actualizaciones de seguridad para sistemas Linux sin necesidad de reiniciar el sistema.

#### Instalar un firewall
``` bash
sudo apt install gufw
```

#### Instalar antimalware
``` bash
sudo apt install clamav
```

Actualiza la base de datos -> recomendable ejecutarlo cada cierto tiempo
``` bash
sudo freshclam
```

Para ver los detalles de un análisis debemos utilizar

``` bash
sudo clamscan -rv /ruta/a/examinar
```

#### Eliminar rootkit
``` bash
sudo apt install chkrootkit
```

``` bash
sudo chkrootkit
```

#### Usuarios
GNU/Linux es un sistema multiusuario

[[DIRECTORIOS]]
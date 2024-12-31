###### Iniciar un servicio

``` bash
systemctl start ssh
```

###### Estado de un servicio 

``` bash
systemctl status ssh
```

Para agregar OpenSSH al script SysV para indicarle al sistema que ejecute este servicio después del inicio, podemos vincularlo con el siguiente comando: 

``` bash
systemctl enable ssh
```

Para comprobar que el servidor se ejecuta automáticamente ejecutamos 

``` bash
ps -aux | grep ssh
```

###### Enumeración de todos los servicios 

``` bash
systemctl list-units --type=service
```

###### Ver registros de servicios

``` bash
journalctl -u ssh.service --no-pager
```


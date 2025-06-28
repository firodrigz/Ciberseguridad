Encontrar la versión y construir el número de nuestro sistema.

```powershell-session
PS C:\htb> Get-WmiObject -Class Win32_OperatingSystem | Select-Object Version, BuildNumber

Version    BuildNumber
-------    -----------
10.0.19041 19041
```


Un **proveedor de servicios de seguridad gestionado (MSSP)** ofrece supervisión y gestión externa de dispositivos y sistemas de seguridad. Los servicios comunes incluyen cortafuegos gestionado, detección de intrusiones, red privada virtual, escaneo de vulnerabilidad y servicios antivirales.


Algunas de las tecnologías de acceso remoto más comunes incluyen, pero no se limitan a:

- Redes Privadas Virtuales (VPN)
- Shell de seguridad (SSH)
- Protocolo de transferencia de archivos (FTP)
- Computación de Redes Virtuales (VNC)
- Administración remota de Windows (o remoting de PowerShell) (WinRM)
- Protocolo remoto de escritorio (RDP)

#### Protocolo remoto de escritorio (RDP)

Es importante tener en cuenta que RDP escucha por defecto en el puerto lógico `3389`.

Podemos utilizar RDP para conectarnos a un objetivo de Windows desde un host de ataque que ejecuta a Linux o Windows. Si nos estamos conectando a un objetivo de Windows desde un host con Windows, podemos utilizar la aplicación de cliente RDP integrada llamada `Remote Desktop Connection`([mstsc.exe](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/mstsc)).


Desde un host de ataque basado en Linux podemos utilizar una herramienta llamada [xfreerdp](https://linux.die.net/man/1/xfreerdp) para acceder remotamente a los objetivos de Windows.


```shell-session
user@htb[/htb]$ xfreerdp /v:<targetIp> /u:htb-student /p:Password
```


## NOTA sobre "Windows NT":

- Internamente, **Windows 10** es **NT 10.0**    
- **Windows 11** también es **NT 10.0** (sí, ambos comparten esa versión del kernel)    
- Windows 7 = NT 6.1    
- Windows 8 = NT 6.2    
- Windows 8.1 = NT 6.3    

Para saber exactamente la **versión NT**, usá:
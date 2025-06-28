### Sysmon

Es un servicio del sistema de Windows y un controlador de dispositivo que permanece residente en los reinicios del sistema para supervisar y registrar la actividad del sistema en el registro de eventos de Windows. Sysmon proporciona información detallada sobre la creación de procesos, las conexiones de red, los cambios en el tiempo de creación de archivos y mucho más.

Los componentes principales de Sysmon incluyen:

- Un servicio de Windows para supervisar la actividad del sistema.
- Un controlador de dispositivo que ayuda a capturar los datos de actividad del sistema.
- Un registro de eventos para mostrar los datos de actividad capturados.

 Sysmon utiliza un archivo de configuración basado en XML. El archivo de configuración le permite incluir o excluir ciertos tipos de eventos en función de diferentes atributos como nombres de procesos, direcciones IP, etc.


[Sysmon - Sysinternals | Microsoft Learn](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon)
Sysmon para Linux:
[Sysinternals/SysmonForLinux (github.com)](https://github.com/Sysinternals/SysmonForLinux)
La [Solución de Contraseña de Microsoft Local Administrator (LAPS)](https://www.microsoft.com/en-us/download/details.aspx?id=46899) se utiliza para aleatorizar y rotar las contraseñas de administrador local en los hosts de Windows y evitar el movimiento lateral.

### **¿LAPS es lo mismo que CyberArk?**

**No, LAPS y CyberArk no son lo mismo, pero tienen objetivos similares.**

|Característica|LAPS|CyberArk|
|---|---|---|
|**Crea y gestiona contraseñas de Administrador local**|✅ Sí|✅ Sí|
|**Administra contraseñas de otros sistemas (servidores, bases de datos, etc.)**|❌ No|✅ Sí|
|**Funciona solo en entornos de Active Directory**|✅ Sí|❌ No, CyberArk es más flexible|
|**Es gratis y de Microsoft**|✅ Sí|❌ No, es un producto pago|
|**Proporciona bóveda de credenciales avanzada**|❌ No|✅ Sí|

🔹 **LAPS** es una solución **específica** para manejar contraseñas de administradores locales en computadoras dentro de un dominio de Active Directory.  
🔹 **CyberArk** es una **solución más completa y avanzada** que maneja **contraseñas privilegiadas** en toda la empresa (servidores, bases de datos, aplicaciones, etc.).


#### Políticas
- [Políticas locales](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/security-options) - Estos se aplican a una computadora específica e incluyen la política de auditoría de eventos de seguridad, asignaciones de derechos de usuario (prinarios de usuario en un host), y ajustes de seguridad específicos como la capacidad de instalar conductores, si el administrador y las cuentas de los huéspedes están habilitados, renombrando las cuentas de los huéspedes y administradores, evitando que los usuarios instale impresoras o utilicen medios extraíbles, y una variedad de controles de acceso a la red y seguridad de la red.
    
- [Políticas de restricción de software](https://docs.microsoft.com/en-us/windows-server/identity/software-restriction-policies/software-restriction-policies) - Configuraciones para controlar qué software se puede ejecutar en un host.
    
- [Políticas de control](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) de [aplicaciones](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) - Configuración para controlar qué aplicaciones pueden ser ejecutadas por ciertos usuarios/grupos. Esto puede incluir bloquear a ciertos usuarios de ejecutar todos los ejecutables, archivos de Instalo de Windows, scripts, etc. Los administradores utilizan [AppLocker](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) para restringir el acceso a ciertos tipos de aplicaciones y archivos. No es raros ver a las organizaciones bloquear el acceso a CMD y PowerShell (entre otros ejecutables) para los usuarios que no los requieren para su trabajo diario. Estas políticas son imperfectas y a menudo pueden ser sorteadas pero necesarias para una estrategia de defensa en profundidad.
    
- [Configuración](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/secpol-advanced-security-audit-policy-settings) de [la Política](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/secpol-advanced-security-audit-policy-settings) de [Auditoría](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/secpol-advanced-security-audit-policy-settings) Avanzada - Una variedad de configuraciones que se pueden ajustar a actividades de auditoría tales como acceso o modificación de archivos, inicio de cuentas/logoff, cambios de políticas, uso de privilegios y más.


#### Gestión de la actualización (SCCM/WSUS)

La gestión adecuada de los parches es fundamental para cualquier organización, especialmente para aquellos que ejecutan sistemas Windows/Directory Active. El [Servicio de Actualización de Servidor de Windows (WSUS)](https://docs.microsoft.com/en-us/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus) se puede instalar como un rol en un servidor de Windows y se puede utilizar para minimizar la tarea manual de parchear los sistemas Windows. `System Center Configuration Manager`(SCCM) es una solución de pago que se basa en el rol de Windows Server WSUS que se está instalando y ofrece más características que WSUS por sí sola.


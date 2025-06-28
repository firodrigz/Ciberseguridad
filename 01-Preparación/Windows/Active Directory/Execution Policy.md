```powershell-session
PS C:\htb> get-alias

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           CFS -> ConvertFrom-String                          3.1.0.0    Microsoft.PowerShell.Utility
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
Alias           cli -> Clear-Item
Alias           clp -> Clear-ItemProperty
```


|**Política**|**Descripción**|
|---|---|
|`AllSigned`|Todos los scripts pueden ejecutarse, pero un editor de confianza debe firmar scripts y archivos de configuración. Esto incluye guiones remotos y locales. Recibimos un aviso antes de ejecutar guiones firmados por editores que aún no hemos enumerado como de confianza o no de confianza.|
|`Bypass`|No se bloquean scripts ni archivos de configuración, y el usuario no recibe advertencias ni indicaciones.|
|`Default`|Esto establece la política de ejecución por defecto, `Restricted`para máquinas de escritorio de Windows y `RemoteSigned`para servidores de Windows.|
|`RemoteSigned`|Los guiones pueden funcionar pero requiere una firma digital en los scripts que se descargan de internet. Las firmas digitales no son necesarias para los scripts que se escriben localmente.|
|`Restricted`|Esto permite comandos individuales, pero no permite ejecutar scripts. Todos los tipos de archivos de script, incluyendo archivos de configuración (`.ps1xml`), archivos de script del módulo (`.psm1`), y los perfiles de PowerShell (`.ps1`) están bloqueados.|
|`Undefined`|No se establece ninguna política de ejecución para el alcance actual. Si la política de ejecución de TODOS los alcances está sin definir, entonces la política de ejecución por defecto de `Restricted`se usará.|
|`Unrestricted`|Esta es la política de ejecución por defecto para los ordenadores no Windows, y no se puede cambiar. Esta política permite ejecutar scripts sin firmar, pero advierte al usuario antes de ejecutar scripts que no son de la zona de intranet local.|

```powershell-session
PS C:\htb> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

```powershell-session
PS C:\htb> Set-ExecutionPolicy Bypass -Scope Process

Execution Policy Change
The execution policy helps protect you from scripts that you do not trust. Changing the execution policy might expose
you to the security risks described in the about_Execution_Policies help topic at
https:/go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
```


```powershell-session
PS C:\htb>  Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process          Bypass
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

## 🔐 ¿Por qué existe la "Execution Policy"?

Porque **PowerShell quiere protegerte**. Si no hubiera una política, un virus podría hacerte ejecutar un script malicioso sin que te des cuenta.

Por eso, PowerShell tiene una “política de ejecución” que controla **si se permite ejecutar scripts o no, y en qué condiciones**.


## Tipos de ejecución más comunes:

|Política|¿Qué permite?|
|---|---|
|`Restricted`|❌ No permite ejecutar ningún script. (Es la predeterminada en muchos casos).|
|`RemoteSigned`|✅ Permite scripts, pero si vienen de internet tienen que estar firmados.|
|`Unrestricted`|⚠️ Permite cualquier script (no es recomendable en entornos seguros).|

## ¿Qué es el `Scope` y para qué sirve?

El `Scope` es **a quién afecta la política**.

### Ejemplo con la vida real:

Supongamos que estás en una oficina:

- El **dueño del edificio** pone reglas que afectan a todos → eso sería `LocalMachine`.    
- Un **usuario común** (vos) quiere una regla solo para él → eso sería `CurrentUser`.    
- Si abrís una ventana y ponés una regla que se borra cuando la cerrás → eso es `Process`.

### Tabla de Scope:

| Scope          | ¿Quién puede cambiarlo? | ¿Afecta a...?                    |
| -------------- | ----------------------- | -------------------------------- |
| `LocalMachine` | Solo administrador      | A todos los usuarios del sistema |
| `CurrentUser`  | Cualquier usuario       | Solo al usuario actual           |
| `Process`      | Cualquier usuario       | Solo a esa sesión de PowerShell  |

## Ejemplo real:

### Escenario 1 – Usuario sin permisos de admin:

Facu quiere ejecutar un script que se bajó de internet, pero PowerShell lo bloquea. Entonces corre esto:

Set-ExecutionPolicy RemoteSigned -Scope CurrentUser

👉 Y con eso ya puede ejecutar scripts **solo para su usuario**.

### Escenario 2 – Admin quiere permitir scripts para todos:

Un administrador IT quiere que todos los usuarios puedan ejecutar scripts firmados:

Set-ExecutionPolicy RemoteSigned -Scope LocalMachine

👉 Pero esto solo lo puede hacer un administrador.


## ⚠️ ¿Entonces se puede cambiar la política cuando uno quiera?

Sí, **siempre y cuando tengas los permisos necesarios**.

- Si sos usuario común: solo podés cambiar `CurrentUser` o `Process`.    
- Si sos administrador: podés cambiar cualquiera, incluso `LocalMachine`.
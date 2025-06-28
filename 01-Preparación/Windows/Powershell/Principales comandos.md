
##### Help

```powershell-session
PS C:\Users\htb-student> Get-Help Test-Wsman

NAME
    Test-WSMan

SYNTAX
    Test-WSMan [[-ComputerName] <string>] [-Authentication {None | Default | Digest | Negotiate | Basic | Kerberos |
    ClientCertificate | Credssp}] [-Port <int>] [-UseSSL] [-ApplicationName <string>] [-Credential <pscredential>]
    [-CertificateThumbprint <string>]  [<CommonParameters>]


ALIASES
    None


REMARKS
    Get-Help cannot find the Help files for this cmdlet on this computer. It is displaying only partial help.
        -- To download and install Help files for the module that includes this cmdlet, use Update-Help.
        -- To view the Help topic for this cmdlet online, type: "Get-Help Test-WSMan -Online" or
           go to https://go.microsoft.com/fwlink/?LinkId=141464.
```


```powershell-session
PS C:\Windows\system32> Update-Help
```

```powershell-session
PS C:\Users\DLarusso> Get-Location

Path
----
C:\Users\DLarusso
```

```powershell-session
PS C:\htb> Get-ChildItem 

Directory: C:\Users\DLarusso


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/26/2021  10:26 PM                .ssh
d-----         1/28/2021   7:05 PM                .vscode
d-r---         1/27/2021   2:44 PM                3D Objects
d-r---         1/27/2021   2:44 PM                Contacts
d-r---         9/18/2022  12:35 PM                Desktop
d-r---         9/18/2022   1:01 PM                Documents
d-r---         9/26/2022  12:27 PM                Downloads
d-r---         1/27/2021   2:44 PM                Favorites
d-r---         1/27/2021   2:44 PM                Music
dar--l         9/26/2022  12:03 PM                OneDrive
d-r---         5/22/2022   2:00 PM                Pictures
```


```powershell-session
PS C:\htb>  Set-Location .\Documents\

PS C:\Users\tru7h\Documents> Get-Location

Path
----
C:\Users\DLarusso\Documents
```


```powershell-session
PS C:\htb> Get-Content Readme.md  

# ![logo][] PowerShell

Welcome to the PowerShell GitHub Community!
PowerShell Core is a cross-platform (Windows, Linux, and macOS) automation and configuration tool/framework that works well with your existing tools and is optimized
for dealing with structured data (e.g., JSON, CSV, XML, etc.), REST APIs, and object models.
It includes a command-line shell, an associated scripting language and a framework for processing cmdlets. 
```

| **Command**      | **Alias**        | **Description**                                                                                        |
| ---------------- | ---------------- | ------------------------------------------------------------------------------------------------------ |
| `Get-Item`       | gi               | Recuperar un objeto (podría ser un archivo, carpeta, objeto de registro, etc.)                         |
| `Get-ChildItem`  | ls / dir / gci   | Lista el contenido de una carpeta o colmena de registro.                                               |
| `New-Item`       | md / mkdir / ni  | Crear nuevos objetos. (pueden ser archivos, carpetas, enlaces de symlinks, entradas de registro y más) |
| `Set-Item`       | si               | Modificar los valores de propiedad de un objeto.                                                       |
| `Copy-Item`      | copy / cp / ci   | Haz un duplicado del artículo.                                                                         |
| `Rename-Item`    | ren / rni        | Cambia el nombre del objeto.                                                                           |
| `Remove-Item`    | rm / del / rmdir | Elimina el objeto.                                                                                     |
| `Get-Content`    | cat / type       | Muestra el contenido dentro de un archivo u objeto.                                                    |
| `Add-Content`    | ac               | Agregar contenido a un archivo.                                                                        |
| `Set-Content`    | sc               | Sobrescribe cualquier contenido en un archivo con nuevos datos.                                        |
| `Clear-Content`  | clc              | Borrar el contenido de los archivos sin borrar el archivo en sí.                                       |
| `Compare-Object` | diff / compare   | Compare dos o más objetos entre sí. Esto incluye el objeto en sí y el contenido interior.\|            |

Encontrar un archivo específico

``` powershell
Get-ChildItem -Path F:\ -Recurse -File archivo.png
```

**Estás consultando al Active Directory** para obtener el **nombre de pila (GivenName)** de los usuarios cuyo **apellido (Surname)** es exactamente `"Flag"`

``` powershell
Get-ADUser -Filter {Surname -eq "Flag"} -Properties GivenName | Select-Object GivenName
```



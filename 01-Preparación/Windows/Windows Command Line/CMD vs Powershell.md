Una diferencia clave es que usted puede ejecutar comandos de comando Prompt de una consola PowerShell, pero para ejecutar los comandos de PowerShell desde un Comando Prompt, usted tendría que prefacio el comando con `powershell`(es decir, `powershell get-alias`).


|PowerShell|Comando Prompt|
|---|---|
|Introducido en 2006|Introducido en 1981|
|Puede ejecutar tanto comandos por lotes como PowerShell cmdlets|Sólo pueden ejecutar comandos por lotes|
|Soporta el uso de alias de mando|No apoya alias de mando|
|La salida de Cmdlet se puede pasar a otros cmdlets|La salida de comando no se puede pasar a otros comandos|
|Toda salida está en forma de objeto|La salida de comandos es texto|
|Capaz de ejecutar una secuencia de cmdlets en un script|Un comando debe terminar antes de que el siguiente comando pueda funcionar|
|Tiene un entorno de scripting integrado (ISE)|No tiene un ISE|
|Puede acceder a las bibliotecas de programación porque se construye sobre el . Marco de laNET|No se puede acceder a estas bibliotecas|
|Se puede ejecutar en sistemas Linux|Sólo se puede ejecutar en sistemas Windows|


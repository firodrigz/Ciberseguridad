### Pirámide del dolor
<p align="center"> 
<img src="https://i.postimg.cc/DwVxXrkD/image.png" alt="Diamond-Model"/>
</p>
### HASHES

Es muy fácil detectar un archivo malicioso si tenemos el hash en nuestro arsenal. Sin embargo, como atacante, modificar un archivo incluso en un solo bit es trivial, lo que produciría un valor hash diferente. Con tantas variaciones e instancias de malware o ransomware conocidos, la búsqueda de amenazas mediante hashes de archivos como los IOC (indicadores de compromiso) puede resultar difícil.

```powershell
PS C:\Users\THM\Downloads> Get-FileHash .\OpenVPN_2.5.1_I601_amd64.msi -Algorithm MD5
Algorithm Hash                             Path                                                 
_________ ____                             ____                                                 
MD5       D1A008E3A606F24590A02B853E955CF7 C:\Users\THM\Downloads\OpenVPN_2.5.1_I601_amd64.msi
```

#### Hash de archivo (después de la modificación)

```powershell

PS C:\Users\THM\Downloads> echo "AppendTheHash" >> .\OpenVPN_2.5.1_I601_amd64.msi
PS C:\Users\THM\Downloads> Get-FileHash .\OpenVPN_2.5.1_I601_amd64.msi -Algorithm MD5
Algorithm Hash                             Path                                                 
_________ ____                             ____                                                 
MD5       9D52B46F5DE41B73418F8E0DACEC5E9F C:\Users\THM\Downloads\OpenVPN_2.5.1_I601_amd64.msi
```

#### DIRECCIÓN IP
Una de las formas en que un adversario puede dificultar el bloqueo de IP con éxito es mediante el uso de Fast Flux.

Según [Akamai](https://blogs.akamai.com/2017/10/digging-deeper-an-in-depth-analysis-of-a-fast-flux-network-part-one.html), Fast Flux es una técnica de DNS utilizada por las botnets para ocultar el phishing, el proxy web, la entrega de malware y las actividades de comunicación de malware detrás de hosts comprometidos que actúan como proxies. El propósito de usar la red Fast Flux es hacer que la comunicación entre el malware y su servidor de comando y control (C&C) sea difícil de descubrir por los profesionales de la seguridad.

Por lo tanto, el concepto principal de una red Fast Flux es tener múltiples direcciones IP asociadas con un nombre de dominio, que cambia constantemente.


#### NOMBRES DE DOMINIO
Este es uno de los ejemplos de un ataque Punycode utilizado por los atacantes para redirigir a los usuarios a un dominio malicioso que parece legítimo a primera vista.

¿Qué es Punycode? Según [Wandera](https://www.wandera.com/punycode-attacks/), "Punycode es una forma de convertir palabras que no se pueden escribir en ASCII, en una codificación ASCII Unicode".

Lo que viste en la URL anterior es que tiene el Punycode de `adıdas.de``http://xn--addas-o4a.de/`

Los atacantes suelen ocultar los dominios maliciosos en **acortadores de URL.** Puede ver el sitio web real al que lo redirige el enlace acortado agregándole "+" (vea los ejemplos a continuación). Escriba la URL abreviada en la barra de direcciones del navegador web y agregue los caracteres anteriores para ver la URL de redireccionamiento.

#### ARTEFACTOS DE HOST
Los artefactos de host son los rastros u observables que los atacantes dejan en el sistema, como los valores del registro, la ejecución de procesos sospechosos, los patrones de ataque o IOC (indicadores de compromiso), los archivos eliminados por aplicaciones maliciosas o cualquier cosa exclusiva de la amenaza actual.

#### ARTEFACTOS DE RED
Un artefacto de red puede ser una cadena de agente de usuario, información C2 o patrones de URI seguidos de las solicitudes HTTP POST. Un atacante puede usar una cadena User-Agent que no se ha observado antes en su entorno o que parece fuera de lo común. El User-Agent se define por [RFC2616](https://datatracker.ietf.org/doc/html/rfc2616#page-145) como el campo de encabezado de solicitud que contiene la información sobre el agente de usuario que origina la solicitud.

#### HERRAMIENTAS
Los atacantes utilizarían las utilidades para crear documentos macro maliciosos (maldocs) para intentos de spearphishing, una puerta trasera que se puede utilizar para establecer [C2 (Infraestructura de Comando y Control),](https://www.varonis.com/blog/what-is-c2/) cualquier .EXE personalizada y .Archivos DLL, cargas útiles o descifradores de contraseñas.
El **hash difuso** también es un arma poderosa contra las herramientas del atacante. El hash aproximado le ayuda a realizar un análisis de similitud: haga coincidir dos archivos con diferencias menores en función de los valores hash difusos. Uno de los ejemplos de hash difuso es el uso de [SSDeep](https://ssdeep-project.github.io/ssdeep/index.html); en el sitio web oficial de SSDeep, también puede encontrar la explicación completa del hash difuso.

#### TTP
Tácticas, Técnicas y Procedimientos. Esto incluye toda la [matriz MITRE](https://attack.mitre.org/) [ATT&CK](https://attack.mitre.org/), es decir, todos los pasos que da un adversario para lograr su objetivo, desde los intentos de phishing hasta la persistencia y la exfiltración de datos.

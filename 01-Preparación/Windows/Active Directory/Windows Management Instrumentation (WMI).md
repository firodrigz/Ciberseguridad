
Determinar información del sistema operativo utilizando WMI

```cmd-session
C:\htb> wmic os list brief

BuildNumber  Organization  RegisteredUser  SerialNumber             SystemDirectory      Version
19041                      Owner           00123-00123-00123-AAOEM  C:\Windows\system32  10.0.19041
```

SID

```cmd-session
C:\htb> wmic useraccount get name,sid

Name        SID
Jim         S-1-5-21-2614195641-1726409526-3792725429-1006
```


SID GROUP

```cmd-session
C:\htb> wmic group get name,sid

Name        SID
HR         S-1-5-21-2614195641-1726409526-3792725429-1007
```
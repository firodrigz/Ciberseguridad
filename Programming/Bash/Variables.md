

```shell-session
firodrigz@htb[/htb]$ variable="Declared without an error."
firodrigz@htb[/htb]$ echo $variable

Declared without an error.
```

Arrays

```bash
#!/bin/bash

domains=(www.inlanefreight.com ftp.inlanefreight.com vpn.inlanefreight.com www2.inlanefreight.com)

echo ${domains[0]}
```


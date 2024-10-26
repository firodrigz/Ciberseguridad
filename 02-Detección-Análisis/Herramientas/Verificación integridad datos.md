hashes ->echo -n 'contenido de el fichero' | md5sum


cifrado
 echo 'hash' | openssl aes-256-cdc -pbkdf2 -a -d

echo "hash ./loqueinstale.exe" | sha256sum --check -

#### En windows:

``` powershell
Get-FileHash VirtualBox.exe
```

[![Integridad-Hash.png](https://i.postimg.cc/zvLmzJcJ/Integridad-Hash.png)](https://postimg.cc/LgMQvMS7)
#### En linux:

``` bash
sha256sum <file>
```


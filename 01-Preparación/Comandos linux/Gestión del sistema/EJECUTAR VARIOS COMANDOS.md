Hay tres posibilidades para ejecutar varios comandos, uno tras otro. Estos están separados por:

> Punto y coma ( ; )
> Doble ampersand ( && )
> Tuberías ( | )

La diferencia entre ellos radica en el tratamiento de los procesos anteriores y depende de si el proceso anterior se completó con éxito o con errores. El punto y coma ( ;) es un separador de comandos y ejecuta los comandos ignorando los resultados y errores de los comandos anteriores. 

``` bash
echo '1'; ls MISSING_FILE; echo '3'

1
ls: cannot access 'MISSING_FILE': No such file or directory
3
```

Sin embargo, se ve diferente si usamos los caracteres dobles AND ( &&) para ejecutar los comandos uno tras otro. Si hay un error en uno de los comandos, los siguientes no se ejecutarán más y se detendrá todo el proceso. 

``` bash
echo '1' && ls MISSING_FILE && echo '3'

1
ls: cannot access 'MISSING_FILE': No such file or directory
```

Tuberías ( | ) dependen no sólo del funcionamiento correcto y sin errores de los procesos anteriores sino también de los resultados de los procesos anteriores. 
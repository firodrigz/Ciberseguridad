Podemos pasarle hasta 9 argumentos a un script de bash.

```shell-session
firodrigz@htb[/htb]$ ./script.sh ARG1 ARG2 ARG3 ... ARG9
       ASSIGNMENTS:       $0      $1   $2   $3 ...   $9
```

$# -> Esta variable contiene el número de argumentos pasados al script.

$? -> El estado de salida del script. Esta variable es útil para determinar el éxito de un comando. El valor 0 representa la ejecución exitosa, mientras que 1 es el resultado de un fracaso.



Los procesos se pueden controlar mediante kill, pkill, pgrep, y killall. 

Los más utilizados son:

| Señal | Descripción                                                                                                                              |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | SIGHUP - Este se envía a un proceso cuando el terminal que lo controla está cerrado.                                                     |
| 2     | SIGINT - Enviado cuando un usuario presiona [Ctrl] + C en el terminal de control para interrumpir un proceso.                            |
| 3     | SIGQUIT - Enviado cuando un usuario presiona [Ctrl] + D para dejar de fumar.                                                             |
| 9     | SIGKILL - Finalizar inmediatamente un proceso sin operaciones de limpieza.                                                               |
| 15    | SIGTERM - Terminación del programa.                                                                                                      |
| 19    | SIGSTOP - Detener el programa. Ya no se puede manejar.                                                                                   |
| 20    | SIGTSTP - Enviado cuando un usuario presiona [Ctrl] + Z para solicitar la suspensión de un servicio. El usuario puede manejarlo después. |

Por ejemplo, si un programa se congelara, podríamos forzar su finalización con el siguiente comando: 

``` bash
kill 9 <PID> 
```

El [Ctrl] + Z El acceso directo suspende los procesos y no se ejecutarán más. Para que siga ejecutándose en segundo plano, debemos ingresar el comando bg para poner el proceso en segundo plano. 


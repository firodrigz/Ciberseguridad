1. **Modificar el archivo**

   `nano ~/.bashrc`

2. **Encuentra la variable PS1**, que define el prompt de Bash. Si no existe, puedes añadirla al final del archivo.
   
3. **Personaliza la variable PS1** con los caracteres especiales para la información que quieras mostrar. Por ejemplo:
   
   `PS1="\u@\h \w $(date +'%Y-%m-%d %H:%M:%S') \[\033[01;32m\]\$?\[\033[00m\] \$ "`
  
   En este ejemplo:
   
   - `\u` muestra el nombre del usuario actual.
   - `\h` muestra el nombre del host.
   - `\w` muestra la ruta completa del directorio de trabajo actual.
   - `$(date +'%Y-%m-%d %H:%M:%S')` ejecuta un comando para mostrar la fecha y hora actuales.
   - `\$?` muestra el estado de salida del último comando ejecutado.

4. **Guarda y cierra el archivo `.bashrc`**.
   
5. **Aplica los cambios** ejecutando:

   `source ~/.bashrc`

[Bash Prompt Generator](https://bash-prompt-generator.org/)
[powerline/powerline: Powerline is a statusline plugin for vim, and provides statuslines and prompts for several other applications, including zsh, bash, tmux, IPython, Awesome and Qtile.](https://github.com/powerline/powerline)

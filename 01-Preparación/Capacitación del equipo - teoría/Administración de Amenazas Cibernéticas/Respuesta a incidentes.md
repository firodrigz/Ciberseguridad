# Cuando se produce un incidente de seguridad es importante recopilar información para ver el alcance del mismo.

Se deben saber y respetar los requisitos para la preservación de la información recolectada.

### Proceso forense de evidencia digital
- **Recolección**: identificación, obtención, manejo y almacenamiento de los datos. (Cadena de custodia)
- **Exámen**: evaluar (descompresión y desencriptado). Se elimina información irrelevante. 
- **Análisis**: Relacionado a sacar conclusiones de datos. 
- **Informes**: documentar incluyendo limitaciones de análisis y problemas surgidos en el proceso.   
## Tipos de evidencia
Evidencia directa (dispositivos del acusado o archivos que se pueden probar que no fueron alterados o algún testigo) o indirecta (pruebas que demuestren que el individuo involucrado tuvo delitos anteriormente similares).
## Orden de recolección de la evidencia
Debe comenzar con las pruebas más volátiles hasta llegar a las menos volátiles.
- Contenido de la RAM
- Contenido de discos fijos    
- Datos de copia de respaldo archivados
Ej:
Registros de memoria, memoria caché
Tabla de routing, caché de ARP, tabla de procesos, estadísticas del núcleo, memoria RAM
Sistemas de archivos temporales
Medios no volátiles, fijos y extraíbles
Registros remotos y datos de monitoreo
Topologías e interconexiones físicas
Medios de archivado, cinta u otros tipos de copias de respaldo
  
## Cadena de custodia
La cadena de custodia implica la recolección, el manejo y el almacenamiento seguro de la evidencia.

- ¿Quién descubrió y recopiló la evidencia?
- Todos los detalles sobre el manejo de la evidencia, incluidos momentos, lugares y personal involucrado.
- ¿Quién era el responsable principal de la evidencia, cuándo se le asignó la responsabilidad y cuándo cambió la custodia?
- Quién tiene acceso físico a la evidencia mientras está almacenada. El acceso debe limitarse solamente al personal esencial.
  
Es importante hacer una copia del disco o artefacto a analizar para mantener la integridad del original.

Es importante que usuarios no apaguen, desconecten, reinicien máquinas infectadas ya que el principal medio de recolección de datos más volátil se borrarian evidencias/huellas. 

Uno de los objetivos es identificar a los actores de amenaza (puede ser un individuo, grupo, gobierno, organización)

El equipo recopila los TTP utilizados por los atacantes para aprender y perfeccionar sus sistemas.

Por eso también es importante la administración de activos ya que esto ayuda mucho a la hora de analizar ataques de origen interno.

## Recopilar información volátil del sistema comprometido.
En este paso, creará un archivo llamado report.txt que incluye una variedad de información del sistema que puede utilizarse para el análisis de incidentes. Este informe puede transferirse a una unidad USB, enviarse por correo electrónico o cargarse en un servidor en la nube para conservar la información. Luego, se puede desactivar el sistema.

a.   Cambie al usuario root con el comando sudo su. Introduzca password como la contraseña de raíz
cisco @ labvm: ~ $ sudo su
[sudo ] password for cisco: password
root@labvm:/home/cisco#

 b.   Ingrese el comando echo y especifique un encabezado para un archivo recién creado llamado report.txt. Ingrese el comando cat para revisar el nuevo archivo. 
root@labvm:/home/cisco# echo Informe de Incidente del Investigador > report.txt
root@labvm:/home/cisco# cat report.txt

Informe de Incidente del Investigador
root@labvm:/home/cisco# 

 c.    Ingrese el comando date y redirija la fecha y la marca de tiempo al archivo report.txt. Asegúrese de utilizar corchetes de doble ángulo (>>) para agregar al archivo report.txt. De lo contrario, reemplazará el contenido anterior.
Nota: Para documentar mejor el contenido almacenado en report.txt, utilice el comando echo para agregar un subencabezado como se muestra aquí para la Fecha y hora de inicio. Cada subpaso especificará un subencabezado para que agregue antes de recopilar información.  

root@labvm:/home/cisco# echo===== Fecha y hora de inicio ===== >> report.txt
root@labvm:/home/cisco#date >> report.txt  

 d.   Ingrese el comando uname para imprimir la información del sistema. Utilice la opción -a para agregar toda la información del sistema al archivo report.txt.
root@labvm:/home/cisco# echo ===== Información del sistema ===== >> report.txt
root@labvm:/home/cisco# uname -a >> report.txt

 e.   Ingrese el comando ifconfig -a y agregue toda la información de la interfaz de red al archivo report.txt.
root@labvm:/home/cisco# echo ===== Interfaces de red ===== >> report.txt
root@labvm:/home/cisco# ifconfig -a >> report.txt  

 f.     El comando netstat puede recopilar todas las estadísticas de la red. Ingrese el comando con las opciones -ano para recopilar datos en todos los sockets (-a), direcciones IP en lugar de nombres de dominio (-n) e información relacionada con los tiempos de red (-o). Agregue la salida al archivo report.txt.
root@labvm:/home/cisco# echo ===== Estadísticas de red ===== >> report.txt
root@labvm:/home/cisco# netstat -ano >> report.txt  

 g.   El comando ps reporta una foto de los procesos actuales que se ejecutan en el sistema. Ingrese el comando con las opciones -axu para enumerar todos los procesos que se ejecutan en el sistema (-a y -x) y en un formato orientado al usuario (-u). Agregue la salida al archivo report.txt.
root@labvm:/home/cisco# echo ===== Procesos ===== >> report.txt
root@labvm:/home/cisco# ps axu >> report.txt 

 h.   El comando route enumera la tabla de enrutamiento utilizada actualmente por el sistema. Ingrese el comando con la opción -n para enumerar las direcciones IP en lugar de intentar determinar los nombres de host. Agregue la salida al archivo report.txt.  
root@labvm:/home/cisco# echo ===== Tabla de Enrutamiento ===== >> report.txt
root@labvm:/home/cisco# route -n >> report.txt  

 i.     Ingrese el comando date y agregue la fecha y la marca de hora al final del archivo para completar el informe.
root@labvm:/home/cisco# echo ===== Fecha y hora de finalización ===== >> report.txt
root@labvm:/home/cisco# date >> report.txt  

 j.     Utilice el comando cat y canalice la salida al comando less para ver report.txt página o una línea a la vez. Presione la barra espaciadora para desplazarse hacia abajo por página o presione Intro (Enter) para desplazarse hacia abajo una sola línea. Ingrese q cuando haya terminado
root@labvm:/home/cisco# cat report.txt | less

## Analizar diferentes archivos de registro y conocer su importancia.
Además de capturar la información almacenada en la RAM, el sistema también mantiene una variedad de registros que debe revisar después de un incidente. Estos archivos de registro también pueden agregarse a su archivo report.txt o almacenarse por separado del sistema en caso de que el sistema deba eliminarse. Los registros de particular interés incluyen, entre otros, los siguientes:

●   auth.log - registra información de autorización del sistema
●   btmp.log - registra intentos fallidos de inicio de sesión
●   wtmp.log - registra quién ha iniciado sesión actualmente en el sistema  

 a.   Utilice el comando cat para ver auth.log y canalizarlo al comando less. Presione la barra espaciadora para desplazarse hacia abajo por página o presione Intro para desplazarse hacia abajo una sola línea. Ingrese q cuando haya terminado Su salida será diferente.  

 El último comando muestra una lista de los últimos usuarios conectados. Ingrese el comando con la opción -f para especificar el archivo de registro. El archivo de registro btmp muestra intentos fallidos de inicio de sesión. Su salida será diferente.
root@labvm:/home/cisco# last -f /var/log/btmp 

 Ingrese el comando last nuevamente especificando el archivo wtmp para mostrar quién está actualmente conectado al sistema. Su salida será diferente.
root@labvm:/home/cisco# last -f /var/log/wtmp

Ingrese el comando exit para volver al usuario de Cisco.
root@labvm:/home/cisco# exit 

# Cadena de eliminación cibernética (Kill Chain) 

Existen 7 pasos. Lo importante es intentar detener el ataque en los primeros pasos de la cadena. 

- Reconocimiento   
- Preparación   
- Entregar   
- Aprovechamiento   
- Instalación   
- Comand and control   
- Acciones sobre objetivos

## Modelo de diamante
- Adversario: son las partes responsables de la intrusión
- Capacidad: es una herramienta o técnica que utiliza el adversario
- Infraestructura: ruta o ruta de red que utilizan los adversarios
- Víctima: es el objetivo, que luego puede ser utilizado como un vector de infraestructura para establecer otras víctimas. 

El adversario usa la infraestructura para conectarse con la víctima. El adversario desarrolla la capacidad de explotar a la víctima

## Plan de Recuperación ante Desastres (DRP)

El DRP incluye las actividades que realiza la organización para evaluar, salvar, reparar y restaurar instalaciones o activos dañados.  

## Planificación de la Continuidad del Negocio

Es un plan más amplio que el plan de recuperación ante desastres (DRP), dado que incluye el envío de sistemas críticos a otra ubicación mientras la reparación de la instalación original está en curso.
La creación de un plan de continuidad comercial comienza con la realización de un análisis de impacto comercial (BIA) para identificar procesos comerciales críticos, recursos y relaciones entre sistemas. El BIA se centra en las consecuencias de la interrupción de funciones comerciales críticas y examina las consideraciones clave que se enumeran a continuación.
Los controles de continuidad de los negocios son mucho más que una simple copia de respaldo de los datos y redundancia del hardware. Las organizaciones necesitan empleados para configurar y operar correctamente los sistemas. Los datos pueden ser irrelevantes hasta que proporcionan información.
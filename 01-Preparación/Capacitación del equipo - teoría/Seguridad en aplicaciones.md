### Seguridad en aplicaciones

- El desarrollo de aplicaciones debe realizarse sobre un entorno de prueba, testeada y Aprovisionamiento (creación o actualización de software) y desaprovisionamiento (eliminación)
- Se deben tener cuidado con la reutilización de código para evitar vulnerabilidades
- Usar ofuscación y camuflaje: (Un desarrollador puede utilizar la ofuscación y el camuflaje para evitar que el software sea objeto de ingeniería inversa. La ofuscación oculta los datos originales con caracteres o datos aleatorios. El camuflaje sustituye los datos sensibles por datos ficticios realistas.)
- Evitar usar SDK (kits de desarrollo de soft) y repos para evitar arrastrar vulnerabilidades.

Realizar siempre **validación de entrada de datos** (evitar SQLi). Estos dependen mucho del diseño de la base de datos.
- Tamaño: Controla la cantidad de caracteres en un elemento de datos
- Formato: Controla que los datos se ajusten a un formato específico
- Coherencia: Controla la coherencia de los códigos en los elementos de datos relacionados
- Rango: Controla que los datos se encuentran dentro de un valor mínimo y un valor máximo
- Dígito de control: Proporciona un cálculo adicional para generar un dígito de control para la detección de errores.
 
![Dígito de control](https://i.postimg.cc/44DjKz4f/ddecontrol.png)

#### Controles de integridad

Un **control de integridad** puede medir la consistencia de los datos en un archivo, imagen o registro para garantizar que no se hayan dañado. El control de integridad realiza una **función hash** para tomar una instantánea de los datos y luego utiliza esta instantánea para garantizar que los datos permanezcan sin cambios. Un **checksum** es un ejemplo de una función de hash.  [[Verificación integridad datos]]


![Controles de integridad](https://i.postimg.cc/9QpkNKd0/contorlesdeintegridad.png)


##### Autorización
Se debe gestionar de manera correcta quien tiene acceso a ciertos ficheros

##### La **firma de código** 
valida digitalmente que el código del software no ha cambiado y es auténtico.

##### Las **cookies seguras** 
almacenan datos de forma segura para futuras solicitudes mientras se navega por un sitio web.

La disponibilidad es algo crucial por lo que se aplican políticas de los 5 nueves osea el 99,999% debe estar disponible la información. Para esto hay puntos de redundancia en los activos de una empresa y configuraciones antibucles. También existe la copia de seguridad de la información de forma periódica.

Los dispositivos tienen medidas de temperaturas a respetar, al igual que deben tenerse en cuenta apagones o problemas eléctricos.
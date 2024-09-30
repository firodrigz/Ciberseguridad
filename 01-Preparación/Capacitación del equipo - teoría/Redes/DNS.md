El DNS (Sistema de Nombres de Dominio) nos proporciona una forma sencilla de comunicarnos con dispositivos en Internet sin recordar números complejos.

**TLD (Dominio de Nivel Superior)

Un TLD es la parte más a la derecha de un nombre de dominio

- gTLD  (Generic Top Level): propósito del nombre de dominio (.com)
- ccTLD  (Country Code Top Level Domain): fines geográficos (.ar)

**Dominio de segundo nivel**

Tomando tryhackme.com como ejemplo, la parte .com es el TLD, y tryhackme es el dominio de segundo nivel. Al registrar un nombre de dominio, el dominio de segundo nivel está limitado a 63 caracteres + el TLD y solo puede usar a-z 0-9 y guiones (no puede comenzar ni terminar con guiones ni tener guiones consecutivos).

**Subdominio**  

Un subdominio se encuentra en el lado izquierdo del dominio de segundo nivel usando un punto para separarlo.
 Un nombre de subdominio tiene las mismas restricciones de creación que un dominio de segundo nivel, ya que está limitado a 63 caracteres y solo puede usar a-z 0-9 y guiones (no puede comenzar ni terminar con guiones ni tener guiones consecutivos). Puede usar varios subdominios divididos con puntos para crear nombres más largos, como jupiter.servers.tryhackme.com. Pero la longitud debe mantenerse en 253 caracteres o menos. No hay límite en el número de subdominios que puedes crear para tu nombre de dominio.

![[Pasted image 20240218163728.png]]

### Formato de mensajes DNS

![[Pasted image 20240221022816.png]]

## Comando para resolución de dominios

nslookup website.thm

### Forma de saber que contiene un acortador de links

https://tinyurl.com/bw7t8p4u+ IMPORTANTE AGREGAR EL "+" PARA QUE DESCIFRE LA URL VERDADERA.
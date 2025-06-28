#### Kerberos
Es un estándar. Cuando un usuario inicia sesión en su PC, Kerberos se utiliza para autenticarlos a través de la autenticación mutua, o tanto el usuario como el servidor verifican su identidad.
El boleto Kerberos Tickets (TGS) se basa en un tickets válido de Tickets (TGT). Supone que si el usuario tiene una TGT válida, debe haber probado su identidad.

Ejemplo para entender:
- **Kerberos** es como un guardia mágico en la entrada que te da un pase especial (llamado "ticket") si demuestras que eres quien dices ser.
- Con ese pase, puedes entrar y moverte por diferentes partes del castillo sin tener que demostrar quién eres otra vez.

#### DNS
DNS se utiliza para resolver nombres de host a direcciones IP y se utiliza ampliamente entre redes internas e internet.

#### LDAP
LDAP es cómo los sistemas en el entorno de la red pueden "hablar" con AD

Ejemplo para entender:

Piensa en un gran directorio telefónico de una escuela.
- **LDAP** es como ese directorio, pero en lugar de números de teléfono, guarda información sobre quiénes son los estudiantes, los profesores, dónde están sus casilleros y qué pueden hacer en la escuela.
- Si necesitas encontrar a alguien o saber si tienes permiso para usar algo, consultas este directorio.

#### MSRPC
Microsoft de Remote Procedure Call (RPC) 

Ejemplo para entender:
Imagina que varias personas están trabajando juntas en un proyecto, y necesitan pasarse notas de un lado a otro para coordinarse.

- **MSRPC** es como el sistema de mensajería que usan las computadoras para hablar entre ellas y asegurarse de que todo funciona correctamente, como compartir archivos o impresoras.

#### NTLM
Además de Kerberos y LDAP, Active Directory utiliza varios otros métodos de autenticación que pueden ser utilizados (y abusados) por aplicaciones y servicios en AD.  NTLM son protocolos de autenticación que utilizan el hash LM o NT. 

Ejemplo para entender:
Supongamos que tienes una contraseña secreta para entrar a un club.

- **NTLM** es el método que usa el club para asegurarse de que tu contraseña es correcta. Aunque ya no es el sistema más moderno, sigue funcionando en algunos lugares.

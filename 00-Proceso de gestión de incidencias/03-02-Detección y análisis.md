### Detección:

La fase involucra todos los aspectos de la detección de un incidente, como la utilización de sensores, registros y personal capacitado. También incluye el intercambio de información y conocimientos, así como la utilización de inteligencia de amenazas basada en el contexto. La segmentación de la arquitectura y tener una comprensión clara y visibilidad dentro de la red también son factores importantes.`detection & analysis`

### Niveles de detección

- Detección en el perímetro de la red (mediante firewalls, sistemas de detección/prevención de intrusiones en la red orientados a Internet, zona desmilitarizada, etc.)
- Detección a nivel de red interna (mediante firewalls locales, sistemas de detección/prevención de intrusiones en hosts, etc.)
- Detección a nivel de endpoint (utilizando sistemas antivirus, sistemas de detección y respuesta de endpoints, etc.)
- Detección a nivel de aplicación (mediante registros de aplicaciones, registros de servicio, etc.)
### Investigación inicial

- Fecha/hora en que se reportó el incidente. Además, ¿quién detectó el incidente y/o quién lo reportó?
- ¿Cómo se detectó el incidente?
- ¿Cuál fue el incidente? ¿Phishing? ¿Indisponibilidad del sistema? etc.
- Reúna una lista de los sistemas afectados (si corresponde)
- Documente quién ha accedido a los sistemas afectados y qué acciones se han tomado. Tome nota de si se trata de un incidente en curso o si la actividad sospechosa se ha detenido
- Ubicación física, sistemas operativos, direcciones IP y nombres de host, propietario del sistema, propósito del sistema, estado actual del sistema
- (Si se trata de malware) Lista de direcciones IP, hora y fecha de detección, tipo de malware, sistemas afectados, exportación de archivos maliciosos con información forense sobre ellos (como hashes, copias de los archivos, etc.)

### Preguntas sobre la gravedad y el alcance del incidente

A la hora de gestionar un incidente de seguridad, también debemos intentar responder a las siguientes preguntas para hacernos una idea de la gravedad y el alcance del incidente:

- ¿Cuál es el impacto de la explotación?
- ¿Cuáles son los requisitos de explotación?
- ¿Puede algún sistema crítico para el negocio verse afectado por el incidente?
- ¿Hay alguna medida de corrección sugerida?
- ¿Cuántos sistemas se han visto afectados?
- ¿Se está utilizando el exploit en la naturaleza?
- ¿Tiene el exploit alguna capacidad similar a la de un gusano?


### Investigación: 
Es importante saber el cómo se llegó a concretar un ataque y solo remediar /reconstruir los sist afectados xq la vulnerabilidad puede ser nuevamente aprovechada.

Consiste en 3 procesos cíclicos:
- Creación y utilización de indicadores de compromiso (COI)
- Identificación de nuevos clientes potenciales y sistemas impactados
- Recopilación y análisis de datos de los nuevos clientes potenciales y los sistemas afectados

1.Los indicadores de compromiso (IOCs, por sus siglas en inglés) en ciberseguridad son una serie de datos o eventos que pueden indicar que un sistema ha sido comprometido por un atacante. Estos indicadores pueden incluir direcciones IP, nombres de dominio, archivos maliciosos, patrones de tráfico de red, comportamiento anómalo de usuarios, entre otros.
Es importante destacar que los IOCs no siempre indican una amenaza real y, por lo tanto, deben ser verificados y validados antes de tomar cualquier medida.
Los indicadores de compromiso (IOCs) más importantes en ciberseguridad varían dependiendo del tipo de amenaza y del contexto en el que se encuentre el sistema o la red. A continuación, se presentan algunos ejemplos de IOCs comunes:

- Direcciones IP maliciosas: son direcciones IP que han sido identificadas como fuente de ataques o como destino de comunicaciones maliciosas. Estas direcciones se pueden encontrar en listas negras y en feeds de inteligencia de amenazas.

- Nombres de dominio maliciosos: son nombres de dominio utilizados por los atacantes para alojar sitios web maliciosos o para enviar correos electrónicos de phishing. Estos nombres de dominio se pueden encontrar en listas negras y en feeds de inteligencia de amenazas.

- Hashes de archivos maliciosos: son valores numéricos que se calculan a partir del contenido de un archivo. Los hashes se utilizan para identificar archivos maliciosos conocidos y para detectar variantes de malware.

- Patrones de tráfico de red anómalos: son patrones de tráfico que se desvían del comportamiento normal de la red. Estos patrones se pueden utilizar para detectar actividades maliciosas, como el robo de datos o el control remoto de un sistema.

- Comportamiento anómalo de usuarios: son actividades de usuarios que se desvían del comportamiento normal de la organización. Estas actividades se pueden utilizar para detectar ataques de phishing, ingeniería social y otros tipos de ataques dirigidos.

IoA (Indicadores de ataque): Se centran en la posibilidad de que una acción o acontecimiento pueda representar una amenaza. Actúan conjuntamente.

2.Los IoC pueden relevar otros sistemas comprometidos asociados o no al incidente investigado.

3.Los datos se pueden recopilar "en vivo" o una vez apagado, aunque este último puede no preservar data importante ya que suele almacenarse en memoria RAM. Se debe evitar la alteración de la evidencia. El análisis y la recopilación se debe hacer mediante una cadena de custodia digital.






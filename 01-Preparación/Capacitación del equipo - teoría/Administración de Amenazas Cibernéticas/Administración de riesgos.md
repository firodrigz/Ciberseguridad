## Administración de riesgos  

- **Identificar riesgos**: identificar activos, vulnerabilidades y amenazas.
- **Evaluación de riesgos**: Puntuación, ponderar, priorizar (riesgos inherentes, riesgos residuales).
- **Planificación de respuestas de riesgos**: determinar una respuesta/tratamiento para disminuir el riesgo inherente.
- **Implementación de la respuesta**: donde se produce el riesgo residual.
- **Monitoreo y revisión**: hacer un seguimiento de los riesgos y la efectividad de las estrategias planteadas de mitigación, ajustándolas en caso de tener que adaptarse a nuevas amenazas o cambios en el entorno.  

¿Quiénes son los actores de amenaza que quieren atacarnos?
¿Qué vulnerabilidades pueden explotar los actores de amenazas?
¿Cómo pueden afectarnos los ataques?
¿Cuál es la probabilidad de que ocurran diferentes ataques?  

Uno de los objetivos es identificar amenazas y vulnerabilidades y vincularlas entre sí en un proceso llamado T-V, threat-vulnerability. Relación con riesgo inherente.  

## Respuesta a riesgos:

- **Evitar el riesgo**: Dejar de realizar las actividades que conllevan el riesgo. El riesgo supera al beneficio de una actividad. (ELIMINAR)
- **Reducción de riesgos**: Se toman medidas de mitigación. Ej: aplicar parches de seguridad a servidores objetivos ni bien se detecten vulnerabilidades. (MITIGAR)
- **Riesgo compartido**: Transferir parte del riesgo a otras partes(áreas y/o terceros). Ej: contratar un CSIRT(es un equipo especializado en la gestión y respuesta a incidentes de seguridad informática) de seguridad para realizar monitoreo. (TRANSFERIR)
- **Retención de riesgo**: Aceptar el riesgo y sus consecuencias. Son aquellos riesgos que tienen un impacto potencial bajo y un costo de mitigación o reducción relativamente alto. Otra situación es cuando un riesgo es tán dramático que no queda otra. (ACEPTAR) 

## Administración de vulnerabilidades

- **Descubrir**: inventariado de activos.
- **Priorizar activos**: clasificación en grupos y asignarles un valor según el negocio de la empresa.
- **Evaluar**: determinar un perfil de riesgo teniendo en cuenta la priorización del activo, criticidad, vulnerabilidad, amenazas.
- **Informar**:evaluar riesgo teniendo en cuenta políticas de seguridad de la empresa. Documentar plan de seguridad, monitorear y descubrir vulnerabilidades conocidas.
- **Corregir**: priorizar según el riesgo de comercio.
- **Verificar**: seguimiento de remediaciones mediante auditorías. 

## Administración de activos

Las organizaciones deben saber qué equipo tiene acceso a la red, dónde se encuentra ese equipo dentro de la empresa y su posición lógica en la red, y qué software y datos almacenan o usan esos sistemas.
## Administración de configuraciones

La administración de configuraciones se ocupa del inventario y control de configuraciones de hardware y software de los sistemas.  

## Administración de parches

Se debe contemplar la implementación de parches para mitigar las diferentes vulnerabilidades que van surgiendo.
Ej:  Microsoft System Center (Microsoft System Center Configuration Manager SCCM) es una herramienta a nivel empresarial.  

- **Basado en agentes**:un soft está instalado en el host y tiene comunicación directa con el servidor de amdinistración de parches, cuando el soft detecta vulnerabilidad, llama al servidor d administración para aplicar un parche. El es método más utilizado para la implementación de parches en dispositivos móviles.
- **Análisis sin agentes**:el servidor es quien analiza la red en búsqueda de dispositivos sin parche.
- **Monitoreo de red pasivo**:Servidor monitorea a partir del tráfico de red. 

## Tipos de riesgo

El objetivo de la administración de riesgos es reducir estas amenazas a un nivel aceptable e implementar controles para mantener ese nivel.
El riesgo puede ser interno, externo o ambos.
La administración de riesgos es un proceso formal que mide el impacto de una amenaza y el costo de implementar controles o contramedidas para mitigar esa amenaza.
La administración de riesgos reduce la amenaza de daños a un nivel aceptable e implementa controles para mantener ese nivel de riesgo.
El riesgo puede ser interno, externo o ambos, y su impacto puede afectar a toda la organización, afectando también a otras entidades externas.

## Tipos de fuentes de amenaza

Una amenaza es el potencial de que una vulnerabilidad sea identificada y explotada, mientras que un vector de amenaza es la ruta que utiliza un atacante para afectar el objetivo. 

- **Adversarios**: Amenazas de individuos, grupos, organizaciones o naciones.
- **Accidental**: Acciones que se producen sin intención maliciosa.
- **Estructural**: Fallas de equipos y software.
- **Ambiental**: Desastres externos que pueden ser naturales o provocados por el hombre, como incendios e  inundaciones.

## Metodología de evaluación de riesgos

Al evaluar la vulnerabilidad, factores como la facilidad de detección, la explotabilidad, el conocimiento y la detección de intrusiones juegan un papel. Combinación de datos históricos y de estimación para proporcionar la probabilidad más precisa de que se produzca un evento. 

### Análisis de riesgo cuantitativo

### Análisis de riesgo cualitativo
  
## Mitigación de riesgos

Controles técnicos, sistemas de autentificación, permisos de archivos y firewalls, parches, actualizaciones periódicas, desarrollo incremental de software, transferir el riesgo a terceros, adquirir seguros o contratar soporte.

La mitigación puede tener un impacto positivo como negativo. 

- **Controles administrativos**: procedimientos y políticas que organización implementa ante la manipulación de información confidencial.
- **Controles técnicos**: hardware y software implementado para controlar el riesgo.
- **Controles físicos**: cercas, cerraduras, personal de seguridad  

## Controles preventivos
Privilegios de usuarios, un firewall que bloquea puertos o servicios de acceso específicos.
## Controles disuasivos
Objetivo desalentar a que algo suceda. No son como los elementos preventivos que pueden detener por completo la interacción. Ej: Es como poner cámaras de seguridad o un guardia de seguridad.
## Controles de detección
Identifican actividad no autorizada. Van desde sensores de movimiento hasta un sistema de detección de intrusiones. Generan alertas/graban acciones.
## Controles correctivos
Sirven para contrarrestar, restaurar sistemas a la normalidad. Ej: Políticas de seguridad, alarmas, programas antivirus, puertas trampa, planificación de continuidad de negocios.
## Controles de recuperación
Restauran funciones, recursos y capacidades. Ej: operaciones de respaldo/operación, sistemas de unidades con tolerancia a fallas, agrupación de servidores, duplicación de bases de datos.
## Controles compensatorios
Son sustituyen al control ideal que debería de tener una empresa.
# Controles relevantes para el marco de cumplimiento
- PCI DSS
- Marco de Ciberseguridad del NIST
- HIPAA
- GDPR
- ISO/IEC 2001
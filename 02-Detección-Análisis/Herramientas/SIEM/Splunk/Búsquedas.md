Las búsquedas se pueden realizar para buscar comportamientos o eventos extraños extrayendo los logs relevantes para la investigación del caso.

##### Search Terms
- Las búsquedas no son key-sensitive -> fail = FaIL
- AND, OR, NOT
- info="user \"chrisV4\" not in database
- user IN (admin,administrator) = user=admin OR user=administrator


Ejemplo: 
index=network sourcetype=cisco_wsa_squid usage=Violation
| stats count(usage) as Visits by cs_username
| search Visits >1

sourcetype=access_combined failed

##### Knowledge Objects
- Data interpretation
- Data classification
- Data enrichment
- Data normalization
- Data models

Pueden ser creados por un usuario y compartidos a otros usuarios basado en configuraciones de permisos.
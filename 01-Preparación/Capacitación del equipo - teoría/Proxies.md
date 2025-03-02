Un **proxy** es cuando un dispositivo o servicio se sienta en medio de una conexión y actúa como mediador. El mediator es la información crítica porque significa que el dispositivo en el medio debe ser capaz de inspeccionar el contenido del tráfico. Sin la capacidad de ser una mediator, el dispositivo es técnicamente un **gateway**, no un proxy.

Los proxies casi siempre operarán en la capa 7 del Modelo OSI.

**Forward Proxy (Proxy Directo o Dedicado)**
   
   - Se usa para conectar clientes a internet a través de un servidor intermedio (filtra peticiones salientes desde hosts a servidores).
   - Ejemplo: Un proxy HTTP en una empresa que filtra y monitorea el tráfico de los empleados.
   
**Reverse Proxy (Proxy Inverso)**
  
   - Se coloca frente a servidores para manejar peticiones entrantes.
   - Ejemplo: Un proxy inverso que balancea carga entre varios servidores web (ejemplo CloudFlare con su gran capacidad de reducir ataques DDOS) .
   
**Transparent Proxy (Proxy Transparente)**
  
   - Se implementa sin que el usuario lo note.
   - No requiere configuración en el cliente.
   - Ejemplo: Un ISP que usa un proxy para almacenar en caché contenido web y reducir el tráfico externo. Squid utilizado por escuelas para filtrar contenido inapropiado. 

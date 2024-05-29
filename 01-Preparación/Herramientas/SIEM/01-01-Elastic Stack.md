### Elastic Stack 

Se puede usar como una solución de gestión de eventos e información de seguridad (SIEM) para recopilar, almacenar, analizar y visualizar datos relacionados con la seguridad de diversas fuentes.

Para implementar el stack elástico como una solución SIEM, los datos relacionados con la seguridad de varias fuentes, como firewalls, IDS/IPS y endpoints, deben ingerirse en el stack elástico mediante Logstash. Elasticsearch debe configurarse para almacenar e indexar los datos de seguridad, y Kibana debe usarse para crear dashboards y visualizaciones personalizados para proporcionar información sobre eventos relacionados con la seguridad.

### Kibana Query Language (KQL) 

Simplifica el proceso de extracción de información de los datos indexados de Elasticsearch

- `Basic Structure`: Las consultas KQL se componen de pares, en los que el campo representa el atributo de los datos y el valor representa los datos que está buscando. Por ejemplo:`field:value`
  
```shell-session
event.code:4625
```

La consulta KQL filtra los datos en Kibana para mostrar los eventos que tienen el [código de evento de Windows 4625](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4625). Este código de evento de Windows está asociado con intentos fallidos de inicio de sesión en un sistema operativo Windows.`event.code:4625`

Mediante el uso de esta consulta, los analistas de SOC pueden identificar los intentos fallidos de inicio de sesión en máquinas Windows dentro del índice de Elasticsearch e investigar el origen de los intentos y las posibles amenazas de seguridad. Este tipo de consulta puede ayudar a identificar ataques de fuerza bruta, adivinación de contraseñas y otras actividades sospechosas relacionadas con los intentos de inicio de sesión en sistemas Windows.

Al refinar aún más la consulta con condiciones adicionales, como la dirección IP de origen, el nombre de usuario o el intervalo de tiempo, los analistas de SOC pueden obtener información más específica e investigar eficazmente posibles incidentes de seguridad.

- `Free Text Search`: KQL admite la búsqueda de texto libre, lo que le permite buscar un término específico en varios campos sin especificar un nombre de campo. Por ejemplo:

```shell-session
"svc-sql1"
```

Esta consulta devuelve registros que contienen la cadena "svc-sql1" en cualquier campo indizado.

- `Logical Operators`: KQL admite los operadores lógicos AND, OR y NOT para construir consultas más complejas. Los paréntesis se pueden utilizar para agrupar expresiones y controlar el orden de evaluación. Por ejemplo:

```shell-session
event.code:4625 AND winlog.event_data.SubStatus:0xC0000072
```

La consulta KQL filtra los datos en Kibana para mostrar los eventos que tienen el código de evento de Windows 4625 (intentos de inicio de sesión fallidos) y el valor SubStatus de 0xC0000072.`event.code:4625 AND winlog.event_data.SubStatus:0xC0000072`

En Windows, el valor SubStatus indica el motivo de un error de inicio de sesión. Un valor de SubStatus de 0xC0000072 indica que la cuenta está deshabilitada actualmente.

Mediante esta consulta, los analistas de SOC pueden identificar intentos de inicio de sesión fallidos en cuentas deshabilitadas. Este comportamiento requiere una investigación más profunda, ya que las credenciales de la cuenta deshabilitada pueden haber sido identificadas de alguna manera por un atacante.

- `Comparison Operators`: KQL admite varios operadores de comparación, como , , , , y . Estos operadores permiten definir condiciones precisas para hacer coincidir los valores de los campos. Por ejemplo:`:``:>``:>=``:<``:<=``:!`

```shell-session
event.code:4625 AND winlog.event_data.SubStatus:0xC0000072 AND @timestamp >= "2023-03-03T00:00:00.000Z" AND @timestamp <= "2023-03-06T23:59:59.999Z"
```

Al usar esta consulta, los analistas de SOC pueden identificar intentos fallidos de inicio de sesión en cuentas deshabilitadas que tuvieron lugar entre el 3 de marzo de 2023 y el 6 de marzo de 2023

- `Wildcards and Regular Expressions`: KQL admite comodines y expresiones regulares para buscar patrones en los valores de campo. Por ejemplo:

```shell-session
event.code:4625 AND user.name: admin*
```

La consulta KQL de Kibana filtra los datos en Kibana para mostrar los eventos que tienen el código de evento de Windows 4625 (intentos de inicio de sesión fallidos) y donde el nombre de usuario comienza con "admin", como "admin", "administrator", "admin123", etc.`event.code:4625 AND user.name: admin*`

Esta consulta (si se extiende) puede ser útil para identificar intentos de inicio de sesión potencialmente malintencionados dirigidos a cuentas de administrador.
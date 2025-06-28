### DNS

Millones de personas usan el servicio de nombres de dominio (DNS) diariamente. Debido a esto, muchas organizaciones tienen políticas menos rigurosas para protegerse contra amenazas basadas en DNS que las que tienen para protegerse contra otros tipos de ataques.

Variantes de malware emplean el DNS para comunicarse con servidores de comando y control (CnC) y para exfiltrar datos de tráfico disfrazados de consultas de DNS normales. Diversos tipos de codificación, tales como Base64, binaria de 8 bits y hexadecimal, pueden usarse para camuflar datos y evadir las medidas básicas de prevención de pérdida de datos (DLP, Data Loss Prevention).

![DNS](https://i.postimg.cc/SNzVHYKb/DNS.png)

Las consultas de DNS para nombres de dominio generados aleatoriamente o subdominios extremadamente largos que aparecen aleatorios se deben considerar sospechosas, especialmente si su aparición provoca aumentos excesivos de utilización de la red. Los registros de proxy de DNS pueden analizarse para detectar estas condiciones. Otra opción es usar servicios, como el servicio de DNS pasivo Cisco Umbrella, para bloquear solicitudes a dominios sospechosos de CnC y ataque.


IMPORTANTE FUNCIONAMIENTO DNS

los servidores ns son servidores autoritativos (que quiere decir esto? los servidores autoritativos son servidores DNS oficiales del dominio al que estamos consultando) por ejemplo si queremos consultar la dirección IP de google.com si le tiras con nslookup google.com siempre t va a responder un servidor no-autoritativo (es decir t responde un serviodr no oficial , el más rápdio posible, que sabe cual es la IP de google.com)

pero si ponemos nslookup 
set query=ns

nos va a dar info de los servidores autoritativos que tienen la respuesta posta de quien es google.com

![[Pasted image 20250604191454.png]]

![[Pasted image 20250604191500.png]]



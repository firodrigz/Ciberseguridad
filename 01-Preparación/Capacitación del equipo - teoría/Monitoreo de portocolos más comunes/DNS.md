### DNS

Millones de personas usan el servicio de nombres de dominio (DNS) diariamente. Debido a esto, muchas organizaciones tienen políticas menos rigurosas para protegerse contra amenazas basadas en DNS que las que tienen para protegerse contra otros tipos de ataques.

Variantes de malware emplean el DNS para comunicarse con servidores de comando y control (CnC) y para exfiltrar datos de tráfico disfrazados de consultas de DNS normales. Diversos tipos de codificación, tales como Base64, binaria de 8 bits y hexadecimal, pueden usarse para camuflar datos y evadir las medidas básicas de prevención de pérdida de datos (DLP, Data Loss Prevention).

![DNS](https://i.postimg.cc/SNzVHYKb/DNS.png)

Las consultas de DNS para nombres de dominio generados aleatoriamente o subdominios extremadamente largos que aparecen aleatorios se deben considerar sospechosas, especialmente si su aparición provoca aumentos excesivos de utilización de la red. Los registros de proxy de DNS pueden analizarse para detectar estas condiciones. Otra opción es usar servicios, como el servicio de DNS pasivo Cisco Umbrella, para bloquear solicitudes a dominios sospechosos de CnC y ataque.

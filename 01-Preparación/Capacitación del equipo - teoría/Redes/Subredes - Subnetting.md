
Las direcciones IP pueden clasificarse en clase A (/8) - B (/16) - C (/24) - D - E

| CLASE | DIRECCIONES DESDE | DIRECCIONES HASTA | CANTIDADES DE REDES | CANTIDAD DE HOST |   APLICACION   |
| :---: | :---------------: | :---------------: | :-----------------: | :--------------: | :------------: |
|   A   |      0.0.0.0      |  127.255.255.255  |         128         |    16,777,214    | GRANDES REDES  |
|   B   |     128.0.0.0     |  191.255.255.255  |       16,384        |      65,534      | REDES MEDIANAS |
|   C   |     192.0.0.0     |  223.255.255.255  |      2,097,152      |       254        | REDES PEQUEÑAS |
|   D   |     224.0.0.0     |  239.255.255.255  |      NO APLICA      |    NO APLICA     |   MULTICAST    |
|   E   |     240.0.0.0     |  255.255.255.255  |      NO APLICA      |    NO APLICA     | INVESTIGACIÓN  |

**127.0.0.0 A 127.255.255.255 RESERVADO COMO LOOPBACK**


Una vez que se aplica subneteo pierden su clase.

Si yo necesito 5 subredes necesito encontrar un nro mayor o igual que sea potencia de 2
N son la cantidad de bits que se van a encender en la parte de host.

![SUBNETTING](https://i.postimg.cc/zf2nh3VW/SUBNETTING.png)
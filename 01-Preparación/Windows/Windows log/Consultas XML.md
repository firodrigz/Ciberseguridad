### Filtros XML

 "Filtrar registro actual" -> "XML" -> "Editar consulta manualmente"

En la consulta de ejemplo, nos centramos en los eventos que contienen el campo "SubjectLogonId" con un valor de "0x3E7". La selección de este valor se deriva de la necesidad de correlacionar los eventos asociados con un "ID de inicio de sesión" específico y comprender los detalles relevantes dentro de esos eventos.

![FiltrosXML](https://i.postimg.cc/PrDPNgcy/Filtros-XML.png)

Eventos para usuario test9

```XML
<QueryList>  
<Query Id="0">  
<Select Path="Security">  
*[EventData[Data[Data[@Name='SubjectUserName'] y (Data='test9')]]  
</Select>  
</Query>  
</QueryList>```

### Metadatos del evento:

En este punto, es posible que se pregunte, ¿dónde se le ocurrió SubjectUserName y qué más puedo filtrar? La forma más fácil de encontrar estos datos es buscar un evento específico, hacer clic en la pestaña de detalles y, a continuación, hacer clic en el botón de opción Vista XML.

![Filtrado XML avanzado en el Visor de eventos de Windows](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/105236i7784C001DAE283BC)

Desde esta ventana, podemos ver la estructura de los metadatos XML del evento. Este evento tiene una etiqueta `<System>` y una etiqueta `<EventData>`. Cada uno de estos nombres de datos se puede utilizar en el filtro y combinar mediante operadores booleanos estándar.

Con la misma vista, podemos examinar los metadatos del `<Sistema>` para encontrar nombres de datos adicionales para filtrar.

![](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/105237i69D664AA2C1FD7DA))

Ahora supongamos que solo estamos interesados en un ID de evento específico que involucre a cualquiera de estos usuarios. Podemos incorporar un booleano AND para filtrar los datos del sistema.

_La consulta siguiente busca eventos 4663 para el usuario test5 o test9._

```XML
<QueryList>  
<Query Id="0">  
<Select Path="Security">  
*[EventData[Data[Data[@Name='SubjectUserName'] and (Data='test5' or Data='test9')]]  
y  
*[System[(EventID='4663')]]  
</Select>  
</Query>  
</QueryList>```

```XML
<QueryList>
<Query Id="0">
<Select Path="Security">
(*[EventData[Data[@Name='SubjectUserName']='test5']]
or
*[EventData[Data[@Name='SubjectUserName']='test9')]])
and
*[System[(EventID='4663')]]
</Select>
</Query>
</QueryList>
```

### Filtrado más amplio:

Supongamos que desea filtrar por eventos relacionados con **test5**, pero no está seguro de si estaría en SubjectUserName, TargetUserName o en otro lugar. No es necesario especificar el nombre específico en el que pueden estar los datos, sino simplemente buscar que algunos datos en `<EventData>` contengan **test5** .  

_En la consulta siguiente se buscan eventos que indiquen que los datos de `<EventData>` sean iguales a test5._

```XML
<QueryList>  
<Query Id="0">  
<Select Path="Security">  
*[EventData[Data and (Data='test5')]]  
</Select>  
</Query>  
</QueryList>```

### Varias instrucciones de selección:

También puede tener varias instrucciones select en la consulta para extraer datos diferentes en el mismo registro o datos en otro registro. Puede especificar qué registro extraer de la etiqueta `<select>` y tener varias etiquetas `<select>` en la misma etiqueta `<query>`.  
_  
En el ejemplo siguiente se extraerán 4663 eventos del registro de eventos de seguridad y 1704 eventos del registro de eventos de la aplicación._

```XML
<QueryList>  
<Query Id="0">  
<Select Path="Security">*[System[(EventID='4663')]]</Select>  
<Select Path="Application">*[System[(EventID='1704')]]</Select>  
</Query>  
</QueryList>```
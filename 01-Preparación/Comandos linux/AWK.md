Manejo básico
`awk 'patron { accion }' archivo` 

Delimitar con -F 
`awk -F '"' '{print $3}'` 
//En este caso delimita/saltea las palabras x comillas dobles, por ejemplo: 
// cat archivo.html | grep -i 'generator' | awk -F '"' '{print $4}' 

Manejo de '{print $num}' y -F' " ' especifica el salteo por comillas dobles

![AWK](https://i.postimg.cc/vHt7HVHv/AWK.png)

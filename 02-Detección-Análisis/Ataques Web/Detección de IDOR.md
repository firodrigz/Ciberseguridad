
## IDOR (Broken Access Control)

Es cuando no se comprueban los pasajes de referencias por GET con el usuario. No se utilizan tokens de sessión. 
Si la aplicación web no comprueba que el valor "id" de la solicitud pertenece a la persona que realiza la solicitud, cualquiera puede realizar esa solicitud y ver la información del usuario. Esta vulnerabilidad web se llama IDOR.

Si un atacante explotara una vulnerabilidad de IDOR, podría:

- Robar información personal
- Acceder a documentos no autorizados
- Realizar acciones no autorizadas (como eliminar, modificar)

Se pueden utilizar varios métodos para identificar los ataques IDOR. Estos son:

- **Compruebe todos los parámetros:** Una vulnerabilidad IDOR puede ocurrir en cualquier parámetro. Por lo tanto, no olvide verificar todos los parámetros.
- **Fíjate en el número de solicitudes realizadas a la misma página:** Cuando los atacantes descubren una vulnerabilidad IDOR, normalmente quieren acceder a la información de todos los demás usuarios, por lo que suelen realizar un ataque de fuerza bruta. Esta es la razón por la que es posible que vea muchas solicitudes para la misma página de una fuente.
- **Trata de encontrar un patrón:** Los atacantes planearán un ataque de fuerza bruta para alcanzar todos los objetos. Dado que realizarán el ataque en valores sucesivos y predecibles, como números enteros, puede intentar encontrar un patrón en las solicitudes que vea. Por ejemplo, si ve solicitudes como id = 1, id = 2, id = 3, es posible que sospeche.

**IMPORTANTE**: mirar tamaño de respuesta de solicitudes.

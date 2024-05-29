### Salting
La técnica de **salting** permite que el hash de la contraseña sea más seguro.

Si dos usuarios tienen la misma contraseña, también tendrán los mismos hashes de la contraseña. Un salt, que es una cadena aleatoria de caracteres, es una entrada adicional agregada a la contraseña antes del hash.

Esto crea un resultado hash diferente incluso cuando las dos contraseñas son idénticas, como se muestra aquí. Entonces, la base de datos almacena tanto el hash como el salt. La misma contraseña genera un hash diferente para diferentes usuarios porque el salt en cada instancia es diferente. Mientras tanto, el salt no tiene que ser secreto ya que es un número aleatorio.

![Salting](https://i.postimg.cc/fLG11C59/salting.png)
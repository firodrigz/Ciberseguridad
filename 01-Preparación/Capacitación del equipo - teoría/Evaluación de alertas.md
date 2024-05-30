### Evaluación de alertas

|                                         | Verdadero                                                     | Falso                                     |
| --------------------------------------- | ------------------------------------------------------------- | ----------------------------------------- |
| **Positivo (la alerta existe)**         | Se ha producido un incidente                                  | No se ha producido ningún incidente       |
| **Negativo (No existe ninguna alerta)** | No se ha producido ningún incidente. La actividad es benigna. | Se ha producido un incidente no detectado |

**Los positivos verdaderos** son el tipo de alerta deseado. Si ocurren, significa que las reglas que generan alertas funcionan correctamente.

Los **falsos positivos** no son deseables. Aunque no indican que se ha producido un ataque no detectado, son costosos porque los analistas de ciberseguridad deben investigar las falsas alarmas; por lo tanto, le quitan tiempo a la investigación de alertas que indican la presencia de ataques reales.

**Los negativos verdaderos** también son deseables. Indican que el tráfico benigno normal se ignora correctamente y que no se emiten alertas erróneas.

Los **falsos negativos** son peligrosos. Indican que los sistemas de seguridad implementados no detectan ataques. Estos incidentes podrían pasar inadvertidos durante mucho tiempo y causar daños y pérdidas de datos constantes.

Los eventos benignos son aquellos que no deben desencadenar alertas. Los eventos benignos excesivos indican que es necesario mejorar o eliminar algunas reglas u otros detectores.
### Ciclo de vida del ataque (también conocido como la cadena de muerte cibernética).

[![image.png](https://i.postimg.cc/zXtrNVPj/image.png)](https://postimg.cc/JGkgc48D)
#### Reconocimiento: 
El atacante se encarga de recopilar datos ya sea de forma pasiva - footprinting (redes sociales, google dorking) o activa - fingerprinting.
- P - Las publicaciones de linkedin suelen brindar mucha información acerca de tecnologías utilizadas, antivirus, versiones de windows, etc.
- A - escaneo activo de aplicaciones web, ip.

#### Weaponize (militarización): 
Se buscan los puntos de acceso, analizando antivirus utilizados en el objetivo o EDR - endpoint detection and response (es una solución más efectiva que el antivirus ya que identifica los nuevos exploits a medida que se ejecutan y puede detectar la actividad sospechosa de un atacante durante un incidente activo)

#### Delivery (entrega): 
Método de difusión del exploit/malware en el objetivo. Phishing o la interacción física mediante un pendrive que se dejan en lugares estratégicos para despertar la curiosidad de algún empleado.

#### Explotación:
Se activa el exploit entregado, el atacante intenta ejecutar código para obtener acceso o control en la víctima.

#### Instalación: 
Busca la persistencia.
- **Droppers**: Los atacantes pueden usar **droppers** para enviar malware al sistema de destino. Un dropper es un pequeño fragmento de código diseñado para instalar malware en el sistema y ejecutarlo. El cuentagotas puede entregarse a través de varios medios, como archivos adjuntos de correo electrónico, sitios web maliciosos o tácticas de ingeniería social.
    
- **Puertas traseras**: Una puerta trasera es un tipo de malware diseñado para proporcionar al atacante acceso continuo al sistema comprometido. La puerta trasera puede ser instalada por el atacante durante la etapa de explotación o entregada a través de un cuentagotas. Una vez instalada, la puerta trasera se puede utilizar para ejecutar más ataques o robar datos del sistema comprometido.
    
- **Rootkits**: Un rootkit es un tipo de malware diseñado para ocultar su presencia en un sistema comprometido. Los rootkits se utilizan a menudo en la etapa de instalación para evadir la detección por parte del software antivirus y otras herramientas de seguridad. El rootkit puede ser instalado por el atacante durante la etapa de explotación o entregado a través de un cuentagotas.

#### Command and control:
Teniendo el control del sistema, el atacante **establece los canales de comunicación** que a distancia le van a permitir controlar el sistema vulnerado.

#### Acción: 
Exfiltración de datos, escalada de privilegios con el objetivo de ejecutar ransomware, infectar otros objetivos de la red.

Es importante entender que los adversarios no operarán de manera lineal (como muestra la cadena de muerte cibernética). Algunas etapas anteriores de la cadena de muerte cibernética se repetirán una y otra vez. Si tomamos, por ejemplo, la etapa de un compromiso exitoso, el siguiente paso lógico para un adversario en el futuro es iniciar la etapa nuevamente para identificar objetivos adicionales y encontrar vulnerabilidades para explotar, de modo que se mueva más profundamente en la red y finalmente logre los objetivos del ataque.
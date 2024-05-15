### Consta de 2 objetivos
- capacidad de manejo de incidentes dentro de la organización
- capacidad de protegerse y prevenir incidentes de seguridad informática mediante la implementación de medidas de protección adecuadas ( protección de servidores y puntos de conexión, la organización en niveles de Active Directory, la autenticación multifactor, la administración de acceso con privilegios, etc )

## Requisitos:       
		- capacitación del equipo, del cliente
		 - políticas y documentación claras
		 - herramientas (software y hardware)


### Políticas y documentación claras
Algunas de las políticas y documentación escritas deben contener una versión actualizada de la siguiente información:

- Información de contacto y funciones de los miembros del equipo de gestión de incidentes
- Información de contacto del departamento legal y de cumplimiento, el equipo de administración, el soporte de TI, el departamento de comunicaciones y relaciones con los medios, las fuerzas del orden, los proveedores de servicios de Internet, la administración de instalaciones y el equipo externo de respuesta a incidentes
- Política, plan y procedimientos de respuesta a incidentes
- Política y procedimientos de intercambio de información sobre incidentes
- Líneas de base de sistemas y redes, a partir de una imagen dorada y un entorno de estado limpio
- Diagramas de red
- Base de datos de gestión de activos de toda la organización
- Cuentas de usuario con privilegios excesivos que el equipo puede usar a petición cuando sea necesario (también para sistemas críticos para el negocio, que se manejan con las habilidades necesarias para administrar ese sistema específico). Normalmente, estas cuentas de usuario se habilitan cuando se confirma un incidente durante la investigación inicial y luego se deshabilitan una vez que finaliza. También se realiza un restablecimiento obligatorio de la contraseña cuando se deshabilitan los usuarios.
- Posibilidad de adquirir hardware, software o un recurso externo sin un proceso completo de adquisición (compra urgente de hasta una determinada cantidad). Lo último que necesita durante un incidente es esperar semanas para la aprobación de una herramienta de $ 500.
- Hojas de referencia forenses/de investigación

es importante documentar el incidente a medida que investiga.


### Herramientas (Software y Hardware)
De cara al futuro, también tenemos que asegurarnos de que tenemos las herramientas adecuadas para realizar el trabajo. Estos incluyen, pero no se limitan a:

- Un ordenador portátil adicional o una estación de trabajo forense para cada miembro del equipo de gestión de incidentes para conservar las imágenes de disco y los archivos de registro, realizar análisis de datos e investigar sin restricciones (sabemos que el malware se probará aquí, por lo que las herramientas como el antivirus deben desactivarse). Estos dispositivos deben manejarse de manera adecuada y no de una manera que introduzca riesgos para la organización.
- Herramientas digitales de adquisición y análisis de imágenes forenses
- Herramientas de captura y análisis de memoria
- Captura y análisis de respuestas en vivo
- Herramientas de análisis de registros
- Herramientas de captura y análisis de redes
- Cables de red y conmutadores
- Bloqueadores de escritura
- Discos duros para imágenes forenses
- Cables de alimentación
- Destornilladores, pinzas y otras herramientas relevantes para reparar o desmontar dispositivos de hardware si es necesario
- Creador del indicador de compromiso (IOC) y la capacidad de buscar IOC en toda la organización
- Formularios de cadena de custodia
- Software de encriptación
- Sistema de seguimiento de tickets
- Instalación segura para el almacenamiento y la investigación
- Sistema de gestión de incidentes independiente de la infraestructura de su organización

Muchas de las herramientas mencionadas anteriormente formarán parte de lo que se conoce como un: siempre listas con las herramientas necesarias para ser recogidas y salir de inmediato. Sin esta bolsa preparada, reunir todas las herramientas necesarias sobre la marcha puede llevar días o semanas antes de que esté listo para responder.`jump bag`

### SPF / DKIM / DMARC

[Messageheader (googleapps.com)](https://toolbox.googleapps.com/apps/messageheader/)

Permiten que los correos enviados lleguen al destino correctamente.

SPF (Sender Politicy Framework): es un estándar de autentificación que vincula un nombre de dominio a una dirección de correo electrónico. Consiste en definir cuál es el remitente o remitentes autorizado para enviar emails con un dominio determinado. De este modo, los clientes de emails como Gmail o Outlook pueden comprobar que el email entrante procede de un host autorizado por el administrador del dominio desde el que se envía.

DKIM (DomainKeys Identified Mail): es un protocolo de autentificación que vincula un nombre de dominio a un mensaje. El protocolo te permite firmar tu email con tu nombre de dominio. El objetivo del protocolo DKIM no es sólo demostrar que el nombre de dominio no ha sido usurpado, sino que también el mensaje no ha sido alterado durante la transmisión.

DMARC (Domain-based Message Authentication, Reporting and Conformance): indica a los servidores receptores qué hacer con sus mensajes que no pasan SPF o DKIM
Para pasar la autenticación DMARC, los mensajes deben autenticarse mediante SPF o DKIM, o ambos. El dominio de autenticación debe ser el mismo dominio que aparece en el encabezado del mensaje De:.

### EDR

Algunas acciones muy importantes (que realmente funcionan) a tener en cuenta y hacer algo son:

- Deshabilitar LLMNR/NetBIOS
- Implemente LAPS y elimine los privilegios administrativos de los usuarios normales
- Deshabilite o configure PowerShell en el modo "ConstrainedLanguage"
- Habilitación de reglas de reducción de superficie expuesta a ataques (ASR) si se usa Microsoft Defender
- Implemente la lista blanca. Sabemos que esto es casi imposible de implementar. Considere al menos la posibilidad de bloquear la ejecución de carpetas grabables por el usuario (Descargas, Escritorio, AppData, etc.). Estas son las ubicaciones en las que se encontrarán inicialmente los exploits y las cargas útiles maliciosas. Recuerde también bloquear los tipos de script como .hta, .vbs, .cmd, .bat, .js y similares. Preste atención a los archivos [LOLBin](https://lolbas-project.github.io/) al implementar la lista blanca. No los pases por alto; Realmente se utilizan en la naturaleza como acceso inicial para eludir la lista blanca.
- Utilice firewalls basados en host. Como mínimo, bloquee la comunicación entre estaciones de trabajo y bloquee el tráfico saliente a LOLBins
- Implemente un producto EDR. En este momento, [AMSI](https://learn.microsoft.com/en-us/windows/win32/amsi/how-amsi-helps) proporciona una gran visibilidad de los scripts ofuscados para que los productos antimalware inspeccionen el contenido antes de que se ejecute. Se recomienda encarecidamente que solo elija productos que se integren con AMSI.

### Protección en la red

Implementación de IPS/IDS. Determinar que solo ciertos dispositivos se puedan conectar a al red. Si es una empresa solo en la nube que usa, por ejemplo, Azure/Azure AD, puede lograr una protección similar con directivas de acceso condicional que permitirán el acceso a los recursos de la organización solo si se conecta desde un dispositivo administrado por la empresa. 

### Gestión de identidades de privilegios / MFA / Contraseñas

Establecer contraseñas seguras a usuarios administradores. Recomendación de usar frases en contraseñas. EJ: "i LIK3 my coffeE warm".

La autenticación multifactor (MFA) es otra solución de protección de identidad que debe implementarse al menos para cualquier tipo de acceso administrativo a **TODAS las** aplicaciones y dispositivos.

### Análisis de vulnerabilidades

Se deben hacer pentesting con frecuencia para hacer un autofeedback de la seguridad.

### Campañas de concientización

Se debe tener en constante actualización a los usuarios sobre las técnicas más utilizadas como phishing, pendrives USB tirados en la oficina, etc.

### Evaluación de seguridad de Active Directory

La mejor manera de detectar errores de configuración de seguridad o vulnerabilidades críticas expuestas es buscándolas desde la perspectiva de un atacante. Hacer sus propias revisiones (o contratar a un tercero si falta el conjunto de habilidades en la organización) garantizará que cuando un dispositivo de punto final se vea comprometido, el atacante no tenga la posibilidad de escalar en un solo paso a altos privilegios en la red. Cuantas más herramientas y actividad adicional genere un atacante, mayor será la probabilidad de que los detecte, así que trate de eliminar las ganancias fáciles y las frutas maduras tanto como sea posible.

Active Directory tiene algunas rutas de escalamiento o errores conocidos y únicos. A menudo también se descubren nuevos. Las evaluaciones de seguridad de Active Directory son cruciales para la posición de seguridad del entorno en su conjunto. No asuma que los administradores de su sistema están al tanto de todos los errores descubiertos o publicados, porque en realidad probablemente no lo estén.


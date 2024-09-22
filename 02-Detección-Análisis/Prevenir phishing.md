### Spoofing EMAIL

1. **Configuración del cliente de correo**: Configurar manualmente el cliente de correo para usar una dirección "De" falsa y una dirección "Responder a" diferente.
2. **Servidores de correo vulnerables**: Usar servidores de correo mal configurados que permiten enviar correos con direcciones "De" y "Responder a" personalizadas.
3. **Phishing kits y scripts**: Usar herramientas y scripts diseñados para automatizar el envío de correos electrónicos falsificados.

Debemos tener mucho cuidado con las cabeceras de los mails, estas nos darán mucha información.
Para esto descargar el mail recibido en formato .eml 
#### Verificar:
<p align="center"> 
<img src="https://i.postimg.cc/3wyb9zDD/header.png" alt="HeaderMail"/>
</p>
## SPF 
Es el servidor en nombre del dominio que envía el mail, si no tiene cualquier servidor puede mandar un mail en nombre de dicho dominio. [SPF Check & SPF Lookup - Sender Policy Framework (SPF) - MxToolBox](https://mxtoolbox.com/SPF.aspx)
### ¿Se envió el correo electrónico desde el servidor SMTP correcto?

Se debe confirmar que el `from` desde donde recibimos el correo utilice los mismos servidores MX de la cabecera `received` para esto usamos [Network Tools: DNS,IP,Email (mxtoolbox.com)](https://mxtoolbox.com/SuperTool.aspx)

##### Mails cabeceras (IMPORTANTE ANALIZARLAS)
[Messageheader (googleapps.com)](https://toolbox.googleapps.com/apps/messageheader/)
[Network Tools: DNS,IP,Email (mxtoolbox.com)](https://mxtoolbox.com/SuperTool.aspx)

##### Dominios (Análisis estático)
[urlDNA | The DNA test for websites](https://urldna.io/)
[Notmining – Scan and detect phishing websites](https://notmining.es/es_es/)
[VirusTotal - Home](https://www.virustotal.com/gui/home/upload)

### Ver contenido de links sin afectar navegador principal (Análisis dinámico)
[Browserling – Online cross-browser testing](https://www.browserling.com/)

### Analizar excels
olevba `file`

### Punycode

[Conversor - Punycode](https://punycode.es/) (Importante para ver si no hay unicode en urls -> punycode = estandar que convierte todos los unicode)

En firefox activar en configuración de navegador: network.IDN_show_punycode TRUE


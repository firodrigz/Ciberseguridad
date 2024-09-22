### **Tipos de inyecciones XXS**

Hay 3 tipos de XSS. Estos son:

1. **XSS reflejado (no persistente):** Se trata de un tipo de XSS no persistente en el que la carga útil XSS debe estar presente en la solicitud. Es el tipo más común de XSS.  
2. **XSS almacenado (persistente):** este tipo de XSS es donde el atacante puede cargar permanentemente la carga útil XSS en la aplicación web. En comparación con otros tipos, el XSS almacenado es el tipo de XSS más peligroso.  
3. **XSS basado en DOM: XSS** basado en DOM es un ataque XSS en el que la carga útil del ataque se ejecuta como resultado de modificar el "entorno" del DOM en el navegador de la víctima utilizado por el script original del lado del cliente para que el código del lado del cliente se ejecute de manera "inesperada". (OWASP)

Se basa en intentar ejecutar código javascript que se ejecutará en el servidor para obtener información del mismo en URL, campos de texto.

### Detección de ataques XXS
- **Utilizar frameworks de seguridad correspondientes**.
- **Desinfectar siempre los datos recibidos de un usuario:** Nunca se debe confiar en los datos recibidos de un usuario. 
- **Compruebe el uso de caracteres especiales:** Compruebe los datos procedentes de un usuario para ver si hay caracteres especiales que se utilizan habitualmente en las cargas útiles XSS, como mayor que (>) o menor que (<), están presentes.

Si se realiza herramientas automatizadas vemos que las solicitudes son muchas en el mismo segundo y muchas tienen su nombre dentro de la solicitud como "python-urllib3"

**Buscar**:  "script", "prompt" y "console.log"
### **Tipos de inyecciones SQL**

Hay 3 tipos de inyección SQL. Estos son:

1. **SQLi en banda (SQLi clásico):** cuando se envía una consulta SQL y se responde a ella en el mismo canal, lo llamamos SQLi en banda. Esto es más fácil de explotar para los atacantes que otras categorías de SQLi.  
2. **SQLi inferencial (SQLi ciego):** Las consultas SQL que reciben una respuesta que no se puede ver se denominan SQLi inferencial. También se les llama "SQLi ciegos" porque no se puede ver la respuesta.  
3. **SQLi fuera de banda**: Si la respuesta a una consulta SQL se comunica a través de otro canal, este tipo de SQLi se denomina "SQLi fuera de banda". Por ejemplo, si el atacante recibe respuestas a las consultas SQL a través de DNS, esto se denomina SQLi fuera de banda.

## **Cómo evitar las inyecciones SQL**

- **Desinfectar siempre los datos recibidos de un usuario:** Nunca se debe confiar en los datos recibidos de un usuario. Además, se debe desinfectar todos los datos (como encabezados, URL, etcétera), no solo los datos del formulario. Verificar los encabezados de solicitud HTTP, como el "User-Agent".
- **Utilizar consultar SQL procesadas:** Aprovechar la seguridad proporcionada por el framework.
- **Identificar herramientas automatizadas:** Existen muchas herramientas automatizadas como SQLMap que dejan su nombre de firma en los ataques en encabezados de solicitud HTTP, como el "User-Agent" o en los payloads como `sqlmap' or 1=1`
- **Buscar palabras clave SQL:** Palabras como "INSERT", "SELECCIONAR" y "DÓNDE" en los datos recibidos de los usuarios.
- **Comprobar los caracteres especiales:** Buscar apóstrofes ('), guiones (-) o paréntesis utilizados en SQL o caracteres especiales utilizados habitualmente.
- **Compruebe la frecuencia de las solicitudes:** para identificar una automatización de payloads, un humano puede enviar 1 payload cada segundos, una herramienta miles. (verificar en registros de acceso desde el servidor web).

**Buscar**: SELECT, INSERT , WHERE, 1=1, OR, SQLMAP


[payloadbox/sql-injection-payload-list: 🎯 Lista de carga útil de inyección SQL (github.com)](https://github.com/payloadbox/sql-injection-payload-list)
[Prevención de inyecciones SQL - Serie de hojas de referencia rápida de OWASP](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html)



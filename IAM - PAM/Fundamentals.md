## 🔹 **¿Qué es IAM (Identity and Access Management)?**

IAM (Gestión de Identidades y Accesos) es el conjunto de políticas, tecnologías y procesos que permiten a una organización administrar quién puede acceder a qué recursos y bajo qué condiciones. Es fundamental para la seguridad de cualquier empresa, ya que evita accesos no autorizados y protege información sensible.

### 🔍 **Conceptos clave en IAM**

1. **Identidad digital**: Un usuario, servicio o dispositivo con credenciales que lo identifican.
2. **Autenticación**: Proceso de validar la identidad (contraseñas, MFA, biometría).
3. **Autorización**: Control sobre lo que un usuario puede hacer en un sistema (roles, permisos).
4. **Single Sign-On (SSO)**: Un solo inicio de sesión para múltiples sistemas.
5. **Federación de Identidad**: Uso de identidades en diferentes dominios (Ej: OAuth, SAML).
6. **Zero Trust**: Modelo de seguridad que asume que nadie es de confianza por defecto.

### 🔧 **Tecnologías clave en IAM**

- **Active Directory (AD) / Azure AD** (Gestión de identidades en entornos Microsoft).
- **Okta** (Plataforma IAM en la nube).
- **Ping Identity** (Alternativa a Okta).
- **SAML, OAuth, OpenID Connect** (Protocolos para autenticación federada).
- **LDAP** (Protocolo para acceder a directorios de usuarios).
- **MFA (Multi-Factor Authentication)** (Autenticación en dos pasos).


### 4 pilares:
- Gestión de accesos 
- Gestión de identidades (altas/bajas/modificaciones)
- Gestión de accesos privilegiados
- Gobierno de identidades (Zero Trust)

---

## 🔹 **¿Qué es PAM (Privileged Access Management)?**

PAM (Gestión de Accesos Privilegiados) es una especialización dentro de IAM que se enfoca en **proteger cuentas con altos privilegios**, como administradores de sistemas, bases de datos y servidores críticos.

### 🔍 **Conceptos clave en PAM**

1. **Cuentas privilegiadas**: Administradores de sistemas, root, DBA, etc.
2. **Vault (bóveda de credenciales)**: Almacena credenciales de forma segura.
3. **Session Management**: Registro y monitoreo de sesiones privilegiadas.
4. **Just-In-Time Access (JIT)**: Acceso temporal basado en necesidad.
5. **Privileged Session Recording**: Graba sesiones para auditoría.
6. **Password Rotation**: Rotación automática de contraseñas de cuentas privilegiadas.

### 🔧 **Tecnologías clave en PAM**

- **CyberArk** (Líder en el mercado de PAM).
- **BeyondTrust** (Competencia fuerte de CyberArk).
- **Thycotic / Delinea** (Otra alternativa).
- **HashiCorp Vault** (Enfocado en DevOps y cloud).
- **AWS Secrets Manager / Azure Key Vault** (Gestión de credenciales en la nube).
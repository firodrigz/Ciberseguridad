### **Funcionamiento básico:**

1. **Inspección del tráfico:**  
   Analiza los paquetes de datos que entran y salen de la red. Examina la dirección IP, los puertos y el contenido según las políticas de seguridad.
   
2. **Aplicación de reglas:**  
   Cada paquete es comparado con una lista de reglas (lista blanca/negra). Las reglas especifican qué tipo de tráfico está permitido o denegado.
   
3. **Filtrado de paquetes:**  
   Decide si permite o bloquea el tráfico en función de criterios como:   
   - Dirección IP origen/destino
   - Número de puerto
   - Protocolo (TCP, UDP, ICMP)
   - Contenido o estado de la conexión

4. **Monitoreo de conexiones (Stateful vs Stateless):**
   - **Stateful:** Mantiene un registro del estado de las conexiones activas. Verifica si un paquete pertenece a una sesión existente.
   - **Stateless:** Evalúa cada paquete individualmente, sin considerar el estado de la conexión.

5. **Registro de eventos (Logging):**  
   Documenta las actividades detectadas, como intentos de acceso fallidos o tráfico bloqueado. Esto facilita la auditoría y el análisis forense.
   
6. **Detección y prevención de intrusiones (IDS/IPS):**  
   Algunos firewalls modernos incluyen sistemas de detección (IDS) y prevención de intrusiones (IPS), que analizan patrones de tráfico sospechoso y reaccionan automáticamente.
   
7. **Aplicación de políticas de seguridad:**  
   Los administradores pueden configurar políticas específicas para usuarios o grupos, limitando el acceso a ciertos servicios o restringiendo tráfico según necesidades empresariales.

##### Reglas Flotantes
Se ejecutan antes, mayor orden de prioridad.

---

### **Tipos comunes de firewalls:**

- **Firewalls de red (Network Firewalls):** Protegen redes enteras, generalmente en la frontera entre redes internas y externas (por ejemplo, Internet).
- **Firewalls de host (Host-Based Firewalls):** Se ejecutan en dispositivos individuales, filtrando el tráfico que entra o sale de un sistema específico.
- **Firewalls de aplicación (WAF - Web Application Firewall):** Protegen aplicaciones web contra ataques específicos como inyecciones SQL o XSS.
- **Firewalls de próxima generación (NGFW):** Incluyen capacidades avanzadas como inspección profunda de paquetes (DPI), control de aplicaciones y protección contra malware.
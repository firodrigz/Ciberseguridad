## 🌳 ¿Qué es un **árbol** en Active Directory?

Imaginá que un **árbol** es como una familia de dominios que **tienen un apellido en común**. Todos los dominios del árbol comparten el mismo **espacio de nombres** (nombre del dominio).

### Ejemplo:

- papas.galletas.com    
- chocolate.galletas.com    
- galletas.com    

Todos pertenecen al **árbol de galletas.com**, porque comparten el "apellido" **galletas.com**.

### Comparación:

Es como una mamá y sus hijos.

- La mamá es **galletas.com**    
- Los hijos son **papas.galletas.com** y **chocolate.galletas.com**    

Todos tienen el mismo apellido, entonces **son familia directa**.

---

## 🌲 ¿Qué es un **bosque** en Active Directory?

Un **bosque** es como un **vecindario** donde viven muchas familias diferentes. Cada familia (árbol) tiene su propio apellido, pero **pueden vivir en paz y compartir cosas si se llevan bien**.

### Ejemplo:

- Una familia se llama **galletas.com**    
- Otra familia se llama **pan.com**    
- Otra familia se llama **helado.org**    

Cada uno es un árbol diferente, pero todos **viven en el mismo bosque**.

---

## 🤝 ¿Qué es una **relación de confianza** (trust)?

Es como un **trato o acuerdo** entre dos dominios para que se dejen entrar mutuamente.

### Ejemplo con niños:

Imaginá que vos sos del dominio **chocolate.galletas.com** y querés ir a jugar a la casa de un amigo que vive en **vainilla.helado.org**.

Como son de **familias (árboles) distintas**, no podés entrar así nomás...  
Entonces los papás (administradores) hacen un **acuerdo de confianza**, donde dicen:

> "Está bien, Facu puede entrar a jugar con permiso".

Eso es una **relación de confianza** entre **dos dominios**. Permite que los usuarios de un dominio usen recursos (carpetas, impresoras, apps) en otro dominio, **como si fueran de casa**.

---
## 🔍 Ejemplos reales en empresas:

1. **Empresa multinacional**   
    - Tiene oficinas en varios países:        
        - `usa.corporativo.com`            
        - `mexico.corporativo.com`            
        - `españa.corporativo.com`            
    - Todos pertenecen al mismo **árbol**.        
2. **Fusión de empresas**    
    - `empresaA.local` y `empresaB.local` se fusionan.        
    - Crean un **bosque**, con una **relación de confianza** para que los usuarios de ambas puedan trabajar entre sí.        
3. **Proveedores externos**    
    - Una empresa tiene un proveedor de soporte TI.        
    - Se crea una **relación de confianza** entre `empresa.local` y `soporte.proveedor.com`, solo para que el equipo de soporte pueda ingresar remotamente a ciertas PCs.

---

## 🧩 ¿Las relaciones de confianza **tienen que darse sí o sí dentro de un bosque**?

**No.** Las relaciones de confianza **pueden darse dentro del mismo bosque o entre bosques distintos**.

---

## 🔄 ¿Pueden darse relaciones de confianza entre **miembros de distintos bosques**?

**Sí**, se llaman **relaciones de confianza entre bosques** (**forest trust**).  
Eso pasa cuando, por ejemplo, dos empresas distintas quieren colaborar, compartir recursos, o permitir que usuarios de una accedan a recursos de la otra.

> 🔐 Pero **NO se crean automáticamente**. Las tiene que crear un administrador **manualmente**.

---

## 🌳 ¿Qué sentido tienen los bosques?

Un **bosque en Active Directory** tiene varios propósitos importantes:

1. **Es el límite de seguridad más grande en AD**  
    Todo lo que está dentro de un bosque **confía por defecto** entre sí, y puede compartir recursos si está permitido.    
2. **Agrupa árboles con diferentes nombres**, pero que quieren trabajar juntos.  
    Por ejemplo, `miempresa.com` y `ventas.com` pueden estar en el mismo bosque, aunque tengan apellidos distintos.    
3. Permite tener **una sola configuración global** (por ejemplo, una política de contraseñas, certificados, etc.) para todos los dominios del bosque.    

---

## ✅ ¿Todos los miembros de un bosque tienen relación de confianza entre sí?

**Sí. Todos los dominios dentro de un mismo bosque tienen relaciones de confianza automáticamente creadas.**

Y además:
- Son **bidireccionales** → confían en ambos sentidos.    
- Son **transitivas** → si A confía en B y B confía en C, entonces A confía en C.

---


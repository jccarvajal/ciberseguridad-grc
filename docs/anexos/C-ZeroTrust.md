# ANEXO C: Checklist de Madurez Zero Trust
**(Herramienta de Autoevaluación Arquitectónica)**

### 1. Instrucciones de Uso

**Zero Trust** (Confianza Cero) no es un producto que se compra; es una estrategia de diseño basada en tres principios dogmáticos:

1.  **Verificación Explícita:** Autenticar y autorizar siempre, basándose en todos los puntos de datos disponibles.
2.  **Privilegio Mínimo:** Dar solo el acceso necesario, solo por el tiempo necesario (Just-in-Time).
3.  **Asumir la Brecha (*Assume Breach*):** Diseñar la arquitectura pensando que ya hay un atacante dentro de la red.

Utilice esta lista para auditar sus controles actuales frente a la realidad de la **Autonomía Adversaria**.

---

### 2. Pilar 1: IDENTIDAD (El Nuevo Perímetro)
*¿Estamos seguros de que el usuario es quien dice ser?* (Ver Capítulo 5)

* [ ] **MFA Universal:** ¿Está activo el Doble Factor de Autenticación para el **100%** de los empleados, incluidos ejecutivos y terceros? *(Sin excepciones)*.
* [ ] **Acceso Condicional:** ¿El sistema bloquea automáticamente intentos de login desde países inusuales, IPs de riesgo o dispositivos desconocidos?
* [ ] **Identidad Única (SSO):** ¿Existe un *Single Sign-On* centralizado para evitar la dispersión de credenciales débiles?
* [ ] **Gestión de Privilegios (PAM):** ¿Las cuentas de Administrador están protegidas en una bóveda, aisladas de internet y requieren rotación automática?
* [ ] **Limpieza de Cuentas (JML):** ¿Existe un proceso automático para desactivar cuentas de empleados que se van (*Leavers*) en menos de 24 horas?

---

### 3. Pilar 2: DISPOSITIVOS (Endpoints)
*¿Confiamos en la salud de la máquina que se conecta?*

* [ ] **Inventario Completo:** ¿Sabemos exactamente qué dispositivos están conectados a la red ahora mismo? *(No se puede proteger lo que no se ve)*.
* [ ] **Validación de Salud:** ¿Se bloquea el acceso a la red si el dispositivo no tiene el antivirus actualizado o el disco cifrado (BitLocker)?
* [ ] **EDR/XDR:** ¿Tenemos un sistema de Detección y Respuesta en el Endpoint capaz de aislar hosts y matar procesos maliciosos remotamente?
* [ ] **BYOD Contenido:** Los dispositivos personales (celulares/laptops) ¿están aislados en una red de invitados o gestionados por un MDM (*Mobile Device Management*)?

---

### 4. Pilar 3: RED (Infraestructura)
*¿Puede un atacante moverse libremente si logra entrar?* (Ver Capítulo 4)

* [ ] **Micro-segmentación:** ¿Están separados los servidores críticos (Base de Datos) de las redes de usuarios generales (PCs de oficina)?
* [ ] **Cifrado de Tráfico:** ¿Todo el tráfico interno viaja cifrado (HTTPS/TLS), incluso dentro del centro de datos?
* [ ] **Eliminación de VPN Plana:** ¿La VPN da acceso a "toda la red" o solo a las aplicaciones específicas que el usuario necesita?
* [ ] **Protección Anti-DDoS:** ¿Existen defensas en el borde para mitigar ataques de denegación de servicio volumétricos?

---

### 5. Pilar 4: DATOS (El Activo)
*¿Sabemos qué estamos protegiendo?* (Ver Capítulo 6)

* [ ] **Clasificación:** ¿Están etiquetados los documentos y correos (Confidencial, Interno, Público) de forma automática o manual?
* [ ] **Cifrado en Reposo:** ¿Las bases de datos, discos duros y medios extraíbles están cifrados?
* [ ] **Backups Inmutables:** ¿Existe una copia de seguridad que sea técnicamente imposible de borrar o sobrescribir por un administrador de red? *(Defensa crítica Anti-Ransomware)*.
* [ ] **DLP (Prevención de Fuga):** ¿Hay controles para alertar o bloquear si alguien intenta enviar datos sensibles (PII, Tarjetas) por correo o USB?

---

### 6. Pilar 5: ANALÍTICA Y AUTOMATIZACIÓN
*¿Qué tan rápido reaccionamos?* (Ver Capítulo 8)

* [ ] **Logs Centralizados (SIEM):** ¿Todos los logs (Firewall, AD, Antivirus, Cloud) van a un repositorio centralizado seguro e inalterable?
* [ ] **Correlación de Eventos:** ¿Hay reglas que alerten comportamientos anómalos cruzados (ej: "Usuario de RRHH accediendo a Base de Datos de Ingeniería")?
* [ ] **Respuesta Automática (SOAR):** ¿Existen *Playbooks* que bloqueen IPs, aíslen máquinas o revoquen usuarios automáticamente sin intervención humana?

---

### 7. Tabla de Madurez (Resumen Ejecutivo)

Marque dónde se encuentra su organización hoy para reportar al Directorio:

| Nivel | Descripción del Estado | Riesgo Asociado |
| :--- | :--- | :--- |
| **0. Tradicional** | Red plana, contraseñas simples, backups locales, procesos manuales. | 🔴 **Crítico.** Blanco fácil para Ransomware básico y exfiltración masiva. |
| **1. Avanzado** | MFA en todo, Segmentación básica (VLANs), EDR instalado, Backups en nube. | 🟡 **Medio.** Resistente a ataques comunes (*Commodity*), vulnerable a ataques dirigidos. |
| **2. Óptimo (Zero Trust)** | Identidad como perímetro, Micro-segmentación dinámica, Automatización SOAR, Cultura de Seguridad. | 🟢 **Bajo.** Resiliencia alta. Si entran, el daño es mínimo y contenido (*Blast Radius* reducido). |

---

> **NOTA ESTRATÉGICA PARA EL CISO:**
> 
> No intente marcar todas las casillas en un mes. La implementación es una maratón, no un sprint.
> 
> **Prioridad 1 (Supervivencia):** MFA Universal + Backups Inmutables.
> **Prioridad 2 (Visibilidad):** EDR en el 100% de los equipos.
> **Prioridad 3 (Contención):** Microsegmentación de Red.
> 
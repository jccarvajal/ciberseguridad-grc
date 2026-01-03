# ANEXO C: Checklist de Madurez Zero Trust
**(Herramienta de Autoevaluación Arquitectónica)**

### 1. Instrucciones de Uso
Zero Trust (Confianza Cero) no es un producto; es una estrategia basada en tres principios:
1.  **Verificación Explícita:** Autenticar y autorizar siempre.
2.  **Privilegio Mínimo:** Dar solo el acceso necesario, solo por el tiempo necesario.
3.  **Asumir la Brecha:** Diseñar pensando que ya hay un atacante dentro.

Utilice esta lista para auditar sus controles actuales.

---

### 2. Pilar 1: IDENTIDAD (El Nuevo Perímetro)
*¿Estamos seguros de que el usuario es quien dice ser?*

* [ ] **MFA Universal:** ¿Está activo el Doble Factor de Autenticación para el 100% de los empleados, incluidos ejecutivos y terceros? (Sin excepciones).
* [ ] **Acceso Condicional:** ¿El sistema bloquea automáticamente intentos de login desde países inusuales o dispositivos desconocidos?
* [ ] **Identidad Única (SSO):** ¿Existe un Single Sign-On para no tener múltiples contraseñas dispersas?
* [ ] **Gestión de Privilegios (PAM):** ¿Las cuentas de Administrador están protegidas en una bóveda y requieren rotación de contraseña automática?
* [ ] **Limpieza de Cuentas (JML):** ¿Existe un proceso automático para desactivar cuentas de empleados que se van (Leavers) en menos de 24 horas?

### 3. Pilar 2: DISPOSITIVOS (Endpoints)
*¿Confiamos en la salud de la máquina que se conecta?*

* [ ] **Inventario Completo:** ¿Sabemos exactamente qué dispositivos están conectados a la red ahora mismo?
* [ ] **Validación de Salud:** ¿Se bloquea el acceso si el dispositivo no tiene el antivirus actualizado o el disco cifrado (BitLocker)?
* [ ] **EDR/XDR:** ¿Tenemos un sistema de Detección y Respuesta en el Endpoint (no solo antivirus) capaz de matar procesos maliciosos remotamente?
* [ ] **BYOD Contenido:** Los dispositivos personales (celulares/laptops) ¿están aislados en una red de invitados o gestionados por MDM (Mobile Device Management)?

### 4. Pilar 3: RED (Infraestructura)
*¿Puede un atacante moverse libremente si entra?*

* [ ] **Micro-segmentación:** ¿Están separados los servidores críticos (Base de Datos) de las redes de usuarios (PCs de oficina)?
* [ ] **Cifrado de Tráfico:** ¿Todo el tráfico interno viaja cifrado (HTTPS/TLS), incluso dentro del centro de datos?
* [ ] **Eliminación de VPN Plana:** ¿La VPN da acceso a "toda la red" o solo a las aplicaciones específicas que el usuario necesita?
* [ ] **Protección Anti-DDoS:** ¿Existen defensas en el borde para mitigar ataques de denegación de servicio?

### 5. Pilar 4: DATOS (El Activo)
*¿Sabemos qué estamos protegiendo?*

* [ ] **Clasificación:** ¿Están etiquetados los documentos (Confidencial, Interno, Público)?
* [ ] **Cifrado en Reposo:** ¿Las bases de datos y discos duros están cifrados?
* [ ] **Backups Inmutables:** ¿Existe una copia de seguridad que sea técnicamente imposible de borrar o sobrescribir (Anti-Ransomware)?
* [ ] **DLP (Prevención de Fuga):** ¿Hay controles para alertar si alguien intenta enviar datos sensibles por correo o USB?

### 6. Pilar 5: ANALÍTICA Y AUTOMATIZACIÓN
*¿Qué tan rápido reaccionamos?*

* [ ] **Logs Centralizados (SIEM):** ¿Todos los logs (Firewall, AD, Antivirus) van a un lugar centralizado seguro?
* [ ] **Correlación:** ¿Hay reglas que alerten comportamientos anómalos (ej: "Usuario de RRHH accediendo a Base de Datos de Ingeniería")?
* [ ] **Respuesta Automática (SOAR):** ¿Existen "Playbooks" que bloqueen IPs o usuarios automáticamente sin intervención humana?

---

### 7. Tabla de Madurez (Resumen Ejecutivo)

Marque dónde se encuentra su organización hoy:

| Nivel | Descripción | Riesgo Asociado |
| :--- | :--- | :--- |
| **0. Tradicional** | Red plana, contraseñas simples, backups locales, procesos manuales. | **Crítico.** (Blanco fácil para Ransomware básico). |
| **1. Avanzado** | MFA en todo, Segmentación básica (VLANs), EDR instalado, Backups en nube. | **Medio.** (Resistente a ataques comunes, vulnerable a dirigidos). |
| **2. Óptimo (Zero Trust)** | Identidad como perímetro, Micro-segmentación dinámica, Automatización SOAR, Cultura de Seguridad. | **Bajo.** (Resiliencia alta. Si entran, el daño es mínimo). |

---
**Nota para el CISO:**
No intente marcar todas las casillas en un mes.
**Prioridad 1:** MFA Universal + Backups Inmutables.
**Prioridad 2:** EDR en todos los equipos.
**Prioridad 3:** Segmentación de Red.

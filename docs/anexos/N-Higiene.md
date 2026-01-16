# ANEXO N: La Línea Base de Higiene Digital
**(Controles Esenciales de Debida Diligencia)**

### 1. Propósito de este Anexo

Este documento define el "Suelo Mínimo de Seguridad" (*Security Baseline*).
No representa la excelencia, sino la **supervivencia**. La ausencia de cualquiera de estos controles en una auditoría moderna no se considera una "brecha técnica", sino una **negligencia administrativa** por falta de gobierno básico.

Estos controles siguen el **Principio de Pareto**: constituyen el 20% del esfuerzo que mitiga el 80% de los vectores de ataque comunes (oportunistas).

---

### 2. Higiene de Presencia Pública (Lo que ve el mundo)

Estos controles son visibles desde internet sin necesidad de intrusión. Su ausencia señala a los atacantes (y auditores) que la organización es un objetivo blando (*Low Hanging Fruit*).

#### A. Identidad del Correo (Anti-Phishing)
* **Control:** Implementación estricta de **SPF, DKIM y DMARC**.
* **Configuración Requerida:** DMARC debe estar configurado en modo `p=reject` o al menos `p=quarantine`. El modo `p=none` solo sirve para monitoreo y no protege la marca.
* **Impacto GRC:** Evita que criminales envíen correos fingiendo ser el CEO o la marca oficial (Protección de Reputación y Fraude Financiero).

#### B. Integridad Web
* **Control:** **HSTS (HTTP Strict Transport Security)**.
* **Configuración Requerida:** Cabecera obligatoria en servidores web que fuerza a los navegadores a conectarse *solo* por HTTPS, rechazando conexiones inseguras.
* **Impacto GRC:** Mitiga ataques de interceptación (*Man-in-the-Middle*) que degradan la seguridad de los datos de clientes en tránsito.

#### C. Canal de Reporte Ético
* **Control:** Archivo **`security.txt`** (Estándar RFC 9116).
* **Ubicación:** `dominio.com/.well-known/security.txt`
* **Impacto GRC:** Establece un canal oficial para que investigadores de seguridad reporten vulnerabilidades antes de que sean explotadas, demostrando apertura y diligencia en la gestión de amenazas externas.

---

### 3. Higiene de Identidad y Acceso (El Nuevo Perímetro)

Dado que el perímetro físico desapareció con la nube y el teletrabajo, la identidad es la única muralla real.

#### A. Autenticación Robusta
* **Control:** **MFA (Multi-Factor Authentication)** Obligatorio.
* **Alcance:** 100% de los accesos remotos (VPN, Correo, SaaS) y 100% de las cuentas administrativas.
* **Regla de Oro:** Una contraseña, por compleja que sea, ya no se considera seguridad suficiente.
* **Impacto GRC:** Detiene el 99.9% de los ataques automatizados de fuerza bruta y reutilización de credenciales robadas.

#### B. Segregación de Privilegios
* **Control:** Separación de cuentas de Usuario vs. Administrador.
* **Regla de Oro:** Ningún empleado (incluido el personal de TI) debe navegar por internet o leer correos usando una cuenta con privilegios de "Admin de Dominio" o "Root".
* **Impacto GRC:** Contiene la infección. Si un usuario hace clic en un malware, el daño se limita a su PC y no se propaga a toda la red.

---

### 4. Higiene de Datos (La Última Línea de Defensa)

Cuando las defensas anteriores fallan, estos controles determinan si la empresa se recupera o cierra.

#### A. Respaldo Inmutable
* **Control:** Estrategia de Backup **3-2-1-1-0**.
    * 3 copias de datos.
    * 2 medios diferentes.
    * 1 copia fuera del sitio (Off-site).
    * **1 copia inmutable (Offline o WORM) que no pueda ser borrada ni cifrada por ransomware.**
    * 0 errores en las pruebas de restauración.
* **Impacto GRC:** Es el único antídoto real contra el Ransomware. Sin esto, pagar el rescate se vuelve la única (y mala) opción.

#### B. Inventario de Activos
* **Control:** Mapeo actualizado de Hardware y Software.
* **Axioma:** "No puedes proteger lo que no sabes que existe."
* **Impacto GRC:** Identifica sistemas legados u olvidados (*Shadow IT*) que suelen ser la puerta de entrada de los atacantes.

---

> **Nota para el Auditor:**
> La implementación de estos controles es de bajo costo financiero pero de alto impacto en la reducción de riesgo (ALE). Priorizar tecnologías complejas (IA, Blockchain) sin tener esta base resuelta es un error de arquitectura fundamental.

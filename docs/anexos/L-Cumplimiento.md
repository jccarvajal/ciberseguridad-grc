# ANEXO L: Cumplimiento Normativo y Riesgo de Terceros
**(La Hoja de Ruta Legal y Gestión de Proveedores)**

### 1. El Principio de Responsabilidad Solidaria
Bajo la nueva normativa (Ley 21.663 y estándares globales), existe una regla de oro:
> **"Se puede externalizar el servicio, pero NUNCA se puede externalizar la responsabilidad."**

Si su proveedor de nube, su agencia de marketing o su soporte de TI es hackeado y eso afecta sus datos, la multa de la **ANCI** y la demanda civil caerán sobre **usted**. Este anexo provee las herramientas para gestionar esa responsabilidad.

---

### 2. Tabla de Plazos Fatales (Cheat Sheet Legal)
*Tiempos máximos de notificación obligatoria según Ley Marco de Ciberseguridad (Chile).*

El reloj empieza a correr desde el momento en que se **toma conocimiento** del incidente.

| Tipo de Incidente | Plazo de Notificación | A quién notificar | Multa por Incumplimiento |
| :--- | :--- | :--- | :--- |
| **Impacto Significativo** (Operadores de Importancia Vital) | **3 Horas** | CSIRT Nacional (ANCI) | Gravísima (Hasta 20.000 UTM) |
| **Incidente General** (Servicios Esenciales) | Lo antes posible (**< 24 Hrs**) | CSIRT Nacional | Grave |
| **Fuga de Datos Personales** (Ley de Datos) | Inmediato / 72 Hrs (GDPR) | Agencia de Protección de Datos | Según Ley 19.628 (Modif.) |
| **Brecha de Proveedor** | Según Contrato | A la Empresa Contratante | Civil / Contractual |

**Definición de "Impacto Significativo":**
Cualquier incidente que interrumpa la continuidad de un servicio esencial, afecte la integridad física de las personas o comprometa la seguridad nacional.

---

### 3. Semáforo de Riesgo de Terceros (Vendor Risk Management)

Antes de firmar contrato con **cualquier** proveedor que toque sus datos o su red, aplique este filtro rápido.

#### A. Cuestionario de "Factibilidad de Seguridad" (Must-Haves)
Si el proveedor responde "NO" a cualquiera de estas, **no se firma**.

1.  [ ] **MFA:** ¿Sus administradores usan Doble Factor de Autenticación para acceder a nuestros datos?
2.  [ ] **Cifrado:** ¿Los datos están cifrados en tránsito (TLS) y en reposo (AES-256)?
3.  [ ] **Notificación:** ¿Se comprometen por contrato a reportarnos una brecha en menos de **2 horas**?
4.  [ ] **Derecho a Auditoría:** ¿Podemos escanear o auditar su seguridad? (O entregar reportes SOC2 Type II vigentes).
5.  [ ] **Destrucción de Datos:** ¿Certifican que borrarán nuestros datos al finalizar el contrato?

#### B. Clasificación del Proveedor

| Nivel de Riesgo | Tipo de Acceso | Requisito de Seguridad |
| :--- | :--- | :--- |
| 🔴 **Crítico** | Acceso a Datos Personales, Bases de Datos Core o VPN permanente. | Cuestionario Completo, Auditoría Presencial, ISO 27001 obligatoria. |
| 🟡 **Medio** | Acceso a sistemas no críticos (SaaS de Marketing, Encuestas). | Cuestionario Simplificado, Cláusulas Contractuales. |
| 🟢 **Bajo** | Sin acceso a datos ni red (Insumos de oficina, Catering). | Cláusulas de confidencialidad estándar (NDA). |

---

### 4. Cláusulas de Ciberseguridad Obligatorias (Copy-Paste para Legal)

No firme contratos genéricos. Inserte estas tres cláusulas en el anexo técnico:

> **CLÁUSULA 1: OBLIGACIÓN DE NOTIFICACIÓN RÁPIDA**
> "EL PROVEEDOR se obliga a notificar al CLIENTE sobre cualquier incidente de seguridad que afecte la confidencialidad, integridad o disponibilidad de los servicios contratados, en un plazo máximo de **2 horas** desde su detección. El retraso en esta notificación generará una multa automática de [X] UF por hora de retraso, sin perjuicio de las indemnizaciones legales."
> *(Nota Estratégica: El plazo debe ser menor al que usted tiene con la ANCI. Si usted tiene 3 horas, el proveedor debe avisarle en 2).*

> **CLÁUSULA 2: PARCHADO Y VULNERABILIDADES**
> "EL PROVEEDOR garantiza que el software entregado estará libre de vulnerabilidades críticas conocidas (CVE con CVSS > 9.0) y se obliga a aplicar los parches de seguridad en un plazo no mayor a **48 horas** tras su publicación."

> **CLÁUSULA 3: DERECHO DE AUDITORÍA (AUDIT RIGHT)**
> "EL CLIENTE se reserva el derecho de realizar, por sí mismo o a través de terceros auditores, escaneos de vulnerabilidades y revisiones de seguridad sobre los servicios contratados, previo aviso de 72 horas."

---

### 5. Gestión de "Software Prohibido" (Blacklist)

Para cumplimiento GRC, la organización debe mantener una lista de tecnologías prohibidas por riesgo geopolítico o de obsolescencia.

* **Software "End of Life" (EOL):** Prohibido usar Windows 2008, Windows 7, SQL 2012 en producción.
* **Hardware de Alto Riesgo:** Restricción de compra de equipamiento de red de fabricantes sancionados internacionalmente (según política de geopolítica de la empresa).
* **Software de Acceso Remoto Gratuito:** Prohibido el uso de TeamViewer gratuito o AnyDesk no gestionado (Vectores comunes de ataque).

---

### 6. Nuevas Obligaciones Tácticas (Ley 21.663 y Ley de Datos)

Más allá de la respuesta a incidentes, la normativa impone deberes preventivos y de diseño que transforman la arquitectura de seguridad.

#### A. Deber de Reporte Preventivo (Vulnerabilidades)
La obligación de informar no nace solo cuando "nos atacan" (Incidente), sino cuando "detectamos que somos vulnerables" (Amenaza).
* **El Gatillador:** Descubrimiento de una vulnerabilidad crítica (ej: CVSS > 9.0) en un activo esencial, o hallazgo de un *Zero Day* no parchado.
* **La Acción Legal:** Notificación preventiva al CSIRT Nacional (ANCI) según la normativa técnica vigente.
* **El Riesgo:** Ocultar una vulnerabilidad conocida que luego es explotada constituye un agravante de negligencia inexcusable.

#### B. La Muralla China: CISO vs. DPO
La normativa exige dos roles que, por diseño, deben operar con tensiones opuestas para evitar el conflicto de interés:

| Rol | Foco Principal | Ley Madre | Conflicto |
| :--- | :--- | :--- | :--- |
| **CISO (Encargado de Ciberseguridad)** | Continuidad Operacional, Seguridad de la Red, Disponibilidad. | Ley Marco (21.663) | Quien *implementa* el control. |
| **DPO (Delegado de Protección de Datos)** | Privacidad, Derechos ARCO, Consentimiento del Usuario. | Ley de Datos Personales | Quien *audita* el control. |

> **Advertencia de Gobernanza:** En organizaciones reguladas, fusionar ambos roles en una sola persona es un riesgo de cumplimiento. El auditor (DPO) no puede ser la misma persona que el auditado (CISO). "No poner al zorro a cuidar el gallinero".

---

### 57. La Zona Gris: Convergencia Regulatoria

**Cuidado:** Cumplir con la ANCI (Ciberseguridad) no garantiza cumplir con la Agencia de Protección de Datos. Son dos fiscalizadores distintos con multas independientes.

> **El Principio de Seguridad "Por Diseño" (Art. 14 quáter):**
> Si recuperas el sistema en 2 horas tras un ataque (Éxito ante ANCI), pero se filtraron las contraseñas de clientes en texto plano (Fracaso ante Datos), la multa es inevitable.
>
> **La Estrategia de Supervivencia:** El **Cifrado (Encryption)** es el único salvavidas doble.
> 1. Protege la integridad del activo (Ciberseguridad).
> 2. Hace que el dato robado sea ilegible, reduciendo drásticamente la multa por impacto a la privacidad (Protección de Datos).

---

### Resumen para el Directorio

Cuando el Directorio pregunte: *"¿Estamos seguros con este nuevo proveedor de Inteligencia Artificial?"*, la respuesta del Vigilante Estratégico debe ser:

> *"Técnicamente parece sólido, pero legalmente necesitamos ajustar el contrato. No podemos permitir que usen nuestros datos para entrenar sus modelos públicos y necesitamos que firmen la cláusula de notificación en 2 horas para cumplir con la Ley 21.663."*

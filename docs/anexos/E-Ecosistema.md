# ANEXO E: El Ecosistema Global de Inteligencia
**(Fuentes, Estándares y Organismos de Referencia)**

### Introducción: La Defensa es un Esfuerzo Global

En ciberseguridad, el aislamiento es sinónimo de vulnerabilidad. Ninguna organización, por grande que sea, puede identificar todas las amenazas por sí sola. Para que el **Vigilante Estratégico** sea efectivo, debe operar dentro de una infraestructura global de intercambio de información.

Este anexo detalla el ecosistema de inteligencia que permite a los expertos identificar, medir y priorizar fallos de seguridad basándose en estándares internacionales. Para el Mando Medio, estas siglas no son solo tecnicismos; son las **fuentes de autoridad** que respaldan la toma de decisiones ante el Directorio y la ANCI.

---

### 1. La Identidad: MITRE y los CVE

El primer paso para gestionar un riesgo es nombrarlo de forma inequívoca.

* **MITRE Corporation:** Organización sin fines de lucro que gestiona el sistema de identificación universal de vulnerabilidades bajo contrato con el gobierno de EE.UU.
* **CVE (*Common Vulnerabilities and Exposures*):** Es el "DNI" de una vulnerabilidad. Cada fallo identificado en un software comercial o de código abierto recibe un código único.
    * *Formato:* `CVE-AAAA-NNNNN` (Ej: `CVE-2026-12345`).
* **Valor Estratégico:** El uso de códigos CVE evita la ambigüedad en los reportes de incidentes y permite que el equipo técnico, los proveedores y los auditores hablen exactamente de lo mismo.

---

### 2. La Taxonomía: CWE (Common Weakness Enumeration)

Si el CVE identifica un fallo específico en un producto, el **CWE** identifica el *tipo* de error de ingeniería que lo causó.

* **Definición:** Una lista categorizada de debilidades de software (Ej: *CWE-79: Cross-site Scripting* o *CWE-89: SQL Injection*).
* **Valor Estratégico:** Permite al mando medio identificar **patrones de falla** en el desarrollo interno (Capítulo 12). Si la organización reporta múltiples CVEs asociados al mismo CWE, el problema no es el parche, sino el proceso de desarrollo seguro (*DevSecOps*).

---

### 3. La Medición: FIRST y el sistema CVSS

Una vez identificada, la vulnerabilidad debe ser pesada. El estándar global para esto es el **CVSS (*Common Vulnerability Scoring System*)**, mantenido por **FIRST**.

* **Puntuación Base:** Se calcula mediante una fórmula que evalúa la complejidad del ataque, si requiere privilegios y el impacto en la confidencialidad, integridad y disponibilidad (CIA).

* **Cálculo Técnico:** El puntaje se expresa en una escala de 0.0 a 10.0.
    $Score = f(Exploitability, Impact)$

* **Valor Estratégico:** Proporciona una métrica objetiva para la priorización. Una vulnerabilidad con un **CVSS de 9.0+ (Crítica)** debe detener cualquier otro proyecto hasta ser remediada para evitar negligencia.

---

### 4. El Repositorio Maestro: NIST y la NVD

La **NVD (*National Vulnerability Database*)** es el repositorio centralizado gestionado por el **NIST** (National Institute of Standards and Technology).

* **Función:** Sincroniza con la lista de MITRE y enriquece cada CVE con análisis técnicos, puntajes CVSS oficiales y enlaces a parches de los fabricantes.
* **Valor Estratégico:** Es la "fuente de verdad" para las herramientas de escaneo y auditoría. Si una vulnerabilidad no está analizada en la NVD, su gestión suele carecer de respaldo para auditorías internacionales.

---

### 5. La Inteligencia de Acción: CISA y el catálogo KEV

Este es el componente más crítico para la resiliencia moderna (2025-2026). Mientras el CVSS mide la gravedad teórica, el **KEV (*Known Exploited Vulnerabilities*)** mide la realidad.

* **KEV de CISA:** Un catálogo de vulnerabilidades que la agencia de seguridad de EE.UU. ha confirmado que **ya están siendo explotadas activamente por atacantes** en el mundo real.
* **Regla del Mando Medio:** Si una vulnerabilidad tiene un CVSS alto y además aparece en el catálogo KEV, la orden de remediación es **indiscutible e inmediata**.
    * *No se discute el "si", se discute el "cuándo" (y la respuesta debe ser "ahora").*
    * *Ignorar una vulnerabilidad KEV es evidencia de falta de Debida Diligencia.*

---

### 6. Comunidades de Intercambio (ISACs y CSIRTs)

La inteligencia no es solo estática; es humana y relacional.

* **ISAC (*Information Sharing and Analysis Centers*):** Foros sectoriales (Financiero, Salud, Energía) donde las empresas comparten inteligencia de amenazas de forma anónima para proteger el ecosistema común.
* **CSIRT Nacional (Chile):** El centro de respuesta del gobierno que actúa como nodo de alerta temprana para incidentes que afectan la infraestructura crítica nacional (**Ley 21.663**).

---

### 7. Resumen: Matriz de Uso para el Vigilante

| Acrónimo | Pregunta que Responde | Uso Principal |
| :--- | :--- | :--- |
| **CVE** | ¿Cómo se llama el problema? | Identificación única en contratos y reportes. |
| **CVSS** | ¿Qué tan grave es teóricamente? | Priorización automática en tableros. |
| **KEV** | ¿Me van a atacar hoy? | **Urgencia Máxima.** Gatillador de ventanas de emergencia. |
| **CWE** | ¿Por qué fallamos al programar? | Mejora continua del ciclo de desarrollo. |

---

### 8. Plantilla de Notificación Técnica (Ejemplo)

Cuando un ingeniero informa una vulnerabilidad al Comité, debe usar este estándar de autoridad:

> **REPORTE DE VULNERABILIDAD CRÍTICA**
>
> "Se ha detectado el **CVE-2026-XXXX** (Tipo: *CWE-89 SQL Injection*) en el servidor de Pagos.
>
> * **Severidad Técnica:** Puntaje **CVSS de 9.8** (Crítico).
> * **Estado de Amenaza:** Esta vulnerabilidad figura en el **catálogo KEV de CISA**, lo que confirma que hay grupos de ransomware explotándola activamente hoy.
>
> **Conclusión:** Se requiere aplicar el parche de seguridad en las próximas **24 horas** para mantener el cumplimiento normativo."

# Glosario Unificado
**(El Lenguaje del Vigilante Estratégico)**

### Introducción: Un Lenguaje Común

Este anexo es el léxico centralizado de "Ciberseguridad Orientada a Resultados". La terminología en este campo suele ser confusa y está plagada de acrónimos técnicos; un malentendido conceptual entre el CISO y el Directorio puede llevar a una parálisis en la toma de decisiones o a una asignación ineficiente de capital. Este glosario no es solo una lista de definiciones; es un mapa de referencia que conecta los conceptos técnicos con los bloques estratégicos donde se exploran en profundidad. Úsalo para asegurar que tanto ingenieros como ejecutivos hablen el mismo idioma durante la gestión del riesgo y la crisis.

---

### Léxico de "Ciberseguridad Orientada a Resultados"

**ABAC (Attribute-Based Access Control)**
* **Definición:** *Control de Acceso Basado en Atributos.* Modelo que otorga permisos según un contexto dinámico (rol, ubicación, estado del dispositivo). Es el estándar para arquitecturas Zero Trust de alta madurez.
* **Referencia Principal:** Capítulo 05.

**Air-Gap (Brecha de Aire)**
* **Definición:** Medida de seguridad física o lógica donde un sistema de respaldo o red crítica está completamente aislado y desconectado de cualquier otra red, haciendo imposible el acceso remoto para un atacante.
* **Referencia Principal:** Anexo I / Anexo K.

**ALE (Annualized Loss Expectancy)**
* **Definición:** *Expectativa de Pérdida Anualizada.* Métrica financiera que proyecta la pérdida anual por un riesgo específico. 
* **Fórmula:** $$ALE = SLE \times ARO$$.
* **Referencia Principal:** Capítulo 02.

**ANCI (Agencia Nacional de Ciberseguridad)**
* **Definición:** Órgano fiscalizador en Chile con potestad para calificar la suficiencia de las medidas de seguridad y sancionar la negligencia bajo la Ley 21.663.
* **Referencia Principal:** Capítulo 03.

**Antifragilidad**
* **Definición:** Capacidad de una organización para fortalecerse y mejorar a partir de eventos de estrés, fallos o desastres.
* **Referencia Principal:** Capítulo 12.

**ARO (Annualized Rate of Occurrence)**
* **Definición:** *Tasa de Ocurrencia Anualizada.* Estimación de cuántas veces al año se espera que ocurra un evento de riesgo.
* **Referencia Principal:** Capítulo 02.

**Asumir la Brecha (Assume Breach)**
* **Definición:** Mentalidad de diseño que asume que el atacante ya ha comprometido el perímetro, priorizando la detección y la contención interna.
* **Referencia Principal:** Capítulo 04.

**BCP (Business Continuity Plan)**
* **Definición:** *Plan de Continuidad de Negocio.* Estrategia para mantener las operaciones críticas (procesos manuales, planes B) mientras la tecnología está fuera de servicio.
* **Referencia Principal:** Capítulo 11.

**BIA (Business Impact Analysis)**
* **Definición:** *Análisis de Impacto al Negocio.* Proceso que determina los tiempos máximos tolerables de interrupción (*RTO*) y pérdida de datos (*RPO*) para cada proceso vital.
* **Referencia Principal:** Capítulo 11.

**Botón Rojo**
* **Definición:** Metáfora de la decisión soberana del Directorio de desconectar servicios críticos para contener un daño irreversible.
* **Referencia Principal:** Capítulo 10.

**CISO Centauro**
* **Definición:** Modelo de liderazgo donde el humano utiliza la IA para gestionar la escala técnica mientras preserva la soberanía del criterio estratégico.
* **Referencia Principal:** Capítulo 13.

**CSIRT (Computer Security Incident Response Team)**
* **Definición:** Equipo especializado responsable de la respuesta táctica ante incidentes de seguridad.
* **Referencia Principal:** Capítulo 07.

**CVE / CWE**
* **Definición:** Estándares universales de fallos. 
    * **CVE:** Identificador único de una vulnerabilidad específica en un producto.
    * **CWE:** Categoría de debilidad de diseño o programación (ej. Inyección SQL).
* **Referencia Principal:** Anexo E / Anexo F.

**CVSS (Common Vulnerability Scoring System)**
* **Definición:** Sistema de puntuación (0 a 10) que mide la severidad técnica de una vulnerabilidad.
* **Referencia Principal:** Anexo F.

**Debida Diligencia**
* **Definición:** Estado de cumplimiento continuo probado mediante decisiones informadas y documentadas para exonerar de responsabilidad a la dirección ante la ANCI.
* **Referencia Principal:** Capítulo 03.

**DLP (Data Loss Prevention)**
* **Definición:** *Prevención de Fuga de Datos.* Capacidad técnica para evitar que información sensible abandone la organización en reposo, tránsito o uso.
* **Referencia Principal:** Capítulo 06.

**DRP (Disaster Recovery Plan)**
* **Definición:** *Plan de Recuperación de Desastres.* Brazo técnico enfocado en restaurar servidores, redes y datos desde respaldos.
* **Referencia Principal:** Capítulo 11.

**EPSS (Exploit Prediction Scoring System)**
* **Definición:** Probabilidad real de que una vulnerabilidad sea explotada en los próximos 30 días.
* **Referencia Principal:** Capítulo 02.

**Flash Report**
* **Definición:** Primer artefacto de evidencia de debida diligencia generado al Minuto 60 de un incidente para informar al Directorio sobre el impacto y la estrategia.
* **Referencia Principal:** Capítulo 07 / Anexo D.

**IAM (Identity and Access Management)**
* **Definición:** Gestión del ciclo de vida de las identidades (*Joiner, Mover, Leaver*) como eje central de la gobernanza.
* **Referencia Principal:** Capítulo 05.

**IRP (Incident Response Plan)**
* **Definición:** *Plan de Respuesta a Incidentes.* Manual de guerra para transformar una intrusión en una operación de contención controlada.
* **Referencia Principal:** Capítulo 07.

**KEV (Known Exploited Vulnerabilities)**
* **Definición:** Catálogo de vulnerabilidades que ya están siendo usadas por atacantes en el mundo real.
* **Referencia Principal:** Anexo E.

**Ley 21.663**
* **Definición:** Ley Marco de Ciberseguridad en Chile que establece deberes de dirección y sanciones por negligencia.
* **Referencia Principal:** Capítulo 01 / Capítulo 03.

**MFA (Multi-Factor Authentication)**
* **Definición:** Autenticación basada en algo que sabes, tienes o eres.
* **Referencia Principal:** Capítulo 05.

**Microsegmentación**
* **Definición:** División de la red en compartimentos estancos para reducir el radio de explosión.
* **Referencia Principal:** Capítulo 04.

**MTTR (Mean Time To Remediate)**
* **Definición:** *Tiempo Medio de Remediación.* Métrica que mide la velocidad de vuelta a la normalidad operativa.
* **Fórmula:** $$MTTR = \frac{\sum (Fin \: Incidente - Detección)}{Número \: de \: Incidentes}$$.
* **Referencia Principal:** Capítulo 08.

**PAM (Privileged Access Management)**
* **Definición:** Control estricto de cuentas de administrador mediante bóvedas y acceso Just-in-Time (*JIT*).
* **Referencia Principal:** Capítulo 05.

**PoLP (Principle of Least Privilege)**
* **Definición:** *Principio de Mínimo Privilegio.* Otorgar solo el acceso necesario para la tarea y solo durante el tiempo requerido.
* **Referencia Principal:** Capítulo 04.

**ROS (Return on Security)**
* **Definición:** Evaluación de la eficiencia financiera de una inversión en seguridad frente al riesgo reducido.
* **Referencia Principal:** Capítulo 02.

**RTO / RPO**
* **Definición:** Indicadores críticos de recuperación.
    * **RTO:** Tiempo máximo de recuperación aceptable.
    * **RPO:** Cantidad máxima de pérdida de datos tolerable.
* **Referencia Principal:** Capítulo 11.

**SLE (Single Loss Expectancy)**
* **Definición:** *Expectativa de Pérdida Única.* Costo monetario de un incidente si ocurre una sola vez.
* **Referencia Principal:** Capítulo 02.

**SOAR (Security Orchestration, Automation, and Response)**
* **Definición:** Capa tecnológica que automatiza la respuesta mediante *playbooks* que generan evidencia inalterable.
* **Referencia Principal:** Capítulo 08.

**Zero Trust (Confianza Cero)**
* **Definición:** Modelo basado en "nunca confiar, siempre verificar", eliminando la noción de red interna segura.
* **Referencia Principal:** Capítulo 04.
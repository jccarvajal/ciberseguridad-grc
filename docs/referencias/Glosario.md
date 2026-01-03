## Glosario Unificado

### Introducción: Un Lenguaje Común

Este anexo es el léxico centralizado de "Ciberseguridad Orientada a Resultados". La terminología en este campo suele ser confusa y está plagada de acrónimos técnicos; un malentendido conceptual entre el CISO y el Directorio puede llevar a una parálisis en la toma de decisiones o a una asignación ineficiente de capital. Este glosario no es solo una lista de definiciones; es un mapa de referencia que conecta los conceptos técnicos con los bloques estratégicos donde se exploran en profundidad. Úsalo para asegurar que tanto ingenieros como ejecutivos hablen el mismo idioma durante la gestión del riesgo y la crisis.

---

### Léxico de "Ciberseguridad Orientada a Resultados"

**ALE (Annualized Loss Expectancy)**
* **Definición:** *Expectativa de Pérdida Anualizada.* Es la métrica financiera que proyecta cuánto dinero perderá la organización en un año debido a un riesgo específico si no se aplican controles. Es la base para calcular el ROI de cualquier inversión en seguridad.
* **Referencia Principal:** Capítulo 02 (Riesgo Financiero), Anexo B (Métricas).

**Asumir la Brecha (Assume Breach)**
* **Definición:** El cambio de paradigma fundamental. Es la mentalidad de diseño que asume que el atacante ya ha comprometido el perímetro y está dentro de la red. Obliga a priorizar la detección y la velocidad de recuperación.
* **Referencia Principal:** Capítulo 04 (Zero Trust), Nota Metodológica.

**BCP (Business Continuity Plan)**
* **Definición:** *Plan de Continuidad de Negocio.* Documento estratégico que describe cómo la organización mantendrá sus operaciones críticas (procesos manuales, comunicación) mientras la tecnología está fuera de servicio.
* **Referencia Principal:** Capítulo 11 (Integración de la Resiliencia), Anexo J (Plan de Continuidad).

**BIA (Business Impact Analysis)**
* **Definición:** *Análisis de Impacto al Negocio.* Proceso para determinar cuáles son los procesos vitales de la organización y cuál es el tiempo máximo que pueden estar detenidos antes de que el daño sea irreversible.
* **Referencia Principal:** Capítulo 11 (Integración de la Resiliencia), Anexo J (Plan de Continuidad).

**CSIRT (Computer Security Incident Response Team)**
* **Definición:** El equipo especializado responsable de recibir, revisar y responder a informes y actividades de incidentes de seguridad informática. Es el "equipo de respuesta rápida" de la institución.
* **Referencia Principal:** Capítulo 07 (Flujo IRP), Anexo G (Estructura CSIRT).

**CVE / CWE (Common Vulnerabilities and Exposures / Weakness Enumeration)**
* **Definición:** Estándares universales para identificar fallos. 
    * **CVE:** Es el identificador único para una vulnerabilidad específica en un producto real. 
    * **CWE:** Es la categoría o tipo de error de arquitectura/programación (ej. "Inyección de SQL").
* **Referencia Principal:** Anexo F (Gestión de Vulnerabilidades), Anexo E (Ecosistema de Inteligencia).

**CVSS (Common Vulnerability Scoring System)**
* **Definición:** Sistema de puntuación estándar (0 a 10) que mide la severidad técnica de una vulnerabilidad. Permite a los ingenieros priorizar el parcheo basándose en métricas objetivas como el vector de ataque y el impacto en la confidencialidad.
* **Referencia Principal:** Anexo F (Gestión de Vulnerabilidades), Anexo E (Ecosistema de Inteligencia).

**DRP (Disaster Recovery Plan)**
* **Definición:** *Plan de Recuperación de Desastres.* Es el brazo técnico de la continuidad. Se enfoca exclusivamente en la restauración de los sistemas, servidores, redes y datos después de un evento catastrófico o ataque de ransomware.
* **Referencia Principal:** Capítulo 11 (Integración de la Resiliencia), Anexo I (Plan DRP).

**KEV (Known Exploited Vulnerabilities)**
* **Definición:** *Catálogo de Vulnerabilidades Explotadas Conocidas.* Lista mantenida por CISA que identifica fallos que **ya están siendo usados por atacantes** en el mundo real. Es la métrica de urgencia más alta para un Mando Medio.
* **Referencia Principal:** Anexo E (Ecosistema de Inteligencia), Anexo F (Gestión de Vulnerabilidades).

**MITRE (MITRE Corporation)**
* **Definición:** Organización sin fines de lucro que gestiona el sistema CVE y el framework ATT&CK. Actúa como el árbitro central que estandariza cómo se nombran las vulnerabilidades y cómo se describen las tácticas de los atacantes a nivel global.
* **Referencia Principal:** Anexo E (Ecosistema de Inteligencia).

**NVD (National Vulnerability Database)**
* **Definición:** El repositorio del gobierno de EE.UU. (NIST) que centraliza y analiza todos los CVEs del mundo, proveyendo los puntajes CVSS oficiales de los que se alimentan los softwares de escaneo.
* **Referencia Principal:** Anexo E (Ecosistema de Inteligencia).

**RTO / RPO (Recovery Time Objective / Recovery Point Objective)**
* **Definición:** Los dos indicadores críticos de recuperación.
    * **RTO (Tiempo):** ¿Cuánto tiempo tardamos en volver a operar? 
    * **RPO (Datos):** ¿Cuánta información estamos dispuestos a perder? 
* **Referencia Principal:** Capítulo 11 (Integración de la Resiliencia), Anexo I (Plan DRP).

**Zero Trust (Confianza Cero)**
* **Definición:** Modelo de seguridad basado en el principio "nunca confiar, siempre verificar". Elimina el concepto de "red interna segura" y requiere autenticación continua para cada acceso a recursos.
* **Referencia Principal:** Capítulo 04 (Zero Trust), Anexo C (Checklist Zero Trust).

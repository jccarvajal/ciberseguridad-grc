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

**Asimetría de Información**

* **Definición:** Fenómeno económico donde una parte (el Directorio) tiene menos información que la otra (el CISO) para tomar una decisión, resultando en una valoración ineficiente del riesgo ("Mercado de los Limones").
* **Referencia Principal:** Capítulo 01.

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

**Clean Room (Zona Limpia)**

* **Definición:** Entorno de red aislado y saneado donde se realiza la restauración de sistemas críticos durante un incidente, garantizando que no haya reinfección antes de volver a producción.
* **Referencia Principal:** Anexo I.

**CSIRT (Computer Security Incident Response Team)**

* **Definición:** Equipo especializado responsable de la respuesta táctica ante incidentes de seguridad.
* **Referencia Principal:** Capítulo 07.

**Culpa in Vigilando**

* **Definición:** Doctrina legal que establece la responsabilidad del superior (Directorio) por no haber supervisado adecuadamente a quienes están bajo su mando. Impide delegar la culpa penal en el técnico que cometió el error.
* **Referencia Principal:** Capítulo 10.

**CVE / CWE**

* **Definición:** Estándares universales de fallos. 
    * **CVE:** Identificador único de una vulnerabilidad específica en un producto.
    * **CWE:** Categoría de debilidad de diseño o programación (ej. Inyección SQL).
* **Referencia Principal:** Anexo E / Anexo F.

**CVSS (Common Vulnerability Scoring System)**

* **Definición:** Sistema de puntuación (0 a 10) que mide la severidad técnica de una vulnerabilidad.
* **Referencia Principal:** Anexo F.

**Dark Data (Datos Oscuros)**

* **Definición:** Activos de información que la organización recolecta y almacena pero no utiliza. Representan un pasivo tóxico: generan costo de almacenamiento y riesgo legal masivo sin aportar valor comercial.
* **Referencia Principal:** Capítulo 06.

**Debida Diligencia**

* **Definición:** Estado de cumplimiento continuo probado mediante decisiones informadas y documentadas para exonerar de responsabilidad a la dirección ante la ANCI.
* **Referencia Principal:** Capítulo 03.

**Defensa Agéntica**

* **Definición:** Evolución de la ciberseguridad donde sistemas autónomos de IA tienen la facultad de razonar y ejecutar contramedidas (bloqueos, aislamiento) sin intervención humana para combatir amenazas de alta velocidad.
* **Referencia Principal:** Capítulo 13.

**DLP (Data Loss Prevention)**

* **Definición:** *Prevención de Fuga de Datos.* Capacidad técnica para evitar que información sensible abandone la organización en reposo, tránsito o uso.
* **Referencia Principal:** Capítulo 06.

**DRP (Disaster Recovery Plan)**

* **Definición:** *Plan de Recuperación de Desastres.* Brazo técnico enfocado en restaurar servidores, redes y datos desde respaldos.
* **Referencia Principal:** Capítulo 11.

**EDR / XDR (Endpoint/Extended Detection and Response)**

* **Definición:** Evolución del antivirus tradicional. No solo bloquea virus conocidos, sino que monitorea comportamientos anómalos, graba la actividad para análisis forense y permite aislar el equipo remotamente.
* **Referencia Principal:** Anexo C.

**EPSS (Exploit Prediction Scoring System)**

* **Definición:** Probabilidad real de que una vulnerabilidad sea explotada en los próximos 30 días.
* **Referencia Principal:** Capítulo 02.

**Flash Report**

* **Definición:** Primer artefacto de evidencia de debida diligencia generado al Minuto 60 de un incidente para informar al Directorio sobre el impacto y la estrategia.
* **Referencia Principal:** Capítulo 07 / Anexo D.

**IAM (Identity and Access Management)**

* **Definición:** Gestión del ciclo de vida de las identidades (*Joiner, Mover, Leaver*) como eje central de la gobernanza.
* **Referencia Principal:** Capítulo 05.

**Incident Commander (IC)**

* **Definición:** Rol de autoridad absoluta durante una crisis (Nivel 1 o 2). Es el "Director de Orquesta" que toma las decisiones tácticas y autoriza acciones drásticas (como desconexiones) sin burocracia.
* **Referencia Principal:** Anexo G / Anexo H.

**Incidente vs. Ciberataque**

* **Definición:** Distinción jurídica crítica. Un **Incidente** es cualquier interrupción de la tríada CIA (puede ser accidental). Un **Ciberataque** implica dolo y acción deliberada de un tercero. No se deben usar como sinónimos en reportes legales.
* **Referencia Principal:** Capítulo 09.

**IRP (Incident Response Plan)**

* **Definición:** *Plan de Respuesta a Incidentes.* Manual de guerra para transformar una intrusión en una operación de contención controlada.
* **Referencia Principal:** Capítulo 07.

**KEV (Known Exploited Vulnerabilities)**

* **Definición:** Catálogo de vulnerabilidades que ya están siendo usadas por atacantes en el mundo real.
* **Referencia Principal:** Anexo E.

**KPI vs. KRI**

* **Definición:** Distinción métrica fundamental. **KPI** (*Key Performance Indicator*) mira hacia atrás (desempeño pasado), mientras que **KRI** (*Key Risk Indicator*) mira hacia adelante (probabilidad futura de un evento adverso).
* **Referencia Principal:** Anexo B.

**Ley 21.663**

* **Definición:** Ley Marco de Ciberseguridad en Chile que establece deberes de dirección y sanciones por negligencia.
* **Referencia Principal:** Capítulo 01 / Capítulo 03.

**MFA (Multi-Factor Authentication)**

* **Definición:** Autenticación basada en algo que sabes, tienes o eres.
* **Referencia Principal:** Capítulo 05.

**Microsegmentación**

* **Definición:** División de la red en compartimentos estancos para reducir el radio de explosión.
* **Referencia Principal:** Capítulo 04.

**MITRE ATT&CK**

* **Definición:** Base de conocimiento global que describe las *Tácticas, Técnicas y Procedimientos* (TTPs) que usan los adversarios reales. Se usa para mapear si las defensas actuales cubren ataques específicos.
* **Referencia Principal:** Anexo E.

**MTPD (Maximum Tolerable Period of Disruption)**

* **Definición:** *Período Máximo Tolerable de Interrupción.* El tiempo límite que un proceso de negocio puede estar detenido antes de que el daño sea irreversible (quiebra, sanción fatal). Si el RTO supera al MTPD, el negocio muere.
* **Referencia Principal:** Anexo J.

**MTTD (Mean Time To Detect)**

* **Definición:** *Tiempo Medio de Detección.* El tiempo promedio que transcurre desde que el atacante entra en la red hasta que el sistema de vigilancia (SOC) lo ve. Es la métrica clave de la visibilidad.
* **Referencia Principal:** Anexo B.

**MTTR (Mean Time To Remediate)**

* **Definición:** *Tiempo Medio de Remediación.* Métrica que mide la velocidad de vuelta a la normalidad operativa.
* **Fórmula:** $$MTTR = \frac{\sum (Fin \: Incidente - Detección)}{Número \: de \: Incidentes}$$.
* **Referencia Principal:** Capítulo 08.

**OODA (Observar, Orientar, Decidir, Actuar)**

* **Definición:** Ciclo estratégico de combate (John Boyd). En ciberseguridad, el objetivo de la automatización (SOAR) es completar este ciclo más rápido que el adversario para neutralizar la amenaza antes de que se oriente en la red.
* **Referencia Principal:** Capítulo 08.

**Out-of-Band (OOB)**

* **Definición:** Canales de comunicación "Fuera de Banda" (ej: Signal, Satélite, Líneas análogas) que no dependen de la infraestructura corporativa y se usan cuando la red principal está comprometida o no es confiable.
* **Referencia Principal:** Anexo G.

**PAM (Privileged Access Management)**

* **Definición:** Control estricto de cuentas de administrador mediante bóvedas y acceso Just-in-Time (*JIT*).
* **Referencia Principal:** Capítulo 05.

**PoLP (Principle of Least Privilege)**

* **Definición:** *Principio de Mínimo Privilegio.* Otorgar solo el acceso necesario para la tarea y solo durante el tiempo requerido.
* **Referencia Principal:** Capítulo 04.

**RACI (Responsible, Accountable, Consulted, Informed)**

* **Definición:** Matriz de asignación de responsabilidades que elimina la ambigüedad operativa. Define quién ejecuta la tarea (R) y, crucialmente, quién responde (A) por el riesgo final ante el Directorio.
* **Referencia Principal:** Anexo A.

**Regla 3-2-1-1-0**

* **Definición:** Estándar de oro moderno para respaldos resilientes: 3 copias de datos, 2 medios diferentes, 1 copia fuera del sitio, 1 copia inmutable/offline y 0 errores de verificación (probados).
* **Referencia Principal:** Anexo I.

**Responsabilidad Solidaria**

* **Definición:** Principio legal (Ley 21.663) que establece que la organización contratante es responsable ante el regulador por las fallas de seguridad de sus proveedores. "Se delega el servicio, no la responsabilidad".
* **Referencia Principal:** Anexo L.

**ROS (Return on Security)**

* **Definición:** Evaluación de la eficiencia financiera de una inversión en seguridad frente al riesgo reducido.
* **Referencia Principal:** Capítulo 02.

**RTO / RPO**

* **Definición:** Indicadores críticos de recuperación.
    * **RTO:** Tiempo máximo de recuperación aceptable.
    * **RPO:** Cantidad máxima de pérdida de datos tolerable.
* **Referencia Principal:** Capítulo 11.

**Ruido (Noise)**

* **Definición:** Variabilidad no deseada en el juicio humano (Kahneman). A diferencia del sesgo (error sistemático), el ruido es la inconsistencia aleatoria entre diferentes expertos o del mismo experto en diferentes momentos.
* **Referencia Principal:** Capítulo 02.

**Shadow IT (TI en las Sombras)**

* **Definición:** Anti-patrón donde departamentos de negocio contratan software, hardware o servicios en la nube sin el conocimiento ni control del área de TI/Seguridad, creando puertas traseras invisibles.
* **Referencia Principal:** Anexo K.

**SLE (Single Loss Expectancy)**

* **Definición:** *Expectativa de Pérdida Única.* Costo monetario de un incidente si ocurre una sola vez.
* **Referencia Principal:** Capítulo 02.

**SOAR (Security Orchestration, Automation, and Response)**

* **Definición:** Capa tecnológica que automatiza la respuesta mediante *playbooks* que generan evidencia inalterable.
* **Referencia Principal:** Capítulo 08.

**TPRM (Third-Party Risk Management)**

* **Definición:** *Gestión de Riesgos de Terceros.* Disciplina de gobernanza enfocada en identificar y mitigar los riesgos introducidos por la cadena de suministro y proveedores externos.
* **Referencia Principal:** Anexo L.

**Zero Trust (Confianza Cero)**

* **Definición:** Modelo basado en "nunca confiar, siempre verificar", eliminando la noción de red interna segura.
* **Referencia Principal:** Capítulo 04.
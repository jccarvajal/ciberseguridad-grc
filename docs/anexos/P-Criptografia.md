# ANEXO P: Fragilidad Temporal del Control Criptográfico
**Riesgo Post-Cuántico, Persistencia del Secreto y Obsolescencia Asimétrica del Control**

> *Todo mecanismo de confianza tiene una fecha de vencimiento, incluso cuando esa fecha no aparece escrita en ninguna parte.*

## 1. La Vida Útil del Control y la Paradoja del Secreto Persistente

Todo control criptográfico posee una vida útil. No falla necesariamente por una vulnerabilidad, un error de implementación o una mala configuración. Puede fallar simplemente porque el tiempo transcurre. La arquitectura de seguridad contemporánea opera bajo el supuesto implícito de que los controles criptográficos vigentes hoy seguirán siendo controles vigentes mañana. Este supuesto resulta cada vez más difícil de sostener para horizontes de planificación de largo plazo.

La mayoría de los controles de seguridad se diseñan para proteger el presente. La criptografía, en cambio, protege simultáneamente el presente y el futuro. Por ello, el valor de un control criptográfico no depende solo de su resistencia actual, sino de si esa resistencia sobrevive durante toda la vida útil del secreto que protege. La pregunta correcta en el diseño de la arquitectura no es *"¿Es seguro hoy?"*, sino *"¿Seguirá siendo seguro hasta que el dato deje de tener valor?"*.

El riesgo post-cuántico es un problema de gestión del tiempo, no de gestión de algoritmos. El cifrado no protege para siempre; protege mientras el costo computacional de romperlo supere el valor del secreto. Cuando ese equilibrio se altera por avance tecnológico, el control expira. Este anexo extiende la lógica de *"Assume Breach"* al horizonte temporal del secreto.

---

## 2. La Amenaza: Harvest Now, Decrypt Later (HNDL)

El vector de ataque que hace urgente este análisis no requiere computadoras cuánticas operativas hoy. Requiere solo capacidad de almacenamiento, que es de bajo costo, y paciencia estratégica.

El ataque HNDL opera en dos fases:

*   **Fase 1 — Captura (presente):** El adversario intercepta y almacena tráfico cifrado en tránsito, respaldos exfiltrados y comunicaciones protegidas. El contenido es ilegible, pero se almacena para su uso futuro.
*   **Fase 2 — Descifrado (futuro):** Cuando la computación cuántica alcance la madurez suficiente para romper los algoritmos en uso, el adversario aplica esa capacidad retroactivamente sobre el material acumulado.

La consecuencia operativa es crítica: el riesgo de un dato cifrado hoy no se materializa hoy. Se materializa en el futuro, sobre una decisión tomada en el pasado, sin posibilidad de corrección retroactiva.

---

## 3. El Reloj de Obsolescencia Criptográfica

La distinción técnica fundamental ante la amenaza cuántica reside en el tipo de criptografía:

*   **Algoritmos en riesgo estructural:** La criptografía de clave pública (RSA, ECC, Diffie-Hellman) basa su seguridad en la dificultad de factorizar números enteros o calcular logaritmos discretos. El algoritmo de Shor resuelve ambos en tiempo polinomial. La seguridad de estos algoritmos no se degrada; colapsa.
*   **Algoritmos con resistencia cuántica:** La criptografía simétrica (AES-256) y las funciones hash (SHA-3) son resistentes. El algoritmo de Grover reduce su seguridad efectiva a la mitad, pero duplicar la longitud de clave compensa esta reducción (AES-256 cuántico equivale a AES-128 clásico).

Los estimados actuales (NIST y comunidad científica) sitúan la aparición de computadoras cuánticas con capacidad criptográficamente relevante (CRQC) durante la próxima década, aunque con incertidumbre significativa respecto de la fecha exacta. Esta no es una fecha de expiración precisa; es una ventana de riesgo creciente que ya está activa.

---

## 4. El Estándar de Respuesta y Estrategias Híbridas de Transición

En agosto de 2024, el NIST publicó los primeros estándares de criptografía post-cuántica (PQC):

*   **ML-KEM (FIPS 203):** Mecanismo de encapsulación de clave. Reemplaza RSA y ECDH para el intercambio de claves (TLS, VPN).
*   **ML-DSA (FIPS 204):** Esquema de firma digital. Reemplaza RSA y ECDSA para autenticación y certificados.
*   **SLH-DSA (FIPS 205):** Firma digital basada en funciones hash. Alternativa conservadora a ML-DSA.

El consenso operativo actual no implica una sustitución abrupta de los algoritmos clásicos, sino la adopción de **esquemas híbridos**. Durante el periodo de transición, las implementaciones deben combinar algoritmos clásicos probados con algoritmos post-cuánticos (ej. X25519 + ML-KEM para intercambio de claves). Esto asegura que la comunicación mantenga la seguridad del algoritmo clásico frente a vulnerabilidades imprevistas en las nuevas implementaciones matemáticas, mientras añade resistencia cuántica.

---

## 5. Gobernanza de Datos y Superficie Criptográfica

Antes de cualquier decisión de migración, la organización debe clasificar su información en función de su horizonte de confidencialidad. No todos los datos requieren protección PQC inmediata. 

**Clasificación por Horizonte de Confidencialidad**

| Tipo de Dato | Horizonte Estimado | Urgencia de Migración |
| :--- | :--- | :--- |
| Telemetría / Logs Operacionales | 1–3 años | Baja (No requiere PQC) |
| Información Financiera Transaccional | 5–10 años | Media (Planificación) |
| Datos Regulatorios y Evidencia Digital | 10+ años | Alta (Crítica) |
| Información Estratégica / Propiedad Intelectual | 15+ años | Alta (Crítica) |

Esta clasificación debe cruzarse con las cinco categorías de la superficie criptográfica:

1.  **Tránsito:** Protocolos TLS, VPN, SSH. Mayor exposición al ataque HNDL.
2.  **Reposo:** Cifrado de discos, bases de datos y respaldos.
3.  **Identidad y Autenticación:** Certificados X.509, tokens, infraestructura PKI.
4.  **Evidencia y Cadena de Custodia:** Registros de auditoría, documentos con firma electrónica.
5.  **Comunicaciones Estratégicas:** Correo cifrado, mensajería corporativa.

---

## 6. Implicaciones para la Cadena de Custodia Digital

Los registros de auditoría, los logs con firma digital y los documentos con firma electrónica avanzada constituyen la base de la evidencia forense en procesos de investigación, litigios o auditorías regulatorias.

La confianza en la autenticidad de firmas basadas en algoritmos vulnerables podría verse comprometida si las claves privadas asociadas pudieran ser reconstruidas mediante capacidad cuántica suficiente. La consecuencia práctica es que los registros de auditoría que deben mantener valor probatorio más allá del horizonte de vulnerabilidad cuántica deben ser refirmados con algoritmos post-cuánticos antes de que los originales sean vulnerables, o generarse nativamente con ML-DSA o SLH-DSA. Esto es una obligación de diseño para marcos regulatorios con retención documental extendida.

---

## 7. La Asimetría del Defensor y el Riesgo en la Cadena de Suministro

El defensor debe migrar su infraestructura manteniendo la operatividad, asumiendo costos inmediatos y gestionando la coexistencia de algoritmos. El atacante, en cambio, tiene un costo marginal de almacenamiento y su inversión se amortiza con la espera. Posponer la migración traslada el riesgo al futuro mientras el adversario acumula material en el presente.

A nivel de gobernanza, el principal riesgo de migración no suele encontrarse en la organización, sino en su ecosistema tecnológico. La superficie criptográfica depende de proveedores de *appliances*, módulos HSM, firewalls y sistemas *legacy* que pueden impedir la adopción técnica. La gobernanza del riesgo post-cuántico exige auditoría estricta sobre la cadena de suministro y la exigencia contractual de hojas de ruta de migración verificables a los proveedores críticos.

---

## 8. La Criptografía Obsoleta como Deuda Técnica

La dependencia prolongada de algoritmos criptográficos cuya sustitución futura ya es conocida constituye una forma de deuda técnica. La diferencia respecto de otras deudas tecnológicas es que su interés no se paga en costos operativos, sino en riesgo acumulado sobre la confidencialidad futura de la información. 

Toda organización conoce la fecha de vencimiento de sus certificados digitales. Pocas conocen la fecha de vencimiento de los fundamentos matemáticos que los sostienen. Esta métrica de deuda técnica permite a la dirección evaluar la migración PQC no como un proyecto de TI aislado, sino como la mitigación de un pasivo estructural que amenaza la integridad de los activos de información a largo plazo.

---

## 9. Conclusión

La criptografía es el fundamento técnico de la arquitectura de seguridad: el cifrado en Zero Trust, la autenticidad en IAM, la integridad en los logs, la confidencialidad en el IRP. Si ese fundamento tiene fecha de expiración, todo lo construido sobre él comparte esa fragilidad.

La obsolescencia del control criptográfico no se gestiona en el momento del colapso. Se gestiona en el momento del diseño. La organización que prioriza su inventario criptográfico mediante el análisis de horizontes de confidencialidad y exposición a redes públicas dispone del margen temporal necesario para ejecutar una transición estructurada.

*(Este anexo complementa el Capítulo 02: Matemática del Riesgo, el Capítulo 04: Zero Trust, el Capítulo 05: Identidad — IAM, el Capítulo 13: El Futuro Inevitable y el Anexo O: Ley Marco Ciberseguridad).*

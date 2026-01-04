# CAPÍTULO 7: El Flujo del Incidente (IRP)
**(El Manual de Guerra para el "Día Cero")**

En los capítulos anteriores diseñamos defensas, calculamos riesgos y establecimos leyes. Pero en ciberseguridad, existe una máxima ineludible: **La protección absoluta es una ilusión.** Tarde o temprano, un atacante encontrará una brecha, un empleado cometerá un error o un sistema fallará. 

La diferencia entre una organización que sobrevive y una que colapsa no es el ataque en sí, sino su **Plan de Respuesta a Incidentes (IRP)**. En el marco de la Ley 21.663, un incidente no es solo un evento técnico: es un **hecho jurídico**. El IRP no existe para “apagar incendios”, sino para demostrar que cada decisión tomada bajo presión fue razonable, documentada y defendible ante el escrutinio regulatorio.

### 1. El Ciclo de Vida del Incidente (NIST 800-61)

Para el **Vigilante Estratégico**, responder no es correr en círculos; es seguir un ciclo de cuatro fases diseñado para minimizar el $SLE$ (Impacto de un solo evento):

1.  **Preparación:** La fase más crítica. Ocurre *antes* del ataque e incluye la formación del equipo **CSIRT** (Anexo G) y la creación de los libros de jugadas (*Playbooks*).
2.  **Detección y Análisis:** El momento en que los sensores (Capítulo 4) disparan una alerta. El **Ingeniero** debe validar si es un falso positivo o un incidente real.
3.  **Contención, Erradicación y Recuperación (CER):** El corazón de la batalla. El objetivo es detener el fuego, limpiar la casa y restaurar la operación.
4.  **Actividad Post-Incidente:** El proceso de aprendizaje técnico y estratégico indispensable para la mejora continua (Capítulo 12).

---

### 2. El Triángulo CER: La Táctica de Combate

El **Ingeniero** y el **Mando Medio** deben ejecutar estas tres etapas con precisión quirúrgica para salvaguardar la **debida diligencia**:

* **Contención:** Detener la hemorragia. Si un activo está comprometido, se aísla mediante microsegmentación. El objetivo es que el **radio de explosión** no afecte la continuidad sistémica.
* **Erradicación:** Eliminar la causa raíz. Si el atacante explotó un **CVE crítico** (Anexo F), se cierra la vulnerabilidad y se eliminan las persistencias (*backdoors*) detectadas.
* **Recuperación:** Retorno a la normalidad. Se restauran sistemas desde respaldos verificados y se valida la integridad antes de restablecer el servicio.

---

### 3. El Rol del Mando Medio: El "Flash Report"

Durante un incidente, el Directorio no requiere detalles de código; exige visibilidad sobre el riesgo de continuidad. El **Mando Medio** actúa como el traductor de crisis mediante el **Flash Report** (Ver **Anexo D**):

El **Flash Report** no es un resumen operativo: es el primer artefacto de **evidencia de debida diligencia** que permite demostrar que la alta dirección fue informada oportunamente y tomó decisiones bajo la mejor información disponible.

* **Minuto 0:** Detección técnica.
* **Minuto 15:** Notificación al CISO.
* **Minuto 60:** Primer reporte ejecutivo: ¿Qué ocurrió?, ¿Cuál es el impacto potencial? y ¿Cuál es la estrategia de contención?

---

### 4. Blueprint 7: El Tablero de Comando del Incidente

| Fase | Acción Clave | Responsable | Soporte |
| :--- | :--- | :--- | :--- |
| **Triage** | Clasificar severidad (Baja a Crítica). | Ingeniero | **Anexo F** (CVSS/KEV) |
| **Aislamiento** | Ejecutar bloqueo de red o de cuentas. | Ingeniero | **Anexo E** (PAM/IAM) |
| **Comunicación** | Emitir reporte ejecutivo y evaluar umbrales de notificación regulatoria. | Mando Medio | **Anexo D** (Reporting) |
| **Evidencia** | Preservar logs y memoria para análisis forense. | Ingeniero | **Anexo L** (Glosario) |

---

### 5. La Regla de Oro: Evidencia vs. Velocidad

Un error crítico es priorizar la recuperación inmediata borrando las huellas del atacante. El **Vigilante Estratégico** sabe que sin evidencia no existe defensa legal ante la **ANCI** (Ley 21.663). La **debida diligencia** exige:

1.  **Contener:** Detener el daño operativo.
2.  **Preservar:** Asegurar logs y memorias para el análisis de causa raíz.
3.  **Erradicar y Recuperar:** Solo tras garantizar la trazabilidad del incidente.

---

### Conclusión: El Sistema Inmunológico Institucional

El IRP es el sistema inmunológico de la organización. El ingeniero que detecta y el mando medio que coordina son los agentes que evitan que una infección se convierta en una falla orgánica sistémica. En términos de gobernanza, un IRP que no genera evidencia es indistinguible de la improvisación; y la improvisación, bajo escrutinio regulatorio, es sinónimo de negligencia.

Si el IRP funciona bajo los principios de la **debida diligencia**, el incidente es una lección operativa; si falla, es el fin de la organización. En el próximo capítulo, veremos cómo potenciar este flujo mediante la **Automatización (SOAR)**.

---

> **Tesis del Capítulo:** En una crisis, la velocidad es importante, pero el orden es vital. No se responde al instinto; se responde al proceso. Un incidente gestionado con evidencia es la prueba máxima de madurez institucional y debida diligencia.

---
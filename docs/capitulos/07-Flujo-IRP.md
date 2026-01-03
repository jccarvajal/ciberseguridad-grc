# CAPÍTULO 7: El Flujo del Incidente (IRP)
**(El Manual de Guerra para el "Día Cero")**

En los capítulos anteriores diseñamos defensas, calculamos riesgos y establecimos leyes. Pero en ciberseguridad, existe una máxima ineludible: **La protección absoluta es una ilusión.** Tarde o temprano, un atacante encontrará una brecha, un empleado cometerá un error o un sistema fallará. 

La diferencia entre una organización que sobrevive y una que colapsa no es el ataque en sí, sino su **Plan de Respuesta a Incidentes (IRP)**. Este capítulo detalla el flujo de trabajo que transforma el caos de una intrusión en una operación de contención controlada.

### 1. El Ciclo de Vida del Incidente (NIST 800-61)

Para el **Vigilante Estratégico**, responder no es correr en círculos; es seguir un ciclo de cuatro fases diseñado para minimizar el **SLE** (Impacto de un solo evento):

1.  **Preparación:** La fase más importante. Ocurre *antes* del ataque. Incluye la formación del equipo **CSIRT** (Anexo G) y la creación de los libros de jugadas (*Playbooks*).
2.  **Detección y Análisis:** El momento en que los sensores (Capítulo 4) disparan una alerta. El **Ingeniero** debe validar si es un falso positivo o un incidente real.
3.  **Contención, Erradicación y Recuperación (CER):** El corazón de la batalla. El objetivo es detener el fuego, limpiar la casa y volver a operar.
4.  **Actividad Post-Incidente:** El aprendizaje técnico y estratégico (Capítulo 12).

---

### 2. El Triángulo CER: La Táctica de Combate

El **Ingeniero** y el **Mando Medio** deben ejecutar estas tres etapas con precisión quirúrgica:

* **Contención:** Detener la hemorragia. Si un servidor está infectado, se aísla de la red (Microsegmentación). El objetivo es que el **radio de explosión** no crezca.
* **Erradicación:** Eliminar la causa raíz. Si el atacante entró por un **CVE crítico** (Anexo F), se cierra la vulnerabilidad y se eliminan las "puertas traseras" que el atacante pudo haber dejado.
* **Recuperación:** El retorno a la normalidad. Se restauran sistemas desde respaldos limpios y se verifica que el servicio sea seguro antes de abrirlo al público.



---

### 3. El Rol del Mando Medio: El "Flash Report"

Durante un incidente, el Directorio no necesita saber qué línea de código falló; necesita saber si el negocio está en peligro. El **Mando Medio** actúa como el traductor de crisis mediante el **Flash Report** (Ver **Anexo D**):

* **Minuto 0:** Detección técnica.
* **Minuto 15:** Notificación al CISO.
* **Minuto 60:** Primer reporte ejecutivo con tres datos: ¿Qué pasó? ¿Cuál es el impacto potencial? ¿Qué estamos haciendo ahora?

---

### 4. Blueprint 7: El Tablero de Comando del Incidente

Este tablero permite al **CSIRT** mantener el control bajo presión:

| Fase | Acción Clave | Responsable | Herramienta de Soporte |
| :--- | :--- | :--- | :--- |
| **Triage** | Clasificar la severidad (Baja, Media, Alta, Crítica). | Ingeniero / Analista | **Anexo F** (CVSS/KEV) |
| **Aislamiento** | Ejecutar bloqueo de red o de cuentas privilegiadas. | Ingeniero | **Anexo E** (PAM/IAM) |
| **Comunicación** | Emitir el primer reporte de situación. | Mando Medio | **Anexo D** (Reporting) |
| **Evidencia** | Preservar logs y memoria para análisis forense. | Ingeniero | **Anexo L** (Glosario) |

---

### 5. La Regla de Oro: Evidencia vs. Velocidad

Un error común de los ingenieros novatos es "limpiar" el sistema demasiado rápido para volver a operar, borrando las huellas del atacante. El **Vigilante Estratégico** sabe que sin evidencia no hay aprendizaje ni acción legal (Ley 21.663).
* **Primero:** Contener (detener el daño).
* **Segundo:** Preservar (clonar discos, guardar logs).
* **Tercero:** Erradicar y Recuperar.

### Conclusión para el "Vigilante Estratégico"

El IRP es el sistema inmunológico de la empresa. El ingeniero que detecta y el mando medio que coordina son los anticuerpos que evitan que una infección se convierta en una falla orgánica sistémica. Si el IRP funciona, el incidente es solo una anécdota costosa; si falla, el incidente es el fin de la organización.

En el próximo capítulo, veremos cómo potenciar este flujo mediante la **Automatización (SOAR)**, para que la respuesta no dependa solo de la velocidad humana, sino de la potencia de la arquitectura.

---
> **Tesis del Capítulo:** En una crisis, la velocidad es importante, pero el orden es vital. No se responde al instinto; se responde al proceso. Un incidente bien gestionado es la prueba máxima de madurez institucional.
---
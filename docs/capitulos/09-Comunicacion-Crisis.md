# CAPÍTULO 9: Comunicación en Tiempos de Crisis
**(Gestionando la Verdad y la Licencia Social)**

Cuando ocurre un incidente, la organización se enfrenta a dos incendios simultáneos. El primero es **técnico**: servidores cifrados, datos filtrados o servicios caídos. El segundo es **reputacional**: la pérdida de confianza, el escrutinio público y la presión regulatoria. 

El incendio técnico se apaga con arquitectura; el reputacional, con una comunicación estratégica basada en la **debida diligencia**. Bajo la **Ley 21.663**, la notificación no es una opción de relaciones públicas, sino un mandato legal. El silencio, en 2026, se interpreta como una confesión de falta de control.

### 1. El Vacío de Información y la Reducción del Ruido

El mayor error del **Mando Medio** es esperar a tener la "verdad total" para hablar. En el vacío de información, el **ruido** de los rumores y el pánico destruyen la credibilidad institucional.

* **La Regla del Vigilante:** Si usted no lidera la narrativa, el atacante o el rumor la liderarán por usted.
* **Transparencia de Proceso:** No siempre se puede informar "qué pasó" de inmediato, pero siempre se debe informar "qué estamos haciendo". La transparencia sobre el proceso es el primer escudo contra la negligencia. 
* **La Transparencia no es Especulación:** Informar lo que se sabe no autoriza la especulación técnica; comunicar hipótesis no verificadas erosiona la credibilidad y compromete gravemente la defensa regulatoria futura.

!!! danger "Advertencia de Gobernanza: La Trampa de la Especulación"
    Jamás utilice frases absolutas como *"No hubo robo de datos"* en las primeras 24 horas.
    
    Si el análisis forense posterior demuestra lo contrario, su primera declaración se convierte en prueba de **ocultamiento o falta de control** ante el regulador y la opinión pública. Es preferible decir *"Estamos investigando el alcance"* (verdad temporal) que afirmar una falsedad que destruya su credibilidad jurídica (mentira técnica).
    
---

### 2. El Cronómetro Legal (Tiempos de Silencio Máximo)

Bajo la Ley Marco de Ciberseguridad (Ley 21.663), el tiempo no es solo dinero; es responsabilidad administrativa. El Vigilante Estratégico debe conocer las "Ventanas de Notificación" antes de que el incidente ocurra. Exceder estos tiempos activa multas automáticas y presunción de negligencia.

| Tipo de Entidad / Incidente | Plazo Máximo (Alerta Temprana) | Destinatario Legal | Consecuencia del Silencio |
| :--- | :--- | :--- | :--- |
| **Operador de Importancia Vital (OIV)** | **3 Horas** | CSIRT Nacional (ANCI) | Infracción Gravísima (Multa tope 40k UTM). |
| **Servicios Esenciales (SE)** | **3 Horas** (Si hay impacto significativo) | CSIRT Nacional (ANCI) | Infracción Grave/Gravísima. |
| **Brecha de Datos Personales** | **72 Horas** (Estándar Legal) | Agencia de Protección de Datos | Sanción por desprotección de derechos. |
| **Ransomware con Extorsión** | **Inmediato** (Recomendado) | Ministerio Público / Policía | Pérdida de cadena de custodia penal. |

> **Nota Crítica:** El reloj de las 3 horas comienza a correr desde la **"Toma de Conocimiento"** del incidente, no desde su solución. Para la actualización técnica del reporte, los plazos se extienden (24h para OIV, 72h para SE), pero el *aviso inicial* debe ser inmediato.

---

### 3. La Cadena de Reporte: Hechos vs. Especulación

Para el **Ingeniero**, su labor es proveer la materia prima del relato: los hechos inalterables. Debe alimentar al Comité de Crisis usando el **Flash Report (Anexo D)**, evitando cualquier especulación que pueda contradecir la evidencia técnica del **SOAR** (Capítulo 8).

**Toda comunicación externa debe estar estrictamente alineada con la evidencia técnica preservada por el IRP; una declaración inconsistente con los registros forenses no es un error comunicacional, es un riesgo legal mayor.** 

Los datos críticos para el relato son:

* **Alcance:** Sistemas confirmados como comprometidos.
* **Integridad:** Estado de la exfiltración de datos según el inventario del Capítulo 6.
* **Cronología:** Tiempos de detección y contención para probar la diligencia técnica.

!!! info "Semántica Legal: Incidente vs. Ciberataque"
    Bajo la Ley Marco, la precisión del lenguaje es vital:
    
    * **Incidente de Ciberseguridad:** Cualquier evento que comprometa la disponibilidad, integridad o confidencialidad (puede ser un error humano o una falla de hardware).
    * **Ciberataque:** Un incidente donde existe dolo y una acción deliberada de un tercero.
    
    No llame "ataque" a una falla de disco; eso activa protocolos legales y de seguros diferentes e innecesarios.
    
---

### 4. Gestionando a los *Stakeholders* (Grupos de Interés)

El **Directorio** debe asegurar que el mensaje sea coherente para todos, pero adaptado a la necesidad de cada audiencia:

| Audiencia | Qué necesitan saber | Canal Recomendado |
| :--- | :--- | :--- |
| **El Directorio** | Impacto financiero (***ALE***), legal y continuidad. | Comité de Crisis / Acta de Directorio. |
| **La ANCI (Regulador)**| Detalles técnicos y cumplimiento de la Ley 21.663. | Portal de Notificación Oficial. |
| **Clientes** | Seguridad de sus datos y tiempo de restauración. | Comunicado Oficial / Redes Sociales. |
| **Empleados** | Protocolos de operación y narrativa interna. | Intranet / Comunicación Directa. |

---

### 5. Blueprint 9: La Matriz de Comunicación de Crisis

!!! example "Cronograma de Comunicación Estratégica"
    El **Mando Medio** coordina estos hitos para proteger la "Licencia Social" de la empresa ante un incidente visible:

    1.  **Hito 1 (T+60 min):** Notificación interna. Confirmación de activación de protocolos de **debida diligencia**.
    2.  **Hito 2 (T+4 horas):** Primera declaración oficial. Enfoque en la contención y protección de datos.
    3.  **Hito 3 (T+24 horas):** Reporte de progreso y transparencia sobre la fase de recuperación (**DRP - Anexo I**).
    4.  **Hito 4 (Post-Crisis):** El *Post-Mortem* público. Demostración de aprendizaje y endurecimiento de la arquitectura (Capítulo 12).

---

### 6. La Licencia Social y la Verdad Defendible

En la era de la IA, la velocidad del engaño es masiva. La **Licencia Social** no se recupera con parches técnicos, sino con la demostración de que la organización actuó con **debida diligencia** demostrable. El relato de crisis debe ser **jurídicamente defendible**: cada palabra dicha en público queda como un registro oficial que será contrastado con la evidencia forense preservada en el Capítulo 7. 

---

### Conclusión: La Confianza como Registro Público

Comunicar durante una crisis no es "maquillar" la realidad; es liderar la narrativa mediante la exposición de hechos controlados. En crisis, comunicar no es persuadir: es dejar un registro público coherente con la evidencia privada. Un incidente bien comunicado prueba que la organización es madura y posee el control del proceso, incluso cuando la tecnología ha fallado.

En el próximo capítulo, abordaremos la decisión más difícil para el **Vigilante Estratégico**: **El Gobierno de la Crisis y el Botón Rojo**. Veremos quién tiene la autoridad de apagar el negocio para salvar la empresa.

---

!!! abstract "Tesis del Capítulo"
    La confianza se construye en años y se pierde en minutos. Durante un incidente, la transparencia no es una debilidad; es la única forma de transformar un desastre técnico en un registro público de madurez institucional y **debida diligencia**.

---
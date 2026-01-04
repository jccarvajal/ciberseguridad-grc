# ANEXO G: Estructura y Roles del CSIRT
**(Computer Security Incident Response Team)**

### 1. Propósito y Alcance

El **CSIRT** es la fuerza de tarea encargada de coordinar, contener y erradicar incidentes de seguridad de la información. A diferencia del soporte técnico habitual, que opera por tickets y colas de espera, el CSIRT opera bajo una **estructura de mando militar** durante una crisis para asegurar decisiones rápidas y unívocas.

* **Objetivo Primario (Operativo):** Minimizar el daño, reducir el *Tiempo de Exposición* y recuperar la operatividad del negocio.
* **Objetivo Secundario (Legal):** Preservar la cadena de custodia de la evidencia para el análisis forense y la defensa jurídica ante la **ANCI**.

---

### 2. Niveles de Activación (Escalamiento)

El CSIRT no se reúne para problemas menores (como un PC lento). Se activa según la severidad del impacto potencial:

| Nivel | Descripción del Escenario | Activación Requerida |
| :--- | :--- | :--- |
| **Nivel 3 (Evento)** | Anomalía rutinaria contenida por defensas automáticas o analista L1. (Ej: Malware bloqueado en un endpoint). | **SOC (Operación Diaria).** No requiere activar CSIRT. |
| **Nivel 2 (Incidente)** | Amenaza activa que requiere coordinación humana o afecta un servicio no crítico. (Ej: Movimiento lateral detectado, caída de web secundaria). | **CSIRT Técnico.** (Incident Commander + Líder Técnico). |
| **Nivel 1 (Crisis)** | Amenaza existencial. Afectación de Core de Negocio, Exfiltración de Datos Personales masiva o Ransomware activo. | **CSIRT Completo + Comité de Crisis Ejecutivo.** (Activa "Botón Rojo"). |

---

### 3. Roles y Responsabilidades (El Organigrama de Guerra)

Para que el CSIRT funcione bajo presión, **deben asignarse personas específicas (Titular y Suplente)** a estos roles en tiempos de paz. Durante la crisis, los cargos jerárquicos normales se suspenden.

#### A. El Núcleo de Mando (*Command Core*)

* **Incident Commander (IC) / Comandante del Incidente**
    * **Perfil:** Usualmente el CISO o un Gerente de TI Senior con autoridad delegada.
    * **Misión:** "Director de Orquesta". No configura firewalls; toma las decisiones tácticas y autoriza cambios de emergencia.
    * **Autoridad:** Tiene poder delegado (ver **Anexo A**) para ordenar la desconexión de sistemas (*Kill Switch*) sin burocracia previa si la integridad de la red está en riesgo inminente.
    * **Regla de Oro:** El IC no toca teclados. El IC dirige.

* **Scribe / Escriba (Encargado de Bitácora)**
    * **Perfil:** Un analista designado, asistente ejecutivo o miembro de Riesgo Operacional.
    * **Misión:** Mantener el "Diario de Guerra". Registra cronológicamente cada hallazgo, cada decisión tomada, quién la tomó y a qué hora exacta.
    * **Valor GRC:** Su bitácora es la única defensa ante un sumario administrativo, auditoría de la ANCI o demanda legal posterior. **Si no está escrito en la bitácora, no sucedió.**

#### B. El Equipo Táctico (*Operations*)

* **Ops Lead / Líder Técnico**
    * **Perfil:** Jefe de Infraestructura, Líder de Ciberseguridad o Lead del SOC.
    * **Misión:** Traduce la orden estratégica del IC ("Aíslen la red de Finanzas") en comandos técnicos ejecutables por los ingenieros.
* **Investigador Forense**
    * **Misión:** Analiza la causa raíz y preserva la evidencia (Imagen de disco, volcados de memoria) antes de la restauración.
* **Comunicaciones / Enlace**
    * **Misión:** Gestiona los mensajes hacia los empleados (RRHH) y hacia el público/prensa (RRPP). Su objetivo es evitar filtraciones y controlar la narrativa.

#### C. Enlace Legal y Normativo

* **Asesor Legal (Fiscalía)**
    * **Misión:** Determina la obligatoriedad de notificar al Regulador o al CSIRT Nacional dentro de los plazos legales (ej: 3 horas para operadores vitales). Valida que las medidas de monitoreo de empleados sean legales.

---

### 4. Flujo de Autoridad (Matriz de Decisión)

En crisis, la democracia se suspende. Se aplica la siguiente matriz de decisión soberana:

| Tipo de Decisión | Autoridad Exclusiva | Consulta / Validación |
| :--- | :--- | :--- |
| **Aislar equipos infectados** | Analista / Líder Técnico | Ninguna (Acción inmediata pre-autorizada). |
| **Desconectar Servicios Críticos** (Fábrica/Web/ERP) | Incident Commander (IC) | Informar al CIO/CEO (Post-acción si es inminente). |
| **Notificar a Autoridades/Prensa** | Comité de Crisis (CEO + Legal) | Asesoría del CISO/IC (Inputs del Anexo D). |
| **Pagar Rescate (Ransomware)** | Directorio / Ministro / Dueño | Asesoría Legal y Técnica (Estrictamente prohibido sin esta validación). |

---

### 5. Infraestructura de la "Sala de Guerra" (*War Room*)

Si la red interna está comprometida (como en el caso de un ransomware avanzado), no se puede usar el correo corporativo, Teams o Slack internos para gestionar la crisis, ya que el atacante podría estar monitoreando las comunicaciones ("Eavesdropping").

**Canales Fuera de Banda (*Out-of-Band*):**

1.  **Mensajería Segura:** Grupo de **Signal** o **Wire** (pre-creado y verificado) en celulares personales, no corporativos.
2.  **Sala Física:** Una sala de reuniones designada ("Búnker") con pizarra blanca, desconectada de la red comprometida.
3.  **Almacenamiento Seguro:** Un repositorio externo (nube aislada o discos duros fríos) para guardar la bitácora y evidencias, lejos del alcance del cifrado del atacante.

---

### 6. Checklist de Activación (Hora 0)

Cuando el IC declara "Código Rojo" (Nivel 1), se ejecuta esta secuencia inmediata:

- [ ] **1. Convocatoria OOB:** Notificar al equipo por el canal de emergencia (Signal/Teléfono). No usar correo.
- [ ] **2. Asignación de Roles:** El IC verbaliza: *"Yo soy el Comandante. [Nombre] es el Escriba. [Nombre] es el Líder Técnico. Nadie más da órdenes."*
- [ ] **3. Silencio de Radio:** Ordenar la prohibición absoluta de usar canales corporativos comprometidos para discutir la defensa.
- [ ] **4. Evaluación de Daños (Triage):** Responder las 3 preguntas clave para el *Flash Report*:
    - *¿Qué sistemas críticos están afectados?*
    - *¿Hay evidencia de exfiltración de datos?*
    - *¿Tenemos backups íntegros y aislados?*
- [ ] **5. Apertura de Bitácora:** El Escriba anota la hora de inicio oficial del incidente para efectos legales.

---

> **Nota para la Implementación Pública**
> 
> Para organismos del Estado, es mandatorio designar formalmente al **Enlace con el CSIRT de Gobierno**. Esta persona es la única autorizada con clave única/token para subir el reporte de incidente al portal gubernamental, cumpliendo con la obligación de notificación de la Ley 21.663.

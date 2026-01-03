# ANEXO G: Estructura y Roles del CSIRT
**(Computer Security Incident Response Team)**

### 1. Propósito y Alcance
El CSIRT es la fuerza de tarea encargada de coordinar, contener y erradicar incidentes de seguridad de la información. A diferencia del soporte técnico habitual, el CSIRT opera bajo una **estructura de mando militar** durante una crisis para asegurar decisiones rápidas.

**Objetivo Primario:** Minimizar el daño y recuperar la operatividad.
**Objetivo Secundario:** Preservar la evidencia para análisis forense y legal.

### 2. Niveles de Activación (DEFCON)
El CSIRT no se reúne para problemas menores (como un PC lento). Se activa según la severidad:

| Nivel | Descripción | Activación |
| :--- | :--- | :--- |
| **Nivel 3 (Evento)** | Anomalía rutinaria contenida por defensas automáticas o analista L1. (Ej: Malware bloqueado en un PC). | **SOC (Operación Diaria).** No requiere activar CSIRT. |
| **Nivel 2 (Incidente)** | Amenaza activa que requiere coordinación humana o afecta un servicio no crítico. (Ej: Movimiento lateral detectado, caída de web secundaria). | **CSIRT Técnico.** (IC + Líder Técnico). |
| **Nivel 1 (Crisis)** | Amenaza existencial. Afectación de Core de Negocio, Datos Personales masivos o Ransomware. | **CSIRT Completo + Comité de Crisis Ejecutivo.** |

### 3. Roles y Responsabilidades (El Organigrama de Guerra)

Para que el CSIRT funcione, **deben asignarse personas específicas (Titular y Suplente)** a estos roles antes del incidente.

#### A. El Núcleo de Mando (Command Core)

* **Incident Commander (IC) / Comandante del Incidente**
    * **Quién es:** Usualmente el CISO o un Gerente de TI Senior.
    * **Misión:** "Director de Orquesta". Toma las decisiones tácticas.
    * **Autoridad:** Tiene **poder delegado** para ordenar la desconexión de sistemas (Kill Switch) sin burocracia previa si la integridad de la red está en riesgo inminente.
    * **Regla de Oro:** El IC no toca teclados. El IC dirige.

* **Scribe / Escriba (Encargado de Bitácora)**
    * **Quién es:** Un analista designado, asistente o miembro de riesgo.
    * **Misión:** Mantener el "Diario de Guerra". Registra cronológicamente cada hallazgo, cada decisión tomada, quién la tomó y a qué hora.
    * **Importancia:** Su bitácora es la única defensa ante un sumario administrativo o demanda legal posterior. Si no está escrito, no sucedió.

#### B. El Equipo Táctico (Operations)

* **Ops Lead / Líder Técnico**
    * **Quién es:** Jefe de Infraestructura o Líder del SOC.
    * **Misión:** Coordina a los ingenieros. Traduce la orden del IC ("Aíslen la red") en comandos técnicos.
* **Investigador Forense**
    * **Misión:** Analiza la causa raíz. Asegura la cadena de custodia de la evidencia.
* **Comunicaciones / Enlace**
    * **Misión:** Gestiona los mensajes hacia los empleados (RRHH) y hacia el público/prensa (RRPP). Evita filtraciones y rumores.

#### C. Enlace Legal y Normativo

* **Asesor Legal (Fiscalía)**
    * **Misión:** Determina la obligatoriedad de notificar al Regulador o al CSIRT Nacional (Gobierno). Valida la legalidad de las medidas de monitoreo.

### 4. Flujo de Autoridad (Quién decide qué)

En crisis, la democracia se suspende. Se aplica la siguiente matriz:

| Decisión | Autoridad Exclusiva | Consulta Requerida |
| :--- | :--- | :--- |
| **Aislar equipos infectados** | Analista / Líder Técnico | Ninguna (Acción inmediata). |
| **Desconectar Servicios Críticos** (Fábrica/Web/ERP) | Incident Commander (IC) | Informar al CIO/CEO (Post-acción si es inminente). |
| **Notificar a Autoridades/Prensa** | Comité de Crisis (CEO + Legal) | Asesoría del CISO/IC. |
| **Pagar Rescate (Ransomware)** | Directorio / Ministro / Dueño | Asesoría Legal y Técnica. |

### 5. Infraestructura de la "Sala de Guerra" (War Room)

Si la red interna está comprometida (como en el caso Akira), no se puede usar el correo corporativo ni Teams/Slack internos para gestionar la crisis, ya que el atacante podría estar leyendo.

**Canales Fuera de Banda (Out-of-Band):**
* **Mensajería Segura:** Grupo de Signal o Wire (pre-creado) en celulares personales.
* **Sala Física:** Una sala de reuniones designada con pizarra blanca y líneas telefónicas analógicas (si existen).
* **Almacenamiento Seguro:** Un repositorio externo (nube aislada o discos duros) para guardar la bitácora y evidencias, lejos del alcance del Ransomware.

### 6. Checklist de Activación (Hora 0)

Cuando el IC declara "Código Rojo" (Nivel 1):

1.  [ ] **Convocatoria:** Notificar al equipo por el canal de emergencia (Signal/Teléfono).
2.  [ ] **Asignación:** El IC dice en voz alta: *"Yo soy el Comandante. [Nombre] es el Escriba. [Nombre] es el Líder Técnico."*
3.  [ ] **Silencio de Radio:** Prohibir el uso de canales corporativos comprometidos para discutir la estrategia de defensa.
4.  [ ] **Evaluación de Daños:** Responder las 3 preguntas clave:
    * ¿Qué sistemas están afectados?
    * ¿Se están robando datos (exfiltración)?
    * ¿Tenemos backups seguros?
5.  [ ] **Apertura de Bitácora:** El Escriba anota la hora de inicio oficial del incidente.

---
**Nota para la Implementación:**
En el sector público/gobierno, es vital designar formalmente al **Enlace con el CSIRT Nacional**. Esta persona es la única autorizada para subir el reporte de incidente al portal gubernamental, cumpliendo con la normativa vigente.

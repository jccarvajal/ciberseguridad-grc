# ANEXO O: La Brújula Operativa de la Ley 21.663
**(Traducción Táctica de la Ley Marco de Ciberseguridad)**

### 1. Propósito: Traducir Riesgo Legal a Acción Técnica

Este documento no pretende ser un resumen jurídico exhaustivo, sino una **guía de aplicabilidad** diseñada para la gerencia y la operación técnica. Su función es traducir los mandatos de la Ley Marco de Ciberseguridad (Ley 21.663) a parámetros concretos de arquitectura, configuración y presupuesto.

El objetivo central es evitar que un incidente técnico, ya de por sí crítico, se transforme en una catástrofe legal por desconocimiento de las nuevas obligaciones de reporte y gestión.

---

### 2. El Filtro de Alcance: Clasificación de Entidades

La normativa no afecta a todas las organizaciones por igual. El nivel de exigencia, y la cuantía de las multas, depende estrictamente de la clasificación de la entidad según su impacto en la sociedad.

#### A. Servicios Esenciales (SE)
Esta categoría constituye la base de la regulación. Abarca sectores cuyo funcionamiento es vital para la continuidad del país.
* **Sectores Incluidos:** Energía, Agua, Telecomunicaciones, Salud, Transporte, Servicios Financieros, Logística, Seguridad Social, entre otros.
* **⚠️ El Riesgo de la Cadena de Suministro:** Es crucial entender que la ley alcanza a los proveedores de estos servicios. Si su empresa es un Datacenter, un MSP (*Managed Service Provider*) o un SaaS que presta servicios a un banco o a un hospital, la ley le aplica por extensión. Usted se convierte en un regulado indirecto.

#### B. Operadores de Importancia Vital (OIV)
Son una subcategoría crítica dentro de los Servicios Esenciales. No es una autodeclaración; una empresa se convierte en OIV solo mediante una resolución expresa de la **ANCI**.
* **Criterio de Designación:** Se asigna esta categoría cuando la interrupción de los servicios de la entidad podría paralizar el país, afectar la seguridad nacional, la salud pública o el abastecimiento básico.
* **Carga de Cumplimiento:** Los OIV tienen obligaciones adicionales, como realizar auditorías externas anuales, certificar sus sistemas de gestión (SGSI) y ejecutar simulacros de crisis obligatorios.

> **Árbol de Decisión Simplificado:**
> 1. Si no pertenece a un sector crítico, solo le aplica la Ley de Datos Personales.
> 2. Si pertenece a un sector crítico, es un **Servicio Esencial (SE)** y debe cumplir los mínimos de reporte.
> 3. Si recibe una resolución de la ANCI, es un **Operador de Importancia Vital (OIV)** y debe cumplir con el estándar máximo y las multas tope.

---

### 3. Diccionario de Traducción (Legal ↔ Técnico)

Para facilitar la comunicación entre el CISO y la Fiscalía corporativa, se presenta la siguiente tabla de equivalencias operativas:

| Concepto Legal (ANCI) | Traducción Operativa (TI/CISO) | Acción Técnica Requerida |
| :--- | :--- | :--- |
| **"Medida Correctiva Inmediata"** | Mitigación de Vulnerabilidad Crítica. | Implica la aplicación de parches, segmentación de red o aislamiento de activos (*Kill Switch*) en un plazo inferior a 24 horas. |
| **"Reporte de Ciberamenaza"** | Notificación de Vulnerabilidad (CVE). | Obligación de reportar *Zero-Days* o fallos críticos (CVSS > 9.0) detectados en infraestructura propia, antes de que sean explotados. |
| **"Simulacro Significativo"** | *Tabletop Exercise* Ejecutivo. | Realización de una simulación de crisis con participación real de la Gerencia General, documentada en un Acta de Lecciones Aprendidas (ver Anexo M). |
| **"Preservación de Evidencia"** | Cadena de Custodia Forense. | Prohibición de reiniciar o formatear servidores comprometidos sin antes realizar un volcado de memoria y logs para análisis forense (ver Anexo G). |

---

### 4. La Agencia Nacional de Ciberseguridad (ANCI)

La creación de la ANCI marca el fin de la era de las "recomendaciones". Este nuevo organismo posee facultades fiscalizadoras con efectos punitivos reales:

1.  **Facultad de Instrucción:** La Agencia puede ordenar medidas específicas, como la baja de un servicio inseguro. Desobedecer una instrucción directa se considera una infracción gravísima.
2.  **Facultad de Acceso:** En el contexto de una investigación, la Agencia puede requerir acceso a las redes, sistemas y registros de la entidad afectada, bajo los resguardos de confidencialidad correspondientes.
3.  **Facultad Sancionatoria:** Es el organismo encargado de cursar las multas en Unidades Tributarias Mensuales (UTM).

#### Régimen Sancionatorio (El Costo de la Negligencia)

| Gravedad | Conducta Típica | Tope Multa (OIV)* | Impacto Organizacional |
| :--- | :--- | :--- | :--- |
| **Leve** | Retrasos administrativos en reportes no críticos o falta de actualización documental. | **5.000 UTM** | Advertencia financiera significativa. |
| **Grave** | No contar con protocolos de seguridad, no realizar auditorías obligatorias o no reportar incidentes significativos. | **20.000 UTM** | Impacto directo a los resultados financieros (EBITDA) y evaluación de desempeño. |
| **Gravísima** | Ocultar vulnerabilidades críticas, entregar información falsa sobre incidentes o no acatar instrucciones de la ANCI. | **40.000 UTM** | **Riesgo Existencial.** Posible responsabilidad legal directa del Directorio. |

*\*Nota: Los montos son referenciales al tope legal para OIVs.*

---

### 5. Rutinas de Cumplimiento Obligatorio

La ciberseguridad deja de ser un estado pasivo para convertirse en un ciclo activo de cumplimiento legal. El calendario anual debe incluir:

1.  **SLA Legal de Reporte:**
    * **Alerta Temprana:** Máximo **3 horas** desde la confirmación del incidente.
    * **Actualización:** Máximo **72 horas** (se reduce a 24 horas para OIVs).
2.  **Auditoría Externa:** Obligatoria anualmente para los OIV.
3.  **Simulacros de Crisis:** Ejecución de al menos un ejercicio anual con alcance ejecutivo/directivo.
4.  **Revisión de Arquitectura:** Validación continua de controles de seguridad "Por Diseño" y "Por Defecto".

---

### 6. Escenarios de Aplicación Práctica

**Caso A: El Banco (OIV)**
Ante un ataque de Ransomware que paraliza la atención en sucursales, la entidad tiene la obligación estricta de reportar a la ANCI en un plazo de **3 horas**. Si la organización decide pagar un rescate sin informar a la autoridad o sin poder acreditar el "estado de necesidad", el Directorio se expone a multas gravísimas y a potenciales responsabilidades penales.

**Caso B: El Proveedor de Nube (MSP de un Servicio Esencial)**
Una empresa de tecnología detecta una vulnerabilidad crítica en sus propios servidores. Aunque la empresa no sea un OIV directo, debe reportar el hallazgo porque su fallo podría comprometer la operación de sus clientes regulados (ej: Clínicas o Bancos). Ocultar el fallo y permitir que afecte al cliente conlleva multas de la ANCI y responsabilidad civil contractual.

---

> **Nota Final para la Alta Dirección:**
> Bajo la Ley 21.663, ignorar una vulnerabilidad técnica conocida ya no es un "riesgo aceptable", sino una infracción administrativa fiscalizable. Administrativamente, gestionar mal un ciberincidente es ahora equivalente a la evasión tributaria: un acto ilegal, trazable y multable.

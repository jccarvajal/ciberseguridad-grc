# ANEXO O: La Brújula Operativa de la Ley 21.663
**(Traducción Táctica de la Ley Marco de Ciberseguridad)**

### 1. Propósito: Traducir Riesgo Legal a Acción Técnica

Este documento no pretende ser un resumen jurídico exhaustivo, sino una **guía de aplicabilidad** diseñada para la gerencia y la operación técnica. Su función es traducir los mandatos de la Ley Marco de Ciberseguridad (Ley 21.663) a parámetros concretos de arquitectura, configuración y presupuesto.

El objetivo central es evitar que un incidente técnico se transforme en una catástrofe legal.

!!! failure "Crítico: La Trampa del Reglamento Pendiente"
    Existe la creencia errónea de que "sin reglamento no hay ley". **Falso.**
    La Ley 21.663 está vigente. Si sufre un incidente hoy y no reporta, la ANCI puede sancionarlo igual invocando los principios generales de la ley. **No espere la "letra chica" para gestionar el riesgo grueso.**

---

### 2. El Filtro de Alcance: Clasificación de Entidades

La normativa no afecta a todas las organizaciones por igual. El nivel de exigencia (y la multa) depende estrictamente de su clasificación.

#### A. Servicios Esenciales (SE)
Constituyen la base de la regulación (Energía, Agua, Salud, Banca, Transporte, etc.).

!!! danger "Zona de Riesgo: El Efecto Dominó (Supply Chain)"
    Si usted presta servicios de TI (Hosting, Desarrollo, Soporte) a un Banco o Clínica, **usted es un regulado indirecto.**
    La ley obliga al Banco a fiscalizarlo a usted. Si usted falla, el Banco cae, y la ANCI lo perseguirá a usted por la vía contractual. **Revise sus SLAs hoy mismo.**

#### B. Operadores de Importancia Vital (OIV)
Subcategoría crítica designada por resolución de la **ANCI**. Tienen carga máxima: auditorías externas y simulacros obligatorios.

!!! question "Árbol de Decisión Simplificado"
    1.  ¿Pertenezco a un sector crítico? -> **NO** (Ley de Datos aplica, Ley Marco no).
    2.  ¿Pertenezco a un sector crítico? -> **SÍ** -> Eres **Servicio Esencial (SE)**.
    3.  ¿La ANCI me notificó resolución? -> **SÍ** -> Eres **OIV** (Obligaciones Máximas).

---

### 3. Diccionario de Traducción (Legal ↔ Técnico)

Para facilitar la comunicación entre el CISO y la Fiscalía corporativa:

| Concepto Legal (ANCI) | Traducción Operativa (TI/CISO) | Acción Técnica Requerida |
| :--- | :--- | :--- |
| **"Medida Correctiva Inmediata"** | Mitigación de Vulnerabilidad. | Parchear o aplicar *Kill Switch* en < 24 horas. |
| **"Reporte de Ciberamenaza"** | Notificación de Vulnerabilidad. | Reportar *Zero-Days* o fallos críticos (CVSS > 9.0) antes de ser explotados. |
| **"Simulacro Significativo"** | *Tabletop Exercise* Ejecutivo. | Simulación con Gerencia General y Acta de Lecciones (ver Anexo M). |
| **"Preservación de Evidencia"** | Cadena de Custodia Forense. | **Prohibido reiniciar servidores** sin volcado de memoria previo. |

---

### 4. La Agencia Nacional de Ciberseguridad (ANCI)

La ANCI no sugiere; instruye. Posee facultades de **Instrucción** (ordenar bajar servicios), **Acceso** (entrar a redes en investigaciones) y **Sanción**.

#### Régimen Sancionatorio (El Costo de la Negligencia)

| Gravedad | Conducta Típica | Tope Multa (OIV)* | Impacto |
| :--- | :--- | :--- | :--- |
| **Leve** | Retrasos en reportes burocráticos. | **5.000 UTM** | Advertencia financiera. |
| **Grave** | No auditar, no reportar incidentes. | **20.000 UTM** | Impacto a EBITDA. |
| **Gravísima** | Ocultar vulnerabilidades, mentir a la ANCI. | **40.000 UTM** | **Riesgo Existencial.** |

!!! quote "Doctrina de Responsabilidad Indelegable"
    El Directorio puede delegar la *tarea* de la ciberseguridad (al CISO o a un MSSP), pero **jamás puede delegar la responsabilidad legal.**
    Ante una investigación, el argumento *"yo no sabía de tecnología"* se considera una confesión de negligencia en el deber de supervisión (*Culpa in Vigilando*).

---

### 5. Rutinas de Cumplimiento Obligatorio

El calendario anual de supervivencia legal debe incluir:

* **SLA Legal de Reporte:** 3 horas (Alerta) / 72 horas (Informe).
* **Auditoría Externa:** Anual (OIV).
* **Simulacros:** Anual con alcance ejecutivo.
* **Revisión de Arquitectura:** Validación de controles "Por Diseño".

!!! warning "La Trampa del Lunes a las 9 AM: Compliance Formal vs. Realidad Operativa"
    Existe una peligrosa confusión entre salvarse de la multa por tiempo y salvarse de la multa por negligencia.

    * **El Escenario:** Un ataque inicia el sábado a las 03:00 AM. Nadie lo ve. Su equipo llega el lunes a las 09:00 AM y confirma el incidente.
    * **La Verdad Legal (El Cronómetro):** El plazo de reporte (3 horas) empieza legalmente el lunes a las 09:00 AM (*Toma de Conocimiento*, concepto jurídico que no reemplaza el deber de vigilancia continua en entidades críticas). Si reporta antes del mediodía, evita la sanción por retraso.
    * **La Trampa Regulatoria (El Deber de Seguridad):** Aunque cumpla el plazo de reporte, la ANCI puede sancionarlo por **"Falta de Medidas Técnicas Apropiadas"**. La lógica del regulador será: *"Si usted es un Operador Vital, su obligación es tener monitoreo continuo. No lo multo por reportar tarde, lo multo por haber estado ciego durante 54 horas"*.
    * **La Verdad Operativa:** Independiente de la multa, el atacante tuvo 54 horas libres (*Dwell Time*) para destruir sus respaldos.

    **Lección:** Cumplir con el trámite administrativo no lo exime de la responsabilidad técnica de vigilancia. El monitoreo 24/7 no es para complacer al regulador, es para que su negocio amanezca vivo el lunes.

---

### 6. Escenarios de Aplicación Práctica

!!! example "Caso A: El Banco (OIV)"

    * **Situación:** Ransomware paraliza sucursales. 
    * **Obligación:** Reportar a ANCI en **3 horas**. 
    * **Riesgo:** Si paga el rescate sin informar o sin acreditar "estado de necesidad", el Directorio arriesga multas gravísimas y responsabilidad penal.

!!! example "Caso B: El Proveedor de Nube (MSP)"

    * **Situación:** Detecta vulnerabilidad crítica propia. 
    * **Obligación:** Aunque no sea OIV, debe reportar porque su fallo afecta a un Servicio Esencial. 
    * **Riesgo:** Ocultar el fallo conlleva multas de la ANCI y demandas civiles del cliente.

> **Nota Final:** Bajo la Ley 21.663, gestionar mal un ciberincidente es administrativamente equivalente a la evasión tributaria: ilegal, trazable y multable.

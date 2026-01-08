# ANEXO B: Tablero de Métricas de Resiliencia (KPIs y KRIs)
**(Cómo medir el éxito más allá de "no nos hackearon")**

### 1. Filosofía de Medición: Señal vs. Ruido
El error más común en los reportes de ciberseguridad es presentar **"Métricas de Vanidad"** que inflan el ego técnico pero no informan sobre el riesgo de negocio.

* ❌ **Métrica de Vanidad (Ruido):** *"El Firewall bloqueó 5 millones de ataques este mes."*
    * *Por qué está mal:* Es irrelevante. Es como contar cuántas gotas de lluvia caen sobre el techo; lo único que importa es si hay goteras.
* ✅ **Métrica de Eficacia (Señal):** *"El tiempo promedio para parchar una vulnerabilidad crítica bajó de 30 días a 48 horas."*
    * *Por qué está bien:* Mide la velocidad de reacción y la reducción de la ventana de exposición.

Para este tablero, dividimos las métricas en dos categorías:

1.  **KPI (Key Performance Indicator):** ¿Qué tan bien lo hicimos ayer? (Mirada al pasado).
2.  **KRI (Key Risk Indicator):** ¿Qué tan probable es que tengamos problemas mañana? (Mirada al futuro).

---

### 2. Nivel 1: Tablero Ejecutivo (Para el Directorio/Ministro)
*Frecuencia de Revisión: Trimestral / Semestral*

Este tablero responde a la única pregunta que le importa a la Alta Dirección: **¿Qué tan expuestos estamos financieramente y legalmente?**

| Indicador (KRI) | Definición GRC | Meta (Target) | Estado Actual (Ejemplo) |
| :--- | :--- | :--- | :--- |
| **Nivel de Madurez NIST** | Puntuación (1-5) basada en la autoevaluación de controles y la función GOVERN. | **> 3.5** | 🔴 **1.2 (Bajo)** |
| **Riesgo Residual (*ALE*)** | Pérdida anualizada esperada en dinero ($ALE = SLE \times ARO$). | **< $50k USD** | 🔴 **$500k USD** |
| **Cobertura de Activos Críticos** | % de Sistemas Tier 0/1 protegidos por Backups Inmutables y MFA. | **100%** | 🟡 **60%** |
| **Tasa de Éxito en Simulacros** | % de pruebas de restauración (**DRP**) que funcionaron en el tiempo prometido (*RTO*). | **100%** | 🟢 **100%** |
| **Costo de Incidentes Reales** | Dinero real perdido por paradas no planificadas o multas (**Ley 21.663**). | **$0** | 🔴 **$100k** (Caso Ransomware) |

---

### 3. Nivel 2: Tablero Operativo (Para el CISO/Gerente TI)
*Frecuencia de Revisión: Mensual / Semanal*

Este tablero responde a la pregunta técnica: **¿Qué tan rápido somos?** (En ciberseguridad, Velocidad = Supervivencia).

#### A. Métricas de Velocidad (Detección y Respuesta)
Estas métricas validan la inversión en **SOAR** (Capítulo 8).

* **MTTD (*Mean Time To Detect*):** Tiempo promedio desde que el atacante entra hasta que el SOC lo ve.
    * *Meta:* **< 1 Hora.**
    * *Contexto:* Si el MTTD es > 24 horas, el ransomware ya se desplegó y cifró los respaldos.
* **MTTR (*Mean Time To Respond*):** Tiempo promedio desde que se detecta hasta que se contiene (aislamiento del host).
    * *Meta:* **< 30 Minutos.**
    * *Contexto:* Aquí es donde la automatización brilla.

#### B. Métricas de Higiene (Prevención)
Estas métricas validan la gestión de vulnerabilidades (**Anexo F**) e identidad (**Capítulo 5**).

* **Latencia de Parchado (*Patch Latency*):** Tiempo promedio entre que se publica un parche crítico (ej: KEV) y se instala en producción.
    * *Meta:* **< 48 Horas para Críticos.**
    * *Peligro:* Si su promedio es 30 días, su ventana de exposición es de 28 días.
* **Cobertura de EDR/Antivirus:** % de endpoints con el agente de seguridad instalado, actualizado y reportando.
    * *Meta:* **> 98%.** (Los puntos ciegos son la entrada preferida de los atacantes).
* **Usuarios con Privilegios de Admin:** % de usuarios totales que tienen permisos de Administrador Local en sus estaciones.
    * *Meta:* **< 5%** (Estrictamente limitado a personal de TI autorizado).

#### C. Métricas de Factor Humano
* **Tasa de Clic en Phishing (*Click Rate*):** % de empleados que caen en las pruebas simuladas de phishing.
    * *Meta:* **< 4%.**
    * *Acción:* Si un departamento supera el umbral, se activa re-entrenamiento obligatorio presencial.

---

### 4. Visualización Recomendada (El Semáforo)

**Regla del Vigilante:** No entregue una hoja de cálculo al Directorio. Entregue un **Semáforo**. Los ejecutivos toman decisiones binarias (Aprobar/Rechazar) basadas en señales claras de estado.

> **EJEMPLO: INFORME DE ESTADO CIBERSEGURIDAD - Q1 2026**
>
> * 🟢 **Gobernanza:** Políticas aprobadas, Comité de Crisis sesionando mensualmente.
> * 🟢 **Defensa Perimetral:** Firewalls actualizados y segmentación core activa.
> * 🟡 **Gestión de Identidad:** MFA implementado al 70%. Riesgo medio en acceso de contratistas.
> * 🔴 **Resiliencia de Datos (CRÍTICO):** Pruebas de restauración fallaron en el servidor de Finanzas el 12/03. **Riesgo inminente de pérdida de datos ante incidente.**
> * 🟢 **Endpoint:** Cobertura de EDR al 99%.

**Interpretación del Semáforo:**

* 🟢 **Verde:** Riesgo dentro del apetito aceptado. Mantener estrategia.
* 🟡 **Amarillo:** Riesgo latente o desviación menor. Requiere atención o reasignación de recursos.
* 🔴 **Rojo:** Riesgo inminente, materializado o fuera de cumplimiento legal. **Requiere decisión inmediata del Directorio (Inversión o Aceptación formal).**

---

### 5. Advertencia Doctrinal sobre "El Cero"

> **ADVERTENCIA:** Nunca establezca como meta **"0 Incidentes"** o **"0 Ataques"**.

Es una meta imposible en un entorno de Autonomía Adversaria. Si la logra, es por pura suerte o porque sus sistemas de detección no están viendo la realidad.

**Use metas de resiliencia:**

* *"0 Incidentes con impacto material financiero"* (Antifragilidad).
* *"100% de Incidentes críticos contenidos en < 1 hora"* (Capacidad de Respuesta).

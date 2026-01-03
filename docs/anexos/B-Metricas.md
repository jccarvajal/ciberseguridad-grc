# ANEXO B: Tablero de Métricas de Resiliencia (KPIs y KRIs)
**(Cómo medir el éxito más allá de "no nos hackearon")**

### 1. Filosofía de Medición
Evite las **"Métricas de Vanidad"**.
* *Malo:* "El Firewall bloqueó 5 millones de ataques este mes." (Esto es ruido; es como contar cuántas gotas de lluvia caen en el techo).
* *Bueno:* "El tiempo promedio para parchar una vulnerabilidad crítica bajó de 30 días a 48 horas." (Esto es eficacia).

Dividimos el tablero en Indicadores de Desempeño (KPI) e Indicadores de Riesgo (KRI).

---

### 2. Nivel 1: Tablero Ejecutivo (Para el Directorio/Ministro)
*Frecuencia: Trimestral / Semestral*

Este tablero responde a la pregunta: **¿Qué tan expuestos estamos financieramente?**

| Métrica | Definición | Meta (Target) | Estado Actual (Ejemplo) |
| :--- | :--- | :--- | :--- |
| **Nivel de Madurez NIST** | Puntuación (1-5) basada en la autoevaluación de controles (Anexo F). | **3.5** | 🔴 1.2 (Bajo) |
| **Riesgo Financiero Residual (ALE)** | Pérdida anualizada esperada en dinero (ver Capítulo 2). | **< $50k USD** | 🔴 $500k USD |
| **Cobertura de Activos Críticos** | % de Sistemas Críticos (Tier 0 y 1) cubiertos por Backups Inmutables y MFA. | **100%** | 🟡 60% |
| **Tasa de Éxito en Simulacros** | % de pruebas de restauración (DRP) que funcionaron en el tiempo prometido. | **100%** | 🟢 100% |
| **Costo de Incidentes Reales** | Dinero perdido por paradas no planificadas o multas en el último periodo. | **$0** | 🔴 $100k (Caso Akira) |

---

### 3. Nivel 2: Tablero Operativo (Para el CISO/Gerente TI)
*Frecuencia: Mensual / Semanal*

Este tablero responde a la pregunta: **¿Qué tan rápido somos?** (Velocidad = Supervivencia).

#### A. Métricas de Velocidad (Detección y Respuesta)
* **MTTD (Mean Time To Detect):** Tiempo promedio desde que el atacante entra hasta que el SOC lo ve.
    * *Meta:* < 1 Hora.
    * *Realidad (Akira):* Si es > 24 horas, el ransomware ya se desplegó.
* **MTTR (Mean Time To Respond):** Tiempo promedio desde que se detecta hasta que se contiene (aislamiento).
    * *Meta:* < 30 Minutos.
    * *Nota:* Aquí es donde la automatización (SOAR) brilla.

#### B. Métricas de Higiene (Prevención)
* **Latencia de Parchado (Patch Latency):** Tiempo promedio entre que sale un parche crítico (ej: vulnerabilidad en VPN) y se instala en producción.
    * *Meta:* < 48 Horas para Críticos.
    * *Peligro:* Si su promedio es 30 días, es vulnerable por 28 días.
* **Cobertura de EDR/Antivirus:** % de endpoints con el agente de seguridad instalado, actualizado y reportando.
    * *Meta:* > 98%. (Los huecos ciegos son por donde entran).
* **Usuarios con Privilegios de Admin:** % de usuarios totales que tienen permisos de Administrador Local en sus PCs.
    * *Meta:* < 5% (Solo personal de TI autorizado).

#### C. Métricas de Factor Humano
* **Tasa de Clic en Phishing (Click Rate):** % de empleados que caen en las pruebas simuladas de phishing.
    * *Meta:* < 4%.
    * *Acción:* Si un departamento tiene tasa alta, requiere re-entrenamiento presencial.

---

### 4. Visualización Recomendada (El Semáforo)

No entregue Excel. Entregue un **Semáforo**.
Los ejecutivos toman decisiones rápidas basadas en colores.

> **INFORME DE CIBERSEGURIDAD - Q1 2026**
>
> * **Gobernanza:** 🟢 (Políticas aprobadas, Comité activo).
> * **Defensa Perimetral:** 🟢 (Firewalls actualizados).
> * **Gestión de Identidad:** 🟡 (MFA implementado al 70%, faltan contratistas).
> * **Resiliencia de Datos:** 🔴 **CRÍTICO** (Pruebas de restauración fallaron en servidor de Finanzas. Riesgo de pérdida de datos).
> * **Endpoint:** 🟢 (EDR al 99%).

**Interpretación:**
* **Verde:** Riesgo controlado. Mantener inversión.
* **Amarillo:** Riesgo latente. Se requiere atención o presupuesto moderado.
* **Rojo:** Riesgo inminente o materializado. Requiere acción inmediata del Directorio.

### 5. Advertencia sobre "El Cero"
Nunca ponga como meta "0 Incidentes" o "0 Ataques".
Es una meta imposible. Si la logra, es suerte o mentira.
Mejor use: "0 Incidentes con impacto material" o "100% de Incidentes contenidos en < 1 hora".

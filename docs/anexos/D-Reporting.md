# ANEXO D: Guía de Reporting Ejecutivo
**(Traducción de Riesgo Técnico a Valor de Negocio)**

### Introducción: El Puente de Comunicación

El mayor error de un equipo de ciberseguridad es creer que su trabajo termina cuando identifica un fallo técnico. En realidad, el trabajo estratégico comienza ahí: en la capacidad de **traducir** ese hallazgo para que el Directorio o la Alta Gerencia comprendan por qué deben asignar recursos o autorizar una ventana de mantenimiento crítica.

Esta guía proporciona al Ingeniero y al Mando Medio el marco de comunicación necesario para que sus reportes no sean descartados como "ruido técnico", sino valorados como **"inteligencia de negocio"**.

---

### 1. La Pirámide de la Información

Para que la comunicación fluya y no sature, cada nivel de la organización debe recibir la información procesada según sus necesidades de decisión:

* **Nivel Operativo (Ingenieros):** Reportan *Vulnerabilidades y Parches* (CVE, Logs, Puertos, IPs).
    * *Objetivo:* Remediación técnica.
* **Nivel Táctico (Mandos Medios):** Reportan *Riesgos y Procesos* (Sistemas afectados, SLAs, Cumplimiento de Políticas).
    * *Objetivo:* Gestión de recursos y priorización.
* **Nivel Estratégico (Directorio/C-Level):** Reportan *Exposición Financiera y Continuidad* (Impacto en ingresos, Multas legales, Reputación, ALE).
    * *Objetivo:* **Gobernanza y Supervivencia.**

---

### 2. La Regla de Oro: El "Impacto" sobre la "Técnica"

Un reporte ejecutivo nunca debe centrarse en *cómo* funciona el ataque (la curiosidad técnica), sino en *qué* le pasa a la empresa si el ataque tiene éxito (la consecuencia de negocio).

| Enfoque Incorrecto (Técnico) | Enfoque Correcto (De Negocio) |
| :--- | :--- |
| ❌ "Tenemos un *Buffer Overflow* en el servicio Apache debido a la falta de parches de seguridad." | ✅ "Existe una vulnerabilidad crítica en el **Portal de Clientes** que permitiría a un tercero detener la facturación indefinidamente o exfiltrar la base de pagos." |
| ❌ "El firewall bloqueó conexiones al puerto 445 desde una IP de China." | ✅ "Nuestros sistemas de defensa perimetral contuvieron un intento de acceso no autorizado dirigido a la propiedad intelectual, sin impacto operativo." |

---

### 3. Estructura del "Executive Flash Report" (Plantilla)

Cada vez que se deba informar un riesgo inminente o un incidente en curso (Minuto 60 del IRP), utilice esta plantilla estricta.

> **ASUNTO: [FLASH REPORT] Riesgo Crítico en [Nombre del Activo] - Acción Requerida**
>
> **1. Hallazgo Estratégico:**
> Se ha identificado una vulnerabilidad activa que afecta la integridad del [Nombre del Proceso de Negocio, ej: Proceso de Cierre Mensual].
>
> **2. Activo de Negocio Afectado:**
> Servidor Central de Finanzas (Soporta el 80% de la facturación).
>
> **3. Gravedad Contextualizada:**
> **CRÍTICA.** No es un riesgo teórico; existe evidencia de explotación activa en la industria (KEV). Si se materializa, la interrupción del servicio sería total.
>
> **4. Costo de la Inacción (Impacto):**
> De no actuar, estimamos un riesgo de multa por incumplimiento de la Ley 21.663 y una pérdida operativa diaria de $XX,XXX USD.
>
> **5. Recomendación de Acción (Decisión Solicitada):**
> Se solicita autorización para una **ventana de mantenimiento de emergencia** hoy a las 20:00 hrs (duración: 2 horas) para aplicar el parche de seguridad.
>
> *Atte. [Nombre], CISO.*

---

### 4. El Semáforo de Decisión (Dashboard Ejecutivo)

Para los reportes de estado mensuales (Cadencia de Gobierno), el Mando Medio debe utilizar un sistema de semáforo que fuerce la toma de decisiones, evitando la ambigüedad.

| Estado | Significado GRC | Acción Requerida del Directorio |
| :--- | :--- | :--- |
| 🔴 **Crítico** | El riesgo actual supera el apetito de riesgo financiero o legal. | **Inversión Inmediata** o detención de procesos inseguros. |
| 🟡 **Advertencia** | Vulnerabilidades detectadas pero en proceso de remediación dentro de SLA. | **Monitoreo.** Validar que no se conviertan en deuda técnica. |
| 🟢 **Saludable** | Postura de seguridad alineada con el plan anual y la normativa. | **Mantenimiento.** Continuar con el presupuesto asignado. |

---

### 5. Anti-Patrones de Comunicación (Lo que se debe evitar)

* **La Parálisis por Análisis:** Entregar reportes de 50 páginas que nadie lee. Un reporte ejecutivo **no debe exceder una página (o dos diapositivas)**.
* **El "Cries Wolf" (El pastor mentiroso):** Reportar todo como "urgente" o "rojo". Si todo es una crisis, entonces nada lo es, y el Directorio dejará de escuchar.
* **El Silencio Técnico:** No informar de un riesgo "porque ya lo estamos arreglando". La Alta Gerencia odia las sorpresas; prefiere saber que hay un problema identificado y controlado, a enterarse por la prensa o una demanda.
* **La Jerga ("Technobabble"):** Usar términos como "Hash", "Salt", "Handshake" sin explicar su relevancia. Si no puede explicarlo en términos de dinero o ley, no lo ponga en el reporte.

---

### Conclusión para el "Vigilante Estratégico"

El éxito de un líder de Ciberseguridad no se mide solo por su capacidad de cerrar puertos, sino por su capacidad de **persuadir** a la organización para que sea más segura. Hablar el lenguaje del negocio es el firewall más potente que puedes construir.

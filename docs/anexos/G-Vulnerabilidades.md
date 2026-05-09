# ANEXO G: Gestión Técnica de Vulnerabilidades
**(Taxonomía, Análisis y Ciclos de Parcheo - SLAs)**

### Introducción: Del Escaneo a la Gestión

La gestión de vulnerabilidades no consiste en comprar un software que genere reportes de 500 páginas que nadie lee. Consiste en un proceso de **ciclo cerrado** que identifica, prioriza y remedia las debilidades antes de que la **Autonomía Adversaria** las explote.

Para el Ingeniero, este anexo es su hoja de ruta operativa. Para el Mando Medio, es la herramienta de control para asegurar que la superficie de ataque de la organización se mantenga dentro de los límites de riesgo aceptables definidos en el **Capítulo 2**.

---

### 1. El Triángulo de la Priorización: CVE, CVSS y EPSS

Para decidir qué arreglar primero en un mar de miles de fallos, utilizamos tres métricas combinadas (Ver **Anexo E** para definiciones):

* **CVE (La Identidad):** Nos dice qué fallo es.
* **CVSS (La Gravedad):** Nos dice qué tan malo es técnicamente el daño potencial (Escala 0-10).
* **EPSS (La Probabilidad):** El *Exploit Prediction Scoring System* es una métrica probabilística (0-100%) que nos dice qué tan probable es que esa vulnerabilidad sea atacada en los próximos 30 días.

> **Regla Estratégica:** Un fallo con CVSS 9.0 pero EPSS bajo (<1%) puede esperar más que un CVSS 7.0 con EPSS alto (>80%, explotación inminente). **Priorizamos riesgo real sobre gravedad teórica.**

---

### 2. Diferencias Críticas: Escaneo, Análisis y Pentest

Es común que el Directorio confunda estas tres actividades. El Arquitecto debe diferenciarlas para asignar presupuesto y expectativas correctamente:

| Actividad | Método | Frecuencia | Resultado GRC |
| :--- | :--- | :--- | :--- |
| **Escaneo de Vulnerabilidades** | Automatizado (Robot) | Semanal / Continuo | Lista técnica masiva de parches faltantes y malas configuraciones. |
| **Análisis de Vulnerabilidades** | Humano / Experto | Mensual | Contextualización del escaneo: *"¿Este fallo realmente nos afecta con nuestra configuración actual?"* |
| **Pruebas de Penetración (Pentest)** | Humano (Ofensivo) | Semestral / Anual | Demostración de impacto (evidencia) de cómo un atacante podría encadenar fallos para robar datos o detener el negocio. |

---

### 3. El Ciclo de Vida de la Remediación

Todo hallazgo técnico debe pasar por estas cuatro etapas sin excepción para garantizar la trazabilidad:

1.  **Descubrimiento (*Discovery*):** Identificación del fallo mediante escaneo recurrente o inteligencia externa (KEV).
2.  **Análisis y Priorización:** Clasificación según el impacto de negocio (**BIA**) y la severidad técnica.
3.  **Remediación / Mitigación:**
    * *Remediación:* Aplicar el parche definitivo (Solución Raíz).
    * *Mitigación:* Aplicar un "control compensatorio" (ej. regla de bloqueo en el WAF) si el parche no puede aplicarse de inmediato por razones operativas.
4.  **Verificación:** Un re-escaneo técnico que confirme que la vulnerabilidad ya no es detectable. **Sin verificación, el ticket no se cierra.**

---

### 4. Niveles de Servicio (SLAs) de Parcheo

La organización debe comprometerse a tiempos de respuesta basados en la criticidad. Estos son los tiempos máximos tolerables para una arquitectura resiliente:

| Severidad | Criterio Técnico | SLA de Remediación | Acción en caso de Incumplimiento |
| :--- | :--- | :--- | :--- |
| 🔴 **Crítica** | CVSS 9.0-10.0 o **Listado en KEV** | **< 48 Horas** | Comité de Crisis + Ventana de Emergencia. |
| 🟠 **Alta** | CVSS 7.0 - 8.9 | **< 7 Días** | Escalado al CISO si hay retraso. |
| 🟡 **Media** | CVSS 4.0 - 6.9 | **< 30 Días** | Próxima ventana de mantenimiento mensual. |
| 🟢 **Baja** | CVSS 0.0 - 3.9 | **Best Effort** | Según disponibilidad de recursos. |

---

### 5. Excepciones y Riesgo Aceptado

No siempre es posible parchear (ej. sistemas legados, equipos médicos industriales o riesgo de caída del servicio). En esos casos, no se ignora la alerta; se gestiona la excepción.

**Requisitos para una Excepción:**

1.  Debe documentarse formalmente.
2.  Debe ser firmada por el **Dueño del Activo (Negocio)**, no solo por TI (Ver **Anexo A: Accountability**).
3.  Debe tener fecha de caducidad (máximo 6 meses) y controles compensatorios obligatorios.

#### Plantilla: Formulario de Excepción de Seguridad

> **SOLICITUD DE EXCEPCIÓN DE VULNERABILIDAD**
>
> **ID Vulnerabilidad:** [CVE-XXXX-XXXX]
> **Activo Afectado:** [Nombre del Servidor/Sistema]
> **Razón de la No-Remediación:**
> [ ] Incompatibilidad técnica con el software legado.
> [ ] Riesgo de caída operativa mayor al riesgo de seguridad.
> [ ] Proveedor ya no existe (Obsolescencia).
>
> **Control Compensatorio Aplicado:**
> [Ej: El servidor ha sido aislado en una VLAN sin salida a Internet y con acceso restringido a una sola IP de administración].
>
> **Fecha de Revisión/Vencimiento:** [DD/MM/AAAA]
>
> __________________________
> **Firma Dueño del Activo (Aceptación del Riesgo Residual)**

---

### Conclusión para el Mando Medio

El éxito de este anexo no se mide por cuántas vulnerabilidades se encuentran (eso es fácil), sino por la **reducción del MTTR (*Mean Time To Remediate*)**.
Un equipo que parcha fallos críticos en 24 horas es infinitamente más valioso y resiliente que uno que tiene la mejor herramienta de escaneo del mercado pero tarda 60 días en actuar.

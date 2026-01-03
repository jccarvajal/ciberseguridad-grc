# Anexo F: Gestión Técnica de Vulnerabilidades
**(Taxonomía, Análisis y Ciclos de Parcheo (SLAs))**

### Introducción: Del Escaneo a la Gestión

La gestión de vulnerabilidades no consiste en comprar un software que genere reportes de 500 páginas. Consiste en un proceso de **ciclo cerrado** que identifica, prioriza y remedia las debilidades antes de que un atacante las explote. 

Para el Ingeniero, este anexo es su hoja de ruta operativa. Para el Mando Medio, es la herramienta de control para asegurar que la superficie de ataque de la organización se mantenga dentro de los límites de riesgo aceptables.

---

### 1. El Triángulo de la Priorización: CVE, CVSS y EPSS

Para decidir qué arreglar primero en un mar de miles de fallos, utilizamos tres métricas:

* **CVE (La Identidad):** Nos dice qué fallo es.
* **CVSS (La Gravedad):** Nos dice qué tan malo es técnicamente (Escala 0-10).
* **EPSS (La Probabilidad):** El *Exploit Prediction Scoring System* es una métrica probabilística que nos dice qué tan probable es que esa vulnerabilidad sea atacada en los próximos 30 días.
* **Valor Estratégico:** Un fallo con CVSS 9.0 pero EPSS bajo puede esperar más que un CVSS 7.0 con EPSS alto (explotación inminente).

### 2. Diferencias Críticas: Escaneo, Análisis y Pentest

Es común confundir estas tres actividades. El Arquitecto debe diferenciarlas para asignar presupuesto correctamente:

| Actividad | Método | Frecuencia | Resultado |
| :--- | :--- | :--- | :--- |
| **Escaneo de Vulnerabilidades** | Automatizado | Semanal / Continuo | Lista técnica de parches faltantes y malas configuraciones. |
| **Análisis de Vulnerabilidades** | Humano / Experto | Mensual | Contextualización del escaneo: "¿Este fallo realmente nos afecta en esta red?" |
| **Pruebas de Penetración (Pentest)** | Humano (Ofensivo) | Anual / Semestral | Demostración de cómo un atacante podría encadenar fallos para robar datos. |

### 3. El Ciclo de Vida de la Remediación

Todo hallazgo técnico debe pasar por estas cuatro etapas sin excepción:

1.  **Descubrimiento (Discovery):** Identificación del fallo mediante escaneo o reporte externo.
2.  **Análisis y Priorización:** Clasificación según impacto de negocio (BIA) y severidad (CVSS).
3.  **Remediación / Mitigación:** * *Remediación:* Aplicar el parche definitivo.
    * *Mitigación:* Aplicar un "control compensatorio" (ej. regla en el Firewall) si el parche no puede aplicarse de inmediato.
4.  **Verificación:** Un re-escaneo técnico que confirme que la vulnerabilidad ya no es detectable.

### 4. Niveles de Servicio (SLAs) de Parcheo

La organización debe comprometerse a tiempos de respuesta basados en la criticidad. Estos son los tiempos recomendados para una arquitectura resiliente:

* **Crítica (CVSS 9.0 - 10.0):** Remediación en **< 48 horas**. Requiere comité de crisis si afecta sistemas core.
* **Alta (CVSS 7.0 - 8.9):** Remediación en **< 7 días**.
* **Media (CVSS 4.0 - 6.9):** Remediación en el próximo ciclo de mantenimiento mensual (**< 30 días**).
* **Baja (CVSS 0.1 - 3.9):** Remediación según disponibilidad de recursos o riesgo aceptado.

### 5. Excepciones y Riesgo Aceptado

No siempre es posible parchear (ej. sistemas legados o equipos médicos). En esos casos:
* Se debe documentar una **Excepción de Seguridad**.
* Debe ser firmada por el Dueño del Activo (Negocio), no solo por TI.
* Debe incluir una fecha de revisión y un plan de salida (decomiso del sistema o aislamiento total de la red).

---

### Conclusión para el Mando Medio
El éxito de este anexo no se mide por cuántas vulnerabilidades se encuentran, sino por la **reducción del "MTTR" (Mean Time To Remediate)**. Un equipo que parches fallos críticos en 24 horas es infinitamente más valioso que uno que solo compra la mejor herramienta de escaneo del mercado.

# Anexo D: Guía de Reporting Ejecutivo
**(Traducción de Riesgo Técnico a Valor de Negocio)**

### Introducción: El Puente de Comunicación

El mayor error de un equipo de ciberseguridad es creer que su trabajo termina cuando identifica un fallo técnico. En realidad, el trabajo estratégico comienza ahí: en la capacidad de **traducir** ese hallazgo para que el Directorio o la Alta Gerencia comprendan por qué deben asignar recursos o autorizar una ventana de mantenimiento crítica.

Esta guía proporciona al Ingeniero y al Mando Medio el marco de comunicación necesario para que sus reportes no sean vistos como "ruido técnico", sino como "inteligencia de negocio".

---

### 1. La Pirámide de la Información

Para que la comunicación fluya, cada nivel de la organización debe recibir la información procesada según sus necesidades de decisión:

* **Nivel Operativo (Ingenieros):** Reportan *Vulnerabilidades y Parches* (CVE, Logs, Puertos).
* **Nivel Táctico (Mandos Medios):** Reportan *Riesgos y Procesos* (Sistemas afectados, SLAs, Cumplimiento).
* **Nivel Estratégico (Directorio/C-Level):** Reportan *Exposición Financiera y Continuidad* (Impacto en ingresos, Multas legales, Reputación).



### 2. La Regla de Oro: El "Impacto" sobre la "Técnica"

Un reporte ejecutivo nunca debe centrarse en *cómo* funciona el ataque, sino en *qué* le pasa a la empresa si el ataque tiene éxito.

* **Mal:** "Tenemos un *Buffer Overflow* en el servicio Apache debido a la falta de parches de seguridad."
* **Bien:** "Existe una vulnerabilidad crítica en el portal de clientes que permitiría a un tercero detener la facturación por tiempo indefinido o robar la base de datos de pagos."

### 3. Estructura del "Executive Flash Report" (Plantilla)

Cada vez que se deba informar un riesgo o incidente de alto impacto, se debe seguir este formato de cinco puntos:

1.  **Hallazgo Estratégico:** (Nombre claro del problema, sin siglas innecesarias).
2.  **Activo de Negocio Afectado:** (Ej: "Sistema de Remuneraciones", "Portal de Trámites Ciudadanos").
3.  **Gravedad Contextualizada:** No usar solo el número CVSS; explicar la urgencia (Ej: "Riesgo de interrupción total del servicio").
4.  **Recomendación de Acción:** (Ej: "Se requiere una ventana de mantenimiento extraordinaria de 2 horas este jueves").
5.  **Costo de la Inacción:** (Ej: "Si no actuamos, el riesgo de filtración de datos sensibles es inminente bajo la Ley 21.663").

### 4. El Semáforo de Decisión (Dashboard Ejecutivo)

Para reportes de estado mensuales, el Mando Medio debe utilizar un sistema de semáforo que fuerce la toma de decisiones:

* 🔴 **Crítico (Acción Inmediata):** Riesgos que superan el apetito de riesgo financiero. Requieren presupuesto o detención de procesos.
* 🟡 **Advertencia (Gestión en Curso):** Vulnerabilidades en proceso de remediación dentro de los plazos legales/técnicos.
* 🟢 **Saludable (Mantenimiento):** Postura de seguridad alineada con el plan anual.



### 5. Anti-Patrones de Comunicación (Lo que se debe evitar)

* **La Parálisis por Análisis:** Entregar reportes de 100 páginas que nadie lee. Un reporte ejecutivo no debe exceder una página (o dos slides).
* **El "Cries Wolf" (Asustar por asustar):** Reportar todo como "urgente". Si todo es una crisis, nada lo es.
* **El Silencio Técnico:** No informar de un riesgo "porque ya lo estamos arreglando". La gerencia odia las sorpresas; prefiere saber que hay un problema y que el equipo tiene el control.

---

### Conclusión para el "Vigilante Estratégico"
El éxito de un Ingeniero de Ciberseguridad no se mide solo por su capacidad de cerrar puertos, sino por su capacidad de **persuadir** a la organización para que sea más segura. Hablar el lenguaje del negocio es el firewall más potente que puedes construir.

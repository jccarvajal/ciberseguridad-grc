# ANEXO A: Modelo de Accountability (Matriz RACI)
**(Definición de Roles y Propiedad del Riesgo)**

### 1. El Problema de la Ambigüedad

La mayoría de las brechas de seguridad no ocurren por falta de tecnología, sino en las "zonas grises" de responsabilidad operativa. Cuando ocurre un incidente, las frases más comunes suelen ser:

* *"Pensé que TI cerraba los accesos cuando alguien renunciaba."* (TI argumenta que RRHH nunca envió el ticket de baja).
* *"Pensé que Seguridad aprobaba la salida a producción."* (Seguridad argumenta que Desarrollo nunca les informó del lanzamiento).

Para eliminar estas zonas grises y asegurar la **Debida Diligencia**, utilizamos la **Matriz RACI**.

---

### 2. Definiciones RACI

Para cada proceso crítico de ciberseguridad, debe haber un nombre y apellido asignado a cada una de estas letras. La regla de oro es: **Puede haber muchos responsables de ejecutar (R), pero solo un responsable final (A).**

* **[R] Responsible (El Ejecutor):** Quien realiza el trabajo técnico ("Las manos en el teclado").
* **[A] Accountable (El Dueño):** Quien tiene la autoridad final, aprueba el trabajo y responde ante el Directorio si algo sale mal ("La cabeza que rueda"). **Solo puede haber una "A" por proceso.**
* **[C] Consulted (El Asesor):** Experto cuya opinión se busca *antes* de decidir o actuar. En nuestro modelo, este suele ser el rol del **CISO** y del **DPO**.
* **[I] Informed (El Notificado):** A quien se le avisa *después* de que la acción o decisión ha sido tomada.

---

### 3. Matriz RACI de Ciberseguridad

Esta tabla define la gobernanza operativa estándar para una organización regulada, integrando el rol del **DPO (Data Protection Officer)**.

| Proceso Crítico | [R] Ejecutor (Hacer) | [A] Accountable (Responder) | [C] Consultado (Asesorar) | [I] Informado (Notificar) |
| :--- | :--- | :--- | :--- | :--- |
| **Alta de Usuarios (Joiners)** | Mesa de Ayuda (TI) | **Gerente de RRHH** | CISO (Roles) / DPO (Privacidad) | Jefe Directo |
| **Baja de Usuarios (Leavers)** | Mesa de Ayuda (TI) | **Gerente de RRHH** *(Crítico: RRHH gatilla)* | CISO | Seguridad Física / DPO |
| **Parchado de Servidores** | Infraestructura (TI) | **CIO / Gerente TI** | CISO (Define Prioridad) | Dueños de Servicio |
| **Declaración de Incidente** | CISO / SOC | **Comité de Crisis (CEO)** | Legal y DPO (Impacto Datos) | Comunicaciones |
| **Evaluación de Impacto (DPIA)**| Dueño de Proyecto | **Gerente del Negocio** | DPO (Dictamen Vinculante) | CISO / Legal |
| **Aprobación de Excepciones** | CISO (Evalúa Riesgo) | **Gerente del Negocio Solicitante** | CIO / DPO (Si hay datos PII) | Riesgo Operacional |
| **Gestión de Backups** | Operaciones TI | **CIO / Gerente TI** | CISO (Verifica Integridad) | Auditores |
| **Pago de Ransomware** | Director Financiero | **Directorio / Ministro** | CISO, Legal y DPO | Accionistas |

!!! info "Concepto Clave: DPIA (Privacidad desde el Diseño)"
    La **Evaluación de Impacto en Protección de Datos (DPIA)** no es un trámite burocrático; es la evidencia tangible de **Privacidad desde el Diseño**.
    
    Se trata de una auditoría de riesgo obligatoria que debe realizarse *antes* de iniciar cualquier proyecto que involucre datos sensibles, IA o perfilamiento masivo. Su función en la Matriz RACI es crítica: formaliza que el **Gerente de Negocio (Accountable)** ha entendido y aceptado los riesgos de privacidad identificados por el **DPO**, asegurando que la búsqueda de rentabilidad no comprometa la legalidad del tratamiento de datos. 
    
    **Sin una DPIA firmada, el proyecto nace con "Deuda Legal" desde el día cero.**

---

### 4. El Concepto de "Risk Ownership" (Dueño del Riesgo)

Es vital para la salud mental de la organización entender que **el CISO no es el dueño del riesgo del negocio**. El CISO es el asesor de confianza, no el dueño del activo.

* **El Error:** Si el Gerente de Marketing quiere lanzar un sitio web sin medidas de seguridad porque "hay prisa", el CISO tradicional intenta prohibirlo (convirtiéndose en el "Dr. No").
* **La Solución GRC:** El CISO emite una **"Carta de Aceptación de Riesgo"**.

**El Flujo de Soberanía:**

1.  **CISO:** *"Lanzar esta web en estas condiciones implica un riesgo ALTO de fuga de datos según nuestra política."*
2.  **Marketing:** *"Entiendo el riesgo, pero la oportunidad comercial lo justifica. Asumo la responsabilidad."*
3.  **Firma:** El Gerente de Marketing firma la Carta de Aceptación (convirtiéndose en el **Accountable**).
4.  **Resultado:** Si la web es comprometida, la responsabilidad recae en Marketing, no en el CISO.

---

### 5. Carta Tipo de Aceptación de Riesgo (Plantilla)

Esta plantilla debe estar formalizada en el procedimiento de gestión de riesgos.

> **MEMORÁNDUM DE ACEPTACIÓN DE RIESGO**
>
> **De:** [Nombre del CISO]
> **Para:** [Nombre Gerente de Negocio / Dueño del Activo]
> **Fecha:** [DD/MM/AAAA]
> **Asunto:** Excepción de Seguridad para [Nombre del Proyecto/Sistema]
>
> Por medio de la presente, el área de Ciberseguridad informa que se ha identificado el siguiente riesgo crítico en el proyecto de la referencia, el cual excede el apetito de riesgo corporativo aprobado:
>
> * **Riesgo Identificado:** [Ej: Ausencia de MFA en acceso remoto para proveedores].
> * **Impacto Potencial (SLE):** [Ej: Acceso no autorizado a datos personales, multas estimadas de hasta X UTM según Ley 21.663].
> * **Recomendación del CISO:** No implementar hasta corregir / Implementar controles compensatorios.
>
> El Gerente de Negocio abajo firmante reconoce haber sido informado de este riesgo y, por razones operativas/comerciales, decide **ACEPTARLO**, asumiendo la responsabilidad plena (Accountability) por las posibles consecuencias financieras, legales y reputacionales derivadas de esta decisión ante el Directorio.
>
> __________________________
> **Firma Gerente de Negocio (Accountable)**

---

### 6. Delegación de Autoridad para Crisis (El "Botón Rojo")

Para evitar la parálisis por análisis durante un ciberataque masivo (ver **Capítulo 10**), el Directorio debe firmar preventivamente esta delegación de autoridad en tiempos de paz:

> **DELEGACIÓN DE AUTORIDAD DE EMERGENCIA**
>
> *"Se autoriza al CISO y al Incident Commander a desconectar cualquier sistema, servicio, servidor o enlace de comunicaciones de la organización, sin necesidad de consulta previa, si determinan técnicamente que existe un riesgo inminente de propagación de malware destructivo o exfiltración masiva de datos. Esta autoridad es válida 24/7 y prima sobre la continuidad operativa inmediata en favor de la supervivencia institucional."*

---

**Nota de Implementación:**
Imprima la Matriz RACI en tamaño grande y péguela en la oficina de TI y Operaciones. Cuando ocurra un fallo y alguien pregunte *"¿De quién es culpa que no se haya parchado el servidor?"*, no discuta; señale la columna **[A] Accountable**.

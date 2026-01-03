# ANEXO A: Modelo de Accountability (Matriz RACI)
**(Definición de Roles y Propiedad del Riesgo)**

### 1. El Problema de la Ambigüedad
La mayoría de las brechas de seguridad ocurren en las "zonas grises" de responsabilidad.
* *"Pensé que TI cerraba los accesos cuando alguien renunciaba."* (Pero TI dice que RRHH nunca avisó).
* *"Pensé que Seguridad aprobaba la salida a producción."* (Pero Seguridad dice que nadie les mostró el código).

Para eliminar estas zonas grises, utilizamos la **Matriz RACI**.

### 2. Definiciones RACI
Para cada proceso crítico, debe haber un nombre y apellido en cada una de estas letras:

* **[R] Responsible (El Ejecutor):** Quien hace el trabajo técnico ("Las manos en el teclado").
* **[A] Accountable (El Dueño):** Quien tiene la autoridad final y la responsabilidad si algo sale mal. **Solo puede haber una "A" por proceso.** ("La cabeza que rueda").
* **[C] Consulted (El Asesor):** Experto cuya opinión se busca *antes* de decidir. (Usualmente el CISO).
* **[I] Informed (El Notificado):** A quien se le avisa *después* de la acción.

### 3. Matriz RACI de Ciberseguridad

| Proceso Crítico | [R] Ejecutor | [A] Dueño/Accountable | [C] Consultado | [I] Informado |
| :--- | :--- | :--- | :--- | :--- |
| **Alta de Usuarios (Joiners)** | Mesa de Ayuda (TI) | Gerente de RRHH | CISO (Roles) | Jefe Directo |
| **Baja de Usuarios (Leavers)** | Mesa de Ayuda (TI) | **Gerente de RRHH** *(Crítico: RRHH gatilla)* | CISO | Seguridad Física |
| **Parchado de Servidores** | Infraestructura (TI) | CIO / Gerente TI | CISO (Prioridad) | Dueños de Servicio |
| **Declaración de Incidente** | CISO / SOC | Comité de Crisis (CEO) | Legal | Comunicaciones |
| **Aprobación de Excepciones** *(Ej: Usar software no estándar)* | CISO (Evalúa) | **Gerente del Negocio Solicitante** | CIO | Riesgo Operacional |
| **Gestión de Backups** | Operaciones TI | CIO / Gerente TI | CISO (Verifica) | Auditores |
| **Pago de Ransomware** | Director Financiero | **Directorio / Ministro** | CISO y Legal | Accionistas |

### 4. El Concepto de "Risk Ownership" (Dueño del Riesgo)

Es vital entender que **el CISO no es el dueño del riesgo del negocio**.

* Si el Gerente de Marketing quiere lanzar una web sin medidas de seguridad porque "hay prisa", el CISO no debe prohibirlo (Dr. No).
* El CISO debe emitir una **"Carta de Aceptación de Riesgo"**.

**El flujo es:**
1.  **CISO:** *"Lanzar esta web así tiene un riesgo ALTO de fuga de datos."*
2.  **Marketing:** *"Asumo el riesgo porque necesitamos vender ya."*
3.  **Firma:** El Gerente de Marketing firma la Carta de Aceptación (convirtiéndose en el **Accountable**).
4.  **Resultado:** Si hackean la web, la responsabilidad es de Marketing, no del CISO.

### 5. Carta Tipo de Aceptación de Riesgo (Plantilla)

> **MEMORÁNDUM DE ACEPTACIÓN DE RIESGO**
>
> **De:** [Nombre CISO]
> **Para:** [Nombre Gerente de Negocio / Dueño del Activo]
> **Fecha:** [DD/MM/AAAA]
>
> **Asunto:** Excepción de Seguridad para [Nombre del Proyecto/Sistema]
>
> Por medio de la presente, el área de Ciberseguridad informa que se ha identificado el siguiente riesgo crítico en el proyecto de la referencia:
>
> * **Riesgo:** [Describir vulnerabilidad, ej: Falta de MFA en acceso remoto].
> * **Impacto Potencial:** [Describir impacto, ej: Acceso no autorizado a datos personales, multas de hasta X UTM].
> * **Recomendación CISO:** No implementar hasta corregir / Implementar controles compensatorios.
>
> El Gerente de Negocio abajo firmante reconoce haber sido informado de este riesgo y, por razones operativas/comerciales, decide **ACEPTARLO**, asumiendo la responsabilidad por las posibles consecuencias financieras, legales y reputacionales derivadas de esta decisión.
>
> __________________________
> **Firma Gerente de Negocio (Accountable)**

### 6. Delegación de Autoridad para Crisis (El "Botón Rojo")

Para evitar la parálisis durante un ataque (Capítulo 10), el Directorio firma preventivamente esta delegación:

> *"Se autoriza al CISO y al Incident Commander a desconectar cualquier sistema, servicio o enlace de comunicaciones de la organización, sin consulta previa, si determinan técnicamente que existe un riesgo inminente de propagación de malware destructivo o exfiltración masiva de datos. Esta autoridad es válida 24/7."*

---
**Nota de Implementación:**
Imprima la Matriz RACI en tamaño grande y péguela en la oficina de TI. Cuando alguien pregunte *"¿De quién es culpa que no se haya parchado el servidor?"*, señale la columna **[A] Accountable**.

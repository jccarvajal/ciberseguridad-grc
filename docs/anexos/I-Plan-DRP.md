# ANEXO I: Plan de Recuperación de Desastres (DRP)
**(Plantilla de Restauración Tecnológica)**

### 1. Alcance y Priorización (Tiers)

En una crisis total, intentar "levantar todo a la vez" es garantía de fracaso. La recuperación debe seguir un orden estricto de dependencias e importancia de negocio, previamente definido en el **BIA (Anexo J)**.

| Nivel (Tier) | Definición GRC | RTO Objetivo | Activos Típicos |
| :--- | :--- | :--- | :--- |
| **Tier 0 (Vital)** | **Identidad y Seguridad.** Sin esto, no existe red ni confianza. | **< 2 Horas** | Directorio Activo (AD/DNS), VPN, Firewalls, **Consola de Backups**, MFA. |
| **Tier 1 (Crítico)** | **Facturación y Cumplimiento.** Si faltan, perdemos dinero o violamos la Ley. | **< 4-8 Horas** | ERP (SAP/Oracle), Base de Datos Principal, Web Transaccional, Correo. |
| **Tier 2 (Importante)** | **Operación Interna.** Procesos de soporte. | **< 24 Horas** | Servidor de Archivos (File Server), CRM Secundario, Intranet, Telefonía VoIP. |
| **Tier 3 (Soporte)** | **No Urgente.** Datos fríos o entornos no productivos. | **> 48 Horas** | Entornos de Desarrollo/QA, Archivos Históricos, BI/Reporting. |

---

### 2. Estrategia de Protección de Datos (Regla 3-2-1-1-0)

Para garantizar la recuperabilidad ante ataques destructivos modernos (tipo Akira o LockBit), la arquitectura de respaldo debe cumplir estrictamente este estándar:

1.  **3 Copias de los datos:** (Producción + Copia A + Copia B).
2.  **2 Medios diferentes:** (Ej: Disco Rápido y Nube/Cinta).
3.  **1 Copia fuera del sitio (*Off-site*):** Para sobrevivir a incendios o terremotos en el Data Center principal.
4.  **1 Copia INMUTABLE u OFFLINE (*Air-gapped*):**
    * *Definición:* Esta copia tiene un "candado de tiempo" (Object Lock). No puede ser borrada ni modificada antes de la fecha de expiración, **ni siquiera con credenciales de Administrador de Dominio**. Es la única defensa real contra el ransomware que borra *Shadow Copies*.
5.  **0 Errores (Verificación Automatizada):**
    * *Definición GRC:* No basta con que el trabajo de backup diga "Éxito". Se debe realizar una prueba automática de arranque (*SureBackup/Sandbox*) para confirmar que los datos dentro del archivo son legibles y la aplicación levanta.
    * *Axioma:* **Un backup no verificado es solo un archivo grande y costoso que ocupa espacio.**

---

### 3. Procedimiento de Activación del DRP

El DRP se activa formalmente cuando el **Incident Commander (IC)** declara que la infraestructura actual es **irrecuperable**, **no confiable** o ha sido **comprometida totalmente** por un adversario.

#### FASE 1: Preparación de la "Zona Limpia" (*Clean Room*)
**¡ADVERTENCIA CRÍTICA!** Nunca restaure servidores limpios sobre la red infectada; se reinfectarán en segundos.

1.  [ ] **Aislamiento:** Crear una VLAN de Recuperación aislada, sin rutas a la red antigua ni a Internet abierto.
2.  **Saneamiento del Hipervisor:** Si el ataque comprometió la virtualización (ej: VMware ESXi), se debe reinstalar desde cero (*Bare Metal Restore*) antes de montar cualquier backup.

#### FASE 2: Restauración de Servicios Base (Tier 0)
1.  [ ] **Identidad (AD):** Restaurar el Controlador de Dominio (DC) en la Zona Limpia.
2.  [ ] **Limpieza de Identidad:** Antes de conectar nada más, resetear la cuenta **KRBTGT** (evita ataques *Golden Ticket*) y forzar cambio de contraseña de Administradores.
3.  [ ] **Seguridad:** Levantar consola de Antivirus/EDR. Asegurar que los agentes se instalen y actualicen en cada máquina que se levante a continuación.

#### FASE 3: Restauración de Negocio (Tier 1)
1.  [ ] **Base de Datos:** Restaurar DB Server. Ejecutar comandos de integridad (ej: `DBCC CHECKDB` en SQL) para asegurar que el backup no está corrupto.
2.  [ ] **Aplicación:** Restaurar App Server y reconectar a la DB.
3.  [ ] **Escaneo Previo:** Escanear el servidor restaurado con antivirus actualizado *antes* de abrir el puerto de servicio. (Evitar que el backup traiga el virus "dormido").

#### FASE 4: Reconexión Gradual
1.  [ ] **Apertura Controlada:** Habilitar rutas de red solo para puertos específicos (ej: solo 443, bloquear SMB/RDP).
2.  [ ] **Retorno de Usuarios:** Forzar cambio de contraseñas a todos los usuarios finales antes de permitir el primer login en el sistema restaurado.

---

### 4. Inventario de Recuperación (Matriz Operativa)

*Este cuadro debe ser llenado con datos reales y actualizado trimestralmente.*

| Sistema | IP Original | Dependencias Críticas | Ubicación del Backup | Responsable Técnico |
| :--- | :--- | :--- | :--- | :--- |
| **Controlador Dominio** | 10.0.0.5 | Ninguna | Repositorio Inmutable A | Juan Pérez |
| **ERP (Base de Datos)** | 10.0.0.20 | Dominio, Storage SAN | Repositorio B (Cinta) | María Gómez |
| **Web Transaccional** | 10.0.0.50 | SQL ERP, WAF | Azure Blob (Inmutable) | Pedro D. |
| **File Server** | 10.0.0.100 | Dominio | NAS Local | Juan Pérez |

---

### 5. Plan de Pruebas (Drills)

Un DRP no probado es una alucinación peligrosa. La **ANCI** exigirá evidencia de estas pruebas.

* **Prueba de Escritorio (Trimestral):** Reunión del equipo para revisar este documento, verificar números de teléfono y vigencia de contratos de soporte.
* **Prueba Técnica Granular (Semestral):** Restaurar aleatoriamente un servidor crítico (Tier 1) en un entorno de *Sandbox* aislado y verificar que la base de datos es legible.
* **Simulacro Total (Anual):** Simulación de caída completa en fin de semana. Medir tiempos reales de restauración vs. RTO prometido en el BIA.

---

> **ADVERTENCIA DE SEGURIDAD (CUENTAS "BREAK GLASS")**
>
> **Problema:** Si el Ransomware cifra el Directorio Activo, sus credenciales de "Admin de Dominio" no funcionarán. No podrá entrar a la consola de Backups para iniciar la restauración.
>
> **Solución:**
> 
> 1. La consola de Backup **NO debe estar unida al dominio**.
> 2. Debe existir una cuenta de **Administrador Local** con contraseña compleja (25+ caracteres), guardada en un sobre sellado en la caja fuerte física o en una bóveda de contraseñas *offline*.
> 3. **Documentación Física:** Imprima este anexo. Si el servidor de archivos está cifrado, no podrá leer este PDF para saber cómo recuperarlo.

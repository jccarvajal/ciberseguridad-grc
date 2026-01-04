# ANEXO H: Plan de Respuesta a Incidentes (IRP)
**(Plantilla Maestra de Ejecución Táctica)**

### 1. Criterios de Activación

Este plan no es opcional. Se activa automáticamente cuando el **Incident Commander (IC)** confirma un incidente de **Nivel 1 (Crisis)** o **Nivel 2 (Incidente Mayor)**, según la definición del **Anexo G**.

**Objetivo del Plan:** Guiar al CSIRT desde el caos inicial hasta la recuperación del servicio, priorizando la **preservación de evidencia** (para la defensa legal) y la **minimización del impacto financiero** (para la supervivencia del negocio).

---

### 2. El Ciclo de Vida del Incidente (Fases Maestras NIST)

**ADVERTENCIA DE MANDO:** Siga este flujo secuencial. **NO SALTE PASOS.** Un error común por pánico es intentar "Recuperar" (Fase 4) sin haber terminado la "Erradicación" (Fase 3), lo que provoca una reinfección inmediata.

#### FASE 1: Detección y Análisis (Triage)
* **Validar:** ¿Es un falso positivo? Confirmar cruzando al menos dos fuentes (Logs de Firewall + Alerta de EDR + Reporte de Usuario).
* **Clasificar:** Determinar el alcance (¿Un PC aislado o el Controlador de Dominio?) y la severidad.
* **Declarar:** El IC activa formalmente el **CSIRT** y convoca a la "Sala de Guerra" (Física o Virtual Segura).

#### FASE 2: Contención (El Torniquete)
*Prioridad: Detener la hemorragia operativa.*
* **Aislamiento de Red:** Desconectar VLANs afectadas en el Core Switch. Bloquear tráfico de salida (*Egress*) en el Firewall perimetral.
* **Suspensión de Cuentas:** Deshabilitar usuarios comprometidos y cuentas de administración global (*Domain Admins*).
* **Preservación Forense:**
    * 🛑 **NO APAGAR LOS EQUIPOS INFECTADOS:** Apagar borra la memoria RAM, donde reside la evidencia clave del ataque y, a veces, las llaves de descifrado.
    * ✅ **ACCIÓN:** Desconectar el cable de red o hibernar la máquina virtual.

#### FASE 3: Erradicación (La Cirugía)
*Prioridad: Eliminar la amenaza de raíz.*
* **Limpieza:** Eliminar binarios de malware, artefactos y persistencias.
* **Cierre de Puertas Traseras (*Backdoors*):** Buscar cuentas creadas recientemente, tareas programadas ocultas o reglas de firewall no autorizadas.
* **Parchado de Causa Raíz:** Cerrar la vulnerabilidad que permitió la entrada inicial (Ej: Aplicar parche a la VPN o cerrar puerto RDP).
* **Rotación de Credenciales:** Resetear **todas** las contraseñas de administración y servicio (Asumir que Kerberos/Active Directory fue comprometido).

#### FASE 4: Recuperación (La Rehabilitación)
*Prioridad: Restaurar el servicio de forma segura y gradual.*
* **Restauración:** Levantar servicios críticos desde backups limpios y verificados (Tier 0 y 1).
* **Cuarentena de Red:** Los servidores restaurados no deben tener salida a Internet inmediata.
* **Monitoreo Intensivo:** Vigilar el tráfico de red por 24/48 horas para asegurar que el atacante no regrese (*Persistence check*).
* **Fin del Incidente:** El IC declara formalmente el retorno a la normalidad y disuelve la Sala de Guerra.

---

### 3. PLAYBOOK ESPECÍFICO: RANSOMWARE
*(Guía de Ejecución Rápida para casos tipo Akira/LockBit)*

**A. Acción Inmediata (Minutos 0-15)**
1.  [ ] **Aislar:** Desconectar físicamente (cable) o lógicamente (vSwitch) los equipos infectados.
2.  [ ] **Proteger Backups:** Verificar que los repositorios de respaldo estén desconectados de la red (*Air-Gapped*) o en modo inmutable inmediatamente.
3.  [ ] **Identificar Variante:** Tomar una muestra de la nota de rescate y un archivo cifrado. Subir a *ID Ransomware* (desde una red externa segura) para identificar la familia.

**B. Decisión de Negocio (Horas 1-4)**
1.  [ ] **Evaluar Viabilidad:** ¿Podemos restaurar desde backups con un RTO aceptable?
    * *SÍ:* Proceder a limpiar y restaurar. **NO PAGAR.**
    * *NO (Backups cifrados/inexistentes):* Escalar al Comité de Crisis/Directorio de inmediato.
    * **ADVERTENCIA:** Solo el Directorio puede decidir sobre negociación/pago (Ver **Capítulo 10**). Pagar sin autorización legal puede constituir financiamiento del terrorismo.

**C. Investigación Forense (Paralelo)**
1.  [ ] **Vector de Entrada:** ¿Cómo entraron? (VPN sin MFA, Phishing, RDP expuesto). **Si no se encuentra y cierra la entrada, volverán a cifrar mañana.**
2.  [ ] **Exfiltración (Doble Extorsión):** Revisar logs de firewall para ver si salieron grandes volúmenes de datos antes del cifrado. Esto activa obligaciones legales de notificación (**Ley 21.663**).

---

### 4. PLAYBOOK ESPECÍFICO: COMPROMISO DE CORREO (BEC)
*(Guía para Phishing y Robo de Credenciales)*

1.  [ ] **Kill Session:** Resetear la contraseña del usuario afectado y forzar el cierre de todas las sesiones activas (*Revoke Tokens*).
2.  [ ] **MFA:** Forzar el re-registro de los dispositivos de Multi-Factor Authentication (el atacante pudo haber registrado su propio celular).
3.  [ ] **Auditoría de Persistencia:** Revisar reglas de correo (*Inbox Rules*). Los atacantes suelen crear reglas de "Reenvío automático" o "Eliminar y mover a RSS" para ocultar sus huellas.
4.  [ ] **Búsqueda Lateral:** Auditar si la cuenta comprometida envió correos de phishing internos a otros empleados o externos a clientes/proveedores.

---

### 5. Lista de Contactos Críticos (Llenar y Mantener Impreso)

*Este cuadro debe estar lleno y actualizado **antes** de la crisis.*

| Rol | Entidad / Nombre | Teléfono 24/7 (Emergencia) | Correo Alternativo |
| :--- | :--- | :--- | :--- |
| **Soporte Firewall/Red** | (Ej: Proveedor ISP) | | |
| **Soporte Cloud/SaaS** | (Ej: Partner Microsoft) | | |
| **Forense Externo** | (Ej: Empresa Ciberseguridad) | | |
| **Asesor Legal** | (Fiscalía / Externo) | | |
| **Seguro Ciber** | (Aseguradora / Broker) | | |
| **CSIRT Nacional** | (Enlace de Gobierno) | | |

---

### 6. Protocolo de Evidencia (Cadena de Custodia)

Para asegurar la defensa jurídica ante la **ANCI** y posibles litigios:

1.  **Regla de Oro:** Nunca trabajar forense sobre la "Evidencia Original". Hacer una copia imagen (*bit-a-bit*) de los discos afectados y trabajar sobre la copia.
2.  **Hashing:** Calcular el *Hash* (MD5/SHA256) de la evidencia original al momento de la adquisición para probar que no fue alterada.
3.  **Registro:** El **Escriba** (Ver Anexo G) debe registrar en la bitácora: quién tuvo acceso al disco, cuándo, por qué y dónde se almacenó.
4.  **Custodia:** Almacenar el disco original en una caja fuerte o armario bajo llave con acceso restringido.

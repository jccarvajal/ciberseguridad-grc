# ANEXO H: Plan de Respuesta a Incidentes (IRP)
**(Plantilla Maestra de Ejecución)**

### 1. Criterios de Activación
Este plan se activa cuando el **Incident Commander (IC)** confirma un incidente de Nivel 1 (Crisis) o Nivel 2 (Incidente Mayor), según se define en el Anexo A.

**Objetivo del Plan:** Guiar al equipo desde el caos inicial hasta la recuperación del servicio, asegurando la evidencia y minimizando el impacto financiero/operacional.

---

### 2. El Ciclo de Vida del Incidente (Fases Maestras)

Siga este flujo secuencial. **NO salte pasos.** Un error común es intentar "Recuperar" (Paso 4) sin haber terminado la "Erradicación" (Paso 3), lo que provoca una reinfección inmediata.

#### FASE 1: Detección y Análisis
* **Validar:** ¿Es un falso positivo? Confirmar con múltiples fuentes (Logs, reportes de usuario, alertas EDR).
* **Clasificar:** Determinar alcance (¿Un PC? ¿Toda la granja de servidores?) y severidad.
* **Declarar:** El IC activa el CSIRT y la Sala de Guerra.

#### FASE 2: Contención (El Torniquete)
*Prioridad: Detener la propagación.*
* **Aislamiento de Red:** Desconectar VLANs afectadas. Bloquear tráfico en Firewall perimetral.
* **Suspensión de Cuentas:** Deshabilitar usuarios comprometidos y cuentas de administración global.
* **Preservación:** **NO APAGAR** los equipos infectados a menos que sea la única forma de frenar el daño (apagar borra la memoria RAM, vital para el forense). Preferir "hibernar" o desconectar el cable de red.

#### FASE 3: Erradicación (La Cirugía)
*Prioridad: Eliminar la amenaza de raíz.*
* **Limpieza:** Eliminar malware, artefactos y puertas traseras (*backdoors*).
* **Parchado:** Cerrar la vulnerabilidad que permitió la entrada (ej: parchar la VPN, cerrar puerto RDP).
* **Cambio de Credenciales:** Resetear **todas** las contraseñas de administración (suponer que fueron robadas).

#### FASE 4: Recuperación (La Rehabilitación)
*Prioridad: Restaurar el servicio de forma segura.*
* **Restauración:** Levantar servicios desde backups limpios (verificados).
* **Monitoreo Intensivo:** Vigilar el tráfico de red por 24/48 horas para asegurar que el atacante no regrese.
* **Retorno a Normalidad:** El IC declara el fin del incidente.

---

### 3. PLAYBOOK ESPECÍFICO: RANSOMWARE
*(Guía rápida para casos tipo Akira/LockBit)*

**A. Acción Inmediata (Minutos 0-15)**
1.  [ ] **Aislar:** Desconectar físicamente o lógicamente los equipos infectados de la red central.
2.  [ ] **Proteger Backups:** Verificar que los repositorios de respaldo estén desconectados de la red o en modo inmutable inmediatamente para evitar que sean cifrados.
3.  [ ] **Identificar Variante:** Tomar una muestra de la nota de rescate y archivo cifrado. Subir a *ID Ransomware* (desde una red externa) para identificar la familia.

**B. Decisión de Negocio (Horas 1-4)**
1.  [ ] **Evaluar Viabilidad:** ¿Podemos restaurar desde backups?
    * *SÍ:* Proceder a limpiar y restaurar. **NO PAGAR.**
    * *NO (Backups cifrados/inexistentes):* Escalar al Comité de Crisis/Directorio. Solo ellos pueden decidir sobre negociación/pago (considerando legalidad).

**C. Investigación Forense (Paralelo)**
1.  [ ] **Vector de Entrada:** ¿Cómo entraron? (VPN sin MFA, Phishing, RDP expuesto). **Si no se encuentra la entrada, volverán a entrar.**
2.  [ ] **Exfiltración:** Revisar logs de firewall para ver si salieron grandes volúmenes de datos (Doble Extorsión).

---

### 4. PLAYBOOK ESPECÍFICO: COMPROMISO DE CORREO (BEC)
*(Guía para Phishing, Robo de Credenciales)*

1.  [ ] **Bloqueo:** Resetear contraseña del usuario afectado y cerrar todas las sesiones activas (Token Revocation).
2.  [ ] **MFA:** Forzar re-registro de Multi-Factor Authentication.
3.  [ ] **Auditoría de Reglas:** Revisar si el atacante creó reglas de "Reenvío automático" o "Eliminación" en el buzón para ocultar sus huellas.
4.  [ ] **Búsqueda Interna:** Buscar si el usuario envió correos de phishing a otros empleados o clientes desde su cuenta.

---

### 5. Lista de Contactos Críticos (Llenar previamente)

| Rol | Nombre / Empresa | Teléfono 24/7 | Correo Alternativo |
| :--- | :--- | :--- | :--- |
| **Soporte Firewall/Red** | (Ej: Proveedor ISP) | | |
| **Soporte Microsoft/Cloud** | (Ej: Partner Azure) | | |
| **Forense Externo** | (Ej: Empresa Ciberseguridad) | | |
| **Legal / Abogado** | | | |
| **Seguro (Ciberpóliza)** | | | |
| **CSIRT Nacional** | (Enlace Gobierno) | | |

---

### 6. Protocolo de Evidencia (Cadena de Custodia)
Para fines de sumario administrativo o denuncia legal:
1.  No trabajar sobre la "Evidencia Original". Hacer una copia imagen (bit-a-bit) de los discos afectados.
2.  Registrar quién tuvo acceso al disco, cuándo y por qué en la Bitácora (Anexo A).
3.  Almacenar la evidencia en un lugar seguro bajo llave.
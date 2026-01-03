# ANEXO I: Plan de Recuperación de Desastres (DRP)
**(Plantilla de Restauración Tecnológica)**

### 1. Alcance y Priorización (Tiers)
No todos los servidores son iguales. En una crisis, no se puede "levantar todo a la vez". Se debe seguir un orden estricto de dependencias e importancia de negocio (definido en el BIA).

| Nivel (Tier) | Descripción | RTO Objetivo | Activos Típicos |
| :--- | :--- | :--- | :--- |
| **Tier 0 (Vital)** | Infraestructura base. Sin esto, nada funciona. | < 2 Horas | Directorio Activo (AD), DNS, DHCP, SAN/Storage, Firewalls, **Consola de Backups**. |
| **Tier 1 (Crítico)** | Servicios Core del Negocio. Si faltan, perdemos dinero/normativa. | < 4-8 Horas | ERP, Base de Datos Principal, Web Transaccional, Correo. |
| **Tier 2 (Importante)** | Operación interna. | < 24 Horas | Servidor de Archivos, CRM Secundario, Intranet. |
| **Tier 3 (Soporte)** | No urgente. | > 48 Horas | Entornos de Desarrollo/QA, Archivos Históricos. |

### 2. Estrategia de Protección de Datos (Anti-Ransomware)
Para garantizar la recuperabilidad ante ataques destructivos (tipo Akira), la arquitectura de respaldo cumple la **Regla 3-2-1-1**:

1.  **3** Copias de los datos (Producción + Copia A + Copia B).
2.  **2** Medios diferentes (Disco y Nube/Cinta).
3.  **1** Copia fuera del sitio (Off-site).
4.  **1** Copia **INMUTABLE** o **OFFLINE** (Air-gapped).
    * *Nota:* Esta copia no puede ser borrada ni siquiera con credenciales de Administrador de Dominio. Es la única defensa contra el borrado de shadow copies.

### 3. Procedimiento de Activación del DRP

El DRP se activa cuando el Incident Commander declara que la infraestructura actual es **irrecuperable** o **no confiable** y se requiere restauración masiva.

#### FASE 1: Preparación de la "Zona Limpia" (Clean Room)
**¡ADVERTENCIA!** No restaurar sobre la red infectada.
1.  Aislar una subred (VLAN de Recuperación) que no tenga conexión con la red infectada ni con Internet abierto.
2.  Reconstruir o verificar la integridad de la capa de virtualización (VMware/Hyper-V). Si el ataque fue a nivel de hipervisor, se debe reinstalar desde cero (Bare Metal Restore).

#### FASE 2: Restauración de Servicios Base (Tier 0)
1.  **Identidad:** Restaurar el Controlador de Dominio (DC) en la Zona Limpia.
    * *Validación:* Verificar que el DNS resuelve y que las cuentas de administrador de emergencia funcionan.
2.  **Seguridad:** Levantar consola de Antivirus/EDR. Asegurar que los agentes se instalen en cada máquina que se levante a continuación.

#### FASE 3: Restauración de Datos y Aplicaciones (Tier 1)
1.  **Base de Datos:** Restaurar DB Server. Verificar integridad de tablas (DBCC CHECKDB).
2.  **Aplicación:** Restaurar App Server. Conectar a la DB.
3.  **Saneamiento:** Escanear el servidor restaurado con antivirus actualizado *antes* de abrirlo a los usuarios. (Evitar que el backup traiga el virus dormido).

#### FASE 4: Reconexión de Red
1.  Una vez validados los Tier 0 y 1, abrir rutas de red controladas.
2.  Forzar cambio de contraseñas a todos los usuarios antes de permitir el login.

### 4. Inventario de Recuperación (Llenar con datos reales)

| Sistema | IP Original | Dependencias | Ubicación del Backup | Encargado TI |
| :--- | :--- | :--- | :--- | :--- |
| Controlador Dominio 1 | 192.168.x.x | Ninguna | Repositorio Inmutable A | Juan Pérez |
| Servidor SQL ERP | 192.168.x.x | Dominio, Storage | Repositorio B | María Gómez |
| Web Server | 192.168.x.x | SQL, Firewall | Azure Blob | Pedro D. |

### 5. Plan de Pruebas (Drills)
Un DRP no probado es una alucinación.

* **Prueba de Escritorio (Trimestral):** Revisar este documento y verificar que los contactos y prioridades siguen vigentes.
* **Prueba Técnica Granular (Semestral):** Restaurar aleatoriamente un servidor crítico en un entorno de sandbox y verificar que los datos son legibles.
* **Simulacro Total (Anual):** Simular caída completa en fin de semana. Medir tiempos reales de restauración vs. RTO prometido.

---

### Notas para el Equipo de Infraestructura:
* **Credenciales de Backup:** La consola de backup NO debe estar unida al dominio. Si cae el Directorio Activo, no podemos perder el acceso a los backups.
* **Documentación Física:** Mantener una copia impresa de este anexo. Si el ransomware cifra el servidor de archivos donde guarda este Word, no podrá leer las instrucciones para recuperarlo.
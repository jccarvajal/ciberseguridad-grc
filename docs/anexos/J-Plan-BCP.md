# ANEXO J: Plan de Continuidad de Negocio (BCP)
**(Manual de Supervivencia y Operación Manual)**

### 1. Objetivo y Alcance
Este plan establece los procedimientos para mantener las funciones críticas de la organización operativas cuando la tecnología de soporte no está disponible.
Se activa cuando el tiempo estimado de recuperación tecnológica (RTO) supera el tiempo máximo tolerable por el negocio (MTPD).

**Lema del BCP:** *"La tecnología se detiene, pero el servicio continúa."*

### 2. Análisis de Impacto al Negocio (BIA) - Resumen Crítico
*Identificación de procesos que NO pueden detenerse.*

| Proceso Crítico | Impacto de la Parada | MTPD (Tiempo Máx. sin servicio) | Estrategia de Continuidad |
| :--- | :--- | :--- | :--- |
| **Atención a Usuarios/Ciudadanos** | Quejas legales, multas, daño reputacional severo. | 4 Horas | Ventanilla manual con formularios físicos pre-impresos. |
| **Pagos a Proveedores/Nómina** | Corte de suministros, huelga, incumplimiento contractual. | 24 - 48 Horas | Emisión de cheques manuales o transferencias vía portal bancario externo (4G). |
| **Recepción de Documentos** | Vencimiento de plazos legales. | 24 Horas | Libro de ingresos manual (Timbre de agua). |
| **Comunicación Interna** | Caos y rumores. | Inmediato | Árbol de llamadas telefónicas y Tablón de Anuncios físico. |

### 3. Procedimientos de Operación en "Modo Degradado" (Papel)

Cuando se activa el BCP, cada área debe sacar su "Kit de Emergencia" físico.

#### A. Atención al Público / Ventanilla
1.  **Formularios:** Utilizar talonarios de formularios de solicitud pre-impresos (guardados en bodega).
2.  **Registro:** Anotar cada ingreso en el "Libro de Actuaciones de Contingencia" (foliado y timbrado).
3.  **Respaldo:** Tomar fotografía (con dispositivo autorizado) o fotocopia de la cédula de identidad y documentos entregados por el usuario.
4.  **Compromiso:** Informar al usuario que su trámite ingresó, pero que el procesamiento iniciará cuando retornen los sistemas.

#### B. Finanzas y Pagos
1.  **Bancos:** Si la red interna está caída, el Tesorero y el Apoderado deben dirigirse a una ubicación con internet seguro (o usar dongles 4G corporativos limpios) para acceder a los portales bancarios en la nube.
2.  **Registro:** Llevar planilla Excel local (en laptop aislada) de todos los pagos realizados para su posterior conciliación.

#### C. Comunicaciones
1.  Si el correo corporativo (Exchange/Gmail) no funciona o no es seguro:
    * **Interno:** Usar megafonía, carteles en ascensores o cadenas de WhatsApp (solo para coordinación, no para datos sensibles).
    * **Externo:** Habilitar una casilla de correo de emergencia temporal (ej: `emergencia.institucion@gmail.com`) *solo* si es legalmente viable, o derivar todo a canal telefónico/presencial.

### 4. La Fase de Retorno: Digitación y Conciliación
*El BCP no termina cuando vuelve la luz. Termina cuando los datos del papel están en el sistema.*

Una vez que TI declara los sistemas "Operativos" (Anexo C), se inicia el **Plan de Recuperación de Datos (Data Catch-up)**:

1.  **Congelamiento:** No abrir el sistema al público general todavía.
2.  **Digitación:** Asignar un equipo de "digitadores de emergencia" para ingresar manualmente todos los formularios, pagos y trámites acumulados durante la crisis.
3.  **Validación:** Verificar que los totales del sistema coincidan con los libros manuales.
4.  **Apertura:** Una vez sincronizados, se declara el fin de la Contingencia.

### 5. Logística de Emergencia (Kit BCP)
Cada Gerencia/Departamento debe tener una caja física ("Crash Box") que contenga:

* [ ] Copia impresa de este Plan BCP y del IRP.
* [ ] Lista de teléfonos de empleados y proveedores críticos.
* [ ] Formularios de papel esenciales (Facturas, Solicitudes, Actas).
* [ ] Bolígrafos, libretas, engrapadoras.
* [ ] Linternas y baterías (si la crisis implica corte eléctrico).
* [ ] Modem/Banda Ancha Móvil de respaldo (no conectado a la red corporativa).

### 6. Directorio de Proveedores Críticos (Llenar)

| Servicio | Proveedor | Contacto Comercial | Contacto Emergencia 24/7 |
| :--- | :--- | :--- | :--- |
| **Internet / Enlaces** | | | |
| **Aseo / Seguridad Física** | | | |
| **Insumos / Logística** | | | |
| **Abogado Externo** | | | |
| **Seguro** | | | |

---
**Nota para el Responsable del BCP:**
La prueba de este plan es simple: Corte el cable de red de su departamento un martes por la mañana. ¿Pueden seguir trabajando? Si la respuesta es "no, nos vamos a tomar café", entonces **no tiene un BCP**.

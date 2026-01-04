# ANEXO J: Plan de Continuidad de Negocio (BCP)
**(Manual de Supervivencia y Operación Manual)**

### 1. Objetivo y Alcance

Este plan establece los procedimientos para mantener las funciones críticas de la organización operativas cuando la tecnología de soporte no está disponible. A diferencia del DRP (que busca revivir servidores), el **BCP busca mantener vivo el flujo de valor**.

**Criterio de Activación:** Se activa cuando el tiempo estimado de recuperación tecnológica (**RTO** del DRP) supera el tiempo máximo tolerable de interrupción (**MTPD**) definido por el negocio.

> **Lema del BCP:** *"La tecnología se detiene, pero el servicio continúa."*

---

### 2. Resumen del BIA (*Business Impact Analysis*)
*Identificación de procesos que NO pueden detenerse bajo ninguna circunstancia.*

Este cuadro dicta la prioridad de recuperación del Anexo I.

| Proceso Crítico | Impacto de la Parada (GRC) | MTPD (Tiempo Máx. sin servicio) | Estrategia de Continuidad (Modo Degradado) |
| :--- | :--- | :--- | :--- |
| **Atención a Ciudadanos / Clientes** | Quejas legales, multas de regulador, daño reputacional severo. | **4 Horas** | Ventanilla manual con formularios físicos pre-impresos y numerados. |
| **Pagos a Proveedores / Nómina** | Corte de suministros críticos, huelga, incumplimiento contractual. | **24 - 48 Horas** | Emisión de cheques manuales o transferencias vía portal bancario externo (Red 4G aislada). |
| **Recepción de Documentos Legales** | Vencimiento de plazos fatales (Prescripción). | **24 Horas** | Libro de ingresos manual (Foliado y con timbre de agua oficial). |
| **Comunicación y Mando** | Caos, rumores y parálisis de decisión. | **Inmediato (< 15 min)** | Árbol de llamadas telefónicas satelitales/celulares y Tablón de Anuncios físico. |

---

### 3. Procedimientos de Operación en "Modo Degradado"

Cuando el **Comité de Crisis** activa el BCP, cada área debe ejecutar su protocolo analógico ("Lápiz y Papel").

#### A. Atención al Público / Ventanilla
1.  **Formularios:** Utilizar talonarios de formularios de solicitud pre-impresos (sacados de la bodega de seguridad).
2.  **Registro Legal:** Anotar cada ingreso en el "Libro de Actuaciones de Contingencia" (debe estar foliado y timbrado para validez legal).
3.  **Respaldo de Identidad:** Tomar fotografía (con dispositivo corporativo autorizado) o fotocopia de la cédula de identidad y documentos entregados.
4.  **Gestión de Expectativas:** Informar al usuario que su trámite ha sido recibido legalmente (fecha/hora), pero que el procesamiento iniciará cuando retornen los sistemas.

#### B. Finanzas y Tesorería
1.  **Bancos:** Si la red interna está comprometida, el Tesorero y el Apoderado deben trasladarse a una ubicación externa o usar *dongles* 4G corporativos limpios para acceder a los portales bancarios en la nube. **Nunca usar la red infectada.**
2.  **Registro Paralelo:** Mantener una planilla Excel local (en laptop aislada) de todos los pagos realizados para su posterior conciliación.

#### C. Comunicaciones Internas
1.  Si el correo corporativo (Exchange/Gmail) no funciona o no es confiable:
    * **Interno:** Usar megafonía, carteles físicos en ascensores/pasillos o cadenas de mensajería segura (*Signal*) para coordinación.
    * **Externo:** Habilitar una casilla de correo de emergencia temporal (ej: `emergencia.institucion@gmail.com`) *solo* si es legalmente viable y autorizado por Fiscalía.

---

### 4. La Fase de Retorno: Conciliación de Datos (*Data Catch-up*)

*El BCP no termina cuando vuelve la luz. Termina cuando los datos del papel están en el sistema digital.*

Una vez que TI declara los sistemas "Operativos y Limpios" (Fin del Anexo I), se inicia el proceso más riesgoso: la sincronización.

1.  **Congelamiento:** No abrir el sistema al público general todavía.
2.  **Digitación Intensiva:** Asignar un equipo de "digitadores de emergencia" para ingresar manualmente todos los formularios, pagos y trámites acumulados durante la crisis.
3.  **Validación Cruzada:** Verificar que los totales del sistema coincidan exactamente con los libros manuales y planillas Excel de emergencia.
4.  **Apertura:** Solo una vez conciliado el 100% de los datos, se declara el fin de la Contingencia.

---

### 5. Logística de Emergencia (La "Crash Box")

Cada Gerencia o Departamento Crítico debe tener una caja física sellada ("Crash Box") que contenga:

* [ ] Copia impresa de este Plan BCP, del IRP y del Directorio de Contactos (Anexo G).
* [ ] Talonarios de formularios críticos (Facturas, Solicitudes, Actas, Recibos).
* [ ] "Libro de Actas de Contingencia" (Cuaderno de tapa dura, foliado).
* [ ] Material de oficina básico (Bolígrafos, libretas, engrapadoras, sellos/timbres).
* [ ] Linternas y baterías (si la crisis implica corte eléctrico).
* [ ] Modem/Banda Ancha Móvil de respaldo (no conectado a la red corporativa).
* [ ] Radio a pilas o satelital (según zona geográfica).

---

### 6. Directorio de Proveedores Críticos

*Mantener actualizado trimestralmente. Sin estos teléfonos, el BCP falla.*

| Servicio Crítico | Proveedor | Contacto Comercial | Emergencia 24/7 |
| :--- | :--- | :--- | :--- |
| **Enlace Internet / Datos** | | | |
| **Seguridad Física / Guardias** | | | |
| **Insumos / Logística** | | | |
| **Abogado Externo** | | | |
| **Aseguradora (Póliza)** | | | |

---

> **ADVERTENCIA DE PRIVACIDAD (LEY 19.628):**
> En modo manual, los formularios con datos personales quedan expuestos en escritorios.
> **Regla:** Todo papel con datos sensibles debe guardarse bajo llave cada vez que el funcionario se levanta de su puesto. La seguridad física del papel es ahora su ciberseguridad.

---
**Prueba de Fuego para el Responsable:**

La prueba de este plan es simple: Corte el cable de red de su departamento un martes por la mañana sin avisar. **¿Pueden seguir trabajando y facturando?**
Si la respuesta es "no, nos vamos a tomar café", entonces **usted no tiene un BCP, solo tiene buenos deseos.**

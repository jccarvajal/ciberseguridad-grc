# ANEXO N: La Línea Base de Higiene Digital
**(Controles Esenciales de Debida Diligencia)**

### 1. Propósito y Alcance

Este documento define el **"Piso Mínimo de Seguridad"** (*Security Baseline*).
No representa la excelencia, sino la **supervivencia operativa**.

!!! failure "Axioma de Auditoría"
    La ausencia de cualquiera de estos controles en una organización moderna no se considera una "brecha técnica" compleja, sino una **negligencia administrativa** por falta de gobierno básico.

Estos controles son agnósticos al tamaño de la organización y siguen el **Principio de Pareto**: constituyen el 20% del esfuerzo táctico que mitiga el 80% de los vectores de ataque oportunistas.

---

### 2. Higiene de Presencia Pública
*(El Perímetro Expuesto)*

La ausencia de estos controles es visible públicamente sin necesidad de intrusión. Señala a los atacantes y auditores que la organización es un "Objetivo Blando" (*Low Hanging Fruit*), **incrementando significativamente la probabilidad de ataques oportunistas**.

#### A. Identidad del Correo (Anti-Spoofing)
* **Control:** Implementación estricta de la tríada **SPF, DKIM y DMARC**.
* **Configuración Requerida:** DMARC debe estar configurado en modo `p=reject` o `p=quarantine`.
* **Advertencia de Auditoría:** Mantener una política `p=none` por periodos extendidos indica una madurez incompleta y no protege la marca.
* **Impacto GRC:** Previene la suplantación de identidad del CEO o la marca oficial (Fraude Financiero y Daño Reputacional).

#### B. Integridad Web
* **Control:** **HSTS (HTTP Strict Transport Security)**.
* **Configuración Requerida:** Cabecera obligatoria en servidores web que fuerza a los navegadores a conectarse *exclusivamente* por HTTPS.
* **Impacto GRC:** Mitiga ataques de interceptación (*Man-in-the-Middle*) asegurando la confidencialidad de los datos de clientes en tránsito.

#### C. Divulgación Coordinada de Vulnerabilidades
* **Control:** Archivo **`security.txt`** (Estándar RFC 9116).
* **Ubicación:** `dominio.com/.well-known/security.txt`
* **Impacto GRC:** Establece el canal oficial para que investigadores reporten vulnerabilidades antes de su explotación masiva. Demuestra diligencia proactiva ante la comunidad global y los reguladores.

---

### 3. Higiene de Identidad y Acceso
*(El Nuevo Perímetro Lógico)*

Desaparecido el perímetro físico, la identidad es la única barrera efectiva.

#### A. Autenticación Robusta
* **Control:** **MFA (Multi-Factor Authentication)** Mandatorio.
* **Alcance:** 100% de los accesos remotos (VPN, Correo, SaaS) y 100% de las cuentas con privilegios administrativos.
* **Regla de Oro:** Una contraseña, independiente de su complejidad, se considera un control **comprometido por defecto**.
* **Impacto GRC:** Neutraliza la inmensa mayoría de ataques automatizados de fuerza bruta y reutilización de credenciales (*Credential Stuffing*).

#### B. Segregación de Privilegios
* **Control:** Separación estricta de cuentas de Usuario vs. Administrador.
* **Regla de Oro:** Ningún funcionario (incluido personal TI) debe navegar por internet o gestionar correo utilizando credenciales de "Admin de Dominio" o "Root".
* **Impacto GRC:** **Contención**. Si un usuario ejecuta malware, el daño queda encapsulado en su sesión y se evita la propagación lateral a toda la infraestructura.

---

### 4. Higiene de Datos
*(La Última Línea de Defensa)*

Cuando la prevención falla, estos controles determinan la viabilidad futura de la institución.

#### A. Respaldo Inmutable
* **Control:** Estrategia de Backup **3-2-1-1-0**.
    * **3** copias de los datos.
    * **2** medios de almacenamiento diferentes.
    * **1** copia fuera del sitio (*Off-site*).
    * **1 copia inmutable (Offline/WORM):** Inaccesible para el ransomware.
    * **0** errores en pruebas de restauración semestrales.
* **Impacto GRC:** Es el único antídoto real contra el Ransomware moderno. Sin esta capacidad, la continuidad operacional deja de ser una estrategia y se convierte en una **apuesta**.

#### B. Inventario de Activos
* **Control:** Mapeo actualizado y **automatizado** de Hardware y Software.
* **Axioma:** "No se puede gobernar lo que no se conoce".
* **Advertencia:** Los inventarios manuales o declarativos (hojas de cálculo estáticas) se consideran inherentemente incompletos y obsoletos desde su creación.
* **Impacto GRC:** Visibiliza el *Shadow IT* (sistemas olvidados), que estadísticamente representan la puerta de entrada principal en incidentes de alto impacto.

---

### 5. Racionalidad de la Selección (Causa-Efecto)

Cada control en esta lista ha sido seleccionado no por su popularidad, sino porque mitiga directamente un riesgo de carácter existencial para la organización:

| Control de Higiene | Riesgo Existencial que Mitiga |
| :--- | :--- |
| **DMARC / SPF / DKIM** | Fraude Financiero (CEO Fraud) |
| **MFA** | Secuestro de Cuentas (Account Takeover) |
| **Segregación** | Propagación Masiva (Lateral Movement) |
| **Backup Inmutable** | Extorsión y Cierre Operacional (Ransomware) |
| **Inventario** | Ataques Invisibles (Shadow IT) |

!!! warning "Controles Decisivos vs. Controles Tranquilizadores"
    El lector notará la ausencia deliberada del **cifrado de datos** (Encryption) en esta Línea Base. Esta omisión no es un descuido, es una decisión doctrinaria.

    En este marco de trabajo, un control solo se considera "esencial" cuando su ausencia hace inevitable el fracaso operativo frente a ataques comunes.

    El cifrado protege la confidencialidad de los datos, pero no previene la toma de cuentas, no detiene el ransomware, no impide la extorsión ni evita la propagación lateral cuando la identidad ha sido comprometida. En la mayoría de los incidentes reales, los datos ya se encuentran descifrados en el momento del ataque (porque el usuario legítimo accedió a ellos).

    Por esta razón, el cifrado, aunque recomendable y legalmente exigible en muchos contextos, no pertenece al **piso mínimo de supervivencia operativa**, sino a capas posteriores de cumplimiento y gestión reputacional. Confundir controles tranquilizadores con controles decisivos es uno de los errores más costosos en la gestión moderna.

---

### 6. Alineación Normativa (Referencia Cruzada)

La implementación de esta Línea Base cubre los requisitos fundamentales de los principales marcos de control:

| Control | NIST CSF 2.0 | ISO 27001:2022 | CIS Controls v8 |
| :--- | :--- | :--- | :--- |
| **Identidad (MFA)** | PR.AA-03 | A.5.17 | CIS 06 |
| **Respaldo (Backup)** | PR.DS-11 | A.8.13 | CIS 11 |
| **Vulnerabilidades** | ID.RA-01 | A.8.8 | CIS 07 |
| **Inventario** | ID.AM-01 | A.5.9 | CIS 01 |

!!! danger "Nota Final al Directorio"
    Priorizar inversiones en tecnologías emergentes (IA, Blockchain) sin haber resuelto esta **Higiene Digital** no es un error tecnológico, sino un **error de priorización estratégica** que compromete el deber fiduciario.

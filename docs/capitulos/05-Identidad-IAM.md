# CAPÍTULO 5: La Identidad es el Nuevo Perímetro
**(Gobernanza de Acceso y Soberanía Digital)**

Como mencionamos en el capítulo anterior, el "foso" del castillo ha desaparecido. En un ecosistema donde los empleados trabajan desde sus casas y las aplicaciones residen en la nube, la única forma de saber si debemos permitir una acción es validando **quién** la solicita. 

En la ciberseguridad moderna, la **Identidad (IAM - *Identity and Access Management*)** no es solo un tema de nombres de usuario y contraseñas; es el eje central de la gobernanza. Si la identidad se ve comprometida, todo el modelo de resiliencia financiera (Capítulo 2) se desmorona.

### 1. El Ciclo de Vida de la Identidad: Un Proceso de Negocio

El mayor riesgo de identidad no suele ser un atacante externo, sino la mala gestión interna. El **Mando Medio** debe ver el IAM como un ciclo de vida que acompaña al activo más crítico (el humano) desde su ingreso hasta su salida:

1.  **Aprovisionamiento (*Joiner*):** Creación de la identidad bajo el estricto cumplimiento del "Mínimo Privilegio".
2.  **Cambios (*Mover*):** Ajuste dinámico de permisos cuando un empleado cambia de rol, eliminando la "acumulación de privilegios" que genera puntos ciegos de seguridad.
3.  **Desaprovisionamiento (*Leaver*):** El punto más crítico. Las "cuentas huérfanas" de exempleados son el vector principal para el despliegue de ransomware y exfiltración de datos.

---

### 2. El Triángulo de la Autenticación Moderna

Para el **Ingeniero**, asegurar la identidad significa pasar de una autenticación estática a una basada en el riesgo. El estándar de oro es el **MFA (*Multi-Factor Authentication*)**, construido sobre tres pilares:

* **Algo que sabes:** Una contraseña (el factor más vulnerable y propenso al error humano).
* **Algo que tienes:** Un token físico, una aplicación autenticadora o una llave de seguridad (FIDO2).
* **Algo que eres:** Biometría (huella, rostro, reconocimiento de iris).

**La Regla del Vigilante:** Si un acceso a un activo crítico no cuenta con al menos dos de estos factores, el riesgo de suplantación es absoluto ante ataques de *phishing* moderno.

!!! info "Estándar Técnico: ¿Por qué FIDO2?"
    A diferencia de un código SMS o una App de autenticación, una llave de seguridad física (FIDO2) es **resistente al Phishing** por diseño criptográfico.
    
    Incluso si el usuario es engañado y entra a una web falsa (*clonada*), la llave física detectará que el dominio no coincide con el original y se negará a firmar la petición de acceso. Es la única defensa efectiva contra ataques de ingeniería social en tiempo real.
    
---

### 3. PAM: Protegiendo las Llaves del Reino y la Trazabilidad

No todas las identidades tienen el mismo impacto. Las **Cuentas Privilegiadas** poseen la facultad de comprometer la continuidad total del negocio. Su gestión exige una estrategia de **PAM (*Privileged Access Management*)**:

* **Just-in-Time (JIT):** El administrador no posee permisos permanentes; se activan bajo demanda y expiran automáticamente.
* **Bóveda de Credenciales:** Las contraseñas críticas son gestionadas y rotadas por el sistema, no por humanos.

**Evidencia Verificable:** Desde una perspectiva de gobernanza, cada evento de autenticación, elevación de privilegio o acceso denegado debe quedar registrado como evidencia auditable, vinculable a una identidad y a una decisión de negocio. Todo control que no genera evidencia es, bajo escrutinio regulatorio, inexistente.

!!! danger "Advertencia de Gobernanza: El Fin de la Imputabilidad"
    El uso de cuentas administrativas genéricas o compartidas (ej: "root", "admin", "soporte") impide la atribución legal de acciones.
    
    Si tres ingenieros conocen la clave del usuario "Admin", y ese usuario borra un servidor, es jurídicamente imposible probar quién fue. Sin **No Repudio** (capacidad de probar autoría), no hay responsabilidad administrativa ni penal posible. **Cada acción privilegiada debe estar vinculada a un RUT/DNI específico.**
    
---

### 4. Blueprint 5: Matriz de Control de Acceso (RBAC vs. ABAC)

!!! example "Comparativa de Modelos de Autorización"
    La identidad moderna no es un cargo estático, es un contexto dinámico. Esta matriz guía la transición desde la asignación rígida de permisos hacia una validación en tiempo real basada en el riesgo.

    | Modelo | Definición | Uso Recomendado |
    | :--- | :--- | :--- |
    | **RBAC** (Basado en Roles) | Permisos según el cargo estático (ej: "Contador"). | Organizaciones con estructuras jerárquicas rígidas. |
    | **ABAC** (Basado en Atributos)| Permisos según el contexto dinámico (ej: "Rol" + "Ubicación" + "Dispositivo"). | **Arquitecturas Zero Trust de alta madurez.** |
    | **Mínimo Privilegio** | Otorgar solo la autoridad necesaria para la tarea actual. | **Estándar obligatorio para cumplimiento de Ley 21.663.** |

---

### 5. Identidad y Riesgo Financiero

Desde la perspectiva del **Directorio**, una gestión deficiente de identidades tiene un impacto directo en el ***SLE* (*Single Loss Expectancy*)**:

* **Fraude Interno:** Una proporción significativa del fraude financiero tiene su origen en excesos de privilegios o fallas graves en la segregación de funciones (SoD).
* **Cumplimiento ANCI:** La identidad es la evidencia primaria de control. La incapacidad de demostrar quién accedió a un dato sensible constituye una confesión de negligencia ante la autoridad.

---

### Conclusión: La Identidad como Eje de Imputabilidad

La identidad es el "Ghost" (el espíritu) dentro de la arquitectura técnica. Si no controlamos quién entra y qué facultad tiene para actuar, no poseemos seguridad, solo la ilusión de ella. En términos de gobernanza, la identidad es el mecanismo que permite atribuir una acción, evaluar su legitimidad y sostenerla ante el escrutinio regulatorio.

El ingeniero que implementa MFA y el gerente que audita periódicamente las cuentas activas están cerrando la brecha más peligrosa de la organización. En el próximo capítulo, veremos cómo proteger el activo final: los datos. Entraremos en la **Higiene de Datos (DLP)** y la defensa de la soberanía de la información.

---

!!! abstract "Tesis del Capítulo"
    En la red moderna, la identidad es el único perímetro real. Sin una gobernanza que garantice la trazabilidad y la atribución, el riesgo financiero es inmanejable y la responsabilidad legal es total.

---
# CAPÍTULO 5: La Identidad es el Nuevo Perímetro
**(Gobernanza de Acceso y Soberanía Digital)**

Como mencionamos en el capítulo anterior, el "foso" del castillo ha desaparecido. En un ecosistema donde los empleados trabajan desde sus casas y las aplicaciones residen en la nube, la única forma de saber si debemos permitir una acción es validando **quién** la solicita. 

En la ciberseguridad moderna, la **Identidad (IAM - Identity and Access Management)** no es solo un tema de nombres de usuario y contraseñas; es el eje central de la gobernanza. Si la identidad se ve comprometida, todo el modelo de resiliencia financiera (Capítulo 2) se desmorona.

### 1. El Ciclo de Vida de la Identidad: Un Proceso de Negocio

El mayor riesgo de identidad no suele ser un hacker externo, sino la mala gestión interna. El **Mando Medio** debe ver el IAM como un ciclo de vida que acompaña al empleado desde su ingreso hasta su salida:

1.  **Aprovisionamiento (Joiner):** Creación de la identidad con el "Mínimo Privilegio".
2.  **Cambios (Mover):** Ajuste de permisos cuando un empleado cambia de rol (evitando la "acumulación de privilegios").
3.  **Desaprovisionamiento (Leaver):** El punto más crítico. Las "cuentas huérfanas" de exempleados son la puerta de entrada principal para el ransomware.



---

### 2. El Triángulo de la Autenticación Moderna

Para el **Ingeniero**, asegurar la identidad significa pasar de una autenticación estática a una dinámica. El estándar de oro es el **MFA (Multi-Factor Authentication)**, basado en tres factores:
* **Algo que sabes:** Una contraseña (el factor más débil).
* **Algo que tienes:** Un token físico, una aplicación en el celular o una llave de seguridad (FIDO2).
* **Algo que eres:** Biometría (huella, rostro, iris).

**La Regla del Vigilante:** Si un acceso crítico no tiene al menos dos de estos factores, el riesgo de suplantación es cercano al 100% en caso de un ataque de *phishing*.

### 3. PAM: Protegiendo las Llaves del Reino

No todas las identidades son iguales. Las **Cuentas Privilegiadas** (administradores de bases de datos, redes o sistemas core) tienen el poder de destruir la organización.

La gestión de estas cuentas requiere una estrategia de **PAM (Privileged Access Management)**:
* **Just-in-Time (JIT):** El administrador no tiene permisos permanentes. Los solicita solo cuando los necesita y por un tiempo limitado (ej. 2 horas).
* **Bóveda de Credenciales:** Las contraseñas de administrador no las conoce el humano; están cifradas y rotan automáticamente tras cada uso.

---

### 4. Blueprint 5: Matriz de Control de Acceso (RBAC vs. ABAC)

El **Mando Medio** debe decidir cómo otorgar permisos. En este libro proponemos la transición hacia modelos más inteligentes:

| Modelo | Definición | Uso Recomendado |
| :--- | :--- | :--- |
| **RBAC** (Basado en Roles) | Permisos según el cargo (ej: "Contador"). | Organizaciones estables y jerárquicas. |
| **ABAC** (Basado en Atributos)| Permisos según el contexto (ej: "Contador" + "Horario laboral" + "Desde oficina"). | Organizaciones con alta movilidad y arquitectura Zero Trust. |
| **Mínimo Privilegio** | Dar solo lo justo para la tarea actual. | **Obligatorio para cumplimiento de Ley 21.663.** |



---

### 5. Identidad y Riesgo Financiero

Desde la perspectiva del **Directorio**, una mala gestión de identidades impacta directamente en el **SLE (Single Loss Expectancy)**:
* **Fraude Interno:** El 60% de los fraudes financieros ocurren por exceso de privilegios o falta de segregación de funciones (SoD).
* **Multas Legales:** La Ley 21.663 y las leyes de protección de datos (19.628) sancionan severamente la falta de control sobre quién accede a la información sensible.

### Conclusión para el "Vigilante Estratégico"

La identidad es el "Ghost" (el espíritu) dentro de la máquina. Si no controlamos quién entra y qué puede hacer, no tenemos seguridad, solo tenemos la ilusión de ella. El ingeniero que implementa MFA y el gerente que audita las cuentas huérfanas están cerrando la brecha más peligrosa de la empresa.

En el próximo capítulo, veremos cómo proteger el activo que estas identidades buscan consumir: los datos. Entraremos en la **Higiene de Datos (DLP)** y la soberanía de la información.

---
> **Tesis del Capítulo:** En la red moderna, tu identidad es tu pasaporte. Sin una gobernanza estricta de quién es quién, el perímetro es inexistente y el riesgo es total.
---
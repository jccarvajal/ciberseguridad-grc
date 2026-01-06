# CAPÍTULO 6: Higiene de Datos y Soberanía (DLP)
**(Protegiendo el Activo más Crítico)**

Si la Identidad (Capítulo 5) es el pasaporte que permite circular por la organización, el **Dato** es la mercancía valiosa que ese pasaporte intenta proteger. En el entorno de 2026, los datos mal gestionados son similares a los **desechos radiactivos**: extremadamente útiles si se mantienen en su contenedor, pero catastróficos si se filtran.

La higiene de datos no es solo un proceso de limpieza; es la capacidad técnica de asegurar que la información sensible no abandone la organización por canales no autorizados (**DLP - *Data Loss Prevention***).

### 1. El Dilema de la Visibilidad y el Ruido de Juicio

El mayor riesgo para el **Mando Medio** es la "oscuridad de datos". No se puede proteger lo que no se conoce. La higiene institucional comienza con la **Clasificación**, un proceso que debe ser dictado por el negocio pero ejecutado por la técnica para reducir el **Ruido de Juicio** en la toma de decisiones:

* **Públicos:** Información de marketing y comunicados.
* **De Uso Interno:** Minutas, memorándums y flujos operativos.
* **Confidenciales:** Datos financieros y datos personales (sujetos a la **Ley 19.628**).
* **Secretos:** Propiedad intelectual, "Joyas de la Corona" y estrategias de mercado.

---

### 2. DLP: Los Tres Estados del Dato

Para el **Ingeniero**, la protección no es un estado estático, sino un flujo continuo. El sistema DLP debe generar evidencia de control en los tres estados del ciclo de vida:

1.  **Dato en Reposo (*At Rest*):** Almacenado en servidores o nubes. La defensa es el **Cifrado** y la gestión de acceso privilegiado (Capítulo 5).
2.  **Dato en Tránsito (*In Motion*):** Viajando por la red o correos. Requiere protocolos seguros (TLS 1.3) e inspección de contenido en tiempo real.
3.  **Dato en Uso (*In Use*):** Procesado en memoria o visible en pantalla. Exige control de periféricos y marcas de agua digitales para garantizar la **Trazabilidad**.

---

### 3. Soberanía de Datos y Cumplimiento Legal

Desde la perspectiva del **Directorio**, la higiene de datos es el pilar de la **Debida Diligencia**. Bajo la **Ley 21.663**, la pérdida de datos sensibles no es solo un fallo técnico, sino una violación de la **Licencia para Operar**.

* **Residencia de Datos:** El Vigilante Estratégico debe conocer la jurisdicción física de los datos. En un conflicto legal, la ubicación del servidor determina la ley aplicable.
* **Derecho al Olvido y Portabilidad:** La arquitectura debe permitir la eliminación o migración eficiente de datos para cumplir con los estándares de privacidad modernos, evitando el ***SLE*** derivado de sanciones regulatorias masivas.

Los reportes de DLP (*Data Loss Prevention*, controles diseñados para detectar, bloquear y registrar la salida no autorizada de datos sensibles) no solo detienen la fuga: constituyen evidencia objetiva de debida diligencia y control efectivo ante la ANCI.

---

### 4. Blueprint 6: Matriz de Control de Fuga de Datos

!!! example "Canales y Controles DLP"
    El **Mando Medio** implementa estos "peajes" de control para asegurar la soberanía institucional:

    | Canal de Fuga | Método de Control | Nivel de Restricción |
    | :--- | :--- | :--- |
    | **Correo Electrónico** | Escaneo de *keywords* y adjuntos cifrados. | Alto (Bloqueo de PII/RUTs). |
    | **Almacenamiento Cloud** | **CASB** (*Cloud Access Security Broker*). | Crítico (Solo nubes corporativas). |
    | **IA Generativa** | Filtrado de *Prompts* y anonimización. | Alto (Prevención de fuga a modelos externos). |
    | **Endpoint / USB** | Bloqueo de puertos y monitoreo de portapapeles. | Crítico (Prohibición de extracción masiva). |

---

### 5. La Regla de Oro: Minimización de la Exposición Financiera

La forma más eficiente de reducir el ***ALE*** es eliminar los datos que no aportan valor operativo. 

* **Higiene:** Ejecutar políticas de retención y eliminación segura. Un dato borrado es un dato que no puede ser robado.
* **Ofuscación:** El uso de datos sintéticos o anonimización en entornos de prueba reduce la superficie de ataque sin afectar la agilidad del desarrollo.

!!! info "Definición de Industria: Dark Data (Datos Oscuros)"
    Gartner define los *Dark Data* como los activos de información que las organizaciones recopilan, procesan y almacenan durante sus actividades comerciales regulares, pero que **no utilizan para otros fines**.
    
    Son el equivalente digital a guardar periódicos viejos: ocupan espacio, cuestan dinero y, en caso de incendio (o hackeo), se convierten en combustible puro para la crisis legal.
    
!!! danger "Advertencia de Gobernanza: El Pasivo de los 'Datos Zombis'"
    En ciberseguridad, el dato más seguro es el que no existe.
    
    Mantener bases de datos de hace 10 años "por si acaso" no es una práctica de respaldo, es acumulacion de **riesgo tóxico**. Si esos datos antiguos (que ya no generan valor) son exfiltrados, la multa de la Ley 21.663 se aplica con el mismo rigor que si fueran datos actuales. **Si el dato no trabaja para el negocio, debe ser eliminado.**
    
---

### Conclusión: La Soberanía como Hábito

Un sistema seguro con datos desordenados es una bomba de tiempo. El ingeniero que implementa reglas de DLP y el gerente que clasifica la información están construyendo la verdadera soberanía institucional. Los datos son el alma de la organización; su higiene es el hábito que separa a las empresas resilientes de las negligentes.

Con este capítulo finalizamos el **Bloque 2: Arquitectura y Prevención**. Ahora que tenemos los muros (Zero Trust), las llaves (Identidad) y el tesoro protegido (Datos), es hora de enfrentar la realidad: **¿Qué pasa cuando el sistema falla?** Entramos al **Bloque 3: Gestión de Crisis**.

---

!!! abstract "Tesis del Capítulo"
    La seguridad del dato no es un candado; es un proceso de visibilidad y clasificación continua. Sin saber qué datos tienes y quién los mueve, no tienes soberanía, solo tienes la ilusión de control.

---
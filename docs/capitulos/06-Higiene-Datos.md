# CAPÍTULO 6: Higiene de Datos y Soberanía (DLP)
**(Protegiendo el Activo más Crítico)**

Si la Identidad (Capítulo 5) es el pasaporte que permite circular por la organización, el **Dato** es la mercancía valiosa que ese pasaporte intenta proteger. En la economía digital de 2026, los datos son a menudo descritos como "el nuevo petróleo", pero para el **Vigilante Estratégico**, los datos mal gestionados son más parecidos a los **desechos radiactivos**: son extremadamente útiles si se manejan bien, pero catastróficos si se filtran.

La higiene de datos no es solo un proceso de limpieza; es la capacidad técnica de asegurar que la información sensible no salga de la organización por canales no autorizados (**DLP - Data Loss Prevention**).

### 1. El Dilema de la Visibilidad: No puedes proteger lo que no conoces

El mayor riesgo para el **Mando Medio** es la "oscuridad de datos". Muchas organizaciones gastan millones en seguridad sin saber dónde están sus datos más críticos (Propiedad intelectual, datos de clientes, fórmulas, estrategias financieras).

La higiene de datos comienza con la **Clasificación**, un proceso que debe ser dictado por el negocio pero ejecutado por la técnica:
* **Datos Públicos:** Información de marketing, comunicados.
* **Datos de Uso Interno:** Memorándums, minutas de reuniones.
* **Datos Confidenciales:** Información financiera, datos personales de clientes (sujetos a la Ley 19.628).
* **Datos Secretos:** Propiedad intelectual, "Joyas de la Corona", claves maestras.

---

### 2. DLP: Los Tres Estados del Dato

Para el **Ingeniero**, la protección no es estática. El sistema de prevención de fuga de datos (DLP) debe actuar en los tres estados del ciclo de vida del dato:

1.  **Dato en Reposo (At Rest):** Datos almacenados en servidores, nubes o discos. La defensa aquí es el **Cifrado** y el control de acceso estricto.
2.  **Dato en Tránsito (In Motion):** Datos viajando por la red o correos electrónicos. La defensa es el uso de protocolos seguros (TLS/SSL) y la inspección de tráfico.
3.  **Dato en Uso (In Use):** Datos abiertos en la pantalla de un analista o procesados en memoria. La defensa es el control de periféricos (bloqueo de USB) y marcas de agua digitales.

---

### 3. Soberanía de Datos y Cumplimiento Legal

Desde la perspectiva del **Directorio**, la higiene de datos es una obligación de cumplimiento. Con la actualización de la normativa de protección de datos en Chile y el estándar GDPR en Europa, el **SLE (Impacto)** de una filtración no es solo la pérdida del dato, sino la **Pérdida de la Licencia Social**.

* **Derecho al Olvido y Portabilidad:** La arquitectura debe permitir borrar o mover datos si el cliente lo solicita.
* **Residencia de Datos:** ¿Dónde están físicamente nuestros datos? ¿En una nube en EE.UU., Europa o en suelo nacional? Esto define qué leyes aplican en caso de un conflicto legal.

---

### 4. Blueprint 6: Matriz de Control de Fuga de Datos

El **Mando Medio** debe implementar estos peajes de control para asegurar la higiene institucional:

| Canal de Fuga | Método de Control | Nivel de Restricción |
| :--- | :--- | :--- |
| **Correo Electrónico** | Escaneo de palabras clave y adjuntos cifrados. | Alto (Bloqueo de envío de tarjetas de crédito/RUTs). |
| **Almacenamiento Cloud** | CASB (Cloud Access Security Broker). | Medio (Solo nubes corporativas autorizadas). |
| **Dispositivos USB** | Bloqueo de puertos o cifrado obligatorio. | Crítico (Prohibición de extracción de bases de datos). |
| **IA Generativa** | Filtrado de Prompts (Ver Capítulo 1). | Alto (Evitar que datos sensibles entrenen modelos públicos). |

---

### 5. La Regla de Oro: Datos Mínimos Necesarios

La mejor forma de reducir el riesgo financiero (**ALE**) es simplemente no tener datos que no necesitamos. 
* **Higiene:** Eliminar datos antiguos (políticas de retención).
* **Ofuscación:** Si el equipo de desarrollo necesita probar una App, no debe usar la base de datos real; debe usar datos sintéticos o anonimizados.

---

### Conclusión para el "Vigilante Estratégico"

Un sistema seguro con datos sucios es una bomba de tiempo. El ingeniero que implementa reglas de DLP y el gerente que clasifica la información están construyendo la verdadera soberanía de la empresa. Los datos son el alma de la organización; su higiene es el hábito que separa a las empresas maduras de las negligentes.

Con este capítulo finalizamos el bloque de arquitectura. Ahora que tenemos los muros (Zero Trust), las llaves (Identidad) y el tesoro protegido (Datos), es hora de prepararnos para lo inevitable: **¿Qué pasa cuando, a pesar de todo, algo sale mal?** Entramos al Bloque 3: Gestión de Crisis.

---

> **Tesis del Capítulo:** La seguridad del dato no es un candado; es un proceso de visibilidad y clasificación. Si no sabes qué datos tienes y quién los mueve, no tienes soberanía, solo tienes suerte.

---
# CAPÍTULO 2: La Matemática del Riesgo
**(De las Matrices de Colores al Valor Monetario)**

En la mayoría de las salas de juntas, la ciberseguridad se presenta mediante una "Matriz de Calor": un cuadro de 5x5 lleno de celdas rojas, amarillas y verdes. El CISO apunta a un cuadro rojo y dice: *"Esto es de alta probabilidad y alto impacto"*. El Directorio asiente, pero nadie sabe realmente qué significa eso en términos de negocio.

El problema de las matrices de colores es que son **subjetivas y ambiguas**. Lo que para un ingeniero es "Probabilidad Alta", para un financiero puede ser "Riesgo Aceptable". Para ser un socio de negocio, debemos abandonar los colores y abrazar la única métrica que no requiere traducción: el **Dinero**.

### 1. El Fracaso de la Intuición: El "Efecto Kahneman"

Como exploramos en la nota metodológica, el cerebro humano (Sistema 1) es pésimo calculando riesgos de baja frecuencia pero gran impacto. Tendemos a sobreestimar amenazas mediáticas y a subestimar vulnerabilidades críticas pero "aburridas".

La matemática del riesgo existe para forzar al **Sistema 2** (el pensamiento analítico) a tomar el mando. No gestionamos "miedo"; gestionamos la **Exposición Financiera Anualizada (ALE)**.

---

### 2. La Ecuación Fundamental del Riesgo

Para que un ingeniero pueda hablar con un Director, debe dejar de hablar de "amenazas" y empezar a hablar de variables. La fórmula que rige este libro es:

$$ALE = SLE \times ARO$$

Donde:
* **SLE (Single Loss Expectancy):** ¿Cuánto nos cuesta que el incidente ocurra **una sola vez**? Aquí sumamos multas (Ley 21.663), pérdida de productividad, horas hombre de recuperación y daño reputacional.
* **ARO (Annualized Rate of Occurrence):** ¿Cuántas veces al año esperamos que esto ocurra?

#### El Rol del Ingeniero y el Mando Medio en la Variable ARO
Aquí es donde conectamos la técnica con la estrategia. ¿Cómo determinamos el ARO? No por intuición, sino por datos (Ver **Anexo E y F**):
* Si una vulnerabilidad está en el **Catálogo KEV de CISA**, el ARO es alto porque hay explotación activa.
* Si el **CVSS** es 9.8 pero el sistema está aislado, el ARO baja.
* Si el **EPSS** (Exploit Prediction Scoring System) es del 90%, el ARO es inminente.

---

### 3. Calculando el ROI de la Seguridad

Una de las preguntas más difíciles que recibe un mando medio es: *¿Por qué debo gastar $50,000 USD en este firewall?* La respuesta no es "para estar seguros", sino para **proteger el valor**.

El ROI de seguridad se calcula comparando el riesgo antes y después del control:

$$ROS = \frac{(ALE_{previo} - ALE_{post}) - CostoControl}{CostoControl}$$

Si la inversión en un control es menor que la reducción del riesgo que produce, la decisión es financieramente obligatoria. Si el costo del control supera el riesgo, el Directorio puede optar por **Aceptar el Riesgo**.

---

### 4. Blueprint 2: La Tabla de Decisión Financiera

En lugar de una matriz de colores, presente al Directorio una **Tabla de Exposición**. Esto permite que el Mando Medio sea el proveedor de datos y el Directorio sea el tomador de decisiones.

| Activo de Negocio | Amenaza Técnica (CVE) | Impacto (SLE) | Frecuencia (ARO) | Exposición (ALE) | Acción Recomendada |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Portal de Pagos** | Inyección SQL (Anexo F) | $500,000 USD | 0.5 (1 vez c/2 años) | $250,000 USD | **Mitigar:** Invertir $20k en WAF. |
| **Base de Datos** | Ransomware (Anexo E) | $1,200,000 USD | 0.1 (1 vez c/10 años)| $120,000 USD | **Transferir:** Seguro Ciber. |
| **Blog Corporativo** | Defacement | $2,000 USD | 2 (2 veces al año) | $4,000 USD | **Aceptar:** No requiere inversión. |

---

### 5. Las Cuatro Rutas del Riesgo

Una vez que tenemos la matemática, el Directorio solo tiene cuatro caminos:

1.  **Mitigar:** Aplicar controles técnicos (parches, MFA, segmentación) para bajar el ARO o el SLE.
2.  **Transferir:** Comprar una póliza de seguro ciber (traslada el SLE financiero a un tercero).
3.  **Evitar:** Dejar de realizar la actividad que genera el riesgo (ej. apagar un servicio obsoleto).
4.  **Aceptar:** Reconocer que el riesgo existe, que su ALE es bajo y que no vale la pena invertir en él.

### Conclusión para el "Vigilante Estratégico"

El ingeniero que domina esta matemática deja de ser un operario que pide parches y se convierte en un consultor que **protege el EBITDA**. Al usar estándares como CVSS y KEV para alimentar esta fórmula, usted le da al Directorio algo que no pueden ignorar: una justificación económica para la seguridad.

En el próximo capítulo, veremos cómo este análisis financiero se cruza con una nueva realidad inevitable: la **Ley Marco de Ciberseguridad** y las multas que cambian por completo el cálculo del SLE.

---
> **Tesis del Capítulo:** El riesgo no se elimina, se gestiona. Y para gestionarlo, primero hay que medirlo en la única unidad de medida que entiende la Alta Gerencia: el impacto económico.
---
# CAPÍTULO 10: Gobierno de la Crisis y el "Botón Rojo"
**(La Decisión Final en el Ojo de la Tormenta)**

Todo lo que hemos construido hasta ahora (la matemática del riesgo, la arquitectura Zero Trust y los planes de respuesta) tiene un solo objetivo: que en el momento en que el ataque sea crítico, la organización no actúe por pánico, sino por diseño. 

El **"Botón Rojo"** es una metáfora de la decisión más difícil que puede enfrentar un Directorio: desconectar los servicios *core*, apagar la operación o interrumpir la conectividad para contener un daño irreversible. En 2026, esta decisión no es técnica; es un acto de **Gobernanza de Alta Dirección**.

### 1. ¿Quién Presiona el Botón? El Comité de Crisis

Un error catastrófico en muchas organizaciones es dejar la decisión de "apagar el negocio" en manos de un **Ingeniero** de guardia. El ingeniero posee el conocimiento técnico, pero carece de la visión del impacto financiero y de la representación legal necesaria para tal acto.

La decisión del Botón Rojo debe ser tomada por el **Comité de Crisis**, liderado por el CEO o el Directorio, bajo la recomendación técnica del CISO. 

* **El Ingeniero:** Provee el diagnóstico objetivo (¿Qué vulnerabilidad se explota? ¿Cuál es el radio de expansión?).
* **El Mando Medio:** Provee el pronóstico operativo (¿Cuánto tardaremos en recuperar según el ***DRP***?).
* **El Directorio:** Decide el curso de acción basado en la supervivencia patrimonial del negocio.

---

### 2. La Lógica del Apagado: ¿Cuándo es correcto detenerse?

La decisión de presionar el Botón Rojo debe basarse en un umbral de dolor financiero y legal. Usando nuestra matemática del riesgo (Capítulo 2), el Directorio debe evaluar la siguiente desigualdad, no como un cálculo matemático exacto, sino como un **criterio de decisión soberana**:

$$Costo_{Operar} > Costo_{Incidente} \times Probabilidad_{Impacto \: Total}$$

Si mantener el sistema encendido permite que un *ransomware* cifre la totalidad de la infraestructura o que la exfiltración de datos active multas máximas de la **ANCI** (Ley 21.663), apagar preventivamente es la decisión financieramente más responsable y una acción de **debida diligencia**.

---

### 3. El Insumo Técnico: Datos sobre Instinto

Para que el Directorio decida, el equipo técnico debe entregar certidumbre mediante el **Flash Report (Anexo D)**. El **Ingeniero** debe informar basándose en la evidencia del ecosistema de seguridad:

* **Evidencia de Explotación:** Identificación de vulnerabilidades de alta destructividad (ej. catálogo **KEV**).
* **Estado de la Propiedad:** Confirmación de compromiso en cuentas con privilegios de administrador (***PAM***).
* **Eficacia de la Contención:** Reporte sobre el fallo de la microsegmentación y la inminencia del movimiento lateral.

---

### 4. Blueprint 10: Matriz de Decisión del Botón Rojo

| Escenario de Crisis | Hallazgo Técnico | Acción Recomendada | Quién Decide |
| :--- | :--- | :--- | :--- |
| **Ransomware en curso** | Encriptación activa de servidores de respaldo. | **Botón Rojo:** Desconexión total para salvar *backups*. | Directorio / CEO |
| **Exfiltración Masiva** | Tráfico inusual hacia IP externa identificada. | **Aislamiento Selectivo:** Cortar salida a Internet, mantener red interna. | CISO / Mando Medio |
| **DDoS (Denegación)** | Saturación de enlaces por *botnets*. | **Limpieza de Tráfico:** Activar peajes de seguridad *cloud*. No apagar. | Mando Medio |
| **Falla de Integridad (IA)** | Modelos financieros entregando datos falsos. | **Suspensión de Proceso:** Detener ejecución automática de la IA. | Gerente / CISO |

---

### 5. Responsabilidad Legal y debida diligencia

Bajo la **Ley 21.663**, el Directorio no puede delegar la responsabilidad de una crisis mayor. La decisión de apagar, o de seguir operando, quedará registrada en actas como evidencia de gobierno. 

* **Negligencia:** Si el Directorio decide NO apagar y el daño se multiplica de forma previsible.
* **debida diligencia:** Si el Directorio decide APAGAR basándose en un proceso documentado de ***IRP***, protegiendo la integridad de los datos y la licencia social de la empresa.

---

### Conclusión: El Vigilante en el Centro de la Tormenta

Presionar el Botón Rojo no es un acto de derrota; es un acto de control soberano. Es la demostración de que la organización prefiere el costo de una parada controlada que el caos de una destrucción sistémica. El ingeniero que entrega la evidencia y el director que toma la decisión son las dos caras de la **resiliencia operativa**.

En el próximo bloque, pasaremos de la crisis a la recuperación. Veremos cómo integrar la **Resiliencia** en el ADN organizacional y cómo la cultura post-incidente se convierte en nuestra mejor defensa futura.

---

!!! abstract "Tesis del Capítulo"
    El poder real en ciberseguridad no es saber cómo encender los sistemas, sino tener el criterio, los datos y el valor para saber cuándo apagarlos bajo los principios de la **debida diligencia**.

---
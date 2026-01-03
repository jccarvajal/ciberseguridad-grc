# CAPÍTULO 10: Gobierno de la Crisis y el "Botón Rojo"
**(La Decisión Final en el Ojo de la Tormenta)**

Todo lo que hemos construido hasta ahora —la matemática del riesgo, la arquitectura Zero Trust y los planes de respuesta— tiene un solo objetivo: que en el momento en que el ataque sea crítico, la organización no actúe por pánico, sino por diseño. 

El **"Botón Rojo"** es una metáfora de la decisión más difícil que puede enfrentar un Directorio: desconectar los servicios core, apagar la operación o interrumpir la conectividad nacional para contener un daño irreversible. En 2026, esta decisión no es técnica; es un acto de **Gobernanza de Alta Dirección**.

### 1. ¿Quién Presiona el Botón? El Comité de Crisis

Un error catastrófico en muchas organizaciones es dejar la decisión de "apagar el negocio" en manos de un **Ingeniero** de guardia. El ingeniero tiene el conocimiento técnico, pero no tiene la visión del impacto financiero ni la responsabilidad legal (Anexo G).

La decisión del Botón Rojo debe ser tomada por el **Comité de Crisis**, liderado por el CEO o el Directorio, bajo la recomendación del CISO. 
* **El Ingeniero:** Provee el diagnóstico (¿Qué CVE se está explotando? ¿Cuál es el radio de expansión?).
* **El Mando Medio:** Provee el pronóstico (¿Cuánto tardaremos en recuperar según el DRP?).
* **El Directorio:** Decide el curso de acción basado en la supervivencia del negocio.

---

### 2. La Lógica del Apagado: ¿Cuándo es correcto detenerse?

La decisión de presionar el Botón Rojo debe basarse en un umbral de dolor financiero y legal. Usando nuestra matemática del riesgo (Capítulo 2), el Directorio debe evaluar:

$$Costo_{Operar} > Costo_{Incidente} \times Probabilidad_{Impacto \: Total}$$

Si mantener el sistema encendido permite que un Ransomware cifre el 100% de la infraestructura o que la exfiltración de datos sensibles active multas máximas de la **ANCI** (Ley 21.663), apagar preventivamente es la decisión financieramente más responsable.

### 3. El Insumo Técnico: Datos sobre Instinto

Para que el Directorio decida, el equipo técnico debe entregar certidumbre mediante el **Flash Report (Anexo D)**. No basta con decir "estamos bajo ataque". El **Ingeniero** debe informar basándose en el **Ecosistema Global (Anexo E)**:

* **Evidencia de Explotación:** "Es una vulnerabilidad del catálogo **KEV**, altamente destructiva".
* **Estado de la Propiedad:** "El atacante ya tiene privilegios de Administrador de Dominio (PAM comprometido)".
* **Eficacia de la Contención:** "La microsegmentación ha fallado; el movimiento lateral es inminente".

---

### 4. Blueprint 10: Matriz de Decisión del Botón Rojo

El **Mando Medio** debe guiar al Comité utilizando estos escenarios predefinidos:

| Escenario de Crisis | Hallazgo Técnico (Anexo F) | Acción Recomendada | Quién Decide |
| :--- | :--- | :--- | :--- |
| **Ataque de Ransomware en curso** | Encriptación activa de servidores de respaldo. | **Presionar Botón Rojo:** Desconexión total de la red para salvar backups. | Directorio / CEO |
| **Exfiltración de Datos Masiva** | Tráfico inusual hacia IP externa identificada. | **Aislamiento Selectivo:** Cortar salida a Internet, mantener red interna. | CISO / Mando Medio |
| **DDoS (Denegación de Servicio)** | Saturación de enlaces por botnets. | **Limpieza de Tráfico:** Activar peajes de seguridad cloud. No apagar. | Mando Medio |
| **Falla de Integridad (IA)** | Modelos de decisión financiera dando datos falsos. | **Suspensión de Proceso:** Detener ejecución automática de la IA. | Gerente de Área / CISO |

---

### 5. Responsabilidad Legal y Diligencia Debida

Bajo la **Ley 21.663**, el Directorio no puede delegar la responsabilidad de una crisis mayor. La decisión de apagar (o de seguir operando a pesar del riesgo) quedará registrada en las actas. 
* **Si el Directorio decide NO apagar** y el daño se multiplica, la ANCI puede calificar la acción como **Negligencia**.
* **Si el Directorio decide APAGAR** basándose en un proceso documentado de IRP (Anexo H), está ejerciendo su **Diligencia Debida**, protegiendo el patrimonio y la licencia social de la empresa.

### Conclusión para el "Vigilante Estratégico"

Presionar el Botón Rojo no es un acto de derrota; es un acto de control. Es la demostración de que la organización prefiere el costo de una parada controlada que el caos de una destrucción sistémica. El ingeniero que entrega la evidencia y el director que toma la decisión son las dos caras de la misma moneda: la **Resiliencia Operativa**.

Con este capítulo cerramos el bloque de gestión de crisis. Ahora que sabemos cómo operar durante el fuego, es hora de ver cómo nos levantamos. Entramos al Bloque 4: Resiliencia y Futuro.

---
> **Tesis del Capítulo:** El poder real en ciberseguridad no es saber cómo encender los sistemas, sino tener el criterio, los datos y el valor para saber cuándo apagarlos.
---
# CAPÍTULO 3: Marcos, Leyes y Madurez
**(El Escudo Legal del Directorio)**

Si el Capítulo 2 nos enseñó la matemática del riesgo, el Capítulo 3 nos enseña la **gravedad del incumplimiento**. En 2026, la ciberseguridad ha dejado de ser una "buena práctica" para convertirse en una obligación legal ineludible. 

Para el Directorio, los marcos legales son su seguro de responsabilidad. Para el Ingeniero y el Mando Medio, son los planos de construcción que dictan qué controles son obligatorios y cómo deben ser reportados.

### 1. La Ley Marco de Ciberseguridad (Ley 21.663)

La entrada en vigencia de la **Ley 21.663** en Chile cambió las reglas del juego. Ya no se trata solo de proteger datos; se trata de proteger la continuidad de la nación.

* **ANCI (Agencia Nacional de Ciberseguridad):** La nueva autoridad con facultades fiscalizadoras y sancionatorias.
* **Servicios Esenciales e Infraestructura Crítica:** Si su organización pertenece a estos sectores, el estándar de cuidado exigido es máximo.
* **El impacto en el SLE:** Recuerde nuestra fórmula del Capítulo anterior. La Ley 21.663 introduce multas de hasta **40.000 UTM**. 
    $$SLE_{nuevo} = SLE_{operativo} + Multa_{ANCI} + Costo_{Litigación}$$
    Esta nueva variable financiera hace que riesgos que antes eran "aceptables" ahora sean críticos.

### 2. Responsabilidad de la Alta Dirección: "Diligencia Debida"

Bajo la nueva normativa, los directores y gerentes tienen la obligación de implementar medidas de seguridad. Ya no pueden alegar ignorancia técnica. La **Diligencia Debida** se prueba mediante la existencia de una estructura de reporte clara:

* **El Directorio** es responsable de la estrategia y los recursos.
* **El Mando Medio** es responsable de la ejecución y el cumplimiento de los niveles de servicio (SLAs) definidos en el **Anexo F**.
* **El Ingeniero** es responsable de la detección técnica y de alimentar el ecosistema de inteligencia del **Anexo E**.

### 3. El Estándar Global: NIST CSF 2.0

Para no reinventar la rueda, este libro se alinea con el **NIST Cybersecurity Framework 2.0**. La gran novedad de esta versión es la función **GOVERN (Gobernar)**, que se coloca al centro de todo el ciclo:

1.  **Gobernar:** Definir políticas, roles (Anexo A) y apetito de riesgo.
2.  **Identificar:** Conocer nuestros activos y vulnerabilidades (Anexo F).
3.  **Proteger:** Implementar salvaguardas (Cifrado, IAM, Zero Trust).
4.  **Detectar:** Monitorear anomalías en tiempo real.
5.  **Responder:** Activar el equipo CSIRT (Anexo G) e IRP (Anexo H).
6.  **Recuperar:** Volver a la normalidad mediante el DRP (Anexo I).

---

### 4. Blueprint 3: El Mapa de Madurez Institucional

¿Cómo saber si estamos cumpliendo? El Mando Medio debe utilizar este mapa para reportar el avance al Directorio:

| Nivel | Estado | Características | Percepción de la ANCI |
| :--- | :--- | :--- | :--- |
| **1. Reactivo** | "Apaga-fuegos" | No hay procesos definidos. Se depende de heroísmos individuales. | **Negligencia** (Riesgo de multas máximas). |
| **2. Repetible** | En Proceso | Se siguen algunos estándares (NIST), pero la documentación es débil. | **Esfuerzo Insuficiente**. |
| **3. Definido** | Cumplimiento | Procesos documentados y alineados con la Ley 21.663. Reportes mensuales. | **Cumplimiento Base**. |
| **4. Gestionado** | Resiliente | Se miden KPIs financieros (ALE/ROI). Mejora continua basada en datos. | **Diligencia Debida**. |
| **5. Optimizado** | Estratégico | La seguridad habilita nuevos negocios. Arquitectura Zero Trust completa. | **Referente de Industria**. |

---

### 5. La "Prueba del Ácido" para el Mando Medio

Cuando la ANCI o un auditor externo llegue a su puerta, no preguntará si tiene el mejor firewall. Preguntará:
1.  ¿Tiene un registro actualizado de sus activos y sus CVEs críticos? (**Anexo F**)
2.  ¿Puede demostrar que el Directorio fue informado de los riesgos financieros? (**Anexo D**)
3.  ¿Tiene un plan de respuesta probado en el último año? (**Anexo H**)

### Conclusión para el "Vigilante Estratégico"

El cumplimiento legal no es un "Check-box" de auditoría; es el **blindaje jurídico** de la organización. El ingeniero que documenta correctamente un parche y el mando medio que reporta un riesgo no solo están protegiendo servidores; están protegiendo la libertad y el patrimonio de los directivos.

En el próximo capítulo, entraremos en la arquitectura que hace posible este cumplimiento: el modelo de **Confianza Cero (Zero Trust)**, el estándar de oro de la resiliencia moderna.

---
> **Tesis del Capítulo:** En la era de la ANCI, la ciberseguridad es ley. La madurez no es una opción técnica, sino un requisito de permanencia en el mercado.
---
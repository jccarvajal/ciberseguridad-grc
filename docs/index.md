# Ciberseguridad Orientada a Resultados
## Arquitectura de Resiliencia y Gobernanza para la Tríada Estratégica

**Versión 1.1 (Enero 2026)**

**Autor:** [Juan Carlos Carvajal](https://www.jccarvajal.com/)

<img src="assets/images/portada-ciber.png" alt="Portada del Libro - Ciberseguridad Orientada a Resultados" width="500">

---

## Descripción del Proyecto

Esta obra no es un libro técnico tradicional de TI; es una **documentación técnica y estratégica** diseñada para cerrar la brecha entre la complejidad de las amenazas digitales y la toma de decisiones en los niveles de alta gerencia y directorios.

Mientras el mercado se satura con la venta de herramientas y software de defensa, este repositorio se enfoca en el **criterio de arquitectura y gestión** necesario para construir organizaciones verdaderamente resilientes.

El objetivo es proporcionar un **Marco de GRC (Gobernanza, Riesgo y Cumplimiento)** que permita a líderes estratégicos:

1.  **Decidir** inversiones de seguridad basadas en el riesgo financiero y el valor de negocio (ALE/ROI).
2.  **Diseñar** infraestructuras robustas bajo el paradigma de Confianza Cero (*Zero Trust*).
3.  **Gobernar** la crisis mediante protocolos de respuesta y recuperación que aseguren la continuidad ante lo inevitable.

---

## Tesis Central: Resiliencia e Integridad

La premisa fundamental de este libro es que la seguridad absoluta es una imposibilidad técnica. Por lo tanto, la estrategia debe evolucionar desde la "protección perimetral" hacia la **Antifragilidad Operativa**. 

Este repositorio propone el principio de **"Asumir la Brecha" (*Assume Breach*)**: operamos bajo la certeza de que el sistema será vulnerado. La verdadera ventaja competitiva reside en la capacidad de detectar, contener y recuperarse antes de que el incidente comprometa la licencia social o la viabilidad financiera de la institución.

---

## Estructura de la Documentación

El contenido está organizado modularmente siguiendo el ciclo de vida del riesgo y la anatomía de una crisis.

### Introducción y Preliminares
Marco conceptual y bases metodológicas.

* [Nota al Lector](./nota-al-lector.md)
  *Filosofía del manual y reglas de compromiso.*
* [Nota Metodológica](./nota-metodologica.md)
  *Alineación con NIST 2.0, ISO 27001 y Ley 21.663.*
* [Prólogo Ejecutivo](./prologo.md)
  *El cambio de paradigma: de gasto de TI a riesgo de Directorio.*
* [Ideas Centrales](./ideas-centrales.md)
  *Resumen ejecutivo: si solo tienes 5 minutos, lee esto.*

### Bloque 1: Fundamentos y Estrategia (Capítulos 1 a 3)
Estableciendo el lenguaje del negocio y la gobernanza.

* [Capítulo 01: CISO Socio de Negocio](./capitulos/01-CISO-Socio-Negocio.md)
  *Del "No" técnico al "Cómo" estratégico.*
* [Capítulo 02: Matemática del Riesgo](./capitulos/02-Riesgo-Financiero.md)
  *Cuantificación del riesgo: ALE, RTO y el retorno de inversión en seguridad.*
* [Capítulo 03: Marcos y Madurez Legal](./capitulos/03-Marcos-Madurez.md)
  *Cumplimiento regulatorio y responsabilidad legal de la alta dirección.*

### Bloque 2: Arquitectura y Prevención (Capítulos 4 a 6)
Diseño de la fundación técnica bajo el modelo soberano.

* [Capítulo 04: Zero Trust (Confianza Cero)](./capitulos/04-Zero-Trust.md)
  *Arquitectura de Confianza Cero y segmentación lógica.*
* [Capítulo 05: Identidad (IAM)](./capitulos/05-Identidad-IAM.md)
  *La identidad como el nuevo perímetro de seguridad.*
* [Capítulo 06: Higiene de Datos (DLP)](./capitulos/06-Higiene-Datos.md)
  *Estrategias de DLP y protección del activo más crítico.*

### Bloque 3: Gestión de Crisis (Capítulos 7 a 10)
El manual de guerra: Operación y toma de decisiones bajo presión.

* [Capítulo 07: Flujo del Incidente (IRP)](./capitulos/07-Flujo-IRP.md)
  *El Plan de Respuesta a Incidentes: Contención, Erradicación y Recuperación.*
* [Capítulo 08: Automatización y SOAR](./capitulos/08-Automatizacion-SOAR.md)
  *Uso de telemetría y respuesta orquestada ante ataques a gran escala.*
* [Capítulo 09: Comunicación de Crisis](./capitulos/09-Comunicacion-Crisis.md)
  *Gestión de la reputación institucional y comunicación con stakeholders.*
* [Capítulo 10: Gobierno de Crisis y Botón Rojo](./capitulos/10-Gobierno-Crisis.md)
  *Protocolos de mando y la autoridad del "Botón Rojo".*

### Bloque 4: Resiliencia y Proyección (Capítulos 11 a 13)
Aprendizaje sistémico y el futuro de la amenaza.

* [Capítulo 11: Integración de la Resiliencia](./capitulos/11-Integracion-Resiliencia.md)
  *Sinergia entre IRP, DRP y BCP basada en el impacto (BIA).*
* [Capítulo 12: Cultura Post-Incidente](./capitulos/12-Cultura-Post-Incidente.md)
  *Análisis forense, lecciones aprendidas y el ciclo de mejora continua.*
* [Capítulo 13: El Futuro Inevitable](./capitulos/13-Futuro-Inevitable.md)
  *Ciberseguridad Agéntica e IA Adversaria.*

---

## Conclusión y Cierre
* [Epílogo: La Dimensión Humana](./epilogo.md)
  *El mandato ético del Vigilante Estratégico.*

---

## Anexos Operativos (Biblioteca del Arquitecto)

### Control y Medición
* [Anexo A: Matriz RACI](./anexos/A-Matriz-RACI.md)
  *Accountability organizacional.*
* [Anexo B: Tablero de Métricas](./anexos/B-Metricas.md)
  *KPIs y KRIs para el reporte ejecutivo.*
* [Anexo C: Checklist Zero Trust](./anexos/C-ZeroTrust.md)
  *Rúbrica de madurez técnica.*

### Comunicación e Inteligencia
* [Anexo D: Guía de Reporting Ejecutivo](./anexos/D-Reporting.md)
  *Traducción de bits a dólares.*
* [Anexo E: Ecosistema Global de Inteligencia](./anexos/E-Ecosistema.md)
  *Fuentes CVE, KEV y NVD.*
* [Anexo F: Gestión de Vulnerabilidades](./anexos/F-Vulnerabilidades.md)
  *Ciclos de parcheo y SLAs.*

### Respuesta y Supervivencia
* [Anexo G: Estructura CSIRT](./anexos/G-CSIRT.md)
  *Roles y cadena de mando.*
* [Anexo H: Plan IRP](./anexos/H-Plan-IRP.md)
  *Respuesta táctica a incidentes.*
* [Anexo I: Plan DRP](./anexos/I-Plan-DRP.md)
  *Recuperación técnica de desastres.*
* [Anexo J: Plan BCP](./anexos/J-Plan-BCP.md)
  *Continuidad del negocio y BIA.*

### Cultura y Legal
* [Anexo K: Patrones de Fracaso](./anexos/K-Fracaso.md)
  *Antifragilidad operativa.*
* [Anexo L: Cumplimiento Normativo y Riesgo de Terceros](./anexos/L-Cumplimiento.md)
  *Hoja de ruta legal y gestión de proveedores.*
* [Anexo M: Protocolo de Entrenamiento y Simulación](./anexos/M-Entrenamiento.md) 
  *Ingeniería del Factor Humano y "Human Firewall"*

## Referencias y Fundamento
* [Glosario](./referencias/Glosario.md)
  *Diccionario Técnico-Negocio.*
* [Bibliografia](./referencias/Bibliografia.md)
  *Lecturas Clave para el Arquitecto de Resiliencia y el Vigilante Estratégico.*

---

## Changelog
* **v1.1 (Enero 2026):** Actualización "Consolidación Legal". Integración de Anexos K (Anti-patrones) y L (Cumplimiento/Terceros), y formalización de revisión adversarial.
* **v1.0 (Enero 2026):** Lanzamiento oficial. Consolidación del marco GRC, publicación de los 13 capítulos y el kit base de anexos operativos.
* Ver [Historial Completo](./changelog.md).

## Sugerencias y Mejoras
Este es un documento vivo. Si encuentras una errata o tienes una sugerencia de mejora, puedes reportarla directamente en el [Repositorio de GitHub](https://github.com/jccarvajal/Ciberseguridad-GRC).

## Licencia
El contenido se distribuye bajo licencia **CC BY-NC-ND 4.0**.
Se autoriza su uso educativo y de referencia profesional. No se permite la modificación ni el uso comercial sin autorización expresa del autor.
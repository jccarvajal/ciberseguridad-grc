# ANEXO K: Patrones de Fracaso (Anti-Patrones)
**(Cómo sabotear su propia seguridad sin darse cuenta)**

### 1. ¿Qué es un Anti-Patrón?
Un anti-patrón es una respuesta común a un problema recurrente que suele ser ineficaz y contraproducente. Son "malas prácticas" disfrazadas de sentido común.

Si usted identifica tres o más de estos patrones en su organización, la probabilidad de sufrir un incidente catastrófico en los próximos 12 meses es **Alta**.

---

### CATEGORÍA A: CULTURA Y GOBERNANZA

#### 1. "El Héroe Solitario" (Bus Factor = 1)
* **El Síntoma:** Solo hay una persona ("Juan") que sabe cómo funcionan los backups, las claves del firewall y la configuración del Directorio Activo. Si Juan se enferma o se va de vacaciones, el departamento de TI tiembla.
* **Por qué falla:** Los héroes no escalan. Y cuando el héroe se va (o es sobornado/extorsionado), la organización colapsa.
* **El Antídoto:** Documentación obligatoria y rotación de roles. Nadie es indispensable.

#### 2. "Cumplimiento de Papel" (Paper Shield)
* **El Síntoma:** La organización se obsesiona con pasar la auditoría ISO/NIST una vez al año. Pasan las semanas previas llenando planillas Excel y generando evidencias falsas o apresuradas. El día después de la auditoría, todo vuelve al caos.
* **Por qué falla:** Los hackers no auditan papeles; explotan vulnerabilidades técnicas. Estar certificado no significa estar seguro (ver Capítulo 3).
* **El Antídoto:** Seguridad continua, no basada en fechas de auditoría.

#### 3. "Seguridad por Oscuridad"
* **El Síntoma:** *"No documentemos la red para que los hackers no sepan cómo entrar"*. O *"Cambiemos el puerto RDP del 3389 al 3390 para despistar"*.
* **Por qué falla:** Los escáneres automáticos de los atacantes encuentran puertos abiertos en milisegundos. La oscuridad no es una defensa, es una negligencia que impide que su propio equipo entienda la red.
* **El Antídoto:** Defensa en profundidad. Asuma que el atacante tiene el mapa de su red.

---

### CATEGORÍA B: ARQUITECTURA Y TECNOLOGÍA

#### 4. "El M&M" (Duro por fuera, blando por dentro)
* **El Síntoma:** Una inversión millonaria en Firewalls perimetrales, pero una red interna "plana". Una vez que pasas la puerta, puedes acceder desde la impresora hasta la Base de Datos sin restricciones.
* **Por qué falla:** Es el escenario ideal para el Ransomware (como *Akira*). Una sola PC infectada cifra toda la organización en minutos por falta de segmentación interna.
* **El Antídoto:** Zero Trust y Micro-segmentación (VLANs aisladas con ACLs estrictas).

#### 5. "El Backup Conectado" (La Ilusión de Respaldo)
* **El Síntoma:** Los backups se realizan correctamente, pero el servidor de backups está unido al Dominio y los discos de respaldo se ven como una unidad de red (Z:).
* **Por qué falla:** El ransomware moderno escanea la red, encuentra el servidor de backups, usa las credenciales de administrador robadas y cifra (o borra) los backups *antes* de cifrar los servidores de producción.
* **El Antídoto:** Inmutabilidad y Air-Gap (Backups fuera de línea o con candado de escritura).

#### 6. "Excepciones Permanentes"
* **El Síntoma:** *"Desactiva el antivirus en este servidor porque pone lenta la base de datos"*. Esa excepción temporal se olvida y queda activa por 5 años.
* **Por qué falla:** Los atacantes buscan activamente estas "islas de inseguridad". Un servidor sin parches o sin antivirus es la cabeza de playa perfecta.
* **El Antídoto:** Revisión trimestral de todas las excepciones de seguridad. Las excepciones deben tener fecha de caducidad.

---

### CATEGORÍA C: OPERACIÓN Y PERSONAS

#### 7. "Fatiga de Alertas" (El Niño que gritó Lobo)
* **El Síntoma:** El equipo del SOC recibe 10,000 correos de alerta al día. Nadie los lee. Se crean reglas de correo para enviarlos a una carpeta de "Spam".
* **Por qué falla:** Entre esas 10,000 alertas irrelevantes, está la única alerta real de intrusión que nadie vio.
* **El Antídoto:** Afinar las herramientas (Tuning). Si una alerta no requiere acción, no debe ser una alerta. Automatización (SOAR).

#### 8. "Shadow IT" (TI en las Sombras)
* **El Síntoma:** El departamento de Marketing contrata un servidor en AWS con tarjeta de crédito corporativa porque TI es "muy lento". Ese servidor no tiene parches ni MFA.
* **Por qué falla:** No se puede proteger lo que no se sabe que existe. Ese servidor olvidado es la puerta trasera a la red corporativa.
* **El Antídoto:** El CISO como facilitador (Socio de Negocio), no como bloqueador. Descubrimiento de activos continuo.

#### 9. "Capacitación Anual Aburrida"
* **El Síntoma:** Una vez al año, se obliga a los empleados a ver un video de 30 minutos sobre seguridad y responder un test obvio.
* **Por qué falla:** No cambia el comportamiento. El empleado lo ve como un trámite burocrático. Al día siguiente, abre el PDF malicioso.
* **El Antídoto:** Simulaciones de Phishing reales y frecuentes. Gamificación. Cultura de "no castigo" por reportar errores.

---

### AUTOEVALUACIÓN RÁPIDA (Bingo del Desastre)

Si marca **SÍ** en 3 o más casillas, su organización está en peligro inminente:

1.  [ ] ¿Las contraseñas de Administrador son conocidas por más de 3 personas y no se rotan?
2.  [ ] ¿Los backups se pueden borrar desde la misma red de Windows?
3.  [ ] ¿Existe una red "plana" donde las estaciones de trabajo ven a los servidores?
4.  [ ] ¿Hay servidores "Legacy" (Windows 2008/2012) sin soporte conectados a Internet?
5.  [ ] ¿El CISO se entera de los nuevos proyectos el día del lanzamiento?
6.  [ ] ¿Creemos que el Antivirus tradicional es suficiente defensa?

# 1. Functional Requirements (FRs) - Requerimientos Funcionales

## funciones críticas que UrbanAlert

 **Reporte de Incidentes en Tiempo Real**: El sistema debe permitir al usuario enviar una alerta de emergencia (incendio, crimen, accidente) presionando un botón de pánico, el cual debe capturar automáticamente el tipo de incidente y la hora del suceso.

**Geolocalización Automática**: Al enviar un reporte, el sistema debe capturar y enviar las coordenadas GPS exactas del dispositivo del usuario a los servicios de emergencia y a otros usuarios cercanos.

**Notificaciones Push:** La aplicación debe ser capaz de recibir y mostrar alertas críticas enviadas por las autoridades o por otros usuarios dentro de un radio de 2 kilómetros de la ubicación actual.

**Validación de Evidencia Multimedia:** El sistema debe permitir al usuario adjuntar una fotografía o un video corto (máximo 15 segundos) al reporte del incidente para proveer contexto a las autoridades.

**Gestión de Estado de Usuario (Check-in de Seguridad):** El sistema debe permitir al usuario marcarse como "A salvo" durante un desastre natural o evento crítico, actualizando su estado en la base de datos central visible para sus contactos de emergencia.

2. Non-Functional Requirements (NFRs) - Atributos de Calidad

Basado en la norma ISO 25010. Hemos seleccionado 3 atributos clave. Nota que para tu objetivo final, incluí "Eficiencia de Desempeño" (aunque no estaba en tu texto pegado, es necesario para tu justificación de velocidad vs seguridad).
A. Fiabilidad (Subcaracterística: Disponibilidad)

Para una app de emergencias, es vital que siempre funcione.

    Definición: Capacidad del sistema de estar operativo y accesible para su uso cuando se requiere.

    Medición (Bien escrito): "El sistema UrbanAlert debe garantizar una disponibilidad del 99.9% anual, permitiendo un tiempo máximo de inactividad no planificada de 8.7 horas al año, asegurando que los usuarios puedan enviar alertas en cualquier momento crítico."

B. Seguridad (Subcaracterística: Autenticidad)

Es importante saber que quien envía la alerta es una persona real para evitar bromas, pero sin entorpecer el uso.

    Definición: Capacidad de un producto para demostrar que la identidad de un sujeto o recurso es la que se afirma.

    Medición (Bien escrito): "El proceso de autenticación de usuario al iniciar sesión o reactivar la app no debe exceder los 2 segundos mediante el uso de biometría (huella/rostro) o token persistente, garantizando que solo el usuario registrado pueda emitir alertas sin retrasar el acceso en una emergencia."

C. Eficiencia de Desempeño (Subcaracterística: Comportamiento Temporal / Velocidad)


    Definición: Capacidad del producto para proporcionar tiempos de respuesta y procesamiento apropiados bajo condiciones determinadas.

    Medición (Bien escrito): "El tiempo de latencia transcurrido entre que el usuario presiona el botón de 'Enviar Alerta' y la confirmación de recepción en el servidor central no debe exceder los 300ms (milisegundos) bajo condiciones de red 4G/5G, para asegurar una respuesta inmediata de las autoridades."

3. Conflict of Interest (Conflicto de Interés)

### Velocidad sobre Seguridad estricta.

Justificación: Prioridad de la Velocidad (Eficiencia) sobre la Seguridad Estricta

Para el equipo de desarrollo de UrbanAlert, el atributo de calidad más crítico es la Eficiencia de Desempeño (Velocidad), priorizándola incluso sobre niveles extremos de Seguridad.

 E n una situación de riesgo vital (como un asalto, secuestro o desastre natural), cada segundo cuenta. Si implementáramos capas de seguridad excesivas (como autenticación de dos factores por SMS o contraseñas complejas cada vez que se abre la app) para maximizar la "Confidencialidad" o "Integridad", podríamos causar un retraso fatal. Un usuario bajo estrés extremo necesita que la aplicación responda instantáneamente (en menos de 300ms). Por lo tanto, aceptamos el riesgo de una seguridad ligeramente más relajada (ej. sesiones abiertas por más tiempo o autenticación biométrica rápida) a cambio de garantizar que la alerta se envíe lo más rápido posible. La vida humana depende de la velocidad de reacción del sistema, no de qué tan encriptado esté el reporte en ese preciso instante.
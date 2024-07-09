# Visor de Eventos de Windows en S.I.

El Visor de Eventos de Windows es una herramienta poderosa y versátil que puede ser extremadamente útil en eventos de seguridad informática. Aquí te explico en qué puede ayudarte y cómo usarlo eficazmente:

### En qué puede ser útil

1. **Detección de Actividades Sospechosas**:
   - **Accesos no autorizados**: Puedes rastrear intentos de inicio de sesión fallidos y exitosos.
   - **Cambios en configuraciones**: Detecta modificaciones en la configuración del sistema que puedan indicar un compromiso.
   - **Ejecución de programas**: Identifica la ejecución de aplicaciones no autorizadas o sospechosas.

2. **Auditoría de Sistemas**:
   - **Rastreo de actividades de usuario**: Monitorea las acciones realizadas por los usuarios en el sistema.
   - **Auditoría de cambios en archivos y directorios**: Verifica quién hizo cambios en archivos críticos y cuándo.

3. **Investigación Post-Incidente**:
   - **Recolección de evidencias**: Proporciona un registro detallado de eventos que pueden ser usados para reconstruir un incidente de seguridad.
   - **Análisis forense**: Facilita el análisis forense digital al proporcionar información detallada sobre eventos pasados.

4. **Cumplimiento Normativo**:
   - **Registros de auditoría**: Ayuda a mantener registros de auditoría necesarios para cumplir con normativas de seguridad y privacidad.

### Cómo usarlo eficazmente

1. **Acceso al Visor de Eventos**:
   - Abre el Visor de Eventos presionando `Win + R`, escribiendo `eventvwr` y presionando Enter.
   - Alternativamente, ve a `Panel de control > Herramientas administrativas > Visor de eventos`.

2. **Navegación y Filtrado de Eventos**:
   - Navega por las diferentes categorías de registros en el panel izquierdo, como `Aplicación`, `Seguridad`, `Sistema`, y `Registros de eventos de Windows`.
   - Filtra eventos para centrarse en información relevante usando el menú contextual de cada categoría (`Clic derecho > Filtrar registro actual`).

3. **Tipos de Registros Clave en Seguridad**:
   - **Seguridad**: Rastrea eventos relacionados con la auditoría de seguridad, como inicios de sesión y accesos a recursos.
   - **Sistema**: Contiene eventos generados por los componentes del sistema operativo, como errores y avisos.
   - **Aplicación**: Incluye eventos registrados por aplicaciones instaladas.

4. **Eventos Específicos a Monitorear**:
   - **4624**: Inicio de sesión exitoso.
   - **4625**: Intento de inicio de sesión fallido.
   - **4648**: Inicio de sesión con credenciales explícitas.
   - **4672**: Privilegios especiales asignados a un nuevo inicio de sesión.
   - **4688**: Creación de un nuevo proceso.
   - **4700**: Un trabajo programado se ha activado.
   - **4720**: Creación de una nueva cuenta de usuario.

5. **Configuración de Auditoría Avanzada**:
   - Para un monitoreo más detallado, puedes configurar políticas de auditoría avanzadas a través de `gpedit.msc` (`Configuración del equipo > Configuración de Windows > Configuración de seguridad > Políticas locales > Política de auditoría`).

6. **Exportación y Análisis de Datos**:
   - Exporta los registros para análisis detallado en herramientas especializadas o para su revisión en equipos fuera de la red afectada (`Clic derecho en la categoría > Guardar eventos como`).

### Ejemplo Práctico

Imagina que detectas un inicio de sesión sospechoso en uno de tus servidores. Usando el Visor de Eventos, puedes:

1. **Buscar el evento 4624** en la categoría de seguridad para confirmar el inicio de sesión.
2. **Filtrar por fecha y hora** para limitar los resultados al período de interés.
3. **Examinar detalles del evento** para identificar el origen del intento de inicio de sesión (dirección IP, nombre de usuario, etc.).
4. **Correlacionar con otros eventos** (como creación de procesos o cambios en el sistema) para identificar cualquier actividad maliciosa adicional.

Utilizando estas capacidades, el Visor de Eventos se convierte en una herramienta esencial para la detección, análisis y respuesta a incidentes de seguridad informática.

---

## Otras herramientas

Además del Visor de Eventos, Windows incluye varias herramientas nativas que pueden ser útiles en un evento de seguridad informática. A continuación, se describen algunas de las herramientas más importantes y cómo pueden ser utilizadas:

### 1. **Administrador de Tareas (Task Manager)**
   - **Monitorización de procesos**: Permite ver y gestionar los procesos y servicios en ejecución.
   - **Rendimiento del sistema**: Proporciona información sobre el uso de CPU, memoria, disco y red.
   - **Usuarios activos**: Muestra qué usuarios están actualmente conectados al sistema.
   - **Inicio de aplicaciones**: Revisa y gestiona los programas que se inician con el sistema.

### 2. **PowerShell**
   - **Automatización de tareas**: Facilita la ejecución de scripts para automatizar la recolección de datos y la respuesta a incidentes.
   - **Análisis de registros**: Permite extraer y analizar datos de registros y otros archivos.
   - **Administración remota**: Proporciona capacidades para administrar y ejecutar comandos en equipos remotos.
   - **Comandos útiles**: `Get-EventLog`, `Get-Process`, `Get-Service`, `Get-WinEvent`.

### 3. **Monitor de Recursos (Resource Monitor)**
   - **Detección de actividad sospechosa**: Proporciona una vista detallada de la actividad del sistema, incluyendo el uso de CPU, disco, red y memoria.
   - **Monitorización de redes**: Permite ver qué procesos están utilizando la red y qué conexiones están abiertas.
   - **Identificación de cuellos de botella**: Ayuda a identificar qué recursos están bajo alta demanda.

### 4. **Registro de Windows (Windows Registry)**
   - **Revisión de configuraciones**: Permite revisar y modificar configuraciones del sistema que pueden ser indicadores de compromisos o ataques.
   - **Restauración del sistema**: Puede ser usado para revertir cambios no deseados realizados por malware o usuarios malintencionados.
   - **Lugares clave**: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run` para programas que se ejecutan al inicio.

### 5. **Política de Seguridad Local (Local Security Policy)**
   - **Configuración de políticas de auditoría**: Permite definir qué eventos se registran en el sistema.
   - **Gestión de políticas de seguridad**: Configura restricciones y políticas de seguridad para proteger el sistema.
   - **Acceso a herramientas**: `secpol.msc` en el cuadro de diálogo de ejecutar.

### 6. **Windows Defender / Microsoft Defender Antivirus**
   - **Protección en tiempo real**: Proporciona protección continua contra malware y otras amenazas.
   - **Análisis bajo demanda**: Permite ejecutar análisis completos o personalizados del sistema para detectar y eliminar amenazas.
   - **Registro de amenazas detectadas**: Muestra el historial de amenazas detectadas y acciones tomadas.

### 7. **Firewall de Windows con Seguridad Avanzada**
   - **Gestión de reglas de firewall**: Permite crear y gestionar reglas para controlar el tráfico de red entrante y saliente.
   - **Monitoreo de conexiones**: Proporciona información sobre conexiones activas y bloqueadas.
   - **Protección de la red**: Ayuda a prevenir accesos no autorizados y ataques de red.

### 8. **Centro de Seguridad de Windows (Windows Security Center)**
   - **Vista unificada de seguridad**: Proporciona una vista centralizada de las configuraciones y el estado de seguridad del sistema.
   - **Gestión de antivirus, firewall y otras protecciones**: Facilita la gestión de las distintas capas de seguridad del sistema.

### 9. **Comando `netstat`**
   - **Monitorización de conexiones de red**: Muestra todas las conexiones de red activas y los puertos en uso.
   - **Detección de conexiones sospechosas**: Identifica conexiones a direcciones IP sospechosas o inusuales.
   - **Opciones útiles**: `netstat -ano` para listar todas las conexiones con los identificadores de proceso (PID).

### 10. **Comando `tasklist` y `taskkill`**
   - **Listado de procesos**: `tasklist` muestra todos los procesos en ejecución y sus detalles.
   - **Terminación de procesos**: `taskkill` permite terminar procesos por nombre o PID, útil para detener aplicaciones sospechosas o maliciosas.

### Ejemplo Práctico de Uso Combinado

Imagina que sospechas de una posible infección por malware en tu sistema. Aquí tienes un flujo de trabajo utilizando estas herramientas:

1. **Visor de Eventos**: Revisa los registros de seguridad y sistema para detectar actividades sospechosas (p. ej., inicios de sesión inusuales, errores críticos).
2. **Administrador de Tareas**: Identifica procesos inusuales o de alto consumo de recursos.
3. **PowerShell**: Usa `Get-Process` y `Get-WinEvent` para obtener detalles adicionales de los procesos sospechosos y eventos de registro.
4. **Registro de Windows**: Verifica las claves de inicio para detectar programas que se inicien automáticamente sin tu conocimiento.
5. **Windows Defender**: Ejecuta un análisis completo del sistema para detectar y eliminar malware.
6. **Firewall de Windows**: Bloquea cualquier conexión de red sospechosa o no autorizada detectada mediante `netstat`.
7. **Política de Seguridad Local**: Asegúrate de que las políticas de auditoría están configuradas para registrar eventos clave de seguridad.
8. **Centro de Seguridad de Windows**: Revisa el estado general de seguridad del sistema y aplica las recomendaciones.

Utilizando estas herramientas de manera coordinada, puedes detectar, investigar y responder a incidentes de seguridad de manera eficaz en un entorno Windows.
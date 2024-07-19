# Seguridad Avanzada en Windows

---

Vamos a explorar algunas configuraciones de seguridad avanzada de Windows. Configuraciones avanzadas de seguridad que son menos comunes pero altamente efectivas. Estas configuraciones son cruciales para profesionales en ciberseguridad que buscan proteger sistemas de forma integral. Aunque no abordaremos conceptos básicos como Windows Defender, el antivirus de Windows, o su firewall, ya que no tienen  mucha relevancia para nuestro propósito. En lugar de eso, nos centraremos en configuraciones menos comunes pero realmente útiles para la ciberseguridad.

## Configuraciones clave y su importancia

### Aislamiento del Núcleo en Windows

El aislamiento del núcleo es una característica que pocas personas conocen, a pesar de su potencia. Esta funcionalidad utiliza tecnologías de virtualización basadas en hardware para proteger los componentes esenciales del sistema operativo. En esencia, crea un entorno seguro y aislado donde se ejecutan los componentes críticos del sistema, proporcionando una barrera robusta contra diversos tipos de malware, especialmente aquellos que intentan modificar el kernel .

#### ¿Cómo Funciona?

El aislamiento del núcleo se basa en Hyper-V, el hipervisor nativo de Windows, que permite la creación de máquinas virtuales dentro del hardware. Dentro de estas máquinas virtuales se ejecutan los procesos críticos del sistema, aislando así el núcleo del resto del entorno de ejecución. Esto significa que, incluso si un malware infecta parte del sistema operativo, tendrá dificultades para llegar al núcleo .

### Integridad de Memoria

Hablando de seguridad avanzada, también debemos mencionar la integridad de memoria. Esta característica verifica la integridad de los controladores y otros códigos que se ejecutan a nivel del kernel, bloqueando aquellos que no estén debidamente firmados o que presenten comportamientos sospechosos. De esta manera, se impide que el malware se infiltre y opere a un nivel más profundo del sistema .

#### Consideraciones de Rendimiento

Es importante tener en cuenta que aumentar la seguridad puede sacrificar el rendimiento. La virtualización para aislar el núcleo y la verificación continua de la integridad de la memoria requieren recursos adicionales. Si tu máquina no tiene suficientes recursos de hardware, podrías experimentar una disminución en el rendimiento. Por lo tanto, te recomiendo activar estas funcionalidades solo si tu sistema tiene la capacidad necesaria .

### Activación de aislamiento del núcleo y la integridad de memoria

Para activar estas características:

1. Ve a **Configuraciones**.
2. Dirígete a **Actualización y Seguridad**.
3. Selecciona **Seguridad de Windows**. Ingresa aquí.
4. Ve a **Seguridad del dispositivo** y luego a **Aislamiento del núcleo**, entra en los detalles.
5. Activa la **Integridad de la memoria**.

### Utilidad en Entornos Domésticos y Corporativos

Aunque estas funcionalidades ofrecen una mayor protección contra el malware, en un entorno doméstico el costo en términos de recursos puede no ser justificado. Sin embargo, en redes corporativas, como en un Windows Server que actúa como controlador de dominio, estas capas adicionales de seguridad son muy valiosas debido a la mayor capacidad de recursos y la necesidad crítica de protección .

En resumen, prueba estas configuraciones si tu hardware lo permite y evalúa su impacto en el rendimiento. Si el sistema funciona bien, mantén activadas estas características para disfrutar de una mayor seguridad.

### Enlaces para Ampliar la Información

Estos enlaces te permitirán profundizar en cada uno de los temas tratados y obtener información directamente de las fuentes oficiales de Microsoft.

- [Microsoft Docs sobre Aislamiento del Núcleo](https://docs.microsoft.com/en-us/windows/security/threat-protection/device-guard/kernel-isolation)
- [Guía de Microsoft sobre Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/about/)
- [Seguridad del Dispositivo en Windows 10](https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/device-security)
- [Información sobre Integridad de Memoria](https://docs.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-overview)

---

#### Recuerda

**Aislamiento del Núcleo**: Esta característica utiliza tecnologías de virtualización basadas en hardware para crear un entorno seguro donde se ejecutan los componentes críticos del sistema. Esto dificulta que el malware pueda acceder y modificar el kernel de Windows. El aislamiento del núcleo se apoya en Hyper-V, el hipervisor nativo de Windows, creando máquinas virtuales donde se ejecutan procesos críticos del sistema.

**Integridad de la Memoria**: Esta función verifica que los controladores y otros códigos que se ejecutan en el kernel estén firmados y sean legítimos. Bloquea aquellos que no cumplan con estos criterios, impidiendo que el malware ataque el kernel. Aunque estas características mejoran significativamente la seguridad, pueden requerir recursos adicionales del sistema, por lo que es importante evaluar su impacto en el rendimiento de tu hardware.

Para más detalles, puedes consultar la documentación oficial de Microsoft sobre [Aislamiento del núcleo](https://docs.microsoft.com/es-es/windows/security/threat-protection/microsoft-defender-atp/device-control-guard) y [Integridad de la memoria](https://docs.microsoft.com/es-es/windows/security/threat-protection/device-guard/memory-integrity).

> La integridad de memoria verifica que cada controlador o código que intenta ejecutarse en el *kernel* sea legítimo y esté firmado correctamente.

## Prevención de Ejecución de Datos (DEP)

**Data Execution Prevention (DEP)**: DEP es una característica de seguridad que ayuda a prevenir la ejecución de código malicioso en áreas de la memoria que deberían contener solo datos. Esto se logra segmentando la memoria RAM y marcando ciertas áreas como no ejecutables.

Para configurar DEP:
1. Ve a **Panel de Control**.
2. Selecciona **Sistema y Seguridad**.
3. Haz clic en **Sistema**.
4. Ve a **Configuración avanzada del sistema**.
5. En la pestaña **Rendimiento**, selecciona **Configuración** y luego **Prevención de ejecución de datos**.

DEP está activado por defecto para servicios esenciales de Windows, pero puedes configurarlo para proteger todo el software del sistema. Consulta la guía oficial de Microsoft para más información sobre [DEP](https://docs.microsoft.com/es-es/windows/security/threat-protection/data-execution-prevention).

## Directivas de Auditoría

Las directivas de auditoría permiten registrar eventos de seguridad en el sistema, como intentos de inicio de sesión, cambios en la configuración de seguridad, y accesos a archivos o directorios.

Para acceder y configurar las directivas de auditoría:
1. Abre una ventana de ejecución y escribe `secpol.msc`.
2. Ve a **Directivas locales** y luego a **Directiva de auditoría**.
3. Aquí puedes activar directivas específicas como la auditoría de inicio de sesión y de inicio de sesión de cuenta.

Estas configuraciones se registran en el Visor de Eventos, que permite realizar análisis forenses y detectar actividades sospechosas. Para más detalles, consulta la documentación oficial de Microsoft sobre [Directivas de Auditoría](https://docs.microsoft.com/es-es/windows/security/threat-protection/auditing/basic-security-audit-policies).

## Visor de Eventos de Windows

El Visor de Eventos es una herramienta fundamental para monitorear y analizar los eventos de seguridad en el sistema. Permite ver registros de eventos categorizados por aplicación, seguridad, instalación, sistema y eventos reenviados.

Para acceder al Visor de Eventos:
1. Busca **Visor de Eventos** en el sistema o abre una ventana de ejecución y escribe `eventvwr`.
2. En **Registros de Windows**, explora las subcategorías como **Aplicación**, **Seguridad**, **Instalación**, **Sistema** y **Eventos reenviados**.

Para buscar eventos específicos:
1. Utiliza la opción de **Buscar** en la subcategoría deseada.
2. Filtra por ID de evento, nivel de evento, o palabras clave.

Puedes crear vistas personalizadas para guardar criterios de búsqueda específicos, facilitando el monitoreo continuo de eventos críticos.

Para más información, consulta la documentación oficial de Microsoft sobre el [Visor de Eventos](https://docs.microsoft.com/es-es/windows/security/threat-protection/auditing/view-audit-log).

\*\*\*

*Estas configuraciones avanzadas en Windows son esenciales para cualquier profesional de ciberseguridad. Aunque requieren un entendimiento profundo y un análisis cuidadoso del impacto en el rendimiento, proporcionan una capa adicional de protección contra diversas amenazas. Implementar y dominar estas herramientas te ayudará a asegurar sistemas de manera efectiva y a mantener un entorno seguro en cualquier escenario, desde el hogar hasta redes corporativas.*

\*\*\*

Veamos algunos asuntos con cierto detalle:

### Directivas de Auditoría en Windows

Las directivas de auditoría son una parte crucial de las directivas de seguridad en Windows. Las directivas de seguridad son un conjunto de reglas y configuraciones que controlan varios aspectos de la seguridad y el comportamiento del sistema operativo. Dentro de estas directivas se incluyen configuraciones como:

- **Políticas de cuenta**: Requisitos de contraseña, bloqueo de cuenta, etc.
- **Asignación de derechos de usuario**: Controla quién puede realizar determinadas acciones en el sistema.
- **Opciones de seguridad local**: Configuraciones a nivel de User Access Control (UAC) y firewall.

La **directiva de auditoría** se enfoca específicamente en el seguimiento y registro de eventos de seguridad. Define qué actividades y eventos del sistema se deben registrar en los logs de seguridad, como:

- Intentos de inicio de sesión (correctos y erróneos)
- Cambios en la configuración de seguridad del sistema
- Modificaciones del software
- Acceso a archivos o directorios

La finalidad principal de la directiva de auditoría es proporcionar un registro detallado de las actividades de seguridad para detectar actividad sospechosa, realizar análisis forense o cumplir con requisitos de cumplimiento y auditoría, como el Reglamento General de Protección de Datos (RGPD) .

### Acceso a las Directivas de Auditoría

Para acceder y configurar las directivas de auditoría:

1. Abre una ventana de ejecución y escribe `secpol.msc`. 
2. Esto abrirá la Política de Seguridad Local, que es una consola de administración para configurar políticas y servicios en Windows.

Una vez dentro, dirígete a:

- **Directivas locales** 
- **Directiva de auditoría**

Aquí puedes ver y configurar las directivas para registrar eventos específicos que luego se podrán consultar en el visor de eventos.

### Configuración de Directivas de Auditoría Comunes

Algunas directivas de auditoría comunes que podrías usar incluyen:

- **Auditoría de inicio de sesión**
- **Auditoría de inicio de sesión de cuenta**

Para activar estas directivas:

1. Ábrelas y selecciona las opciones necesarias para registrar los inicios de sesión correctos, incorrectos o ambos.
2. Esta configuración te permitirá ver en el visor de eventos si alguien intentó acceder a tu cuenta y si lo logró o no.

### Visor de Eventos de Windows

El **Visor de eventos de Windows** es una herramienta poderosa para supervisar y analizar las actividades del sistema. Los registros de eventos incluyen información sobre errores, advertencias e información operativa. Este visor es esencial para las auditorías de seguridad, el diagnóstico de problemas y el análisis forense.

#### Acceso al Visor de Eventos

Puedes acceder al visor de eventos:

1. Buscándolo en el sistema
2. Abriendo una ventana de ejecución y escribiendo `eventvwr` o `eventvwr.msc`

#### Uso del Visor de Eventos

En el visor de eventos, encontrarás varias categorías principales, pero nos enfocaremos en **Registros de Windows** y dentro de esta sección en **Seguridad**. Aquí podrás ver los registros de auditoría exitosos y fallidos, que son cruciales para la detección de actividades sospechosas.

#### Niveles de Eventos

En la subcategoría de seguridad, los niveles de eventos son:

- **Auditoría exitosa**: Acciones correctas sin problemas aparentes de seguridad.
- **Auditoría fallida**: Intentos fallidos o no autorizados, como un intento de inicio de sesión con una contraseña incorrecta.

### Creación de Vistas Personalizadas

Para facilitar la búsqueda de eventos específicos:

1. Crea una nueva vista personalizada.
2. Configura los criterios de búsqueda, como rango de fechas, nivel del evento, subcategoría y ID del evento.
3. Guarda y nombra la vista para consultarla fácilmente en el futuro.

Por ejemplo, puedes buscar eventos de inicio de sesión exitosos (ID 4624) o fallidos (ID 4625) para investigar si alguien intentó acceder a tu cuenta sin éxito.

Para más información, consulta la [documentación oficial de Microsoft](https://docs.microsoft.com/es-es/windows/security/threat-protection/auditing/audit-policy-recommendations) sobre políticas de auditoría y el visor de eventos.

### Uso del Visor de Eventos en Windows

El **Visor de Eventos de Windows** es una herramienta esencial para supervisar y analizar eventos del sistema. Aquí te mostramos cómo usarlo para monitorear la seguridad de tu PC y resolver problemas:

#### Categorías y Subcategorías Principales

En el Visor de Eventos, hay cuatro categorías principales bajo "Registros de Windows":
- **Aplicación**
- **Seguridad**
- **Instalación**
- **Sistema**
- **Eventos Reenviados**

Cada subcategoría almacena registros específicos asociados a su temática. Al hacer clic en una categoría global, puedes ver estadísticas generales como el nombre, tipo, número de eventos y tamaño de los registros.

#### Columnas y Niveles de Eventos

Al entrar en una subcategoría, verás registros individuales con varias columnas importantes:
- **Nivel**: Clasifica el evento según su gravedad (Error, Advertencia, Información).
- **Fecha y hora**: Indica cuándo ocurrió el evento.
- **Origen**: Identifica la fuente del evento.
- **ID del Evento**: Un número que representa un tipo específico de evento.
- **Categoría de la Tarea**: Describe la naturaleza de la actividad registrada.

##### Niveles de Eventos:

- **Error**: Problemas significativos que requieren atención inmediata.
- **Advertencia**: Eventos no críticos que pueden indicar problemas futuros.
- **Información**: Eventos que describen la operación normal del sistema.

#### Subcategoría de Seguridad

En la subcategoría de **Seguridad**, los niveles de eventos son diferentes:
- **Auditoría exitosa**: Acciones completadas correctamente, sin problemas de seguridad aparentes.
- **Auditoría fallida**: Intentos fallidos o no autorizados, como intentos de inicio de sesión con contraseñas incorrectas.

Estos niveles son cruciales para detectar actividades sospechosas y posibles violaciones de seguridad.

#### Propiedades Adicionales de los Eventos

Cada evento tiene propiedades adicionales. Para verlas, haz doble clic o clic derecho en el evento y selecciona "Propiedades". Aquí encontrarás detalles más específicos sobre el evento.

#### Uso de la Función de Búsqueda

Para buscar eventos específicos:
1. Utiliza la función de búsqueda introduciendo términos clave como "logon" o IDs específicos de eventos.
2. Los IDs comunes en la subcategoría de seguridad incluyen:
   - **4624**: Inicio de sesión exitoso.
   - **4625**: Inicio de sesión fallido.
   - **4648**: Inicio de sesión usando credenciales explícitas (ej. ejecutar como administrador).

#### Creación de Vistas Personalizadas

Para optimizar la búsqueda y filtrado de eventos, puedes crear vistas personalizadas:
1. Selecciona "Crear Vista Personalizada".
2. Define los criterios como rango de fechas, nivel de evento, subcategoría, ID del evento, y palabras clave.
3. Guarda y nombra la vista para acceder fácilmente a estos registros en el futuro.

Por ejemplo, para ver inicios de sesión exitosos:
- Selecciona la subcategoría "Seguridad".
- Introduce el ID 4624 y la palabra clave "auditoría correcta".
- Guarda la vista para futuras consultas.

#### Enlaces para ampliar información

Estas referencias te proporcionarán información detallada y oficial sobre cómo configurar y utilizar las directivas de auditoría y el visor de eventos en Windows.

1. [Políticas de Auditoría en Windows](https://docs.microsoft.com/es-es/windows/security/threat-protection/auditing/audit-policy-recommendations)
2. [Visor de Eventos de Windows](https://docs.microsoft.com/es-es/windows/security/threat-protection/auditing/event-viewer-security-logs)
3. [Configuración de Directivas de Seguridad](https://docs.microsoft.com/es-es/windows/security/threat-protection/security-policy-settings/security-policy-settings)
4. [Id de evento](https://learn.microsoft.com/es-es/windows-server/identity/ad-ds/plan/appendix-l--events-to-monitor)
5. [Event error codes](https://learn.microsoft.com/es-es/defender-endpoint/event-error-codes)

### Directivas de Grupo

Las directivas de grupo son una herramienta poderosa que permite a los administradores de sistemas configurar y gestionar de manera centralizada los ajustes y políticas de los sistemas operativos y aplicaciones en una red. Aunque este curso se enfoca en ciberseguridad, es esencial entender algunos aspectos básicos de las directivas de grupo, ya que probablemente acabaremos utilizándolas en algún momento.

Las directivas de grupo se utilizan principalmente en entornos corporativos y no tanto en redes locales o para usuarios domésticos. Sin embargo, existen algunas políticas que podrían ser útiles en ciertos contextos para realizar modificaciones en el sistema.

Las directivas de grupo permiten a los administradores establecer políticas para grupos de usuarios y equipos, controlar la instalación de software, configurar ajustes de seguridad, personalizar entornos de trabajo y centralizar configuraciones para múltiples activos dentro de una misma red. Estas directivas se aplican a través de Active Directory, una herramienta que exploraremos en cursos más avanzados.

Para acceder a las directivas de grupo en Windows, simplemente busca "Editor de directivas de grupo" en el buscador de Windows y ábrelo. En la interfaz gráfica que aparece, verás dos categorías principales: "Configuración del equipo" y "Configuración de usuario", que se dividen en tres subcategorías: Configuración de software, Configuración de Windows y Plantillas administrativas.

- **Configuración de software**: Permite a los administradores especificar ajustes relacionados con la instalación, actualización y eliminación de software.
- **Configuración de Windows**: Aquí se establecen políticas específicas del sistema operativo, como configuraciones de seguridad, scripts de inicio y apagado, componentes de Windows, etc.
- **Plantillas administrativas**: Contiene opciones de configuración detalladas para características y componentes específicos del sistema operativo y aplicaciones.

Para más información sobre las directivas de grupo y su uso, puedes consultar la [documentación oficial de Microsoft sobre Directivas de Grupo](https://docs.microsoft.com/es-es/windows-server/identity/ad-ds/manage/component-updates/group-policy-overview).

### BitLocker

BitLocker es una herramienta de cifrado de disco incorporada en versiones selectas de Windows, como Windows Pro, Enterprise y Education. BitLocker utiliza el algoritmo de cifrado AES (Advanced Encryption Standard) con longitudes de clave de 128 o 256 bits. Este cifrado asegura que la información en la unidad de almacenamiento solo pueda ser accedida si se proporciona la contraseña correcta.

El uso de BitLocker es común en entornos corporativos para cumplir con normativas de seguridad, como el GDPR (Reglamento General de Protección de Datos) o HIPAA (Ley de Portabilidad y Responsabilidad del Seguro de Salud), que requieren mantener un alto nivel de confidencialidad en la información. También puede proteger contra ciertos tipos de malware que intentan modificar el proceso de arranque.

Para activar BitLocker en una unidad de almacenamiento en Windows:

1. **Particionar la unidad**: Desde el Administrador de discos, selecciona la parte que quieres particionar, dale formato y nombre.
2. **Activar BitLocker**: Haz clic derecho en la partición y selecciona "Activar BitLocker".
3. **Seleccionar método de desbloqueo**: Puedes elegir una contraseña o una tarjeta inteligente.
4. **Elegir cantidad a cifrar**: Puedes optar por cifrar solo la parte usada o toda la unidad.
5. **Seleccionar modo de cifrado**: Nuevo (para unidades internas) o Compatible (para unidades externas).
6. **Completar el proceso**: Sigue las indicaciones y guarda la clave de recuperación en un lugar seguro.

Para más detalles sobre la configuración y uso de BitLocker, puedes revisar la [guía oficial de Microsoft sobre BitLocker](https://docs.microsoft.com/es-es/windows/security/information-protection/bitlocker/bitlocker-overview).

### Ejemplo práctico de uso de BitLocker

Si deseas cifrar la unidad donde está instalado el sistema operativo, el proceso es similar al descrito anteriormente, pero requiere habilitar el TPM (Trusted Platform Module), un chip de seguridad que proporciona funciones de seguridad a nivel de hardware. 

Para habilitar el uso de BitLocker sin TPM:

1. **Acceder a las directivas de grupo**: Busca "Editor de directivas de grupo" en el buscador de Windows y ábrelo.
2. **Navegar a la configuración adecuada**: Ve a Configuración del equipo > Plantillas administrativas > Componentes de Windows > Cifrado de unidad BitLocker > Unidades del sistema operativo.
3. **Habilitar la configuración**: Abre "Requerir autenticación adicional al iniciar" y actívala.

Luego, puedes seguir el procedimiento habitual para activar BitLocker en la unidad del sistema.

### Seguridad y rendimiento

El uso de BitLocker puede afectar ligeramente el rendimiento del sistema debido a los procesos de cifrado y descifrado, pero esta herramienta está optimizada para funcionar correctamente en sistemas Windows. Es recomendable cifrar tanto las unidades internas como las externas para proteger tus datos contra accesos no autorizados.

Para más detalles sobre la seguridad y el rendimiento de BitLocker, consulta la [guía de rendimiento de BitLocker](https://docs.microsoft.com/es-es/windows/security/information-protection/bitlocker/bitlocker-deployment-and-administration-best-practices).

### Conclusión

Las directivas de grupo y BitLocker son herramientas esenciales para la administración de seguridad en entornos Windows. Las directivas de grupo permiten una gestión centralizada de configuraciones y políticas, mientras que BitLocker proporciona un cifrado robusto para proteger la información sensible. Ambas herramientas son fundamentales en entornos corporativos y, aunque no se usen tanto a nivel doméstico, conocer su funcionamiento puede ser muy beneficioso para cualquier usuario avanzado de Windows.

---

---

Practicas ???



¡Claro! Aquí tienes dos prácticas formativas basadas en los textos mejorados: una sobre la configuración de directivas de grupo y otra sobre la activación de BitLocker en Windows. Cada práctica incluye pasos detallados para que puedas seguirlas fácilmente.

### Práctica 1: Configuración de Directivas de Grupo

**Objetivo:** Aprender a configurar una directiva de grupo para impedir la instalación de software no autorizado en un entorno Windows.

#### Paso 1: Acceder al Editor de Directivas de Grupo
1. En tu computadora con Windows, presiona `Win + R` para abrir el cuadro de diálogo Ejecutar.
2. Escribe `gpedit.msc` y presiona Enter para abrir el Editor de directivas de grupo.

#### Paso 2: Navegar a la Configuración de Software
1. En el Editor de directivas de grupo, ve a `Configuración del equipo` > `Plantillas administrativas` > `Componentes de Windows` > `Instalador de Windows`.
2. Haz clic en `Prohibir la instalación de software no autorizado`.

#### Paso 3: Configurar la Directiva
1. Haz doble clic en `Prohibir la instalación de software no autorizado`.
2. Selecciona `Habilitada`.
3. En la sección `Opciones`, puedes especificar los criterios para la instalación permitida o bloqueada, como los editores de software permitidos.
4. Haz clic en `Aceptar` para guardar los cambios.

#### Paso 4: Aplicar la Directiva
1. Abre una ventana de comando con privilegios de administrador: presiona `Win + X` y selecciona `Símbolo del sistema (Administrador)`.
2. Ejecuta el comando `gpupdate /force` para aplicar las nuevas configuraciones de directiva de grupo.

#### Paso 5: Verificar la Configuración
1. Intenta instalar un software no autorizado en el sistema.
2. Verifica que la instalación sea bloqueada conforme a la directiva configurada.

**Recursos adicionales:**
- [Documentación oficial de Microsoft sobre Directivas de Grupo](https://docs.microsoft.com/es-es/windows-server/identity/ad-ds/manage/component-updates/group-policy-overview)

### Práctica 2: Activación de BitLocker

**Objetivo:** Aprender a activar BitLocker en una unidad de almacenamiento en Windows 10.

#### Paso 1: Particionar la Unidad
1. Abre el Administrador de discos: presiona `Win + X` y selecciona `Administración de discos`.
2. Selecciona el disco donde deseas crear una partición.
3. Haz clic derecho en el espacio no asignado y selecciona `Nuevo volumen simple`.
4. Sigue el asistente para crear y formatear la nueva partición.

#### Paso 2: Activar BitLocker en la Partición
1. Haz clic derecho en la nueva partición creada y selecciona `Activar BitLocker`.
2. En el asistente de BitLocker, selecciona `Usar una contraseña para desbloquear la unidad`.
3. Introduce y confirma una contraseña segura.

#### Paso 3: Guardar la Clave de Recuperación
1. Elige dónde guardar la clave de recuperación: puedes guardarla en tu cuenta de Microsoft, en un archivo (en una unidad diferente) o imprimirla.
2. Sigue las instrucciones para completar el proceso.

#### Paso 4: Seleccionar Cantidad a Cifrar
1. Selecciona si deseas cifrar solo el espacio utilizado o todo el disco.
2. Para esta práctica, elige `Cifrar solo el espacio utilizado` para un proceso más rápido.

#### Paso 5: Elegir el Modo de Cifrado
1. Selecciona el modo de cifrado adecuado. Para unidades internas, selecciona `Nuevo modo de cifrado`.

#### Paso 6: Iniciar el Cifrado
1. Haz clic en `Iniciar cifrado` y espera a que el proceso finalice.

#### Paso 7: Verificar el Cifrado
1. Reinicia el sistema para completar el proceso.
2. Verifica que la unidad está cifrada intentando acceder a ella e introduciendo la contraseña que configuraste.

**Recursos adicionales:**
- [Guía oficial de Microsoft sobre BitLocker](https://docs.microsoft.com/es-es/windows/security/information-protection/bitlocker/bitlocker-overview)

Ambas prácticas te ayudarán a familiarizarte con herramientas importantes de administración y seguridad en Windows, proporcionándote habilidades útiles tanto para entornos corporativos como personales.

---

Herramienta de escaneo de vulnerabilidades de Windows

- http://public.cyber.mil/stigs/scap  &rarr; [SCC 5.9 Windows](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/scc-5.9_Windows_bundle.zip)
- https://www.niwcatlantic.navy.mil/Technology/SCAP/ &rarr; [videos](https://www.niwcatlantic.navy.mil/Technology/SCAP/SCAP-Tutorial-Videos/)

 # Herramientas para la auditoría de sistemas 

Debido a la gran variedad de vulnerabilidades existentes, las herramientas  encargadas de su detección y análisis son abundantes y variadas. 

La auditoría de sistemas es un proceso crucial para garantizar la seguridad, eficiencia y cumplimiento de un sistema de TI. Implica la evaluación de los sistemas informáticos y la infraestructura para identificar vulnerabilidades, riesgos, cumplimiento de normativas y eficiencia operativa. Para llevar a cabo estas auditorías, existen diversas herramientas especializadas que ayudan a los auditores a realizar su trabajo de manera efectiva. 

> Un auditor debe contar con herramientas de análisis de red, puertos y servicios, herramientas de análisis de protocolos, herramientas de ataque de diccionario  y de fuerza bruta, etc., además de las herramientas internas de cada sistema  operativo.

Veamos algunas de las herramientas más utilizadas para la auditoría de sistemas:

## Herramientas del sistema operativo tipo Ping, Traceroute, etc.

Las herramientas de diagnóstico de red son fundamentales para evaluar y solucionar problemas de conectividad y rendimiento en redes. Ayudan a detectar si existe alguna anomalía de  red, comprobar el alcance de esta anomalía y, además, cuáles han sido los  servicios que se han hecho inaccesibles por la incidencia. Esta herramientas comunes vienen integradas en la mayoría de los sistemas operativos:

### 1. **Ping (Packet Internet Groper) o rastreador de paquetes de red**

Se utiliza fundamentalmente para comprobar la calidad y la velocidad de  una red determinada y para comprobar la latencia[^1] entre dos equipos.

   - **Función**: Verificación de conectividad.
   - **Descripción**: Ping envía paquetes ICMP (Internet Control Message Protocol) a un destino específico (por ejemplo, una dirección IP o un nombre de dominio) y mide el tiempo que tarda en recibir una respuesta. Es útil para comprobar si un host está activo y accesible.
   - **Caso de uso**: Verificar la conectividad de un servidor web.
   - **Ejemplo**: Supongamos que no puedes acceder a un sitio web, como `www.ejemplo.com`. Puedes usar `ping www.ejemplo.com` para verificar si el servidor responde. Si recibes respuestas (con tiempos de respuesta), significa que el servidor está accesible; si no, podría haber un problema de red o el servidor podría estar inactivo.

### 2. **Traceroute (o Tracert en Windows)**

   - **Función**: Rastreo de rutas.
   - **Descripción**: Se utiliza para seguir la ruta de los paquetes en  una red IP y el retardo que se produce en este tránsito. Traceroute muestra la ruta que toman los paquetes para llegar a un destino específico, identificando cada salto intermedio (normalmente routers). Es útil para identificar puntos de fallo o latencia en la red. 
   - **Caso de uso**: Diagnosticar dónde se produce un problema de red en el camino hacia un servidor.
   - **Ejemplo**: Si los usuarios están experimentando lentitud al acceder a un servicio remoto, puedes usar `traceroute www.ejemplo.com` para ver la ruta que toman los paquetes y determinar en qué salto hay un retraso o pérdida de paquetes.

### 3. **nslookup**
   - **Función**: Consulta de DNS.
   - **Descripción**: nslookup es una herramienta para consultar el sistema de nombres de dominio (DNS). Permite averiguar la dirección IP asociada a un nombre de dominio y viceversa. También es útil para diagnosticar problemas de resolución de nombres.
   - **Caso de uso**: Resolver problemas de DNS.
   - **Ejemplo**: Si un usuario no puede acceder a un dominio, como `www.ejemplo.com`, puedes usar `nslookup www.ejemplo.com` para verificar si el DNS está resolviendo correctamente el nombre de dominio a una dirección IP.

### 4. **dig**
   - **Función**: Consulta avanzada de DNS.
   - **Descripción**: dig (Domain Information Groper) es una herramienta más avanzada que nslookup para realizar consultas DNS. Proporciona detalles adicionales y es ampliamente utilizada para diagnosticar problemas con los servidores DNS.
   - **Caso de uso**: Obtener información detallada sobre registros DNS.
   - **Ejemplo**: Para verificar el registro MX (Mail Exchange) de un dominio y asegurarte de que los correos electrónicos se enruten correctamente, puedes usar `dig ejemplo.com MX` para ver a qué servidores de correo está apuntando el dominio.

### 5. **netstat**
   - **Función**: Estadísticas de red.
   - **Descripción**: netstat muestra estadísticas detalladas de las conexiones de red actuales, incluyendo puertos abiertos, conexiones activas y el estado de estas conexiones. Es útil para diagnosticar problemas de red y monitorear la actividad de la red.
   - **Caso de uso**: Monitorizar conexiones de red abiertas en un servidor.
   - **Ejemplo**: Si sospechas que un servidor está siendo atacado o tiene conexiones no autorizadas, puedes usar `netstat -an` para listar todas las conexiones activas y los puertos en los que está escuchando. Esto ayuda a identificar conexiones sospechosas.

### 6. **ipconfig (Windows) / ifconfig (Linux/Unix)**
   - **Función**: Configuración de red.
   - **Descripción**: 
     - **ipconfig** (Windows): Muestra la configuración actual de la red, incluyendo direcciones IP, máscaras de subred y puertas de enlace predeterminadas.
     - **ifconfig** (Linux/Unix): Similar a ipconfig, pero con capacidades adicionales, como habilitar o deshabilitar interfaces de red y cambiar su configuración.
   - **Caso de uso**: Verificar la configuración de la red local en un equipo.
- **Ejemplo**: Si un usuario no puede acceder a la red, puedes usar `ipconfig` en Windows o `ifconfig` en Linux/Unix para verificar la configuración de la IP, máscara de subred y puerta de enlace. Esto puede ayudar a diagnosticar si el problema es una configuración incorrecta o falta de conectividad.

### 7. **arp**
   - **Función**: Tabla de resolución de direcciones.
   - **Descripción**: arp muestra y modifica la tabla ARP (Address Resolution Protocol), que mapea direcciones IP a direcciones MAC en una red local. Es útil para resolver problemas de conectividad en redes locales.
   - **Caso de uso**: Detectar conflictos de direcciones IP en una red local.
   - **Ejemplo**: Si dos dispositivos en la misma red tienen la misma dirección IP, puedes usar `arp -a` para ver la tabla ARP y comprobar si la dirección IP está asociada a diferentes direcciones MAC, lo que indicaría un conflicto.

### 8. **hostname**
   - **Función**: Muestra o configura el nombre del host.
   - **Descripción**: hostname muestra el nombre del host actual del sistema o permite configurarlo. Es útil para identificar el nombre de red del equipo.
   - **Caso de uso**: Identificar rápidamente el nombre de un equipo en la red.
   - **Ejemplo**: En una red corporativa grande, puedes usar `hostname` en un equipo para saber su nombre de host, lo que facilita la administración y el acceso a través de la red.

### 9. **route**
   - **Función**: Tabla de enrutamiento.
   - **Descripción**: route permite ver y manipular la tabla de enrutamiento IP del sistema, que determina cómo se enrutan los paquetes de red hacia diferentes destinos.
   - **Caso de uso**: Modificar la tabla de enrutamiento para solucionar problemas de red.
   - **Ejemplo**: Si una ruta predeterminada está mal configurada y el tráfico no se enruta correctamente, puedes usar `route add` para añadir una ruta específica o `route delete` para eliminar una ruta problemática.

### 10. **netcat (nc)**
   - **Función**: Herramienta de red versátil.
   - **Descripción**: netcat es una herramienta de red que puede leer y escribir datos a través de conexiones de red utilizando los protocolos TCP o UDP. Es extremadamente flexible y se utiliza para pruebas de conectividad, transferencia de archivos, escaneo de puertos, y más.
   - **Caso de uso**: Probar la conectividad de un puerto específico en un servidor.
   - **Ejemplo**: Si un servicio como un servidor web en el puerto 80 no responde, puedes usar `nc -zv www.ejemplo.com 80` para verificar si el puerto está abierto y aceptando conexiones.

### 11. **telnet**
   - **Función**: Conexión a puertos de red.
   - **Descripción**: telnet permite conectarse a puertos de red específicos en un host remoto. Aunque es un protocolo antiguo y no seguro, sigue siendo útil para diagnosticar problemas de conectividad y probar servicios de red.
   - **Caso de uso**: Diagnosticar problemas de conectividad a servicios específicos.
   - **Ejemplo**: Si no puedes conectarte a un servidor de correo en el puerto 25 (SMTP), puedes usar `telnet mail.ejemplo.com 25` para ver si el puerto está abierto y el servicio responde. Esto también permite interactuar directamente con el servicio para diagnósticos más profundos.

### 12. **mtr (My Traceroute)**
   - **Función**: Diagnóstico de ruta en tiempo real.
   - **Descripción**: mtr combina las funcionalidades de `ping` y `traceroute` para proporcionar un monitoreo continuo de la ruta de red entre el origen y el destino. Es muy útil para detectar problemas de red intermitentes.
   - **Caso de uso**: Monitoreo continuo de la calidad de la conexión a un servidor.
   - **Ejemplo**: Si estás enfrentando problemas intermitentes de conexión con un servidor remoto, puedes usar `mtr www.ejemplo.com` para ver en tiempo real cómo varía la latencia y la pérdida de paquetes en cada salto de la ruta.

### 13. **tcpdump**
   - **Función**: Captura de paquetes.
   - **Descripción**: tcpdump es una herramienta de captura de tráfico de red. Permite capturar y analizar el tráfico de red que pasa a través de una interfaz de red específica, lo que es útil para el diagnóstico profundo de problemas de red.
   - **Caso de uso**: Capturar y analizar tráfico de red para detectar problemas o ataques.
   - **Ejemplo**: Si sospechas que hay tráfico malicioso en tu red, puedes usar `tcpdump` para capturar el tráfico en una interfaz específica y analizarlo para identificar patrones de ataque, como intentos de escaneo de puertos o conexiones no autorizadas.

### 14. **ss**
   - **Función**: Información de sockets.
   - **Descripción**: ss (socket statistics) es una herramienta similar a netstat, pero más moderna y eficiente. Proporciona información detallada sobre conexiones y sockets de red, incluyendo TCP, UDP, y más.
   - **Caso de uso**: Verificar el estado de conexiones de red y sockets en un servidor.
   - **Ejemplo**: Si un servidor está bajo mucha carga y sospechas que hay demasiadas conexiones abiertas, puedes usar `ss -tuln` para ver todas las conexiones y puertos que están en uso, lo que puede ayudar a identificar cuellos de botella o ataques de tipo DoS.

### 15. **nmap**
   - **Función**: Escaneo de puertos y auditoría de seguridad.
   - **Descripción**: Aunque mencionada en el contexto de auditoría de sistemas, nmap también es útil para escanear redes en busca de puertos abiertos y servicios, lo que puede ayudar a diagnosticar problemas de conectividad y seguridad.
   - **Caso de uso**: Escanear una red para identificar dispositivos activos y servicios expuestos.
   - **Ejemplo**: Antes de realizar una auditoría de seguridad, puedes usar `nmap -sP 192.168.1.0/24` para hacer un escaneo de ping de la red interna y descubrir todos los dispositivos activos. Luego, puedes hacer un escaneo más detallado para identificar los servicios y puertos abiertos en esos dispositivos.

Estas herramientas son esenciales para la administración y diagnóstico de redes, ayudando a identificar y resolver problemas de conectividad, rendimiento, y seguridad.

## Herramientas de análisis de red, puertos y servicios tipo Nmap,  Netcat, NBTScan, etc

Las herramientas de análisis de red, puertos y servicios son fundamentales para entender cómo está configurada una red, identificar servicios activos, y detectar posibles vulnerabilidades. 

Veamos algunas de estas herramientas populares como Nmap, Netcat, y NBTScan, junto con ejemplos de casos de uso para cada una:

### 1. **Nmap**
   - **Función**: Escaneo de red y auditoría de seguridad.
   - **Descripción**: Nmap es una herramienta de código abierto utilizada para el descubrimiento de redes y la auditoría de seguridad. Permite a los auditores identificar dispositivos en la red, servicios activos, sistemas operativos y posibles vulnerabilidades.
   - **Caso de uso**: Descubrimiento de dispositivos y servicios en una red corporativa.
   - **Ejemplo**: Imagina que estás realizando una auditoría de seguridad en la red de una empresa. Utilizas `Nmap` para escanear todos los dispositivos conectados a la red, identificando qué servicios están corriendo en cada uno (por ejemplo, servidores web, bases de datos, etc.). Esto te ayuda a identificar posibles puntos débiles como servicios innecesarios o no autorizados que podrían ser explotados por atacantes.
   - **Ejemplo**: Quieres identificar todos los servicios activos en un servidor de la red. Usas `nmap -sV 192.168.1.100` para escanear la IP del servidor, lo que te permite identificar qué puertos están abiertos y qué servicios y versiones de software están corriendo. Esto es útil para identificar servicios que podrían ser vulnerables a ataques.

### 2. **Wireshark**

   - **Función**: Análisis de tráfico de red.
   - **Descripción**: Wireshark es una herramienta de análisis de paquetes de red que permite a los auditores capturar y analizar tráfico de red en tiempo real. Es útil para detectar problemas de red, intrusiones, vulnerabilidades en la seguridad y comprender cómo fluyen los datos a través de la red.
   - **Caso de uso**: Análisis de tráfico para detectar actividades sospechosas.
   - **Ejemplo**: Durante una auditoría, se sospecha que hay una fuga de datos en la red. Usas `Wireshark` para capturar y analizar el tráfico de red, buscando patrones inusuales, como la transferencia de grandes volúmenes de datos a una IP externa desconocida. Esto podría indicar un compromiso de seguridad.
   - **Caso de uso**: Análisis de tráfico para descubrir fuga de información.
   - **Ejemplo**: Si se sospecha que un empleado está enviando información confidencial fuera de la empresa, se podría usar `Wireshark` para capturar y analizar el tráfico saliente desde su estación de trabajo. Si se descubre tráfico cifrado sospechoso hacia una dirección IP no autorizada, esto podría ser indicativo de una fuga de datos, lo que permitiría tomar medidas correctivas inmediatas.

### 3. **Nessus**
   - **Función**: Escaneo de vulnerabilidades.
   - **Descripción**: Nessus es una de las herramientas más populares para la detección de vulnerabilidades en sistemas y redes. Proporciona informes detallados sobre posibles problemas de seguridad y sugerencias para mitigarlos.
   - **Caso de uso**: Identificación de vulnerabilidades en servidores y aplicaciones.
   - **Ejemplo**: En una auditoría de seguridad de servidores, ejecutas un escaneo con `Nessus` para detectar vulnerabilidades conocidas, como software desactualizado, configuraciones inseguras o la presencia de malware. Nessus genera un informe con recomendaciones para mitigar estas vulnerabilidades, lo que te permite priorizar las acciones correctivas.

### 4. **Metasploit**
   - **Función**: Pruebas de penetración.
   - **Descripción**: Metasploit es una herramienta de código abierto utilizada para realizar pruebas de penetración. Permite a los auditores simular ataques para identificar y explotar vulnerabilidades en sistemas, lo que ayuda a evaluar la efectividad de las medidas de seguridad implementadas.
   - **Caso de uso**: Prueba de penetración para evaluar la seguridad de un sistema.
   - **Ejemplo**: Después de identificar una vulnerabilidad con Nessus, decides usar `Metasploit` para intentar explotarla y verificar su impacto. Realizas un ataque controlado para simular cómo un hacker podría aprovechar la vulnerabilidad para acceder a datos sensibles, lo que te proporciona evidencia para reforzar la seguridad del sistema.

### 5. **Splunk**

   - **Función**: Monitoreo y análisis de logs.
   - **Descripción**: Splunk es una plataforma que permite a los auditores recopilar, indexar y analizar grandes volúmenes de datos de registros (logs) en tiempo real. Es útil para la detección de incidentes, análisis forense y cumplimiento normativo.
   - **Caso de uso**: Monitoreo de registros en tiempo real para detectar incidentes de seguridad.
   - **Ejemplo**: Durante una auditoría, configuras `Splunk` para recopilar y analizar los logs de diferentes servidores, aplicaciones y dispositivos de red. Detectas un patrón de intentos fallidos de inicio de sesión que podría indicar un ataque de fuerza bruta. Con esta información, puedes responder rápidamente al incidente antes de que ocurra una brecha de seguridad.

### 6. **SolarWinds Network Performance Monitor (NPM)**
   - **Función**: Monitoreo de rendimiento de red.
   - **Descripción**: SolarWinds NPM es una herramienta que permite a los auditores monitorear el rendimiento de la red, identificar problemas de conectividad, cuellos de botella y asegurar que la red esté funcionando de manera óptima.
   - **Caso de uso**: Monitoreo del rendimiento de la red para identificar cuellos de botella.
   - **Ejemplo**: En una auditoría de infraestructura, usas `SolarWinds NPM` para monitorizar el tráfico de red y el rendimiento de los dispositivos. Descubres que un switch está sobrecargado, lo que provoca lentitud en la red. Esto te permite recomendar mejoras en la configuración de la red o la actualización del hardware.

### 7. **Kali Linux**
   - **Función**: Distribución de pruebas de penetración.
   - **Descripción**: Kali Linux es una distribución de Linux diseñada para pruebas de penetración y auditorías de seguridad. Incluye una gran cantidad de herramientas preinstaladas, como Nmap, Wireshark, Metasploit, y más, que son esenciales para la auditoría de sistemas.
   - **Caso de uso**: Auditoría completa de seguridad utilizando una suite de herramientas.
   - **Ejemplo**: Realizar una auditoría de seguridad exhaustiva en una red corporativa utilizando `Kali Linux`, que incluye herramientas como Nmap, Wireshark, Metasploit, y otras. Realizar escaneos de red, pruebas de penetración, análisis de tráfico y revisiones de configuración para identificar y mitigar todos los posibles riesgos de seguridad.

### 8. **OpenVAS**
   - **Función**: Escaneo de vulnerabilidades.
   - **Descripción**: OpenVAS (Open Vulnerability Assessment System) es una herramienta de código abierto para el escaneo de vulnerabilidades. Ofrece una solución completa para la auditoría de seguridad de redes y sistemas.
   - **Caso de uso**: Escaneo de vulnerabilidades en una red interna.
   - **Ejemplo**: Como parte de una auditoría de cumplimiento, utilizas `OpenVAS` para escanear la red interna de una organización en busca de vulnerabilidades. El escaneo revela varias vulnerabilidades en servidores antiguos que no han sido parcheados. Con esta información, puedes ayudar a la empresa a priorizar la actualización de su software para mejorar la seguridad.

### 9. **AuditBoard**
   - **Función**: Gestión de auditorías y cumplimiento.
   - **Descripción**: AuditBoard es una plataforma de gestión de auditorías que permite planificar, ejecutar y documentar auditorías de manera eficiente. Es útil para la auditoría interna, la gestión de riesgos y el cumplimiento normativo.
   - **Caso de uso**: Gestión de auditorías de cumplimiento normativo.
   - **Ejemplo**: Estás realizando una auditoría de cumplimiento para una empresa que debe adherirse a normativas como GDPR. Usas `AuditBoard` para planificar y documentar la auditoría, asegurando que todos los controles requeridos se revisen y se reporten de manera estructurada. Además, generas informes detallados para demostrar el cumplimiento a los reguladores.

### 10. **Tripwire**
   - **Función**: Detección de cambios y cumplimiento.
   - **Descripción**: Tripwire es una herramienta que ayuda a los auditores a detectar cambios no autorizados en los sistemas, verificar la integridad de los archivos y asegurar el cumplimiento de las políticas de seguridad.
   - **Caso de uso**: Verificación de la integridad de los archivos del sistema.
   - **Ejemplo**: Durante una auditoría de seguridad, implementas `Tripwire` para monitorizar cambios en los archivos críticos del sistema. Esto te permite detectar cualquier modificación no autorizada que podría indicar una intrusión o compromiso, y tomar medidas correctivas de inmediato.

### 11. **Burp Suite**
   - **Función**: Pruebas de seguridad de aplicaciones web.
   - **Descripción**: Burp Suite es una herramienta utilizada para realizar auditorías de seguridad en aplicaciones web. Permite a los auditores identificar y explotar vulnerabilidades como inyecciones SQL, XSS, y más.
- **Caso de uso**: Auditoría de seguridad de aplicaciones web.
- **Ejemplo**: Como parte de una auditoría de seguridad de aplicaciones web, usas `Burp Suite` para realizar un escaneo automatizado y manual de una aplicación web en busca de vulnerabilidades como inyecciones SQL o XSS. El análisis revela varias vulnerabilidades que podrían permitir a un atacante comprometer la seguridad de los datos de los usuarios, lo que te permite recomendar parches y mejoras en la seguridad de la aplicación.

 ### 12. **Netcat (nc)**

- **Función**: Comunicación directa con puertos de red.
- **Descripción**: Netcat es una herramienta de red extremadamente flexible que permite crear conexiones TCP/UDP para leer y escribir datos. Se usa comúnmente para depuración y pruebas de servicios de red.
- **Caso de uso:**
  - **Ejemplo**: Necesitas verificar si un servidor está aceptando conexiones en un puerto específico. Ejecutas `nc -zv 192.168.1.100 80` para probar si el puerto 80 (HTTP) está abierto y responde. Esto es útil para comprobar si un servidor web está funcionando correctamente.

### 13. **NBTScan**

- **Función**: Escaneo de NetBIOS en redes Windows.
- **Descripción**: NBTScan es una herramienta de línea de comandos utilizada para escanear redes en busca de información NetBIOS, que es el sistema de nombres utilizado en redes Windows para compartir recursos.
- **Caso de uso:**
  - **Ejemplo**: Estás auditando una red Windows y necesitas identificar todos los dispositivos que están compartiendo recursos a través de NetBIOS. Usas `nbtscan 192.168.1.0/24` para escanear la red y obtener una lista de nombres NetBIOS, direcciones IP y nombres de host de todos los dispositivos. Esto ayuda a identificar recursos compartidos no autorizados.

### 14. **Angry IP Scanner**

- **Función**: Escaneo rápido de IP y puertos.
- **Descripción**: Angry IP Scanner es una herramienta fácil de usar para escanear rangos de IP y puertos en busca de hosts activos. Es conocida por su velocidad y simplicidad.
- **Caso de uso:**
  - **Ejemplo**: Necesitas hacer un escaneo rápido de todos los dispositivos activos en un rango de IP. Usas `Angry IP Scanner` para escanear el rango `192.168.1.0/24` y obtener una lista de IPs activas y los puertos abiertos en cada dispositivo. Esto es útil para una rápida auditoría de red.

### 5. **Hping**1

- **Función**: Generación de paquetes TCP/IP personalizados y pruebas de red.

- **Descripción**: Hping es una herramienta de línea de comandos utilizada para la creación de paquetes TCP/IP personalizados. Se puede usar para realizar pruebas de seguridad, como ataques de denegación de servicio (DoS) o escaneo de puertos ocultos.

- Caso de uso

  :

  - **Ejemplo**: Quieres probar la resistencia de un servidor contra un ataque SYN flood (un tipo de ataque DoS). Usas `hping3 -S -p 80 --flood 192.168.1.100` para enviar una gran cantidad de paquetes SYN al puerto 80 del servidor, lo que te permite evaluar su capacidad para manejar este tipo de ataque.

### 6. **Masscan**

- **Función**: Escaneo masivo de puertos.

- **Descripción**: Masscan es una herramienta de escaneo de puertos extremadamente rápida que puede escanear toda la Internet en cuestión de minutos, según la configuración de red. Es ideal para tareas de escaneo masivo.

- Caso de uso

  :

  - **Ejemplo**: Necesitas escanear rápidamente un rango de IP muy grande (por ejemplo, un bloque /8) para identificar puertos abiertos en millones de direcciones IP. Usas `masscan -p80,443 0.0.0.0/0` para buscar servidores web que respondan en esos puertos. Esta herramienta es útil para auditorías a gran escala.

Estas herramientas permiten realizar una auditoría exhaustiva, cubriendo diferentes aspectos de los sistemas, desde la infraestructura de red hasta la seguridad de las aplicaciones y el cumplimiento normativo. Dependiendo de los objetivos específicos de la auditoría, se pueden utilizar diferentes combinaciones de estas herramientas.

---

**Notas:**

[^1]: Se denomina *latencia* al tiempo de respuesta existente entre dos equipos. El comando ping mide el  tiempo que tarda un equipo de destino en devolver una respuesta ante el envío de paquetes de datos.









### 7. **Wireshark**

- **Función**: Captura y análisis de tráfico de red.

- **Descripción**: Wireshark es una herramienta gráfica que permite capturar y analizar tráfico de red en tiempo real. Es utilizada para el diagnóstico de redes y análisis profundo de paquetes.

- Caso de uso

  :

  - **Ejemplo**: Estás investigando un posible ataque en la red. Usas `Wireshark` para capturar el tráfico en una interfaz de red durante un período de tiempo y luego analizas los paquetes para identificar patrones sospechosos, como intentos de escaneo de puertos o transferencias de datos no autorizadas.

### 8. **Zenmap**

- **Función**: Interfaz gráfica para Nmap.

- **Descripción**: Zenmap es la interfaz gráfica de usuario (GUI) de Nmap, que facilita el uso de Nmap para usuarios menos experimentados y proporciona una forma visual de revisar los resultados de los escaneos.

- Caso de uso

  :

  - **Ejemplo**: Quieres hacer un escaneo de red usando Nmap, pero prefieres una interfaz gráfica para ver los resultados. Usas `Zenmap` para configurar el escaneo y analizar visualmente los resultados, lo que facilita la identificación de posibles vulnerabilidades sin necesidad de usar la línea de comandos.

### 9. **OpenVAS**

- **Función**: Escaneo de vulnerabilidades.

- **Descripción**: OpenVAS es un sistema completo de escaneo de vulnerabilidades que permite identificar problemas de seguridad en dispositivos y servicios de red.

- Caso de uso

  :

  - **Ejemplo**: Estás realizando una auditoría de seguridad en la red de una empresa. Ejecutas un escaneo con `OpenVAS` para detectar vulnerabilidades conocidas en servidores, routers y otros dispositivos de red. El informe te proporciona un listado detallado de problemas y recomendaciones para mitigarlos.

### 10. **Nikto**

- **Función**: Escaneo de vulnerabilidades en servidores web.

- **Descripción**: Nikto es una herramienta de escaneo que se centra en detectar vulnerabilidades en servidores web. Busca problemas como configuraciones inseguras, versiones desactualizadas de software y archivos peligrosos.

- Caso de uso

  :

  - **Ejemplo**: Estás evaluando la seguridad de un servidor web. Ejecutas `Nikto` contra el servidor (`nikto -h http://www.ejemplo.com`) para identificar posibles vulnerabilidades en la configuración del servidor web, como directorios expuestos o software desactualizado.

Estas herramientas son esenciales para administradores de sistemas y profesionales de la seguridad informática que buscan asegurar sus redes, identificar posibles vulnerabilidades y realizar auditorías de seguridad efectivas. Cada herramienta tiene su propio conjunto de características que la hacen adecuada para diferentes tipos de análisis y auditorías de red.
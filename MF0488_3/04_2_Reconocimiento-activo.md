# Reconocimiento activo

El reconocimiento activo implica interactuar directamente con el dominio o sistema objetivo para obtener información detallada sobre su infraestructura, servicios, puertos abiertos, vulnerabilidades, etc. A continuación, se presentan algunas de las herramientas más utilizadas para realizar este tipo de reconocimiento:

### 1. **Nmap**
   - **Descripción**: Es una de las herramientas más populares para el escaneo de redes. Permite descubrir hosts, servicios, versiones de software, sistemas operativos, y más.
   - **Uso**: Puedes utilizar comandos como `nmap -sS` para un escaneo SYN, `nmap -O` para detección de sistema operativo, y `nmap -sV` para detección de versiones de servicios.

### 2. **Nikto**
   - **Descripción**: Es un escáner de servidores web que busca vulnerabilidades comunes, configuraciones inseguras, y archivos peligrosos. Es útil para analizar la seguridad de aplicaciones web.
   - **Uso**: Ejecuta `nikto -h <URL>` para escanear un sitio web.

### 3. **Metasploit**
   - **Descripción**: Es un framework de explotación que incluye herramientas para realizar reconocimiento, escaneo de vulnerabilidades, y pruebas de penetración. Metasploit puede ser utilizado para identificar y explotar vulnerabilidades en un sistema.
   - **Uso**: Dentro de Metasploit, puedes usar módulos como `auxiliary/scanner/portscan/tcp` para escaneo de puertos o `auxiliary/scanner/http/title` para identificar títulos de páginas web.

### 4. **OpenVAS**
   - **Descripción**: Es un escáner de vulnerabilidades de código abierto que permite identificar fallos de seguridad en sistemas y redes.
   - **Uso**: Requiere instalación y configuración. Una vez configurado, puedes ejecutar escaneos contra objetivos específicos y generar reportes de vulnerabilidades.

### 5. **Dirb/Dirbuster**
   - **Descripción**: Herramientas para realizar fuerza bruta en directorios y archivos web ocultos. Permiten descubrir rutas no indexadas o páginas de administración.
   - **Uso**: Ejemplo: `dirb http://example.com/` para escanear directorios comunes en un sitio web.

### 6. **SQLmap**
   - **Descripción**: Es una herramienta de código abierto que automatiza el proceso de detección y explotación de vulnerabilidades SQL Injection en aplicaciones web.
   - **Uso**: Puedes ejecutarla con un comando como `sqlmap -u "http://example.com/index.php?id=1" --dbs` para listar las bases de datos.

### 7. **Hydra**
   - **Descripción**: Es una herramienta de fuerza bruta para atacar servicios de autenticación. Puede ser utilizada para intentar acceder a servicios como SSH, FTP, HTTP, entre otros.
   - **Uso**: Ejemplo: `hydra -l admin -P /path/to/passwords.txt ftp://example.com` para intentar credenciales en un servidor FTP.

### 8. **ZAP (OWASP Zed Attack Proxy)**
   - **Descripción**: Es una herramienta de seguridad web que permite realizar pruebas de penetración en aplicaciones web, incluyendo el escaneo de vulnerabilidades y la manipulación de peticiones HTTP.
   - **Uso**: Tiene una interfaz gráfica donde puedes configurar los escaneos y visualizar los resultados.

### 9. **Burp Suite**
   - **Descripción**: Es una plataforma para pruebas de seguridad de aplicaciones web. Permite interceptar tráfico, realizar análisis dinámico de seguridad, y explotar vulnerabilidades.
   - **Uso**: Burp Suite se utiliza generalmente como un proxy para interceptar y modificar tráfico entre el cliente y el servidor.

### 10. **Wpscan**
   - **Descripción**: Es una herramienta diseñada específicamente para escanear sitios web que utilizan WordPress, en busca de vulnerabilidades conocidas, temas y plugins inseguros, y usuarios débiles.
   - **Uso**: Puedes escanear un sitio WordPress usando `wpscan --url http://example.com`.

### 11. **XRay**
   - **Descripción**: Es una herramienta avanzada que se utiliza para escaneo de vulnerabilidades en aplicaciones web, compatible con múltiples protocolos y con la capacidad de identificar una amplia variedad de fallas de seguridad.
   - **Uso**: XRay se ejecuta desde la línea de comandos y se puede integrar en pipelines de CI/CD para escaneo automático.

### 12. **Amass**
   - **Descripción**: Es una herramienta avanzada para el descubrimiento de subdominios y el mapeo de redes de organizaciones. Combina técnicas de reconocimiento activo y pasivo.
   - **Uso**: Puedes usarlo para enumerar subdominios con `amass enum -d example.com`.

### 13. **Gobuster**
   - **Descripción**: Similar a Dirb, Gobuster es una herramienta rápida para hacer fuerza bruta en directorios, subdominios, y archivos, utilizando diccionarios.
   - **Uso**: Ejemplo: `gobuster dir -u http://example.com/ -w /path/to/wordlist.txt`.

Estas herramientas te permiten obtener información detallada y realizar análisis de seguridad en un dominio o sistema, lo que puede ser crucial para identificar posibles vulnerabilidades y evaluar la postura de seguridad del objetivo. Es importante utilizarlas con responsabilidad y siempre obtener el consentimiento adecuado antes de realizar pruebas de penetración.
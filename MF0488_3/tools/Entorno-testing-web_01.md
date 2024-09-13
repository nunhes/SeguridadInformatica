# Entorno de pruebas de seguridad

Crear un entorno de pruebas de seguridad en VirtualBox es una excelente manera de aprender y practicar sin poner en riesgo sistemas reales. A continuación, te proporcionaré un paso a paso para diseñar una red virtual con un servidor web Linux y una máquina atacante Kali Linux, junto con recomendaciones sobre las aplicaciones web que puedes instalar para realizar pruebas.

### **1. Configuración del Entorno Virtual en VirtualBox**

#### **A. Crear la Red Virtual**

1. **Configurar la Red en VirtualBox**:
   - Abre VirtualBox y ve a **Archivo > Preferencias > Red**.
   - Selecciona la pestaña **Redes de solo anfitrión** (**Host-only Networks**).
   - Crea una nueva red de solo anfitrión (**Host-Only Adapter**), que permitirá que las máquinas virtuales se comuniquen entre sí y con el host (tu máquina física), pero no tendrán acceso a internet, lo que es ideal para un entorno seguro de pruebas.
   - Asegúrate de que la configuración de DHCP esté activada para asignar IPs automáticamente.

2. **Configurar Adaptadores de Red en las Máquinas Virtuales**:
   - En cada máquina virtual (servidor web y Kali Linux), ve a **Configuración > Red**.
   - Configura **Adaptador 1** como **Host-Only Adapter** y selecciona la red que creaste anteriormente.
   - Si necesitas que la máquina atacante (Kali Linux) tenga acceso a internet para instalar herramientas adicionales, puedes configurar un **Adaptador 2** en modo **NAT**.

#### **B. Crear las Máquinas Virtuales**

1. **Máquina Virtual 1: Kali Linux (Atacante)**:
   - Descarga la ISO de Kali Linux desde su [sitio oficial](https://www.kali.org/downloads/).
   - Crea una nueva máquina virtual en VirtualBox con la configuración recomendada por el asistente (2 GB de RAM, 2 CPUs, 20 GB de disco).
   - Monta la ISO de Kali Linux y sigue el proceso de instalación.
   - Configura el adaptador de red como **Host-Only** y, opcionalmente, un segundo adaptador en **NAT**.

2. **Máquina Virtual 2: Servidor Web Linux (Objetivo)**:
   - Descarga la ISO de Ubuntu Server o Debian, ambas son buenas opciones.
   - Crea una nueva máquina virtual en VirtualBox con 1 GB de RAM, 1 CPU, y 20 GB de disco.
   - Monta la ISO de la distribución Linux elegida y sigue el proceso de instalación.
   - Durante la instalación, selecciona la opción de instalar el servidor SSH y el servidor web (Apache).
   - Configura el adaptador de red como **Host-Only**.

### **2. Configuración del Servidor Web (Objetivo)**

#### **A. Instalar y Configurar Apache**

1. **Instalar Apache**:
   ```bash
   sudo apt-get update
   sudo apt-get install apache2
   ```

2. **Verificar que Apache está funcionando**:
   - Después de la instalación, Apache debería iniciarse automáticamente.
   - Abre un navegador web en tu máquina anfitrión y accede a `http://[IP del servidor web]` para ver la página de bienvenida de Apache.

#### **B. Instalar Aplicaciones Web Vulnerables para Pruebas**

1. **DVWA (Damn Vulnerable Web Application)**:
   - **Instalación**:
     ```bash
     sudo apt-get install git
     cd /var/www/html
     sudo git clone https://github.com/digininja/DVWA.git
     sudo chmod -R 777 /var/www/html/DVWA/
     sudo cp /var/www/html/DVWA/config/config.inc.php.dist /var/www/html/DVWA/config/config.inc.php
     sudo apt-get install php php-mysqli php-gd
     sudo service apache2 restart
     ```
   - **Acceso**: `http://[IP del servidor web]/DVWA`

2. **OWASP Mutillidae II**:
   - **Instalación**:
     ```bash
     cd /var/www/html
     sudo git clone https://github.com/webpwnized/mutillidae.git
     sudo chmod -R 777 /var/www/html/mutillidae/
     sudo service apache2 restart
     ```
   - **Acceso**: `http://[IP del servidor web]/mutillidae`

3. **WebGoat**:
   - **Instalación**:
     ```bash
     sudo apt-get install default-jdk maven
     cd /opt
     sudo git clone https://github.com/WebGoat/WebGoat.git
     cd WebGoat
     sudo mvn clean install
     sudo java -jar webgoat-server/target/webgoat-server-*.jar
     ```
   - **Acceso**: `http://[IP del servidor web]:8080/WebGoat`

4. **bWAPP (Buggy Web Application)**:
   - **Instalación**:
     ```bash
     cd /var/www/html
     sudo git clone https://github.com/snoopysecurity/bwapp.git
     sudo chmod -R 777 /var/www/html/bwapp/
     sudo service apache2 restart
     ```
   - **Acceso**: `http://[IP del servidor web]/bwapp`

### **3. Configuración de Kali Linux (Atacante)**

#### **A. Instalar Herramientas Adicionales**
Kali Linux viene con una gran cantidad de herramientas preinstaladas, pero puedes instalar adicionales si lo necesitas.

1. **Ejemplo de instalación de Nikto**:
   ```bash
   sudo apt-get install nikto
   ```

2. **Ejemplo de instalación de Gobuster**:
   ```bash
   sudo apt-get install gobuster
   ```

#### **B. Configuración Adicional**
- Puedes configurar un entorno de trabajo para cada aplicación que pruebes, por ejemplo, tener diferentes directorios de trabajo para DVWA, WebGoat, etc.

### **4. Realizar Pruebas de Seguridad**

Una vez que todo esté configurado:

1. **Pruebas de Reconocimiento y Escaneo**:
   - Utiliza herramientas como `Nmap` y `Nikto` desde Kali Linux para escanear el servidor web y descubrir qué servicios están corriendo y qué vulnerabilidades pueden existir.

   ```bash
   nmap -sS -sV [IP del servidor web]
   nikto -h http://[IP del servidor web]
   ```

2. **Pruebas de Explotación**:
   - Usa `SQLmap` para buscar y explotar inyecciones SQL en DVWA o Mutillidae.
   - Utiliza `Metasploit` para explotar vulnerabilidades específicas si encuentras alguna.
    
   ```bash
   sqlmap -u "http://[IP del servidor web]/DVWA/vulnerabilities/sqli/?id=1&Submit=Submit" --dbs
   ```

3. **Post-explotación**:
   - Si obtienes acceso a través de una vulnerabilidad, utiliza herramientas como `Meterpreter` (Metasploit) para escalar privilegios y moverte lateralmente.

4. **Análisis y Reporte**:
   - Documenta tus hallazgos, los métodos utilizados, y las recomendaciones para corregir las vulnerabilidades.
   - Puedes usar Dradis en Kali para organizar tus hallazgos y generar un reporte estructurado.

### **5. Mantenimiento del Entorno**

- **Snapshots**: Crea instantáneas (snapshots) en VirtualBox de tus máquinas virtuales antes y después de realizar pruebas para poder revertir cambios fácilmente.
- **Backup**: Mantén copias de seguridad de tu entorno en caso de que necesites restaurar el estado inicial.

---

Este entorno te proporcionará un lugar seguro para practicar habilidades de seguridad informática y probar diferentes técnicas y herramientas sin riesgo para sistemas reales. Recuerda siempre mantener este entorno aislado de redes reales y utilizarlo solo con fines educativos y de mejora profesional.
Recon-ng es una herramienta de reconocimiento y recolección de información automatizada utilizada principalmente en el ámbito de la seguridad informática y el hacking ético. Su objetivo principal es facilitar la fase de reconocimiento en pruebas de penetración, lo que implica recolectar información sobre un objetivo (como una organización, un dominio o una red) antes de llevar a cabo ataques más específicos.

### ¿Para qué sirve Recon-ng?

Recon-ng es utilizada para:
1. **Recolección de Información:** Permite obtener información básica y avanzada sobre un objetivo, como dominios, subdominios, direcciones IP, registros DNS, correos electrónicos, usuarios, y más.
2. **Automatización del Reconocimiento:** Recon-ng automatiza muchos procesos de recolección de información que de otro modo tendrían que hacerse manualmente, ahorrando tiempo y esfuerzo.
3. **Integración con APIs:** La herramienta puede integrarse con diversas APIs públicas y privadas (por ejemplo, Shodan, VirusTotal, etc.) para ampliar la cantidad de datos recolectados.
4. **Generación de Reportes:** Permite exportar la información recolectada en formatos como JSON, XML, CSV, entre otros, lo cual es útil para análisis posteriores.

### ¿Cómo se usa Recon-ng?

Recon-ng tiene una interfaz de línea de comandos similar a Metasploit, lo que facilita su uso para quienes están familiarizados con otras herramientas de seguridad. Aquí te dejo un flujo básico de uso:

1. **Instalación:**
   - Recon-ng se instala fácilmente usando pip:
     ```bash
     pip install recon-ng
     ```

2. **Inicio:**
   - Para iniciar la herramienta, simplemente ejecuta:
     ```bash
     recon-ng
     ```

3. **Configuración del Workspace:**
   - Puedes configurar un espacio de trabajo (workspace) específico para cada objetivo, lo que te permite organizar la información recolectada:
     ```bash
     workspaces create <nombre_del_workspace>
     workspaces select <nombre_del_workspace>
     ```

4. **Módulos:**
   - Recon-ng cuenta con una variedad de módulos para realizar tareas específicas, como la recolección de dominios, la búsqueda de subdominios, la obtención de direcciones IP, entre otros.
   - Para ver los módulos disponibles:
     ```bash
     modules search
     ```
   - Para utilizar un módulo:
     ```bash
     modules load <nombre_del_módulo>
     ```

5. **Ejecutar Módulos:**
   - Una vez cargado un módulo, se deben configurar los parámetros necesarios:
     ```bash
     set SOURCE <tu_objetivo>
     run
     ```

6. **Ver Resultados:**
   - Los resultados obtenidos pueden visualizarse directamente en la terminal o exportarse para un análisis más detallado:
     ```bash
     show hosts
     show contacts
     ```

### Casos de Ejemplo

1. **Recolección de Subdominios:**
   - Un uso común es obtener una lista de subdominios asociados a un dominio principal:
     ```bash
     modules load recon/domains-hosts/shodan_hostname
     set SOURCE example.com
     run
     ```

2. **Buscar Registros DNS:**
   - Para buscar registros DNS asociados a un dominio:
     ```bash
     modules load recon/domains-hosts/bing_domain_web
     set SOURCE example.com
     run
     ```

3. **Obtener Información de Contacto:**
   - Se puede utilizar para extraer correos electrónicos asociados a un dominio:
     ```bash
     modules load recon/domains-contacts/whois_pocs
     set SOURCE example.com
     run
     ```

Recon-ng es una herramienta poderosa que, aunque sencilla de usar, requiere un entendimiento sólido de las técnicas de recolección de información y los posibles impactos éticos y legales de su uso. Es esencial utilizarla con responsabilidad y en contextos donde se tenga autorización para realizar pruebas de seguridad.
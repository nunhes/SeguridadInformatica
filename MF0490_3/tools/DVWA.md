# Damn Vulnerable Web Application

Para resolver un taller de pentesting entre una máquina virtual **Kali Linux** (como atacante), una máquina **Metasploitable2** (como víctima), y la aplicación web **DVWA** (Damn Vulnerable Web Application), puedes seguir estos pasos:

### 1. **Preparativos iniciales**
   - **Configuración de red**: Asegúrate de que tanto la máquina de Kali Linux como la de Metasploitable2 están en la misma red (por ejemplo, en modo **NAT** o **Adaptador puente** en VirtualBox o VMware). Puedes verificarlo con el comando `ifconfig` en ambas máquinas para comprobar que las IP pertenecen a la misma subred.
   - **Instalar DVWA**: Metasploitable2 ya viene con DVWA instalado por defecto. Puedes acceder a DVWA desde el navegador de tu máquina Kali accediendo a la IP de Metasploitable2, seguido del puerto 80:
     ```
     http://[IP_de_Metasploitable2]/dvwa
     ```
     - Las credenciales por defecto para DVWA son: 
       - **Usuario**: admin
       - **Contraseña**: password

### 2. **Configuración de DVWA**
   - Una vez dentro de DVWA, debes configurar la seguridad en un nivel bajo o ajustarla según lo que quieras practicar. Ve a la pestaña **DVWA Security** y elige el nivel de seguridad adecuado (por ejemplo, "low" para vulnerabilidades simples).
   - Asegúrate también de que la base de datos está configurada correctamente. Puedes ir a **DVWA Setup** y hacer clic en "Create/Reset Database".

### 3. **Fases del Pentesting**

   #### **a) Reconocimiento**
   Usa herramientas de Kali Linux para identificar la vulnerabilidad de la aplicación y otros servicios corriendo en Metasploitable2:

   - **nmap**: Escanea la máquina víctima para identificar puertos abiertos y servicios activos.
     ```bash
     nmap -A [IP_de_Metasploitable2]
     ```

   #### **b) Análisis de vulnerabilidades en DVWA**
   - Explora los diferentes módulos de DVWA para probar vulnerabilidades comunes como:
     - **SQL Injection**: Haz pruebas en el campo de inicio de sesión en el módulo de SQL Injection para verificar si puedes inyectar consultas maliciosas.
       - Prueba inyectar la consulta `' OR '1'='1' -- ` en el campo de usuario o contraseña.
       
     - **File Upload**: Intenta cargar un archivo malicioso (por ejemplo, un shell PHP) usando el módulo de "File Upload". Esto te permitirá ejecutar comandos en el servidor si la carga no tiene validación suficiente.

     - **Command Injection**: Usa el módulo de **Command Injection** para intentar ejecutar comandos del sistema en el servidor. Prueba inyectar comandos como `; ls` o `; whoami`.

   #### **c) Explotación**
   - Si logras explotar alguna vulnerabilidad (por ejemplo, subiendo un web shell o realizando una inyección de comandos), puedes obtener acceso a la máquina Metasploitable2.

   - **Web Shell**: Si subiste un web shell exitosamente, accede a él mediante el navegador. Esto te permitirá ejecutar comandos en el servidor. Por ejemplo:
     ```
     http://[IP_de_Metasploitable2]/dvwa/hackable/uploads/shell.php
     ```

   - **Comandos remotos**: Utiliza comandos para obtener más información del sistema o para escalar privilegios. Prueba ejecutar:
     ```bash
     whoami
     uname -a
     ```

   #### **d) Post-explotación**
   - Tras obtener acceso al sistema, intenta:
     - **Escalación de privilegios**: Investiga si puedes elevar tus privilegios para convertirte en root.
     - **Pivoting**: Usa el acceso obtenido para explorar otros servicios o máquinas en la red.

### 4. **Herramientas adicionales**
   - **Burp Suite**: Úsalo para interceptar las solicitudes HTTP y analizar las respuestas de DVWA. Puedes modificar las solicitudes para realizar ataques como inyección de SQL o XSS.
   - **SQLmap**: Para automatizar ataques de inyección SQL.
     ```bash
     sqlmap -u "http://[IP_de_Metasploitable2]/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --dbs
     ```

### 5. **Documenta los resultados**
Registra todas las vulnerabilidades encontradas, los métodos de explotación utilizados y las posibles soluciones para mitigar esos problemas en un entorno real.

Con estos pasos, podrás realizar un análisis completo y explotar vulnerabilidades de la aplicación DVWA en Metasploitable2 usando Kali Linux.

---



Sí, puedes usar un ataque de diccionario en el contexto de pentesting con **Kali Linux** contra la máquina **Metasploitable2** y la aplicación web **DVWA**. Hay varias áreas donde un ataque de diccionario podría ser útil:

### 1. **Ataque de fuerza bruta en DVWA (Módulo Brute Force)**

En **DVWA**, hay un módulo específico para pruebas de fuerza bruta llamado **"Brute Force"**. Puedes usar un ataque de diccionario para intentar adivinar las credenciales de usuario (por ejemplo, el campo de nombre de usuario y contraseña).

#### Herramienta recomendada: **Hydra**

Hydra es una herramienta de Kali Linux que puede realizar ataques de diccionario contra varios servicios, incluyendo formularios web como los que se encuentran en DVWA.

#### Pasos para ejecutar un ataque de diccionario con Hydra:

1. **Identificar el formulario de login**: 
   - Navega hasta la página de login de DVWA para identificar el formulario y los campos que se utilizarán para el ataque (nombre de usuario, contraseña y el botón de envío).

   URL típica del login de DVWA:
   ```
   http://[IP_de_Metasploitable2]/dvwa/login.php
   ```

2. **Configurar Hydra**: 
   Una vez identificado el formulario, puedes lanzar un ataque de fuerza bruta con Hydra. A continuación se muestra un ejemplo básico del comando:

   ```bash
   hydra -l admin -P /ruta/al/diccionario.txt [IP_de_Metasploitable2] http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:Login failed"
   ```
   - **-l admin**: Especifica el nombre de usuario fijo (en este caso, "admin").
   - **-P /ruta/al/diccionario.txt**: Especifica la ruta al archivo de diccionario (lista de contraseñas).
   - **http-post-form**: Indica que estamos usando un formulario de envío tipo POST.
   - **/dvwa/login.php**: Es la ruta de la página de login.
   - **username=^USER^&password=^PASS^**: Define los campos que Hydra intentará completar con el usuario y las contraseñas del diccionario.
   - **Login=Login**: Nombre del botón de envío.
   - **Login failed**: Mensaje de error que aparece cuando la autenticación falla.

3. **Monitorear el ataque**: Hydra comenzará a probar las combinaciones de usuario y contraseñas del diccionario hasta encontrar una válida o hasta que finalice el diccionario.

### 2. **Ataque de diccionario en servicios SSH (Metasploitable2)**

Otra opción es realizar un ataque de diccionario contra el servicio **SSH** de la máquina **Metasploitable2**. SSH es un servicio que suele estar activo por defecto en Metasploitable2, y es un objetivo común para ataques de fuerza bruta.

#### Pasos para el ataque de diccionario contra SSH:

1. Verifica que **SSH** está activo en Metasploitable2 usando **nmap**:
   ```bash
   nmap -p 22 [IP_de_Metasploitable2]
   ```

2. Si el puerto 22 está abierto, lanza el ataque de diccionario con **Hydra**:
   ```bash
   hydra -l root -P /ruta/al/diccionario.txt ssh://[IP_de_Metasploitable2]
   ```
   - **-l root**: Especifica que estás probando el usuario "root".
   - **-P /ruta/al/diccionario.txt**: Especifica el archivo de diccionario de contraseñas.
   - **ssh://[IP_de_Metasploitable2]**: Indica que el servicio que se está atacando es SSH en la máquina Metasploitable2.

3. Hydra intentará conectarse al servicio SSH utilizando el nombre de usuario "root" y todas las contraseñas del diccionario hasta encontrar una coincidencia.

### 3. **Consideraciones y consejos**
   - **Diccionarios**: Existen varios diccionarios de contraseñas disponibles en Kali Linux, por ejemplo `/usr/share/wordlists/rockyou.txt`, que es uno de los más conocidos.
   - **Tiempo de ejecución**: Dependiendo del tamaño del diccionario y la complejidad de la contraseña, el ataque puede tardar más o menos tiempo.
   - **Seguridad del nivel de DVWA**: Asegúrate de que el nivel de seguridad de DVWA está en **"low"** o **"medium"**, ya que en niveles más altos puede haber protecciones contra ataques de fuerza bruta (por ejemplo, bloqueo de la cuenta después de varios intentos fallidos).

### 4. **Mitigación de ataques de diccionario**
   Después de realizar el ataque y obtener acceso, considera analizar formas de mitigar este tipo de ataques:
   - Implementación de **CAPTCHA** en los formularios de autenticación.
   - Limitar el número de intentos fallidos.
   - Requerir contraseñas complejas.
   - Usar autenticación de dos factores (2FA).

### Conclusión
El ataque de diccionario es una técnica efectiva en entornos vulnerables como DVWA y Metasploitable2. Usar herramientas como **Hydra** para atacar formularios de login y servicios como **SSH** es un enfoque común en pentesting.

----



Sí, si no conoces el nombre de usuario, también puedes usar un ataque de diccionario para probar diferentes combinaciones de nombres de usuario y contraseñas. La herramienta **Hydra** te permite especificar tanto un diccionario para nombres de usuario como uno para contraseñas.

### Ataque de fuerza bruta para nombres de usuario y contraseñas

Si no tienes el nombre de usuario, puedes usar un diccionario para probar varios posibles usuarios junto con el diccionario de contraseñas. Aquí te dejo cómo hacerlo con **Hydra**.

#### 1. **Ataque contra el formulario de login de DVWA**

Si quieres atacar el formulario de login de DVWA y no conoces ni el nombre de usuario ni la contraseña, puedes usar dos diccionarios: uno para nombres de usuario y otro para contraseñas.

##### Comando de Hydra:
```bash
hydra -L /ruta/al/diccionario_usuarios.txt -P /ruta/al/diccionario_contraseñas.txt [IP_de_Metasploitable2] http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:Login failed"
```

- **-L /ruta/al/diccionario_usuarios.txt**: Especifica el diccionario de nombres de usuario.
- **-P /ruta/al/diccionario_contraseñas.txt**: Especifica el diccionario de contraseñas.
- **http-post-form**: Hydra atacará un formulario POST de login.
- **username=^USER^&password=^PASS^**: Define los campos del formulario para los valores de usuario y contraseña.
- **Login failed**: Texto que indica un intento fallido.

Hydra probará todas las combinaciones posibles de nombres de usuario y contraseñas hasta encontrar una combinación válida.

#### 2. **Ataque contra SSH de Metasploitable2**

También puedes realizar un ataque de diccionario contra el servicio **SSH** si no conoces el nombre de usuario.

##### Comando de Hydra:
```bash
hydra -L /ruta/al/diccionario_usuarios.txt -P /ruta/al/diccionario_contraseñas.txt ssh://[IP_de_Metasploitable2]
```

- **-L /ruta/al/diccionario_usuarios.txt**: Diccionario de posibles nombres de usuario.
- **-P /ruta/al/diccionario_contraseñas.txt**: Diccionario de contraseñas.
- **ssh://[IP_de_Metasploitable2]**: Ataca el servicio SSH en la IP objetivo.

Hydra probará todas las combinaciones de usuarios y contraseñas hasta encontrar una válida.

### Diccionarios comunes en Kali Linux
- Para los nombres de usuario, puedes usar diccionarios como `usernames.txt` que puedes crear o descargar.
- Para las contraseñas, el archivo más común es el diccionario **rockyou.txt** que ya viene instalado en Kali Linux. Puedes descomprimirlo en la siguiente ruta:
  ```bash
  gunzip /usr/share/wordlists/rockyou.txt.gz
  ```

### **Ejemplo de Diccionario de Usuarios**
Puedes crear tu propio diccionario de nombres de usuario basado en los usuarios más comunes o descargar uno. Aquí tienes un ejemplo básico de un archivo `usernames.txt`:

```
admin
root
user
test
guest
administrator
```

### **Consejos**
- **Tamaño del diccionario**: Usar diccionarios muy grandes puede aumentar el tiempo del ataque, así que trata de utilizar listas de usuarios y contraseñas adecuadas al contexto.
- **Configuración de DVWA**: Recuerda que en niveles de seguridad más altos de DVWA, los intentos de login fallidos pueden generar bloqueos temporales o permanentes de la cuenta. Asegúrate de que el nivel de seguridad esté en **"low"** o **"medium"** para evitar protecciones.

### Mitigaciones contra este tipo de ataque
Este ataque demuestra por qué es importante:
- Implementar medidas como **bloqueo de cuenta** después de varios intentos fallidos.
- Usar **nombres de usuario y contraseñas complejas** que no sean fáciles de adivinar.
- Incorporar **CAPTCHA** o autenticación de dos factores (2FA) para reducir la efectividad de los ataques de fuerza bruta.

De esta manera, puedes realizar ataques de diccionario incluso sin conocer el nombre de usuario, probando varias combinaciones con **Hydra**.

---





Sí, **Hydra** puede devolverte solo la combinación válida de nombre de usuario y contraseña cuando se encuentre. Al realizar el ataque, Hydra muestra únicamente los resultados exitosos en la salida, lo que significa que si encuentra una combinación correcta de nombre de usuario y contraseña, te lo notificará en la terminal.

### Ejemplo de salida de Hydra:

Cuando Hydra encuentra una combinación válida, verás algo como esto:

```
[80][http-post-form] host: 192.168.0.10   login: admin   password: password123
```

Este mensaje muestra el host atacado, el nombre de usuario (login) y la contraseña exitosa (password) encontrados.

### Para hacer que Hydra te muestre solo los resultados válidos:

Puedes agregar la opción `-f` (finish) para que Hydra se detenga después de encontrar la primera combinación válida y no siga probando el resto del diccionario.

#### Comando Hydra con opción `-f`:
```bash
hydra -L /ruta/al/diccionario_usuarios.txt -P /ruta/al/diccionario_contraseñas.txt [IP_de_Metasploitable2] http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:Login failed" -f
```

- **-f**: Detiene Hydra tan pronto como encuentra la primera combinación válida.

De esta manera, una vez que Hydra encuentra una combinación correcta, detiene el ataque y te muestra solo la combinación exitosa.

### Resumen:
- Hydra te muestra solo la combinación válida cuando se encuentra.
- Usa la opción **`-f`** para detener el ataque en cuanto se encuentre una coincidencia válida.
  

Esto te permitirá concentrarte solo en las credenciales correctas sin necesidad de revisar una gran cantidad de combinaciones fallidas.
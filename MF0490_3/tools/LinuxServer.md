# Implantación de un Servidor Ubuntu Linux para Servicios Empresariales

Este manual detallado tiene como objetivo guiar la implantación de un servidor central basado en Ubuntu Linux para gestionar servicios empresariales esenciales como correo electrónico, base de datos, políticas de seguridad, copias de seguridad, servicios web, entre otros.

#### **Índice**
1. [Preparación del entorno](#1-preparación-del-entorno)
2. [Instalación y configuración inicial del servidor](#2-instalación-y-configuración-inicial-del-servidor)
3. [Configuración del servidor de correo](#3-configuración-del-servidor-de-correo)
4. [Instalación de servicios de base de datos](#4-instalación-de-servicios-de-base-de-datos)
5. [Implementación de políticas de seguridad](#5-implementación-de-políticas-de-seguridad)
6. [Configuración de copias de seguridad automáticas](#6-configuración-de-copias-de-seguridad-automáticas)
7. [Implementación de servicios web](#7-implementación-de-servicios-web)
8. [Monitorización y control del servidor](#8-monitorización-y-control-del-servidor)

---

### 1. Preparación del entorno

#### 1.1. Requisitos del hardware
Antes de comenzar, asegúrese de que el servidor cumple con los requisitos mínimos de hardware:
- **Procesador**: 2 núcleos mínimo (preferiblemente 4 núcleos o más).
- **Memoria RAM**: 4 GB (preferiblemente 8 GB o más).
- **Almacenamiento**: 100 GB para datos básicos y logs, se recomienda almacenamiento escalable.
- **Conexión de red**: Acceso a una red local y a Internet con IP fija.

#### 1.2. Descargar Ubuntu Server
Descargue la última versión LTS de Ubuntu Server desde el [sitio oficial](https://ubuntu.com/download/server).

#### 1.3. Instalación del sistema operativo
- Prepare un dispositivo USB con Ubuntu Server utilizando una herramienta como **Rufus**.
- Inicie el servidor desde el USB y siga los pasos de instalación.
  - **Configuración de red**: Configure una IP estática para el servidor.
  - **Particionado**: Use particionado LVM para facilitar futuras expansiones.
  - **Usuarios y contraseñas**: Cree un usuario administrador y defina una contraseña segura para `root`.

---

### 2. Instalación y configuración inicial del servidor

#### 2.1. Actualización del sistema
Después de instalar Ubuntu, es importante actualizar el sistema para tener las últimas mejoras de seguridad y rendimiento.

```bash
sudo apt update && sudo apt upgrade -y
```

#### 2.2. Configuración del hostname
Defina un nombre para el servidor (ejemplo: `servidor-empresa`).

```bash
sudo hostnamectl set-hostname servidor-empresa
```

#### 2.3. Configuración de acceso SSH
Instale y configure el acceso SSH seguro.

```bash
sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
```

Opcionalmente, puede deshabilitar el acceso SSH por contraseña y usar autenticación basada en llaves:

```bash
sudo nano /etc/ssh/sshd_config
# Descomentar y modificar las siguientes líneas:
PasswordAuthentication no
PermitRootLogin no
```

Reinicie el servicio SSH:

```bash
sudo systemctl restart ssh
```

#### 2.4. Cortafuegos básico con UFW
Active y configure el cortafuegos UFW para restringir el acceso solo a los servicios necesarios:

```bash
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status
```

---

### 3. Configuración del servidor de correo

Para configurar un servidor de correo, utilizaremos **Postfix** y **Dovecot**.

#### 3.1. Instalación de Postfix
Postfix se encargará del envío de correos.

```bash
sudo apt install postfix
```

Configure el tipo de servidor como "Internet Site" y defina el dominio.

#### 3.2. Instalación de Dovecot
Dovecot gestionará la entrega de correos a los buzones.

```bash
sudo apt install dovecot-imapd dovecot-pop3d
```

Configure Dovecot editando `/etc/dovecot/dovecot.conf` para habilitar IMAP y POP3.

#### 3.3. Seguridad y cifrado (TLS)
Para garantizar la seguridad de las comunicaciones por correo, es esencial configurar SSL/TLS:

- Cree o compre un certificado SSL.
- Configure Postfix y Dovecot para usar el certificado en `/etc/postfix/main.cf` y `/etc/dovecot/conf.d/10-ssl.conf`.

---

### 4. Instalación de servicios de base de datos

Para gestionar bases de datos, utilizaremos **MySQL** o **PostgreSQL** según sus necesidades.

#### 4.1. Instalación de MySQL

```bash
sudo apt install mysql-server
```

Asegure el servidor ejecutando:

```bash
sudo mysql_secure_installation
```

Cree bases de datos y usuarios para sus aplicaciones:

```bash
mysql -u root -p
CREATE DATABASE empresa_db;
CREATE USER 'usuario_db'@'localhost' IDENTIFIED BY 'contraseña_segura';
GRANT ALL PRIVILEGES ON empresa_db.* TO 'usuario_db'@'localhost';
FLUSH PRIVILEGES;
```

#### 4.2. Instalación de PostgreSQL (opcional)

```bash
sudo apt install postgresql postgresql-contrib
```

Configure los usuarios y bases de datos de manera similar.

---

### 5. Implementación de políticas de seguridad

#### 5.1. Configuración de Fail2Ban
Instale Fail2Ban para prevenir ataques de fuerza bruta:

```bash
sudo apt install fail2ban
```

Edite las configuraciones para proteger servicios como SSH y Postfix en `/etc/fail2ban/jail.local`.

#### 5.2. Actualizaciones automáticas de seguridad

Configure actualizaciones automáticas de seguridad para mantener el sistema seguro:

```bash
sudo apt install unattended-upgrades
sudo dpkg-reconfigure --priority=low unattended-upgrades
```

---

### 6. Configuración de copias de seguridad automáticas

#### 6.1. Instalación de rsync
Utilice **rsync** para realizar copias de seguridad incrementales.

```bash
sudo apt install rsync
```

Cree un script para realizar las copias de seguridad periódicamente y agéndelo en **cron**:

```bash
crontab -e
# Ejemplo de cron diario a las 2 am
0 2 * * * /usr/bin/rsync -a /carpeta_origen /carpeta_destino
```

#### 6.2. Herramientas de copia de seguridad adicionales
Herramientas como **Bacula** o **Amanda** son opciones robustas para copias de seguridad en entornos empresariales.

---

### 7. Implementación de servicios web

#### 7.1. Instalación de Apache o Nginx
Instale un servidor web según sus necesidades.

- **Apache**:

```bash
sudo apt install apache2
```

- **Nginx**:

```bash
sudo apt install nginx
```

#### 7.2. Configuración de Virtual Hosts
Cree configuraciones de Virtual Hosts para manejar múltiples sitios web en el servidor.

Para Apache:

```bash
sudo nano /etc/apache2/sites-available/empresa.conf
# Defina los hosts virtuales
```

Habilite el sitio y reinicie Apache:

```bash
sudo a2ensite empresa.conf
sudo systemctl reload apache2
```

---

### 8. Monitorización y control del servidor

#### 8.1. Instalación de herramientas de monitorización
Instale **Nagios** o **Zabbix** para monitorizar el rendimiento y los servicios del servidor.

#### 8.2. Uso de logs
Utilice herramientas como **Logwatch** para recibir informes periódicos de los logs del sistema:

```bash
sudo apt install logwatch
```

---

Este manual cubre los pasos esenciales para configurar un servidor Ubuntu Linux con varios servicios empresariales clave. Puede expandirse según los requerimientos específicos de la empresa.

## Recomendaciones de Hardening para el Servidor Ubuntu Linux

El hardening o endurecimiento de un servidor es esencial para mejorar su seguridad, protegiéndolo de amenazas tanto internas como externas. Aquí te proporciono una serie de acciones que son necesarias para reducir la superficie de ataque, mitigar vulnerabilidades y proteger la confidencialidad, integridad y disponibilidad de los datos.

#### **1. Deshabilitar Servicios Innecesarios**
- **Descripción**: Al instalar Ubuntu y otros paquetes, puede haber servicios habilitados que no se utilicen o que no sean críticos para la operación del servidor.
- **Acción**: Deshabilitar y eliminar cualquier servicio que no sea estrictamente necesario. Esto reduce la cantidad de puntos que un atacante puede explotar.

    ```bash
    sudo systemctl list-unit-files --type=service
    sudo systemctl disable <nombre-del-servicio>
    sudo systemctl stop <nombre-del-servicio>
    ```

- **Justificación**: Menos servicios activos significan menos oportunidades para que un atacante comprometa el sistema. Los servicios innecesarios son posibles puntos de entrada y de exposición de vulnerabilidades.

#### **2. Uso de Autenticación de Llaves SSH y Deshabilitar Acceso por Contraseña**
- **Descripción**: La autenticación basada en llaves es más segura que las contraseñas, ya que las llaves SSH son más complejas y difíciles de descifrar.
- **Acción**: Generar pares de llaves SSH para los usuarios administradores y deshabilitar el inicio de sesión por contraseña en el archivo `/etc/ssh/sshd_config`.

    ```bash
    PasswordAuthentication no
    PermitRootLogin no
    ```

    **Reiniciar SSH**:
    ```bash
    sudo systemctl restart ssh
    ```

- **Justificación**: Los ataques de fuerza bruta para adivinar contraseñas son comunes. Al usar llaves SSH y deshabilitar el acceso por contraseña, se evita este tipo de ataques.

#### **3. Configuración de Cortafuegos (UFW o iptables)**
- **Descripción**: Limitar el tráfico de red sólo a los puertos y servicios estrictamente necesarios.
- **Acción**: Utilizar **UFW** para permitir solo el acceso a servicios esenciales (SSH, HTTP, HTTPS, correo).

    ```bash
    sudo ufw allow OpenSSH
    sudo ufw allow 80/tcp
    sudo ufw allow 443/tcp
    sudo ufw enable
    ```

    También puedes crear reglas más avanzadas con **iptables** si el servidor requiere configuraciones más detalladas.

- **Justificación**: Limitar el tráfico de red reduce la exposición a ataques externos y minimiza las vulnerabilidades al permitir solo el acceso necesario para los usuarios legítimos.

#### **4. Implementar Fail2Ban para Prevenir Ataques de Fuerza Bruta**
- **Descripción**: Fail2Ban monitorea los intentos fallidos de acceso y bloquea las direcciones IP que realizan múltiples intentos fallidos.
- **Acción**: Instalar y configurar Fail2Ban para proteger servicios como SSH y el servidor de correo.

    ```bash
    sudo apt install fail2ban
    sudo systemctl enable fail2ban
    ```

    Editar el archivo `/etc/fail2ban/jail.local` para agregar protección a servicios:

    ```bash
    [sshd]
    enabled = true
    maxretry = 3
    ```

- **Justificación**: Fail2Ban bloquea automáticamente las direcciones IP sospechosas, mitigando ataques de fuerza bruta y ralentizando los intentos de los atacantes de acceder al servidor.

#### **5. Mantener el Sistema y Paquetes Actualizados**
- **Descripción**: Las actualizaciones de seguridad corrigen vulnerabilidades descubiertas en el sistema operativo y el software instalado.
- **Acción**: Habilitar actualizaciones automáticas de seguridad con **unattended-upgrades** para asegurarse de que el sistema siempre esté parcheado.

    ```bash
    sudo apt install unattended-upgrades
    sudo dpkg-reconfigure --priority=low unattended-upgrades
    ```

- **Justificación**: Las vulnerabilidades descubiertas en software antiguo son uno de los principales vectores de ataque. Mantener el servidor actualizado reduce el riesgo de que sea comprometido por exploits conocidos.

#### **6. Configurar AppArmor para Controlar el Acceso a Recursos**
- **Descripción**: **AppArmor** es un sistema de control de acceso basado en políticas que restringe las capacidades de los programas.
- **Acción**: Habilitar y configurar AppArmor para asegurar que los servicios críticos (por ejemplo, MySQL, Apache) solo accedan a los recursos permitidos.

    ```bash
    sudo apt install apparmor apparmor-utils
    sudo systemctl enable apparmor
    ```

    Ver y modificar perfiles de AppArmor:

    ```bash
    sudo aa-status
    sudo aa-enforce <servicio>
    ```

- **Justificación**: AppArmor limita los daños potenciales en caso de que un servicio sea comprometido, restringiendo qué archivos y recursos pueden ser accedidos o modificados por ese servicio.

#### **7. Habilitar Cifrado de Disco con LUKS**
- **Descripción**: El cifrado de disco garantiza que los datos no puedan ser leídos si el servidor es robado o accedido físicamente.
- **Acción**: Usar LUKS para cifrar discos o particiones sensibles, como las que contienen datos de bases de datos o información crítica.

    Para un disco adicional:

    ```bash
    sudo cryptsetup luksFormat /dev/sdX
    sudo cryptsetup luksOpen /dev/sdX nombre_disco
    ```

    Agregue la partición a `/etc/crypttab` para montarla automáticamente al iniciar el sistema.

- **Justificación**: Si el servidor es robado o se pierde el acceso físico al hardware, el cifrado garantiza que los datos no puedan ser leídos sin la clave de cifrado.

#### **8. Aplicar Políticas de Contraseñas Fuertes**
- **Descripción**: Las contraseñas débiles son una de las principales causas de violaciones de seguridad.
- **Acción**: Configurar políticas de contraseñas seguras en `/etc/security/pwquality.conf` para imponer contraseñas con longitud mínima y complejidad.

    ```bash
    minlen = 12
    dcredit = -1
    ucredit = -1
    ocredit = -1
    lcredit = -1
    ```

- **Justificación**: Asegurarse de que los usuarios utilicen contraseñas fuertes y complejas reduce significativamente la posibilidad de que una cuenta sea comprometida.

#### **9. Auditar y Revisar los Logs Regularmente**
- **Descripción**: El análisis de logs permite identificar intentos de ataque y fallos del sistema.
- **Acción**: Utilizar herramientas como **Logwatch** o **Syslog-ng** para revisar los logs de manera automática y recibir informes.

    Instalar Logwatch:

    ```bash
    sudo apt install logwatch
    sudo logwatch --detail high --mailto admin@empresa.com --service all --range today
    ```

- **Justificación**: Revisar los logs permite detectar ataques en curso, vulnerabilidades o configuraciones incorrectas antes de que causen daño.

#### **10. Configurar SELinux (Opcional)**
- **Descripción**: **SELinux** proporciona un mecanismo de seguridad que implementa políticas de control de acceso obligatorio.
- **Acción**: Aunque no está habilitado por defecto en Ubuntu, puedes instalar y configurar SELinux para fortalecer aún más el control sobre los accesos a los archivos y procesos.

    ```bash
    sudo apt install selinux-basics selinux-policy-default auditd
    sudo selinux-activate
    sudo reboot
    ```

- **Justificación**: SELinux permite un control más granular sobre las interacciones entre los procesos y los archivos, lo que dificulta la escalada de privilegios en caso de que un servicio sea comprometido.

---

### **Resumen**

El hardening de un servidor es crucial para garantizar que esté preparado para resistir ataques. Las acciones mencionadas anteriormente, como deshabilitar servicios innecesarios, reforzar la autenticación, aplicar políticas de contraseñas fuertes, y auditar los logs regularmente, son prácticas recomendadas para cualquier servidor en producción.

El objetivo es reducir la superficie de ataque y mitigar posibles vulnerabilidades para proteger los datos y los servicios críticos de la empresa. La combinación de estas acciones contribuye a un entorno más seguro y menos propenso a sufrir intrusiones o fallos de seguridad.

---

https://www.incibe.es/incibe-cert/seminarios-web/hardening-basico-linux
# Herramientas de seguridad nativas de Linux

En Linux, existen varias herramientas nativas diseñadas para ayudar a los usuarios a mantener la seguridad del sistema operativo y proteger la información contra ataques informáticos. Estas herramientas abarcan desde firewalls y sistemas de detección de intrusos hasta utilidades de encriptación y gestión de permisos. A continuación, se presentan algunas de las herramientas más importantes con ejemplos de uso y recursos adicionales.

### 1. **iptables/nftables**
`iptables` y `nftables` son herramientas para la configuración de reglas de firewall en Linux.

#### iptables
```bash
# Ver reglas actuales
sudo iptables -L -v -n

# Permitir tráfico SSH entrante
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# Bloquear todo el tráfico entrante por defecto
sudo iptables -P INPUT DROP

# Guardar configuración
sudo iptables-save > /etc/iptables/rules.v4
```

#### nftables
```bash
# Ver reglas actuales
sudo nft list ruleset

# Permitir tráfico SSH entrante
sudo nft add rule inet filter input tcp dport 22 accept

# Bloquear todo el tráfico entrante por defecto
sudo nft add rule inet filter input drop

# Guardar configuración
sudo nft list ruleset > /etc/nftables.conf
```

### 2. **SELinux (Security-Enhanced Linux)**
SELinux proporciona un mecanismo de control de acceso que es más granulado que los permisos tradicionales de UNIX.

```bash
# Ver estado de SELinux
sestatus

# Enforcing mode (enforzando políticas)
sudo setenforce 1

# Permissive mode (solo reportando)
sudo setenforce 0

# Cambiar modo permanentemente en /etc/selinux/config
sudo vi /etc/selinux/config
# SELINUX=enforcing
```

### 3. **AppArmor**
AppArmor es otra herramienta de control de acceso obligatorio similar a SELinux.

```bash
# Ver estado de AppArmor
sudo aa-status

# Colocar un programa en modo enforcement
sudo aa-enforce /etc/apparmor.d/usr.bin.your_program

# Colocar un programa en modo complain
sudo aa-complain /etc/apparmor.d/usr.bin.your_program
```

### 4. **Fail2ban**
Fail2ban analiza los archivos de registro y prohíbe las direcciones IP que muestran signos maliciosos.

```bash
# Instalar Fail2ban
sudo apt-get install fail2ban

# Configuración básica en /etc/fail2ban/jail.local
sudo vi /etc/fail2ban/jail.local
# [sshd]
# enabled = true
# port = ssh
# logpath = /var/log/auth.log
# maxretry = 5

# Iniciar Fail2ban
sudo systemctl start fail2ban
sudo systemctl enable fail2ban

# Verificar reglas de iptables aplicadas por Fail2ban
sudo iptables -L
```

### 5. **ClamAV**
ClamAV es un antivirus de código abierto para la detección de malware.

```bash
# Instalar ClamAV
sudo apt-get install clamav

# Actualizar bases de datos
sudo freshclam

# Escanear directorio
clamscan -r /home/usuario
```

### 6. **Auditd**
Auditd proporciona auditoría detallada de eventos del sistema.

```bash
# Instalar auditd
sudo apt-get install auditd

# Iniciar auditd
sudo systemctl start auditd
sudo systemctl enable auditd

# Ver eventos de auditoría
sudo ausearch -m avc

# Configuración básica en /etc/audit/audit.rules
sudo vi /etc/audit/audit.rules
# -w /etc/shadow -p wa -k shadow-file
```

### Casos de Uso

1. **Protección contra ataques de fuerza bruta**:
   - **Fail2ban**: Bloquea IPs que intentan demasiadas conexiones fallidas SSH, reduciendo el riesgo de ataques de fuerza bruta.
   ```bash
   sudo fail2ban-client status sshd
   ```

2. **Control de acceso y ejecución de aplicaciones**:
   - **SELinux/AppArmor**: Restringen los permisos de aplicaciones críticas, asegurando que solo realicen operaciones autorizadas.
   ```bash
   sudo semanage fcontext -a -t httpd_sys_content_t "/var/www/html(/.*)?"
   sudo restorecon -Rv /var/www/html
   ```

3. **Detección y eliminación de malware**:
   - **ClamAV**: Permite escanear y eliminar malware en sistemas Linux, protegiendo archivos y datos importantes.
   ```bash
   sudo clamscan -r /home
   ```

### Recursos Adicionales

1. **Documentación y Manuales Oficiales**:
   - [iptables Documentation](https://linux.die.net/man/8/iptables)
   - [nftables Documentation](https://wiki.nftables.org/wiki-nftables/index.php/Main_Page)
   - [SELinux Project](https://selinuxproject.org/page/Main_Page)
   - [AppArmor Documentation](https://gitlab.com/apparmor/apparmor/-/wikis/home)
   - [Fail2ban Documentation](https://www.fail2ban.org/wiki/index.php/Main_Page)
   - [ClamAV Documentation](https://docs.clamav.net/)
   - [Auditd Documentation](https://linux.die.net/man/8/auditd)
2. **Tutoriales y Guías**:
   - [DigitalOcean Community Tutorials](https://www.digitalocean.com/community/tutorials)
   - [LinuxSecurity.com](https://linuxsecurity.com/)
4. **Comunidades y Foros**:
   - [Stack Overflow](https://stackoverflow.com/questions/tagged/linux)
   - [Reddit: r/linux](https://www.reddit.com/r/linux/)
   - [LinuxQuestions.org](https://www.linuxquestions.org/)

Estas herramientas y prácticas te ayudarán a mantener la seguridad de tu sistema Linux y proteger tu información contra posibles ataques.
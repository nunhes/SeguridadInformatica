La gestión de la seguridad informática y de la información es crucial para proteger los sistemas y los datos de accesos no autorizados, ataques y pérdidas. Tanto en Windows como en Linux, existen diversas herramientas de consola que permiten realizar tareas de seguridad de manera eficiente y controlada. A continuación, se presentan algunas de las herramientas y técnicas más comunes para ambos sistemas operativos.

### Herramientas de Consola en Windows

#### PowerShell
PowerShell es una herramienta poderosa para la gestión y automatización de la seguridad en Windows.

1. **Verificar permisos de archivos y carpetas**
   ```powershell
   Get-Acl <ruta_del_archivo_o_carpeta>
   ```

2. **Cambiar permisos de archivos y carpetas**
   ```powershell
   $acl = Get-Acl <ruta_del_archivo_o_carpeta>
   $perm = "DOMAIN\User","FullControl","Allow"
   $accessRule = New-Object System.Security.AccessControl.FileSystemAccessRule $perm
   $acl.SetAccessRule($accessRule)
   Set-Acl <ruta_del_archivo_o_carpeta> $acl
   ```

3. **Auditoría de eventos**
   ```powershell
   Get-EventLog -LogName Security -Newest 100
   ```

4. **Gestión de usuarios y grupos**
   ```powershell
   Get-LocalUser
   New-LocalUser -Name "UserName" -Password (ConvertTo-SecureString "Password" -AsPlainText -Force)
   Add-LocalGroupMember -Group "Administrators" -Member "UserName"
   ```

#### Windows Defender (CMD)
Windows Defender se puede gestionar desde la línea de comandos.

1. **Escaneo rápido**
   ```cmd
   mpcmdrun -scan -scantype 1
   ```

2. **Escaneo completo**
   ```cmd
   mpcmdrun -scan -scantype 2
   ```

3. **Actualizar definiciones**
   ```cmd
   mpcmdrun -signatureUpdate
   ```
4. **Escanear únicamente el sector de arranque del sistema:**
   ```cmd
   mpcmdrun -scan -bootsectorscan
   ```

#### Sysinternals Suite
Una colección de utilidades avanzadas para administración de Windows. Algunos ejemplos:

1. **AccessChk**
   Verifica los permisos de archivos, carpetas y otros objetos.
   ```cmd
   AccessChk.exe -s <ruta_del_archivo_o_carpeta>
   ```

2. **PsExec**
   Ejecuta procesos de forma remota.
   ```cmd
   PsExec.exe \\remotecomputer -u usuario -p contraseña cmd
   ```

### Herramientas de Consola en Linux

#### Comandos Básicos de Seguridad

1. **Permisos de archivos**
   ```bash
   ls -l <nombre_del_archivo>
   chmod 755 <nombre_del_archivo>
   chown usuario:grupo <nombre_del_archivo>
   ```

2. **Auditoría de eventos**
   ```bash
   tail -f /var/log/auth.log
   ausearch -m avc
   ```

#### Firewall (iptables/nftables)

1. **Ver reglas actuales (iptables)**
   ```bash
   sudo iptables -L -v -n
   ```

2. **Agregar regla (iptables)**
   ```bash
   sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
   ```

3. **Ver reglas actuales (nftables)**
   ```bash
   sudo nft list ruleset
   ```

4. **Agregar regla (nftables)**
   ```bash
   sudo nft add rule inet filter input tcp dport 22 accept
   ```

#### Gestión de Usuarios y Grupos

1. **Agregar usuario**
   ```bash
   sudo adduser username
   ```

2. **Agregar usuario a grupo**
   ```bash
   sudo usermod -aG groupname username
   ```

3. **Bloquear usuario**
   ```bash
   sudo usermod -L username
   ```

#### ClamAV (Antivirus)

1. **Instalar ClamAV**
   ```bash
   sudo apt-get install clamav
   ```

2. **Actualizar bases de datos**
   ```bash
   sudo freshclam
   ```

3. **Escanear sistema**
   ```bash
   clamscan -r /home
   ```

### Recomendaciones y Buenas Prácticas

1. **Actualizaciones regulares**: Mantén siempre actualizado el sistema operativo y las aplicaciones para protegerte contra vulnerabilidades conocidas.
2. **Políticas de contraseñas**: Implementa políticas de contraseñas fuertes y obligatorias.
3. **Cifrado de datos**: Usa herramientas de cifrado para proteger datos sensibles.
4. **Monitoreo continuo**: Utiliza herramientas de monitoreo y auditoría para detectar y responder rápidamente a incidentes de seguridad.
5. **Backup regular**: Realiza copias de seguridad regularmente y verifica su integridad y restaurabilidad.
6. **Educación y entrenamiento**: Capacita a los usuarios en prácticas de seguridad y concienciación sobre amenazas comunes.

### Recursos Adicionales

- **Documentación oficial**:
  - [Microsoft PowerShell Documentation](https://docs.microsoft.com/en-us/powershell/)
  - [Linux man pages](https://linux.die.net/man/)
- **Comunidades y foros**:
  - [Stack Overflow](https://stackoverflow.com/)
  - [Reddit](https://www.reddit.com/r/PowerShell/)

Estas herramientas y prácticas ayudarán a gestionar y mejorar la seguridad de tus sistemas, tanto en Windows como en Linux, usando la línea de comandos.


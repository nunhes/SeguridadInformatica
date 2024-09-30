# Entendiendo los logs del sistema

La importancia de conocer que ocurre o ha ocurrido en nuestro sistema Linux radica en entender los **logs del sistema**.
Los archivos **logs en Linux** son los encargados de registrar y recoger en el sistema todos los eventos que se van produciendo en la ejecución de los diferentes procesos, llegando a ser vitales para monitorear y solucionar cualquier problema que nos podamos encontrar o para entender cual ha sido el motivo del o de los mismos.

Los archivos *logs* se suelen encontrar habitualmente en el directorio `/var/log` y en sus subdirectorios y nos muestran esta información precisa y necesaria sobre los eventos del sistema.

## Logs de uso generalizado

Existen multitud de *logs* dado que cualquier aplicación o programa que tengamos puede generar el suyo propio pero los más comunes, propios de la mayoría de los sistemas son los siguientes:

- **alternatives.log**: Archivo de registro que se encarga de «anotar» el histórico de todos los cambios realizados por el comando `update-alternatives`. Este comando es parte del sistema de alternativas Debian, mecanismo que usa para administrar múltiples versiones de un archivo.
  Su importancia es vital dado que permite realizar un seguimiento de todos los cambios realizados a los archivos del sistema a través del `update-alternatives`.
- **anaconda.log**: En este archivo log se almacenan todos los mensajes relativos, que se generan, en la instalación del sistema.
- **auth.log**: Es el encargado de registrar los accesos de autorización del sistema, incluyendo a su vez todos los inicios de sesión de todos los usuarios y los mecanismos usados para la autenticación.
  Al almacenarse tanta información en este archivo log, es recomendable filtrar los datos a consultar. Por ejemplo, para analizar los datos de acceso mediante SSH se puede filtrar usando el comando `grep`.

```
grep sshd /var/log/auth.log | less
```

- **boot.log**: Contiene toda la información que se registra cuando se inicia el sistema, registrándose que servicios se han levantado, que unidades se han montado o las conexiones de red, entre otros.
- **btmp**: En este archivo se almacenan todos los intentos fallidos de acceso al sistema, registrando el usuario, la IP desde que se ha intentado el acceso y la fecha y hora entre algún otro dato más. Para poder acceder al registro `btmp` hace falta ser un administrador y las mejores opciones para que nos muestre la información son los comandos `lastb` y `last`.

```
sudo lastb
last -f /var/log/btmp | more
```

- **cron**: Es el archivo log donde se registran todos los datos generados por el cron del sistema, es decir, los trabajos o tareas programadas. En Debian no existe por defecto este archivo, registrándose estos eventos en `syslog` aunque se puede configurar en el archivo de configuración rsyslog.conf para que genere el logo para cron de forma independiente.
- **cups**: Registra todos los mensajes relacionados con las impresoras y los sistemas de impresión que existen en el sistema. Se almacena en `/var/log/cups/error_log`.
- **daemon.log**: Registra los eventos generados por los `daemon` que son los programas o scripts que corren en segundo plano, normalmente de forma automática tales como el de gdm (Gnome Display Manager), el de Bluetooth HCI o el de la base de datos MySQL.
- **debug**: Detalla los mensajes de depuración tanto del sistema como de las aplicaciones que se encuentran en modo ‘debug’.
- **dmesg**: Contiene la información del buffer de anillo del kernel. Al arrancar el sistema, este imprime por pantalla los dispositivos de hardware que el sistema detecta, y estos registros son los que se pueden consultar mediante el comando `dmesg`.
  Estos registros son reescritos cada vez reiniciamos el sistema.
- **dpkg.log**: Almacena los datos sobre los paquetes que se instalan o desinstalan mediante el comando `dpkg`.
- **fail2ban.log**: Registra los datos sobre el bloqueo o desbloqueo de una IP al intentar acceder a un determinado servicio.
- **faillog**: Registra los intentos fallidos al acceder de los usuarios. En este registro configurable, se puede ver la lista de usuarios, números de fallos permitidos, en que momento se ha registrado, …
  Se puede visualizar con el comando `faillog`.
- **history.log**: Registra una lista concisa de las acciones que ocurrieron al usar `apt` o `apt-get`. Útil para saber qué sucedió y cuándo, pero sin detalles sobre la resolución de problemas.
- **kern.log**: Ofrece información detallada sobre los mensajes del kernel del sistema, proveyendo información útil ante un nuevo kernel o uno personalizado.
- **lastlog**: Muestra la información de acceso más reciente de todos los usuarios.
  Se puede visualizar con el comando `lastlog`.
- **mail.log**: Contiene la información del servidor de correo electrónico que está ejecutándose en el sistema.
- **messages**: Contiene el sistema de mensajes general, incluyendo los mensajes durante el inicio del sistema. Así mismo registra eventos y servicios no iniciados correctamente como son correo, cro, daemon, kern, …
- **rkhunter.log**: La utilidad Rootkit Hunter (rkhunter) comprueba el sistema Ubuntu en busca de puertas traseras (*backdoors*), rastreadores (*sniffers*) y rootkits, que son signos de compromiso de su sistema.
- **secure**: Contiene información relativa a la autenticación y a la autorización de privilegios, por ejemplo, todos los mensajes del servicio sshd, incluidas las autenticaciones fallidas, se encuentran en este log.
- **syslog**: Registra mensajes de diferentes servicios y aplicaciones del sistema. Es un archivo de registro central que contiene la totalidad de logs capturados por rsyslogd. Se puede configurar mediante el archivo `/etc/rsyslog.conf`.
- **term.log**: Registra toda la salida de la terminal, al usar `apt` o `apt-get`, muy útil cuando hay problemas. Destinado a ser legible por humanos, pero incluye muchos detalles adicionales que son innecesarios cuando no hay ningún problema.
- **ufw.log**: Registra las entradas de iptables dado que `ufw` es una interfaz para iptables. Registra fecha, usuario, hora, bloqueo, MAC, IP de donde vienen los datos, puertos de origen, destino, etc.
- **utmp**/wtmp: Contiene los registros de acceso. Con el comando `who` se obtienen los usuarios autenticados en todo momento.
- **user.log**: Contiene información sobre todos los registros a nivel de usuario.
- **wtmp**/utmp: Contiene los registros históricos de acceso y cierre de sesión de los usuarios. Con el comando `last` se tiene acceso al archivo log.
- **Xorg.x.log**: Almacena los mensajes del sistema gráfico de ventanas y sirve fundamentalmente para diagnosticar errores o problemas con este entorno.
- **yum.log**: Almacena los datos sobre los paquetes que se instalan o desinstalan mediante el comando `yum`.

## Logs SMB Samba

El servicio para compartir archivos Samba almacena sus archivos logs en la ubicación `/var/log/samba/`, donde se registra cualquier evento originado en el servicio Samba, como son las operaciones originadas en los archivos y sus directorios: creación, copia, borrado, renombrado; y sus conexiones y autenticaciones.

Samba mantiene tres tipos diferentes de logs en su directorio:

- **log.nmbd**: – mensajes relacionados con la funcionalidad NETBIOS sobre IP de Samba (network stuff)
- **log.smbd**: – mensajes relacionados con la funcionalidad SMB/CIFS de Samba (compartir archivos e impresiones)
- **log.[IP_ADDRESS]**: – mensajes relacionados con solicitudes de servicios desde la dirección IP contenida en el nombre del archivo de registro, por ejemplo, `log.192.168.1.1`.

## Logs Apache/Nginx/MySQL/Lets Encrypt

Cuando el sistema dispone de un servidor web, ya sea Apache o Nginx, muy probablemente dispondrá, a su vez, de un servidor de bases de datos MySQL.
Todos sus eventos se registrarán en los siguientes archivos logs en alguna de estas direcciones:

### Apache

```
/var/log/apache2/
/var/log/httpd/
```

- **access.log**: Registra cada página servida y cada archivo cargado por el servidor web.
- **error.log**: Registra cada uno de los errores y advertencias (*warnings*) que genera el servidor Apache.
- **access_log**: Registra los datos de los usuarios que han accedido al servidor web Apache: páginas, fechas, horas, … de cada IP que ha accedido.

### Nginx

```
/var/log/nginx/
```

- **access.log**: Registra cada página servida y cada archivo cargado por el servidor web.
- **error.log**: Registra cada uno de los errores y advertencias (*warnings*) que genera el servidor Nginx.

### MySQL

```
/var/log/mysql/
```

- **mysql.log**: Registra las sentencias que se envían al servidor.
- **error.log**: Registra los errores detectados al iniciar, ejecutar o parar el servicio, así como los errores originados en las consultas.
- **mysql-slow.log**: Registra información sobre las sentencias que han tardado más tiempo del especificado en la variable del sistema long_query_time.

### Letsencrypt

```
/var/log/letsencrypt/
```

- **letsencrypt.log**: Registra los eventos, errores e información acerca de los certificados de let’s Encrypt.

## Monitorear y revisar los logs periódicamente

El revisar los registros (logs) de forma periódica es una protección añadida que se debe tener al admimistrar un servidor o sistema Linux.

Gran cantidad de ataques llegan a ser visibles con un análisis periódico de los registros, aunque llegue a ser una tarea algo tediosa y porque no decirlo aburrida.

Los logs se encuentran en la carpeta `/var/` pero principalmente en `/var/log/` y sus subidirectorios.

Los principales logs que se deben verificar son:
`/var/log/syslog`: archivo de registro principal para todos los servicios.
`/var/log/message`: archivo de registro de todo el sistema.
`/var/log/auth.log`: archivo de registro de todos los intentos de autenticación.

Si existe un servidor de correos:
`/var/log/mail.log`: registro de los correos electrónicos recientes enviados.

Si existe un entorno web y/o MySQL
`/var/log/apache2/error.log`: registro de errores que genera el servidor Apache.
`/var/log/mysql/error.log`: registro de errores que genera el servidor de base de datos MySQL.

Existen soluciones y comandos para simplificar el trabajo de revisión de los logs.
Se puede configurar `syslog` para enviar registros a un servidor maestro, con una interfaz para leerlos, filtrar, etc.
También es posible utilizar `logwatch` para obtener informes diarios sobre el funcionamiento del sistema.

## Rotación de logs en Linux

Un problema de los archivos logs es que pueden llegar a contener un gran número de registros y datos, llegando a ser casi misión imposible controlarlos.
Para evitar este problema los archivos logs van rotando creando cada tiempo un archivo comprimido y dejando paso al siguiente ciclo.

Se pueden encontrar los archivos `syslog` de la siguiente manera:

```
syslog
syslog.1
syslog.2
...
```

De esta forma los registros más antiguos se van almacenando añadiendo un número al final.

En algunos registros, estos están comprimidos para que ocupen menos,

```
dmesg
dmesg.1.gz
dmesg.2.gz
dmesg.3.gz
...
```

Mediante esta función se consigue evitar que los logs lleguen a saturar el espacio de almacenamiento del sistema.
Esta rotación y su periodicidad es configurable en los archivos de configuración situados en

```
/etc/logrotate.d
```

Si se analiza un archivo tipo, como `rsyslog` se puede ver el siguiente contenido:

```
/var/log/syslog
/var/log/mail.info
/var/log/mail.warn
/var/log/mail.err
/var/log/mail.log
/var/log/daemon.log
/var/log/kern.log
/var/log/auth.log
/var/log/user.log
/var/log/lpr.log
/var/log/cron.log
/var/log/debug
/var/log/messages
{
        rotate 4
        weekly
        missingok
        notifempty
        compress
        delaycompress
        sharedscripts
        postrotate
                /usr/lib/rsyslog/rsyslog-rotate
        endscript
}
/etc/logrotate.d/rsyslog (END)
```



---

**_ref**: [Gestión de logs de Linux: técnicas avanzadas y buenas prácticas - NinjaOne](https://www.ninjaone.com/es/blog/gestion-de-logs-de-linux/#:~:text=La gestión de logs en Linux es fundamental)
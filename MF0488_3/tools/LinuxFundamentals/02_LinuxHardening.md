# Seguridad Linux 

------

Todos los sistemas informáticos tienen un riesgo inherente de intrusión. Algunos presentan más riesgos que otros, como un servidor web con acceso a Internet que aloja múltiples aplicaciones web complejas. Los sistemas Linux también son menos propensos a los virus que afectan a los sistemas operativos Windows y no presentan una superficie de ataque tan grande como los hosts unidos a un dominio de Active Directory. De todos modos, es esencial contar con ciertos fundamentos para proteger cualquier sistema Linux. 

Una de las medidas de seguridad más importantes de los sistemas operativos Linux es mantener actualizados el sistema operativo y los paquetes instalados. Esto se puede lograr con un comando como: 



```shell-session
nunhes@htb[/htb]$ apt update && apt dist-upgrade
```

Si las reglas del firewall no están configuradas adecuadamente a nivel de red, podemos usar el firewall de Linux y/o `iptables` para restringir el tráfico dentro/fuera del host. 

Si SSH está abierto en el servidor, la configuración debe configurarse para no permitir el inicio de sesión con contraseña y no permitir que el usuario raíz inicie sesión a través de SSH. También es importante evitar iniciar sesión y administrar el sistema como usuario root siempre que sea posible y gestionar adecuadamente el control de acceso. El acceso de los usuarios debe determinarse basándose en el principio de privilegio mínimo. Por ejemplo, si un usuario necesita ejecutar un comando como root, entonces ese comando debe especificarse en el `sudoers` configuración en lugar de darles todos los derechos de sudo. Otro mecanismo de protección común que se puede utilizar es `fail2ban`. Esta herramienta cuenta la cantidad de intentos fallidos de inicio de sesión y, si un usuario ha alcanzado el número máximo, el host que intentó conectarse se manejará según la configuración. 

También es importante auditar periódicamente el sistema para garantizar que no existan problemas que puedan facilitar la escalada de privilegios, como un kernel desactualizado, problemas de permisos de usuario, archivos grabables en todo el mundo y trabajos cron mal configurados o servicios mal configurados. Muchos administradores se olvidan de la posibilidad de que algunas versiones del kernel deban actualizarse manualmente. 

Una opción para bloquear aún más los sistemas Linux es `Security-Enhanced Linux` ( `SELinux`) o `AppArmor`. Este es un módulo de seguridad del kernel que se puede utilizar para políticas de control de acceso de seguridad. En SELinux, cada proceso, archivo, directorio y objeto del sistema recibe una etiqueta. Las reglas de política se crean para controlar el acceso entre estos procesos y objetos etiquetados y el núcleo las aplica. Esto significa que el acceso se puede configurar para controlar qué usuarios y aplicaciones pueden acceder a qué recursos. SELinux proporciona controles de acceso muy granulares, como especificar quién puede agregar un archivo o moverlo. 

Además, existen diferentes aplicaciones y servicios como [ Snort ](https://www.snort.org/) , [ chkrootkit ](http://www.chkrootkit.org/) , [ rkhunter ](https://packages.debian.org/sid/rkhunter) , [ Lynis ](https://cisofy.com/lynis/) y otros que pueden contribuir a la seguridad de Linux. Además, se deben realizar algunas configuraciones de seguridad, como por ejemplo: 

- Eliminar o deshabilitar todos los servicios y software innecesarios 
- Eliminar todos los servicios que dependen de mecanismos de autenticación no cifrados 
- Asegúrese de que NTP esté habilitado y que Syslog se esté ejecutando 
- Asegúrese de que cada usuario tenga su propia cuenta 
- Hacer cumplir el uso de contraseñas seguras 
- Configurar la antigüedad de la contraseña y restringir el uso de contraseñas anteriores 
- Bloquear cuentas de usuario después de errores de inicio de sesión 
- Deshabilite todos los archivos binarios SUID/SGID no deseados 

Esta lista está incompleta, ya que la seguridad no es un producto sino un proceso. Esto significa que siempre se deben tomar medidas específicas para proteger mejor los sistemas, y depende de los administradores qué tan bien conocen sus sistemas operativos. Cuanto mejor estén familiarizados los administradores con el sistema y cuanto más capacitados estén, mejores y más seguras serán sus precauciones y medidas de seguridad. 

------

## TCP Wrappers

El contenedor TCP es un mecanismo de seguridad utilizado en los sistemas Linux que permite al administrador del sistema controlar a qué servicios se les permite acceder al sistema. Funciona restringiendo el acceso a ciertos servicios según el nombre de host o la dirección IP del usuario que solicita acceso. Cuando un cliente intenta conectarse a un servicio, el sistema primero consultará las reglas definidas en los archivos de configuración de los contenedores TCP para determinar la dirección IP del cliente. Si la dirección IP coincide con los criterios especificados en los archivos de configuración, el sistema otorgará al cliente acceso al servicio. Sin embargo, si no se cumplen los criterios, se denegará la conexión, proporcionando una capa adicional de seguridad para el servicio. Los contenedores TCP utilizan los siguientes archivos de configuración: 

- `/etc/hosts.allow`
- `/etc/hosts.deny`

En resumen, el `/etc/hosts.allow` El archivo especifica qué servicios y hosts tienen permitido acceder al sistema, mientras que el `/etc/hosts.deny` El archivo especifica qué servicios y hosts no tienen permitido el acceso. Estos archivos se pueden configurar agregando reglas específicas a los archivos. 

#### /etc/hosts.allow 

```shell-session
nunhes@htb[/htb]$ cat /etc/hosts.allow

# Allow access to SSH from the local network
sshd : 10.129.14.0/24

# Allow access to FTP from a specific host
ftpd : 10.129.14.10

# Allow access to Telnet from any host in the inlanefreight.local domain
telnetd : .inlanefreight.local
```

#### /etc/hosts.deny 

```shell-session
nunhes@htb[/htb]$ cat /etc/hosts.deny

# Deny access to all services from any host in the inlanefreight.com domain
ALL : .inlanefreight.com

# Deny access to SSH from a specific host
sshd : 10.129.22.22

# Deny access to FTP from hosts with IP addresses in the range of 10.129.22.0 to 10.129.22.255
ftpd : 10.129.22.0/24
```

Es importante recordar que el orden de las reglas en los archivos es importante. La primera regla que coincida con el servicio y el host solicitados es la que se aplicará. También es importante tener en cuenta que los contenedores TCP no reemplazan a un firewall, ya que están limitados por el hecho de que solo pueden controlar el acceso a los servicios y no a los puertos. 



# Configuración del cortafuegos 

------

El objetivo principal de los firewalls es proporcionar un mecanismo de seguridad para controlar y monitorear el tráfico de red entre diferentes segmentos de red, como redes internas y externas o diferentes zonas de red. Los firewalls desempeñan un papel crucial en la protección de las redes informáticas contra accesos no autorizados, tráfico malicioso y otras amenazas a la seguridad. Linux, al ser un sistema operativo popular utilizado en servidores y otros dispositivos de red, proporciona capacidades de firewall integradas que se pueden utilizar para controlar el tráfico de la red. En otras palabras, pueden filtrar el tráfico entrante y saliente según reglas, protocolos, puertos y otros criterios predefinidos para evitar el acceso no autorizado y mitigar las amenazas a la seguridad. El objetivo específico de la implementación de un firewall puede variar según las necesidades específicas de la organización, como garantizar la confidencialidad, integridad y disponibilidad de los recursos de la red. 

Un ejemplo de la historia de los firewalls de Linux es el desarrollo de la herramienta iptables, que reemplazó a las anteriores herramientas ipchains e ipfwadm. La utilidad iptables se introdujo por primera vez en el kernel Linux 2.4 en 2000 y proporcionó un mecanismo flexible y eficiente para filtrar el tráfico de red. iptables se convirtió en la solución de firewall estándar de facto para sistemas Linux y ha sido ampliamente adoptada por muchas organizaciones y usuarios. 

La utilidad iptables proporcionó una interfaz de línea de comandos simple pero poderosa para configurar reglas de firewall, que podrían usarse para filtrar el tráfico según varios criterios, como direcciones IP, puertos, protocolos y más. iptables fue diseñado para ser altamente personalizable y podría usarse para crear complejos conjuntos de reglas de firewall que podrían proteger contra diversas amenazas de seguridad, como ataques de denegación de servicio (DoS), escaneos de puertos e intentos de intrusión en la red. 

En Linux, la funcionalidad del firewall generalmente se implementa utilizando el marco Netfilter, que es una parte integral del kernel. Netfilter proporciona un conjunto de ganchos que se pueden utilizar para interceptar y modificar el tráfico de la red a medida que pasa por el sistema. La utilidad iptables se usa comúnmente para configurar las reglas del firewall en sistemas Linux. 

------

## iptables 

La utilidad iptables proporciona un conjunto flexible de reglas para filtrar el tráfico de red según varios criterios, como direcciones IP de origen y destino, números de puerto, protocolos y más. También existen otras soluciones como nftables, ufw y firewalld. `Nftables` proporciona una sintaxis más moderna y un rendimiento mejorado con respecto a iptables. Sin embargo, la sintaxis de las reglas de nftables no es compatible con iptables, por lo que la migración a nftables requiere cierto esfuerzo. `UFW` significa "Firewall sin complicaciones" y proporciona una interfaz simple y fácil de usar para configurar reglas de firewall. UFW está construido sobre el marco de iptables como nftables y proporciona una forma más sencilla de administrar las reglas de firewall. Finalmente, FirewallD proporciona una solución de firewall dinámica y flexible que se puede usar para administrar configuraciones de firewall complejas, admite un amplio conjunto de reglas para filtrar el tráfico de red y se puede usar para crear zonas y servicios de firewall personalizados. Consta de varios componentes que trabajan juntos para proporcionar una solución de firewall potente y flexible. Los principales componentes de iptables son: 

| **Componente** | **Descripción**                                              |
| -------------- | ------------------------------------------------------------ |
| `Tables`       | Las tablas se utilizan para organizar y categorizar reglas de firewall. |
| `Chains`       | Las cadenas se utilizan para agrupar un conjunto de reglas de firewall aplicadas a un tipo específico de tráfico de red. |
| `Rules`        | Las reglas definen los criterios para filtrar el tráfico de red y las acciones a tomar para los paquetes que coinciden con los criterios. |
| `Matches`      | Las coincidencias se utilizan para hacer coincidir criterios específicos para filtrar el tráfico de red, como direcciones IP de origen o destino, puertos, protocolos y más. |
| `Targets`      | Los objetivos especifican la acción para los paquetes que coinciden con una regla específica. Por ejemplo, los destinos se pueden utilizar para aceptar, descartar o rechazar paquetes o modificar los paquetes de otra manera. |

#### tablas 

Cuando se trabaja con firewalls en sistemas Linux, es importante comprender cómo funcionan las tablas en iptables. Las tablas en iptables se utilizan para categorizar y organizar reglas de firewall según el tipo de tráfico para el que están diseñadas. Estas tablas se utilizan para organizar y categorizar reglas de firewall. Cada mesa es responsable de realizar un conjunto específico de tareas. 

| **Nombre de la tabla** | **Descripción**                                              | **Cadenas incorporadas**                                     |
| ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `filter`               | Se utiliza para filtrar el tráfico de red según direcciones IP, puertos y protocolos. | ENTRADA, SALIDA, ADELANTE                                    |
| `nat`                  | Se utiliza para modificar las direcciones IP de origen o destino de los paquetes de red. | ENRUTAMIENTO PREVIO, ENRUTAMIENTO POSTERIOR                  |
| `mangle`               | Se utiliza para modificar los campos de encabezado de los paquetes de red. | ENRUTAMIENTO PREVIO, SALIDA, ENTRADA, ADELANTE, ENRUTAMIENTO POSTERIOR |

Además de las tablas integradas, iptables proporciona una cuarta tabla llamada tabla sin formato, que se utiliza para configurar opciones especiales de procesamiento de paquetes. La tabla sin formato contiene dos cadenas integradas: PREROUTING y OUTPUT. 

#### Cadenas 

En iptables, las cadenas -*chains*- organizan reglas que definen cómo se debe filtrar o modificar el tráfico de la red. Hay dos tipos de cadenas en iptables: 

- Cadenas incorporadas - Built-in chains
- Cadenas definidas por el usuario - User-defined chains

Las cadenas integradas están predefinidas y se crean automáticamente cuando se crea una tabla. Cada mesa tiene un conjunto diferente de cadenas incorporadas. Por ejemplo, la tabla de filtros tiene tres cadenas integradas: 

- INPUT
- OUTPUT
- FORWARD

Estas cadenas se utilizan para filtrar el tráfico de red entrante y saliente, así como el tráfico que se reenvía entre diferentes interfaces de red. La tabla nat tiene dos cadenas integradas: 

- PREROUTING
- POSTROUTING

La cadena PREROUTING -enrutamiento previo- se utiliza para modificar la dirección IP de destino de los paquetes entrantes antes de que la tabla de enrutamiento los procese. La cadena POSTROUTING -postenrutamiento- se utiliza para modificar la dirección IP de origen de los paquetes salientes después de que la tabla de enrutamiento los haya procesado. La mesa de mandril tiene cinco cadenas incorporadas: 

- PREROUTING
- OUTPUT
- INPUT
- FORWARD
- POSTROUTING

Estas cadenas se utilizan para modificar los campos de encabezado de los paquetes entrantes y salientes y los paquetes procesados por las cadenas correspondientes. 

`User-defined chains` puede simplificar la administración de reglas agrupando reglas de firewall según criterios específicos, como la dirección IP de origen, el puerto de destino o el protocolo. Se pueden agregar a cualquiera de las tres tablas principales. Por ejemplo, si una organización tiene varios servidores web y todos requieren reglas de firewall similares, las reglas para cada servidor podrían agruparse en una cadena definida por el usuario. Otro ejemplo es cuando una cadena definida por el usuario podría filtrar el tráfico destinado a un puerto específico, como el puerto 80 (HTTP). Luego, el usuario podría agregar reglas a esta cadena que filtren específicamente el tráfico destinado al puerto 80. 

#### Reglas y objetivos 

Las reglas de iptables se utilizan para definir los criterios para filtrar el tráfico de red y las acciones a realizar para los paquetes que coinciden con los criterios. Las reglas se agregan a las cadenas usando el `-A` opción seguida del nombre de la cadena, y se pueden modificar o eliminar utilizando varias otras opciones. 

Cada regla consta de un conjunto de criterios o coincidencias y un objetivo que especifica la acción para los paquetes que coinciden con los criterios. Los criterios o coincidencias coinciden con campos específicos en el encabezado IP, como la dirección IP de origen o destino, el protocolo, el origen, el número de puerto de destino y más. El objetivo especifica la acción para los paquetes que coinciden con los criterios. Especifican la acción a realizar para los paquetes que coinciden con una regla específica. Por ejemplo, los destinos pueden aceptar, descartar, rechazar o modificar los paquetes. Algunos de los objetivos comunes utilizados en las reglas de iptables incluyen los siguientes: 

| **Nombre de destino** | **Descripción**                                              |
| --------------------- | ------------------------------------------------------------ |
| `ACCEPT`              | Permite que el paquete pase a través del firewall y continúe hasta su destino. |
| `DROP`                | Descarta el paquete, bloqueándolo efectivamente para que no pase a través del firewall. |
| `REJECT`              | Descarta el paquete y envía un mensaje de error a la dirección de origen, notificándoles que el paquete fue bloqueado. |
| `LOG`                 | Registra la información del paquete en el registro del sistema. |
| `SNAT`                | Modifica la dirección IP de origen del paquete, normalmente utilizada para la traducción de direcciones de red (NAT) para traducir direcciones IP privadas a direcciones IP públicas. |
| `DNAT`                | Modifies the destination IP address of the packet, typically used for NAT to forward traffic from one IP address to another |
| `MASQUERADE`          | Similar a SNAT pero se usa cuando la dirección IP de origen no es fija, como en un escenario de dirección IP dinámica |
| `REDIRECT`            | Redirige paquetes a otro puerto o dirección IP               |
| `MARK`                | Agrega o modifica el valor de la marca Netfilter del paquete, que puede usarse para enrutamiento avanzado u otros fines. |

Ilustremos una regla y consideremos que queremos agregar una nueva entrada a la cadena INPUT que permita aceptar el tráfico TCP entrante en el puerto 22 (SSH). El comando para eso sería similar al siguiente: 

```shell-session
nunhes@htb[/htb]$ sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

#### Matches 

`Matches` se utilizan para especificar los criterios que determinan si se debe aplicar una regla de firewall a un paquete o conexión en particular. Las coincidencias se utilizan para hacer coincidir características específicas del tráfico de red, como la dirección IP de origen o destino, el protocolo, el número de puerto y más. 

| **Nombre del partido** | **Descripción**                                              |
| ---------------------- | ------------------------------------------------------------ |
| `-p` o `--protocol`    | Especifica el protocolo que debe coincidir (por ejemplo, tcp, udp, icmp) |
| `--dport`              | Especifica el puerto de destino que debe coincidir           |
| `--sport`              | Especifica el puerto de origen que debe coincidir            |
| `-s` o `--source`      | Especifica la dirección IP de origen para que coincida       |
| `-d` o `--destination` | Especifica la dirección IP de destino para que coincida      |
| `-m state`             | Coincide con el estado de una conexión (por ejemplo, NUEVA, ESTABLECIDA, RELACIONADA) |
| `-m multiport`         | Coincide con múltiples puertos o rangos de puertos           |
| `-m tcp`               | Coincide con paquetes TCP e incluye opciones adicionales específicas de TCP |
| `-m udp`               | Coincide con paquetes UDP e incluye opciones adicionales específicas de UDP |
| `-m string`            | Coincide con paquetes que contienen una cadena específica    |
| `-m limit`             | Coincide con paquetes a un límite de velocidad específico    |
| `-m conntrack`         | Coincide con paquetes según la información de seguimiento de su conexión |
| `-m mark`              | Coincide con paquetes según su valor de marca Netfilter      |
| `-m mac`               | Coincide con paquetes según su dirección MAC                 |
| `-m iprange`           | Coincide con paquetes basados en un rango de direcciones IP  |

En general, las coincidencias se especifican usando la opción '-m' en iptables. Por ejemplo, el siguiente comando agrega una regla a la cadena 'INPUT' en la tabla 'filter' que coincide con el tráfico TCP entrante en el puerto 80: 

```shell-session
nunhes@htb[/htb]$ sudo iptables -A INPUT -p tcp -m tcp --dport 80 -j ACCEPT
```

Esta regla de ejemplo coincide con el tráfico TCP entrante ( `-p tcp`) en el puerto 80 ( `--dport 80`) y salta al objetivo aceptado ( `-j ACCEPT`) si el partido tiene éxito. 

|      |                                                              |
| ---- | ------------------------------------------------------------ |
| 1.   | Inicie un servidor web en el puerto TCP/8080 en su destino y use iptables para bloquear el tráfico entrante en ese puerto. |
| 2.   | Cambie las reglas de iptables para permitir el tráfico entrante en el puerto TCP/8080. |
| 3.   | Bloquee el tráfico desde una dirección IP específica.        |
| 4.   | Permitir el tráfico desde una dirección IP específica.       |
| 5.   | Bloquear el tráfico según el protocolo.                      |
| 6.   | Permitir el tráfico según el protocolo.                      |
| 7.   | Crea una nueva cadena.                                       |
| 8.   | Reenviar el tráfico a una cadena específica.                 |
| 9.   | Eliminar una regla específica.                               |
| 10.  | Enumere todas las reglas existentes.                         |

# Logs o Registros del sistema 

------

Los registros del sistema en Linux son un conjunto de archivos que  contienen información sobre el sistema y las actividades que se llevan a cabo en él. Estos registros son importantes para monitorear y  solucionar problemas del sistema, ya que pueden proporcionar información sobre el comportamiento del sistema, la actividad de las aplicaciones y los eventos de seguridad. Estos registros del sistema también pueden  ser una valiosa fuente de información para identificar posibles  debilidades y vulnerabilidades de seguridad dentro de un sistema Linux.  Al analizar los registros en nuestros sistemas de destino, podemos  obtener información sobre el comportamiento del sistema, la actividad de la red y la actividad del usuario, y podemos usar esta información para identificar cualquier actividad anormal, como inicios de sesión no  autorizados, intentos de ataques, credenciales de texto sin cifrar o  archivos inusuales. acceso, lo que podría indicar una posible violación  de seguridad. 

Nosotros, como evaluadores de penetración, también podemos utilizar  registros del sistema para monitorear la efectividad de nuestras  actividades de pruebas de seguridad. Al revisar los registros después de realizar pruebas de seguridad, podemos determinar si nuestras  actividades desencadenaron algún evento de seguridad, como alertas de  detección de intrusiones o advertencias del sistema. Esta información  puede ayudarnos a perfeccionar nuestras estrategias de prueba y mejorar  la seguridad general del sistema. 

Para garantizar la seguridad de un sistema Linux, es importante  configurar los registros del sistema correctamente. Esto incluye  establecer los niveles de registro adecuados, configurar la rotación de  registros para evitar que los archivos de registro se vuelvan demasiado  grandes y garantizar que los registros se almacenen de forma segura y  estén protegidos contra el acceso no autorizado. Además, es importante  revisar y analizar periódicamente los registros para identificar  posibles riesgos de seguridad y responder a cualquier evento de  seguridad de manera oportuna. Existen varios tipos diferentes de  registros del sistema en Linux, que incluyen: 

- Registros del núcleo 
- Registros del sistema 
- Registros de autenticación 
- Registros de aplicaciones 
- Registros de seguridad 

#### Registros del kernel 

Estos registros contienen información sobre el kernel del sistema,  incluidos controladores de hardware, llamadas al sistema y eventos del  kernel. Se almacenan en el `/var/log/kern.log` archivo. Por  ejemplo, los registros del kernel pueden revelar la presencia de  controladores vulnerables u obsoletos que los atacantes podrían atacar  para obtener acceso al sistema. También pueden proporcionar información  sobre fallas del sistema, limitaciones de recursos y otros eventos que  podrían provocar una denegación de servicio u otros problemas de  seguridad. Además, los registros del kernel pueden ayudarnos a  identificar llamadas sospechosas al sistema u otras actividades que  podrían indicar la presencia de malware u otro software malicioso en el  sistema. Al monitorear el `/var/log/kern.log` archivo, podemos detectar cualquier comportamiento inusual y tomar las medidas adecuadas para evitar daños mayores al sistema. 

#### Registros del sistema 

Estos registros contienen información sobre eventos a nivel del  sistema, como inicios y detenciones de servicios, intentos de inicio de  sesión y reinicios del sistema. Se almacenan en el `/var/log/syslog` archivo. Al analizar los intentos de inicio de sesión, los inicios y  paradas del servicio y otros eventos a nivel del sistema, podemos  detectar cualquier posible acceso o actividad en el sistema. Esto puede  ayudarnos a identificar cualquier vulnerabilidad que pueda explotarse y  ayudarnos a recomendar medidas de seguridad para mitigar estos riesgos.  Además, podemos utilizar el `syslog` para identificar  problemas potenciales que podrían afectar la disponibilidad o el  rendimiento del sistema, como inicios fallidos del servicio o reinicios  del sistema. A continuación se muestra un ejemplo de cómo tales `syslog` El archivo podría verse así: 

#### Syslog - registro del sistema 

```shell-session
Feb 28 2023 15:00:01 server CRON[2715]: (root) CMD (/usr/local/bin/backup.sh)
Feb 28 2023 15:04:22 server sshd[3010]: Failed password for htb-student from 10.14.15.2 port 50223 ssh2
Feb 28 2023 15:05:02 server kernel: [  138.303596] ata3.00: exception Emask 0x0 SAct 0x0 SErr 0x0 action 0x6 frozen
Feb 28 2023 15:06:43 server apache2[2904]: 127.0.0.1 - - [28/Feb/2023:15:06:43 +0000] "GET /index.html HTTP/1.1" 200 13484 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.149 Safari/537.36"
Feb 28 2023 15:07:19 server sshd[3010]: Accepted password for htb-student from 10.14.15.2 port 50223 ssh2
Feb 28 2023 15:09:54 server kernel: [  367.543975] EXT4-fs (sda1): re-mounted. Opts: errors=remount-ro
Feb 28 2023 15:12:07 server systemd[1]: Started Clean PHP session files.
```

#### Registros de autenticación 

Estos registros contienen información sobre los intentos de  autenticación del usuario, incluidos los intentos exitosos y fallidos.  Se almacenan en el `/var/log/auth.log` archivo. Es importante señalar que si bien el `/var/log/syslog` El archivo puede contener información de inicio de sesión similar, el `/var/log/auth.log` El archivo se centra específicamente en los intentos de autenticación  del usuario, lo que lo convierte en un recurso más valioso para  identificar posibles amenazas a la seguridad. Por lo tanto, es esencial  que los probadores de penetración revisen los registros almacenados en  el `/var/log/auth.log` archivo para garantizar que el sistema sea seguro y no se haya visto comprometido. 

#### Auth.log

```shell-session
Feb 28 2023 18:15:01 sshd[5678]: Accepted publickey for admin from 10.14.15.2 port 43210 ssh2: RSA SHA256:+KjEzN2cVhIW/5uJpVX9n5OB5zVJ92FtCZxVzzcKjw
Feb 28 2023 18:15:03 sudo:   admin : TTY=pts/1 ; PWD=/home/admin ; USER=root ; COMMAND=/bin/bash
Feb 28 2023 18:15:05 sudo:   admin : TTY=pts/1 ; PWD=/home/admin ; USER=root ; COMMAND=/usr/bin/apt-get install netcat-traditional
Feb 28 2023 18:15:08 sshd[5678]: Disconnected from 10.14.15.2 port 43210 [preauth]
Feb 28 2023 18:15:12 kernel: [  778.941871] firewall: unexpected traffic allowed on port 22
Feb 28 2023 18:15:15 auditd[9876]: Audit daemon started successfully
Feb 28 2023 18:15:18 systemd-logind[1234]: New session 4321 of user admin.
Feb 28 2023 18:15:21 CRON[2345]: pam_unix(cron:session): session opened for user root by (uid=0)
Feb 28 2023 18:15:24 CRON[2345]: pam_unix(cron:session): session closed for user root
```

En este ejemplo, podemos ver en la primera línea que se ha utilizado  una clave pública exitosa para la autenticación del usuario. `admin`. Además, podemos ver que este usuario está en el `sudoers` grupo porque puede ejecutar comandos usando `sudo`. El mensaje del kernel indica que se permitió tráfico inesperado en el  puerto 22, lo que podría indicar una posible violación de seguridad.  Después de eso, vemos que se creó una nueva sesión para el usuario  "admin" por `systemd-logind` y que un `cron` sesión abierta y cerrada para el usuario `root`. 

#### Registros de aplicaciones 

Estos registros contienen información sobre las actividades de  aplicaciones específicas que se ejecutan en el sistema. A menudo se  almacenan en sus propios archivos, como `/var/log/apache2/error.log` para el servidor web Apache o `/var/log/mysql/error.log` para el servidor de base de datos MySQL. Estos registros son  particularmente importantes cuando nos dirigimos a aplicaciones  específicas, como servidores web o bases de datos, ya que pueden  proporcionar información sobre cómo estas aplicaciones procesan y  manejan los datos. Al examinar estos registros, podemos identificar  posibles vulnerabilidades o configuraciones incorrectas. Por ejemplo,  los registros de acceso se pueden utilizar para realizar un seguimiento  de las solicitudes realizadas a un servidor web, mientras que los  registros de auditoría se pueden utilizar para realizar un seguimiento  de los cambios realizados en el sistema o en archivos específicos. Estos registros se pueden utilizar para identificar intentos de acceso no  autorizados, filtración de datos u otras actividades sospechosas. 

Además, los registros de acceso y auditoría son registros críticos  que registran información sobre las acciones de los usuarios y procesos  en el sistema. Son cruciales para fines de seguridad y cumplimiento, y  podemos usarlos para identificar posibles problemas de seguridad y  vectores de ataque. 

Por ejemplo, `access logs` Mantenga un registro de la  actividad del usuario y del proceso en el sistema, incluidos los  intentos de inicio de sesión, el acceso a archivos y las conexiones de  red. `Audit logs` registrar información sobre eventos  relevantes para la seguridad en el sistema, como modificaciones a los  archivos de configuración del sistema o intentos de modificar archivos o configuraciones del sistema. Estos registros ayudan a rastrear posibles ataques y actividades o identificar violaciones de seguridad u otros  problemas. Una entrada de ejemplo en un archivo de registro de acceso  puede tener el siguiente aspecto: 

#### Entrada de registro de acceso 

```shell-session
2023-03-07T10:15:23+00:00 servername privileged.sh: htb-student accessed /root/hidden/api-keys.txt
```

En esta entrada de registro, podemos ver que el usuario `htb-student` usó el `privileged.sh` script para acceder al `api-keys.txt` archivo en el `/root/hidden/` directorio. En los sistemas Linux, los servicios más comunes tienen ubicaciones predeterminadas para los registros de acceso: 

| **Servicio** | **Descripción**                                              |
| ------------ | ------------------------------------------------------------ |
| `Apache`     | Los registros de acceso se almacenan en el archivo /var/log/apache2/access.log (o similar, según la distribución). |
| `Nginx`      | Los registros de acceso se almacenan en el archivo /var/log/nginx/access.log (o similar). |
| `OpenSSH`    | Los registros de acceso se almacenan en el archivo /var/log/auth.log en Ubuntu y en /var/log/secure en CentOS/RHEL. |
| `MySQL`      | Los registros de acceso se almacenan en el archivo /var/log/mysql/mysql.log. |
| `PostgreSQL` | Los registros de acceso se almacenan en el archivo /var/log/postgresql/postgresql-version-main.log. |
| `Systemd`    | Los registros de acceso se almacenan en el directorio /var/log/journal/. |

#### Registros de seguridad 

Estos registros de seguridad y sus eventos a menudo se registran en  una variedad de archivos de registro, según la aplicación o herramienta  de seguridad específica que se utilice. Por ejemplo, la aplicación  Fail2ban registra los intentos fallidos de inicio de sesión en el `/var/log/fail2ban.log` archivo, mientras que el firewall UFW registra la actividad en el `/var/log/ufw.log` archivo. Otros eventos relacionados con la seguridad, como cambios en  los archivos o configuraciones del sistema, pueden registrarse en  registros del sistema más generales, como `/var/log/syslog` o `/var/log/auth.log`. Como evaluadores de penetración, podemos utilizar herramientas y  técnicas de análisis de registros para buscar eventos o patrones de  actividad específicos que puedan indicar un problema de seguridad y  utilizar esa información para probar más a fondo el sistema en busca de  vulnerabilidades o posibles vectores de ataque. 

Es importante estar familiarizado con las ubicaciones predeterminadas para los registros de acceso y otros archivos de registro en los  sistemas Linux, ya que esta información puede resultar útil al realizar  una evaluación de seguridad o una prueba de penetración. Al comprender  cómo se registran y almacenan los eventos relacionados con la seguridad, podemos analizar de manera más efectiva los datos de registro e  identificar posibles problemas de seguridad. 

Se puede acceder a todos estos registros y analizarlos utilizando una variedad de herramientas, incluidos los visores de archivos de registro integrados en la mayoría de los entornos de escritorio Linux, así como  herramientas de línea de comandos como `tail`, `grep`, y `sed` comandos. El análisis adecuado de los registros del sistema puede  ayudar a identificar y solucionar problemas del sistema, así como a  detectar violaciones de seguridad y otros eventos de interés. 
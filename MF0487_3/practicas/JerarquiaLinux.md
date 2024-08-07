## ESTÁNDAR DE JERARQUIA DEL SISTEMA DE ARCHIVOS?

El estándar de jerarquía del sistema de archivos, también conocido como FHS (Filesystem Hierarchy Standard), es la **norma creada por la comunidad que define los directorios y el contenido de los directorios en los sistemas operativos GNU/Linux y Unix**.

Mediante la normativa que fija como debe ser la estructura de directorios en GNU-Linux conseguimos disponer de un sistema de directorios completamente estructurado, coherente y estandarizado obteniendo así las siguiente ventajas:

1. El software que tenemos instalado en nuestro ordenador sabe en todo momento las carpetas y los permisos de las carpetas de nuestro ordenador. Por lo tanto nuestro software en todo momento sabe donde encontrar y almacenar la información que necesita para su funcionamiento.
2. Los usuarios saben en todo momento el contenido que hay en cada una de las carpetas del ordenador.
3. Ayuda a la hora de realizar el mantenimiento de un sistema operativo.
4. Ayuda a otorgar los permisos pertinentes a cada uno de los archivos de nuestro sistema operativo.

###### Nota: El estándar de jerarquía del sistema de archivos es flexible y existe cierta libertad a la hora de aplicar las normas. De hecho ciertas distribuciones GNU-Linux introducen modificaciones a la estructura de directorios estándar para adaptarla a sus necesidades.

###### Nota: Quien requiera de información adicional respecto a la FHS puede consultar el siguiente [link](https://wiki.linuxfoundation.org/en/FHS).

## TIPOS DE DIRECTORIOS EN GNU-LINUX

En GNU-Linux existen distintos tipos de directorios. Los distintos tipos de directorios existentes según su uso son los siguiente:

### Directorios compartibles

Los directorios compartidos son aquellos directorios que **se pueden acceder desde distintos equipos**. Por lo tanto los directorios compartibles son aquellos que contienen archivos que se pueden usar desde otros equipos.

Algunos ejemplos de directorios compartibles son:

/var/mail, /opt, /home, /var/www/html, /usr, etc.

### Directorios no compartibles

Al contrario que los directorios compartibles, los directorios no compartibles son aquellos **directorios que no se pueden compartir y su acceso y modificación están limitados al administrador del sistema**. Por lo tanto los los directorios no compartibles contienen archivos que solo puedes ser accesibles y modificados por el administrador del sistemas.

Algunos ejemplos de directorios no compartibles son:

/etc, /boot, /var/run, etc.

### Directorios variables

Son aquellos directorios que **contienen archivos que pueden ser modificados y pueden variar su contenido sin la intervención del administrador del sistema**.

Algunos ejemplos de directorios variables son:

/var/log/messages, /var/mail, /var/spool/news, /home, /var/run, etc.

### Directorios estáticos

Son aquellos directorios que **contienen archivos que solo pueden ser modificados con la intervención del administrador del sistema**.

Algunos ejemplos de directorios estáticos son:

/etc/password, /etc/shadow, /usr, /opt, /etc, /boot, /bin, /sbin, etc.

## ESTRUCTURA DE DIRECTORIOS EN GNU-LINUX

### Directorio Raíz (/)

El directorio raíz, simbolizado por el símbolo (/), es el **directorio principal a partir del cual se ramifican todo el resto de directorios**.

Por lo tanto podemos decir que el directorio raíz es el contenedor de nuestro sistema operativo ya que de él nacen el resto de directorios que tendrá nuestro sistema operativo. Lo que acabamos de comentar se puede ver representado en el siguiente dibujo en que el directorio raíz es la rama principal del árbol.

[![Árbol de directorios en Linux](https://geekland.eu/wp-content/uploads/2015/10/Arbol-de-directorios-en-Linux-234x300.png)](https://geekland.eu/wp-content/uploads/2015/10/Arbol-de-directorios-en-Linux.png)

### Directorio /bin

El directorio /bin es un **directorio estático y compartible en el que se almacenan archivos binarios/ejecutables necesarios para el funcionamiento del sistema**. Estos archivos binarios los pueden usar la totalidad de usuarios del sistema operativo.

Algunos de los archivos ejecutables almacenados en el directorio /bin son cp, echo, tar, cat, mv, rm, ping, cp, gzip, kill, ls, ping, su etc. Estos archivos son los que nos permiten realizar la gran mayoría de utilidades básicas a través de la terminal Linux.

El directorio /bin en ningún caso podrá contener subdirectorios.

### Directorio /boot

Es un directorio estático no compartible que **contiene la totalidad de archivos necesarios para el arranque del ordenador excepto los archivos de configuración**. Algunos de los archivos indispensables para el arranque del sistema que acostumbra a almacenar el directorio /boot son el kernel y el gestor de arranque Grub.

La totalidad de contenido almacenado en el directorio /boot es el que se utiliza antes de que el Kernel de comience a ejecutar programas en modo usuario.

El directorio /boot puede estar ubicado en su propia partición (partición /boot).

### Directorio /dev

El sistema operativo Gnu-Linux trata los dispositivos de hardware como si fueran un archivo. **Estos archivos que representan nuestros dispositivos de hardware se hallan almacenados en el directorio /dev**.

Cada vez que nosotros accedemos o usamos un dispositivo de hardware, como puede ser una memoria USB, una impresora, un disco duro externo, un ratón, etc, accedemos al hardware del dispositivo leyendo y escribiendo en el fichero correspondiente ubicado en el directorio /dev.

Algunos de los archivos básicos que podemos encontrar en este directorio son:

1. cdrom que representa nuestro dispositivo de CDROM.
2. sda que representa nuestro disco duro sata.
3. audio que representa nuestra tarjeta de sonido.
4. psaux que representa el puerto PS/2.
5. lpx que representa nuestra impresora.
6. fd0 que representa nuestra disquetera.
7. etc.

### Directorio /etc

El directorio /etc es un **directorio estático que contiene los archivos de configuración del sistema operativo**. Este directorio también contiene archivos de configuración para controlar el funcionamiento de diversos programas.

Algunos de los archivos de configuración de la carpeta /etc pueden ser sustituidos o complementados por archivos de configuración ubicados en nuestra carpeta personal /home.

Este directorio solamente contiene archivos de texto y subdirectorios. Estos subdirectorios también contendrán archivos de configuración para configurar partes de nuestro sistema como por ejemplo:

1. /etc/apt: Carpeta que contiene ficheros de configuración del gestor de paquetes apt.
2. /etc/opt: Carpeta que contiene los ficheros de configuración para los programas alojados en la carpeta /opt. Algunos programas alojados en esta carpeta pueden ser Spotify, Google-earth, Google Chrome, Teamviewer, etc.
3. /etc/profile: Carpeta que contiene parámetros de configuración de los usuarios para inicializar la shell o interprete de comandos “terminal”
4. /etc/sgml: Carpeta que contiene los ficheros de configuración para SGML. SGML es un lenguaje que se utiliza para la organización y marcado de documentos.
5. /etc/X11: Ficheros para la configuración del sistema X Window
6. etc.

###### Nota: Si quieren más información acerca de la totalidad de subdirectorios que incluye la carpeta /etc pueden consultar el siguiente [enlace](http://www.linuxtotal.com.mx/index.php?cont=info_admon_013).

### Directorio /home

El directorio /home se trata de un **directorio variable y compartible**. Este directorio está **destinado a alojar la totalidad de archivos personales de los distintos usuarios del sistema operativo a excepción del usuario root**. Algunos de los archivos personales almacenados en la carpeta /home son fotografías, documentos de ofimática, vídeos, etc.

Esta carpeta **también contiene los ficheros de configuración de los programas que utilizan cada uno de los usuarios** del sistema operativo a excepción del usuario root.

Todos los archivos personales y archivos de configuración que acabamos de mencionar se almacenan en subdirectorios dentro de la carpeta /home. Así por ejemplo si en nuestro ordenador tenemos 2 usuarios (usuario1 y usuario2) los archivos personales y de configuración del usuario 1 se almacenarán en la ubicación:

/home/usuario1

Por otro lado los archivos personales y de configuración del usuario 2 se almacenarán en la carpeta:

/home/usuario2

De esta forma los archivos personales y de configuración quedan perfectamente clasificados por usuario.

Normalmente el directorio /home reside un una partición propia. El hecho que el directorio /home resida en una partición propia es importante ya que de este modo podremos reinstalar nuestro sistema operativo sin perder nuestros datos personales y manteniendo la configuración antigua.

###### Nota: Haciendo un símil forzado con Windows, la partición /home sería similar a la carpeta Mis documentos de Windows.

### Directorio /lib

El directorio /lib es un **directorio estático y que puede ser compartible**. Este directorio **contiene bibliotecas compartidas que son necesarias para arrancar los ejecutables que se almacenan en los directorios /bin y /sbin**.

Este directorio también contiene módulos del kernel y controladores de drivers que son necesarios durante el inicio del sistema y durante el funcionamiento del sistema operativo.

### Directorio /mnt

El directorio /mnt **tiene la finalidad de albergar los puntos de montaje de los distintos dispositivos de almacenamiento** como por ejemplo discos duros externos, particiones de unidades externas, etc.

Los medios montados en esta carpeta pueden ser tanto estáticos como variables y por norma general son compartibles.

### Directorio /media

La función del directorio /media es similar a la del directorio /mnt. Este directorio **contiene los puntos de montaje de los medios extraíbles de almacenamiento** como por ejemplo memorias USB, lectores de CD-ROM, unidades de disquete, etc.

En el directorio /media también podemos montar sin ningun tipo de problema medios que montaríamos en el directorio /mnt.

### Directorio /opt

El contenido almacenado en el directorio /opt **es estático y compartible**. **La función de este directorio es almacenar programas que no vienen con nuestro sistema operativo** como por ejemplo Spotify, Google-earth, Google Chrome, Teamviewer, etc.

Como es un directorio compartible los programas presentes en esta carpeta pueden ser usados por todos los usuarios del sistema operativo.

La función de este directorio es muy similar a la del directorio /usr/local, pero a diferencia de la carpeta /usr/local en /opt se instalan programas que no siguen los estándares para almacenar su contenido en la carpeta /usr.

### Directorio /proc

El directorio /proc **se trata de un sistema de archivos virtual**. Este sistema de archivos virtual **nos proporciona información acerca de los distintos procesos y aplicaciones que se están ejecutando en nuestro sistema operativo**.

Para cada uno de los procesos en marcha existe un subdirectorio dentro de la carpeta /proc. Dentro del subdirectorio es donde se almacena esta información.

Como curiosidad decir que la totalidad del contenido almacenado en la carpeta /proc no está almacenado en nuestro disco duro. El contenido de este directorio está almacenado en la memoria RAM y el mismo sistema operativo es quien crea y borra el contenido de la carpeta /proc.

Quien quiera más información acerca del directorio /proc puede consultar el siguiente [enlace](http://www.linuxtotal.com.mx/index.php?cont=info_admon_016).

### Directorio /root

El directorio /root se trata de un **directorio variable no compartible**. El directorio /root **es el directorio /home del administrador del sistema** (usuario root).

### Directorio /sbin

El directorio /sbin se trata de un **directorio estático y compartible**. Su función es similar al directorio /bin, pero a diferencia del directorio /bin, el directorio /sbin **almacena archivos binarios/ejecutables que solo puede ejecutar el usuario root** o administrador del sistema.

Los archivos incluidos en el directorio /sbin son aquellos que son primordiales para el arranque, restauración y reparación del sistema operativo. Algunos de los archivos ejecutables almacenados en este directorio son fsck, init, reboot, shutdown, fastboot, etc.

Otros directorios que contienen programas y binarios para la administración del sistema son el /usr/bin y el /usr/local/sbin.

### Directorio /srv

El directorio /srv se usa **para almacenar directorios y datos que usan ciertos servidores que podamos tener instalados en nuestro ordenador**.

Algunos de los servidores que almacenan datos en el directorio /srv son:

1. Servidor web apache en el directorio /srv/www
2. Cualquier servidor ftp en la ubicación /srv/ftp
3. Un servidor CVS.
4. Etc.

### Directorio /tmp

El directorio /tmp es es **donde se crean y se almacenan los archivos temporales y las variables que los programas puedan funcionar de forma adecuada**.

Generalmente **los sistemas operativos vacían el directorio /tmp cada vez que reiniciamos el ordenador**. En el caso que no sea así es recomendable vaciar cada cierto el contenido de esta carpeta.

### Directorio /usr

El directorio /usr es un **directorio compartido y estático**. Este directorio es el que **contiene la gran mayoría de programas instalados** en nuestro sistema operativo.

Todo el contenido almacenado en la carpeta /usr es accesible para todos los usuarios y **su contenido es solo de lectura**.

**El directorio /usr contiene una serie de subdirectorios** que acostumbran a almacenar la siguiente información:

/usr/bin: Subdirectorio que almacena los archivos ejecutables del software que tenemos almacenado en nuestro ordenador.

/usr/include: Subdirectorio que incluye la totalidad de archivos de cabecera que necesita el software instalado en nuestro sistema operativo para que funcione de forma adecuada.

/usr/lib: Subdirectorio que incluye bibliotecas compartidas y ficheros binarios que únicamente pueden ser ejecutados por el administrador del sistema.

/usr/local: GNU-Linux es un sistema operativo diseñado para ser usado en entornos de red. Por lo tanto es posible que el directorio /usr no esté instalado localmente en nuestro y esté en un servidor. En estos casos existe el directorio /usr/local que está destinado a alojar los programas que instala localmente el administrador del sistema. Este directorio está protegido de las actualizaciones automáticas de todo el sistema operativo y tiene una estructura de directorios muy similar a la del directorio /usr.

/usr/sbin: Directorio que contiene archivos binarios para la administración del nuestro equipo no esenciales para el proceso de arranque ni para reparar el ordenador. Estos archivos binarios almacenados en la carpeta /usr/sbin solamente pueden ser usados por el administrador del sistema. Algunos de estos archivos binarios no críticos para administrar el sistema operativo pueden ser por ejemplo varios demonios para diversos servicios de red, xcalib para calibrar el color de nuestro monitores, etc.

/usr/share: En el directorio /usr/share encontramos archivos de texto compartibles que son independientes de la arquitectura del sistema operativo. En este directorio podemos encontrar por ejemplo los archivos de ayuda como por ejemplo los documentos info y las páginas de man, ficheros de configuración, imágenes, iconos, themes, etc.

/usr/src: En el directorio /usr/src normalmente encontramos el código fuente de algunas aplicaciones y del kernel que tenemos instalado en nuestro sistema operativo.

### Directorio /var

El directorio /var **contiene archivos de datos variables y temporales como por ejemplo los registros del sistema (logs), los registros de programas que tenemos instalados en el sistema operativo, archivos spool, etc.**

**La principal función del directorio /var es la detectar problemas y solucionarlos**. Se recomienda ubicar el directorio /var en una partición propia, y en caso de no ser posible es recomendable ubicarlo fuera de la partición raíz.

**Algunos de los subdirectorios importantes que están dentro de la carpeta /var** son los siguientes:

/var/cache: Subdirectorio pensado para almacenar datos de aplicaciones en modo cache. Un ejemplo de lo que acabo de citar es apt-get. En el momento de instalar una aplicación con apt-get se almacena una copia del paquete binario instalado en la ubicación /var/cache/apt/archives/. Así en el caso que desinstalaramos el programa y quisiéramos volver instalarlo no seria necesario descargar el fichero binario de nuevo y la instalación seria inmediata.

/var/lib: En este subdirectorio encontramos información sobre el estado de las aplicaciones. Este directorio también contiene bases de datos del sistema.

/var/lock: Directorio en el que se hallan los archivos de bloqueo que crean ciertos programas. La función de los archivos de bloqueo creados por algunos programas, como por ejemplo un servidor web, es evitar que ciertos recursos sean usados por otros programas que no sean el propio servidor web. En el momento de cerrar la aplicación que ha generado el archivo de bloqueo, el archivo de bloqueo desaparece.

/var/log: En el directorio /var/log se encuentran de forma clasificada gran parte de los registros de nuestros programas y del sistema operativo. Este directorio es muy importante ya que en caso de problemas, el administrador del sistema lo puede consultar para intentar averiguar la causa del problema. Los log o registros se encuentran perfectamente clasificados, así por lo tanto si queremos consultar los registros generados por el kernel tendremos que consultar el archivo /var/log/messages, si queremos consultar los accesos a nuestro sistema operativo podemos consultar el archivo /var/log/wtmp, etc.

/var/mail: Directorio en el que se ubican los archivos de correo electrónico de cada uno de los usuarios del servidor de mail. También es posible ubicar nuestros archivos de correo electrónico en la partición /home.

/var/opt: En el directorio /var/opt se almacenan datos variables que utilizan los programas instalados en la ubicación /opt.

/var/run: El directorio /var/run contiene información de la sesión que estamos ejecutando. Ejemplos de la información que contienen los archivos de esta carpeta son los demonios que están en ejecución, los usuarios que están logueados, los procesos que están activos, etc.

/var/spool: Directorio que almacena archivos que controlan la tareas pendientes de realizar. Así por ejemplo en el directorio /var/spool/cups encontraremos los archivos que gestionan los trabajos de impresión en espera, en el directorio /var/spool/cron encontraremos los archivos que gestionan las tareas planificadas pendientes de ejecutar, etc.

/var/tmp: Directorio que al igual que el directorio /tmp contiene archivos temporales. La principal diferencia entre los directorios /var/tmp y /tmp es que los archivos temporales ubicados en la carpeta /tmp se acostumbran a borrar automáticamente entre sesiones o reinicios del sistema, mientras que los archivos temporales ubicados en el directorio /var/tmp no lo hacen.

### Directorio /sys

Directorio que **contiene información similar a la del directorio /proc**. Dentro de esta carpeta podemos encontrar i**nformación estructurada y jerárquica acerca del kernel de nuestro equipo, de nuestras particiones y sistemas de archivo, de nuestros drivers**, etc.

### Directorio /lost+found

Directorio que se crea en las particiones de disco con un sistema de archivos ext después ejecutar herramientas para restaurar y recuperar el sistema operativo como por ejemplo fsch.

Si nuestro sistema no ha presentado problemas este directorio estará completamente vacío. En el caso que hayan habido problemas **este directorio contendrá ficheros y directorios que han sido recuperados tras la caída del sistema operativo**.

Para finalizar solo comentar que espero que esta pequeña explicación les haya sido útil para tener una idea genérica del contenido que se encuentra en cada una de las carpetas de nuestro sistema operativo.



ref: [Estructura de directorios en el sistema operativo GNU-Linux (geekland.eu)](https://geekland.eu/estructura-de-directorios-en-linux/)

- https://overthewire.org/wargames/bandit/        &rarr; para practicar Linux.
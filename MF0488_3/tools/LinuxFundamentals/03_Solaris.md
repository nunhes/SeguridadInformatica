# Solaris 

------

Solaris es un sistema operativo basado en Unix desarrollado por Sun  Microsystems (luego adquirido por Oracle Corporation) en la década de  1990. Es conocido por su robustez, escalabilidad y soporte para sistemas de hardware y software de alta gama. Solaris se utiliza ampliamente en  entornos empresariales para aplicaciones de misión crítica, como gestión de bases de datos, computación en la nube y virtualización. Por  ejemplo, incluye un hipervisor integrado llamado `Oracle VM Server for SPARC`, que permite ejecutar varias máquinas virtuales en un único servidor  físico. En general, está diseñado para manejar grandes cantidades de  datos y brindar servicios confiables y seguros a los usuarios y, a  menudo, se usa en entornos empresariales donde la seguridad, el  rendimiento y la estabilidad son requisitos clave. 

El objetivo de Solaris es proporcionar una plataforma altamente  estable, segura y escalable para la informática empresarial. Tiene  funciones integradas para alta disponibilidad, tolerancia a fallas y  administración de sistemas, lo que lo hace ideal para aplicaciones de  misión crítica. Se utiliza ampliamente en los sectores bancario,  financiero y gubernamental, donde la seguridad, la confiabilidad y el  rendimiento son primordiales. También se utiliza en centros de datos a  gran escala, entornos de computación en la nube y plataformas de  virtualización. Empresas como Amazon, IBM y Dell utilizan Solaris en sus productos y servicios, destacando su importancia en la industria. 

------

## Distribuciones de Linux frente a Solaris 

Las distribuciones Solaris y Linux son dos tipos de sistemas operativos  que se diferencian significativamente. En primer lugar, Solaris es un  sistema operativo propietario propiedad de Oracle Corporation y  desarrollado por ella, y su código fuente no está disponible para el  público en general. Por el contrario, la mayoría de las distribuciones  de Linux son de código abierto, lo que significa que su código fuente  está disponible para que cualquiera pueda modificarlo y utilizarlo.  Además, las distribuciones de Linux suelen utilizar el sistema de  archivos Zettabyte ( `ZFS`), que es un sistema de archivos  muy avanzado que ofrece funciones como compresión de datos, instantáneas y alta escalabilidad. Por otro lado, Solaris utiliza una instalación de gestión de servicios ( `SMF`), que es un marco de gestión de servicios muy avanzado que proporciona mayor confiabilidad y  disponibilidad para los servicios del sistema. 

| **Directorio** | **Descripción**                                              |
| -------------- | ------------------------------------------------------------ |
| `/`            | El directorio raíz contiene todos los demás directorios y archivos del sistema de archivos. |
| `/bin`         | Contiene archivos binarios del sistema esenciales que se requieren para el arranque y las operaciones básicas del sistema. |
| `/boot`        | El directorio de inicio contiene archivos relacionados con el inicio, como el cargador de inicio y las imágenes del kernel. |
| `/dev`         | El directorio dev contiene archivos de dispositivos que representan dispositivos físicos y lógicos conectados al sistema. |
| `/etc`         | El directorio etc contiene archivos de configuración del sistema,  como scripts de inicio del sistema y datos de autenticación del usuario. |
| `/home`        | Directorios de inicio de los usuarios.                       |
| `/kernel`      | Este directorio contiene módulos del kernel y otros archivos relacionados con el kernel. |
| `/lib`         | Directorio de bibliotecas requeridas por los binarios en los directorios /bin y /sbin. |
| `/lost+found`  | Este directorio lo utiliza la herramienta de reparación y  verificación de coherencia del sistema de archivos para almacenar  archivos recuperados. |
| `/mnt`         | Directorio para montar sistemas de archivos temporalmente.   |
| `/opt`         | Este directorio contiene paquetes de software opcionales que están instalados en el sistema. |
| `/proc`        | El directorio proc proporciona una vista del proceso del sistema y del estado del kernel como archivos. |
| `/sbin`        | Este directorio contiene los archivos binarios del sistema necesarios para las tareas de administración del sistema. |
| `/tmp`         | Los archivos temporales creados por el sistema y las aplicaciones se almacenan en este directorio. |
| `/usr`         | El directorio usr contiene datos y programas de solo lectura para  todo el sistema, como documentación, bibliotecas y ejecutables. |
| `/var`         | Este directorio contiene archivos de datos variables, como registros del sistema, spools de correo y spools de impresora. |

Solaris tiene una serie de características únicas que lo diferencian  de otros sistemas operativos. Una de sus fortalezas clave es su soporte  para sistemas de hardware y software de alta gama. Está diseñado para  funcionar con centros de datos de gran escala e infraestructuras de red  complejas, y puede manejar grandes cantidades de datos sin problemas de  rendimiento. 

En términos de gestión de paquetes, Solaris utiliza el Image Packaging System ( `IPS`) administrador de paquetes, que proporciona una forma poderosa y  flexible de administrar paquetes y actualizaciones. Solaris también  proporciona funciones de seguridad avanzadas, como control de acceso  basado en roles ( `RBAC`) y controles de acceso obligatorios, que no están disponibles en todas las distribuciones de Linux. 

------

## Diferencias 

Profundicemos en las diferencias entre las distribuciones de Solaris y Linux. Una de las diferencias más importantes es que el código fuente  no es de código abierto y sólo se conoce en círculos cerrados. Esto  significa que, a diferencia de Ubuntu o muchas otras distribuciones, el  público no puede ver ni analizar el código fuente. En resumen, las  principales diferencias se pueden agrupar en las siguientes categorías: 

- Sistema de archivos 
- Gestión de procesos 
- Gestión de paquetes 
- Soporte de kernel y hardware 
- Monitoreo del sistema 
- Seguridad 

Para comprender mejor las diferencias, echemos un vistazo a algunos ejemplos y comandos. 

#### Información del sistema 

En Ubuntu usamos el `uname` comando para mostrar  información sobre el sistema, como el nombre del kernel, el nombre del  host y el sistema operativo. Esto podría verse así: 

```shell-session
nunhes@htb[/htb]$ uname -a

Linux ubuntu 5.4.0-1045 #48-Ubuntu SMP Fri Jan 15 10:47:29 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux
```

Por otro lado, en Solaris, el `showrev` El comando se  puede utilizar para mostrar información del sistema, incluida la versión de Solaris, el tipo de hardware y el nivel de parche. A continuación se muestra un resultado de ejemplo: 

```shell-session
$ showrev -a

Hostname: solaris
Kernel architecture: sun4u
OS version: Solaris 10 8/07 s10s_u4wos_12b SPARC
Application architecture: sparc
Hardware provider: Sun_Microsystems
Domain: sun.com
Kernel version: SunOS 5.10 Generic_139555-08
```

La principal diferencia entre los dos comandos es que `showrev` proporciona información más detallada sobre el sistema Solaris, como el nivel de parche y el proveedor de hardware, mientras `uname` Sólo proporciona información básica sobre el sistema Linux. 

#### Instalación de paquetes 

En Ubuntu, el `apt-get` El comando se utiliza para instalar paquetes. Esto podría parecerse a lo siguiente: 

```shell-session
nunhes@htb[/htb]$ sudo apt-get install apache2
```

However, in Solaris, we need to use `pkgadd` to install packages like `SUNWapchr`.

```shell-session
$ pkgadd -d SUNWapchr
```

La principal diferencia entre los dos comandos es la sintaxis y el  administrador de paquetes utilizado. Ubuntu usa Advanced Packaging Tool  (APT) para administrar paquetes, mientras que Solaris usa Solaris  Package Manager (SPM). Además, tenga en cuenta que no utilizamos `sudo` en este caso. Esto se debe a que Solaris utilizó el `RBAC` herramienta de gestión de privilegios, que permitía la asignación de permisos granulares a los usuarios. Sin embargo, `sudo` has been supported since Solaris 11.

#### Gestión de permisos 

En sistemas Linux como Ubuntu pero también en Solaris, el `chmod` El comando se utiliza para cambiar los permisos de archivos y  directorios. A continuación se muestra un comando de ejemplo para  otorgar permisos de lectura, escritura y ejecución al propietario del  archivo: 

```shell-session
nunhes@htb[/htb]$ chmod 700 filename
```

Para buscar archivos con permisos específicos en Ubuntu, usamos el `find` dominio. Echemos un vistazo a un ejemplo de un archivo con el bit SUID establecido: 

```shell-session
nunhes@htb[/htb]$ find / -perm 4000
```

Para buscar archivos con permisos específicos, como con el bit SUID  configurado en Solaris, también podemos usar el comando buscar, pero con un pequeño ajuste. 

```shell-session
$ find / -perm -4000
```

La principal diferencia entre estos dos comandos es el uso del `-` antes del valor del permiso en el comando Solaris. Esto se debe a que  Solaris utiliza un sistema de permisos diferente al de Linux. 

#### NFS en Solaris 

Solaris tiene su propia implementación de NFS, que es ligeramente  diferente de distribuciones de Linux como Ubuntu. En Solaris, el  servidor NFS se puede configurar mediante el `share` comando, que se utiliza para compartir un directorio a través de la red, y  también nos permite especificar varias opciones como permisos de  lectura/escritura, restricciones de acceso y más. Para compartir un  directorio a través de NFS en Solaris, podemos usar el siguiente  comando: 

```shell-session
$ share -F nfs -o rw /export/home
```

Este comando comparte el `/export/home` Directorio con permisos de lectura y escritura sobre NFS. Un cliente NFS puede montar el sistema de archivos NFS utilizando el `mount` comando, de la misma manera que con Ubuntu. Para montar un sistema de  archivos NFS en Solaris, debemos especificar el nombre del servidor y la ruta al directorio compartido. Por ejemplo, para montar un recurso  compartido NFS desde un servidor con la dirección IP `10.129.15.122` y el directorio compartido `/nfs_share`, utilizamos el siguiente comando: 

```shell-session
nunhes@htb[/htb]$ mount -F nfs 10.129.15.122:/nfs_share /mnt/local
```

En Solaris, la configuración para NFS se almacena en el `/etc/dfs/dfstab` archivo. Este archivo contiene entradas para cada directorio compartido, junto con las diversas opciones para compartir NFS. 

```shell-session
# cat /etc/dfs/dfstab

share -F nfs -o rw /export/home
```

#### Mapeo de procesos 

El mapeo de procesos es un aspecto esencial de la administración y resolución de problemas del sistema. El `lsof` comando es una poderosa utilidad que enumera todos los archivos  abiertos por un proceso, incluidos los sockets de red y otros  descriptores de archivos que podemos usar en distribuciones Debian como  Ubuntu. podemos usar `lsof` para enumerar todos los archivos  abiertos por un proceso. Por ejemplo, para enumerar todos los archivos  abiertos por el proceso del servidor web Apache, podemos usar el  siguiente comando: 

```shell-session
nunhes@htb[/htb]$ sudo lsof -c apache2
```

En Solaris, el `pfiles` El comando se puede utilizar para  enumerar todos los archivos abiertos por un proceso. Por ejemplo, para  enumerar todos los archivos abiertos por el proceso del servidor web  Apache, podemos usar el siguiente comando: 

```shell-session
$ pfiles `pgrep httpd`
```

Este comando enumera todos los archivos abiertos por el proceso del servidor web Apache. La salida del `pfiles` El comando es similar a la salida del `lsof` comando y proporciona información sobre el tipo de descriptor de  archivo, el número del descriptor de archivo y el nombre del archivo. 

#### Acceso ejecutable 

En Solaris, `truss` Se utiliza, que es una utilidad muy  útil para desarrolladores y administradores de sistemas que necesitan  depurar problemas de software complejos en el sistema operativo Solaris. Al rastrear las llamadas al sistema realizadas por un proceso, `truss` puede ayudar a identificar el origen de errores, problemas de  rendimiento y otros problemas, pero también puede revelar información  confidencial que puede surgir durante el desarrollo de aplicaciones o el mantenimiento del sistema. La utilidad también puede proporcionar  información detallada sobre las llamadas al sistema, incluidos los  argumentos que se les pasan y sus valores de retorno, lo que permite a  los usuarios comprender mejor el comportamiento de sus aplicaciones y el sistema operativo subyacente. 

`Strace` es una alternativa a `truss` sino para Ubuntu, y es una herramienta esencial tanto para administradores de  sistemas como para desarrolladores, que les ayuda a diagnosticar y  solucionar problemas en tiempo real. Permite a los usuarios analizar las interacciones entre el sistema operativo y las aplicaciones que se  ejecutan en él, lo que resulta especialmente útil en entornos altamente  complejos y de misión crítica. Con `truss`, los usuarios  pueden identificar y aislar rápidamente problemas relacionados con el  rendimiento de las aplicaciones, la conectividad de la red y la  utilización de los recursos del sistema, entre otros. 

Por ejemplo, para rastrear las llamadas al sistema realizadas por el  proceso del servidor web Apache, podemos usar el siguiente comando: 

```shell-session
nunhes@htb[/htb]$ sudo strace -p `pgrep apache2`
```

A continuación se muestra un ejemplo de cómo utilizar `truss` para rastrear las llamadas al sistema realizadas por el `ls` comando en Solaris: 

```shell-session
$ truss ls

execve("/usr/bin/ls", 0xFFBFFDC4, 0xFFBFFDC8)  argc = 1
...SNIP...
```

La salida es similar a `strace`, pero el formato es ligeramente diferente. Una diferencia entre `strace` y `truss` es eso `truss` También puede rastrear las señales enviadas a un proceso, mientras `strace` no puedo. Otra diferencia es que `truss` tiene la capacidad de rastrear las llamadas al sistema realizadas por procesos secundarios, mientras `strace` Solo puede rastrear las llamadas al sistema realizadas por el proceso especificado en la línea de comando. 





---

https://academy.hackthebox.com/module/18/section/2101
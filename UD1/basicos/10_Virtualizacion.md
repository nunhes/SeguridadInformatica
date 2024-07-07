# Virtualización

---

**Introducción**

La virtualización nos permite entender mejor conceptos de hardware y software, y si quieres aprender hacking ético, es de muchísima utilidad. Entre otras cosas, te permite montar tus propios laboratorios de hacking en los que practicar diferentes técnicas. Si quieres aprender hacking ético, la virtualización es un tema fundamental que no te debes saltar.

Empezaremos abordando conceptos básicos sobre sistemas operativos. Lo único que necesitas saber es algo de hardware y que impacto tiene la virtualización en el rendimiento de tu máquina anfitrión y en componentes como la memoria RAM o el procesador de un dispositivo.

Aprenderemos a instalar y configurar VirtualBox, a crear máquinas virtuales e instalar sistemas operativos basados en Linux y en Windows en ellas. He elegido VirtualBox porque es un software de código abierto y gratuito, y nos va a ofrecer todas las funcionalidades que necesitamos. Además, VirtualBox pude ser muy útil en tu aprendizaje ya que te permitirá montar laboratorios de hacking, por eso es bueno entender lo mejor posible esta herramienta.

Aunque el propósito de esta serie de cursos sea aprender hacking ético, en este curso de virtualización no vamos a instalar Kali Linux ni ninguna distribución de Linux específica de ciberseguridad. Eso lo vamos a dejar para el próximo curso de Linux para hacking ético.

**Toma notas**

Para tomar notas, puedes usar Notion, CherryTree, Obsidian, Google Docs, un editor Markdown o tu cuaderno, la que quieras. Trata de acompañar tus notas con capturas de pantalla. Puedes usar la Herramienta de recorte de Windows o cualquier otra que te resulte cómoda.

[Flameshot](https://flameshot.org).

---

## **Fundamentos de Sistemas Operativos**

### ¿Qué es un sistema operativo?

Un sistema operativo es un programa que permite la interacción con un ordenador. Básicamente, las funciones principales de un sistema operativo son administrar los recursos del ordenador, controlar el uso de la CPU, la memoria RAM y otros componentes para asegurarse de que los programas funcionen sin conflictos. También organizan y administran archivos y documentos. El sistema operativo te permite almacenar y organizar tus archivos en carpetas, facilitando así el acceso y la gestión de tu información.

Por otro lado, también controlan los periféricos. Se encargan de conectar y hacer funcionar los dispositivos, como por ejemplo impresoras o escáneres, permitiendo utilizarlos sin problemas, por ejemplo por medio de drivers.

Otra característica principal de un sistema operativo es el hecho de proporcionar a un usuario una interfaz. Se puede ofrecer una **interfaz gráfica** o una **interfaz de línea de comandos** que te permite interactuar con tu dispositivo de una forma relativamente amigable y cómoda, según el propio sistema operativo.

Los sistemas operativos se pueden clasificar según el hardware y la función de cada dispositivo. Hay dos tipos principales: los **sistemas operativos para ordenador** y los **sistemas operativos para dispositivos móviles**. Algunos ejemplos de sistemas operativos para ordenador son Windows, Linux o macOS, y algunos ejemplos de sistemas operativos para dispositivos móviles son Android y iOS.

Tanto macOS como iOS son sistemas operativos de Apple. Windows sería de Microsoft. Y, tanto Linux como Android son de código libre. Otra forma de clasificar los sistemas operativos es referirse a ellos por sus licencias, y aquí encontramos  sistemas operativos de código abierto - Linux, Android- y  sistemas operativos de código propietario - iOS, macOS, Windows-.

La principal diferencia entre un sistema operativo de código abierto y uno propietario está en el tipo de licencia que cada uno adopta y las libertades de uso. El software propietario tiene una licencia comercial donde tienes que pagarle a un desarrollador para usar el sistema y generalmente no es posible acceder o editar el código fuente: el código original en el que está escrito el propio sistema operativo. El software de código abierto tiene una licencia que permite a cualquiera acceder y modificar el código, así como distribuirlo libremente y gratuitamente. 

A la hora de elegir un sistema operativo, es bueno tener en cuenta las aplicaciones que vas a necesitar instalar en él, ya que la elección del sistema operativo afecta a las aplicaciones disponibles. No todas las aplicaciones están disponibles para todos los sistemas operativos. La mayoría de herramientas de hacking están disponibles para sistemas operativos Linux, pero no todas están disponibles para sistemas operativos Windows.

¿Se te ocurre algún sistema operativo que no haya mencionado? Probablemente ese sistema operativo sea una distribución de Linux o use su kernel. Linux es un sistema operativo compuesto por distintos programas desarrollados por diferentes autores y unidos para funcionar en conjunto como un solo sistema. Estrictamente hablando, Linux es el kernel de estos sistemas operativos.

### ¿Qué es el kernel?

El kernel actúa como intermediario entre las aplicaciones y el hardware de un ordenador. Linux y GNU/Linux son dos formas de llamar a un sistema operativo que usa el kernel de Linux, que es la parte que controla el hardware. GNU es un proyecto que quiere crear un sistema operativo libre y completo que incluye muchas herramientas y programas, además del propio kernel de Linux. GNU/Linux es el sistema operativo que usa GNU y el kernel de Linux, y es el que usan muchas distribuciones como Debian o Ubuntu. Linux es solamente una parte de ese sistema operativo; Linux es el kernel y no todos los sistemas operativos que lo usan son GNU/Linux. Por ejemplo, Android usa el kernel de Linux, pero no usa otras herramientas de GNU. Comúnmente usamos el término Linux para referirnos al ecosistema completo de Linux, aunque esto, estrictamente hablando, no es correcto.

### ¿Dónde se utiliza Linux?

Linux se utiliza en servidores, en routers y en otros muchos dispositivos, por ejemplo, en dispositivos de Internet of Things (IoT), de domótica y demás, debido principalmente a su flexibilidad y a su bajo coste o coste cero. Otros sistemas operativos basados en Linux incluyen, por ejemplo, ChromeOS para ultraportátiles o WebOS, que es básicamente una distribución de Linux para SmartTVs de la marca LG.

En este curso vamos a instalar dos distribuciones de Linux diferentes en máquinas virtuales utilizando un hipervisor. ¿Pero qué es un hipervisor y qué es una máquina virtual? 

## **Fundamentos de Virtualización**

### **¿Qué es la Virtualización?**

La virtualización es la creación de una versión virtual de algo, como una plataforma de hardware, un sistema operativo, un dispositivo de almacenamiento o un recurso de red. Cuando trabajamos con máquinas virtuales, estamos virtualizando tanto el hardware como el software. Por ejemplo, estamos virtualizando un disco de almacenamiento para instalar un sistema operativo en él.

Digamos que este es nuestro PC con su hardware: CPU, memoria RAM, dispositivo de almacenamiento, etc. Cuando creamos una máquina virtual dentro de nuestro PC, lo que estamos haciendo es crear un PC dentro del nuestro, corriendo sobre el software anfitrión de nuestro propio ordenador. Básicamente, si nuestro ordenador tiene Windows 11, podríamos crear una máquina virtual que corra sobre ese Windows 11 (o Windows 10, o el sistema operativo que sea). Esta máquina virtual también tendrá una asignación de recursos basada en los recursos del PC anfitrión, como parte de la memoria RAM y CPU.

De la misma forma, podríamos crear dos, tres, cuatro o más máquinas virtuales, teniendo en cuenta que la repartición de recursos del sistema anfitrión se divide entre esas máquinas, consumiendo recursos del hardware del dispositivo anfitrión. En este ejemplo, utilizamos un sistema operativo Windows 11. Para hacer esto, necesitamos un software de virtualización que actúe como hipervisor.

### **¿Qué es un Hipervisor?**

Un hipervisor es una capa de software que permite la creación y gestión de máquinas virtuales. Existen dos tipos de hipervisores: 

1. **Hipervisores de Tipo 1 (Bare Metal):** El hipervisor se instala directamente en el hardware y sobre él se configuran las diferentes máquinas virtuales con sus respectivos sistemas operativos invitados.
2. **Hipervisores de Tipo 2 (Hosted):** El hipervisor se instala en un sistema operativo anfitrión (como Windows 10 o Windows 11), que está instalado sobre el hardware. Sobre el hipervisor corren las máquinas virtuales con sistemas operativos invitados.

Los hipervisores de tipo 2 son los más comúnmente utilizados y los que vamos a usar en este curso.

### **Software de Virtualización**

Existen diferentes software de virtualización, entre ellos:

- **VMware:** Líder en virtualización empresarial con productos como VMware ESXi y VMware Workstation.
- **Hyper-V:** Solución de virtualización de Microsoft para servidores y ordenadores de escritorio.
- **VirtualBox:** Software de virtualización gratuito y de código abierto de Oracle.
- **Citrix:** Ofrece soluciones de virtualización para aplicaciones y escritorios.

### **Ventajas de Virtualizar en Ciberseguridad**

Las ventajas de la virtualización en ciberseguridad incluyen:

1. **Comprobar el comportamiento de una aplicación en varios sistemas operativos.**
2. **Ejecutar programas desconocidos en un entorno virtual seguro, minimizando el riesgo de infección de malware en el sistema principal.**
3. **Realizar análisis estáticos y dinámicos de malware.**
4. **Crear laboratorios en local para practicar técnicas de pen testing o hacking ético.**

Estos entornos están controlados y autorizados, permitiendo realizar pruebas de seguridad sin afectar a un entorno de producción.

### **Consideraciones de Seguridad**

Aunque las máquinas virtuales pueden ser objetivos de ataque, se pueden tomar medidas para mejorar su seguridad, como:

- Asegurar las máquinas virtuales lo más posible.
- Exponer el menor número de servicios posibles.
- Mantener las máquinas virtuales actualizadas.
- Separar el tráfico de red de las máquinas virtuales de la red local.

Durante este curso, pondremos a prueba estas medidas de mitigación y configuraremos nuestros laboratorios de la forma más segura posible.

### **Comparativa entre VirtualBox y VMware**

Los dos principales hipervisores de tipo 2 son VirtualBox y VMware, y hay ciertas diferencias entre ellos:

- **Precio:** VirtualBox es gratuito y de código abierto. VMware Workstation Player es gratuito para uso no comercial, pero de pago para uso comercial.
- **Compatibilidad:** VirtualBox funciona en todas las plataformas x86 (Windows, Mac, Linux, Solaris). VMware Workstation Player funciona con Windows y Linux, pero requiere VMware Fusion para Mac.
- **Número de Máquinas Virtuales Activas:** VMware Workstation Player está limitado a una máquina virtual activa de forma simultánea. VirtualBox permite hasta 32 máquinas virtuales activas.

Por estas razones, utilizaremos VirtualBox. Además, VirtualBox permite instalar fácilmente máquinas de forma desatendida, omitiendo el asistente de instalación del sistema operativo, y crear **snapshots**, lo cual no está disponible en la versión gratuita de VMware.

En los siguientes pasos utilizaremos VirtualBox, aunque conocer ambos software es altamente beneficioso.

## **Instalación y Configuración Inicial**

Para instalar VirtualBox, primero necesitamos acceder a su página web oficial: [virtualbox.org](https://www.virtualbox.org). Una vez en la página, veremos un botón enorme que dice en inglés "Download VirtualBox 7.0". Esto nos llevará a elegir diferentes sistemas operativos anfitriones, es decir, descagaremos la versión adecuada al sistema operativo en el que vamos a instalar VirtualBox. En mi caso, haré clic en [Windows hosts](https://download.virtualbox.org/virtualbox/7.0.18/VirtualBox-7.0.18-162988-Win.exe). Esto descargará un ejecutable.

Una vez descargado, ejecutamos el archivo. Esto abrirá un asistente de instalación de VirtualBox. Pulsamos "Next" en las primeras pantallas, y luego "Install". Es posible que aparezca un mensaje indicando que faltan ciertas dependencias; seleccionamos "Yes" para que se instalen. Tras unos minutos, la instalación habrá terminado.

Después de la instalación, se nos preguntará si queremos iniciar VirtualBox. Desactivamos esta opción porque el siguiente paso es instalar una serie de paquetes de extensión para VirtualBox, llamados "VirtualBox Extension Pack". Estos paquetes permiten el uso de dispositivos USB 2.0 y USB 3.0, cifrado de discos, y más ventajas, y además son gratuitos.

Para instalar el [VirtualBox Extension Pack](https://download.virtualbox.org/virtualbox/7.0.18/Oracle_VM_VirtualBox_Extension_Pack-7.0.18.vbox-extpack), volvemos a la página de descargas y descargamos el archivo correspondiente. Ejecutamos este archivo para instalarlo. Es posible que aparezca una pregunta si ya tenemos una versión instalada; en ese caso, seleccionamos "Reinstalar". Aceptamos los términos y condiciones y completamos la instalación.

### **Creación de una Máquina Virtual en VirtualBox**

Ahora vamos a crear nuestra primera máquina virtual en VirtualBox. Puedes maximizar la ventana de VirtualBox para que sea más fácil de seguir.

Para crear una nueva máquina virtual, hacemos clic en el botón "Nueva" en la parte superior. Primero, debemos nombrar la máquina virtual. En este caso, vamos a crear una máquina Debian, así que la nombraremos "Debian".

Luego, seleccionamos el directorio en el que se guardarán todos los archivos relacionados con esta máquina virtual, incluido el disco de almacenamiento. En el apartado de imagen ISO, lo dejamos en blanco porque vamos a hacer la instalación manualmente.

En el siguiente paso, seleccionamos el tipo de sistema operativo (Linux) y la versión (Debian 12). Esto es principalmente para fines de organización.

Asignamos la cantidad de memoria RAM y hilos de CPU. Para Debian, 2 GB de RAM son suficientes. En cuanto a los procesadores, asignamos 2 hilos. **Es importante recordar que estos recursos serán consumidos por la máquina virtual mientras esté activa**.

Luego, creamos un disco duro virtual. Seleccionamos la opción de disco duro VDI (Virtual Disk Image) y elegimos la opción de almacenamiento dinámico, que crecerá a medida que se almacenen datos en él. Establecemos el tamaño máximo en 20 GB.

Finalmente, revisamos la configuración: el nombre de la máquina, el directorio, el tipo de sistema operativo, la cantidad de RAM y procesadores, y el tamaño del disco. Hacemos clic en "Terminar" para completar la creación de la máquina virtual.

Ya hemos creado nuestra máquina virtual. El siguiente paso será instalar Debian manualmente en esta máquina virtual. 

### Instalación Manual de Debian

Vamos a proceder con la instalación de Debian en la máquina virtual recién creada. Para ello, debemos descargar una imagen ISO y asignarla a la unidad de disco virtual de nuestra máquina virtual.

1. **Descarga de la Imagen ISO:**
   - Accedemos a la página oficial de Debian: `debian.org`.
   - Pulsamos en el botón "Descargar" para obtener la última versión, que en este caso es Debian 12.5.0.
   - La imagen ISO se descargará en el directorio de descargas de nuestro PC.

2. **Asignación de la Imagen ISO:**
   - Abrimos VirtualBox y seleccionamos nuestra máquina virtual.
   - Vamos a `Configuración`, luego a `Almacenamiento`.
   - Asignamos la imagen ISO descargada al emulador de unidad óptica virtualizada.
   - Seleccionamos la imagen ISO y confirmamos.

3. **Arranque e Instalación:**
   - Iniciamos la máquina virtual.
   - Seleccionamos `graphical install` para realizar la instalación con interfaz gráfica.
   - Elegimos el idioma, la ubicación y configuramos el teclado.
   - Introducimos un nombre para la máquina, el nombre de dominio y configuramos usuarios y contraseñas.
   
   

   - Seleccionamos la opción de particionado guiado para usar todo el disco asignado (20 GB).
   - Confirmamos la escritura de los cambios en el disco.
   
4. **Configuración del Gestor de Paquetes:**
   - Seleccionamos la ubicación del gestor de paquetes y omitimos la información sobre el Proxy.
   - Configuramos el gestor de paquetes apt.

5. **Selección de Programas e Instalación del Entorno de Escritorio:**
   - Seleccionamos los programas a instalar, incluyendo el entorno de escritorio. Por defecto, se selecciona GNOME.
   - Elegimos instalar el cargador de arranque GRUB.

6. **Finalización de la Instalación:**
   - Una vez terminada la instalación, reiniciamos la máquina virtual.
   - Accedemos al sistema operativo Debian con la ventana de inicio de sesión.
   - Completamos la configuración inicial del asistente de instalación.

7. **Ajustes Post-Instalación:**
   - La ventana del sistema operativo puede verse pequeña; esto se solucionará instalando las `guest additions` en pasos posteriores.

A continuación, exploraremos las configuraciones y características básicas de VirtualBox. 

## Configuraciones y características básicas de VirtualBox

Antes de seguir con la configuración de nuestra máquina Dean, vamos a echarle un vistazo a las diferentes opciones de configuración de VirtualBox. Como software de virtualización, hay que saber que VirtualBox diferencia entre la configuración de las propias máquinas, independientes de las máquinas virtuales que vayas instalando dentro del software, y la configuración del propio software de la aplicación de VirtualBox.

Así que vamos a echarle un vistazo a esta segunda. Para empezar, retomamos donde lo dejamos. Aquí tenemos nuestra máquina virtual que acabamos de crear. Voy a minimizarla por el momento porque no me va a hacer falta para esta clase y vamos a ir a Archivo.

Bueno, aquí tenemos diferentes botones. Tenemos "Configuración", que esta configuración, recordemos, es relativa a la propia máquina virtual, pero en este caso vamos a echarle un vistazo a la configuración de la propia aplicación de VirtualBox. Vamos a darle por aquí a "Preferencias" y vamos a echar un vistazo a algunas de las características más básicas y esenciales.

Dentro de la configuración de VirtualBox, tenemos por aquí la carpeta predeterminada de las máquinas, que la hemos visto también en clases anteriores cuando hemos instalado VirtualBox y creado la máquina virtual. En "Entrada" podemos echar un vistazo a las diferentes teclas, los diferentes atajos de teclas para VirtualBox. Lo más relevante aquí es que la tecla "Anfitrión" está asignada a Control Derecha, al control de la parte derecha de vuestro teclado. Esto va a ser una tecla bastante esencial porque combinando esta tecla con diferentes otras teclas, podemos hacer diferentes cosas en relación a la propia máquina virtual cuando se esté ejecutando. Por ejemplo, podríamos usar Control Derecha más la tecla F para poner en pantalla completa la máquina virtual que se esté ejecutando en ese momento, y también para pasar de pantalla completa a modo ventana utilizando de nuevo ese mismo atajo de teclas: Control Derecha + F. En este caso, también nos va a servir por si el cursor se bloquea dentro de la propia máquina virtual, para sacar el cursor.

Es muy importante tener en cuenta que hay que pulsar la tecla "Anfitrión" para salir de esa ventana. Si nos movemos a "Actualizar", lo que nos permite esta opción es comprobar actualizaciones cada cierto tiempo. En mi caso, suelo dejarlo desactivado porque me gusta hacerlo de forma manual cuando voy viendo. En "Idioma", podemos, como su propio nombre indica, configurar el idioma de la propia aplicación. En "Pantalla", tenemos diferentes opciones que en mi caso son bastante irrelevantes y que nunca o casi nunca he tenido que tocar. En "Proxy", más de lo mismo, y en "Interfaz", más de lo mismo. Esto es para asignar un color del tema a la propia aplicación. Si en tu propio sistema operativo estás utilizando el modo oscuro, como es mi caso, pues directamente se te asigna el modo oscuro para la propia aplicación. Digamos que esta opción se hereda y directamente el propio VirtualBox se me queda en modo oscuro.

Vamos a aceptar por aquí abajo y vamos a echarle un vistazo a los diferentes apartados de herramientas. Vamos a pulsar por aquí, por "Herramientas". Y esto, de nuevo, son opciones relativas al propio VirtualBox. Si pulsamos sobre "Preferencias", nos va a llevar a la ventana que hemos enumerado previamente y a la que hemos echado un vistazo a cada una de las opciones previamente. Pero también en "Herramientas" podemos encontrar, en la parte derecha, por aquí, un pequeño menú hamburguesa. Si pulsamos, tenemos diferentes secciones dentro de las propias herramientas.

Tenemos "Extensiones". Vemos por aquí confirmamos esa instalación que hemos hecho en clases anteriores del paquete de extensión del propio VirtualBox. Si nos vamos de nuevo al menú de hamburguesa y pasamos sobre "Medio", vamos a ver una lista completa de los medios de los discos virtuales que hemos creado. Y desde aquí también podemos añadir, de forma independiente a las propias máquinas, diferentes imágenes de disco. Podemos crear otras nuevas, podemos copiar este mismo disco virtualizado que hemos creado previamente, liberar, tenemos diferentes opciones. Y también tenemos diferentes opciones para los discos ópticos.

No tenemos por aquí una pequeña advertencia, y es que no se está encontrando ese archivo porque lo he borrado. Esto es un caso propio, en tu caso no debería ser así. Pero en este caso, podría yo eliminarlo para eliminar ese error. Simplemente, no está encontrando una imagen ISO que yo he utilizado para hacer pruebas previamente. Y esta es la imagen ISO que sí que encuentra, que está en la carpeta de descargas de mi propio usuario.

Tenemos por aquí la posibilidad de manipular discos flexibles, que esto ya es bastante antiguo. Esto, de momento, es una opción que no vamos a echar un vistazo ni nosotros, ni probablemente nadie. Y si pulsamos de nuevo por el menú hamburguesa, pues de nuevo tenemos otra opción, que es "Red". Aquí sí que vamos a realizar diferentes configuraciones en clases posteriores porque esto es un tema bastante importante dentro de VirtualBox y entender esto es muy importante para configurar tus máquinas virtuales de la forma más segura.

Si volvemos al menú hamburguesa, tenemos "Cloud". Esto lo vamos a ignorar de momento. Y tenemos también "Actividades". En "Actividades", podemos ver el consumo de los recursos de las diferentes máquinas virtuales. Bueno, pues ya hemos echado un pequeño vistazo superficial a las diferentes opciones del propio VirtualBox. En la siguiente clase, vamos a instalar las Guest Additions en la máquina Dean que hemos creado previamente. Nos vemos por allí.

### Instalación de Guest Additions

Vamos con la instalación de nuestras Guest Additions en nuestra máquina virtualizada Dean. Las Guest Additions son un conjunto de controladores y aplicaciones que se instalan en una máquina virtual con el objetivo de mejorar sus funcionalidades y también su rendimiento. Algunas de las características relevantes dentro de las Guest Editions son:

- La integración completa del teclado y el ratón desde la máquina de anfitrión a la máquina virtual. Esto nos permite utilizar el portapapeles de la máquina anfitrión en la máquina virtual y viceversa, haciendo Control+C, Control+V para copiar y pegar desde la máquina virtual a la máquina anfitrión y viceversa.
  
- Además, nos da la posibilidad de crear carpetas compartidas entre la máquina anfitrión y la máquina virtual para compartir archivos. También vamos a ver una mejora del rendimiento gráfico bastante notable.

Para instalar las Guest Additions, primero tenemos que introducir un disco virtual de las propias Guest Additions. Esto es muy sencillo. En el menú de la parte superior izquierda de la propia máquina virtual, podemos encontrar bajo la pestaña de "Dispositivos" una opción que dice "Insertar imagen de CD de los Complementos de Invitado" (Guest Additions en inglés). Vamos a pulsar por aquí y esto va a hacer que se monte directamente dentro de nuestro sistema operativo Linux un CD, una unidad externa que incluya el asistente de instalación de las Guest Additions.

En este punto, si desde el escritorio hacemos clic en "Actividades", en la parte inferior podemos ver una especie de archivador. No vamos a pulsar por aquí porque esto nos da la posibilidad de un gestor de ventanas para ver las diferentes carpetas de nuestro sistema operativo de una forma más visual que si lo hiciéramos desde una línea de comandos, por ejemplo. Aquí vemos en la parte izquierda que tenemos una unidad de CD/DVD llamada "VBoxGuestAdditions" y la versión también de esas Guest Additions.

Vamos a hacer clic por aquí. Aquí está, aquí tenemos el contenido de esa unidad de CD o DVD. Ahora, lo siguiente que vamos a hacer es un poquito más avanzado, si no has visto Linux, pero vamos a ir muy paso a paso para que se entienda todo correctamente o por lo menos para que se ejecute todo correctamente. Ten en cuenta que no tienes por qué entenderlo todo desde el principio porque puede ser una locura, la verdad. Pero ya poco a poco, especialmente en el curso de Linux para hacking ético, seguro que vas a entender todo esto que vamos a ver ahora bastante más en profundidad.

Así que vamos a hacer clic derecho en cualquier parte de la ventana en la que no haya un archivo o carpeta y vamos a pulsar sobre "Abrir en una terminal". Y esto lo que va a hacer es abrirnos un emulador de terminal en el que podemos ejecutar comandos. 

Vamos a ejecutar los siguientes comandos:

Para empezar, vamos a ejecutar `su` seguido de un espacio y un guion. Esto nos va a pedir la contraseña que hemos asignado previamente. La sesión cambiará del usuario normal al usuario root. Esto lo veremos más en profundidad en el curso de Linux para hacking ético.

```bash
su -
```

Ahora, vamos a ejecutar el siguiente comando:

```bash
usermod -aG sudo <nombre_de_usuario>
```

En mi caso, el nombre de usuario es `nunhes`. Este comando añade el usuario al grupo *sudo*, lo cual le da permisos administrativos. No vamos a entrar en profundidad sobre qué significa todo esto porque lo veremos más adelante en otras sesiones.

Vamos a ejecutar esto por aquí. Parece que no ha hecho nada a simple vista, pero realmente sí que lo ha hecho. Vamos a reiniciar esta máquina para que se apliquen estos cambios. Voy a reiniciar directamente desde aquí utilizando el comando `reboot` para reiniciar la propia máquina.

```bash
reboot
```

Una vez reiniciada la máquina, nos encontramos de nuevo en el escritorio de nuestra Debian. Para continuar con la instalación de las Guest Additions, vamos a abrir de nuevo el Explorador de archivos. Vamos a hacer clic derecho en cualquier parte de la ventana donde no haya un archivo o carpeta y pulsamos sobre "Abrir en una terminal".

En la terminal que se abre, vamos a ejecutar el siguiente comando para ver los grupos a los que pertenece el usuario actual:

```bash
id
```

Verificamos que dentro de todos los campos separados por comas, tengamos el campo `sudo` entre paréntesis después del nombre de nuestro usuario actual, en mi caso `zero`. Confirmado esto, vamos a ejecutar el siguiente comando para cambiar al usuario root:

```bash
sudo bash VBoxLinuxAdditions.run
```

Esto nos va a pedir confirmación. Vamos a escribir `Yes` para continuar con la instalación de las Guest Additions. Ya se están instalando las Guest Additions. Esto va a tardar unos segundos. Una vez finalizada la instalación, vamos a reiniciar el sistema de nuevo para aplicar los cambios.

Podemos hacerlo desde el entorno de escritorio pulsando en el botón que se encuentra en la parte superior derecha y seleccionando "Reiniciar".

Una vez reiniciado el sistema, nos encontramos de nuevo en nuestro escritorio de Debian. Para confirmar que hemos instalado correctamente las Guest Additions, podemos salir del modo de pantalla completa pulsando en este botón de la parte superior derecha y luego pulsando de nuevo sobre "Maximizar ventana". Debería redimensionar correctamente, confirmando así que hemos instalado correctamente las Guest Additions.

Antes de finalizar esta clase, vamos a expulsar el disco de las Guest Additions que hemos instalado previamente. Vamos a pulsar sobre "Actividades" y luego sobre "Archivos" de nuevo. Esto nos abre la misma carpeta, pero ahora tenemos una visión más completa del explorador de archivos.

Para expulsar la unidad, simplemente hay que pulsar sobre el icono de expulsar que está en la parte derecha de la unidad de CD/DVD donde están las Guest Additions. Vamos a pulsar por aquí para expulsar esa unidad y así finalizamos la configuración inicial de nuestra máquina Debian.

Ya tenemos una máquina Debian completamente operativa. A continuación, vamos a realizar algunas configuraciones adicionales para esta máquina, las cuales nos servirán para ejemplificar algunas configuraciones avanzadas de VirtualBox. 

## **Configuraciones de las Máquinas Virtuales en VirtualBox**

Vamos a explorar las configuraciones más relevantes relacionadas directamente con las máquinas virtuales que se pueden crear en VirtualBox.

VirtualBox diferencia entre la configuración del propio software de virtualización y la configuración específica de cada máquina virtual. Dependiendo de dónde nos encontremos dentro de VirtualBox, tendremos acceso a distintas opciones contextuales. Por ejemplo, al hacer clic en la herramienta correspondiente, las pestañas en la parte superior izquierda cambiarán según el contexto de la máquina virtual seleccionada.

Cuando estamos sobre una máquina virtual recién creada, las opciones en la parte superior incluirán pestañas como Recursos y Configuración. En la herramienta de Recursos, podemos gestionar aspectos como almacenamiento y configuraciones avanzadas. Mientras que al hacer clic sobre la máquina virtual en sí, accedemos a la pestaña de Configuración, donde encontramos detalles como el nombre, tipo y versión de la máquina virtual.

Dentro de la pestaña Avanzado, tenemos opciones como Carpetas de instantáneas, aunque esto se discutirá más adelante. También podemos configurar el Portapapeles compartido para permitir copiar y pegar texto bidireccionalmente entre la máquina anfitriona y la virtual.

Existe la opción de Arrastrar y soltar, útil para mover archivos entre la máquina anfitriona y la virtual, pero puede ser problemático en términos de estabilidad y experiencia de usuario, por lo que es recomendable usar con precaución o desactivarlo.

La opción de Descripción permite asignar un nombre descriptivo a la máquina virtual para recordar su propósito o uso, como un "Laboratorio de Hacking".

El Cifrado de disco está disponible para proteger el disco duro de la máquina virtual en caso de que la máquina anfitriona esté comprometida, aunque en muchos casos se considera innecesario para entornos de práctica o laboratorios.

En la sección Sistema, configuramos recursos de hardware como la asignación de memoria y el número de procesadores lógicos. Es importante ajustar la memoria y otros recursos según las necesidades específicas de cada máquina virtual.

En la pestaña Pantalla, ajustamos la cantidad de memoria de video asignada y otros ajustes gráficos como el número de monitores y el controlador gráfico.

*Características Extendidas* ofrece opciones como la habilitación de la aceleración 3D, que puede mejorar el rendimiento pero puede causar problemas gráficos en algunas configuraciones.

En *Almacenamiento*, gestionamos los discos virtuales y podemos expulsar discos ópticos como las Guest Additions después de su instalación.

Las *Opciones de Red* permiten configurar adaptadores de red, donde por defecto se encuentra uno en modo NAT, aunque ya discutiremos configuraciones más seguras en sesiones posteriores.

El apartado de USB permite utilizar dispositivos USB 3.0 mediante el Extension Pack instalado previamente.

Las *Carpetas Compartidas* facilitan el intercambio de archivos entre el sistema anfitrión y la máquina virtual a través de carpetas designadas, ofreciendo una alternativa más estable que el Arrastrar y Soltar.

Finalmente, en el apartado de *Inicio de la máquina virtual*, podemos elegir entre Inicio Normal, Inicio sin Pantalla o Inicio Desacoplado, este último permitiendo manipular la ventana de la máquina virtual de forma independiente.

Cada una de estas configuraciones y opciones específicas dentro de VirtualBox nos permiten personalizar y optimizar nuestras máquinas virtuales según las necesidades particulares y los usos previstos. A continuación, exploraremos los tipos de redes disponibles en VirtualBox para configurar nuestras máquinas virtuales de manera segura y eficiente.

## Tipos de redes en VirtualBox

A continuación vamos a ver los distintos tipos de red y su impacto en la seguridad y funcionalidad de las máquinas virtuales en VirtualBox.

Vamos a explorar los diferentes tipos de redes que ofrece VirtualBox y cómo mejorar la seguridad a nivel de red de tus máquinas virtuales. No te preocupes si no entiendes todos los detalles técnicos de redes en este momento, ya que iremos profundizando en este tema más adelante.

Lo primero que debes entender es el nivel de exposición de tu red. Al crear varias máquinas virtuales, algunas pueden ser vulnerables a propósito para propósitos educativos en hacking ético. Estas máquinas virtuales pueden estar conectadas a Internet y, por lo tanto, expuestas a ataques cibernéticos. Si una máquina virtual es comprometida, un atacante podría incluso llegar a tu máquina anfitriona (por ejemplo, tu sistema operativo principal como Windows 10 o Windows 11).

La exposición de una máquina virtual depende del tipo de conexión de red que elijas en VirtualBox. Las opciones más comunes son NAT, Red NAT, Adaptador Puente y Red Interna.

1. **NAT y Red NAT:** Estos tipos permiten que tu máquina virtual comparta la conexión de red con tu máquina anfitriona. Esto permite que accedan a Internet y a los dispositivos de la red local, pero la máquina virtual no es visible desde el exterior, ya que usa una dirección IP privada.

2. **Adaptador Puente:** Conecta la máquina virtual directamente a la red física, asignándole una dirección IP pública. Esto hace que la máquina virtual sea visible desde el exterior y esté expuesta a los mismos riesgos que tu máquina anfitriona.

3. **Red Interna:** La máquina virtual solo se comunica con otras máquinas virtuales en la misma red interna, aislándola de la red física y de Internet. Esto proporciona aislamiento de amenazas externas pero limita su funcionalidad.

La elección del tipo de red depende del equilibrio entre funcionalidad y seguridad que necesites. Personalmente, prefiero usar NAT o Red NAT, especialmente Red NAT, ya que permite interconectar múltiples máquinas virtuales y crear laboratorios de hacking ético más complejos en el futuro.

En la configuración básica con tres máquinas virtuales usando adaptadores NAT o Red NAT, cada máquina virtual tiene su propio router virtualizado, lo que impide la interconexión directa entre ellas. Sin embargo, con Red NAT, las máquinas virtuales pueden interactuar entre sí.

Para cambiar la configuración de red de una máquina virtual en VirtualBox, simplemente selecciona la máquina virtual, ve a Configuración, luego a Red y elige el modo de red deseado (NAT, Adaptador Puente, Red Interna, etc.).

Para crear una red NAT en VirtualBox, ve al menú Herramientas > Red y sigue las instrucciones para configurarla según tus necesidades.

En resumen, entender los tipos de redes en VirtualBox es crucial para gestionar la seguridad y funcionalidad de tus máquinas virtuales. A continuación, veremos qué son las snapshots o instantáneas en VirtualBox, otra herramienta esencial para administrar y proteger tus entornos virtualizados.

## **Snapshots / Instantáneas**

Vamos a explorar qué son las snapshots o instantáneas en VirtualBox y por qué pueden ser de gran utilidad. Imagina una snapshot en VirtualBox como una foto instantánea de tu máquina virtual en un momento específico. Si más tarde realizas cambios dentro de la máquina virtual o algo sale mal y afecta al sistema operativo, puedes volver al estado capturado con la snapshot, similar a retroceder en el tiempo en un videojuego cuando guardas y cargas una partida.

Una consideración importante sobre las snapshots o instantáneas es que ocupan espacio en memoria. Para demostrar esto, aquí tengo mi máquina virtual Debian recién instalada y completamente funcional. En este punto, voy a apagar la máquina y crear una snapshot desde VirtualBox. Crear una snapshot en VirtualBox es muy sencillo: simplemente vamos al menú de hamburguesa, seleccionamos "Instantáneas", hacemos clic en "Tomar", asignamos un nombre (por ejemplo, "Antes de que se destruya todo") y aceptamos.

Ahora, vamos a simular la pérdida total del sistema operativo de nuestra máquina Debian. Usaré un comando especial desde la terminal como root para eliminar completamente el sistema de archivos. Correré el comando `rm -rf /` para borrar todo el sistema operativo y carpetas desde la raíz. Esta acción, por supuesto, muestra errores y eventualmente deja la máquina sin sistema operativo funcional.

Después de comprobar la destrucción del sistema, intentaremos reiniciar la máquina desde VirtualBox, pero veremos que se queda bloqueada en el gestor de arranque GRUB, confirmando que el sistema operativo está perdido. Vamos a cerrar la máquina y proceder a restaurar la snapshot que habíamos creado previamente.

Al hacer clic en "Restaurar" para la snapshot "Antes de que se destruya todo", la máquina virtual debería arrancar de nuevo como si nada hubiera pasado, restaurando completamente el sistema operativo y la funcionalidad de Debian. Esta demostración destaca lo útiles que pueden ser las snapshots en VirtualBox, permitiéndonos revertir cambios, configuraciones erróneas o daños en el sistema sin perder tiempo.

Recuerda que para aprender hacking ético, configurarás muchos laboratorios y máquinas virtuales donde esta característica de VirtualBox será inmensamente útil. A continuación, veremos cómo importar y exportar servicios virtualizados.

## Importación y exportación de máquinas virtuales

Las máquinas virtuales son útiles para compartir, hacer copias de seguridad o exportar a otros entornos como VirtualBox o VMware. Especialmente en hacking ético, se usan para prácticas y laboratorios de pen testing. Veamos cómo exportar e importar en VirtualBox:

Antes de exportar, eliminemos cualquier snapshot para liberar espacio en disco. Luego, vamos a Archivo > Exportar servicio virtualizado. Seleccionamos la máquina virtual y elegimos el formato de exportación. Recomendamos la versión 1.0 del formato OVF por su compatibilidad y características mejoradas respecto a la versión 0.9.

Elegimos una ruta para guardar el archivo .ova y confirmamos. Luego, seguimos el asistente para completar la exportación. Una vez generado el archivo, podemos importarlo seleccionando Archivo > Importar servicio virtualizado, ubicando el archivo .ova y configurando las preferencias de importación como la asignación de recursos y la carpeta base.

Finalizada la importación, podemos modificar la configuración según necesitemos. Es importante destacar que estos procesos pueden llevar tiempo.

En resumen, hemos visto cómo manejar la importación y exportación de máquinas virtuales en VirtualBox de manera efectiva. En la próxima clase abordaremos la clonación de máquinas virtuales.

## **Clonación de máquinas virtuales**

La clonación en VirtualBox es útil para replicar configuraciones sin necesidad de reinstalar desde cero. Para clonar una máquina, simplemente seleccionamos la opción de clonación completa, que copia todos los discos duros asociados. Luego de asignar un nombre y configurar las opciones, completamos el proceso.

A continuación, veremos cómo instalar de forma manual Windows 10 en una máquina virtual en VirtualBox.

## **Instalación de Windows 10**

Vamos a configurar una máquina virtual para instalar Windows 10, pero no será una instalación estándar.  Usaremos una versión ligera llamada "MiniOS10", conocida por ser una versión liviana y libre del bloatware de Windows10. Esto significa que tiene menos software preinstalado y ocupa menos espacio en memoria en comparación con la versión original de Windows 10.

MiniOS10 conserva muchas de las funcionalidades de Windows 10 estándar pero mejora la privacidad y consume menos recursos. Esta es la razón por la cual elegimos esta versión alternativa, especialmente útil para configurar laboratorios de hacking, donde necesitamos múltiples máquinas virtuales en hardware limitado.

Sin embargo, no se recomienda MiniOS 10 como sistema operativo host debido a la falta de actualizaciones automáticas de seguridad y a posibles inconsistencias en la estabilidad del sistema operativo.

La descarga de MiniOS 10 puede ser complicada; a menudo, la página oficial está llena de anuncios antes de llegar al enlace de descarga del instalador del sistema operativo.

He descargado la imagen ISO de MiniOS 10 y la tengo en mi carpeta de descargas. Antes de proceder, eliminaré la máquina virtual clonada que ya no necesitamos.

Para crear una nueva máquina virtual:
1. Abre VirtualBox y haz clic en "Nueva".
2. Nombre: MiniOS 10.
3. Configura la ruta de guardado y selecciona la imagen ISO de MiniOS 10.
4. Tipo: Microsoft Windows, Versión: Windows 10 (64-bit).
5. Asigna recursos: 2 GB de RAM y 2 procesadores.
6. Disco duro: tamaño recomendado de 32 GB, pero asignaremos 40 GB y usaremos disco duro dinámico.
7. Revisa la configuración y haz clic en "Finalizar".

Antes de iniciar la máquina virtual, revisaremos la configuración para ajustarla:
- Ajusta la memoria de vídeo a 128 MB.
- Revisa los dispositivos asociados (disco duro y unidad óptica virtual).

Cambia el adaptador de red a modo NAT para asegurar la conectividad. Confirma los cambios y haz clic en "Aceptar".

Inicia la máquina virtual y espera a que aparezca el asistente de instalación de Windows 10. Configura el idioma, formato de hora y moneda, y el teclado según tus preferencias. Continúa sin ingresar una clave de producto.

Acepta los términos de licencia y selecciona una instalación personalizada para ajustar la partición del disco duro. Asigna todo el espacio disponible al sistema operativo.

Completa la instalación y configura las opciones de privacidad según tus preferencias. Finaliza la configuración inicial y reinicia la máquina virtual.

Después del reinicio, inicia sesión con tu nombre de usuario y contraseña. Instala VirtualBox Guest Additions para mejorar el rendimiento del sistema operativo y ajustar la resolución de pantalla automáticamente.

Concluye el proceso y ahora puedes utilizar MiniOS 10 en tu máquina virtual para actividades específicas como laboratorios de hacking ético.

## Instalación de Debian Desatendida

El modo desatendido de VirtualBox permite instalar sistemas operativos en máquinas virtuales sin necesidad de interactuar con el asistente de instalación. Esto permite automatizar por completo la instalación de un sistema operativo invitado en una máquina virtual, lo cual es muy útil si quieres mejorar tu eficiencia en la instalación de sistemas operativos.

Es importante conocer la instalación manual de un sistema operativo para entender mejor el proceso. Por eso, en sesiones anteriores, hemos instalado Windows y Debian de forma manual.

Para instalar un sistema operativo de forma desatendida en una máquina virtual, primero necesitamos crear una máquina virtual. Vamos a la pestaña "Máquina" y creamos una nueva. Asignamos un nombre, por ejemplo, "Debian Automatizado", y seleccionamos la imagen ISO de Debian que utilizamos anteriormente.

VirtualBox automáticamente detecta el tipo de sistema operativo y nos ofrece la opción de realizar una instalación desatendida. Al continuar, nos presentará diferentes opciones y configuraciones, como el nombre de usuario, contraseña, nombre de la máquina, y dominio.

Además, podemos instalar las "Guest Additions", lo que nos ahorra pasos adicionales. Seleccionamos los recursos a asignar (2 GB de RAM, 2 procesadores lógicos, 20 GB de disco duro virtual), y al finalizar, la instalación se realiza en segundo plano sin necesidad de nuestra intervención.

Si queremos ver el estado de la instalación, podemos hacer clic en "Mostrar". Una vez completada la instalación, podemos iniciar sesión y comprobar que el sistema operativo se ha instalado correctamente.

En esta clase hemos aprendido a instalar Debian en modo desatendido utilizando VirtualBox, lo cual es útil para desplegar máquinas rápidamente. Sin embargo, notamos que la instalación desatendida tiene algunas limitaciones, como la configuración del idioma del sistema operativo.

## Organización de Máquinas Virtuales

Para organizar nuestras máquinas virtuales en VirtualBox podemos crear grupos de máquinas. Para asignar un grupo a una máquina ya creada, hacemos clic derecho sobre la máquina, seleccionamos "Mover a grupo" y creamos un nuevo grupo.

Podemos renombrar los grupos y asignar más máquinas a cada uno de ellos mediante arrastrar y soltar. Esto nos permite mantener nuestras máquinas virtuales organizadas por categorías temáticas, lo cual es muy útil cuando trabajamos con muchas máquinas.

## Cómo Crear un Entorno Aislado y Seguro en VirtualBox

Para crear un entorno aislado en VirtualBox y mejorar la seguridad, especialmente en tareas de análisis de malware, configuramos la máquina virtual para que no comparta recursos ni conexiones con el sistema anfitrión. Desactivamos la red, el portapapeles compartido, las carpetas compartidas, y la compatibilidad con dispositivos USB. 

Aunque estas configuraciones mejoran la seguridad, siempre existe el riesgo de ataques de escape de máquina virtual, que explotan vulnerabilidades del hipervisor o del software de virtualización.

Gracias por llegar hasta aquí y completar el tutorial. 

---

https://temp-mail.org 

https://www.youtube.com/watch?v=bIoVtXiG9xc&t=2711s


#Virtualización #Tools
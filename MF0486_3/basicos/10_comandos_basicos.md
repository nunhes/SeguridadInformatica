# Comandos útiles en Linux

Algunas cosas clave para saber sobre los comandos de Linux:

- **Son sensibles a mayúsculas y minúsculas**; por ejemplo, “ls” y “LS” significan cosas diferentes.
- **Siguen una sintaxis específica** como “comando -opciones argumentos“.
- **Se pueden combinar** para realizar operaciones complejas mediante pipelines y redirecciones.
- **Te proporcionan un control detallado** sobre tu sistema, algo difícil de lograr con interfaces gráficas.
- **Te permiten automatizar tareas** mediante scripts de shell y procesamiento por lotes.
- **Se pueden utilizar para acceder a recursos del sistema** como el sistema de archivos, red, memoria y CPU.
- **Forman la base de la interacción** con servidores y sistemas operativos Linux.

| **Comando**           | **Función**                                                  |
| --------------------- | ------------------------------------------------------------ |
| **ls**                | Lista el contenido de un directorio                          |
| **pwd**               | Muestra la ruta del directorio de trabajo actual             |
| **cd**                | Cambia el directorio de trabajo                              |
| **mkdir**             | Crea un nuevo directorio                                     |
| **rm**                | Elimina un archivo                                           |
| **cp**                | Copia archivos y directorios, incluido su contenido          |
| **mv**                | Mueve o renombra archivos y directorios                      |
| **touch**             | Crea un nuevo archivo vacío                                  |
| **file**              | Comprueba el tipo de archivo                                 |
| **zip and unzip**     | Crea y extrae un archivo ZIP                                 |
| **tar**               | Archiva ficheros sin compresión en formato TAR               |
| **nano, vi y jed**    | Edita un archivo con un editor de texto                      |
| **cat**               | Lista, combina y escribe el contenido de un archivo como salida estándar |
| **grep**              | Busca una cadena dentro de un archivo                        |
| **sed**               | Busca, sustituye o elimina patrones en un archivo            |
| **head**              | Muestra las diez primeras líneas de un archivo               |
| **tail**              | Imprime las diez últimas líneas de un archivo                |
| **awk**               | Busca y manipula patrones en un archivo                      |
| **sort**              | Reordena el contenido de un archivo                          |
| **cut**               | Secciona e imprime líneas de un archivo                      |
| **diff**              | Compara el contenido de dos archivos y sus diferencias       |
| **tee**               | Imprime las salidas de los comandos en el Terminal y en un archivo |
| **locate**            | Busca archivos en la base de datos de un sistema             |
| **find**              | Muestra la ubicación de un archivo o carpeta                 |
| **sudo**              | Ejecuta un comando como superusuario                         |
| **su**                | Ejecuta programas en el shell actual como otro usuario       |
| **chmod**             | Modifica los permisos de lectura, escritura y ejecución de un archivo |
| **chown**             | Cambia la propiedad de un archivo, directorio o enlace simbólico |
| **useradd y userdel** | Crea y elimina una cuenta de usuario                         |
| **df**                | Muestra el uso general de espacio en disco del sistema       |
| **du**                | Comprueba el consumo de almacenamiento de un archivo o directorio |
| **top**               | Muestra los procesos en ejecución y el uso de recursos del sistema |
| **htop**              | Funciona como **top** pero con una interfaz de usuario interactiva |
| **ps**                | Crea una instantánea de todos los procesos en ejecución      |
| **uname**             | Imprime información sobre el núcleo, el nombre y el hardware de tu máquina |
| **hostname**          | Muestra el nombre de host de tu sistema                      |
| **time**              | Calcula el tiempo de ejecución de los comandos               |
| **systemctl**         | Gestiona los servicios del sistema                           |
| **watch**             | Ejecuta otro comando de forma continua                       |
| **jobs**              | Muestra los procesos en ejecución de un intérprete de órdenes con sus estados |
| **kills**             | Finaliza un proceso en ejecución                             |
| **shutdown**          | Apaga o reinicia el sistema                                  |
| **ping**              | Comprueba la conectividad de red del sistema                 |
| **wget**              | Descarga archivos de una URL                                 |
| **curl**              | Transmite datos entre servidores utilizando URLs             |
| **scp**               | Copia de forma segura archivos o directorios a otro sistema  |
| **rsync**             | Sincroniza el contenido entre directorios o máquinas         |
| **lfconfig**          | Muestra las interfaces de red del sistema y sus configuraciones |
| **netstat**           | Muestra la información de red del sistema, como enrutamiento y sockets |
| **traceroute**        | Rastrea los saltos de un paquete hasta su destino            |
| **nslookup**          | Consulta la dirección IP de un dominio y viceversa           |
| **dig**               | Muestra información del DNS, incluidos los tipos de registro |
| **history**           | Lista los comandos ejecutados anteriormente                  |
| **man**               | Muestra el manual de un comando                              |
| **echo**              | Imprime un mensaje como salida estándar                      |
| **ln**                | Enlaza archivos o directorios                                |
| **alias y unalias**   | Establece y elimina un alias para un archivo o comando       |
| **cal**               | Muestra un calendario en Terminal                            |
| **apt-get**           | Gestiona las bibliotecas de paquetes de las distribuciones basadas en Debian |

Configuración IP en Debian:

```bash
ip addr show
# or
ip a s
```

ref: 

https://www.debian.org/doc/manuals/debian-reference/debian-reference.es.pdf

https://www.hostinger.es/tutoriales/linux-comandos

https://www.swhosting.com/es/comunidad/manual/comandos-basicos-para-la-administracion-de-sistemas-debian

### Comandos útiles en Windows

#### Básicos

**``cd``**. permite navegar por el árbol de directorios de tu computadora

**``dir``**. Muestra todo el contenido de un directorio (carpeta).

**``tree``**. Muestra el árbol de carpetas de la carpeta que le indiques.

**``md``**. Crea una carpeta o directorio.

**``move``**. Te permite mover un archivo de un directorio a otro.

**``rename``**. Cambiar el nombre o la extensión de un archivo, como si lo hicieras en Windows.

**``del``**. Borra el archivo o carpeta que indiques tras un espacio.

**``date``**. Permite ver o cambiar la fecha del equipo.

**``find``**. Busca una cadena de texto en uno o más archivos.

#### Avanzados

- **Comparar archivos**

```bash
fc /a Archivo1.txt Archivo2.txt 
# ou
fc /b Imagen1.jpg Imagen2.jpg
```

- **Configuración IP de Windows**

  `ipconfig` da información detallada sobre la conexión actual del adaptador de red, incluyendo:

  - Dirección IP actual
  - Máscara de subred
  - IP de la puerta de enlace por defecto
  - Dominio actual

  Estos datos son básicos para solucionar problemas de router y de conexión.

```bash
ipconfig
```

- **Lista de todas las conexiones TCP activas** desde el ordenador.

  La seguridad informática está en constante batalla con el malware y otros programas que, además, aprenden de los fallos que encuentran. Muchos programas maliciosos se conectan a lugares de Internet sin que lo sepas para transferir una información determinada.

  `netstat`, proporciona una lista de todas las conexiones TCP activas desde un ordenador.

  ```bash
  netstat
  ```

- **Enviar paquetes de prueba**

  `ping` puede comprobar si tu ordenador puede acceder a otro ordenador, a un servidor o a un sitio web. Así se pueden detectar las desconexiones de la red. Proporciona el tiempo de tránsito de los paquetes en milisegundos, por lo que también revela conexiones defectuosas.

- **Ver el camino que sigue el tráfico de Internet para llegar desde tu navegador a un sistema remoto** como los servidores de Google. Proporcionando la siguiente información:

  - Número de saltos (servidores intermedios) antes de llegar al destino
  - El tiempo que se tarda en llegar a cada salto
  - La IP y a veces el nombre de cada salto

  ``tracert`` puedes averiguar cómo cambian las rutas según tu lugar o dispositivo de acceso. También ayuda a solucionar problemas de routers o switches en una red local.

  ```bash
  tracert 
  ```

- **Informe completo sobre el rendimiento energético del equipo**

  ```bash
  powercfg /ENERGY
  powercfg /?   # ayuda
  ```

- **Apagar, reiniciar, hibernar**,... Con `shutdown /i`  apagarás la computadora, pero sobre una GUI para elegir si reiniciar o apagar del todo. Si no quieres que aparezca ninguna GUI, usa `shutdown /s`

- **Información del sistema**

  `systeminfo` sirve para saber qué marca de tarjeta de red tienes, los detalles del procesador o la versión exacta de tu sistema operativo Windows.
  
  ```bash
  systeminfo
  ```
  
- **Comprobar la estabilidad de los archivos del sistema**

  **``sfc /SCANNOW``** comprobará la integridad de todos los archivos del sistema protegidos. Y si encuentra un problema, intentará repararlo.

  El comando SFC también permite:

  - **``/VERIFYONLY``**: comprobar la integridad, pero no repara los archivos.
  - **``/SCANFILE``**: escanear la integridad de archivos específicos y reparar si están corruptos.
  - **``/VERIFYFILE``**: verificar la integridad de archivos específicos, pero sin repararlo.
  - **``/OFFBOOTDIR``**: hacer reparaciones en un directorio de arranque sin conexión.
  - **``/OFFWINDIR``**: reparar un directorio de Windows sin conexión.
  - **``/OFFLOGFILE``**: Especificar una ruta para guardar un archivo de registro con los resultados del análisis.

- **Mapear unidades**

  Añadir unidades de red. Si tienes una carpeta compartida en un “ordenador2 “ de tu red, puedes asignarla como tu propia unidad Z: escribiendo el comando:

  ``net use Z: \ORDENADOR2\SHARE /persistent:yes``

- **Comprobación del disco duro**

  ```chkdsk```

Y hay más...

El comando HELP te muestra la lista completa de comandos con su respectiva explicación.

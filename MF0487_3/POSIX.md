# POSIX

**POSIX es una serie de normas, estándares y convenciones** creadas por la comunidad de usuarios de [Unix](https://www.profesionalreview.com/2022/07/11/sistema-operativo-unix/). Se utilizan con el fin de mejorar la compatibilidad entre diferentes sistemas operativos Unix y proporcionar una base para que las aplicaciones sean más portables entre distintos sistemas operativos.

Cada arquitectura tiene sus propias **reglas o estándares**; así que no toda la gente usa lo mismo.
En el caso del POSIX, hay muchos “tipos” diferentes de este estándar, pero ninguno son necesariamente mejores que los demás, simplemente son diferentes.

## ¿Qué es el estándar POSIX?

![UNIX](./assets/unix.jpg)

El **estándar POSIX** es un conjunto de normas para los sistemas operativos tipo Unix. La palabra «estándar» puede ser malinterpretada aquí; no significa «lo mejor», sino sólo un conjunto de normas y convenciones. Básicamente, POSIX describe el comportamiento de un sistema informático, las convenciones que deben seguir los sistemas operativos y las interfaces que debe utilizar el software.

La idea es **asegurar la portabilidad del software** entre diferentes sistemas operativos describiendo un estándar común para el comportamiento del software y las interfaces del sistema operativo. El propósito de POSIX es asegurar la compatibilidad y portabilidad del software entre diferentes sistemas operativos Unix. Un programa escrito de manera consistente con las convenciones descritas en el estándar debería funcionar como se espera en cualquier sistema Unix que soporte el estándar.

El estándar **describe la interfaz que los programas** deben utilizar para acceder a los servicios del sistema. También describe el comportamiento que deben mostrar estos servicios. POSIX cubre todos los aspectos de los sistemas operativos, incluyendo las convenciones del lenguaje de programación, el manejo de errores, los formatos de archivo y la administración del sistema. Especifica un conjunto de normas a las que deben ajustarse los sistemas operativos tipo Unix.

## Sistemas operativos POSIX

**Sistemas operativos** que se adhieren al estándar POSIX:

- **GNU/Linux**: Es parcialmente compatible con POSIX. El sistema operativo tipo Unix más utilizado en el mundo, basado en el kernel El kernel de [Linux](https://www.profesionalreview.com/2022/08/13/portatiles-linux/) fue creado por Linus Torvalds. Después de empezar a crear el núcleo, Linus decidió publicarlo bajo la Licencia Pública General de GNU, que es una licencia de software libre y de código abierto para software y otras obras creativas.
- **HP-UX**: Sistema operativo de servidor Unix utilizado por Hewlett-Packard que incorpora características tanto de BSD como de System V y que fue lanzado por primera vez en 1989.
- **FreeBSD**: Sistema operativo tipo Unix basado en el kernel de BSD creado por el Grupo de Investigación de Sistemas Informáticos de la Universidad de California, Berkeley, y publicado por primera vez en 1993.
- **Mac OS X o macOS**: sistema operativo comercial de tipo Unix creado por Apple Inc. que se basa en tecnología de código abierto, incluido el núcleo Darwin, publicado por primera vez en 2001.
- **Solaris**: Sistema operativo tipo Unix creado por Sun Microsystems que se basa en OpenSolaris y que salió a la venta por primera vez en 2002.
- **NetBSD**: Sistema operativo informático similar a Unix que es software de código abierto, creado por la Fundación NetBSD y publicado por primera vez en 1993.
- **OpenBSD**: Sistema operativo informático tipo Unix de código abierto, creado por la Fundación OpenBSD y publicado por primera vez en 1995.
- **GNU Hurd**: El núcleo del sistema operativo GNU. Fue creado por la Free Software Foundation y está disponible como software de código abierto.
- **AIX**: sistema operativo de tipo Unix creado por IBM, basado en la última versión de la arquitectura System V y lanzado por primera vez en 1987.
- **OpenSolaris**: Sistema operativo de tipo Unix creado por Sun Microsystems que se basa en el núcleo OpenSolaris y que se lanzó por primera vez en 2005.
- **IllumOS**: sistema operativo similar a Unix creado por el proyecto IllumOS y publicado por primera vez en 2016.

## Especificaciones POSIX

![especificaciones POSIX](./assets/programacion.jpg)

Hay varios subestándares que forman parte del estándar POSIX. También hay muchos «sabores» diferentes de él, por lo que no todos son iguales.

- IEEE 1003.1 – Esta es la especificación base del estándar POSIX original de 1988. Es la especificación POSIX más básica.
- IEEE 1003.1-2001 – Esta es la segunda edición de la especificación IEEE 1003.1, publicada en 2001. Esta especificación se conoce a veces como «POSIX 2001» o «C99».
- IEEE 1003.1-2008 – Esta es la tercera edición de la especificación IEEE 1003.1, publicada en 2008. Esta especificación se conoce a veces como «POSIX 2008» o «C2008».
- IEEE 1003.1-2017 – Esta es la cuarta edición de la especificación IEEE 1003.1, publicada en 2017. Esta especificación se conoce a veces como «POSIX 2017» o «C17».
- IEEE 1003.2 – Esta es la especificación IEEE que pretendía definir una Interfaz de Sistema Operativo Portátil (POSIX) para sistemas basados en la Arquitectura SPARC. Es un superconjunto de la especificación IEEE 1003.1-2001. Por ello, a veces se la denomina «SPARC-2003».

## ¿Cuáles son las ventajas de usar POSIX?

Hay **muchas ventajas** en el uso de POSIX, incluyendo las siguientes:

- **Compatibilidad** – Los programas escritos para sistemas POSIX normalmente se ejecutarán en otros sistemas POSIX sin modificaciones, por lo que pueden ser utilizados en diferentes sistemas sin ningún problema.
- **Estandarización** – Existen estándares para muchos aspectos de los sistemas POSIX, permitiendo la consistencia y reduciendo las diferencias entre los diferentes sistemas.
- **Portabilidad** – Los sistemas POSIX pueden ser portados más fácilmente a diferentes plataformas que los sistemas no POSIX, permitiendo el desarrollo entre plataformas.

## ¿Cuáles son las desventajas?

La única desventaja de usar POSIX es que es **complicado y difícil de implementar** y entender. Como puede ver, las ventajas de POSIX superan con creces las desventajas. Ahora que sabe qué es POSIX y cómo funciona, puede decidir si es adecuado para ti.

## ¿Cuáles son las características principales de POSIX?

![Unix Posix](./assets/unix-posix.jpg)

Entre las **principales características de POSIX** se puede destacar:

- **Consistencia** – Existen estándares para muchos aspectos de los sistemas POSIX, permitiendo la consistencia y reduciendo las diferencias entre los diferentes sistemas.
- **Portabilidad** – Los sistemas POSIX pueden ser portados más fácilmente a diferentes plataformas que los sistemas no POSIX, permitiendo el desarrollo entre plataformas. –
- **Compatibilidad** – Los programas escritos para estos sistemas normalmente se ejecutarán en otros sistemas sin modificaciones, por lo que pueden ser utilizados en diferentes sistemas sin ningún problema.
- **Estandarización** – Existen estándares para muchos aspectos de los sistemas POSIX, permitiendo la consistencia y reduciendo las diferencias entre los diferentes sistemas.

## ¿Cuál es la historia?

La primera edición **se publicó en 1988**. La segunda edición se publicó en 2001 y la tercera en 2008. La cuarta edición se publicó en 2017.

La idea de tener un estándar para los sistemas Unix se propuso por primera vez a finales de la década de 1970. En aquella época, **Unix era un sistema operativo relativamente nuevo** y desconocido, pero mucha gente sabía que era extremadamente eficiente y potente. Para hacerlo más útil en las empresas, se propuso establecer un estándar para los sistemas Unix con el fin de aumentar su portabilidad. En aquella época, había muchos tipos diferentes de sistemas Unix, por lo que tener un estándar ayudaría a los usuarios y programadores de esos sistemas a ser más compatibles. Cuando el [IEEE](https://www.profesionalreview.com/?s=ieee) publicó su primera edición del estándar en 1988, Unix llevaba muchos años en el mercado y estaba bastante establecido. Esto facilitó la estandarización de los sistemas Unix y la compatibilidad entre ellos.

El estándar y las certificaciones POSIX son importantes para el software, especialmente si se usan en ciertas administraciones.

#estándares
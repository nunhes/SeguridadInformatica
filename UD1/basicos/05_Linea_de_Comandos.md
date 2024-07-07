# Línea de comandos en Windows

Aunque los sistemas operativos Windows están orientados a su manejo a través de una interfaz gráfica, podemos trabajar con ellos utilizando comandos.

De hecho, los sistemas Windows aparecieron para facilitar el uso de los sistemas operativos a usuarios que querían utilizar los sistemas informáticos para desarrollar un trabajo que no tenía que ver con la informática, que eran la mayoría de los potenciales usuarios de los sistemas.

Hoy en día las interfaces gráficas de usuario son amigables, bastante flexibles, permiten realizar operaciones con el sistema de forma sencilla y pudiendo mostrar información de interés bien organizada. Lo mismo ocurre con las herramientas de administración del sistema disponibles en el sistema operativo.

## ¿Por qué necesitamos comandos?

Sin embargo, para los usuarios avanzados que tienen conocimientos del sistema o los profesionales del sector, el uso de comandos agiliza el uso del sistema y, sobre todo, su administración.

En realidad, es en la administración de un sistema donde realmente tiene más sentido el uso de comandos para realizar tareas complejas de forma rápida o automatizar la ejecución de operaciones largas y/o complejas.

#### Ventajas del uso de comandos

Las ventajas del uso de comandos se podrían resumir básicamente en las siguientes:

- Algunas operaciones se realizan de forma más rápida que a través de la interfaz gráfica.
- Se pueden ejecutar operaciones complejas que desde interfaz gráfica no se podrían realizar o sería complicado llevar a cabo. Por ejemplo, gracias a la ejecución de comandos con patrones, variables de entorno y redirecciones.
- Se pueden programar una serie de operaciones que se ejecutarán en secuencia como si fuera una sola tarea que no requiera interacción del usuario. Gracias al uso de scripts del sistema (procesos por lotes).
- Se pueden reutilizar tareas entre distintos sistemas o tareas que se adapten a distintos contextos. Gracias al uso de scripts que reciban parámetros.
- Los comandos, salvo excepciones muy concretas, no cambian entre versiones del mismo sistema operativo. Si aprendemos a utilizar una serie de comandos los podremos aprovechar en sucesivas versiones del sistema operativo. Lo mismo ocurre con los scripts, salvo ligeros cambios que se puedan añadir en el nuevo sistema.

No obstante, para sacar partido de los comandos es necesario conocer como funciona el interprete de comandos y conocer los comandos disponibles.

## Diferencia entre línea de comandos nativa y Bash

La línea de comandos y Bash son términos relacionados con la interacción con sistemas operativos basados en Unix (como Linux y macOS), pero no son exactamente lo mismo. Aquí te explico la diferencia:

### Línea de Comandos
La línea de comandos (o "command line" en inglés) es una interfaz de texto que permite a los usuarios interactuar con el sistema operativo. Se puede considerar como una interfaz donde se ingresan comandos de texto para realizar tareas en el sistema, como navegar por el sistema de archivos, ejecutar programas, manipular archivos, etc.

### Bash
Bash (Bourne Again SHell) es uno de los muchos intérpretes de comandos disponibles para sistemas Unix. Es una mejora del shell original de Unix, el Bourne shell (`sh`). Bash ofrece características adicionales como:

1. **Funciones y alias**: Puedes definir funciones y alias personalizados.
2. **Variables y scripting**: Bash permite el uso de variables y scripting para automatizar tareas.
3. **Historial de comandos**: Bash guarda un historial de los comandos ingresados, permitiendo reejecutarlos fácilmente.
4. **Autocompletado**: Mediante la tecla Tab, Bash puede autocompletar comandos y nombres de archivos.
5. **Redirección y tuberías**: Permite redirigir la salida de un comando a otro, a un archivo, etc.

### Relación entre ambos
- **La línea de comandos** es la interfaz donde escribes y ejecutas comandos.
- **Bash** es uno de los muchos programas (intérpretes de comandos) que puedes usar dentro de la línea de comandos para interpretar y ejecutar esos comandos.

Otros ejemplos de intérpretes de comandos incluyen [`sh` (Bourne shell)](https://www.geeksforgeeks.org/difference-between-sh-and-bash/), [`csh` (C shell)](https://es.wikipedia.org/wiki/C_shell), [`ksh` (Korn shell)](https://es.wikipedia.org/wiki/Korn_shell), [`zsh` (Z shell)](https://terminaldelinux.com/terminal/preparacion-entorno/instalacion-zsh/), entre otros.

### Ejemplo para aclarar
Imagina que la **línea de comandos** es como una hoja en blanco donde escribes instrucciones. **Bash** sería como un diccionario que entiende y ejecuta esas instrucciones de una manera específica. Puedes cambiar ese diccionario (intérprete de comandos) por otro, como `zsh`, pero la hoja en blanco (línea de comandos) sigue siendo la misma.

En resumen, la línea de comandos es la interfaz en la que ingresas tus comandos, y Bash es uno de los programas que puede interpretar y ejecutar esos comandos.

**Lecturas complementarias**

- [La terminal es una interfaz de línea de comandos mediante la cuál nos comunicamos con un sistema a través de órdenes rápidas, eficientes y productivas.](https://terminaldelinux.com/terminal/)

#Línea_de_Comandos #Tools 
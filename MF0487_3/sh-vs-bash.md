# Diferencia entre sh y bash

bash y sh son dos shells diferentes del sistema operativo Unix. bash es sh, pero con más funciones y mejor sintaxis. Bash es “Bourne Again SHell” y es una mejora del original sh (shell Bourne). 

Las secuencias de comandos de Shell son secuencias de comandos en cualquier shell, mientras que las secuencias de comandos de Bash son secuencias de comandos específicas para Bash. 

sh es un intérprete de línea de comandos de shell de sistemas operativos Unix/tipo Unix. sh proporciona algunos comandos integrados. bash es un superconjunto de sh. Shell es una interfaz de línea de comandos para ejecutar comandos y scripts de shell. Los shells vienen en una variedad de sabores, al igual que los sistemas operativos vienen en una variedad de sabores. Entonces, Shell es una interfaz entre el usuario y el sistema operativo, que ayuda al usuario a interactuar con el dispositivo.

## sh:

```
#!/bin/sh
```

## bash:

```
#!/bin/bash
```

### Nota:

- Shell es una interfaz entre el usuario y el sistema operativo.
- sh implementa la interfaz shell.
- bash es un superconjunto de sh.

## sh:

sh, también llamado Bourne Shell, es un **lenguaje de programación de comandos** descrito por el estándar [POSIX](POSIX.md). Es para sistemas operativos UNIX o derivados. Tiene muchas implementaciones. En la mayoría de los sistemas operativos, sh se implementa mediante programas como dash, kash y el Bourne Shell original. sh es un predecesor de bash. /bin/sh es un enlace real a las implementaciones principales. Es un enlace simbólico en la mayoría de los sistemas POSIX.

sh no es un lenguaje de programación en sí. Es sólo una especificación. sh es una descripción detallada de la sintaxis y semántica del lenguaje. No incluye una implementación. sh está escrito como reemplazo de shells UNIX anteriores. La mayor parte de la sintaxis es la misma que la del lenguaje de programación ALGOL68.

Deberíamos usar sh si queremos que nuestro lenguaje sea compatible con múltiples sistemas. Lo más probable es que el script sh se ejecute en bash también sin modificaciones, ya que bash es compatible con versiones anteriores de sh. sh es el lenguaje de scripting más portátil que funciona en la mayoría de los sistemas POSIX/Unix/Linux. Una ventaja de sh es que se garantiza que existirá en todo lo que pertenezca al sistema Unix. 

## bash:

bash también es un lenguaje de programación de comandos como sh. Hoy en día, bash es un shell de inicio de sesión predeterminado en la mayoría de los sistemas operativos basados en Linux. Es una versión extendida del sistema sh para el reemplazo GNU del shell Bourne. También podemos decir que bash es un lenguaje de programación. Aquí piense como Python, podemos iniciar Python en modo interactivo y se comporta como un Shell, pero también podemos ejecutar un programa de Python en cualquier IDE.

bash es un superconjunto de sh. Esto significa que bash admite características de sh y proporciona más funcionalidad que sh. Aunque la mayoría de los comandos hacen lo mismo que sh. bash no es un shell compatible con POSIX. Es un dialecto del lenguaje shell POSIX. Bash puede ejecutarse en una ventana de texto y permite al usuario interpretar comandos para realizar diversas tareas. Tiene las mejores y más útiles características de los shells Korn y C, como manipulación de directorios, control de trabajos, alias y muchas otras.

Al igual que el software GNU, bash proporciona otros shells, incluida una versión de csh, Bash es el shell predeterminado. bash pretende ser una implementación conforme a la parte de herramientas y shell IEEE POSIX de la especificación IEEE POSIX (estándar IEEE 1003.1). Al igual que otros GNU, bash también es bastante portátil. Esto funciona en cualquier sistema basado en Linux/Unix que tenga bash en la ubicación esperada. bash es más funcional que sh en términos de programación y uso interactivo.

### Diferencia entre sh y bash:

|                           **bash**                           |                            **sh**                            |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                      Bourne Again Shell                      |                          Caparazón                           |
|                  Desarrollado por Brain Fox                  |              Desarrollado por Stephen R. Bourne              |
|                        Sucesor de sh                         |                      Predecesor de bash                      |
|               bash es el SHELL predeterminado                |               sh es el SHELL no predeterminado               |
|                         #!/bin/bash                          |                          #!/bin/sh                           |
|        Tiene más funcionalidad con la actualización.         |                  Tiene menos funcionalidad.                  |
|               apoya los controles de trabajo.                |              no soporta el control del trabajo.              |
|              bash no es un shell POSIX válido.               |                 sh es un shell POSIX válido.                 |
|                        Fácil de usar                         |                  no es tan fácil como bash                   |
|                    menos portátil que sh.                    |                    Más portátil que bash.                    |
|                Versión extendida del idioma.                 |                       Idioma original                        |
| Las secuencias de comandos Bash son secuencias de comandos específicas para Bash | Las secuencias de comandos de Shell son secuencias de comandos en cualquier shell |
|               admite el historial de comandos.               |             no admite el historial de comandos.              |

Saber más:

- [Difference Between sh and Bash in Linux? (linkedin.com)](https://www.linkedin.com/pulse/difference-between-sh-bash-linux-alok-mishra-soogc/)
- [Mastering Bash Scripting for Embedded Linux Development](https://embedthreads.com/mastering-bash-scripting-for-embedded-linux-development/?trk=article-ssr-frontend-pulse_little-text-block)
- [Introduction to Bash Scripting: Part 1](https://embedthreads.com/introduction-to-bash-scripting-part-1/?trk=article-ssr-frontend-pulse_little-text-block)
- [Setting Up a VirtualBox Environment with Ubuntu](https://embedthreads.com/setting-up-a-virtualbox-environment-with-ubuntu/?trk=article-ssr-frontend-pulse_little-text-block)
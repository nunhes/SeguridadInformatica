# Debian Linux: listar paquetes instalados

Para listar los paquetes instalados en un sistema Debian utilizando herramientas como `dpkg` y `apt`, puedes seguir los pasos a continuación. Estas herramientas son fundamentales para la gestión de paquetes en sistemas basados en Debian, incluyendo Ubuntu y otras distribuciones derivadas.

### Usando `dpkg`

`dpkg` es la herramienta de bajo nivel para gestionar los paquetes Debian. Puedes usarla para listar todos los paquetes instalados en el sistema.

#### Comando Básico

Para listar todos los paquetes instalados, puedes usar el siguiente comando:

```bash
dpkg --list
```

Este comando mostrará una lista de todos los paquetes instalados en tu sistema. La salida incluye el nombre del paquete, su versión y una breve descripción.

#### Filtrar Resultados

Para filtrar la lista y buscar un paquete específico, puedes usar `grep`. Por ejemplo, para buscar paquetes relacionados con `apache2`:

```bash
dpkg --list | grep apache2
```

### Usando `apt`

`apt` es una herramienta de nivel superior que facilita la gestión de paquetes. Proporciona una interfaz más amigable para los comandos de `dpkg`.

#### Comando Básico

Para listar todos los paquetes instalados, puedes usar el siguiente comando:

```bash
apt list --installed
```

Este comando mostrará una lista de todos los paquetes instalados en tu sistema con su versión y el estado de instalación.

#### Filtrar Resultados

Para filtrar la lista y buscar un paquete específico, puedes usar el siguiente comando:

```bash
apt list --installed | grep apache2
```

### Ejemplos Prácticos

#### Listar Todos los Paquetes Instalados con `dpkg`

```bash
dpkg --list
```

Salida típica:

```
Desired=Unknown/Install/Remove/Purge/Hold
| Status=Not/Inst/Conf-files/Unpacked/halF-conf/Half-inst/trig-aWait/Trig-pend
|/ Err?=(none)/Reinst-required (Status,Err: uppercase=bad)
||/ Name           Version           Architecture Description
+++-==============-=================-============-=================================
ii  adduser        3.118             all          add and remove users and groups
ii  apache2        2.4.41-4ubuntu3.6 amd64        Apache HTTP Server
```

#### Listar Todos los Paquetes Instalados con `apt`

```bash
apt list --installed
```

Salida típica:

```
Listing... Done
adduser/bullseye,now 3.118 all [installed]
apache2/bullseye,now 2.4.41-4ubuntu3.6 amd64 [installed]
```

#### Buscar un Paquete Específico con `dpkg`

```bash
dpkg --list | grep apache2
```

Salida típica:

```
ii  apache2        2.4.41-4ubuntu3.6 amd64        Apache HTTP Server
```

#### Buscar un Paquete Específico con `apt`

```bash
apt list --installed | grep apache2
```

Salida típica:

```
apache2/bullseye,now 2.4.41-4ubuntu3.6 amd64 [installed]
```

### Conclusión

Usar `dpkg` y `apt` para listar paquetes instalados es una tarea sencilla y esencial para la gestión de sistemas Debian. `dpkg` proporciona una visión detallada de los paquetes, mientras que `apt` ofrece una interfaz más amigable y fácil de usar. Ambas herramientas son complementarias y muy útiles para la administración de paquetes en sistemas Debian.
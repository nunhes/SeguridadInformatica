# NMAP

Nmap (Network Mapper) es una herramienta de código abierto, poderosa y versátil, utilizada principalmente para el descubrimiento de redes y auditorías de seguridad. Es ampliamente utilizada en laboratorios de hacking ético debido a su capacidad para identificar dispositivos y servicios en una red, detectar puertos abiertos, servicios activos, sistemas operativos, y mucho más.

Un escaneo de red con Nmap sirve para obtener información, con cierto nivel de detalle, acerca de todos dispositivos conectados en el sistema**. Un escaneo de red con Nmap** **incluye tanto routers como ordenadores y datos sobre la tecnología de cada uno**. Por lo tanto, Nmap sirve para encontrar vulnerabilidades informáticas en los sistemas y determinar qué vector de ataque podría aprovechar un hacker malicioso.

En hacking ético, el escaneo de red con Nmap se utiliza frecuentemente para hacer auditorías de seguridad. Usualmente, se aplica esta herramienta de escaneo de redes en la segunda fase de un *pentesting*, que es la de escaneo de vulnerabilidades. Antes de eso, se recolecta toda la información posible sobre el sistema de manera menos invasiva. **Es necesario tener en cuenta que Nmap produce ruido, ya que le hace peticiones a los puertos del sistema**. Por eso, es posible detectar escaneos con esta herramienta o, incluso, escoger no darle información nunca.

Ahora bien, son muy pocos los sistemas que se encuentran configurados de forma tan hermética, que resistan ser escaneados por Nmap. Por eso, esta herramienta sigue siendo una parte fundamental de los protocolos de *pentesting*, **a pesar de que haya sido creada más de dos décadas atrás, en 1998**, para el escaneo de red con Nmap.

## Usos de Nmap en Hacking Ético

1. **Descubrimiento de Red**: Identificar todos los dispositivos conectados a una red.
2. **Escaneo de Puertos**: Determinar qué puertos están abiertos en un dispositivo específico.
3. **Detección de Servicios**: Identificar qué servicios están corriendo en esos puertos.
4. **Fingerprinting de Sistemas Operativos**: Averiguar qué sistema operativo está usando un dispositivo.
5. **Detección de Vulnerabilidades**: Identificar servicios y configuraciones potencialmente vulnerables.
6. **Script Scanning**: Utilizar NSE (Nmap Scripting Engine) para realizar pruebas de seguridad más avanzadas y específicas.

## Modificadores

Los modificadores (o flags) de Nmap te permiten personalizar tus escaneos de acuerdo a tus necesidades específicas. A continuación, te explico algunos de los modificadores más comunes de Nmap y cómo utilizarlos con ejemplos prácticos.

### Escaneo básico

Para hacer un escaneo simple de una IP o un rango de IPs, puedes usar:
```sh
nmap 192.168.1.1

#Single IP
nmap 127.0.0.1
#Dominio
nmap example.com
#Rango de IPs
nmap 192.168.10.0/24
```
Esto realiza un escaneo básico de puertos en la IP 192.168.1.1.

### Escaneo de Puertos

Para escanear puertos específicos, usa la opción `-p`:
```sh
nmap -p 80,443 192.168.1.1
# o también
nmap -p 1-65535 192.168.1.1
```
El primer ejemplo escanea solo los puertos 80 y 443. El segundo ejemplo escanea todos los puertos del 1 al 65535.

También puedes escanear todos los puertos posibles:
```sh
nmap -p- 192.168.1.1
```

O sólo los más comunes con el modificador `-F`:
```bash
nmap -F 192.168.1.1
```
Esto realiza un escaneo rápido de los 100 puertos más comunes.

### Detección de Sistemas Operativos

Para intentar determinar el sistema operativo de un dispositivo:
```sh
nmap -O 192.168.1.1
```
Esto intenta detectar el sistema operativo del dispositivo objetivo.

### Escaneo de Servicios y Versión

Para detectar servicios y versiones de los mismos:
```sh
nmap -sV 192.168.1.1
```
Esto escanea los puertos y determina qué servicios están corriendo y sus versiones.

### Escaneo UDP

El escaneo UDP se dirige a los puertos UDP del host de destino. Dado que se trata de un protocolo sin conexión, para determinar el estado de un puerto UDP es necesario interpretar la respuesta o la ausencia de ella. Con este escaneo, Nmap detecta la limitación de velocidad y reduce la velocidad para evitar desbordamientos. Utilizamos la opción -F para escanear sólo los 100 puertos principales en lugar de los 65.535.

```sh
nmap -sU 10.0.0.1 -F
```

### Exploración de conexión TCP

El escaneo de conexión TCP es la técnica de escaneo más directa. Nmap establece un protocolo de enlace TCP completo de tres vías con cada puerto de destino para determinar su estado (abierto, cerrado o filtrado). He aquí un ejemplo utilizando una IP encontrada en un escaneo de ping:
```sh
nmap -sT 10.0.0.1
```
Este escaneo da una lista de los puertos en este host

### Escaneo agresivo

Para un escaneo completo usando algunos scripts de NSE:
```sh
nmap -A 192.168.1.1
```
Esto realiza un escaneo agresivo, que incluye detección de sistema operativo, escaneo de servicios y versión, y scripts de detección de vulnerabilidades.

### Escaneo de red completa o escaneo de ping para identificar hosts activos

```bash
nmap -sn 192.168.1.0/24
```
Esto realiza un "ping scan" para descubrir dispositivos activos en la red 192.168.1.0/24 sin realizar un escaneo de puertos. Este tipo de escaneo constituye la base del descubrimiento de hosts, permitiéndote encontrar hosts activos con una red rápidamente.

### Escaneo sigiloso

```bash
nmap -sS 192.168.1.1
```
Esto realiza un escaneo SYN, que es menos probable de ser detectado por firewalls y sistemas de detección de intrusos. También denominado escaneo semiabierto o sigiloso, envía paquetes SYN a los puertos objetivo sin completar el protocolo de enlace y evalúa las respuestas para determinar la apertura del puerto sin conectarse completamente. Esta técnica es más rápida que el escaneo de conexión TCP y es menos probable que se detecte.

### Guardar resultados en un archivo

```bash
nmap -oN scan_result.txt 192.168.1.1
nmap -oX scan_result.xml 192.168.1.1
nmap -oG scan_result.gnmap 192.168.1.1
```
Esto guarda los resultados del escaneo en un archivo en los formatos especificados.

### Escaneo empleando script NSE

```bash
nmap --script vuln 192.168.1.1
```
Esto ejecuta un script de Nmap para buscar vulnerabilidades conocidas en la IP 192.168.1.1.

> Nmap tiene muchos más flags y opciones que puedes explorar según tus necesidades específicas en hacking ético.

Otro ejemplo del empleo de scripts lo vemos con *vulners*, que utiliza la [base de datos de vulnerabilidades Vulners](https://vulners.com/). Este script depende de tener información sobre las versiones de software, por lo que debes utilizar el indicador **-sV** con él. Aquí hay un ejemplo de escaneo usando este script para escanear un rango de IP:

```sh
nmap -sV --script=vulners 10.0.0.0/24
```

El indicador **-sV** indica a Nmap que realice la detección de versiones de los servicios en los puertos especificados.

### Otros ejemplos básicos

Supongamos que estás realizando un reconocimiento en una red corporativa con la dirección IP 192.168.0.0/24 y deseas obtener información sobre los dispositivos y servicios activos.

1. **Descubrimiento de Host**
   ```sh
   nmap -sn 192.168.0.0/24
   ```
   Esto realiza un escaneo de ping para listar todos los dispositivos activos en la red.

2. **Escaneo de Puertos Comunes**
   ```sh
   nmap -F 192.168.0.0/24
   ```
   Este comando escanea rápidamente los puertos más comunes en todos los dispositivos de la red.

3. **Detección de Servicios y Sistemas Operativos**
   ```sh
   nmap -O -sV 192.168.0.1
   ```
   Este escaneo específico en un dispositivo trata de identificar el sistema operativo y los servicios corriendo en sus puertos abiertos.

4. **Escaneo de Vulnerabilidades**
   ```sh
   nmap --script vuln 192.168.0.1
   ```
   Utiliza [scripts NSE](https://www.netally.com/cybersecurity/building-custom-nse-and-discovery-scripts/) para detectar posibles vulnerabilidades en el dispositivo objetivo.

### Consideraciones Éticas

Es crucial recordar que cualquier actividad de escaneo de red debe estar autorizada explícitamente por el propietario de la red. El uso no autorizado de Nmap en redes ajenas puede ser ilegal y considerado como una actividad malintencionada.

### Recursos Adicionales

- [Documentación oficial de Nmap](https://nmap.org/book/man.html)
- [Guía de Nmap para Hacking Ético](https://www.hackingtutorials.org/nmap/nmap-tutorial/)
- [Qué es Nmap y como usarlo](https://www.freecodecamp.org/espanol/news/que-es-nmap-y-como-usarlo-un-tutorial-para-la-mejor-herramienta-de-escaneo-de-todos-los-tiempos/)
- [Nmap Scripting Engine](https://nmap.org/book/nse.html)
- [Nmap alternatives](https://linuxsecurity.expert/tools/nmap/alternatives/) + [1](https://www.networkworld.com/article/966320/alternatives-to-nmap-from-simple-to-advanced-network-scanning.html)
- [Metasploitable2](https://elhackeretico.com/resolucion-de-metasploitable-2/)
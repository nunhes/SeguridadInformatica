# NMAP

Nmap (Network Mapper) es una herramienta de código abierto utilizada principalmente para el descubrimiento de redes y auditorías de seguridad. Es ampliamente utilizada en laboratorios de hacking ético debido a su capacidad para identificar dispositivos y servicios en una red, detectar puertos abiertos, servicios activos, sistemas operativos, y mucho más.

### Usos de Nmap en Hacking Ético

1. **Descubrimiento de Red**: Identificar todos los dispositivos conectados a una red.
2. **Escaneo de Puertos**: Determinar qué puertos están abiertos en un dispositivo específico.
3. **Detección de Servicios**: Identificar qué servicios están corriendo en esos puertos.
4. **Fingerprinting de Sistemas Operativos**: Averiguar qué sistema operativo está usando un dispositivo.
5. **Detección de Vulnerabilidades**: Identificar servicios y configuraciones potencialmente vulnerables.
6. **Script Scanning**: Utilizar NSE (Nmap Scripting Engine) para realizar pruebas de seguridad más avanzadas y específicas.

### Ejemplos de Uso

#### Escaneo Básico

Para hacer un escaneo simple de una IP o un rango de IPs, puedes usar:
```sh
nmap 192.168.1.1
```

#### Escaneo de Puertos

Para escanear puertos específicos, usa la opción `-p`:
```sh
nmap -p 80,443 192.168.1.1
```
O para escanear todos los puertos posibles:
```sh
nmap -p- 192.168.1.1
```

#### Detección de Sistemas Operativos

Para intentar determinar el sistema operativo de un dispositivo:
```sh
nmap -O 192.168.1.1
```

#### Escaneo de Servicios y Versión

Para detectar servicios y versiones de los mismos:
```sh
nmap -sV 192.168.1.1
```

#### Escaneo Completo con Scripts NSE

Para un escaneo completo usando algunos scripts de NSE:
```sh
nmap -A 192.168.1.1
```

### Ejemplo Práctico

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
   Utiliza scripts NSE para detectar posibles vulnerabilidades en el dispositivo objetivo.

### Consideraciones Éticas

Es crucial recordar que cualquier actividad de escaneo de red debe estar autorizada explícitamente por el propietario de la red. El uso no autorizado de Nmap en redes ajenas puede ser ilegal y considerado como una actividad malintencionada.

### Recursos Adicionales

- [Documentación oficial de Nmap](https://nmap.org/book/man.html)
- [Guía de Nmap para Hacking Ético](https://www.hackingtutorials.org/nmap/nmap-tutorial/)
- [Nmap Scripting Engine](https://nmap.org/book/nse.html)
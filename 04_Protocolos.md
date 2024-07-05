

# ¿Qué son y para qué sirven los protocolos de comunicación de redes?

**Los utilizamos prácticamente todos los días, aunque la mayoría de los usuarios no lo sepan, ni conozcan su funcionamiento.**

La[ **interconexión de sistemas** o redes](https://www.kio.tech/blog/data-center/que-es-la-interconexion-empresarial) de computadoras son la base de las comunicaciones hoy en día y están diseñadas bajo múltiples **protocolos de comunicación**. Por ejemplo, existen muchos protocolos al establecer una conexión a internet y según el tipo que se necesite establecer, dichos protocolos van a variar. Además, la **comunicación** a internet no es el único tipo de **comunicación** cuando hablamos de **transmisión de datos** e intercambio de mensajes en redes. En todos los casos, los protocolos de red definen las características de la conexión.

Un protocolo es un conjunto de reglas: los **protocolos de red** son estándares y políticas formales, conformados por restricciones, procedimientos y formatos que definen el intercambio de **paquetes** de información para lograr la comunicación entre dos **servidores** o más [dispositivos a través de una red](https://www.kio.tech/blog/data-center/dispositivos-de-interconexion-de-redes).

Los **protocolos de red** incluyen mecanismos para que los dispositivos se identifiquen y establezcan conexiones entre sí, así como reglas de formato que especifican cómo se forman los **paquetes** y los datos en los mensajes enviados y recibidos. Algunos protocolos admiten el reconocimiento de mensajes y la compresión de datos diseñados para una comunicación de [red confiable de alto rendimiento](https://www.kio.tech/blog/data-center/cómo-medir-la-latencia).

### **Tipos de protocolos de red**

Los protocolos para la **transmisión de datos** en internet más importantes son TCP (Protocolo de Control de Transmisión) e IP (**Protocolo de Internet)**. De manera conjunta (TCP/IP) podemos enlazar los dispositivos que acceden a la red, algunos otros **protocolos de comunicación** asociados a internet son POP, SMTP y HTTP.

Estos los utilizamos prácticamente todos los días, aunque la mayoría de los usuarios no lo sepan ni conozcan su funcionamiento. Estos protocolos permiten la **transmisión de datos** desde nuestros dispositivos para navegar a través de los sitios, enviar correos electrónicos, escuchar música online, etc.

Existen varios tipos de protocolos de red:

- Protocolos de comunicación de red: protocolos de comunicación de **paquetes** básicos como TCP / IP y HTTP.
- Protocolos de seguridad de red: implementan la seguridad en las comunicaciones de red entre **servidores**, incluye HTTPS, SSL y SFTP.
- Protocolos de gestión de red: proporcionan mantenimiento y gobierno de red, incluyen SNMP e ICMP.

Un grupo de protocolos de red que trabajan juntos en los niveles superior e inferior comúnmente se les denomina *familia de protocolos.*

El modelo OSI (Open System Interconnection) organiza conceptualmente a las familias de protocolos de red en **capas de red** específicas. Este Sistema de Interconexión Abierto tiene por objetivo establecer un contexto en el cual basar las arquitecturas de comunicación entre diferentes sistemas.

A continuación listamos algunos de los protocolos de red más conocidos, según las capas del modelo OSI:

**Protocolos de la capa 1 - Capa física**

- USB: Universal Serial Bus
- Ethernet: Ethernet physical layer
- DSL: Digital subscriber line
- Etherloop: Combinación de Ethernet and DSL
- Infrared: Infrared radiation
- Frame Relay
- SDH: Jerarquía digital síncrona
- SONET: Red óptica sincronizada

**Protocolos de la capa 2 - Enlace de datos**

- DCAP: Protocolo de acceso del cliente de la conmutación de la transmisión de datos
- FDDI: Interfaz de distribución de datos en fibra
- HDLC: Control de enlace de datos de alto nivel
- LAPD: Protocolo de acceso de enlace para los canales
- PPP: Protocolo punto a punto
- STP (Spanning Tree Protocol): protocolo del árbol esparcido
- VTP VLAN: trunking virtual protocol para LAN virtual
- MPLS: Conmutación multiprotocolo de la etiqueta

**Protocolos de la capa 3 - Red**

- ARP: Protocolo de resolución de direcciones
- BGP: Protocolo de frontera de entrada
- ICMP: Protocolo de mensaje de control de Internet
- IPv4: Protocolo de internet versión 4
- IPv6: Protocolo de internet versión 6
- IPX: Red interna del intercambio del paquete
- OSPF: Abrir la trayectoria más corta primero
- RARP: Protocolo de resolución de direcciones inverso

**Protocolos de la capa 4 - Transporte**

- IL: Convertido originalmente como capa de transporte para 9P
- SPX: Intercambio ordenado del paquete
- SCTP: Protocolo de la transmisión del control de la corriente
- TCP: Protocolo del control de la transmisión
- UDP: Protocolo de datagramas de usuario
- iSCSI: Interfaz de sistema de computadora pequeña de Internet iSCSI
- DCCP: Protocolo de control de congestión de datagramas

**Protocolos de la capa 5 - Sesión**

- NFS: Red de sistema de archivos
- SMB: Bloque del mensaje del **servidor**
- RPC: Llamada a procedimiento remoto
- SDP: Protocolo directo de sockets
- SMB: Bloque de mensajes del servidor
- SMPP: Mensaje corto punto a punto

**Protocolos de la capa 6- Presentación**

- TLS: Seguridad de la capa de transporte
- SSL: Capa de conexión segura
- XDR: Extenal data representation
- MIME: Multipurpose Internet Mail Extensions

**Protocolos de la capa 7 - Aplicación**

- DHCP: Protocolo de configuración dinámica de host
- DNS: Domain Name System
- HTTP: Protocolo de transferencia de hipertexto
- HTTPS: Protocolo de transferencia de hipertexto seguro
- POP3: Protocolo de oficina de correo
- SMTP: protocolo de transferencia simple de correo
- Telnet: Protocolo de telecomunicaciones de red



**RESUMEN:**

Los protocolos de Internet son conjuntos de reglas y estándares que permiten la comunicación y transferencia de datos entre dispositivos conectados a la red. A continuación, te resumo una lista con algunos de los principales protocolos de Internet:

### 1. **Protocolo de Control de Transmisión (TCP)**
- **Función:** Asegura la entrega fiable de una secuencia de bytes desde un programa en un ordenador a otro programa en otro ordenador.
- **Características:** Conexión establecida mediante un proceso de "handshake" de tres pasos, manejo de retransmisión y control de flujo.

### 2. **Protocolo de Internet (IP)**
- **Función:** Direccionamiento y enrutamiento de los paquetes de datos entre dispositivos en diferentes redes.
- **Versiones:** IPv4 (direcciones de 32 bits) e IPv6 (direcciones de 128 bits).

### 3. **Protocolo de Datagrama de Usuario (UDP)**
- **Función:** Permite el envío de mensajes (datagramas) sin establecer previamente una conexión, con menor sobrecarga que TCP.
- **Características:** No garantiza la entrega ni el orden de los mensajes.

### 4. **Protocolo de Transferencia de Hipertexto (HTTP)**
- **Función:** Facilita la transferencia de documentos en la World Wide Web.
- **Versiones:** HTTP/1.1, HTTP/2 y HTTP/3.

### 5. **Protocolo Seguro de Transferencia de Hipertexto (HTTPS)**
- **Función:** Es una extensión de HTTP que proporciona una capa de seguridad utilizando SSL/TLS.
- **Características:** Cifra los datos para proteger la privacidad y la integridad.

### 6. **Protocolo de Transferencia de Archivos (FTP)**
- **Función:** Transferencia de archivos entre un cliente y un servidor.
- **Modos de operación:** Activo y pasivo.

### 7. **Protocolo Simple de Transferencia de Correo (SMTP)**
- **Función:** Envío de correos electrónicos entre servidores.
- **Características:** No está diseñado para la recuperación de correos, solo para su envío.

### 8. **Protocolo de Oficina de Correos (POP3)**
- **Función:** Recuperación de correos electrónicos desde un servidor.
- **Características:** Descarga los correos al cliente y los elimina del servidor.

### 9. **Protocolo de Acceso a Mensajes de Internet (IMAP)**
- **Función:** Permite acceder y manipular correos electrónicos almacenados en un servidor.
- **Características:** Mantiene los correos en el servidor y permite el acceso desde múltiples dispositivos.

### 10. **Protocolo de Configuración Dinámica de Host (DHCP)**
- **Función:** Asignación automática de direcciones IP a dispositivos en una red.
- **Características:** Facilita la administración de direcciones IP en redes grandes.

### 11. **Protocolo de Resolución de Direcciones (ARP)**
- **Función:** Traduce direcciones IP a direcciones MAC (dirección física de la tarjeta de red).
- **Características:** Funciona dentro de una red de área local (LAN).

### 12. **Protocolo de Mensajes de Control de Internet (ICMP)**
- **Función:** Envía mensajes de control y error entre dispositivos de red.
- **Aplicaciones:** Utilizado por herramientas de diagnóstico como ping y traceroute.

Estos protocolos permiten la comunicación eficiente y fiable entre diferentes sistemas y dispositivos en Internet. Cada uno de ellos cumple funciones específicas y se adapta a diferentes necesidades y escenarios de la red.

**Referencias**

Jithin. Interserver. (2016). *Protocolos de red comunes* https://www.interserver.net/tips/kb/common-network-protocols-ports/ consultado agosto, 2019.

Rouse, Margaret. TechTarget. (s/a). *Protocolos de red* https://searchnetworking.techtarget.com/definition/protocol consultado agosto, 2019.

---

XUN 2024


#Básicos 
#Protocolos

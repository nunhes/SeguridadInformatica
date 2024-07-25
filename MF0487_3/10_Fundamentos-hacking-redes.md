# Fundamentos del hackeo de redes
El hackeo de redes abarca una serie de técnicas diseñadas para explorar, analizar y explotar redes. Dominar los conceptos básicos de la *piratería* de redes es esencial para todo profesional de la ciberseguridad. Esta sección profundiza en las técnicas de reconocimiento de redes, una piedra angular del hacking ético, seguida de un examen de la explotación de servicios y protocolos de red.

## Técnicas de reconocimiento de redes

El reconocimiento, o *escaneo*, es el primer paso esencial en el proceso de hacking, con el objetivo de reunir la mayor cantidad de información posible sobre la red objetivo. Esta fase prepara el terreno para identificar vulnerabilidades que pueden ser explotadas posteriormente. Las principales técnicas de reconocimiento incluyen:

- **Barrido de Ping** (Ping Sweep): Esta técnica implica enviar solicitudes ICMP Echo (pings) a múltiples hosts para determinar cuáles están activos. Es un método básico pero efectivo para mapear sistemas activos dentro de un rango de red.
- **Escaneo de Puertos** (Port Scanning): Al escanear puertos, los hackers pueden identificar puertos abiertos en un dispositivo de red y deducir los servicios asociados que están ejecutándose en ellos. Este conocimiento ayuda a identificar posibles puntos de entrada al sistema.
- **Mapeo de Red** (Network Mapping): Más allá de identificar hosts activos y puertos abiertos, el mapeo de red establece una vista comprensiva de la estructura de la red, incluyendo los dispositivos y cómo están interconectados. Este paso es crucial para planificar estrategias de ataque subsecuentes.

### Herramientas para el Reconocimiento
Se han desarrollado distintas herramientas para automatizar y refinar el proceso de reconocimiento, haciéndolo más eficiente y completo:

- **Nmap** (Network Mapper): Quizás la herramienta de exploración de redes más conocida. Nmap es versátil en la realización de inventarios de red, la gestión de programas de actualización de servicios y el monitoreo del tiempo de actividad de hosts o servicios. Es destacable su eficacia en el escaneo de puertos y el mapeo de redes.
- **Zenmap**: Esta es la versión oficial de interfaz gráfica de usuario (GUI) de Nmap, diseñada para simplificar el proceso de escaneo. Zenmap proporciona una interfaz intuitiva para iniciar escaneos con Nmap e incluye funciones para guardar escaneos, comparar resultados y explorar redes visualmente.
- **Netdiscover**: Una herramienta de reconocimiento ARP activa/pasiva, Netdiscover es excelente para detectar direcciones IP en una red local sin activar los sistemas de detección de intrusos (IDS) de los hosts de la red.

### Explotación de Servicios y Protocolos de Red
Identificar servicios de red vulnerables y comprender los protocolos subyacentes es fundamental para elaborar ataques dirigidos o defensas. Este proceso típicamente sigue a la fase de reconocimiento, aprovechando la información recopilada.

• **Identificación de Servicios Vulnerables**: Una vez que un atacante sabe qué servicios están ejecutándose en puertos abiertos, puede buscar vulnerabilidades conocidas en esos servicios. Esto podría implicar buscar en bases de datos de vulnerabilidades o usar herramientas automatizadas como **Nessus** u **OpenVAS** para escanear debilidades.

### Ejemplos de Ataques a Protocolos de Red Específicos
• **Ataques Man-in-the-Middle (MitM)**: Estos ocurren cuando un atacante intercepta la comunicación entre dos partes, ya sea para escuchar o para hacerse pasar por una de las partes, haciendo que parezca que el intercambio normal de información no se ha interrumpido.
• **Suplantación de DNS (DNS Spoofing)**: Esto implica corromper el proceso de consulta de DNS para redirigir el tráfico de sitios legítimos a sitios maliciosos, a menudo con el objetivo de capturar credenciales o distribuir malware.
• **Explotación de Vulnerabilidades del SMB (Server Message Block)**: Los sistemas más antiguos o no parcheados pueden ser susceptibles a ataques como ***WannaCry***, que explotó vulnerabilidades del protocolo SMB para propagar ransomware.

En resumen, el reconocimiento de red establece la base para identificar vulnerabilidades potenciales en los servicios y protocolos de red. Las herramientas y técnicas destacadas en esta sección son indispensables para cualquiera que busque especializarse en hacking de redes o ciberseguridad. Comprender estos aspectos permite a los hackers éticos y a los profesionales de ciberseguridad anticipar, reconocer y mitigar posibles amenazas a la seguridad de la red.

### Comprensión de los Fundamentos de la Red

Dominar el arte del hacking de redes y asegurar medidas robustas de ciberseguridad requiere una comprensión fundamental de los conceptos de redes. Esta sección introduce los elementos centrales de las redes, la arquitectura de los modelos de red, una visión general de los protocolos de red esenciales y una comprensión de las topologías de red y las vulnerabilidades de infraestructura.

### Introducción a los Conceptos de Redes
Las redes permiten que computadoras y dispositivos se comuniquen y compartan recursos e información. En el corazón de esta comunicación están varios conceptos críticos:

• **Direcciones IP**: Cada dispositivo conectado a una red se asigna una dirección de Protocolo de Internet (IP), que sirve como un identificador único que permite a los dispositivos encontrarse y comunicarse entre sí. Las direcciones IP pueden ser estáticas o dinámicas y se categorizan en IPv4 e IPv6.
• **Direcciones MAC**: Las direcciones de Control de Acceso a Medios (MAC) son identificadores de hardware integrados en las interfaces de red. A diferencia de las direcciones IP, que pueden cambiar según la red, las direcciones MAC son constantes y únicas para cada dispositivo.
• **Subredes**: Una subred, o subred de red, es un segmento de una red más grande. Dividir redes en subredes puede mejorar el rendimiento y la seguridad al contener el tráfico de difusión y reducir la congestión.
• **Enrutadores y Conmutadores**: Ambos son cruciales para dirigir datos en una red. Los enrutadores conectan múltiples redes entre sí, eligiendo la mejor ruta para que los paquetes de datos viajen a través de las redes. Los conmutadores, por otro lado, conectan dispositivos dentro de una sola red, dirigiendo datos basándose en direcciones MAC.

### El Papel de los Modelos OSI y TCP/IP en Redes
El modelo de Interconexión de Sistemas Abiertos (OSI) y el conjunto de Protocolos de Control de Transmisión/Protocolo de Internet (TCP/IP) son marcos que guían los estándares y protocolos para la red digital.

• **El modelo OSI**: es un marco conceptual que consta de siete capas, cada una especificando funciones particulares de la red, desde la transmisión física de datos hasta los servicios específicos de las aplicaciones.
• **El modelo TCP/IP**: más simplificado, consta de cuatro capas. Es la base de Internet y proporciona las reglas que aseguran una comunicación eficiente en Internet. Comprender estos modelos es esencial para los hackers porque ayuda a identificar en qué capa un posible ataque podría dirigirse o dónde pueden estar las vulnerabilidades.

### Protocolos de Red

Los protocolos de red son conjuntos de reglas que dictan cómo se transmiten y reciben los datos en las redes. Los protocolos clave incluyen:

• **TCP (Protocolo de Control de Transmisión) y UDP (Protocolo de Datagrama de Usuario)**: TCP es orientado a la conexión, asegurando la entrega confiable y ordenada de un flujo de datos. UDP es más simple, sin conexión, a menudo utilizado para la transmisión donde la pérdida de algunos datos es tolerable.

• **ICMP (Protocolo de Mensajes de Control de Internet)**: Utilizado para propósitos de diagnóstico e informes de errores en la comunicación de la red.
• **ARP (Protocolo de Resolución de Direcciones)**: Resuelve direcciones IP en direcciones MAC, asegurando que los datos lleguen al dispositivo correcto en una red local.

• **DNS (Sistema de Nombres de Dominio)**: Traduce nombres de dominio fáciles de usar (como www.example.com) en direcciones IP que las computadoras utilizan para acceder entre sí.

Las consideraciones de seguridad varían para cada protocolo, como la susceptibilidad a la suplantación o la escucha, lo que resalta la necesidad de medidas de seguridad robustas, incluidos firewalls, cifrado y configuraciones seguras.

### [Topologías de Red](https://www.lifewire.com/computer-network-topology-illustrated-4064043) e Infraestructura

La disposición de los elementos de una red refleja su topología, lo que afecta significativamente su rendimiento y su vulnerabilidad a ataques:

- **Estrella**: Todos los nodos se conectan a un concentrador central. Es altamente resistente a fallos de nodos, pero depende en gran medida de la estabilidad del concentrador.
- **Bus**: Todos los nodos comparten una única línea de comunicación. Simple pero vulnerable a la escucha y a las colisiones de datos.
- **Anillo**: Los nodos se conectan a exactamente dos otros nodos, formando un anillo. La falla de un solo nodo puede interrumpir toda la red.
- **Malla**: Los nodos están interconectados generosamente, ofreciendo alta resistencia pero a costa de la complejidad.
- **Híbrida**: Combina dos o más topologías, buscando aprovechar los beneficios de cada una. Comprender estas topologías ayuda a identificar posibles puntos de fallo y ataque dentro de la infraestructura de una red.

En conclusión, una sólida comprensión de los fundamentos de la red, desde los roles cruciales de las direcciones IP y MAC hasta las complejidades de los protocolos y topologías de red, es indispensable para el hacking de redes y la ciberseguridad. Permite evaluaciones más informadas, planificación estratégica y protección efectiva de los sistemas de información.

## Enlaces de interés

### Herramientas para el Reconocimiento

- **Zenmap**: [Zenmap Official Documentation](https://nmap.org/zenmap/)
- **Netdiscover**: [Netdiscover GitHub Repository](https://github.com/netdiscover-scanner/netdiscover)

### Explotación de Servicios y Protocolos de Red
- **Nessus**: [Nessus Official Website](https://www.tenable.com/products/nessus)
- **OpenVAS**: [OpenVAS Official Website](https://www.openvas.org/)

### Ejemplos de Ataques a Protocolos de Red Específicos
- **Man-in-the-Middle (MitM) Attacks**: [OWASP MitM Attack Overview](https://owasp.org/www-community/attacks/Manipulator-in-the-middle_attack)
- **DNS Spoofing**: [Cloudflare DNS Spoofing](https://www.cloudflare.com/learning/dns/dns-cache-poisoning/)
- **WannaCry and SMB Vulnerabilities**: [WannaCry Ransomware Attack](https://en.wikipedia.org/wiki/WannaCry_ransomware_attack)
- **DDoS attacks**: [How do layer 3 DDoS attacks work?](https://www.cloudflare.com/learning/ddos/layer-3-ddos-attacks/)

### Comprensión de los Fundamentos de la Red

- **Direcciones IP y MAC**: [What is an IP Address?](https://www.whatismyip.com/what-is-an-ip-address/) y [What is a MAC Address?](https://www.lifewire.com/what-is-a-mac-address-2625970) [1. What is digital identity?](https://www.cloudflare.com/learning/access-management/what-is-identity/))
- **Subredes**: [[What is a subnet? | How subnetting works](https://www.cloudflare.com/learning/network-layer/what-is-a-subnet/)](https://www.networkcomputing.com/networking/ultimate-guide-subnetting)
- **[Enrutadores](https://www.cloudflare.com/learning/network-layer/what-is-a-router/) y Conmutadores**: [Router vs Switch][What is a subnet? | How subnetting works](https://www.cloudflare.com/learning/network-layer/what-is-a-subnet/)

### Modelos OSI y TCP/IP

- **Modelo OSI**: [OSI Model Explained](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/)
- **Modelo TCP/IP**: [TCP/IP Model Explained](https://www.cloudflare.com/learning/ddos/glossary/tcp-ip/)

### [Protocolos](https://www.cloudflare.com/learning/network-layer/what-is-a-protocol/) de Red

- **[TCP](https://www.cloudflare.com/learning/ddos/glossary/tcp-ip/) y [UDP](https://www.cloudflare.com/es-es/learning/ddos/glossary/user-datagram-protocol-udp/)**: [TCP vs UDP](https://www.lifewire.com/tcp-headers-and-udp-headers-explained-817970)
- **ICMP**: [ICMP Protocol](https://www.cloudflare.com/es-es/learning/ddos/glossary/internet-control-message-protocol-icmp/)
- **ARP**: [ARP Protocol](https://www.geeksforgeeks.org/how-address-resolution-protocol-arp-works/)
- **DNS**: [How DNS Works](https://www.cloudflare.com/learning/dns/what-is-dns/)

### [Topologías](https://helpdeskgeek.com/networking/what-is-mesh-network-topology/) de Red [1](https://www.bbc.co.uk/bitesize/guides/z666pbk/revision/1)

- **Star Topology**: [Star Topology](https://www.zenarmor.com/docs/network-basics/what-is-star-topology)
- **Bus Topology**: [Bus Topology](https://www.shiksha.com/online-courses/articles/what-is-a-bus-topology-blogId-156107)
- **Ring Topology**: [Ring Topology](https://www.zenarmor.com/docs/network-basics/what-is-ring-topology)
- **Mesh Topology**: [Mesh Topology](https://www.zenarmor.com/docs/network-basics/what-is-mesh-topology)
- **Hybrid Topology**: [Hybrid Topology](https://www.zenarmor.com/docs/network-basics/what-is-hybrid-topology)


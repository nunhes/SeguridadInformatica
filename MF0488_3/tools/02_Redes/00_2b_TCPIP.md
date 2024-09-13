# MODELO OSI
```mermaid
graph TD
    A[Modelo OSI] --> B[Capa 1: Física]
    A --> C[Capa 2: Enlace de Datos]
    A --> D[Capa 3: Red]
    A --> E[Capa 4: Transporte]
    A --> F[Capa 5: Sesión]
    A --> G[Capa 6: Presentación]
    A --> H[Capa 7: Aplicación]

    %% Descripción de cada capa
    B --> B1[Transmitir señales físicas]
    B --> B2[Medios de transmisión: cables, ondas]
    C --> C1[Control de acceso al medio]
    C --> C2[Detección y corrección de errores]
    D --> D1[Encaminamiento de paquetes]
    D --> D2[Dirección IP]
    E --> E1[Control de flujo de datos]
    E --> E2[Transporte confiable: TCP]
    F --> F1[Establecimiento de sesiones]
    F --> F2[Gestión de conexiones]
    G --> G1[Encriptación y compresión]
    G --> G2[Conversión de formatos de datos]
    H --> H1[Interfaz para aplicaciones de usuario]
    H --> H2[Protocolos como HTTP, FTP]

    %% Comunicación entre capas
    B1 -->|Suministra señales a| C
    C1 -->|Enmarca datos para| D
    D1 -->|Encamina paquetes hacia| E
    E1 -->|Asegura transporte a| F
    F1 -->|Coordina sesiones para| G
    G1 -->|Presenta datos a| H

```

**Capas del Modelo OSI:**

1. **Capa 1: Física**: Medios, señales y transmisión binaria &rarr; RS-232, RJ45, V.34, 100BASE-TX, SHD, DSL, 802.11
2. **Capa 2: Enlace de Datos**: Direccionamiento físico &rarr; Ethernet, 802.11, MAC/LLC, VALN, ATM, HDP, Canal de fibra, Frame Relay, HDLC, PPP, Q.921, Token Ring
3. **Capa 3: Red**: Determinación de ruta y direccionamiento lógico &rarr; IP, ARP, IPsec, ICMP, IGMP, OSPF
4. **Capa 4: Transporte**: Conexiones de extremo a extremo y confiabilidad &rarr; TCP, UDP, SCTP, SSL, TSL
5. **Capa 5: Sesión**: Comunicación entre hosts &rarr; Establecimiento de sesión en TCP, SIP, RTP, RPC-Named pipes
6. **Capa 6: Presentación**: Representación de datos y encriptación &rarr; Reconocimiento de datos: HTML, DOC, JPEG, MP3, AVI, Sockets
7. **Capa 7: Aplicación**: Proceso de red hasta la aplicación &rarr; DNS, WWW/HTTP, P2P, EMAIL/POP, SMTP, Telnet, FTP
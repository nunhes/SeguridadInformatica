# MODELO TCP/IP

```mermaid
graph TD
    A[Modelo TCP/IP] --> B[Capa de Aplicación]
    A --> C[Capa de Transporte]
    A --> D[Capa de Red]
    A --> E[Capa de Enlace de Datos]

    %% Descripción de cada capa
    B --> B1[Protocolos como HTTP, FTP, SMTP, DNS]
    B --> B2[Interfaz para aplicaciones de usuario]
    C --> C1[Protocolos como TCP y UDP]
    C --> C2[Control de flujo y corrección de errores - TCP]
    C --> C3[Transmisión sin conexión - UDP]
    D --> D1[Protocolos como IP]
    D --> D2[Encaminamiento de paquetes]
    E --> E1[Protocolos como Ethernet, Wi-Fi]
    E --> E2[Acceso al medio físico]

    %% Comunicación entre capas
    B1 -->|Solicita servicios de| C
    C1 -->|Encapsula datos para| D
    D1 -->|Encamina paquetes hacia| E
    E1 -->|Transmite señales físicas a| E
```

**Capas del modelo TCP/IP**

- **Capa de Aplicación:** Protocolo de alto nivel que proporciona servicios de red a las aplicaciones.

- **Capa de Transporte:** Maneja la comunicación entre sistemas finales, asegurando la entrega de datos.

- **Capa de Red:** Encaminamiento y direccionamiento de paquetes a través de la red.

- **Capa de Enlace de Datos:** Controla la transmisión de datos a través de los medios físicos.
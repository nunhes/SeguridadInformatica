# Capa 2 o capa de enlace de datos

La capa de enlace de datos es la segunda capa del modelo OSI y se sitúa sobre la capa física. Su principal función es garantizar una transferencia de datos libre de errores entre dos nodos que están directamente conectados a través de un medio físico (por ejemplo, cables, ondas de radio). Esta capa se encarga de la organización, control y gestión del acceso al medio, así como de la detección y corrección de errores en la transmisión.

### Funciones de la Capa de Enlace de Datos

1. **Encapsulamiento de Datos**:
   - La capa de enlace de datos recibe datos de la capa de red (por ejemplo, paquetes IP) y los encapsula en tramas. Cada trama incluye no solo los datos, sino también información de control, como direcciones MAC y sumas de verificación.

2. **Direccionamiento Físico**:
   - Utiliza direcciones MAC (Media Access Control) para identificar de forma única los dispositivos en una red local. Las direcciones MAC se utilizan para enviar tramas al destinatario correcto dentro de la misma red.

3. **Control de Acceso al Medio (MAC - Media Access Control)**:
   - Gestiona el acceso al medio físico de transmisión para evitar colisiones, especialmente en redes compartidas como Ethernet. Este control es crucial en redes donde varios dispositivos pueden intentar transmitir datos simultáneamente.

4. **Detección y Corrección de Errores**:
   - La capa de enlace de datos incluye mecanismos para detectar errores en las tramas recibidas (como bits corruptos). Si se detecta un error, la trama puede ser descartada o se puede solicitar su retransmisión.

5. **Control de Flujo**:
   - Asegura que el transmisor no envíe datos más rápido de lo que el receptor puede procesarlos, evitando la sobrecarga del receptor.

### Subcapas de la Capa de Enlace de Datos
La capa de enlace de datos se divide a menudo en dos subcapas:

1. **Subcapa LLC (Logical Link Control)**:
   - Gestiona la comunicación con la capa de red superior y proporciona control de errores y control de flujo.

2. **Subcapa MAC (Media Access Control)**:
   - Se encarga del control de acceso al medio de transmisión y del direccionamiento físico (direcciones MAC).

### Protocolos de la Capa de Enlace de Datos

Existen varios protocolos que operan en la capa de enlace de datos. Algunos de los más comunes incluyen:

1. **Ethernet**:
   - Es uno de los protocolos más utilizados en redes de área local (LAN). Define cómo los dispositivos en una red local pueden comunicarse a través de un medio compartido. Ethernet utiliza la tecnología de conmutación de tramas y puede operar en diferentes velocidades (10 Mbps, 100 Mbps, 1 Gbps, 10 Gbps, etc.).

2. **Wi-Fi (IEEE 802.11)**:
   - Protocolo utilizado para redes inalámbricas. Permite que dispositivos como computadoras, teléfonos móviles y otros equipos se comuniquen sin cables en una red local. Wi-Fi también define métodos para la autenticación y el cifrado de datos.

3. **PPP (Point-to-Point Protocol)**:
   - Protocolo que permite la transmisión de tramas a través de enlaces punto a punto, como conexiones dial-up o enlaces seriales. PPP incluye mecanismos para la autenticación, la compresión de datos y la encapsulación de diferentes protocolos de red.

4. **HDLC (High-Level Data Link Control)**:
   - Protocolo de enlace de datos utilizado en conexiones punto a punto y en redes de área amplia (WAN). HDLC proporciona un mecanismo para la transferencia de datos secuencial con control de errores.

5. **Frame Relay**:
   - Utilizado en redes de área amplia (WAN) para la transmisión de datos sobre enlaces digitales. Frame Relay es más eficiente que protocolos más antiguos como X.25, pero ofrece menos control sobre los errores, delegando esta función a las capas superiores.

6. **ATM (Asynchronous Transfer Mode)**:
   - Tecnología de conmutación utilizada en redes de alta velocidad. ATM utiliza pequeñas celdas de datos de tamaño fijo para la transmisión, lo que permite un manejo eficiente y predecible del tráfico de red.

Estos protocolos permiten que la capa de enlace de datos cumpla con sus funciones esenciales en una red, garantizando que los datos se transmitan de manera eficiente y confiable entre dispositivos conectados directamente.
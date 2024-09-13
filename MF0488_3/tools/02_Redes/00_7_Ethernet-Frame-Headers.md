# **Principios de Ethernet, Trama y Encabezados**

### 1. **Principios de Ethernet**
Ethernet es una tecnología estándar utilizada para las redes de área local (LAN), que permite la comunicación de datos entre dispositivos en una red. Se basa en los siguientes principios:

- **Acceso múltiple con detección de portadora y evitación de colisiones (CSMA/CD)**: En versiones clásicas de Ethernet (como 10BASE-T), los dispositivos en la red comparten el mismo medio de transmisión y pueden enviar datos en cualquier momento. CSMA/CD se utiliza para gestionar el acceso al medio y evitar colisiones cuando dos dispositivos intentan transmitir al mismo tiempo. Hoy en día, este método es menos relevante debido a la evolución hacia Ethernet conmutada, donde cada dispositivo tiene un enlace dedicado.

- **Topología**: Las redes Ethernet modernas generalmente utilizan una topología en estrella, donde cada dispositivo está conectado a un conmutador (switch). Sin embargo, las primeras versiones de Ethernet usaban una topología en bus o en anillo.

- **Estándares**: Ethernet está estandarizado por el IEEE bajo la norma IEEE 802.3, que define las características físicas y el protocolo de control de acceso al medio (MAC).

### 2. **Trama Ethernet**
Una trama Ethernet es la unidad básica de datos transmitidos en una red Ethernet. Cada trama contiene varios campos con información crucial para la entrega y el procesamiento de los datos.

#### Estructura de una Trama Ethernet:

1. **Preamble (Preámbulo) y Start Frame Delimiter (SFD)**: 
   - **Preamble (7 bytes)**: Consiste en una secuencia de bits que ayuda a sincronizar el reloj entre el emisor y el receptor.
   - **SFD (1 byte)**: Señala el final del preámbulo y el inicio de la trama real.

2. **Destination MAC Address (6 bytes)**: Dirección MAC del destinatario. Indica el dispositivo al que se envía la trama.

3. **Source MAC Address (6 bytes)**: Dirección MAC del emisor. Indica el dispositivo que envió la trama.

4. **EtherType/Length (2 bytes)**: Este campo puede indicar el tipo de protocolo encapsulado en la trama (si su valor es mayor a 1500) o la longitud del campo de datos (si su valor es igual o menor a 1500).

5. **Payload/Datos (46 a 1500 bytes)**: Contiene los datos reales que se están transmitiendo, como un paquete IP. La longitud mínima es de 46 bytes; si los datos son menores, se añaden bytes de relleno para cumplir con la longitud mínima.

6. **Frame Check Sequence (FCS, 4 bytes)**: Es un código de verificación (CRC) que permite al receptor detectar errores en la trama. El FCS se calcula a partir de los datos en la trama y se verifica al recibirla.

#### Estructura del Encabezado Ethernet:
Los campos importantes de la trama Ethernet que forman el encabezado son:

- **Destination MAC Address (6 bytes)**
- **Source MAC Address (6 bytes)**
- **EtherType/Length (2 bytes)**

### 3. **Encabezados en Ethernet**
El encabezado de Ethernet está compuesto principalmente por la dirección MAC de origen, la dirección MAC de destino, y el campo EtherType/Longitud. Este encabezado es fundamental para la entrega de la trama a través de la red, ya que contiene toda la información necesaria para dirigir la trama al dispositivo correcto y determinar el tipo de datos que contiene.

#### Campos Detallados:

- **Direcciones MAC**: Las direcciones MAC son identificadores únicos asignados a cada dispositivo de red. Son esenciales para la entrega de datos en redes Ethernet, permitiendo que las tramas se dirijan correctamente.

- **Campo EtherType/Longitud**: Este campo tiene un doble propósito, ya que puede indicar tanto el tipo de protocolo (por ejemplo, IPv4 o IPv6) como la longitud de la carga útil en tramas más pequeñas.

### Resumen
Ethernet es la base de las redes LAN y opera utilizando tramas que contienen direcciones MAC y datos encapsulados en un formato estandarizado. La estructura de la trama y los principios de funcionamiento, como CSMA/CD en versiones clásicas, permiten que Ethernet sea una tecnología robusta y ampliamente utilizada en todo tipo de redes.
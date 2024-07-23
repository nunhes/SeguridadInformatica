El modelo OSI (Open Systems Interconnection) es un marco conceptual que describe las funciones de un sistema de comunicaciones en siete capas distintas. Cada capa tiene responsabilidades específicas y se comunica con las capas adyacentes. Aquí están las siete capas del modelo OSI:

1. **Capa Física (Layer 1)**:
   - **Función**: Transmisión y recepción de datos sin procesar a través de un medio físico (cables, fibra óptica, etc.).
   - **Ejemplos de dispositivos**: Cables, conectores, repetidores, hubs.

2. **Capa de Enlace de Datos (Layer 2)**:
   - **Función**: Proporciona una transferencia de datos fiable a través de un enlace físico; maneja el direccionamiento físico (direcciones MAC) y la detección/corrección de errores.
   - **Ejemplos de dispositivos**: Switches, bridges.

3. **Capa de Red (Layer 3)**:
   - **Función**: Determina cómo se enrutan los datos de un dispositivo a otro a través de múltiples redes; maneja el direccionamiento lógico (direcciones IP).
   - **Ejemplos de dispositivos**: Routers.

4. **Capa de Transporte (Layer 4)**:
   - **Función**: Proporciona transferencia de datos de extremo a extremo; asegura la entrega completa y ordenada de los datos; maneja el control de flujo y la recuperación de errores.
   - **Ejemplos de protocolos**: TCP (Transmission Control Protocol), UDP (User Datagram Protocol).

5. **Capa de Sesión (Layer 5)**:
   - **Función**: Maneja y controla las conexiones entre computadoras; establece, gestiona y termina sesiones entre aplicaciones.
   - **Ejemplos de protocolos**: RPC (Remote Procedure Call), PPTP (Point-to-Point Tunneling Protocol).

6. **Capa de Presentación (Layer 6)**:
   - **Función**: Traduce los datos entre el formato de la red y el formato que puede entender una aplicación; maneja la codificación, encriptación y compresión de datos.
   - **Ejemplos de formatos/protocolos**: SSL/TLS (Secure Sockets Layer/Transport Layer Security), JPEG, ASCII, XML.

7. **Capa de Aplicación (Layer 7)**:
   - **Función**: Proporciona servicios de red a las aplicaciones de software; maneja la interfaz entre el software de aplicación y la red.
   - **Ejemplos de aplicaciones/protocolos**: HTTP (Hypertext Transfer Protocol), FTP (File Transfer Protocol), SMTP (Simple Mail Transfer Protocol), DNS (Domain Name System).

### Resumen de las Capas del Modelo OSI

1. **Capa Física**: Transmisión de bits a través de un medio físico.
2. **Capa de Enlace de Datos**: Transferencia de datos fiable dentro de una red local.
3. **Capa de Red**: Enrutamiento de datos entre diferentes redes.
4. **Capa de Transporte**: Transferencia de datos de extremo a extremo, confiabilidad.
5. **Capa de Sesión**: Gestión de sesiones y conexiones.
6. **Capa de Presentación**: Traducción, encriptación, y compresión de datos.
7. **Capa de Aplicación**: Servicios de red para aplicaciones de software.

Cada capa del modelo OSI desempeña un papel específico y se comunica con las capas adyacentes para proporcionar una comunicación efectiva y eficiente a través de la red.



## **Capa de Enlace de Datos**: Transferencia de datos fiable dentro de una red local.

La conmutación de capa 2, también conocida como switching de capa 2, es una funcionalidad clave en las redes de área local (LAN). Se refiere a la capacidad de los dispositivos de red, como los switches, para transmitir datos dentro de una red local basándose en las direcciones MAC (Media Access Control) de los dispositivos de origen y destino. Las funciones básicas de la conmutación de capa 2 incluyen:

1. **Aprendizaje de direcciones MAC**:
   - Los switches de capa 2 aprenden las direcciones MAC de los dispositivos conectados a sus puertos. Al recibir un paquete, el switch registra la dirección MAC de origen y el puerto en el que fue recibido en su tabla de direcciones MAC.

2. **Tabla de direcciones MAC**:
   - Esta tabla asocia las direcciones MAC con los puertos específicos del switch. Permite que el switch sepa por dónde reenviar los paquetes para alcanzar un dispositivo particular.

3. **Reenvío de tramas**:
   - Cuando el switch recibe una trama, examina la dirección MAC de destino y consulta su tabla de direcciones MAC para determinar a qué puerto enviar la trama. Si la dirección MAC de destino está en la tabla, el switch reenvía la trama solo a ese puerto específico, reduciendo el tráfico en la red.

4. **Flooding**:
   - Si la dirección MAC de destino no está en la tabla de direcciones MAC (por ejemplo, si es un dispositivo nuevo en la red), el switch envía la trama a todos los puertos excepto al puerto de origen. Este proceso se llama flooding.

5. **Segmentación de red**:
   - Los switches de capa 2 dividen la red en múltiples dominios de colisión, lo que significa que cada puerto en un switch es un dominio de colisión separado. Esto mejora la eficiencia de la red al reducir las colisiones de datos.

6. **Spanning Tree Protocol (STP)**:
   - Los switches de capa 2 utilizan STP para evitar bucles de red. Los bucles pueden ocurrir si hay múltiples caminos redundantes entre los switches. STP desactiva selectivamente los caminos redundantes para asegurar una única ruta libre de bucles.

### Beneficios de la Conmutación de Capa 2

- **Rendimiento mejorado**: Reduce el tráfico innecesario en la red al enviar tramas solo a los dispositivos destinatarios.
- **Segmentación de red**: Mejora la eficiencia y reduce las colisiones al segmentar la red en dominios de colisión más pequeños.
- **Seguridad**: Permite configuraciones de seguridad que pueden limitar el acceso a ciertos segmentos de la red basándose en las direcciones MAC.

En resumen, la conmutación de capa 2 es esencial para la operación eficiente de redes locales, ya que optimiza el flujo de datos y mejora la gestión del tráfico dentro de la red.
# Capa 3 o capa de red

La capa de red es la tercera capa del modelo OSI y se encarga de la gestión del enrutamiento y el direccionamiento de los paquetes de datos a través de redes y subredes. Su principal función es garantizar que los datos se envíen desde el origen hasta el destino a través de una red de manera eficiente, manejando el enrutamiento entre diferentes redes y subredes.

### Funciones de la Capa de Red

1. **Direccionamiento Lógico**:
   - Asigna direcciones lógicas únicas a cada dispositivo en la red (como direcciones IP). Estas direcciones permiten identificar y localizar dispositivos en una red amplia o en Internet.

2. **Encaminamiento (Enrutamiento)**:
   - Determina la mejor ruta para los paquetes de datos desde el origen hasta el destino. Utiliza tablas de enrutamiento y algoritmos para seleccionar el camino más eficiente a través de la red.

3. **Fragmentación y Reensamblaje**:
   - Fragmenta los paquetes grandes en fragmentos más pequeños que pueden ser enviados a través de redes que tienen un tamaño máximo de unidad de transmisión (MTU) más pequeño. Luego, reensambla los fragmentos en el destino.

4. **Control de Congestión**:
   - Gestiona el tráfico para evitar el sobrecargar de redes y garantizar que los paquetes no se pierdan debido a la congestión.

5. **Interconexión de Redes**:
   - Facilita la comunicación entre diferentes redes, como redes locales (LAN) y redes de área amplia (WAN), asegurando que los datos puedan viajar a través de diferentes tipos de redes.

### Protocolos de la Capa de Red

1. **IP (Internet Protocol)**:
   - **IPv4**: Protocolo más utilizado para la asignación de direcciones IP y el enrutamiento de paquetes en redes. Utiliza direcciones de 32 bits, lo que permite alrededor de 4.3 mil millones de direcciones únicas.
   - **IPv6**: Protocolo de próxima generación que utiliza direcciones de 128 bits, lo que permite un número prácticamente ilimitado de direcciones. IPv6 fue diseñado para abordar la limitación de direcciones de IPv4 y proporcionar mejoras en la eficiencia del enrutamiento y la seguridad.

2. **ICMP (Internet Control Message Protocol)**:
   - Utilizado para enviar mensajes de control y errores en redes IP. Por ejemplo, ICMP es utilizado por la herramienta de diagnóstico `ping` para verificar la conectividad entre dispositivos.

3. **IGMP (Internet Group Management Protocol)**:
   - Gestiona la membresía en grupos de multidifusión en redes IPv4. Permite a los dispositivos unirse y salir de grupos de multidifusión, facilitando la transmisión de datos a múltiples destinos al mismo tiempo.

4. **ARP (Address Resolution Protocol)**:
   - Se utiliza para mapear direcciones IP a direcciones MAC en redes locales. ARP permite que un dispositivo determine la dirección física (MAC) correspondiente a una dirección IP cuando necesita enviar un paquete en una red local.

5. **RARP (Reverse Address Resolution Protocol)**:
   - Protocolo menos común utilizado para obtener una dirección IP a partir de una dirección MAC. RARP es una forma inversa de ARP y ha sido en gran medida reemplazado por otros protocolos como BOOTP y DHCP.

6. **OSPF (Open Shortest Path First)**:
   - Protocolo de enrutamiento de estado de enlace utilizado en redes IP para determinar la mejor ruta para el enrutamiento de paquetes. OSPF es un protocolo de enrutamiento interior (IGP) que usa algoritmos basados en el estado del enlace para calcular las rutas.

7. **BGP (Border Gateway Protocol)**:
   - Protocolo de enrutamiento de vector de ruta utilizado para intercambiar información de enrutamiento entre sistemas autónomos en Internet. BGP es esencial para el funcionamiento de la Internet global y asegura que los datos se enruten eficientemente entre diferentes proveedores de servicios.

8. **EIGRP (Enhanced Interior Gateway Routing Protocol)**:
   - Protocolo de enrutamiento avanzado desarrollado por Cisco que combina características de protocolos de estado de enlace y de vector de distancia. EIGRP se utiliza en redes grandes y complejas para mejorar la eficiencia del enrutamiento.

9. **RIP (Routing Information Protocol)**:
   - Uno de los protocolos de enrutamiento más antiguos, basado en el algoritmo de vector de distancia. RIP es sencillo de configurar y se utiliza en redes más pequeñas. Existen versiones como RIPng para IPv6.

### Resumen

La capa de red es fundamental para el funcionamiento de las redes de comunicación, ya que maneja el direccionamiento, enrutamiento y entrega de paquetes a través de diferentes redes. Los protocolos que operan en esta capa aseguran que los datos puedan viajar de manera eficiente y confiable desde el origen hasta el destino, independientemente de la complejidad de la red intermedia.
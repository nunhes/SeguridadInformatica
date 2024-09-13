# Capa 4 o capa de transporte

La capa de transporte es la cuarta capa del modelo OSI y se encarga de la transferencia de datos entre aplicaciones en sistemas finales. Su función principal es asegurar que los datos se transfieran de manera confiable y eficiente, controlando la segmentación, la secuenciación y el flujo de datos entre dos dispositivos finales. La capa de transporte proporciona servicios como el control de errores, el control de flujo y el control de la secuencia de datos.

### Funciones de la Capa de Transporte

1. **Segmentación y Reensamblaje**:
   - Divide los datos de una aplicación en segmentos más pequeños para su transmisión a través de la red. En el destino, estos segmentos se reensamblan para reconstruir los datos originales.

2. **Control de Flujo**:
   - Regula la cantidad de datos que se envían para evitar la sobrecarga del receptor, asegurando que no reciba datos más rápido de lo que puede procesar.

3. **Control de Errores**:
   - Detecta y corrige errores que pueden ocurrir durante la transmisión de los datos, garantizando la entrega de datos sin errores.

4. **Establecimiento, Mantenimiento y Terminación de Conexiones**:
   - En el caso de los protocolos orientados a la conexión, la capa de transporte establece, mantiene y termina conexiones entre aplicaciones en sistemas finales.

5. **Control de Secuencia**:
   - Asegura que los segmentos de datos lleguen en el orden correcto y maneja la retransmisión de segmentos que se pierden o llegan con errores.

### Protocolos de la Capa de Transporte

1. **TCP (Transmission Control Protocol)**:
   - **Orientado a la Conexión**: Establece una conexión entre el emisor y el receptor antes de que comience la transferencia de datos. 
   - **Confiabilidad**: Asegura que los datos se entreguen de manera precisa y en el orden correcto mediante la retransmisión de segmentos perdidos y la reordenación de segmentos desordenados.
   - **Control de Flujo y Errores**: Incluye mecanismos para controlar el flujo de datos y detectar y corregir errores.
   - **Control de Congestión**: Ajusta la velocidad de transmisión de datos para evitar la congestión de la red.

2. **UDP (User Datagram Protocol)**:
   - **No Orientado a la Conexión**: Envía datagramas sin establecer una conexión previa, lo que hace que el proceso sea más rápido pero menos fiable.
   - **Sin Garantías**: No proporciona mecanismos para la retransmisión de datos perdidos ni para el control de errores y flujo. Los datagramas pueden llegar en desorden o perderse sin que el protocolo lo detecte.
   - **Uso**: A menudo se usa en aplicaciones donde la velocidad es crucial y la pérdida ocasional de datos es tolerable, como en el streaming de video y audio en tiempo real.

3. **SCTP (Stream Control Transmission Protocol)**:
   - **Orientado a la Conexión**: Proporciona una conexión entre aplicaciones, similar a TCP, pero con capacidades adicionales.
   - **Multiplexión de Streams**: Permite la transmisión simultánea de múltiples flujos de datos dentro de una sola conexión, lo que puede mejorar el rendimiento y la eficiencia en aplicaciones que requieren múltiples tipos de datos.
   - **Transparencia de la Red**: Incluye características para manejar la pérdida de datos y la recuperación de fallos de red.

4. **DCCP (Datagram Congestion Control Protocol)**:
   - **Protocolo de Datagramas**: Similar a UDP en que no establece una conexión, pero incluye mecanismos para el control de congestión de la red.
   - **Control de Congestión**: Proporciona mecanismos para gestionar la congestión de la red, lo que lo hace adecuado para aplicaciones que requieren un control explícito sobre la congestión pero no necesitan la confiabilidad de TCP.

### Resumen

La capa de transporte es crucial para garantizar la comunicación eficiente y fiable entre aplicaciones en diferentes sistemas. Los protocolos de la capa de transporte, como TCP, UDP, SCTP y DCCP, tienen diferentes características que los hacen adecuados para diversas aplicaciones y escenarios de red. TCP ofrece una comunicación confiable y orientada a la conexión, ideal para aplicaciones que requieren la entrega exacta de datos, mientras que UDP proporciona una opción más rápida y menos fiable, adecuada para aplicaciones en tiempo real. SCTP y DCCP ofrecen capacidades adicionales para manejar flujos de datos múltiples y control de congestión, respectivamente.
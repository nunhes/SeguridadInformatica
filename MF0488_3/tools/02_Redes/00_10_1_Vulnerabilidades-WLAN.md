# Vulnerabilidades en WLANs

Las redes WLAN (Wireless Local Area Networks) son vulnerables a una variedad de ataques debido a la naturaleza inalámbrica de la comunicación. Estas vulnerabilidades pueden ser explotadas para comprometer la seguridad de la red, acceder a información sensible, o incluso interrumpir el servicio. A continuación, se describen las principales vulnerabilidades y ataques que pueden afectar a una WLAN.

### **1. Vulnerabilidades Comunes en WLANs**

1. **Cifrado Débil o Inexistente**:
   - **WEP (Wired Equivalent Privacy)**: Uno de los primeros protocolos de cifrado para redes Wi-Fi, pero ahora considerado extremadamente inseguro debido a sus debilidades criptográficas que permiten ser roto fácilmente.
   - **Cifrado deshabilitado**: Algunas redes pueden no utilizar cifrado, lo que permite que cualquiera pueda interceptar y leer el tráfico.

2. **Configuraciones Predeterminadas Inseguras**:
   - **Contraseñas predeterminadas**: Los routers y puntos de acceso (APs) vienen con contraseñas predeterminadas que son fácilmente adivinables.
   - **SSID predeterminado**: El uso del SSID predeterminado puede indicar a los atacantes que la red tiene configuraciones de seguridad débiles o sin cambios.

3. **Falta de Segmentación de la Red**:
   - Si los usuarios invitados y los dispositivos internos comparten la misma red, se incrementa el riesgo de ataques de un dispositivo comprometido hacia otros dispositivos en la red.

4. **Fallas en el Protocolo WPS (Wi-Fi Protected Setup)**:
   - WPS permite que los usuarios se conecten a la red con solo pulsar un botón o introducir un PIN, pero tiene vulnerabilidades que pueden ser explotadas para acceder a la red, incluso si se utiliza WPA o WPA2.

### **2. Principales Ataques a una WLAN**

1. **Ataques de Sniffing (Escucha Pasiva)**:
   - **Captura de Tráfico**: Un atacante puede interceptar el tráfico de la red si no está cifrado o si se utiliza un cifrado débil. Con herramientas como **Wireshark** o **Kismet**, el atacante puede capturar paquetes de datos para analizarlos y extraer información sensible.
   - **Ataque de Reconocimiento**: El atacante analiza la red para identificar dispositivos conectados, protocolos utilizados, y posibles puntos débiles.

2. **Ataques de Fuerza Bruta y Diccionario**:
   - **Fuerza Bruta**: El atacante intenta todas las combinaciones posibles de contraseñas hasta encontrar la correcta. Este tipo de ataque puede ser dirigido al protocolo WPA/WPA2.
   - **Ataques de Diccionario**: El atacante utiliza listas predefinidas de contraseñas comunes para intentar acceder a la red.

3. **Rogue APs (Puntos de Acceso Falsos)**:
   - **Punto de Acceso Malicioso**: El atacante configura un punto de acceso con un SSID similar al de la red legítima para engañar a los usuarios y hacer que se conecten a su red, lo que permite capturar credenciales y otro tráfico sensible.
   - **Ataque de Hombre en el Medio (Man-in-the-Middle, MITM)**: Una vez que los usuarios están conectados al punto de acceso falso, el atacante puede interceptar y modificar la comunicación entre el usuario y la red legítima.

4. **Ataques de Deautenticación**:
   - **Ataque de Desautenticación**: Utilizando herramientas como **aireplay-ng**, un atacante puede enviar paquetes de desautenticación a los clientes conectados, forzándolos a desconectarse de la red. Esto puede ser utilizado para llevar a cabo otros ataques, como el de rogue APs o simplemente para interrumpir el servicio.
   - **Ataque de Desautenticación Masiva**: Un atacante puede lanzar un ataque de desautenticación contra todos los dispositivos conectados, causando una denegación de servicio (DoS).

5. **Ataques a WPS (Wi-Fi Protected Setup)**:
   - **Ataque PIN Reaver**: WPS usa un PIN de 8 dígitos, pero debido a una debilidad en el protocolo, un atacante puede adivinar el PIN con relativa facilidad, obteniendo acceso a la red. Herramientas como **Reaver** pueden explotar esta vulnerabilidad.

6. **Ataques de Evil Twin**:
   - **Red Evil Twin**: Un atacante crea una réplica exacta de la red legítima (incluyendo el SSID y la configuración de seguridad) para engañar a los usuarios y hacer que se conecten a su red falsa. Una vez conectados, el atacante puede capturar todo el tráfico.

7. **Ataques de Denegación de Servicio (DoS)**:
   - **Interferencia con la señal**: Un atacante puede utilizar un dispositivo para emitir señales en la misma frecuencia que la red Wi-Fi, creando interferencias que degradan o bloquean el servicio.
   - **Ataque de Jamming**: Similar al de interferencia, pero con la intención específica de dejar inoperable la red Wi-Fi.

8. **Explotación de Configuraciones de Seguridad Inadecuadas**:
   - **Redes Abiertas**: Las redes Wi-Fi sin cifrado permiten que cualquier usuario en el rango se conecte a la red y potencialmente acceda a recursos internos o interfiera con otros dispositivos conectados.
   - **Contraseñas débiles**: Si la red utiliza contraseñas fáciles de adivinar, un atacante puede penetrar en la red sin mucha dificultad.

### **3. Cómo Mitigar las Vulnerabilidades**

1. **Usar Cifrado Fuerte**:
   - Configurar la red para usar **WPA3** si es posible, o **WPA2** con AES si WPA3 no está disponible.
   - Desactivar WEP y WPA (TKIP), ya que son inseguros.

2. **Deshabilitar WPS**:
   - WPS es vulnerable a ataques de fuerza bruta. Es recomendable deshabilitarlo si no es estrictamente necesario.

3. **Implementar Autenticación 802.1X con RADIUS**:
   - En redes empresariales, usar autenticación 802.1X para controlar el acceso a la red mediante un servidor RADIUS.

4. **Usar Contraseñas Fuertes y Cambiarlas Regularmente**:
   - Configurar contraseñas WPA2/WPA3 con una longitud y complejidad adecuadas.

5. **Segregar la Red**:
   - Crear VLANs o redes separadas para dispositivos invitados, IoT y la red interna principal para limitar el impacto en caso de una brecha de seguridad.

6. **Monitoreo y Detección de Intrusos**:
   - Implementar sistemas de detección de intrusos (IDS) y software de monitoreo para detectar actividad sospechosa en la red.

7. **Mantener el Firmware Actualizado**:
   - Asegúrate de que los routers, puntos de acceso y otros dispositivos de red estén actualizados con el firmware más reciente, que suele incluir parches de seguridad.

8. **Ocultar el SSID (Opcional)**:
   - Aunque no es una medida de seguridad sólida, ocultar el SSID puede disuadir a los atacantes casuales, aunque los ataques más avanzados aún pueden detectar la red.

9. **Filtrado de Direcciones MAC**:
   - Configura el filtrado de direcciones MAC para permitir solo a dispositivos autorizados conectarse a la red. Sin embargo, ten en cuenta que las direcciones MAC pueden ser falsificadas.

### Resumen

Las WLANs presentan múltiples vulnerabilidades que pueden ser explotadas por atacantes para acceder a información sensible, interrumpir el servicio, o comprometer la seguridad de la red. Para proteger una WLAN, es esencial utilizar cifrado fuerte, desactivar características inseguras como WPS, implementar autenticación robusta, y mantener el firmware de los dispositivos actualizado. Además, medidas como la segmentación de la red y el monitoreo continuo pueden ayudar a mitigar los riesgos y a detectar ataques antes de que causen daños significativos.
# Fingerprinting de sistemas operativos

El **fingerprinting de sistemas operativos** es una técnica utilizada para identificar el sistema operativo de un dispositivo en una red mediante el análisis de las respuestas a solicitudes específicas. Esto se puede hacer de manera activa o pasiva. Una de las formas más comunes de realizar fingerprinting es analizando las respuestas a paquetes ICMP (Internet Control Message Protocol), entre otros tipos de solicitudes.

### 1. **Fingerprinting Activo**
   - **Descripción:** En el fingerprinting activo, el atacante (o auditor) envía solicitudes específicas al sistema objetivo y analiza las respuestas para determinar las características del sistema operativo.
   - **Método ICMP:**
     - **Echo Request (ICMP Type 8):** En un escaneo típico de ping, se envía un paquete ICMP Echo Request, y el sistema operativo responde con un ICMP Echo Reply (Type 0). Sin embargo, la manera en que se estructura la respuesta (como el tamaño del TTL, la longitud del campo de datos, o incluso la presencia o ausencia de ciertas opciones) puede variar según el sistema operativo.
     - **ICMP Timestamp Request (Type 13) y Address Mask Request (Type 17):** Estos tipos menos comunes de ICMP pueden usarse para recopilar información adicional, como la configuración de la máscara de subred o la marca de tiempo del sistema, que también pueden variar según el sistema operativo.

### 2. **Fingerprinting Pasivo**
   - **Descripción:** En el fingerprinting pasivo, no se envían paquetes, sino que el auditor monitorea el tráfico de red existente para analizar patrones en las respuestas y deducir el sistema operativo.
   - **Método ICMP Pasivo:**
     - **Análisis de tráfico:** Un atacante puede observar las respuestas ICMP generadas por otros sistemas en la red (por ejemplo, respuestas ICMP Echo Reply a solicitudes de ping) y analizar características como el TTL, la longitud de la cabecera IP, las banderas IP, y el tamaño de las respuestas para hacer inferencias sobre el sistema operativo sin interactuar directamente con él.

### **Características Específicas Utilizadas en Fingerprinting**
- **TTL (Time to Live):** Diferentes sistemas operativos establecen valores de TTL predeterminados cuando envían un paquete. Por ejemplo:
  - Windows suele usar TTL=128.
  - Linux y Unix frecuentemente usan TTL=64.
  - Cisco routers suelen tener TTL=255.

- **Tamaño de la Ventana TCP (TCP Window Size):** El tamaño de la ventana TCP también varía según el sistema operativo y es un indicador útil cuando se combina con otros factores.

- **Longitud de la Cabecera IP:** Algunos sistemas operativos configuran la longitud de la cabecera IP de manera diferente, lo que puede ser un indicador.

- **Opciones TCP/IP:** La presencia, el orden y la configuración de las opciones en los paquetes TCP/IP (como el uso de SACK, timestamps, etc.) pueden ayudar a identificar el sistema operativo.

### **Ejemplos de Herramientas de Fingerprinting**
- **Nmap:** Una de las herramientas más conocidas que utiliza técnicas activas de fingerprinting. Envía múltiples tipos de paquetes, incluidos ICMP, para identificar el sistema operativo del objetivo.
- **p0f:** Una herramienta que se especializa en fingerprinting pasivo. Analiza el tráfico de red existente sin enviar ningún paquete al objetivo.
- **Wireshark:** Un analizador de protocolos de red de código abierto, compatible con distintos SO. Se utiliza para capturar y analizar **tráfico de red** en tiempo real, lo que permite ver detalles de cada paquete que viaja a través de una red.

### **Aplicaciones y Riesgos**
- **Aplicaciones:** El fingerprinting de sistemas operativos se usa comúnmente en auditorías de seguridad para mapear y clasificar sistemas en una red, ayudando a identificar posibles objetivos para ataques más avanzados. También es útil en la gestión de redes para la identificación de dispositivos y la confirmación de configuraciones.
- **Riesgos:** Para los atacantes, el fingerprinting puede ayudar a seleccionar exploits específicos para un sistema operativo conocido. Para los defensores, es crucial ocultar o modificar las características de las respuestas de red para dificultar este tipo de reconocimiento.

En resumen, el fingerprinting de sistemas operativos mediante ICMP y otros tipos de solicitudes es una técnica poderosa para identificar la plataforma subyacente de un sistema, basada en las particularidades de cómo diferentes sistemas operativos responden a estímulos específicos.


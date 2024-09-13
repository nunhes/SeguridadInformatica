### **VLANs (Virtual Local Area Networks)**

#### 1. **¿Qué es una VLAN?**

Una **VLAN (Virtual Local Area Network)** es una subred lógica que agrupa un conjunto de dispositivos en una red, independientemente de su ubicación física, como si estuvieran en la misma red local. Las VLANs permiten segmentar redes grandes en subredes más pequeñas, lo que mejora la gestión, seguridad y rendimiento de la red.

#### 2. **Funcionamiento de las VLANs**

Las VLANs se implementan en switches gestionables y permiten que dispositivos conectados a diferentes puertos del switch se comuniquen como si estuvieran en la misma red, aunque físicamente estén separados.

- **Switches y VLANs**: Un switch puede soportar múltiples VLANs, y cada VLAN se trata como una red independiente. Los dispositivos en una VLAN no pueden comunicarse directamente con dispositivos en otra VLAN sin la intervención de un router o un dispositivo de capa 3.

- **Etiquetado VLAN (802.1Q)**: Para permitir que múltiples VLANs pasen a través del mismo enlace físico (por ejemplo, entre dos switches), se utiliza el etiquetado VLAN mediante el estándar IEEE 802.1Q. Este protocolo añade una etiqueta a los paquetes que especifica a qué VLAN pertenecen.

#### 3. **Tipos de VLANs**

1. **VLANs de datos**: Segmentan el tráfico de datos normal de los usuarios.
2. **VLANs de voz**: A menudo se utilizan para separar el tráfico de voz (VoIP) del tráfico de datos para asegurar calidad de servicio (QoS).
3. **VLANs de administración**: Separan el tráfico de administración de red para proteger los dispositivos de red de accesos no autorizados.
4. **VLANs nativas**: La VLAN nativa es la VLAN predeterminada a la cual pertenece un puerto si no se ha especificado otra VLAN.

#### 4. **Beneficios de las VLANs**

1. **Mejoras en la seguridad**: Al separar el tráfico de diferentes grupos o tipos de datos, se pueden aplicar políticas de seguridad más estrictas. Por ejemplo, los servidores financieros pueden estar en una VLAN separada de la de los usuarios normales.
  
2. **Reducción del tráfico broadcast**: Las VLANs limitan el alcance de los mensajes broadcast, lo que puede reducir la cantidad de tráfico innecesario en la red.
  
3. **Flexibilidad y escalabilidad**: Permiten una gestión más flexible de los dispositivos en la red, facilitando la reubicación de dispositivos sin necesidad de reconfiguración física del cableado.
  
4. **Optimización del rendimiento**: Al segmentar la red, se puede reducir la congestión en áreas de alto tráfico, optimizando el rendimiento general.

#### 5. **Configuración de VLANs**

La configuración de VLANs se realiza en los switches gestionables. Aquí tienes un ejemplo básico:

1. **Creación de una VLAN**:
   ```bash
   switch(config)# vlan 10
   switch(config-vlan)# name Ventas
   ```

2. **Asignación de puertos a una VLAN**:
   ```bash
   switch(config)# interface fa0/1
   switch(config-if)# switchport mode access
   switch(config-if)# switchport access vlan 10
   ```

3. **Configuración de un Trunk** (para permitir el paso de múltiples VLANs entre switches):
   ```bash
   switch(config)# interface fa0/24
   switch(config-if)# switchport mode trunk
   switch(config-if)# switchport trunk allowed vlan 10,20
   ```

#### 6. **Inter-VLAN Routing**

Para que dispositivos en diferentes VLANs puedan comunicarse, se necesita un router o un switch de capa 3 que realice el **enrutamiento inter-VLAN**. Este proceso permite que el tráfico de una VLAN llegue a otra mediante la redirección de paquetes a través de un router.

#### 7. **Aplicaciones y Usos Comunes de VLANs**

- **Departamentos en una Empresa**: Diferentes departamentos, como ventas, administración y recursos humanos, pueden estar en VLANs separadas para segmentar el tráfico y aplicar políticas de seguridad específicas.
- **Entornos Multicliente (Multitenant)**: En centros de datos, los clientes pueden estar separados en diferentes VLANs para garantizar que su tráfico no se mezcle.
- **Separación de Tráfico de Voz y Datos**: En redes VoIP, se utiliza una VLAN separada para el tráfico de voz para asegurar la calidad del servicio y evitar interferencias con el tráfico de datos.

### Resumen

Las VLANs son fundamentales para la segmentación y gestión eficiente de redes grandes. Proporcionan flexibilidad, seguridad y mejoran el rendimiento al permitir que una única infraestructura de red física soporte múltiples subredes lógicas, cada una con sus propias políticas y configuraciones. Su implementación es clave en redes modernas para optimizar recursos, proteger datos sensibles y asegurar la calidad del servicio en aplicaciones críticas como VoIP.

## Simular VLANs en VirtualBox

Puedes simular una VLAN utilizando máquinas virtuales en VirtualBox. Para hacerlo, necesitarás configurar las máquinas virtuales (VMs) y los conmutadores virtuales de manera que simulen el comportamiento de una VLAN en una red física. A continuación, te guiaré paso a paso para configurar una VLAN simulada utilizando VirtualBox.

### Requisitos Previos
- **VirtualBox**: Debes tener instalado VirtualBox en tu sistema.
- **Máquinas Virtuales**: Debes tener creadas las máquinas virtuales que deseas incluir en las VLANs.
- **Switch Virtual (Router o Switch Gestionable)**: Puedes utilizar software como **pfSense** o **OpenWRT** para simular un switch gestionable o router de capa 3, que permita el enrutamiento entre VLANs.

### Paso 1: Configurar las Interfaces de Red de las Máquinas Virtuales

1. **Abrir VirtualBox**: Inicia VirtualBox en tu sistema.
2. **Configurar las Interfaces de Red**:
   - Para cada máquina virtual, ve a `Configuración > Red`.
   - Cambia el `Adaptador de red` a `Adaptador puente` o `Red interna`. 
     - **Adaptador puente**: Conecta la VM directamente a la red física (ideal si deseas simular VLANs con un router/switch físico).
     - **Red interna**: Conecta las VMs a una red virtual interna dentro de VirtualBox (ideal para simulaciones completas dentro de VirtualBox).

3. **Asignar VLANs a las Interfaces**:
   - VirtualBox por sí solo no soporta etiquetas VLAN (802.1Q) directamente en las interfaces de red de las VMs. Para simular VLANs, puedes utilizar diferentes `Redes Internas` para cada VLAN.
   - Crea diferentes redes internas para cada VLAN, por ejemplo:
     - `VLAN10`
     - `VLAN20`
   - Asigna cada VM a la red interna que representa la VLAN a la que quieres que pertenezca.

### Paso 2: Configurar el Router o Switch Virtual

Si deseas simular la comunicación entre VLANs, necesitarás un dispositivo virtual que soporte el enrutamiento entre VLANs.

1. **Instalar pfSense o OpenWRT**:
   - Crea una nueva VM en VirtualBox e instala un sistema operativo como **pfSense** o **OpenWRT**, que puede funcionar como router o switch de capa 3.
   
2. **Configurar Interfaces en el Router Virtual**:
   - Asigna múltiples interfaces de red en la VM de pfSense/OpenWRT, una para cada VLAN (red interna) que hayas creado en VirtualBox.
   - Configura cada interfaz de red en pfSense/OpenWRT para que actúe como una interfaz para una VLAN diferente.

3. **Configurar Enrutamiento entre VLANs**:
   - En el router virtual, configura las rutas y reglas de firewall necesarias para permitir o bloquear la comunicación entre las diferentes VLANs según sea necesario.
   - Puedes definir reglas de firewall en pfSense para permitir solo cierto tráfico entre VLANs, o para bloquear el tráfico completamente entre algunas VLANs.

### Paso 3: Probar la Configuración

1. **Asignar Direcciones IP**:
   - Asegúrate de que cada VM tenga una dirección IP en el rango correspondiente a la VLAN a la que pertenece.
   - Puedes configurar las direcciones IP manualmente o utilizar un servidor DHCP configurado en el router virtual.

2. **Probar Conectividad**:
   - Desde una VM, realiza un ping a otra VM dentro de la misma VLAN para verificar la conectividad.
   - Si configuraste el enrutamiento entre VLANs, intenta hacer ping desde una VM en una VLAN a una VM en otra VLAN.
   - Verifica que las reglas de firewall en el router virtual están funcionando como esperas (bloqueando o permitiendo el tráfico entre VLANs).

### Paso 4: Opciones Avanzadas

- **Etiquetado VLAN (802.1Q)**: Aunque VirtualBox no soporta directamente el etiquetado VLAN en las interfaces de red de las VMs, puedes utilizar software adicional dentro de las VMs para manejar etiquetas VLAN (por ejemplo, configurar interfaces virtuales VLAN en Linux).
- **Simulación de Switches Gestionables**: Puedes crear escenarios más complejos utilizando múltiples routers o switches virtuales y configurar rutas estáticas, NAT, o incluso VPNs entre diferentes VLANs.

### Resumen

Simular VLANs en VirtualBox es completamente factible y puede ser una excelente manera de aprender y probar configuraciones de red. Aunque VirtualBox tiene algunas limitaciones en cuanto al soporte nativo de etiquetado VLAN, puedes usar diferentes redes internas para simular VLANs y utilizar un router o switch virtual como pfSense para manejar el enrutamiento entre VLANs. Esta configuración te permitirá experimentar con escenarios de red avanzados, probar configuraciones de seguridad, y mejorar tu comprensión del funcionamiento de VLANs en redes reales.
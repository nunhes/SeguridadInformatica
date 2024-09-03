# Red Windows en VirtualBox

Para configurar un rango de IP para tu red interna en VirtualBox, puedes utilizar una subred privada de clase C. Un rango comúnmente utilizado es el **192.168.1.0/24**, lo que te dará las direcciones IP de **192.168.1.1** a **192.168.1.254**. Aquí te dejo una sugerencia para la asignación de direcciones IP dentro de esa subred:

- **Rango de IP de la red**: `192.168.1.0/24`
- **IP del Servidor Windows Server (Controlador de dominio)**: `192.168.1.10`
- **IP para las máquinas Windows 10**:
  - Máquina 1 (Alta seguridad): `192.168.1.20`
  - Máquina 2 (Media seguridad): `192.168.1.21`
  - Máquina 3 (Baja seguridad): `192.168.1.22`

- **Puerta de enlace predeterminada** (si decides usar una máquina o router virtual como puerta de enlace): `192.168.1.1`
- **DNS Server**: Usualmente, es la misma IP del controlador de dominio, en este caso `192.168.1.10`.

### Configuración en VirtualBox:

- **Red Interna (Internal Network)**: Al configurar esta red en VirtualBox, debes asegurarte de que las máquinas compartan la misma red interna. Puedes asignar direcciones IP estáticas a cada máquina o usar el servicio DHCP configurado en el Windows Server si prefieres asignar IPs dinámicamente.

### Configuración en el servidor Windows Server:

Si decides usar IPs estáticas:

1. **Configuración manual de IP en el Windows Server:**
   - Accede a **Centro de redes y recursos compartidos** > **Cambiar configuración del adaptador**.
   - Haz clic derecho en la conexión de red (la que esté conectada a la red interna) y selecciona **Propiedades**.
   - Selecciona **Protocolo de Internet versión 4 (TCP/IPv4)** y haz clic en **Propiedades**.
   - Configura la IP del servidor a `192.168.1.10`, la máscara de subred a `255.255.255.0`, y el DNS preferido a `192.168.1.10`.

2. **Configuración manual de IP en las máquinas Windows 10:**
   - Sigue los mismos pasos que para el servidor, pero asignando las IPs correspondientes a cada máquina (`192.168.1.20`, `192.168.1.21`, `192.168.1.22`).

De esta manera, todas las máquinas estarán en la misma subred y podrán comunicarse entre sí según lo necesites para la administración de Active Directory y las políticas de grupo.

## Configuración de ActiveDirectory

El siguiente paso para configurara nuetro modelo de red corporativa es resolver la configuración del Active Directory (AD) de nuestra red virtual con Windows Server. Vamos a configurar el servidor para que actúe como un controlador de dominio y establecer un dominio, luego crear unidades organizativas (OU) y usuarios con diferentes niveles de permisos.

### Paso 1: Instalar Active Directory y DNS en Windows Server

1. **Inicia tu máquina virtual con Windows Server.**

2. **Abrir el Administrador del Servidor:**
   - Haz clic en **Administrador del servidor** desde la barra de tareas.
   - Selecciona **Agregar roles y características**.

3. **Agregar Roles y Características:**
   - En la pantalla de bienvenida del Asistente para agregar roles y características, haz clic en **Siguiente**.
   - Selecciona **Instalación basada en características o en roles** y haz clic en **Siguiente**.
   - Selecciona el servidor donde deseas instalar los roles (tu servidor actual debería estar seleccionado por defecto) y haz clic en **Siguiente**.

4. **Seleccionar Roles de Servidor:**
   - Marca la casilla **Servicios de dominio de Active Directory (AD DS)**.
   - Aparecerá un cuadro de diálogo para agregar características requeridas para AD DS. Haz clic en **Agregar características**.
   - Haz clic en **Siguiente** hasta llegar a la pantalla de confirmación y luego en **Instalar**.
   - Espera a que se complete la instalación.

5. **Promover el servidor a controlador de dominio:**
   - Una vez que la instalación de AD DS se haya completado, verás una opción en el Administrador del Servidor que dice **Promover este servidor a controlador de dominio**. Haz clic en esa opción.

### Paso 2: Configurar un Nuevo Dominio

1. **Elegir una implementación de configuración:**
   - Selecciona **Agregar un nuevo bosque**.
   - En el campo **Nombre del dominio raíz**, ingresa el nombre de tu dominio (por ejemplo, `empresa.local`).

2. **Configuración de las opciones del dominio:**
   - En **Nivel funcional del bosque** y **Nivel funcional del dominio**, selecciona **Windows Server 2016** (o la versión más reciente disponible).
   - Marca la opción para **Servidor DNS**.
   - Ingresa una contraseña segura para el modo de recuperación de servicios de directorio.

3. **Opciones adicionales:**
   - En la sección de **Opciones de DNS**, simplemente haz clic en **Siguiente**. Podrías ver un mensaje sobre la delegación DNS, ignóralo y sigue adelante.

4. **Ruta de la base de datos de Active Directory, archivos de registro y SYSVOL:**
   - Puedes dejar las rutas por defecto. Haz clic en **Siguiente**.

5. **Revisar y ejecutar:**
   - Revisa la configuración y haz clic en **Instalar**.
   - El servidor se reiniciará automáticamente después de la instalación.

### Paso 3: Configurar Unidades Organizativas (OU) y Usuarios

1. **Abrir Usuarios y Equipos de Active Directory:**
   - Después del reinicio, abre **Usuarios y equipos de Active Directory** desde el menú **Herramientas** en el Administrador del Servidor.

2. **Crear Unidades Organizativas:**
   - Haz clic derecho en el nombre de tu dominio (`empresa.local`) en el panel izquierdo.
   - Selecciona **Nuevo** > **Unidad organizativa**.
   - Crea las siguientes OUs:
     - `AltaSeguridad`
     - `MediaSeguridad`
     - `BajaSeguridad`

3. **Crear Usuarios:**
   - Haz clic derecho en cada OU (por ejemplo, `AltaSeguridad`), selecciona **Nuevo** > **Usuario**.
   - Crea un usuario para cada nivel de seguridad, por ejemplo:
     - `UsuarioAlta` en `AltaSeguridad`
     - `UsuarioMedia` en `MediaSeguridad`
     - `UsuarioBaja` en `BajaSeguridad`
   - Asigna contraseñas a cada usuario y desmarca la opción **El usuario debe cambiar la contraseña en el próximo inicio de sesión** si deseas usar contraseñas predefinidas.

4. **Crear Grupos de Seguridad:**
   - Haz clic derecho en cada OU, selecciona **Nuevo** > **Grupo**.
   - Crea un grupo para cada nivel de seguridad, por ejemplo:
     - `GrupoAlta`
     - `GrupoMedia`
     - `GrupoBaja`
   - Asigna los usuarios correspondientes a sus grupos respectivos.

### Paso 4: Configurar Políticas de Grupo (GPO)

1. **Abrir Administración de directivas de grupo:**
   - En el Administrador del Servidor, selecciona **Herramientas** > **Administración de directivas de grupo**.

2. **Crear GPO para cada OU:**
   - Haz clic derecho en la OU `AltaSeguridad`, selecciona **Crear un GPO en este dominio y vincularlo aquí**.
   - Nombra la GPO, por ejemplo, `GPO_AltaSeguridad`.
   - Repite el proceso para `MediaSeguridad` y `BajaSeguridad`.

3. **Editar cada GPO para definir permisos:**
   - Haz clic derecho en la GPO `GPO_AltaSeguridad` y selecciona **Editar**.
   - Configura las políticas que desees para este grupo, como permisos de acceso, restricciones de software, configuraciones de escritorio, etc.
   - Algunas configuraciones comunes:
     - **AltaSeguridad**: Acceso total a la mayoría de las configuraciones y herramientas.
     - **MediaSeguridad**: Restricciones en la instalación de software y acceso limitado a configuraciones del sistema.
     - **BajaSeguridad**: Acceso solo a aplicaciones específicas y sin permisos para cambiar configuraciones del sistema.

### Paso 5: Unir las Máquinas Windows 10 al Dominio

1. **Configurar IP y DNS en cada máquina Windows 10:**
   - Configura la IP de cada máquina Windows 10 según el rango sugerido (`192.168.1.20`, `192.168.1.21`, `192.168.1.22`) y establece el DNS a la IP del servidor (`192.168.1.10`).

2. **Unir cada máquina al dominio:**
   - En cada máquina Windows 10, ve a **Configuración** > **Sistema** > **Acerca de**.
   - Selecciona **Unirse a un dominio** e ingresa `empresa.local`.
   - Proporciona las credenciales de un administrador del dominio.
   - Reinicia la máquina y luego inicia sesión con los usuarios respectivos (`UsuarioAlta`, `UsuarioMedia`, `UsuarioBaja`).

### Paso 6: Verificación y Pruebas

1. **Verificar la Aplicación de Políticas:**
   - Inicia sesión en cada máquina con las cuentas de usuario y verifica que las restricciones y permisos definidos en las GPO se aplican correctamente.

2. **Probar Accesos y Permisos:**
   - Intenta realizar tareas en cada máquina que deberían estar restringidas según el nivel de seguridad. Por ejemplo, intenta acceder al Panel de Control o instalar software en la máquina con `UsuarioBaja`.


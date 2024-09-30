# Seguridad en sistemas Windows

Para mantener tu Windows (10/11) seguro y mejorar el rendimiento eliminando aplicaciones que no usas (*debloatear*), puedes seguir los siguientes pasos:

### 1. **Mantener Windows Seguro**

#### a) **Mantén el Sistema Actualizado**
   - Windows 11 lanza actualizaciones de seguridad frecuentes. Asegúrate de que las actualizaciones automáticas estén activadas:  
     - **Configuración** → **Windows Update** → **Buscar actualizaciones**.

#### b) **Usa un Antivirus Confiable**
   - Windows Defender es una opción sólida y está integrada en Windows 11. Asegúrate de que esté habilitada:
     - **Configuración** → **Privacidad y seguridad** → **Seguridad de Windows**.
   - Si prefieres, puedes optar por un antivirus de terceros con buena reputación.

#### c) **Configura un Firewall**
   - El firewall integrado de Windows puede ayudar a bloquear accesos no autorizados.
     - **Configuración** → **Privacidad y seguridad** → **Seguridad de Windows** → **Firewall y protección de red**.

#### d) **Configura la Protección Ransomware**
   - Activa la protección contra el ransomware en Windows Defender:
     - **Configuración** → **Privacidad y seguridad** → **Seguridad de Windows** → **Protección contra virus y amenazas** → **Administrar la protección contra ransomware** → Activa **Acceso controlado a carpetas**.

#### e) **Autenticación Multifactor (MFA)**
   - Activa la autenticación en dos pasos para tu cuenta de Microsoft para aumentar la seguridad.

#### f) **Navegación Segura**
   - Evita hacer clic en enlaces sospechosos o descargar software de sitios web desconocidos.
   - Utiliza navegadores seguros con protecciones contra phishing (como Microsoft Edge o Google Chrome).

### 2. **Descongestionar (*Debloatear*) Windows**

Puedes eliminar aplicaciones que no usas de dos formas: manualmente o utilizando herramientas de terceros para hacer el proceso más eficiente.

#### a) **Desinstalar Aplicaciones Manualmente**
   - **Configuración** → **Aplicaciones** → **Aplicaciones y características**.
   - Revisa la lista y desinstala aplicaciones que no utilices.

#### b) **Debloatear con PowerShell**
   - **PowerShell** es una herramienta poderosa para eliminar aplicaciones preinstaladas que no aparecen en la lista normal de desinstalación.
   - Abre PowerShell como administrador y usa los siguientes comandos para eliminar algunas de las aplicaciones preinstaladas más comunes:
     ```powershell
     Get-AppxPackage *nombre_aplicacion* | Remove-AppxPackage
     ```
     Por ejemplo, para eliminar **Cortana**:
     ```powershell
     Get-AppxPackage *Microsoft.549981C3F5F10* | Remove-AppxPackage
     ```

#### c) **Usar Herramientas de Terceros**
   Hay varias herramientas gratuitas que pueden automatizar el proceso de desinstalación y limpiar otras configuraciones no deseadas:
   - **Debloat Windows 11**: Un script que puedes descargar desde GitHub para eliminar aplicaciones bloatware.
     - Ejemplo: [Windows10Debloater en GitHub](https://github.com/Sycnex/Windows10Debloater) 
     - Windows tous
   - **[O&O AppBuster](https://www.oo-software.com/en/ooappbuster)**: Una aplicación gratuita que permite eliminar aplicaciones preinstaladas y las que no son fáciles de desinstalar.

#### d) **Deshabilitar Aplicaciones en el Inicio**
   - Muchas aplicaciones se ejecutan en segundo plano y consumen recursos. Para deshabilitar aplicaciones en el inicio:
     - **Ctrl + Shift + Esc** → **Pestaña Inicio** → Deshabilita las aplicaciones que no necesites al inicio.

#### e) **Deshabilitar Servicios Innecesarios**
   - Puedes desactivar ciertos servicios que no necesitas.
     - **Win + R** → escribe `msconfig` → **Pestaña Servicios** → Marca "Ocultar todos los servicios de Microsoft" y desactiva lo que no necesitas.

### 3. **Consejos Adicionales**
   - **Usa un Navegador Seguro**: Asegúrate de usar navegadores con protección contra amenazas de seguridad.
   - **Habilita la Carpeta Segura**: Protege tus archivos importantes con la característica de carpetas seguras de Windows Defender.

Con estos pasos puedes mejorar la seguridad y rendimiento de tu sistema Windows 11, al mismo tiempo que eliminas el bloatware innecesario.

---



Deshabilitar ciertas aplicaciones y servicios en Windows 11 puede liberar espacio en disco y mejorar el rendimiento de tu sistema. Sin embargo, es importante hacerlo con cuidado, ya que algunos servicios son esenciales para el funcionamiento del sistema. Aquí tienes una lista de **aplicaciones** y **servicios** que puedes deshabilitar de forma segura según tus necesidades:

### 1. **Aplicaciones Innecesarias o Poco Utilizadas**

Las siguientes aplicaciones preinstaladas suelen ser innecesarias para muchos usuarios y pueden desinstalarse:

- **Cortana**: El asistente virtual de Microsoft, no esencial para la mayoría de los usuarios.
  - Desinstalar:  
    ```powershell
    Get-AppxPackage *Microsoft.549981C3F5F10* | Remove-AppxPackage
    ```

- **OneNote**: Si no usas OneNote, puedes desinstalarlo.
  - Desinstalar:  
    ```powershell
    Get-AppxPackage *OneNote* | Remove-AppxPackage
    ```

- **Aplicaciones Xbox**: Si no usas tu PC para juegos, puedes eliminar las aplicaciones relacionadas con Xbox (como Xbox Game Bar y Xbox Console Companion).
  - Desinstalar:  
    ```powershell
    Get-AppxPackage *Xbox* | Remove-AppxPackage
    ```

- **Microsoft Edge**: Aunque no se puede desinstalar completamente, puedes optar por no usarlo y usar otro navegador.
  - Para minimizar su uso, simplemente desactiva sus servicios en segundo plano.

- **3D Viewer, Paint 3D, Mixed Reality Portal, y Solitario**: Estas aplicaciones preinstaladas no son esenciales y se pueden eliminar si no las usas.

### 2. **Servicios que Puedes Deshabilitar**

#### Servicios Relacionados con Windows que Puedes Deshabilitar:
Debes tener cuidado al desactivar servicios, ya que algunos son fundamentales para el funcionamiento del sistema. Aquí hay algunos servicios que generalmente se pueden deshabilitar sin causar problemas:

1. **Fax**: Si no usas un fax físico o virtual, puedes deshabilitar este servicio.
   - Desactivar:  
     - **Win + R** → escribe `services.msc` → Busca **Fax** → Haz clic derecho y selecciona **Propiedades** → En **Tipo de inicio**, selecciona **Deshabilitado**.

2. **Bluetooth Support Service**: Desactívalo si no usas dispositivos Bluetooth.
   - Desactivar:  
     - Mismo proceso que **Fax**.

3. **Windows Search**: Si no usas la búsqueda de Windows con frecuencia, deshabilitar este servicio puede mejorar el rendimiento, especialmente en PCs más lentos. Ten en cuenta que esto desactiva la funcionalidad de búsqueda rápida.
   - Desactivar:  
     - **Win + R** → `services.msc` → Busca **Windows Search** → Deshabilitar.

4. **Connected User Experiences and Telemetry**: Responsable de recopilar datos de diagnóstico y telemetría para Microsoft.
   - Desactivar:  
     - **Win + R** → `services.msc` → Busca **Connected User Experiences and Telemetry** → Deshabilitar.

5. **Print Spooler**: Si no usas impresoras, puedes desactivar este servicio. 
   - Desactivar:  
     - **Win + R** → `services.msc` → Busca **Print Spooler** → Deshabilitar.

6. **Remote Desktop Services**: Si no usas el escritorio remoto, puedes deshabilitar este servicio para mayor seguridad y rendimiento.
   - Desactivar:  
     - **Win + R** → `services.msc` → Busca **Remote Desktop Services** → Deshabilitar.

7. **Windows Error Reporting Service**: Este servicio envía informes de errores a Microsoft. Si no te importa recibir informes de errores, puedes deshabilitarlo.
   - Desactivar:  
     - **Win + R** → `services.msc` → Busca **Windows Error Reporting Service** → Deshabilitar.

8. **Windows Update Medic Service**: Este servicio intenta reparar el sistema Windows Update automáticamente. Si deseas gestionar las actualizaciones manualmente, puedes deshabilitarlo.
   - Desactivar:  
     - **Win + R** → `services.msc` → Busca **Windows Update Medic Service** → Deshabilitar.

9. **Diagnostic Policy Service**: Este servicio realiza diagnósticos del sistema, pero no es estrictamente necesario para el uso diario.
   - Desactivar:  
     - **Win + R** → `services.msc` → Busca **Diagnostic Policy Service** → Deshabilitar.

### 3. **Deshabilitar Programas en el Inicio**
Desactivar programas innecesarios en el arranque también puede acelerar el tiempo de inicio y mejorar el rendimiento general.

- **Ctrl + Shift + Esc** → Pestaña **Inicio**.
- Desactiva programas que no necesitas que se ejecuten al iniciar el sistema, como **Spotify**, **Skype**, o **OneDrive**, si no los usas frecuentemente.

### 4. **Deshabilitar Efectos Visuales**
Reducir efectos visuales también puede mejorar el rendimiento, especialmente en máquinas con hardware más antiguo.

- **Win + R** → Escribe `sysdm.cpl` → **Pestaña Opciones avanzadas** → En **Rendimiento**, haz clic en **Configuración** → Selecciona **Ajustar para obtener el mejor rendimiento** o personaliza deshabilitando efectos visuales específicos.

### 5. **Desinstalar Características de Windows que No Usas**
Puedes deshabilitar características que no uses desde el panel de control:

- **Win + R** → Escribe `optionalfeatures` → Aparecerá la ventana de características de Windows. Aquí puedes desactivar características como:
  - **Internet Explorer 11**.
  - **Servicios de impresión y documentos**.
  - **Media Features** (si no usas Windows Media Player).
  - **Windows Subsystem for Linux** (si no lo usas).

### Consejos Finales:
- Antes de deshabilitar cualquier servicio o aplicación, asegúrate de saber para qué sirve, ya que algunos son críticos para el sistema.
- Es recomendable crear un **punto de restauración** antes de hacer cambios importantes en los servicios, por si necesitas revertir los cambios.
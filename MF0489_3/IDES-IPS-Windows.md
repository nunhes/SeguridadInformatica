# IDS|IPS en Windows

Los sistemas IDS e IPS protegen las redes corporativas, pero son excesivos para una sola computadora portátil. Es como instalar puertas de acero en su casa y rejas en las ventanas, lo que probablemente sea una buena idea si almacena secretos gubernamentales o parte del suministro de oro del país en su casa.

- La principal defensa contra las intrusiones, con diferencia, es un usuario informado y atento. Ningún software o hardware puede sustituirlo.
- La segunda línea de defensa es un enrutador debidamente protegido. Si viaja con un portátil y no puede confiar en el enrutador, utilice una VPN.
- La tercera línea de defensa es una suite antimalware que incluye un firewall.

Además, debes actualizar constantemente tu software y practicar una informática segura (protección con contraseña, cuenta de usuario con mínimos privilegios, etc.)

Si tienes eso, estás lo más cubierto posible contra intrusiones.


# Seguridad en Windows

Windows tiene capacidades de seguridad nativas que incluyen funciones de detección y prevención de intrusos:

### Windows Defender (antes Windows Defender ATP)
- **Funcionalidad**: Windows Defender ofrece tanto detección como prevención de amenazas. Puede identificar actividades sospechosas y tomar medidas para bloquear ataques en tiempo real.
- **Características**: Incluye análisis de comportamiento, protección contra malware y respuestas automáticas ante amenazas.

### Windows Event Viewer
- **Funcionalidad**: Aunque no es un IDS en sí, el Visor de Eventos de Windows permite a los administradores monitorear registros del sistema y de seguridad, lo que ayuda en la detección de anomalías.
- **Características**: Permite analizar registros de seguridad y eventos críticos.

### Opciones Adicionales
Para una protección más avanzada, se recomienda complementar estas herramientas nativas con soluciones de terceros, como Snort o Suricata, que ofrecen capacidades más especializadas de IDS/IPS.

Si deseas más información sobre cómo configurar y usar Windows Defender, aquí tienes un enlace útil: [Guía de Windows Defender](https://support.microsoft.com/es-es/windows/windows-security-88f1f368-37f1-4b91-82f4-634b24572a06).
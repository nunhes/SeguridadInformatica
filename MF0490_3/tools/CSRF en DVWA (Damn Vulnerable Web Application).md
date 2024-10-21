### CSRF en DVWA (Damn Vulnerable Web Application)

**Introducción a CSRF**

La **Cross-Site Request Forgery (CSRF)** es un tipo de vulnerabilidad de seguridad que permite a un atacante enviar solicitudes no autorizadas en nombre de un usuario autenticado a una aplicación web. Esto puede llevar a acciones indeseadas, como transferencias de fondos, cambios en la configuración de la cuenta o la ejecución de acciones no deseadas en el contexto del usuario legítimo.

**Características Principales de CSRF:**
- **Autenticación del Usuario:** La vulnerabilidad se aprovecha del hecho de que los navegadores envían automáticamente las cookies de sesión al servidor, permitiendo que el atacante realice acciones como el usuario autenticado.
- **Acciones Indeseadas:** Los ataques CSRF pueden llevar a cambios en la información de la cuenta, envíos de formularios, y otras acciones sin el conocimiento del usuario.

### CSRF en DVWA

**Damn Vulnerable Web Application (DVWA)** es una aplicación web diseñada para ayudar a los profesionales de la seguridad a practicar y mejorar sus habilidades en pruebas de penetración. DVWA tiene varias vulnerabilidades, incluida CSRF, que se pueden explorar y explotar.

#### Configuración de DVWA para CSRF

1. **Instalación de DVWA:** Asegúrate de tener DVWA instalada en un entorno seguro (como una máquina virtual). Puedes seguir las instrucciones de instalación en su [repositorio de GitHub](https://github.com/digininja/DVWA).

2. **Configuración de Seguridad:** Una vez instalada, establece el nivel de seguridad de DVWA en "Baja" para poder explorar la vulnerabilidad CSRF.

3. **Acceso a la Sección CSRF:**
   - Inicia sesión en DVWA.
   - Navega hasta la sección de "Vulnerabilities" y selecciona "CSRF".

#### Demostración del Ataque CSRF

1. **Autenticación:** Comienza iniciando sesión en DVWA con un usuario legítimo.

2. **Creación del Enlace Malicioso:**
   - Observa cómo se puede forzar la acción que cambia la contraseña o realiza una acción específica mediante la creación de un enlace malicioso que envía una solicitud a la aplicación web en nombre del usuario autenticado.

3. **Ejecutar el Ataque:**
   - Abre una nueva pestaña y visita el enlace malicioso (simulando que el usuario está autenticado en DVWA). Este enlace debería ejecutar la acción sin que el usuario lo sepa.

#### Mitigación de CSRF

Para proteger las aplicaciones web de CSRF, se pueden implementar varias medidas:

1. **Tokens CSRF:** Utilizar tokens únicos y aleatorios que se envían junto con las solicitudes críticas. El servidor verifica la validez del token antes de procesar la solicitud.

2. **Verificación del Referer:** Comprobar el encabezado `Referer` para asegurarse de que la solicitud provenga del mismo dominio.

3. **Métodos HTTP Seguros:** Limitar las acciones sensibles a métodos HTTP como POST y aplicar medidas de seguridad adicionales.

### Recursos Adicionales

- [OWASP CSRF Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Request_Forgery_Prevention_Cheat_Sheet.html) - Una guía completa sobre cómo prevenir CSRF en aplicaciones web.
- [DVWA Documentation](http://www.dvwa.co.uk/) - Documentación oficial de DVWA, que incluye información sobre cómo configurar y utilizar la aplicación.
- [Understanding CSRF Attacks](https://owasp.org/www-community/attacks/csrf) - Una explicación detallada sobre los ataques CSRF y cómo funcionan.

### Conclusión

La vulnerabilidad CSRF en DVWA es un excelente ejemplo de cómo los atacantes pueden explotar las debilidades de las aplicaciones web. Al practicar y entender cómo funcionan estos ataques, los profesionales de la seguridad pueden mejorar sus habilidades en la identificación y mitigación de estas vulnerabilidades en aplicaciones del mundo real.





https://www.udemy.com/course/owasp-zap-from-scratch
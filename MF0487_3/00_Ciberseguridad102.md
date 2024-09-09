# Ciberseguridad102

## Introducción

Bienvenida/o. Este artículo forma parte de la serie de textos sobre ciberseguridad y privacidad, cuyo objetivo es concienciar al público sobre la importancia de la ciberseguridad, tengan o no conocimientos técnicos, o simplemente estén interesados en conocer este extenso mundo.

~~Si has llegado hasta aquí es que ya has leído el articulo anterior **Ciberseguridad101**, si no te recomiendo que lo hagas, ya que este es una continuación del anterior. Y precede al articulo **Ciberseguridad303**, que completa está introducción general a la Seguridad de la información, la Seguridad Informática y la Ciberseguridad, que te recomiendo que leas a continuación de este.~~ 

#### Recordatorio ético

Un hacker no es un ciberdelincuente. Un hacker es un profesional de la ciberseguridad que utiliza su conocimiento con fines éticos para mejorar la seguridad de la información. Por otro lado, un ciberdelincuente utiliza su conocimiento con fines maliciosos, buscando su propio beneficio y dañando a terceros.

Es fundamental que, como futuro profesional de la ciberseguridad, utilices tu conocimiento de manera ética. El hecho de saber vulnerar sistemas no te da derecho a hacerlo sin autorización, de la misma manera que un cerrajero no puede abrir cerraduras sin permiso.

### Importancia de la concienciación en ciberseguridad

La concienciación en ciberseguridad es crucial tanto para individuos como para empresas. La cantidad de riesgos que se pueden evitar con una concienciación adecuada es enorme. A continuación, se presentan algunos puntos importantes para resaltar esta importancia:

#### La era del teletrabajo

Con el incremento del teletrabajo, cada vez más usuarios están conectados a Internet, manejando información sensible. La falta de conocimiento en ciberseguridad y la desinformación pueden llevar a que muchos usuarios no sepan cómo proteger adecuadamente su información.

#### Falsas creencias y desinformación

Es común encontrar falsas creencias sobre ciberseguridad, como pensar que un sitio con un candado verde en el navegador es completamente seguro. La era de la información irónicamente también es la era de la desinformación. Por ello, es esencial que todos los usuarios de Internet tengan un mínimo de conocimiento en ciberseguridad.

#### Estudios y resultados

Según un [estudio realizado por PhishPoint](https://www.phishpoint.com/), la concienciación en ciberseguridad puede reducir significativamente los riesgos. Por ejemplo:
- En una universidad en el noroeste de EE. UU., los ataques de phishing se redujeron hasta en un 90%.
- En una entidad gubernamental, la tasa de clics en enlaces sospechosos se redujo en un 80%.
- En una entidad financiera, se reportó una reducción del 95% en incidentes de malware en un periodo de dos años.

Estos resultados demuestran que la concienciación en ciberseguridad es una medida efectiva para proteger la información.

#### Implementación en Empresas

**No se trata solo de gastar dinero en activos físicos o lógicos para mejorar la seguridad. Es necesario que tanto los empleados como los sistemas de seguridad estén alineados y capacitados. La concienciación y la capacitación en ciberseguridad deben ser una inversión constante para garantizar la seguridad de la información.**

#### Adaptación al Contexto

Cada contexto requiere medidas de seguridad adaptadas. La seguridad necesaria para un particular no es la misma que para una empresa con miles de empleados. Sin embargo, mantener una alta concienciación y capacitación en ciberseguridad siempre será una buena inversión.

> La ciberseguridad y la privacidad son áreas cruciales en la era digital. Recuerda siempre actuar con ética y aprovechar los recursos disponibles para seguir aprendiendo y creciendo en este campo.

## ¿Es seguro un sitio web solo por tener el "candadito verde"?

En esta serie, no vamos a profundizar en detalles técnicos para mantener un lenguaje simple y accesible a todos.

### Desmitificando la seguridad en línea

Todos, o casi todos, entendemos que el "candadito verde" es un símbolo que indica que un sitio web utiliza HTTPS, una versión segura de HTTP. Vamos a desglosar qué significa esto y por qué no es una garantía total de seguridad.

**HTTPS y el candadito verde:**

- **HTTP y HTTPS** son protocolos de comunicación que se emplean en el trafico de datos e información en la red Internet: 
  - HTTP (HyperText Transfer Protocol) permite la transferencia de información en texto plano.
  - HTTPS (HyperText Transfer Protocol Secure) mejora dicha transferencia de información  mediante el cifrado de datos, utilizando el protocolo TLS (Transport Layer Security).


Para una explicación más técnica sobre HTTPS y su importancia, puedes visitar este [artículo de Cloudflare](https://www.cloudflare.com/learning/ssl/what-is-https/).

**Seguridad de TLS y SSL:**

- **SSL y TLS**: SSL (Secure Socket Layer), ahora obsoleto, fue el precursor de TLS y se utilizó para cifrar conexiones. Debido a fallas de seguridad SSL fue reemplazado por TLS, que cuenta con versiones más seguras como TLS 1.2 y 1.3.

Para más detalles sobre las diferencias entre SSL y TLS, consulta este [enlace](https://kinsta.com/knowledgebase/tls-vs-ssl/).

**El problema del candadito verde:**

- Aunque un sitio web con el "candadito verde" indica que utiliza HTTPS y, por ende, cifra la información, esto no garantiza que el sitio sea completamente seguro o legítimo. Los ciberdelincuentes también pueden obtener certificados HTTPS para sus sitios maliciosos.

Lee más sobre los peligros de confiar ciegamente en el candadito verde en este [artículo](https://www.certisur.com/noticias/por-que-no-es-seguro-confiar-en-los-candados-de-los-navegadores/).

---

## ¿Qué es la ingeniería social?

### Entendiendo la manipulación humana en ciberseguridad

La ingeniería social es el arte de manipular a las personas para que realicen acciones que normalmente no harían, como revelar información confidencial. Este tipo de ataques pueden ser simples o extremadamente complejos, dependiendo del contexto y de la información previa que el atacante tenga sobre su objetivo.

**Ejemplo de phishing:**

- Un ataque típico de phishing puede remitir un correo electrónico simulando ser un correo licito, por ejemplo imitando ser de tu banco, solicitando que accedas a un enlace para verificar tu cuenta debido a alguna "actividad sospechosa". Este enlace puede llevarte a un sitio clonado que recoge tus datos personales.

Para saber más sobre cómo identificar correos de phishing, puedes visitar esta [artículo del Incibe](https://www.incibe.es/empresas/tematicas/phishing) o el MOOC [Phishing](https://www.incibe.es/aprendeciberseguridad/phishing).

**Ejemplo de pendrives maliciosos:**

- Los ciberdelincuentes pueden dejar pendrives infectados en áreas públicas de una empresa. Empleados curiosos podrían recogerlos y conectarlos a sus computadoras, introduciendo malware en los sistemas de la empresa sin interacción directa de los atacantes.

Para más ejemplos de ingeniería social y cómo prevenirlos, revisa este [MOOC](https://www.incibe.es/aprendeciberseguridad/ingenieria-social).

### La importancia de la concienciación en ciberseguridad

Concienciar a los empleados y al público en general sobre ciberseguridad es crucial. Aunque las tecnologías avanzadas son importantes, sin una adecuada capacitación y concienciación, las medidas de seguridad pueden fallar.

**Estudios sobre concienciación en ciberseguridad:**

- Un estudio realizado por Proofpoint mostró una reducción del 90% en los ataques de phishing en una universidad del noroeste de Estados Unidos gracias a la concienciación.
- Empleados gubernamentales de una ciudad redujeron la tasa de clics en enlaces sospechosos en un 80% en un año.
- Una entidad financiera reportó una reducción del 95% en incidentes de malware durante dos años tras implementar programas de concienciación.

Para más información sobre la importancia de la concienciación en ciberseguridad, puedes leer este [artículo](https://www.proofpoint.com/us/resources/white-papers/cybersecurity-awareness-training-report).

### Recuerda: La seguridad empieza contigo

- La información es valiosa y protegerla es responsabilidad de todos. No subestimes los riesgos y siempre actúa con precaución.

## ¿Qué es el Phishing?

El phishing es un ataque basado en la suplantación de identidad que utiliza técnicas de ingeniería social para engañar a los usuarios y hacer que caigan en la trampa. Este tipo de ataque es uno de los más comunes hoy en día, especialmente a nivel doméstico, ya que no requiere conocimientos técnicos avanzados para ser ejecutado. Esta facilidad de realización aumenta la cantidad de personas afectadas, en gran parte debido a la falta de concienciación en materia de ciberseguridad.

En este curso, aprenderemos a detectar manual y automáticamente estos ataques para mejorar la seguridad de nuestra información. Primero, veamos algunos aspectos fundamentales del phishing:

### Tipos de Phishing

#### Por Alcance

1. **Phishing general**: Suplantaciones de identidad enviadas a un gran número de usuarios sin personalización. Un ejemplo común es un ciberdelincuente que se hace pasar por un banco y envía correos masivos a usuarios, independientemente de si son clientes de ese banco o no.

2. **Spear phishing**: Ataques dirigidos a un usuario o grupo específico, donde los ciberdelincuentes han investigado previamente para personalizar el mensaje y aumentar las probabilidades de éxito. Más información sobre [spear phishing](https://www.kaspersky.com/resource-center/definitions/spear-phishing).

3. **Whaling**: Similar al spear phishing, pero dirigido a personas influyentes o altos directivos de empresas. Para entender mejor este tipo de ataque, puedes leer este [artículo sobre whaling](https://us.norton.com/internetsecurity-emerging-threats-what-is-whaling.html).

#### Por Medio de Comunicación

1. **Email phishing**: Suplantación de identidad enviada a través de correos electrónicos. Es uno de los métodos más tradicionales y comunes. [Más información sobre email phishing](https://www.phishing.org/what-is-phishing).

2. **Vishing**: Suplantación de identidad a través de llamadas telefónicas. [Aprende más sobre vishing](https://www.spamfighter.com/SLOW-PCfighter/Learn-More/Vishing.asp).

3. **Smishing**: Suplantación de identidad mediante mensajes de texto. [Descubre más sobre smishing](https://www.fcc.gov/smishing-sms-phishing).

4. **QRishing**: Suplantación de identidad a través de códigos QR. Este método utiliza códigos QR maliciosos para dirigir a los usuarios a sitios web falsos. Para más detalles, consulta este [artículo sobre QRishing](https://www.forbes.com/sites/forbestechcouncil/2022/06/09/qrishing-the-new-phishing-threat-with-qr-codes/).

### Cómo Protegerse del Phishing

Para protegerse de estos engaños, es fundamental entender que los ataques de phishing suelen explotar nuestros sesgos cognitivos y emociones. Aquí tienes algunos consejos prácticos:

1. **Razonamiento y sentido común**: Antes de actuar, tómate un momento para pensar. Si algo parece sospechoso, probablemente lo sea.

2. **Ortografía y coherencia**: Los mensajes fraudulentos suelen tener errores ortográficos y de coherencia. Una entidad seria es poco probable que cometa estos errores.

3. **Forma de dirigirse a ti**: Los mensajes genéricos que no usan tu nombre, sino términos como "Estimado usuario" o "Sr./Sra.", son sospechosos. No obstante, esto no es una regla absoluta, solo un indicio.

4. **Dirección del remitente**: Revisa la dirección del correo electrónico del remitente. Si la dirección no coincide con el dominio oficial de la entidad (por ejemplo, un correo de Apple que proviene de un dominio de Hotmail), es motivo de sospecha. Sin embargo, ten en cuenta que los ciberdelincuentes pueden falsificar direcciones de remitentes.

5. **Distribución y formato**: Compara el mensaje con correos anteriores de la entidad. Fíjate en la firma, los colores y la estructura del mensaje.

6. **Hiperenlaces adjuntos**: Pasa el cursor sobre los enlaces para ver la URL de destino sin hacer clic. Herramientas como [VirusTotal](https://www.virustotal.com/gui/home/url) pueden ayudarte a verificar si un enlace es malicioso.

### Ejemplo Práctico

Recientemente recibí un mensaje que supuestamente era del Banco Santander, informándome de una actividad sospechosa en mi cuenta. Como no soy cliente de este banco, supe que era un intento de phishing. Reporté el mensaje al banco para ayudar a prevenir que otros usuarios cayeran en la trampa. Siempre que recibas un mensaje sospechoso, repórtalo a la entidad legítima.

---

### Recursos Adicionales

1. [Phishing: Cómo protegerte](https://staysafeonline.org/stay-safe-online/online-safety-basics/avoid-phishing-scams/)
2. [Guía de seguridad en internet](https://www.consumer.ftc.gov/articles/how-recognize-and-avoid-phishing-scams)
3. [Ingeniería social y ciberseguridad](https://www.csoonline.com/article/3251416/what-is-social-engineering.html)

---

Utiliza estos consejos y recursos para proteger tu información y estar más seguro en línea. 

## ¿Qué es la Autenticación por Múltiples Factores (MFA)?

La autenticación por múltiples factores (MFA) es un conjunto de procesos diseñados para añadir capas adicionales de seguridad al acceder a un activo, como una cuenta en línea. Tradicionalmente, la contraseña ha sido el método más común y básico de protección, pero su uso exclusivo no garantiza una seguridad robusta. Esto se debe a prácticas inseguras como el uso de contraseñas débiles o la reutilización de contraseñas en varios servicios, lo que aumenta el riesgo de que las credenciales sean comprometidas.

### Factores de Autenticación

Los factores de autenticación en MFA se basan en tres categorías principales:

1. **Lo que el usuario sabe**: Este factor se refiere a la información que el usuario conoce, como contraseñas o respuestas a preguntas de seguridad.

2. **Lo que el usuario tiene**: Incluye elementos físicos que el usuario posee, como dispositivos de autenticación (tarjetas inteligentes, dispositivos móviles) o códigos de un solo uso enviados a través de SMS o correo electrónico.

3. **Lo que el usuario es**: Este factor utiliza características biométricas únicas del usuario, como el reconocimiento facial, de huellas dactilares o de voz.

### Implementación de MFA

El método más conocido de MFA es la **verificación en dos pasos** (2FA), que combina dos de estos factores para verificar la identidad del usuario. Por ejemplo, después de ingresar correctamente el nombre de usuario y la contraseña, el sistema puede enviar un código de un solo uso al dispositivo móvil del usuario para ser ingresado como segunda capa de seguridad.

#### Ejemplos de Métodos de MFA:

- **Códigos de un solo uso**: Generados dinámicamente y válidos por un corto período, enviados por SMS, correo electrónico o a través de aplicaciones de autenticación como [Google Authenticator](https://support.google.com/accounts/answer/1066447?hl=es).
  
- **Dispositivos de autenticación físicos**: Tarjetas inteligentes o llaveros USB que generan códigos de acceso únicos.

- **Biometría**: Utilización de rasgos físicos únicos para la autenticación, como el reconocimiento facial o de huellas dactilares.

### Mejorando la Seguridad con MFA

A pesar de la efectividad de MFA, existen riesgos como los ataques de phishing o la ingeniería social, que pueden comprometer incluso sistemas MFA. Por ello, es crucial implementar prácticas de seguridad adicionales:

- **Uso de contraseñas seguras**: Generar contraseñas robustas y únicas para cada servicio.
  
- **Educación en ciberseguridad**: Concienciar sobre los riesgos de seguridad y cómo detectar intentos de phishing u otros ataques.

### Recursos Adicionales

1. [Cómo activar la verificación en dos pasos](https://www.consumer.ftc.gov/articles/how-enable-two-factor-authentication)
   
2. [Seguridad en el uso de contraseñas](https://www.cyberaware.gov.uk/passwords)

3. [Tipos de dispositivos de autenticación](https://www.cnet.com/tech/computing/the-best-two-factor-authentication/)

Implementar MFA y prácticas de seguridad sólidas es crucial para proteger tus activos en línea. Cada capa adicional de seguridad contribuye significativamente a mitigar riesgos y mantener la integridad de la información. Nos vemos en la próxima lección.

## ¿Qué es una VPN?

Una VPN, o Virtual Private Network (Red Virtual Privada), busca expandir una red local de manera virtual. Aunque se utiliza ampliamente en entornos empresariales, hoy en día muchos proveedores ofrecen VPNs también para usuarios domésticos y no técnicos. Las VPNs son frecuentemente recomendadas por creadores de contenido como una medida para mejorar la privacidad y seguridad en línea, aunque entender cómo funcionan puede parecer complejo.

### Funcionamiento Básico

Cuando te conectas a internet normalmente, tu dispositivo envía peticiones directamente a través de tu proveedor de servicios de internet (ISP). Sin embargo, al usar una VPN, estas peticiones pasan primero por un servidor VPN antes de llegar a internet. Esto significa que tu dirección IP pública cambia, proporcionando cierta privacidad y permitiéndote acceder a contenido que puede estar geográficamente restringido.

### Ejemplo de Uso

Por ejemplo, si deseas acceder a contenido que solo está disponible en los Estados Unidos pero te encuentras en México, puedes usar una VPN con servidores en EE.UU. Esto hará que parezca que tu conexión proviene de EE.UU., permitiéndote visualizar el contenido deseado.

### Consideraciones de Privacidad y Seguridad

- **Privacidad**: Una VPN cambia tu dirección IP pública, lo cual ayuda a proteger tu identidad en línea. Sin embargo, no garantiza anonimato completo debido a otros datos como el agente de usuario HTTP que también pueden identificar tu dispositivo.
  
- **Seguridad**: La mayoría de las VPNs cifran el tráfico, lo que significa que si un ciberdelincuente intercepta los datos, no podrá leerlos fácilmente. Sin embargo, no todas las VPNs ofrecen cifrado, por lo que es importante elegir un proveedor confiable y revisar sus políticas de seguridad.

### Consejos al Elegir una VPN

1. **Reputación del Proveedor**: Busca opiniones y referencias sobre el proveedor antes de adquirir su servicio.
   
2. **Cifrado de Datos**: Asegúrate de que la VPN que elijas cifre tu información de manera efectiva.

### Legalidad y Uso de VPNs

El uso de VPNs está permitido en la mayoría de los países, aunque algunos lugares tienen restricciones específicas. Es importante verificar las regulaciones locales antes de utilizar una VPN.

### Evitar VPNs Gratuitas

Evita usar VPNs gratuitas, ya que pueden comprometer tu seguridad y privacidad al vender tus datos o usar prácticas no transparentes. Es preferible invertir en un servicio de calidad y confiable.

### Recursos Adicionales

1. [Recomendaciones de seguridad en el empleo de redes VPN | Empresas | INCIBE](https://www.incibe.es/empresas/blog/recomendaciones-seguridad-el-empleo-redes-vpn)
2. [Teletrabajo: VPN y otras recomendaciones | INCIBE-CERT | INCIBE](https://www.incibe.es/incibe-cert/blog/teletrabajo-vpn-y-otras-recomendaciones)

El uso de una VPN puede mejorar tu privacidad y seguridad en línea, pero es importante entender sus limitaciones y asegurarte de elegir un servicio confiable. Si tienes más preguntas o deseas aprender más, ¡no dudes en explorar los enlaces proporcionados!

## No te Conectes a Redes Wi-Fi Públicas

Imagina un mundo donde siempre tienes acceso gratuito y seguro a internet de alta velocidad en cualquier lugar. Lamentablemente, eso no existe en la realidad. Las redes Wi-Fi públicas son una de las principales vulnerabilidades que los ciberdelincuentes explotan para comprometer la seguridad de los usuarios.

### Riesgos de las Redes Wi-Fi Públicas

Las redes Wi-Fi públicas son accesibles para cualquier usuario, lo que significa que todos los dispositivos en esa red pueden ser visibles entre sí. Esto abre la puerta a varios tipos de ataques:

- **Suplantación de Red (Evil Twin)**: Los ciberdelincuentes crean redes Wi-Fi falsas con nombres similares a las redes legítimas, tanto públicas como protegidas con contraseña. Esto engaña a los usuarios para que se conecten a la red falsa, permitiendo a los atacantes interceptar datos sensibles.

- **Riesgos de Seguridad**: Incluso en redes Wi-Fi protegidas con contraseña, los ciberdelincuentes pueden ejecutar ataques como el robo de información personal o la propagación de malware.

### Protección con VPNs

Si te ves obligado a utilizar redes Wi-Fi públicas, una VPN (Virtual Private Network) puede proporcionar una capa adicional de seguridad cifrando tu tráfico de internet. Aunque no garantiza seguridad al 100%, una VPN puede reducir algunos riesgos significativamente.

### Consejos de Seguridad

- **Sentido Común**: Evita conectarte a redes Wi-Fi públicas siempre que sea posible, especialmente para transacciones financieras o acceso a información sensible.
  
- **Uso de VPN**: Si es necesario utilizar redes Wi-Fi públicas, asegúrate de configurar y activar una VPN confiable para proteger tus datos.

### Recursos Adicionales

1. [Consejos para Seguridad en Redes Públicas](https://www.consumer.ftc.gov/articles/0014-tips-using-public-wi-fi-networks)
   

### Conclusiones

En resumen, las redes Wi-Fi públicas son inherentemente inseguras y sujetas a diversos riesgos. Utilizar una VPN puede mitigar algunos de estos riesgos, pero siempre es mejor evitar estas redes cuando sea posible y optar por conexiones más seguras y confiables.


## Detectar Phishing de Forma Automatizada

En la era digital, es crucial identificar y evitar el phishing, un método comúnmente usado por ciberdelincuentes para suplantar identidades y obtener información confidencial. Existen varias herramientas en línea que permiten analizar URLs para determinar si conducen a recursos maliciosos.

### Herramientas de Análisis

**1. VirusTotal**: Este portal combina múltiples motores de detección y antivirus para analizar URLs y archivos en busca de amenazas. No es un antivirus en sí mismo, pero ofrece un análisis centralizado que puede revelar la legitimidad de un recurso digital. [Visita VirusTotal](https://www.virustotal.com/)

**2. URLVoid**: Especializado en la detección de sitios web fraudulentos y suplantación de identidad, URLVoid proporciona información detallada sobre la reputación de una URL específica. [Visita URLVoid](https://www.urlvoid.com/)

**3. PhishTank**: Mantenido por la comunidad y enfocado exclusivamente en phishing, PhishTank identifica URLs maliciosas y permite a los usuarios contribuir con información sobre sitios de phishing conocidos. [Visita PhishTank](https://www.phishtank.com/)

**4. Cisco Talos**: Orientado principalmente hacia la inteligencia de amenazas, Talos también ofrece una perspectiva sobre la reputación de una URL en términos de seguridad cibernética. [Visita Cisco Talos](https://talosintelligence.com/)

### Ejemplo de Uso

Para ilustrar cómo funcionan estas herramientas, consideremos un ejemplo con dos tipos de URLs:

- **URL Legítima**: Utilizaremos "google.com" como ejemplo evidente de un sitio web legítimo. Al analizarlo en VirusTotal, URLVoid, PhishTank y Talos, todas las herramientas confirmarán su legitimidad y seguridad.

- **URL Maliciosa**: Usaremos una URL que conduce a un sitio de phishing. Al analizar esta URL en las herramientas mencionadas, veremos que todas indican una alta probabilidad de phishing o actividad maliciosa.

### Verificación de Códigos QR

Además de las URLs, es importante verificar la legitimidad de la información codificada en los códigos QR antes de escanearlos. Puedes usar herramientas en línea como "QR Code Monkey" para generar y "QR Code Reader" para escanear y verificar la URL codificada antes de acceder a ella.

### Protege Tu Información

Es fundamental adoptar estos métodos simples pero efectivos para proteger tus datos personales y financieros en línea. La conciencia y el uso de herramientas adecuadas pueden marcar la diferencia en la prevención del phishing y otros ataques cibernéticos.



#Básicos #VPN

---

- [Discord](https://discord.com/), comunidad **Call Security**

- [Cómo poner el candado verde](https://jesusyesares.com/off-topic/como-poner-el-candado-verde/)

- [Aprende cómo saber si tu dispositivo está infectado](https://sensorstechforum.es/como-saber-si-tengo-un-virus-en-el-pendrive/)
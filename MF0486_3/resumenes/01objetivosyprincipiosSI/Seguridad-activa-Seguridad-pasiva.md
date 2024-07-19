---
theme: default
header: "CIBERSEGURIDAD 2024"
footer: i.bernárdez
paginate: true
style: |
        h1{ font-weight: 100; font-size: 4rem; line-height: .8; background: -webkit-linear-gradient(#a0f, #a40);   -webkit-background-clip: text; -webkit-text-fill-color: transparent;}
        h2 { font-size: 2.8rem; font-weight: 300;}
        h3 { font-size: 2.3rem; font-weight: 300;}
        h4 { font-size: 2rem; font-weight: 300;}
        .columns { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 1rem;}

marp: true
---

# Seguridad activa y pasiva en informática: qué son y cuáles son sus diferencias

---

Los ataques informáticos son cada vez más frecuentes. Ni usuarios ni empresas estamos libres de sufrir un ataque informático o sufrir los efectos de una brecha de seguridad. De ahí que cada vez sean más importantes las medidas de control y seguridad para dispositivos, redes y datos.

---

Según el [Sistema Estadístico de Criminalidad (SEC)](https://www.interior.gob.es/opencms/export/sites/default/.galleries/galeria-de-prensa/documentos-y-multimedia/balances-e-informes/2022/Informe-Cibercriminalidad-2022.pdf), **España registró más de 374.737 delitos informáticos en 2022**, lo que supone un incremento del 22,86% respecto al año anterior.

El informe [X-Force Threat Intelligence Index 2024](https://www.ibm.com/es-es/reports/threat-intelligence?adoper=241753_1_PB1), registró un aumento del 71% de los ciberataques cuyo objetivo es la explotación de la identidad digital de los usuarios en 2023 frente a 2022. (*Fuente: https://www.ibm.com/*)

---

La seguridad informática se ha convertido en uno de los mayores problemas a los que nos enfrentamos en este momento. ¿Quién no tiene un ordenador, una tablet o un smartphone conectado a Internet? 

---

Según el informe presentado por Cisco el 17 de mayo de 2023, coincidiendo con la celebración del **Día mundial de Internet**, ese año se alcanzaría la cifra de unos **29.300 millones de dispositivos electrónicos conectados a Internet** en el mundo, y la mitad de ellos serán objetos del Internet de las Cosas (IoT).

---

Podemos decir con rotundidad y sin miedo a equivocarnos que hoy en día **la mayoría de nuestros datos están online.** Registros, información, sistemas, facturas, bases de datos, accesos, datos bancarios… todo se encuentra almacenado en algún tipo de sistema informático, de empresas, organizaciones o dispositivos conectados de los propios usuarios.

---

## ¿Qué es la seguridad informática?

---

**La seguridad informática es el conjunto de medidas y procedimientos que se toman para proteger los sistemas informáticos de posibles ataques y daños causados de forma intencionada o no intencionada.** Estos ataques pueden ser tanto contra el hardware, o soporte físico, como contra el software, los programas y aplicaciones que hacen que todo funcione correctamente.

---

Estamos viviendo un momento en el que todo está conectado y en el que el comercio, las transacciones financieras o el teletrabajo son cada vez más frecuentes. Por lo tanto, aumentan las amenazas que se pueden recibir en todos los sistemas informáticos que usamos en nuestra vida diaria. **Para defendernos de estos ataques y garantizar la seguridad contamos con distintos métodos que se suelen clasificar en: seguridad activa y seguridad pasiva**.

---

## ¿Por que es importante implementar medidas de ciberseguridad?

---

### Protección de datos sensibles
La información personal, financiera y empresarial se almacena en línea y, sin las medidas de seguridad adecuada, puede ser robada, modificada, borrada o comprometida.

---

### Evitar pérdidas económicas
Un ciberataque puede resultar en daños financieros. Esto incluye gastos para remediar el ataque, pérdida de ingresos debido a la interrupción del negocio y posibles demandas de clientes o socios afectados.

---

### Preservar la reputación 
Los hackeos exitosos pueden dañar la imagen de tu organización. Además, la confianza de los clientes puede ser difícil de recuperar y tener un impacto duradero.

---

### Continuidad del negocio 
La ciberseguridad facilita que tu servicio continúe prestándose sin interrupciones graves, incluso en medio de amenazas cibernéticas. Esto es esencial para la estabilidad y el éxito a largo plazo.

---

### Cumplimiento legal 
En último lugar, pero no menos importante, ha de tenerse en cuenta que la normativa de protección de datos requiere que las organizaciones protejan la información de sus clientes. Su incumplimiento puede dar lugar a sanciones significativas.

---

![bg left Formas de ciberseguridad informática](./assets/ciberseguridad-00.jpg)

Para proteger toda nuestra información de las amenazas a las que nos enfrentamos cada día existen múltiples herramientas y estrategias que podemos clasificar en dos grupos principales:

- herramientas y estrategias de **seguridad activa**, y
- herramientas y estrategias de **seguridad pasiva.**

---

Tanto unas como otras son formas de **ciberseguridad** informática que nos ayudan a mantener todo en orden y a salvaguardar nuestros datos.

La principal diferencia radica en el momento en que entran en acción:

- **Seguridad activa:** Busca prevenir e identificar las amenazas antes de que causen daño para evitar que se materialicen en una intrusión o ataque. Por tanto, tiene carácter proactivo.
- **Seguridad pasiva:** Se implementa a largo plazo para minimizar el impacto de un incidente de seguridad una vez que ha ocurrido. 

---

Ambos tipos de medidas son complementarios y necesarios para una estrategia de ciberseguridad sólida. Así, **la seguridad activa protege contra las amenazas en curso**, mientras que **la seguridad pasiva garantiza la recuperación y la continuidad de las operaciones** en caso de un incidente.

---

### ¿Qué es la seguridad informática activa?

---

La **seguridad activa es aquella que está destinada a evitar posibles daños informáticos.** Su objetivo principal es prevenir cualquier tipo de ataque antes de que suceda. Tiene, por tanto, un carácter proactivo. Consiste en realizar una serie de procedimientos de forma habitual para evitar que se produzca cualquier tipo de ataque.

---

### ¿Qué es la seguridad<br> informática pasiva?

---

La **seguridad pasiva es la que se destina a solucionar o minimizar los efectos provocados por un ataque informático una vez que este ya se ha producido.** Es un tipo de [seguridad reactiva](https://asana.com/es/resources/incident-management). Puede ser provocado por un ataque intencionado o por un accidente e implica una serie de prácticas destinadas a retomar la normalidad.

---

### Diferencia entre seguridad activa y pasiva en informática

La diferencia básica entre seguridad pactiva y seguridad pasiva es que **la seguridad activa funciona como método de prevención**, mientras que **la seguridad pasiva se pone en marcha una vez que se ha producido alguna alteración informática.** En el caso de la primera encontramos una serie de acciones destinadas a proteger los sistemas informáticos, pero, en la pasiva, se busca solucionar con la máxima rapidez los daños que ya se han producido.

---

### Medidas de seguridad activa

Para evitar que nuestros sistemas informáticos sufran ataques, los profesionales en ciberseguridad ponen en marcha una serie de **medidas de seguridad activa** como:

---

- **Usar contraseñas seguras y cambiarlas cada cierto tiempo:** es imprescindible para la seguridad digital. Nada de poner el nombre del perro o la fecha de nacimiento; lo ideal es mezclar números, letras, diferentes caracteres y mayúsculas y minúsculas.

---

- **Instalar softwares de protección, firewalls y antivirus:** son una barrera importantísima para frenar cualquier tipo de ataque.

---

- **Actualizar de forma constante todos los programas:** tanto herramientas, como antivirus como de cualquier tipo para evitar brechas por las que puedan colarse.

---

- **Encriptar los datos importantes:** de esta manera no serán tan accesibles para los posibles hackers y estarán ocultos de las intrusiones informáticas.

---

- **Formación y concienciación:** La formación en seguridad cibernética para empleados es crucial. Gracias a ella, los trabajadores son menos propensos a caer en trampas de phishing o cometer errores que puedan comprometer la seguridad. Con la colaboración de todos los miembros de la organización es más fácil lograr una protección más efectiva. Es recomendable, por tanto, impartir formación básica para todos los nuevos empleados.

---

- **Monitorización de eventos:** Los sistemas de detección de intrusiones monitorean constantemente la red en busca de actividades sospechosas. Si detectan algo inusual, como un intento de acceso no autorizado, se generan alertas para que podamos actuar de inmediato.

---

- **Escáner de vulnerabilidades:** Se identifican los puntos débiles de la configuración de seguridad de un equipo y se crean parches para los agujeros de seguridad detectados.

---

- **Auditorías de seguridad:** Se evalúan las medidas de seguridad implementadas para identificar posibles vulnerabilidades, riesgos y deficiencias en la seguridad, así como priorizar posibles necesidades. De esta manera, podemos incrementar su efectividad y garantizar la protección de la información.

---

### Medidas de seguridad pasiva

Las **medidas de seguridad pasiva** están destinadas a solucionar cuanto antes los ataques informáticos que ya se han producido y poner en marcha todos los mecanismos necesarios para recuperar la normalidad en el menor plazo de tiempo posible. Algunas de las más frecuentes son:

---

- **Escanear y desinfectar dispositivos**: todos los equipos informáticos que se hayan visto afectados o comprometidos por una intromisión en la seguridad.

---

- **Recuperar copias de seguridad o** ***backups*** más recientes con toda la información guardada y en buen estado.
Es recomendable, por tanto, realizar copias de seguridad periódicas de los datos críticos es fundamental. Así, si se produce un ataque o una pérdida de información, podemos restaurarlos fácilmente.

---

- **Realizar particiones de discos duros** para almacenar las copias de seguridad y evitar que el malware se extienda a más equipos.

---

- **Usar algún almacenamiento en la nube:** es sencillo, barato y puede salvarnos la vida ante un ataque contra nuestros sistemas.

---

- **Análisis forenses:** La realización de estos análisis consiste en la revisión de información relevante de los equipos comprometidos, como los logs o la memoria. Así, podemos identificar el alcance del incidente y dar con posibles soluciones, descubrir las estrategías, herramientas o brechas de seguridad que permitieron la consumación del ataque y determinar medidas para evitar que pueda volver a ocurrir.

---

![bg 90%](./assets/incident-management.png)

---

## ¿Quién se encarga de la ciberseguridad en las empresas?

---

Estamos viendo que tanto la ***seguridad activa*** como la **seguridad pasiva** en informática son imprescindibles, tanto par empresas como para particulares.

Para encargarse de esto han surgido diversos perfiles que **trabajan en ciberseguridad** para todo tipo de empresas y organizaciones. Tres de los perfiles más importantes son el CSO (Chief Security Officer), el CISO (Chief Information Security Officer) y el auditor de seguridad informática, que se han convertido en pilares de la seguridad de la información empresarial.

---

COIRO XUÑ.2024
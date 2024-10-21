

# OwaspZap

OWASP ZAP es una herramienta esencial en el arsenal de cualquier especialista en seguridad de aplicaciones web. Su facilidad de uso, junto con su poder y capacidad de personalización, lo convierten en una excelente opción para identificar y mitigar vulnerabilidades en aplicaciones web, sin importar el nivel de experiencia del usuario.

### OWASP ZAP: Un Proxy para la seguridad de aplicaciones web

- **ZAP actúa como un proxy entre el navegador y la red**, interceptando y analizando el tráfico HTTP(S) para identificar vulnerabilidades de seguridad en aplicaciones web. A medida que un usuario interactúa con una página web, **ZAP detecta posibles problemas de seguridad y genera informes detallados para el usuario final**.
  
- **ZAP es de código abierto y completamente gratuito**, lo que lo convierte en una herramienta accesible tanto para profesionales de la ciberseguridad como para aficionados. Es mantenido por la comunidad de OWASP (Open Web Application Security Project), lo que asegura que esté en constante evolución y actualización para enfrentar nuevas amenazas.

- **Multiplataforma**: ZAP está disponible para **Windows, Linux y Mac**, permitiendo a los usuarios de diferentes entornos operar sin limitaciones.

- **Fácil de usar para principiantes**: A pesar de su robustez y capacidad avanzada, ZAP es intuitivo y ofrece una interfaz amigable para usuarios que están comenzando en el campo del pentesting o pruebas de seguridad en aplicaciones web. Además, tiene guías y tutoriales disponibles, lo que facilita su adopción.

---

### Documentación y recursos de Interés

Para aprovechar al máximo OWASP ZAP, aquí tienes algunos recursos útiles:

1. **[OWASP ZAP Sitio Oficial](https://www.zaproxy.org/)**
   - Página oficial de OWASP ZAP con descargas, guías de usuario y enlaces a la comunidad.
   
2. **[Guía Rápida de OWASP ZAP](https://www.zaproxy.org/getting-started/)**
   - Instrucciones detalladas para la instalación y uso de OWASP ZAP para principiantes.

3. **[ZAP Marketplace](https://www.zaproxy.org/addons/)**
   - Extensiones adicionales que pueden mejorar la funcionalidad de ZAP, disponibles en el marketplace de ZAP.

4. **[Documentación de OWASP ZAP en GitHub](https://github.com/zaproxy/zaproxy/wiki)**
   - Wiki oficial donde se encuentra información técnica y guías de configuración para usuarios más avanzados.

5. **[OWASP Top 10 Vulnerabilidades](https://owasp.org/www-project-top-ten/)**
   - Lista de las principales vulnerabilidades en aplicaciones web, que ZAP está diseñado para detectar y reportar.

---

### ZAP Proxy

OwaspZap (o Zap Proxy) es una herramienta que permite escanear servidores web y comprobar si existe algún tipo de fallo de seguridad conocido.

Cuando inicie ZAP por primera vez, la herramienta preguntará si deseas mantener la sesión de ZAP. De forma predeterminada, las sesiones ZAP siempre se graban en el disco en una base de datos HSQLDB con un nombre y una ubicación predeterminados. Si la sesión no persiste, esos archivos se eliminarán al cerrar la sesión.

Si eliges mantener una sesión, la información de la sesión se guardará en la base de datos local para que pueda acceder a ella más tarde. También podrá proporcionar nombres personalizados y ubicaciones para guardar los archivos.

![img](./assets/SCiAYE8UTVaNNSVY8ij3_guardar11.png)

Por ahora, seleccione “No”, no quiero persistir en esta sesión en este momento. Luego haga clic en Iniciar. Las sesiones de ZAP no se mantendrán por ahora.

**Interfaz de usuario de escritorio ZAP**

La interfaz de usuario de ZAP Desktop se compone de los siguientes elementos:

- Barra de menú: Brinda acceso a muchas de las herramientas automáticas y manuales.
- Barra de herramientas: Incluye botones que facilitan el acceso a las funciones más utilizadas.
- Ventana de árbol: Muestra el árbol de Sitios y el árbol de Scripts.
- Ventana del área de trabajo: Muestra solicitudes, respuestas y scripts y le permite editarlos.
- Ventana de información: Muestra detalles de las herramientas automáticas y manuales.

Pie de página: Muestra un resumen de las alertas encontradas y el estado de las principales herramientas automatizadas.

![img](./assets/NaALvoJLQsSJpLLGwmWt_guardar12.png)

**Ejecución de un escaneo automatizado**

La forma más sencilla de empezar a utilizar ZAP es a través de la pestaña Inicio rápido. Quick Start es un complemento de ZAP que se incluye automáticamente cuando instala ZAP.

**Para ejecutar un escaneo automatizado de inicio rápido:**

- Inicie ZAP y haga clic en la pestaña Inicio rápido de la ventana del área de trabajo.
- Haga clic en el botón grande de Escaneo automatizado.
- En el cuadro de texto URL para atacar, ingrese la URL completa de la aplicación web que desea atacar.
- Haga clic en el ataque

![img](./assets/2owmZCHVSnKyNfYNFuCF_guardar13.png)

ZAP procederá a rastrear la aplicación web con su araña y escaneará pasivamente cada página que encuentre. Luego, ZAP utilizará el escáner activo para atacar todas las páginas, funcionalidades y parámetros descubiertos.

 

Además, ZAP proporciona 2 arañas para rastrear aplicaciones web, las cuales se pueden seleccionar desde esa misma pantalla.

 

La araña ZAP tradicional que descubre enlaces examinando el HTML en las respuestas de la aplicación web. Esta araña es rápida, pero no siempre es efectiva cuando se explora una aplicación web AJAX que genera enlaces usando JavaScript.

Para las aplicaciones AJAX, es probable que la araña AJAX de ZAP sea más eficaz. Esta araña explora la aplicación web invocando navegadores que luego siguen los enlaces que se han generado. La araña AJAX es más lenta que la araña tradicional y requiere una configuración adicional para su uso en un entorno "sin cabeza".

ZAP escaneará pasivamente todas las solicitudes y respuestas enviadas a través de él. Hasta ahora, ZAP solo ha realizado análisis pasivos de su aplicación web. El escaneo pasivo no cambia las respuestas de ninguna manera y se considera seguro. El escaneo también se realiza en un hilo de fondo para no ralentizar la exploración. El escaneo pasivo es bueno para encontrar algunas vulnerabilidades y como una forma de tener una idea del estado de seguridad básico de una aplicación web y ubicar dónde se puede justificar una mayor investigación.

Sin embargo, el análisis activo intenta encontrar otras vulnerabilidades mediante ataques conocidos contra los objetivos seleccionados. El escaneo activo es un ataque real a esos objetivos y puede ponerlos en riesgo, así que no utilice el escaneo activo contra objetivos para los que no tiene permiso para probar.

**Ver alertas y detalles de alertas**

En el lado izquierdo del pie de página ZAP nos muestra un recuento de las alertas encontradas durante el testeo, desglosadas en categorías de riesgo, las cuales son:

![img](./assets/uNe1MUCvS0yTA2oynsSw_guardar14.png)

Para verlas solo debemos seguir los siguientes pasos:

- Hacer click en la pestaña “Alertas” en la ventana de información.
- Hacer click en cada alerta que se muestra en esa ventana para mostrar la URL y la vulnerabilidad detectada en el lado derecho de la Ventana de información.
- En las ventanas del área de trabajo, hacer click en la pestaña Respuesta para ver el contenido del encabezado y el cuerpo de la respuesta. Se resaltará la parte de la respuesta que generó la alerta.

 

**Generación de informes en ZAP**

Una vez que se realiza el escaneo activo, podemos generar informes. Para eso simplemente debemos hacer click en “OWASP ZAP” >> “Informe” >> “generar informes HTML” >> “ruta de archivo proporcionada” >> “informe de escaneo exportado”.

Y esto sería todo por el momento. Próximamente haremos un nuevo artículo en el cual explicaremos como explorar una aplicación manualmente, además de explicar algunas de las funciones avanzadas de esta herramienta.





---

**[Mikel Hernández Alonso](https://www.linkedin.com/in/mikel-hernandez-alonso-a3975b205/)**


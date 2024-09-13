# **Identificación de Hosts o Subdominios Usando DNS Fierce y TheHarvester**

En el ámbito de la ciberseguridad, es fundamental conocer todos los hosts o subdominios asociados con un dominio principal. Esta información es valiosa tanto para la protección de la infraestructura como para llevar a cabo pruebas de penetración. Dos herramientas muy útiles para esta tarea son **DNS Fierce** y **TheHarvester**.

### **DNS Fierce**

**DNS Fierce** es una herramienta diseñada para identificar subdominios y rangos de IPs asociados con un dominio. Es especialmente útil para encontrar hosts ocultos o subdominios que no están fácilmente visibles en registros DNS comunes.

#### **Funcionalidades Principales**:
- **Brute Force**: DNS Fierce realiza un ataque de fuerza bruta para identificar subdominios, utilizando un diccionario predefinido de nombres comunes.
- **Recursión de DNS**: La herramienta también intenta resolver los subdominios a través de servidores DNS para descubrir más información.
- **Tracing**: Realiza un seguimiento de las rutas de red (traceroute) hacia los subdominios descubiertos.

#### **Ejemplo de Uso**:

```bash
fierce -dns example.com
```

Este comando busca subdominios de "example.com" utilizando un ataque de fuerza bruta. DNS Fierce intentará resolver cada subdominio posible utilizando un diccionario de nombres comunes, como `www`, `mail`, `ftp`, etc.

#### **Casos de Uso**:
- **Reconocimiento en Pruebas de Penetración**: Durante una prueba de penetración, identificar todos los subdominios puede ayudar a encontrar puntos de entrada adicionales en una infraestructura.
- **Auditorías de Seguridad**: Las auditorías periódicas pueden descubrir subdominios no autorizados o mal configurados que podrían representar vulnerabilidades.

### **TheHarvester**

**TheHarvester** es una herramienta diseñada para recopilar información relacionada con dominios y subdominios, direcciones de correo electrónico, nombres de empleados, direcciones IP y más, utilizando motores de búsqueda y bases de datos públicas. 

#### **Funcionalidades Principales**:
- **Recopilación de Subdominios**: Usa fuentes como Bing, Google, y bases de datos de DNS para encontrar subdominios asociados con un dominio.
- **Recopilación de Correos Electrónicos**: Extrae direcciones de correo electrónico vinculadas a un dominio, lo que puede ser útil para identificar empleados o posibles objetivos de phishing.
- **Consulta de PGP y SHODAN**: Integra consultas a bases de datos como PGP y SHODAN para obtener información más profunda sobre los activos de red.

#### **Ejemplo de Uso**:

```bash
theharvester -d example.com -l 500 -b google
```

Este comando busca información relacionada con "example.com" usando Google como motor de búsqueda, limitando la búsqueda a 500 resultados.

#### **Casos de Uso**:
- **Inteligencia de Amenazas**: TheHarvester puede ayudar a recopilar información que podría ser utilizada en ataques dirigidos o para comprender mejor la superficie de ataque de una organización.
- **Preparación para Pruebas de Penetración**: Antes de realizar pruebas de penetración, es útil conocer todos los subdominios y posibles puntos de entrada, para asegurarse de cubrir todo el alcance.

### **Comparación y Mejores Prácticas**

- **Profundidad de Búsqueda**: DNS Fierce es más agresivo en la búsqueda de subdominios mediante ataques de fuerza bruta, mientras que TheHarvester se basa en fuentes abiertas y motores de búsqueda para obtener una visión más amplia y menos intrusiva.
- **Uso Combinado**: Para obtener una lista exhaustiva de subdominios y hosts, es recomendable usar ambas herramientas. DNS Fierce puede descubrir subdominios ocultos que no están indexados por motores de búsqueda, mientras que TheHarvester puede complementar con información adicional de correo electrónico y otros activos.

### **Recursos Adicionales**:

- [Repositorio de DNS Fierce en GitHub](https://github.com/mschwager/fierce): Para obtener el código fuente y documentación sobre DNS Fierce.
- [Repositorio de TheHarvester en GitHub](https://github.com/laramies/theHarvester): Para acceso al código fuente y documentación sobre TheHarvester.
- [Documentación de Kali Linux](https://www.kali.org/tools/theharvester/): La distribución Kali Linux incluye ambas herramientas, con instrucciones detalladas para su uso.

### **Conclusión**

Tanto DNS Fierce como TheHarvester son herramientas poderosas para la identificación de hosts y subdominios en un dominio objetivo. Usarlas juntas en un enfoque complementario puede proporcionar una visión más completa de los activos de red de una organización, lo cual es esencial tanto en la ciberseguridad defensiva como ofensiva.
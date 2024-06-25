# Markdown

## 1. Definición

> Markdown es una herramienta de conversión de texto a HTML para escritores web.

### 1.1 Qué es Markdown?

- Lenguaje de marcado ligera diseñada para facilitar la redacción y la lectura de texto plano que se puede convertir a HTML o a otros formatos y tipos de archivo - PDF, .docx,...
- Proporciona la capacidad de controlar el formato del documento mediante un proceso sencillo y directo.
- Permite crear documentos estructurados con poca sintaxis, lo que facilita su comprensión.

> *Se puede considerar Markdown como un método de escritura que permite añadir formatos como* **negrita**, *cursivas* o incluir [enlaces](https://bitsolto.com/markdown), tablas o imágenes, utilizando simple texto plano.*

### 1.2 Historia

- Creada por [John Gruber](https://daringfireball.net/projects/markdown/) en 2004 en colaboración con Aaron Swartz.
- Desarrollada para que los textos sean fácilmente legibles y publicables en formato HTML.
- Publicada bajo la licencia BSD.

### 1.3 Evolución e Crecimiento

- Con el tiempo, Markdown fue creciendo en capacidades y variantes para adaptarse a la escritura de los más variados tipos de documentos.
- Su simplicidad y versatilidad la hicieron popular entre desarrolladores, blogueros e escritores de documentación técnica.
- Diversas extensiones y *sabores* permiten incluir funcionalidades avanzadas sin perder su sencillez original.

## 2. Marcado

### 2.1 Títulos e cabeceras

- **Sintaxis:** `# Título 1`, `## Título 2`, `### Título 3`, etc.

- **Ejemplo:**

  ```markdown
  # Título 1
  ## Título 2
  ### Título 3
  ```

### 2.2 Párrafos y saltos de línea

- Los párrafos se crean con una o más líneas en blanco entre ellos.
- Saltos de línea con dos espacios al final de la línea.

### 2.3 Texto en énfasis

- **Negrita:** `**texto**` o `__texto__`
- **Cursiva:** `*texto*` o `_texto_`
- **Texto tachado:** `~~texto~~`

### 2.4 Listas

- **Listas no ordenadas:** `-`, `*`, `+`

  ```markdown
  - Elemento 1
  - Elemento 2
  ```

- **Listas ordenadas:** `1.`, `2.`

  ```markdown
  1. Elemento 1
  2. Elemento 2
  ```

### 2.5 Citas

- **Sintaxis:** `> cita`

  ```markdown
  > Esta es una cita.
  ```

### 2.6 Enlaces

- **Sintaxis:** `[texto](URL)`

  ```markdown
  [Google](https://www.google.com)
  ```

### 2.7 Imágenes

- **Sintaxis:** `![texto alternativo](URL)`

  ```markdown
  ![Logotipo de Markdown](https://markdown-here.com/img/icon256.png)
  ```

### 2.8 Código

- **Código en línea:** `` `código` ``

- **Bloques de código:** 
  Envuelve tu código entre comillas inversas. Permite indicar el lenguaje del código justo después de las tres primeras comillas inversas:

  \`\`\`javascript
      console.log('Esto es un bloque de código')
  \`\`\`

O resultado será este:

  ```js
console.log('Esto es un bloque de código')
  ```

### 2.9 Tablas

- **Sintaxis básica:**

  ```markdown
  | Cabecera 1 | Cabecera 2 |
  | ---------- | ---------- |
  | Celda 1    | Celda 2    |
  | Celda 3    | Celda 4    |
  ```

## 3. Variantes

Con el tiempo Markdown ha crecido en capacidades e *sabores* para adaptarse a la escritura de os más variados tipos de documentos y permitiendo incluir características avanzadas sin perder su sencillez original. 

### 3.1 CommonMark

- Un estándar moderno que define la sintaxis básica de Markdown de manera precisa y completa.

### 3.2 GitHub Flavored Markdown (GFM)

- Usada en GitHub con extensiones como tablas, listas de tareas y menciones de usuarios.

  ```markdown
  - [x] Tarea completada
  - [ ] Tarea pendiente
  ```

### 3.3 Markdown Extra

- Extensión que añade funcionalidades adicionales como tablas, definiciones de listas y atributos en HTML.

### 3.4 MultiMarkdown

- Añade características para publicaciones más avanzadas, como referencias cruzadas y notas al pie.

### 3.5 MarkdownHere

- Extensión del navegador que permite convertir texto Markdown a HTML en correos electrónicos.

## 4. Usos Comunes de Markdown

### 4.1 Blogs y Sitios Web

- Muchos sistemas de gestión de contenidos (CMS) permiten usar Markdown para redactar contenido.
- Plataformas como Jekyll y Hugo permiten crear sitios web estáticos con Markdown.

### 4.2 Documentación

- Ampliamente utilizado en documentación de proyectos de software, incluido repositorios de código en GitHub y GitLab.
- Herramientas como MkDocs y Sphinx permiten crear documentación en HTML a partir de archivos Markdown.

### 4.3 Notas y Gestión de Proyectos

- Aplicaciones como Notion, Obsidian o Trello permiten usar Markdown para crear y organizar notas y tareas.

### 4.4 Correos Electrónicos

- Extensiones como MarkdownHere permiten escribir correos electrónicos en Markdown y convertirlos a HTML.

## 5. Buenas Prácticas

### 5.1 Consistencia en la Sintaxis

- Usar la misma sintaxis para negrita, cursiva, etc., a lo largo del documento.

### 5.2 Límites de Línea

- Mantener líneas cortas (menos de 80 caracteres) para facilitar la lectura en texto plano.

### 5.3 Comentarios en Markdown

- Insertar comentarios que no se renderizan usando el típico marcado HTML:

  ```markdown
  <!-- Este es un comentario -->
  ```

## 6. Extensiones y Funcionalidades Avanzadas

Markdown, a lo largo de los años, fue ampliado con varias extensiones y funcionalidades avanzadas que permiten añadir características específicas para diferentes necesidades, manteniendo la sencillez del lenguaje original. A continuación, se exploran algunas de las extensiones y funcionalidades más populares:

### 6.1 GitHub Flavored Markdown (GFM)

- **Características:** 

  - Tablas, listas de tareas, menciones de usuarios, emoticonos y sombreado de sintaxis.
  - Extensión usada principalmente en GitHub para README.md e wikis.

- **Ejemplo:**

  ```markdown
  - [x] Tarea completada
  - [ ] Tarea pendente
  - @usuario mención
  ```

### 6.2 Markdown Extra

- **Características:**

  - Extensión que añade soportes para tablas, listas de definición, notas al pie, atributos en HTML y bloques de código resaltado.

- **Ejemplo:**

  ```markdown
  | Columna1 | Columna2 |
  | -------- | -------- |
  |  Celda1  |  Celda2  |
  
  Término
  : Definición del término
  
  <div id="div-id" class="div-class">
    Contenido HTML adicional
  </div>
  ```

### 6.3 MultiMarkdown

- **Características:**

  - Añade características como referencias cruzadas, notas al pie, citas bibliográficas y matemáticas.

- **Ejemplo:**

  ```markdown
  Esta es una referencia cruzada [Capítulo 1](#capitulo-1).
  
  Esta es una nota al pie [^1].
  
  [^1]: Texto de la nota al pie.
  ```

### 6.4 MarkdownHere

- **Características:**

  - Extensión para navegadores que permite escribir correos electrónicos en Markdown y convertirlos a HTML al enviarlos.

- **Ejemplo:**

  ```markdown
  Markdown en tu correo electrónico. `Markdown Here` convierte esto en HTML.
  ```

### 6.5 MathJax

- **Características:**

  - Permite la inclusión de ecuaciones matemáticas complejas en documentos Markdown utilizando la sintaxis de LaTeX.

- **Ejemplo:**

  ```markdown
  Fórmula en línea: \( E = mc^2 \)
  
  Fórmula en bloque:
  $$
  E = mc^2
  $$
  ```

### 6.6 PlantUML

- **Características:**

  - Herramienta para crear diagramas utilizando texto plano. Puede integrarse con Markdown para incluir diagramas directamente en los documentos.

- **Ejemplo:**

  ```markdown
  ```plantuml
  @startuml
  Alice -> Bob: Solicitud
  Bob --> Alice: Respuesta
  @enduml
  ```

### 6.7 Diagramas Mermaid

- **Características:**

  - Similar a PlantUML, Mermaid permite la creación de diagramas de flujo, gráficos de Gantt, etc.

- **Ejemplo:**

  ```markdown
  ```mermaid
  graph TD;
      A-->B;
      A-->C;
      B-->D;
      C-->D;
  ```

### 6.8 Syntax Highlighting

- **Características:**

  - Permite el resaltado de sintaxis para múltiples lenguajes de programación en los bloques de código.

- **Ejemplo:**

  ```markdown
  ```python
  def ola_mundo():
      print("Ola, Mundo!")
  ```

### 6.9 Tocbot

- **Características:**

  - Herramienta para generar automáticamente una tabla de contenidos a partir de los títulos de un documento Markdown.

- **Ejemplo:**

  ```markdown
  <!-- TOC -->
  ## Sección 1
  ## Sección 2
  ```

### 6.10 KaTeX

- **Características:**

  - Similar a MathJax, KaTeX es otra biblioteca de renderizado de matemáticas que permite la inclusión de ecuaciones.

- **Ejemplo:**

  ```markdown
  Fórmula en bloque:
  $$
  \int_a^b f(x)dx
  $$
  ```

### Integraciones y Herramientas Complementarias

#### 6.11 Pandoc

- **Características:**

  - Herramienta de conversión de documentos que soporta Markdown y puede convertir entre múltiples formatos (HTML, PDF, DOCX, etc.).

- **Ejemplo:**

  ```bash
  pandoc documento.md -o documento.pdf
  ```

#### 6.12 MkDocs

- **Características:**

  - Herramienta para crear sitios de documentación a partir de arquivos Markdown.

- **Ejemplo:**

  ```markdown
  # Introdución
  
  Bienvenido a la documentación.
  ```

#### 6.13 Jekyll y Hugo

- **Características:**

  - Generadores de sitios estáticos que permiten crear blogs y sitios web utilizando Markdown para los contenidos.

- **Ejemplo:**

  ```markdown
  ---
  title: "Entrada de Blog"
  date: 2024-05-30
  ---
  # Bienvenido a mi blog
  ```

Estas extensiones y funcionalidades avanzadas permiten que Markdown sea una herramienta versátil y poderosa para la creación de documentos de diversos tipos, manteniendo la sencillez que le hizo tan popular.

## 7. Ejemplos de Uso en Contextos Reales

### 7.1 Repositorios en GitHub

- Ejemplos de ``README.md`` bien escritos y estructurados.
- Uso de Markdown en wikis de proyectos.

### 7.2 Blogs Personales

- Muchos blogueros usan Markdown para redactar contenido.

## 8. Herramientas y Extensiones

### 8.1 Editores y Herramientas

- **Editores en línea:** [Dillinger](https://dillinger.io), [StackEdit](https://stackedit.io).
- **Aplicaciones de escritorio:** [Typora](https://typora.io), [Visual Studio Code](https://code.visualstudio.com).
- **Extensiones de navegador:** [Markdown Here](https://markdown-here.com).
- **Plugins para Editores de Texto:** Plugins de [Markdown para Visual Studio Code](https://code.visualstudio.com/docs/languages/markdown), [Sublime Text](https://www.sublimetext.com), [Vim](https://www.freecodecamp.org/espanol/news/como-usar-vim-tutorial-para-principiantes/), etc.

### 8.2 Conversores

- Existen múltiples herramientas para convertir Markdown a otros formatos.
  - [Pandoc](https://pandoc.org).

## 9. Recursos Adicionales

### 9.1 Documentación y Tutoriales

- [Documentación](https://www.markdownguide.org)
- Guía de [CommonMark](https://commonmark.org/help/)
- [GitHub Flavored Markdown](https://docs.github.com/es/get-started/writing-on-github)

## 10. Ejercicios Prácticos

### 10.1 Redactar un Documento Simple

- Crear un documento Markdown con títulos, parágrafos, listas, enlaces e imagenes.
- Crear tu CV con Markdown

### 10.2 Crear una Tabla Compleja

- Crear una tabla con varias columnas y filas, incluyendo formatos de texto como negrita y cursiva.

### 10.3 Publicar un Blog con Markdown

- Publicar una entrada de blog usando una plataforma que soporte Markdown (por ejemplo, [Jekyll](https://jekyllrb.com) o [Hugo](https://gohugo.io), o también [Wordpress](https://wpengine.com/resources/using-markdown-wordpress/)).

### 10.4 Static Site Generators (SSG) y Markdown

Los generadores de sitios estáticos (Static Site Generators, SSG) permiten crear sitios web rápidos y seguros al precompilar todos los archivos del sitio en un servidor, lo que elimina la necesidad de procesar el contenido dinámico en tiempo real. Markdown es ampliamente utilizado en estos generadores debido a su sencillez y capacidad para convertir texto plano en HTML de forma eficiente. Aquí tienes una visión general de los SSG más populares y como funcionan con Markdown:

**Que es un Site Static Generator (SSG)?**

- Un SSG es una herramienta que convierte archivos de contenido (normalmente escritos en Markdown) y plantillas en archivos HTML estáticos listos para ser servidos en un servidor web.
- **Ventajas:**
  - **Rendimiento:** Los sitios estáticos cargan más rápido ya que no dependen de consultas a bases de datos o procesamiento en tiempo real.
  - **Seguridad:** Menos puntos de vulnerabilidad ya que non hay backend dinámico.
  - **Fácil de mantener:** Actualizaciones simplificadas y menos dependencias.

#### 10.4.1. Generadores de Sitios Estáticos Populares

##### 10.4.1.1 Jekyll

- **Características:**

  - Integración perfecta con GitHub Pages.
  - Soporte para Markdown y Liquid (lenguaje de plantillas).
  - Gran comunidad y multitud de plugins.

- **Ejemplo:**

  ```markdown
  ---
  layout: post
  title: "Mi primer post"
  ---
  # Hola, mundo!
  Este es mi primer post en Jekyll.
  ```

- **Configuración básica:**

  ```bash
  gem install jekyll bundler
  jekyll new mi-sitio
  cd mi-sitio
  bundle exec jekyll serve
  ```

##### 10.4.1.2 Hugo

- **Características:**

  - Conocido por su velocidad en la compilación de sitios.
  - Soporte para Markdown y  lenguaje de plantillas Go.
  - Extensa biblioteca de temas.

- **Ejemplo:**

  ```markdown
  ---
  title: "Mi primer post"
  date: 2024-05-30
  ---
  # Hola, mundo!
  Este es mi primer post en Hugo.
  ```

- **Configuración básica:**

  ```bash
  hugo new site mi-sitio
  cd mi-sitio
  hugo new posts/mi-primer-post.md
  hugo server
  ```

##### 10.4.1.3 Gatsby

- **Características:**

  - Construido sobre React, permite componentes reutilizables.
  - Soporte para Markdown a través de plugins como `gatsby-transformer-remark`.
  - Enfoque moderno con GraphQL para consultas de datos.

- **Ejemplo:**

  ```markdown
  ---
  title: "Mi primer post"
  date: "2024-05-30"
  ---
  # Hola, mundo!
  Este es mi primer post en Gatsby.
  ```

- **Configuración básica:**

  ```bash
  npx gatsby new mi-sitio
  cd mi-sitio
  npm install gatsby-transformer-remark
  gatsby develop
  ```

##### 10.4.1.4 Eleventy

- **Características:**

  - Flexibilidad para usar múltiples lenguajes de plantillas.
  - Soporte para Markdown.
  - SSG ligero con configuración mínima.

- **Ejemplo:**

  ```markdown
  ---
  title: "Mi primer post"
  date: 2024-05-30
  ---
  # Hola, mundo!
  Este es mi primer post en Eleventy.
  ```

- **Configuración básica:**

  ```bash
  npx @11ty/eleventy
  eleventy --serve
  ```

#### 10.4.2. Configuración de Proyectos con Markdown

##### 10.4.2.1 Estructura Típica de un Proyecto

- **Carpetas y archivos básicos:**
  - `_posts/` o `content/`: Contiene archivos Markdown para las entradas del blog.
  - `_layouts/` o `layouts/`: Plantillas HTML para el contenido.
  - `assets/` o `static/`: Imágenes, CSS, JavaScript y otros archivos estáticos.
  - `config.yml` o `config.toml`: Archivo de configuración do SSG.

##### 10.4.2.2 Integración de Markdown

- **Front Matter:**

  - Metadatos incluidos al comienzo de los archivos Markdown para definir configuración específica del contenido.

  - **Ejemplo:**

    ```markdown
    ---
    title: "Mi primer post"
    date: 2024-05-30
    tags: [introducción, ejemplo]
    ---
    ```

#### 10.4.3. Funcionalidades Avanzadas

##### 10.4.3.1 Plugins y Extensiones

- **Jekyll:**
  - `jekyll-paginate` para la paginación.
  - `jekyll-sitemap` para generar sitemaps automáticamente.
- **Hugo:**
  - `shortcodes` para crear componentes reutilizables.
  - `hugo-algolia` para integración con Algolia Search.
- **Gatsby:**
  - `gatsby-plugin-image` para optimización de imágenes.
  - `gatsby-source-filesystem` para fuentes de datos.
- **Eleventy:**
  - `eleventy-plugin-syntaxhighlight` para resaltado de sintaxis.
  - `eleventy-plugin-rss` para fuentes RSS.

##### 10.4.3.2 Funcionalidades específicas de Markdown

- **Tablas, listas de tareas, imágenes y enlaces:** 

  - Utilización de sintaxis específica para mejorar el contenido.

  - **Ejemplo:**

    ```markdown
    | Cabecera 1 | Cabecera 2 |
    | ---------- | ---------- |
    |  Celda 1   |  Celda 2   |
    
    - [x] Tarea completada
    - [ ] Tarea pendente
    
    ![Imagen de ejemplo](url_da_imaxe)
    ```

#### 10.4.4. Recursos Adicionales

##### 10.4.4.1 Documentación y Tutoriales

- **Jekyll:** [Documentación oficial](https://jekyllrb.com/docs/)
- **Hugo:** [Documentación oficial](https://gohugo.io/documentation/)
- **Gatsby:** [Documentación oficial](https://www.gatsbyjs.com/docs/)
- **Eleventy:** [Documentación oficial](https://www.11ty.dev/docs/)

##### 10.4.4.2 Comunidades e Foros

- **Stack Overflow:** Para resolver problemas y dudas.
- **GitHub:** Repositorios de Ejemplos e proyectos abiertos.
- **Foros específicos:** Discusiones en foros dedicados a cada SSG.

#### 10.4.5. Ejercicios Prácticos

##### 10.4.5.1 Crear un Blog con Jekyll

- Configurar un nuevo blog en GitHub Pages utilizando Jekyll.
- Crear entradas en Markdown y personalizar el tema.

##### 10.4.5.2 Crear un Portafolio con Hugo

- Configurar un nuevo sitio web con Hugo.
- Crear páginas de proyecto utilizando archivos Markdown.

##### 10.4.5.3 Crear un Sitio de Documentación con Gatsby

- Configurar un sitio de documentación utilizando Gatsby.
- Integrar Markdown para las páginas de documentación y personalizar el estilo.

##### 10.4.5.4 Crear un Sitio Personal con Eleventy

- Configurar un sitio web personal utilizando Eleventy.
- Crear entradas de blog e paginas en Markdown.

### A Importancia de Markdown en el Desarrollo e Producción de Contenidos Web Actual

En el mundo del desarrollo y producción de contenidos web actual, Markdown juega un papel fundamental al proporcionar una manera sencilla y eficiente de crear y dar formato al contenido para sitios web. Su importancia radica en su capacidad para simplificar el proceso de escritura y publicación de contenido, al mismo tiempo que permite una gran flexibilidad y potencialidades avanzadas.

#### Sencillez y Facilidad de Uso

Markdown destaca por su sencillez y facilidad de uso. Su sintaxis minimalista permite crear documentos estructurados con facilidad, sin la necesidad de aprender un lenguaje de marcado complejo. Esto hace que sea accesible para personas de todos los niveles de habilidad técnica.

#### Compatibilidad y Portabilidad

Otra ventaja importante de Markdown es su compatibilidad y portabilidad. Los documentos Markdown pueden ser convertidos fácilmente a HTML, lo que permite que el contenido creado con Markdown sea utilizado en cualquier sitio web o plataforma que soporte HTML. Además, muchas herramientas y plataformas populares, como GitHub, GitLab, Jekyll o Hugo, son compatibles con Markdown, lo que hace que sea ampliamente adoptado en la comunidad de desarrollo web.



#### Eficiencia y Productividad

El uso de Markdown también puede mejorar la eficiencia y productividad de los equipos de desarrollo y producción de contenidos. Al eliminar la necesidad de formatos complejos y procesos de edición laboriosos, Markdown permite que los equipos se concentren más en la creación de contenido de calidad y menos en los detalles técnicos de su formato.

#### Flexibilidad y Funcionalidades Avanzadas

A pesar de su sencillez, Markdown también ofrece una gran flexibilidad y potencialidades avanzadas. A través de extensiones y funcionalidades adicionales, como GitHub Flavored Markdown (GFM), Markdown Extra y MultiMarkdown, es posible incluir características avanzadas, como tablas, listas de tareas, menciones de usuarios, ecuaciones matemáticas y diagramas, sin perder la sencillez original del lenguaje.

#### Adopta la Práctica Recomendada

En resumen, Markdown es una herramienta poderosa y versátil que desempeña un papel crucial en el desarrollo y producción de contenidos web actual. Su sencillez, compatibilidad, eficiencia, flexibilidad y potencialidades avanzadas hacen de el una elección ideal para quien busca una manera fácil y eficaz de crear y dar formato al contenido para la web. Al adoptar Markdown como práctica recomendada, los equipos de desarrollo y producción de contenidos pueden mejorar su eficiencia y productividad, al mismo tiempo que ofrecen una mejor experiencia de usuario en sus sitios web.

---

Desarrollo de aplicaciones con tecnologías web<br>COIRO 2024

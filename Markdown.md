# Markdown

## 1. Definición

> Markdown é unha ferramenta de conversión de texto a HTML para escritores web.

### 1.1 Que é Markdown?
- Linguaxe de marcado lixeira deseñada para facilitar a redacción e lectura de texto plano que se pode converter a HTML ou a outros formatos e tipos de arquivo - PDF, .docx,...
- Proporciona a capacidade de controlar o formato do documento mediante un proceso sinxelo e directo.
- Permite crear documentos estruturados con pouca sintaxe, o que facilita a súa comprensión.

> *Se pode considerar Markdown coma un método de escritura que permite engadir formatos como* **negriña**, *cursivas* *ou incluír [enlaces](https://bitsolto.com/markdown) táboas ou imaxes, utilizando simple texto plano.*

### 1.2 Historia
- Creada por [John Gruber](https://daringfireball.net/projects/markdown/) en 2004 en colaboración con Aaron Swartz.
- Desenvolvida para que os textos sexan facilmente lexibles e publicables en formato HTML.
- Publicada baixo a licenza BSD.

### 1.3 Evolución e Crecemento

- Co tempo, Markdown foi medrando en capacidades e variantes para adaptarse á escritura dos máis variados tipos de documentos.
- A súa simplicidade e versatilidade fixérona popular entre desenvolvedores, blogueiros e escritores de documentación técnica.
- Diversas extensións e sabores permiten incluír funcionalidades avanzadas sen perder a súa sinxeleza orixinal.

## 2. Marcado
### 2.1 Títulos e cabeceiras
- **Sintaxe:** `# Título 1`, `## Título 2`, `### Título 3`, etc.
- **Exemplo:**
  ```markdown
  # Título 1
  ## Título 2
  ### Título 3
  ```

### 2.2 Parágrafos e saltos de liña
- Os parágrafos créanse con unha ou máis liñas en branco entre eles.
- Saltos de liña con dous espazos ao final da liña.

### 2.3 Texto en énfase
- **Negriña:** `**texto**` ou `__texto__`
- **Cursiva:** `*texto*` ou `_texto_`
- **Texto tachado:** `~~texto~~`

### 2.4 Listas
- **Listas non ordenadas:** `-`, `*`, `+`
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
- **Sintaxe:** `> cita`
  ```markdown
  > Esta é unha cita.
  ```

### 2.6 Enlaces
- **Sintaxe:** `[texto](URL)`
  ```markdown
  [Google](https://www.google.com)
  ```

### 2.7 Imaxes
- **Sintaxe:** `![texto alternativo](URL)`
  ```markdown
  ![Logo de Markdown](https://markdown-here.com/img/icon256.png)
  ```

### 2.8 Código
- **Código en liña:** `` `código` ``
- **Bloques de código:** 
   Envolve o teu código entre comiñas inversas. Permite indicar a linguaxe do código xusto despois das tres primeiras comiñas inversas:
  
  \`\`\`javascript
      console.log('Isto é un bloque de código')
  \`\`\`

O resultado será este:
  ```js
  console.log('Isto é un bloque de código')
  ```


### 2.9 Táboas
- **Sintaxe básica:**
  ```markdown
  | Cabeceira 1 | Cabeceira 2 |
  | ----------- | ----------- |
  | Cela 1      | Cela 2      |
  | Cela 3      | Cela 4      |
  ```

## 3. Variantes

Co tempo Markdown foi medrando en capacidades e sabores para adaptarse a escritura dos máis variados tipos de documentos e permitindo incluír características avanzadas sen perder a súa sinxeleza orixinal. 

### 3.1 CommonMark
- Un estándar moderno que define a sintaxe básica de Markdown de maneira precisa e completa.

### 3.2 GitHub Flavored Markdown (GFM)
- Usada en GitHub con extensións como táboas, listas de tarefas e mencións de usuarios.
  ```markdown
  - [x] Tarefa completada
  - [ ] Tarefa pendente
  ```

### 3.3 Markdown Extra
- Extensión que engade funcionalidades adicionais como táboas, definicións de listas e atributos en HTML.

### 3.4 MultiMarkdown
- Engade características para publicacións máis avanzadas, como referencias cruzadas e notas ao pé.

### 3.5 Markdown Here
- Extensión do navegador que permite converter texto Markdown a HTML en correos electrónicos.

## 4. Usos Comúns de Markdown
### 4.1 Blogs e Sitios Web
- Moitos sistemas de xestión de contidos (CMS) permiten usar Markdown para redactar contido.
- Plataformas como Jekyll e Hugo permiten crear sitios web estáticos con Markdown.

### 4.2 Documentación
- Amplamente utilizado en documentación de proxectos de software, incluíndo repositores de código en GitHub e GitLab.
- Ferramentas como MkDocs e Sphinx permiten crear documentación en HTML a partir de arquivos Markdown.

### 4.3 Notas e Xestión de Proxectos
- Aplicacións como Notion, Obsidian e Trello permiten usar Markdown para crear e organizar notas e tarefas.

### 4.4 Correos Electrónicos
- Extensións como Markdown Here permiten escribir correos electrónicos en Markdown e convertelos a HTML.

## 5. Boas Prácticas
### 5.1 Consistencia na Sintaxe
- Usar a mesma sintaxe para negriña, cursiva, etc., ao longo do documento.

### 5.2 Límites de Liña
- Manter liñas curtas (menos de 80 caracteres) para facilitar a lectura en texto plano.

### 5.3 Comentarios en Markdown
- Enxertar comentarios que non se renderizan usando o típico marcado HTML:
  ```markdown
  <!-- Este é un comentario -->
  ```

## 6. Extensións e Funcionalidades Avanzadas
Markdown, ao longo dos anos, foi ampliado con varias extensións e funcionalidades avanzadas que permiten engadir características específicas para diferentes necesidades, mantendo a sinxeleza da linguaxe orixinal. A continuación, explóranse algunhas das extensións e funcionalidades máis populares:

### 6.1 GitHub Flavored Markdown (GFM)
- **Características:** 
  - Taboas, listas de tarefas, mencións de usuarios, emoticonas e sombreado de sintaxe.
  - Extensión usada principalmente en GitHub para README.md e wikis.
- **Exemplo:**
  ```markdown
  - [x] Tarefa completada
  - [ ] Tarefa pendente
  - @usuario menciona
  ```

### 6.2 Markdown Extra
- **Características:**
  - Extensión que engade soportes para táboas, definicións de listas, notas ao pé, atributos en HTML e bloques de código resaltado.
- **Exemplo:**
  ```markdown
  Columna1 | Columna2
  -------- | --------
  Celda1   | Celda2
  
  Termo
  : Definición do termo
  
  <div id="div-id" class="div-class">
    Contido HTML adicional
  </div>
  ```

### 6.3 MultiMarkdown
- **Características:**
  - Engade características como referencias cruzadas, notas ao pé, citas bibliográficas e matemáticas.
- **Exemplo:**
  ```markdown
  Esta é unha referencia cruzada [Capítulo 1](#capitulo-1).
  
  Esta é unha nota ao pé [^1].
  
  [^1]: Texto da nota ao pé.
  ```

### 6.4 Markdown Here
- **Características:**
  - Extensión para navegadores que permite escribir correos electrónicos en Markdown e convertelos a HTML ao envialos.
- **Exemplo:**
  ```markdown
  Markdown no teu correo electrónico. `Markdown Here` converte isto en HTML.
  ```

### 6.5 MathJax
- **Características:**
  - Permite a inclusión de ecuacións matemáticas complexas en documentos Markdown utilizando a sintaxe de LaTeX.
- **Exemplo:**
  ```markdown
  Fórmula en liña: \( E = mc^2 \)
  
  Fórmula en bloque:
  $$
  E = mc^2
  $$
  ```

### 6.6 PlantUML
- **Características:**
  - Ferramenta para crear diagramas utilizando texto plano. Pode integrarse con Markdown para incluír diagramas directamente nos documentos.
- **Exemplo:**
  ```markdown
  ```plantuml
  @startuml
  Alice -> Bob: Solicitude
  Bob --> Alice: Resposta
  @enduml
  ```
  ```

### 6.7 Diagramas Mermaid
- **Características:**
  - Similar a PlantUML, Mermaid permite a creación de diagramas de fluxo, gráficos de Gantt, etc.
- **Exemplo:**
  ```markdown
  ```mermaid
  graph TD;
      A-->B;
      A-->C;
      B-->D;
      C-->D;
  ```
  ```

### 6.8 Syntax Highlighting
- **Características:**
  - Permite o resaltado de sintaxe para múltiples linguaxes de programación nos bloques de código.
- **Exemplo:**
  ```markdown
  ```python
  def ola_mundo():
      print("Ola, Mundo!")
  ```
  ```

### 6.9 Tocbot
- **Características:**
  - Ferramenta para xerar automaticamente unha táboa de contidos a partir dos títulos dun documento Markdown.
- **Exemplo:**
  ```markdown
  <!-- TOC -->
  ## Sección 1
  ## Sección 2
  ```

### 6.10 KaTeX
- **Características:**
  - Similar a MathJax, KaTeX é outra biblioteca de renderizado de matemáticas que permite a inclusión de ecuacións.
- **Exemplo:**
  ```markdown
  Fórmula en bloque:
  $$
  \int_a^b f(x)dx
  $$
  ```

### Integracións e Ferramentas Complementarias
#### 6.11 Pandoc
- **Características:**
  - Ferramenta de conversión de documentos que soporta Markdown e pode converter entre múltiples formatos (HTML, PDF, DOCX, etc.).
- **Exemplo:**
  ```bash
  pandoc documento.md -o documento.pdf
  ```

#### 6.12 MkDocs
- **Características:**
  - Ferramenta para crear sitios de documentación a partir de arquivos Markdown.
- **Exemplo:**
  ```markdown
  # Introdución
  
  Benvido á documentación.
  ```

#### 6.13 Jekyll e Hugo
- **Características:**
  - Xeradores de sitios estáticos que permiten crear blogs e sitios web utilizando Markdown para os contidos.
- **Exemplo:**
  ```markdown
  ---
  título: "Entrada de Blog"
  data: 2024-05-30
  ---
  # Benvido ao meu blog
  ```

Estas extensións e funcionalidades avanzadas permiten que Markdown sexa unha ferramenta versátil e poderosa para a creación de documentos de diversos tipos, mantendo a sinxeleza que a fixo tan popular.

## 7. Exemplos de Uso en Contextos Reais
### 7.1 Repositorios en GitHub
- Exemplos de README.md ben escritos e estruturados.
- Uso de Markdown en wikis de proxectos.

### 7.2 Blogs Persoais
- Como os blogueiros usan Markdown para redactar contido.

## 8. Ferramentas e Extensións
### 8.1 Editores e Ferramentas
- **Editores en liña:** [Dillinger](https://dillinger.io), [StackEdit](https://stackedit.io).
- **Aplicacións de escritorio:** [Typora](https://typora.io), [Visual Studio Code](https://code.visualstudio.com).
- **Extensións de navegador:** [Markdown Here](https://markdown-here.com).
- **Plugins para Editores de Texto:** Plugins de [Markdown para Visual Studio Code](https://code.visualstudio.com/docs/languages/markdown), [Sublime Text](https://www.sublimetext.com), [Vim](https://www.freecodecamp.org/espanol/news/como-usar-vim-tutorial-para-principiantes/), etc.

### 8.2 Conversores
- Esisten múltiples ferramentas para converter Markdown a outros formatos.
- [Pandoc](https://pandoc.org).

## 9. Recursos Adicionais
### 9.1 Documentación e Tutoriais
- [Documentación](https://www.markdownguide.org)
- Guía de [CommonMark](https://commonmark.org/help/)
- [GitHub Flavored Markdown](https://docs.github.com/es/get-started/writing-on-github)

## 10. Exercicios Prácticos
### 10.1 Redactar un Documento Simple
- Crear un documento Markdown con títulos, parágrafos, listas, enlaces e imaxes.
- Crear teu CV con Markdown

### 10.2 Crear unha Táboa Complexa
- Crear unha táboa con varias columnas e filas, incluíndo formatos de texto como negriña e cursiva.

### 10.3 Publicar un Blog con Markdown
- Publicar unha entrada de blog usando unha plataforma que soporte Markdown (por exemplo, [Jekyll](https://jekyllrb.com) ou [Hugo](https://gohugo.io), ou tamén [Wordpress](https://wpengine.com/resources/using-markdown-wordpress/)).

### 10.4 Static Site Generators (SSG) e Markdown

Os xeradores de sitios estáticos (Static Site Generators, SSG) permiten crear sitios web rápidos e seguros ao precompilar todos os ficheiros do sitio nun servidor, o que elimina a necesidade de procesar o contido dinámico en tempo real. Markdown é amplamente utilizado nestes xeradores debido á súa sinxeleza e capacidade para converter texto plano en HTML de forma eficiente. Aquí tes unha visión xeral dos SSG máis populares e como funcionan con Markdown:

**Que é un Site Static Generator (SSG)?**
- Un SSG é unha ferramenta que converte ficheiros de contido (normalmente escritos en Markdown) e plantillas en ficheiros HTML estáticos listos para ser servidos nun servidor web.
- **Vantaxes:**
  - **Rendemento:** Os sitios estáticos cargan máis rápido xa que non dependen de consultas a bases de datos ou procesamento en tempo real.
  - **Seguridade:** Menos puntos de vulnerabilidade xa que non hai backend dináminco.
  - **Fácil de manter:** Actualizacións simplificadas e menos dependencias.

#### 10.4.1. Xeradores de Sitios Estáticos Populares
##### 10.4.1.1 Jekyll
- **Características:**
  - Integración perfecta con GitHub Pages.
  - Soporte para Markdown e Liquid (linguaxe de plantillas).
  - Gran comunidade e multitude de plugins.
- **Exemplo:**
  ```markdown
  ---
  layout: post
  title: "O meu primeiro post"
  ---
  # Ola, mundo!
  Este é o meu primeiro post en Jekyll.
  ```
- **Configuración básica:**
  ```bash
  gem install jekyll bundler
  jekyll new meu-sitio
  cd meu-sitio
  bundle exec jekyll serve
  ```

##### 10.4.1.2 Hugo
- **Características:**
  - Coñecido pola súa velocidade na compilación de sitios.
  - Soporte para Markdown e linguaxe de plantillas Go.
  - Extensa biblioteca de temas.
- **Exemplo:**
  ```markdown
  ---
  title: "O meu primeiro post"
  date: 2024-05-30
  ---
  # Ola, mundo!
  Este é o meu primeiro post en Hugo.
  ```
- **Configuración básica:**
  ```bash
  hugo new site meu-sitio
  cd meu-sitio
  hugo new posts/meu-primeiro-post.md
  hugo server
  ```

##### 10.4.1.3 Gatsby
- **Características:**
  - Construído sobre React, permitindo compoñentes reutilizables.
  - Soporte para Markdown a través de plugins como `gatsby-transformer-remark`.
  - Enfoque moderno con GraphQL para consultas de datos.
- **Exemplo:**
  ```markdown
  ---
  title: "O meu primeiro post"
  date: "2024-05-30"
  ---
  # Ola, mundo!
  Este é o meu primeiro post en Gatsby.
  ```
- **Configuración básica:**
  ```bash
  npx gatsby new meu-sitio
  cd meu-sitio
  npm install gatsby-transformer-remark
  gatsby develop
  ```

##### 10.4.1.4 Eleventy
- **Características:**
  - Flexibilidade para usar múltiples linguaxes de plantillas.
  - Soporte para Markdown.
  - SSG lixeiro con configuración mínima.
- **Exemplo:**
  ```markdown
  ---
  title: "O meu primeiro post"
  date: 2024-05-30
  ---
  # Ola, mundo!
  Este é o meu primeiro post en Eleventy.
  ```
- **Configuración básica:**
  ```bash
  npx @11ty/eleventy
  eleventy --serve
  ```

#### 10.4.2. Configuración de Proxectos con Markdown
##### 10.4.2.1 Estrutura Típica dun Proxecto
- **Carpetas e ficheiros básicos:**
  - `_posts/` ou `content/`: Contén ficheiros Markdown para as entradas do blog.
  - `_layouts/` ou `layouts/`: Plantillas HTML para o contido.
  - `assets/` ou `static/`: Imaxes, CSS, JavaScript e outros ficheiros estáticos.
  - `config.yml` ou `config.toml`: Ficheiro de configuración do SSG.

##### 10.4.2.2 Integración de Markdown
- **Front Matter:**
  - Metadatos incluídos ao comezo dos ficheiros Markdown para definir configuración específica do contido.
  - **Exemplo:**
    ```markdown
    ---
    title: "O meu primeiro post"
    date: 2024-05-30
    tags: [introdución, exemplo]
    ---
    ```

#### 10.4.3. Funcionalidades Avanzadas
##### 10.4.3.1 Plugins e Extensións
- **Jekyll:**
  - `jekyll-paginate` para páxinas de paginación.
  - `jekyll-sitemap` para xerar sitemaps automáticamente.
- **Hugo:**
  - `shortcodes` para crear compoñentes reutilizables.
  - `hugo-algolia` para integración con Algolia Search.
- **Gatsby:**
  - `gatsby-plugin-image` para optimización de imaxes.
  - `gatsby-source-filesystem` para fontes de datos.
- **Eleventy:**
  - `eleventy-plugin-syntaxhighlight` para resaltado de sintaxe.
  - `eleventy-plugin-rss` para fontes RSS.

##### 10.4.3.2 Funcionalidades específicas de Markdown
- **Taboas, listas de tarefas, imaxes e enlaces:** 
  - Utilización de sintaxe específica para mellorar o contido.
  - **Exemplo:**
    ```markdown
    | Cabeceira 1 | Cabeceira 2 |
    | ----------- | ----------- |
    | Celda 1     | Celda 2     |
    
    - [x] Tarefa completada
    - [ ] Tarefa pendente
    
    ![Imaxe de Exemplo](url_da_imaxe)
    ```

#### 10.4.4. Recursos Adicionais
##### 10.4.4.1 Documentación e Tutoriais
- **Jekyll:** [Documentación oficial](https://jekyllrb.com/docs/)
- **Hugo:** [Documentación oficial](https://gohugo.io/documentation/)
- **Gatsby:** [Documentación oficial](https://www.gatsbyjs.com/docs/)
- **Eleventy:** [Documentación oficial](https://www.11ty.dev/docs/)

##### 10.4.4.2 Comunidades e Foros
- **Stack Overflow:** Para resolver problemas e dúbidas.
- **GitHub:** Repositorios de exemplos e proxectos abertos.
- **Foros específicos:** Discusións en foros dedicados a cada SSG.

#### 10.4.5. Exercicios Prácticos
##### 10.4.5.1 Crear un Blog con Jekyll
- Configurar un novo blog en GitHub Pages utilizando Jekyll.
- Crear entradas en Markdown e personalizar o tema.

##### 10.4.5.2 Crear un Portafolio con Hugo
- Configurar un novo sitio web con Hugo.
- Crear páxinas de proxecto utilizando ficheiros Markdown.

##### 10.4.5.3 Crear un Sitio de Documentación con Gatsby
- Configurar un sitio de documentación utilizando Gatsby.
- Integrar Markdown para as páxinas de documentación e personalizar o estilo.

##### 10.4.5.4 Crear un Sitio Persoal con Eleventy
- Configurar un sitio web persoal utilizando Eleventy.
- Crear entradas de blog e páxinas en Markdown.

### A Importancia de Markdown no Desenvolvemento e Produción de Contidos Web Actual

No mundo do desenvolvemento e produción de contidos web actual, Markdown xogou un papel fundamental ao proporcionar unha maneira sinxela e eficiente de crear e formatar contido para sitios web. A súa importancia radica na súa capacidade para simplificar o proceso de escritura e publicación de contido, ao mesmo tempo que permite unha gran flexibilidade e potencialidades avanzadas.

#### Sinxeleza e Facilidade de Uso
Markdown destaca pola súa sinxeleza e facilidade de uso. A súa sintaxe minimalista permite crear documentos estruturados con facilidade, sen a necesidade de aprender unha linguaxe de marcado complexa. Isto fai que sexa accesible para persoas de todos os niveis de habilidade técnica.

#### Compatibilidade e Portabilidade
Outra vantaxe importante de Markdown é a súa compatibilidade e portabilidade. Os documentos Markdown poden ser convertidos facilmente a HTML, o que permite que o contido creado con Markdown sexa utilizado en calquera sitio web ou plataforma que soporte HTML. Ademais, moitas ferramentas e plataformas populares, como GitHub, GitLab, Jekyll e Hugo, son compatibles con Markdown, o que fai que sexa amplamente adoptado na comunidade de desenvolvemento web.

#### Eficiencia e Produtividade
O uso de Markdown tamén pode mellorar a eficiencia e produtividade dos equipos de desenvolvemento e produción de contidos. Ao eliminar a necesidade de formatos complexos e procesos de edición laboriosos, Markdown permite que os equipos se concentren máis na creación de contido de calidade e menos nos detalles técnicos da súa formatación.

#### Flexibilidade e Funcionalidades Avanzadas
A pesar da súa sinxeleza, Markdown tamén ofrece unha gran flexibilidade e potencialidades avanzadas. A través de extensións e funcionalidades adicionais, como GitHub Flavored Markdown (GFM), Markdown Extra e MultiMarkdown, é posible incluír características avanzadas, como táboas, listas de tarefas, mencións de usuarios, ecuacións matemáticas e diagramas, sen perder a sinxeleza orixinal da linguaxe.

#### Adoita a Práctica Recomendada
En resumo, Markdown é unha ferramenta poderosa e versátil que desempeña un papel crucial no desenvolvemento e produción de contidos web actual. A súa sinxeleza, compatibilidade, eficiencia, flexibilidade e potencialidades avanzadas fan dela unha elección ideal para quen busca unha maneira fácil e eficaz de crear e formatar contido para a web. Ao adoptar Markdown como práctica recomendada, os equipos de desenvolvemento e produción de contidos poden mellorar a súa eficiencia e produtividade, ao mesmo tempo que ofrecen unha mellor experiencia de usuario nos seus sitios web.

---

Desenvolvemento de aplicacións con tecnoloxías web<br>COIRO 2024

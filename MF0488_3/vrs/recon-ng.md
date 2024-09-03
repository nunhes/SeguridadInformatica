# Reon-ng

Reon-ng es una herramienta de tipo OSINT, desarrollada en Python que permite automatizar tareas de reconocimiento y recolección de información desde múltiples fuentes.

Recon-ng tiene una apariencia similar al framework [Metasploit](https://www.metasploit.com/), lo que reducirá la curva de aprendizaje si ya conoces dicha herramienta.

Entre las ventajas de Recon-ng cabe destacar que la que la información que recopila se almacena en una base de datos, lo que permite la realización de consultas y reportes.

## Instalación

- Desde el repositorio de Github con el comando:

  `sudo apt install recon-ng -y`

- Clonando el repositorio de con la última versión de código:

  -  Asegúrate de tener git y pip instalados:

  ```bash
  sudo apt update -y && sudo apt dist-upgrade -y
  sudo apt install git python3-pip -y
  ```

  - Luego clona el repositorio e instala el frmawork:

  ```bash
  sudo git clone https://github.com/lanmaster53/recon-ng.git
  cd recon-ng
  sudo pip install -r REQUIREMENTS
  ```
## Usar Recon-ng

Si has optado por el primer modo de instalación, para ejecutar el programa basta usar el comando:

``sudo recon-ng``

Si lo has instalado clonando el repositorio de Github, desde la carpeta donde se ha clonado recon-ng, ejecuta:

`sudo ./recon-ng`

### Interface y comandos básicos

Podemos acceder a la ayuda del marco de trabajo con el comando: 

``help``



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="514" height="433" src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-32.png" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-32.png" alt="" class="wp-image-2204 lazy loaded" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-32.png 514w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-32-300x253.png 300w" data-sizes="(max-width: 514px) 100vw, 514px" sizes="(max-width: 514px) 100vw, 514px" srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-32.png 514w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-32-300x253.png 300w" data-was-processed="true"></figure></div>



<p>Con help, listamos todos los comandos que podemos correr dentro de <em>recon-ng.</em> </p>



<h2 class="wp-block-heading">Workspaces</h2>



<p>Ya comentamos que <em>remote-ng</em> nos da la posibilidad de trabajar con workspaces, espacios de trabajo, para poder compartimentarla información obtenida a modo de resultados y que no se mezcle con otra.</p>



<p>Por defecto <em>recon-ng </em>siempre nos crea un workspace llamado “default”. Podemos saber en qué workspace estamos trabajando, si miramos el prompt, nos muestra el nombre:</p>



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="160" height="26" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20160%2026'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-33.png" alt="" class="wp-image-2205 lazy"></figure></div>



<p>Para saber cómo usar los worksapces, basta con correr el comando:</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>worksapces</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<p>Y nos despliega para qué sirve el comamdo y las opciones que podemos usar con él<em>.</em></p>



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="408" height="78" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20408%2078'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-34.png" alt="" class="wp-image-2206 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-34.png 408w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-34-300x57.png 300w" data-sizes="(max-width: 408px) 100vw, 408px"></figure></div>



<h4 class="wp-block-heading">Listar workspaces</h4>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>workspaces list</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="332" height="112" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20332%20112'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-35.png" alt="" class="wp-image-2207 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-35.png 332w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-35-300x101.png 300w" data-sizes="(max-width: 332px) 100vw, 332px"></figure></div>



<h4 class="wp-block-heading">Crear workspaces</h4>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>workspaces create [NombreWorkspace]
workspaces create NoSoloHacking</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="454" height="54" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20454%2054'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-36.png" alt="" class="wp-image-2208 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-36.png 454w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-36-300x36.png 300w" data-sizes="(max-width: 454px) 100vw, 454px"></figure></div>



<p>Cuando creamos el workspace, automáticamente, nos situa en ese workspace y podemos identificarlo porque el prompt a cambiado de default a NoSoloHacking.</p>



<h4 class="wp-block-heading">Cambiando de workspace</h4>



<p>A menudo, nos interesará cambiar de workspace para consultar información.</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>workspaces load [NombreWorkspace]
workspaces load default</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="429" height="47" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20429%2047'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-37.png" alt="" class="wp-image-2209 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-37.png 429w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-37-300x33.png 300w" data-sizes="(max-width: 429px) 100vw, 429px"></figure></div>



<h4 class="wp-block-heading">Borrar un workspace</h4>



<p>Cuando no nos interese mantener guardado un workspace, podemos borrarlo.</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>workspaces remove [NombreWorkspace]
workspace remove NoSoloHacking</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="503" height="38" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20503%2038'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-38.png" alt="" class="wp-image-2210 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-38.png 503w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-38-300x23.png 300w" data-sizes="(max-width: 503px) 100vw, 503px"></figure></div>



<h2 class="wp-block-heading">Trabajando con la Base de datos</h2>



<p>Dijimos que podemos trabajar con una base de datos para guardar toda la información y poder consultarla más tarde.</p>



<p>Para poder ver todos los comandos con los que podemos trabajar en la base de datos, hacemos lo mismo que con workspaces, ejecutar:</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>db</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="425" height="70" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20425%2070'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-39.png" alt="" class="wp-image-2211 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-39.png 425w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-39-300x49.png 300w" data-sizes="(max-width: 425px) 100vw, 425px"></figure></div>



<h4 class="wp-block-heading">Cómo se guarda la información</h4>



<p>Para ver las tablas de las base de datos, podemos correr el comando:</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>db schema</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="308" height="605" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20308%20605'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-41.png" alt="" class="wp-image-2213 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-41.png 308w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-41-153x300.png 153w" data-sizes="(max-width: 308px) 100vw, 308px"></figure></div>



<h4 class="wp-block-heading">Borrando información de la base de datos</h4>



<p>Si necesitamos borrar información almacenada en la base de datos, basta con ejecutar:</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>db delete [información a borrar]</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<figure class="wp-block-image size-large is-style-default"><img decoding="async" width="970" height="49" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20970%2049'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-42.png" alt="" class="wp-image-2215 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-42.png 970w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-42-300x15.png 300w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-42-768x39.png 768w" data-sizes="(max-width: 970px) 100vw, 970px"></figure>



<figure class="wp-block-image size-large is-style-default"><img decoding="async" width="643" height="109" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20643%20109'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-43.png" alt="" class="wp-image-2216 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-43.png 643w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-43-300x51.png 300w" data-sizes="(max-width: 643px) 100vw, 643px"></figure>



<h2 class="wp-block-heading">Uso de claves de 3rd parties</h2>



<p>Podemos cargar en <em>recon-ng </em>las claves de otros servicios como Shodan. PAra ello usamos el comando:</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>keys</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<figure class="wp-block-image size-large is-style-default"><img decoding="async" width="374" height="80" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20374%2080'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-44.png" alt="" class="wp-image-2217 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-44.png 374w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-44-300x64.png 300w" data-sizes="(max-width: 374px) 100vw, 374px"></figure>



<h4 class="wp-block-heading">Listar claves</h4>



<p>Para saber todas las claves que tenemos metidas</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>keys list</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<h4 class="wp-block-heading">Agregando claves</h4>



<p>Si queremos por ejemplo agregar la API de Shodan, ejecutamos:</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>keys add shodan_api [API de Shodan]</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<h2 class="wp-block-heading">Mostrando información almacenada</h2>



<p>Para poder ver una parte de la información recolectada, como dominio, credenciales, hosts.. basta con usar el comando show y lo que queremos ver.</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-syntaxhighlighter-code copy-the-code-target">show [información]
show hosts
show domains
show credentials<button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<figure class="wp-block-image size-large is-style-default"><img decoding="async" width="1024" height="76" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201024%2076'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-45-1024x76.png" alt="" class="wp-image-2219 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-45-1024x76.png 1024w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-45-300x22.png 300w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-45-768x57.png 768w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-45.png 1115w" data-sizes="(max-width: 1024px) 100vw, 1024px"></figure>



<h2 class="wp-block-heading">Creando snapshots</h2>



<p>Si queremos crear snapshots/backups de los wokspaces, lo que tenemos que hacer es usar el comando:</p>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>snapshot</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img decoding="async" width="403" height="58" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20403%2058'%3E%3C/svg%3E" data-src="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-46.png" alt="" class="wp-image-2220 lazy" data-srcset="https://www.nosolohacking.info/wp-content/uploads/2020/10/image-46.png 403w, https://www.nosolohacking.info/wp-content/uploads/2020/10/image-46-300x43.png 300w" data-sizes="(max-width: 403px) 100vw, 403px"></figure></div>



<h4 class="wp-block-heading">Crear snapshots</h4>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>snapshots take</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<h4 class="wp-block-heading">Borrar snapshots</h4>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>snapshots remove [nombre snapshot]</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<h4 class="wp-block-heading">Listar Snapshots</h4>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>snapshots list</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<h4 class="wp-block-heading">Cargar snapshot</h4>



<span data-copy-format="" data-button-text="Copy" data-button-position="inside" data-button-copy-text="Copied!" data-style="button" data-button-title="Copy to Clipboard" data-selector="pre" class="copy-the-code-wrap copy-the-code-style-button copy-the-code-inside-wrap"><pre class="wp-block-code copy-the-code-target"><code>snapshot load [nombre snapshot]</code><button class="copy-the-code-button" data-style="button" title="Copy to Clipboard">Copy</button></pre></span>



<figure class="wp-block-embed-youtube wp-block-embed is-type-video is-provider-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
<iframe loading="lazy" title="RECON-NG comandos básicos e interfaz - OSINT tools - (Parte 2)" width="640" height="360" src="https://www.youtube.com/embed/l229O4ZUFa4?feature=oembed" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe>
</div></figure>



<div class="wp-block-image is-style-default"><figure class="aligncenter"><img class="lazy" decoding="async" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201%201'%3E%3C/svg%3E" data-src="https://media0.giphy.com/media/26u4lOMA8JKSnL9Uk/giphy.gif" alt="My Work Is Done Reaction GIF by SpongeBob SquarePants"></figure></div>



<h4 class="wp-block-heading">Enlace a la parte 3</h4>



<figure class="wp-block-embed-wordpress wp-block-embed is-type-wp-embed is-provider-no-solo-hacking"><div class="wp-block-embed__wrapper">
<blockquote class="wp-embedded-content" data-secret="Zei2J0X0QU"><a href="https://www.nosolohacking.info/recon-ng-parte3-los-modulos-y-su-marketplace/">Recon-ng (parte3): Los módulos y su marketplace</a></blockquote><iframe loading="lazy" class="wp-embedded-content" sandbox="allow-scripts" security="restricted" style="position: absolute; clip: rect(1px, 1px, 1px, 1px);" title="“Recon-ng (parte3): Los módulos y su marketplace” — No Solo Hacking" src="https://www.nosolohacking.info/recon-ng-parte3-los-modulos-y-su-marketplace/embed/#?secret=cMdOsoJpl5#?secret=Zei2J0X0QU" data-secret="Zei2J0X0QU" width="600" height="338" frameborder="0" marginwidth="0" marginheight="0" scrolling="no"></iframe>
</div></figure>
<div class="post-views content-post post-2203 entry-meta load-static">
				<span class="post-views-icon dashicons dashicons-chart-bar"></span> <span class="post-views-label">Post Views:</span> <span class="post-views-count">11,107</span>
			</div>        <script>
        function pinIt()
        {
            var e = document.createElement('script');
            e.setAttribute('type','text/javascript');
            e.setAttribute('charset','UTF-8');
            e.setAttribute('src','https://assets.pinterest.com/js/pinmarklet.js?r='+Math.random()*99999999);
            document.body.appendChild(e);
        }
        </script>
    
        <div class="post-share">
            <div class="post-share-icons cf"> 
                                    <a class="facebook" href="https://www.facebook.com/sharer.php?u=https://www.nosolohacking.info/recon-ng-parte2-introduccion-a-la-interfaz-y-comandos-basicos/" target="_blank">
                        <i class="fab fa-facebook"></i>
                    </a>
                                    <a class="x-twitter" href="http://twitter.com/share?url=https://www.nosolohacking.info/recon-ng-parte2-introduccion-a-la-interfaz-y-comandos-basicos/&amp;text=Recon-ng%20%28Parte2%29%3A%20Introducci%C3%B3n%20a%20la%20interfaz%20y%20comandos%20b%C3%A1sicos" target="_blank">
                        <i class="fa-brands fa-x-twitter"></i>
                    </a>
                                    <a class="envelope" href="mailto:?subject=Recon-ng%20(Parte2):%20Introducción%20a%20la%20interfaz%20y%20comandos%20básicos&amp;body=https://www.nosolohacking.info/recon-ng-parte2-introduccion-a-la-interfaz-y-comandos-basicos/" target="_blank">
                        <i class="fas fa-envelope-open"></i>
                    </a>
                                    <a class="linkedin" href="https://www.linkedin.com/sharing/share-offsite/?url=https://www.nosolohacking.info/recon-ng-parte2-introduccion-a-la-interfaz-y-comandos-basicos/&amp;title=Recon-ng%20%28Parte2%29%3A%20Introducci%C3%B3n%20a%20la%20interfaz%20y%20comandos%20b%C3%A1sicos" target="_blank">
                        <i class="fab fa-linkedin"></i>
                    </a>
                                    <a href="javascript:pinIt();" class="pinterest">
                        <i class="fab fa-pinterest"></i>
                    </a>
                                    <a class="telegram" href="https://t.me/share/url?url=https://www.nosolohacking.info/recon-ng-parte2-introduccion-a-la-interfaz-y-comandos-basicos/&amp;title=Recon-ng%20%28Parte2%29%3A%20Introducci%C3%B3n%20a%20la%20interfaz%20y%20comandos%20b%C3%A1sicos" target="_blank">
                        <i class="fab fa-telegram"></i>
                    </a>
                                    <a class="whatsapp" href="https://api.whatsapp.com/send?text=https://www.nosolohacking.info/recon-ng-parte2-introduccion-a-la-interfaz-y-comandos-basicos/&amp;title=Recon-ng%20%28Parte2%29%3A%20Introducci%C3%B3n%20a%20la%20interfaz%20y%20comandos%20b%C3%A1sicos" target="_blank">
                        <i class="fab fa-whatsapp"></i>
                    </a>
                                    <a class="reddit" href="https://www.reddit.com/submit?url=https://www.nosolohacking.info/recon-ng-parte2-introduccion-a-la-interfaz-y-comandos-basicos/&amp;title=Recon-ng%20%28Parte2%29%3A%20Introducci%C3%B3n%20a%20la%20interfaz%20y%20comandos%20b%C3%A1sicos" target="_blank">
                        <i class="fab fa-reddit"></i>
                    </a>
                                <a class="print-r" href="javascript:window.print()"> <i class="fas fa-print"></i></a>
            </div>
        </div>
                        <div class="clearfix mb-3"></div>
                    
    <nav class="navigation post-navigation" aria-label="Posts">
    	<h2 class="screen-reader-text">Post navigation</h2>
    	<div class="nav-links"><div class="nav-previous"><a href="https://www.nosolohacking.info/recon-ng-instalacion/" rel="prev"><div class="fas fa-angle-double-left"></div><span> Recon-ng, ¿qué es?</span></a></div><div class="nav-next"><a href="https://www.nosolohacking.info/recon-ng-parte3-los-modulos-y-su-marketplace/" rel="next"><span>Recon-ng (parte3): Los módulos y su marketplace </span><div class="fas fa-angle-double-right"></div></a></div></div>
    </nav>                

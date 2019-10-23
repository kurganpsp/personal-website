# Comience a construir su sitio web personal

### Muestra tus habilidades de desarrollo de software

Este repositorio le brinda el código que necesitará para iniciar un sitio web personal que muestre su trabajo como desarrollador de software. Y cuando administra el código en un repositorio de GitHub, automáticamente mostrará una página web con la información del perfil del propietario, incluyendo una foto, biografía y repositorios.

Sin embargo, su sitio web personal está esperando ser personalizado. Incluye espacio para resaltar sus áreas específicas de interés en el desarrollo de software, como idiomas o industrias. Y está listo para publicar su próxima gran publicación de blog.

Todo es posible utilizando la combinación de [Jekyll](https://jekyllrb.com/docs/) (para construir su sitio web), [GitHub Pages](https://pages.github.com/) (para alojar su sitio web ) y [API de GitHub](https://developer.github.com/v3/) (para rellenar automáticamente su sitio web con contenido).

## Instalación

### Bifurca el repositorio `github/personal-website`

Hará su propia copia del repositorio "iniciador de sitio web personal" para que pueda personalizar su propio proyecto. Una "bifurcación" es una copia de un repositorio. Por lo tanto, seleccione "Fork" en la parte superior [el repositorio `github/personal-website`](https://github.com/github/personal-website).

Una vez que haya encontrado un hogar para su repositorio bifurcado, será suyo. Eres el propietario, así que estás listo para publicar, si lo deseas.

### Instalar en su entorno de desarrollo local

Si desea administrar su sitio web en un entorno de desarrollo web local, utilizará [Ruby](https://jekyllrb.com/docs/installation/).

Una vez que haya encontrado un hogar para su repositorio bifurcado, **[clónelo](https://help.github.com/articles/cloning-a-repository/)**.

#### Instalar Jekyll

Jekyll es una [Ruby Gem](https://jekyllrb.com/docs/ruby-101/#gems) que se puede instalar en la mayoría de los sistemas.

1. Instalar un completo [Ruby development environment](https://jekyllrb.com/docs/installation/)
2. Instalar Jekyll y [bundler](https://jekyllrb.com/docs/ruby-101/#bundler) [gems](https://jekyllrb.com/docs/ruby-101/#gems)
```
gem install jekyll bundler
```
3. Cambie a su nuevo directorio
```
cd personal-website
```
4. Instalar gemas faltantes
```
bundle install
```
5. Construya el sitio y póngalo disponible en un servidor local
```
bundle exec jekyll serve
```

Deberías ver algo como:

```
Configuration file: /octocat/personal-website/_config.yml
            Source: /octocat/personal-website
       Destination: /octocat/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
   GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.
                    done in 14.729 seconds.
 Auto-regeneration: enabled for '/octocat/personal-website'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```

No se preocupe por el mensaje "No se pudo encontrar la autenticación de la API de GitHub". [La autenticación API solo es necesaria](https://github.com/jekyll/github-metadata/blob/master/docs/authentication.md) si tiene la intención de mostrar metadatos más detallados, como el nombre de una sucursal.

6. Ahora navegue a [http://localhost:4000](http://localhost:4000)

### Publicar

Cuando aloja el código de su sitio web personal en GitHub, obtiene el soporte de alojamiento gratuito a través de las páginas de GitHub.

**El enfoque más rápido** es cambiar el nombre de su repositorio `username.github.io`, donde` username` es su nombre de usuario de GitHub (o nombre de la organización). Luego, la próxima vez que envíe algún cambio a la rama `master` de su repositorio, estará accesible en la web en su dirección` username.github.io`.

**Si desea utilizar un dominio personalizado**, deberá agregarlo a la configuración de "Dominio personalizado" de su repositorio en github.com. Y luego regístrese y/o [configure su dominio con un proveedor de DNS](https://help.github.com/articles/quick-start-setting-up-a-custom-domain/).

## Personalización

Es su sitio web y usted controla el código fuente. Para que pueda personalizar todo, si lo desea. Pero hemos proporcionado un puñado de personalizaciones rápidas para que usted considere a medida que despega su sitio web.

### Cambios rápidos de configuración

La mayoría de las personalizaciones se pueden hacer en cuestión de segundos, revisando el archivo `_config.yml` de su repositorio. Solo recuerde reiniciar su servidor local cada vez que guarde nuevos cambios para que su sitio web con tecnología Jekyll se reconstruya correctamente:

1. Apague su servidor ingresando el comando de teclado <kbd>CTRL</kbd> + <kbd>c</kbd>
2. Reinicie su servidor: `bundle exec jekyll serve`


#### Diseño

Su sitio web se mostrará en un diseño de dos columnas de forma predeterminada en dispositivos de pantalla más grande, con su foto, nombre e información básica en una "barra lateral" alineada a la izquierda. Puede cambiar rápidamente a un diseño de columna única "apilada" cambiando la línea en su archivo `_config.yml` que dice` layout: sidebar` a `layout: stacked`.

#### Estilo

Su sitio web aparece con un fondo blanco y gris "claro" de forma predeterminada, con texto oscuro. Puede cambiar rápidamente a un fondo "oscuro" con texto blanco cambiando la línea en su archivo `_config.yml` que dice` style: light` a `style: dark`.

#### Proyectos

La sección "Mis proyectos" de su sitio web se genera de forma predeterminada con sus nueve repositorios "empujados" más recientes. También excluye los repositorios que usted bifurcó, por defecto. Pero cada uno de estos parámetros se puede personalizar rápidamente en el archivo `_config.yml` de su repositorio, debajo de la línea del diccionario `projects`.

Los parámetros incluyen:

- `sort_by`: The method by which repositories are sorted. Options include `pushed` and `stars`.
- `limit`: The maximum number of repositories that will be displayed in the "My Projects" section of your website. Out of the box, this number is set to `9`.
- `exclude`:
   - `forks`: When `true`, repositories you've forked will be excluded from the listing.
   - `projects`: A list the repository names you want to exclude from the listing.

- `sort_by`: el método por el cual se ordenan los repositorios. Las opciones incluyen `pushed` y` stars`.
- `limit`: el número máximo de repositorios que se mostrarán en la sección "Mis proyectos" de su sitio web. Fuera de la caja, este número se establece en `9`.
- `excluir`:
  - `forks`: cuando es` true`, los repositorios que haya bifurcado se excluirán de la lista.
  - `projects`: una lista de los nombres de repositorio que desea excluir de la lista.

#### Temas

Su sitio web viene preconfigurado con tres temas (por ejemplo, "Web design" y "Sass") que aparecen en una sección titulada "Mis intereses". Estos también se almacenan en el archivo `_config.yml` de su repositorio, donde puede definir el nombre de cada tema y otros dos detalles opcionales:

- `web_url`: La dirección web a la que desea vincular su tema (e.g. `https://github.com/topics/sass`).
- `image_url`: La dirección web de una imagen (idealmente cuadrada) que le gustaría que aparezca con su tema.

#### Social media

Su sitio web admite la vinculación y el intercambio con los servicios de redes sociales que está utilizando, incluidos Behance, Dribbble, Facebook, LinkedIn, Medium, Stack Overflow, Twitter y YouTube. Para identificar los servicios que utiliza:

1. Edite el archivo `_config.yml` de su repositorio.
2. Edite la línea del diccionario `social_media` y represente los servicios que desee en una forma simple `key: value`:

```
social_media:
  behance: your_username
  dribbble: your_username  
  facebook: your_username
  hackerrank: your_username
  instagram: your_username
  keybase: your_username
  linkedin: your_username
  medium: your_username
  stackoverflow: your_user_id
  telegram: your_username
  twitter: your_username
  unsplash: your_username
  vk: your_username
  website: http://your_website_url
  youtube: your_username
```

Los enlaces a su perfil para cada uno de los servicios que defina aparecerán en el `<header>` de su sitio web, adjunto a su biografía. Y si esos servicios admiten compartir, cualquier publicación de blog que publique incluirá enlaces para compartir esa publicación utilizando cada servicio de redes sociales.

**Nota**: esta función es compatible con dos archivos en su repositorio:

- `/_data/social_media.yml`: Define cada uno de los servicios compatibles, incluidos el nombre de la variable, el nombre para mostrar, la ruta de la URL y el icono SVG.
- `/_includes/social_media_share_url.html`: Emite la URL compartida requerida para cualquiera de los servicios de redes sociales compatibles que admiten URL compartidas.

Si está interesado en agregar un servicio de redes sociales que aún no es compatible con este repositorio, puede editar estos dos archivos para crear ese soporte.

## Agregar páginas

Para **agregar una página** a su sitio web (por ejemplo, currículum detallado):

1. Cree un nuevo archivo `.html` o` .md` en la raíz de su repositorio.
2. Déle un nombre de archivo que desee que se use en la URL de la página (por ejemplo, `http://yoursite.dev/filename`).
3. Al comienzo de su archivo, incluya lo siguiente [tema principal](https://jekyllrb.com/docs/front-matter/):

```
---
diseño: predeterminado
---
```

## Adding blog posts

To **add a blog post** to your website:

1. Create a new `.md` file in your repository's `/_posts/` directory.
2. Give it a filename using the following format:

```
YEAR-MONTH-DAY-title.MARKUP
```

3. At the start of your file, include the following [front matter](https://jekyllrb.com/docs/front-matter/):

```
---
title: "The title of my blog post"
---
```

Your website comes with a placeholder blog post that you can reference. Notably, its [front matter](https://jekyllrb.com/docs/front-matter/) declares `published` as `false`, so that it won't appear on your website.

While you can define a `layout` in the front matter, your website is pre-configured to assign the `post` layout to all of the posts in your `/_posts/` directory. So you don't have to declare that in your posts.

Jekyll's conventions for authoring and managing blog posts is very flexible. You can [learn more in Jekyll's documentation for "Posts."](https://jekyllrb.com/docs/posts/)

## Content and templates

To give you a sound foundation to start your personal website, your repository includes a handful of "includes" -- dynamic `.html` files that are re-used throughout your website. They're all stored in the `/_includes/` directory.

There are the usual suspects, like `header.html` and `footer.html`. But there are few more worth pointing out:

- `interests.html`: A heading and dynamic list of "My Interests," which is populated with the [topics](#topics) you list in your `_config.yml`.
- `masthead.html`: A collection of your avatar, name, bio, and other metadata that's displayed prominently on all your webpages to help identify what the website is about.
- `post-card.html`: A compact, summarized presentation of a blog post, re-used to display a listing of your latest blog posts.
- `projects.html`: A heading and dynamic list of "My Projects," which is populated with a listing of your newest GitHub repositories.
- `repo-card.html`: A compact, summarized presentation of a repository, re-used to display a listing of your GitHub repositories.
- `thoughts.html`: A heading and dynamic list of "My Thoughts," which is populated with a listing of your latest blog posts.
- `topic-card.html`: A compact, summarized presentation of a topic (defined in your `_config.yml`), re-used to display a listing of your interests.

### Layouts

Your repository comes with three layouts:

- **default**: Not used by any of the built-in pages or posts, but useful for any new pages you create.
- **home**: Used by your `index.html` homepage to display listings of your projects, interests, and (optionally) your blog posts.
- **post**: Used by default by the posts in your `/_posts/` directory.

Jekyll's convention for defining layouts is very flexible. You can [learn more about customizing your layouts in the Jekyll "Layouts" docs.](https://jekyllrb.com/docs/layouts/)

## Styles

Your website is pre-configured to use [GitHub's very flexible CSS framework called "Primer,"](https://styleguide.github.com/primer/). It's currently referenced within your `styles.scss` file, using the CSS import at-rule:

```
@import url('https://unpkg.com/primer/build/build.css');
```

You are, of course, welcome to remove it or replace it with another framework. Just bear in mind that the HTML that your website came pre-packaged with references multiple Primer "utility classes" to define things like column widths, margins, and background colors.

You also have the option to add on to and extend Primer's styles by adding custom CSS to your `/assets/styles.scss` Sass stylesheet. By editing this file, you can customize your website's color scheme, typography, and more.


## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

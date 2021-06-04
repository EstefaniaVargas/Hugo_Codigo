---
title: "Crear un tema desde cero"
date: 2021-05-25T12:09:35-05:00
type: without-menu
layout: list
---

# ¿Cómo crear un tema ?

Para empezar crear un tema se debe usar el comando:

`hugo new theme <Nombre_del_tema>`

Este comando creará una carpeta con el nombre deseado en la carpeta themes con los siquientes directorios
```bash
|--themes
   |--<Nombre_del_tema>
      |--archetypes
      |--layouts
      |--static
      |--LICENSE
      |--theme.config
```
De los cuales archetypes layouts y static corresponden a carpetas. 

## Archetypes

El primero archetypes, corresponde a una carpeta donde se alojarán plantillas del forntmatter de los markdown que se creen más adelante.

```bash
---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
---
```
Este es una plantilla básica que puede ir en esta carpeta se le pueden agregar más caracteristicas dependiendo de la necesidad del
usuario.

## Layouts

Seguido a esto nos encontramos con la carpeta layout que tiene la siguiente organizacion:
```bash
|--layouts
   |--_default
      |--baseof.html
      |--list.html
      |--single.html
   |--partials.html
      |--footer.html
      |--head.html
      |--header.html
   |--404.html
   |--index.html
```    
En la carpeta "_ _default_" se encontrarán los archivos de los layouts basicos a usar en las páginas que se creen; en la carpeta de partials se tiene aquellos partes del html que se pueden visualizar en varias paginas, y por último se tienen archivos 404 que es para las paginas que no se encuentran, y index en el cual se puede definir el home de la pagina web.

### Baseof

Entendiendo como funciona el baseof, al abrirlo se puede observar la siguiente estructura.
```bash
<!DOCTYPE html>
<html>
    {{- partial "head.html" . -}}
    <body>
        {{- partial "header.html" . -}}
        <div id="content">
        {{- block "main" . }}{{- end }}
        </div>
        {{- partial "footer.html" . -}}
    </body>
</html>
```
Esta estructura funciona como una base de todas las paginas que se pueden hacer a futuro. Se observa que hace un llamado a los partials head,header y footer, segun como es la estructura de una pagina html. Adicionalmente, se observa que hay un block definido como main en la parte de contenido, la función de este block es que este se pueda definir en otras layouts como el de single o list.

### Single

Para manejar una pagina que funcione como una sola se puede usar la siguiente plantilla.
```bash
{{ define "main" }}
<main class="content">
    {{ .Content }}
</main>
{{end}}
```
Esto nos permitirá  visualizar un contenido sencillo que se escriba en el markdown que use este layout. Para más templates se puede visitar la pagina de [hugo templates single](https://gohugo.io/templates/single-page-templates/).

### List

Para manejar una pagina que se visualice como la lista de otras paginas o publicaciones se puede usar el siguiente template.
```bash
{{ .Content }}
        
{{ range.Data.Pages }}
  <article class="post-snippet">
     <h3>                   
      <a style="text-decoration:none; color:black" href="{{ .RelPermalink }}">{{ .Title }}</a>
     </h3>
 </article>
```
Esto nos permitirá  visualizar un contenido sencillo  y adicionalmente una lista de las paginas que correspondan. Para más templates se puede visitar la pagina de [hugo templates list](https://gohugo.io/templates/lists/).

### Partials
En los partials puede ubicar lo que considere pertinente para un header, head, footer en codigo html como los on logos menus e información que considere pertinente.

## Static

En la carpeta static se ubicaran las imagenes que necesite inlcuir en el diseño de su pagina y el documento que desee incluir para el diseño de la pagina como el formato css.

Referencias:

>**[Migrating WordPress to Hugo: Course Reference](https://tygerbytes.github.io/wp2hugoref/#06-write-a-new-post-with-hugo)**


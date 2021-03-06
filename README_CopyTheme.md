
# ¿Cómo añadir un tema y configurarlo?


Antes de empezar se debe tener en 
cuenta que hay que tener la versión "extendida" Sass/SCSS de Hugo con el siguiente comando:

`
choco install hugo-extended -confirm
`
Si no tiene Windows, puede revisar la página oficial de Hugo para las respectivas instalaciones:
**[(Instalar Hugo)](https://gohugo.io/getting-started/installing/)**


Ahora si, volviendo a los temas: 

Estos permiten crear un sitio web con un aspecto atractivo y de manera más sencilla. El sitio web de Hugo cuenta con una sección completamente dedicada a temas, con muchas alternativas interesantes y adaptables a todo tipo de proyecto.


**[Ingresar temas Hugo!!!](https://themes.gohugo.io/)**

El presente repositorio cuenta con un tema, el cuál es una plantilla base para Bancolombia que puede usar en su archivo raiz. Esta plantilla se encuentra dentro de la carpeta llamada `Tema_PlantillaBase` o tambíen puede usar la carpeta `themes/Theme_Bancolombia`

Para agregar un tema hay dos métodos:

1. Descargar el tema en un zip

    Ya elegido el tema, se descarga en un achivo zip, luego se descomprime y coloca la carpeta con todo el contenido del tema en una subcarpeta del proyecto raíz llamada "themes/".

2. Línea de comandos

Con Git se puede agregar el tema más rápido y consiguiendo un flujo de trabajo más mantenible de cara a las actualizaciones del tema.

- Método submodule     

    Estando en la carpeta raíz del proyecto, se ejecuta lo siguiente:

    `
    git submodule add https://github.ibm.com/Julieth-Acosta/Pruebas_Templates.git themes/<nombre nuevo tema> 
    `

    Este método no se recomienda ya que copia la subcarpeta al repositorio vacía, copiando solo al archivo localmente.
    
- Método clone

    Estando en la carpeta raíz del proyecto, se ejecuta lo siguiente:

    `
    git clone --depth 1  https://github.ibm.com/Julieth-Acosta/Pruebas_Templates.git themes/<nombre nuevo tema>
    `

    Luego borrar el directorio .git

    `
    rm -Recurse -Force themes/<nombre nuevo tema>/.git
    `

Ya agregado el tema, en el proyecto raiz se debe hacer una configuración para especificar el uso del tema. Esto se realiza dentro del archivo `config.toml` y se debe agregar las siguientes lineas de código:

    `
    baseURL = "<URL deseada>"
    languageCode = "en-us"  #idioma
    title = "<Titulo>"
    theme = "<Nombre asignado al tema clonado>"
    `

Para crear un nuevo Post se debe ejecutar el siguiente comando en el directorio raíz:

    `
    hugo new content/<nombre>.md 
    `

Observará un nuevo archivo markdown con el nombre que se asignó donde se deben agregar las siguientes lineas en la parte superior e inferior del código, en el caso de no contenerlas:

    `
    ---
    title: "<Nombre deseado>"
    date: 2021-04-22T00:22:40-05:00  #Actualizar fecha
    draft: false
    ---
    `
Teniendo en cuenta que si el draft esta en "false" la página se va a actualizar automaticamente sin la necesidad de ejecutar códigos de hugo para construir la página.


Ya para ejecutar la página y poder visualizarla junto con el tema seleccionado, se ejecuta el siguiente comando:

    `
    hugo server -D
    `

Para configuraciones adicionales consultar la página de **[Hugo](https://gohugo.io/)**

Referencias:

>**[Migrating WordPress to Hugo: Course Reference](https://tygerbytes.github.io/wp2hugoref/#06-write-a-new-post-with-hugo)**

>**[Primeros pasos con Hugo](https://desarrolloweb.com/articulos/primeros-pasos-hugo)**






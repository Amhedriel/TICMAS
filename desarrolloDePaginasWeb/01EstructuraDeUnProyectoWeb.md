# Estructura de un proyecto Web

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/README.md "Desarrollo de páginas Web")
[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/02ElementosMultimediales.md "Elementos Multi Mediales")

---

Módulo 1

* HTML
    * sintaxis
* Elementos HTML
* Nombres de archivos

+ [¿Qué debo escribir en código HTML?](#¿qué-debo-escribir-en-código-html)
+ [Nombre de archivos](#nombre-de-archivos)
+ [Composición de un documento HTML](#composición-de-un-documento-html)
+ [Estructura de HTML](#estructura-de-html)
    + [`<html></html>`](#htmlhtml)
    + [`<head></head>`](#elemento-headhead)
    + [`<body></body>`](#elemento-bodybody)
    + [Identado](#identado)

Comencemos con HTML.

## ¿Qué debo escribir en código HTML?

Básicamente todo el contenido de la página, pero nada que tenga relación con el diseño y los estilos visuales.

En el HTML se debe incluir:
- Textos.
- Links.
- Llamadas a imágenes.
- videos.

Manejando las **etiquetas** (label) que estructuran el contenido de toda la página web.
Recordemos que todas las definiciones estéticas irán en la hoja de estilos CSS, y no en el documento HTML, a menos que se utilicen bibliotecas como "Tail Wind".

## Nombre de archivos
## ***`index.html`***
Comencemos con un index.html (el índice de nuestro proyecto). Nombre de archivo de la página de inicio de todo sitio web:
<br>
<br>
<svg id="Capa_1" data-name="Capa 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 90"><text transform="translate(46.25 45.12)" font-size="24" fill="#f70014" font-family="Consolas">index.html</text><rect x="22" y="15" width="180" height="45" fill="none" stroke="#f00028" stroke-miterlimit="10" stroke-width="6"/><rect x="3" y="3" width="216" height="71" fill="none" stroke="#f00028" stroke-miterlimit="10" stroke-width="6"/></svg>

Esto significa que sea el único. Los archivos pueden tener cualquier nombre, por convención es `index.html`, sin embargo los servidores van a reconocer al que se llame `index.html` como la página de inicio.

## Composición de un documento HTML
Está principalmente compuesto por las `etiquetas`

+ `<html></html>`
    + `<head></head>`
    + `<body></body>`

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Documento</title>
  </head>
  <body>
  
  </body>
</html>
```
Más adelante veremos para que está destinada cada parte de este documento.
De momento crearemos un "Hola mundo" en nuestro html utilizando la extensión de Live Server.

```html
<body>
  <p>"Hola mundo"</p>
</body>
```
Empecemos a ver que los elementos que encapsulemos dentro del ***tag*** `<body></body>` son aquellos que veremos reflejados en la pantalla del navegador.

![](/media/SintaxisHTML1.svg "")

El contenido de `<title></title>` se mostrará en la solapa de la pestaña en el navegador, en nuestro caso aparece "Documento", sin embargo ahora lo modificaremos para tenerlo un poco más presente:
```html
<title>Nuestro html</title>
```

Veamos con atención el tributo de `<html></html>` que indica el lenguaje en el que está escrito nuestro documento, nosotros lo colocamos en `es` porque utilizaremos el idioma de español.

Ahora tengamos en cuenta la sangría de nuestro código, debemos respetar los espacios que tenemos para poder diferenciar entre padres e hijos, es parte de las buenas prácticas para mejorar la legibilidad de nuestro código.

---

## Estructura de HTML
Veamos un ejemplo de documento HTML

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" src="style.css">
  <title>Estructura HTML</title>
</head>
<body>
  
  <h1>título de 1º jerarquía.</h1>
    <p>Un párrafo cualquiera</p>

  <h2>título de 2º jerarquía.</h2>
  <p>"Hola mundo"</p>
</body>
</html>
```
### `<html></html>`
Es el gran contenedor de toda la estructura y a su vez en su interior divide en 2 grandes partes
* head
* body

### Elemento `<head></head>`
Es el que va a contener toda la meta información que le daremos al navegador respecto a nuestro documento HTML, puede ser el:
* `title` que es el nombre de nuestra página en la solapa de la pestaña del navegador.
* `meta` instrucciones al navegador con elementos que usaremos en el documento actual, incluso enlaces a archivos tales como CSS o JavaScript.
* `<link rel="stylesheet" src="style.css">` enlace con el documento CSS para dar estilos a nuestra página web.
* `<script src="index.js"></script>` enlace con el documento de JvaScript para la interactividad con nuestra página web.

### Elemento `<body></body>`
Es la parte visible para el usuario en el navegador.

Nosotros colocaremos algunos elementos básicos:

Tenemos los **tags** de títulos `<h1></h1>` al `<h6></h6>`.
```html
<body>
  <h1>título de 1º jerarquía.</h1>
  <h2>título de 2º jerarquía.</h2>
  <h3>título de 3º jerarquía.</h3>
  <h4>título de 4º jerarquía.</h4>
  <h5>título de 5º jerarquía.</h5>
  <h6>título de 6º jerarquía.</h6>

  <p>"Hola mundo"</p>
</body>
```
Nosotros podemos ver que todos los elementos dentro de body son los que se renderizan para que el usuario pueda visualizar el contenido cuando visite nuestra página.

Pensemos en HTML como si fuera un rompecabezas en el cual cada pieza tiene que tener un sentido en el documento de acuerdo al valor semántico de cada una de las etiquetas `tags`, para saber que cuando debamos hacer un título tenga más sentido usar un elemento `h1` a `h6` que utilizar un `p` que aunque ambos muestren texto en pantalla no sólo se debe basar en eso.

Veamos que en el ejemplo de `body` los tags `h` lo renderizan del más grande al más pequeño, esto es porque aún no trabajamos con la capa de presentación o Capa de Estilos en Cascada (CSS) lo que estamos haciendo es armar la estructura que va a tener nuestro documento, con lo cual el navegador viene con estilos propios por *default*.
Si nos fijamos del `h1` al `h6` visualmente están renderizados del más grande al más pequeño, esto es porque los navegadores traen estilos por defecto, cuando empecemos a personalizar los estilos de las páginas a lo que nosotros queremos, vamos a poder indicarle la tipografía, colores, tamaños, y otras opciones de las que nos provee CSS para poder configurar la presentación, el diseño que nosotros queremos.

### Identado

Veamos que con el identado nosotros tratamos de respetar cierta lógica en el documento y escribir uno debajo de otro los elemento HTML según su jerarquía o parentesco.

```html
<body>
  <main>
    <ul>
      <li>Contenido</li>
      <li>Contenido</li>
      <li>Contenido</li>
    </ul>
  </main>
</body>
```
Si bien de momento tiene pocos elementos en este momento no es lo mismo presentarlo de esta manera a esto:

```html
<body>
<main>
  <ul><li>Contenido</li><li>Contenido</li><li>Contenido</li></ul>
</main>
</body>
```
Es importante saber que el código que hoy lo estamos haciendo el día de mañana alguien más tendrá que leerlo y un documento de sta manera no es prolijo, no ayuda a la comprensión visual, y tiene muchos peros, tratar de tener buenas prácticas desde el inicio es bueno, así tener el documento lo más limpio, lo más claro posible, por si un compañero o nosotros mismos tengamos que editar esto no resulte difícil entenderlo e interpretarlo.

---

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/README.md "Desarrollo de páginas Web")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/02ElementosMultimediales.md "Elementos Multi Mediales")

[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[_Subir_ **&#11165;**](#estructura-de-un-proyecto-web "Ir al título")

# Estructura de un proyecto Web

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/README.md "Desarrollo de páginas Web")
[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/01.1ElementosDeBloqueDeLinea.md "Elementos de Bloque y elementos de Línea")

---

Módulo 1

* HTML
    * sintaxis
* Elementos HTML
* Nombres de archivos

CONTENIDO:
+ [¿Qué debo escribir en código HTML?](#¿qué-debo-escribir-en-código-html)
+ [Nombre de archivos](#nombre-de-archivos)
+ [Composición de un documento HTML](#composición-de-un-documento-html)
+ [Estructura de HTML](#estructura-de-html)
    + [`<html></html>`](#htmlhtml)
    + [`<head></head>`](#elemento-headhead)
    + [`<body></body>`](#elemento-bodybody)
    + [Identado](#identado)
    + [`<img></img>`](#elemento-img-src-alt)
+ [Consola de desarrolladores](#consola-de-desarrolladores)
+ [Elemento `<form></form>`](#elemento-formform)
    + [`<label></label>`](#elemento-labellabel)
    + [`<input>`](#elemento-input)

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

![Sintaxis de un elemento](/media/SintaxisHTML1.svg "Sintaxis de un elemento")

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

### Elemento `<img src="" alt="">`
Es el elemento que maneja las imágenes y veremos ahora el concepto de "atributo" em HTML.

* **atributo** es información complementaria que se le dá a un elemento para poder mostrarse en el navegador.

![Sintaxis con Atributos](/media/SintaxisConAtributos.svg "Sintaxis con Atributos")

En este caso el elemento `img` necesita el atributo *source* `src=""` Que es la ruta de dónde se encuentra la imagen, y el atributo *alternative* `alt=""` Que es el texto alternativo que aparecerá si la imagen no se carga exitosamente.

El 90% de los elementos html tienen un elemento de apertura y uno de cierre.

![](/media/SintaxisHTML1.svg)

El elemento `img` se cierra a sí mismo, no tiene una etiqueta de cierre, simplemente se lo cierra `>`.
```html
<body>
  <img src="/media/SintaxisConAtributos.svg" alt="Sintaxis con atributos de un elemento html">
</body>
```
En caso de no mostrarse la imagen nos aparecerá el texto escrito en el atributo `alt` (Sintaxis con atributos de un elemento html)

> Siempre que se utilice el elemento `img` a parte del `src` necesario para la ruta de la imagen, debemos colocar el atributo 
> `alt`, si por algún motivo nuestra imagen no se carga exitosamente, el texto debe ser descriptivo a la imagen que se utiliza.

El tener un elemento `img` correctamente escrito ayuda al usuario y al navegador a manejarse en nuestra página y a posicionarla en el buscador. De igual manera podemos tener una imagen enlazada a nuestro `src` que puede estar alojada en algún servidor web, un enlace relativo.

Si tenemos una imagen muy grande y se sale de nuestra pantalla de navegador o al contrario es muy chica, nosotros podemos agregar atributos como `width=""` que es el ancho, y/o `height=""` que es el alto de dicha imagen.

## Consola de desarrolladores

Cada navegador tiene su propia consola de desarrollador, en mi caso utilizo el de Microsoft Edge con la tecla rápida F12.
Es muy útil para ver los elementos y cómo funcionan. Si nosotros hacemos click derecho e inspeccionar veremos que carga el documento html en el que estamos trabajando, podremos visualizar el `title`, `head`, `body` y todos los elementos que tengamos en dicho documento.

Digamos que necesitamos modificar alguna parte de nuestro documento HTML, en caso que queramos cambiar algún aspecto referido a nuestro `h1` podemos buscarlo en nuestra consola, en el apartado de ``elementos`` y hacer cambios en tiempo real, nos sirve para hacer pruebas antes de modificarlo en el editor. La consola es un entorno para editar código en tiempo real, con CSS aparece la pestaña de ``styles`` y en el apartado de consola podremos ver cómo se comporta el conjunto entero ente HTML, CSS y JavaScrip.

### NOTA:
Debemos tener en cuenta que los cambios en consola de desarrollador no se guardan los cambios, para guardar los cambios debemos ir a nuestro IDE y guardar ahí el trabajo.

---

## Elemento `<form></form>`

Se pueden ver varios elementos dentro del elemento `form` de formulario,

Un formulario se utiliza para crear un formulario de contacto, formulario de pedir información, debemos pensarlo como si fuera un elemento que nos permite interactuar, o que otra persona nos envíe información de cualquier tipo, Como cuando nos inscribimos en algo, o tener un acceso, eso es un elemento `form`.

Empecemos conociendo el concepto de elementos anidados, en el cual se crea el nivel del `form` y dentro se empieza a crear las etiquetas `tags` y los campos que necesitamos que el usuario complete:

### Elemento `<label></label>`

El elemento `label` define una etiqueta para los elementos del formulario.

El ``<label>`` es útil para los usuarios de lectores de pantalla, porque el lector de pantalla leerá en voz alta la etiqueta cuando el usuario se centre en el elemento de entrada.

```html
<body>
  <form action="">
    <label for="nombre">Nombre</label>
    <label for="apellido">Apellido</label>
    <label for="mail">E-mail</label>
  </form>
</body>
```
El ``for`` atributo de la etiqueta ``label`` debe ser igual al atributo **id** del elemento `input` para unirlos.

Bien, estas son las etiquetas `label` en donde tenemos que acompañar estos elementos con el elemento `input`

### Elemento `<input>`
El elemento HTML ``input``se usa para crear controles interactivos para formularios basados en la web con el fin de recibir datos del usuario.
Hay disponible una amplia variedad de tipos de datos de entrada y *widgets* de control, que dependen del dispositivo y el agente de usuario (**user agent**). El elemento ``<input>`` es uno de los más potentes y complejos en todo HTML debido a la gran cantidad de combinaciones de tipos y atributos de entrada.

Nosotros necesitamos que el usuario ingrese texto a nuestro formulario, por lo que indicaremos que el tipo `type` de `input` que vamos a crear es de `type=text`, y lo combinamos con el atributo `placeholder` para dar una ayuda visual al usuario.

```html
<body>

  <form action="">
    <label for="">Nombre</label>
    <input type="text" placeholder="Ingrese su nombre">
    <label for="">Apellido</label>
    <input type="text" placeholder="Ingrese su apellido">
    <label for="">E-mail</label>
    <input type="email" placeholder="Ingrese su mail">
    <label for="">Password</label>
    <input type="password" placeholder="Ingrese su password">
  </form>

</body>
```
Si nosotros investigamos más a fondo, podemos notar que existe el `type="email"`, al igual que el `type="password"` y muchas variedades más, es recomendable buscar el que necesitamos a ver si existe por *default* antes de ingresarlo nosotros mismos.

Podemos ver que el formulario se va renderizando en horizontal, lo arreglaremos más adelante, vayamos viendo el funcionamiento que tenemos actualmente.

**Atributos opcionales `input`**

* **`name`**: El nombre que tendrá el input.
* **`value`**: Valor que tiene el input.
* **`type`**: Tipo de input (text | checkbox | number | password | radio | e-mail).
* **`disabled`**: Estado deshabilitado.

Un desarrollador web tiene que dominar correctamente un formulario.

Ahora veremos cuestiones un poco mas técnicas que un desarrollador web FrontEnd lo tiene que dominar, aún teniendo conocimiento de BackEnd y se le agregue lo que hace falta cuando el usuario envíe la información al servidor, del otro lado "BackEnd" se procese y se envíe a una base de datos, a un correo o donde necesitemos que se envíe y se procese.

**Atributos opcionales `label`**

* **`for`**: El ``id`` del input al que acompaña la etiqueta que los enlaza.

Entonces, hablando de buenas prácticas, cuando nosotros creamos un formulario debemos sumar el atributo `action=""` que es el que define a que página vamos a mandar esto cuando el usuario envíe la información.

```html
<body>

  <form action="action_page.php" method="get">

    <label for="nombre">Nombre</label>
    <input type="text" id="nombre" name="nombre" placeholder="Ingrese su nombre">

    <label for="apellido">Apellido</label>
    <input type="text" id="apellido" name="apellido" placeholder="Ingrese su apellido">

    <label for="email">E-mail</label>
    <input type="email" id="e-mail" name="e-mail" placeholder="Ingrese su e-mail">

    <label for="password">Password</label>
    <input type="password" id="password" name="password" placeholder="Ingrese su password">

  </form>

</body>
```
**Atributos opcionales `form`**

* **`action`**: URL hacia donde se enviará la respuesta al formulario.
* **`method`**: Método HTTP que se usará al enviar el formulario, generalmente se trabaja con `"post"`.
* **`name`**: Nombre del formulario.

Agreguemos ahora un `type"submit"` para enviar el formulario
```html
  <form action="action_page.php" method="get">

    <label for="nombre">Nombre</label>
    <input type="text" id="nombre" name="nombre" placeholder="Ingrese su nombre">

    <label for="apellido">Apellido</label>
    <input type="text" id="apellido" name="apellido" placeholder="Ingrese su apellido">

    <label for="email">E-mail</label>
    <input type="email" id="e-mail" name="e-mail" placeholder="Ingrese su e-mail">

    <label for="password">Password</label>
    <input type="password" id="password" name="password" placeholder="Ingrese su password">

    <input type="submit" value="enviar">

  </form>
```
Si nosotros llenamos y enviamos notaremos que la página se recarga y que aparece un signo de interrogación en el enlace, esto sucede porque cuando el método `get` envía la información al servidor, manda las variables en el URL. Lo que pasa si los datos llenados no aparecen es porque no se colocaron los datos en las variables `name`, porque el usuario está ingresando un valor y este valor es el cómo se va a llamar la variable en la cual va a viajar el nombre. Seamos coherentes con los ``name`` que se ponen, si se crea un `input` para que el usuario ingrese su nombre, el `name` debería ser `nombre`.

Ahora, esto esta bien, pero si nosotros trabajaremos con contraseñas no utilizaremos el `method="get"`, por eso en BackEnd se utiliza más el `method="post"`.

## Botones `<button></button>`
```html
<button type="button">Hacer click</button>
```
**Atributos opcionales**

* **`disabled`**: Estado deshabilitado.
* **`type`**: Tipo fr botón (button | reset | submit).
* **`title`**: tooltip.
* **`name`**: El nombre que tendrá el botón.


```html
```
```html
```
```html
```
```html
```

---

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/README.md "Desarrollo de páginas Web")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/01.1ElementosDeBloqueDeLinea.md "Elementos de Bloque y elementos de Línea")

[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[_Subir_ **&#11165;**](#estructura-de-un-proyecto-web "Ir al título")

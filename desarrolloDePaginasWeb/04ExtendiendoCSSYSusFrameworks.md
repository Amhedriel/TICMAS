# Extendiendo CSS y Frameworks

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/03.1SelectoresTipografiasIDClass.md "Capa de Presentación II")
[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/05AlojamientoYTipoDeServidores.md "Alojamiento y Tipo de Servidores")

---
En este módulo se trabajará con los conceptos clave del *responsive web design*. Aprenderás cómo transformar tu página web, originalmente solo para *desktop*, en *ful-responsive*; es decir, que se adapte a cualquier dispositivo y que siga visualizando correctamente.

Después de esto, avanzaremos con los *frameworks* más populares del mercado, de manera tal que, habiendo entendido los conceptos más importantes, puedas utilizarlos para avanzar rápidamente en el desarrollo *full-responsive*.

Ahora veremos un paso muy importante de quiebre en lo que es el desarrollo de una página web, este es el tema del *Responsive Web Design*

## Responsive Web Design
De que trata el *Responsive Web Design*?

*Responsive Web Design* es lo que le permite a cualquier usuario que acceda ya sea con una computadora, un celular, una tablet, etc. poder ver correctamente esa página web.

Con *Responsive Web Design* nosotros vamos a estar trabajando únicamente con HTML y CSS.

Primero debemos ver algunas cuestiones conceptuales que tenemos que entender, lo primero es justamente qué es el *Responsive Web Design*, esto es: que nosotros podamos visualizar tanto en escritorio, tablet, celular, Smart TV. La idea es que independientemente cual sea el tamaño de la pantalla en la que se visite nuestro sitio web, se tenga que visualizar como corresponde.

Diseño para la mejor experiencia de todos los Usuarios:

![](/media/ResponsiveDesign.svg)

Para avanzar con la parte técnica, debemos conocer algunos elementos.

### Meta Viewport 
El *Viewport* es una de las etiquetas más representativas de la web móvil, que nos permite configurar cómo debe interpretar una página el navegador web para móviles.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
El `viewport` define el área visible de una página web. Nos va a ayudar, que desde el HTML poder definir cual es el ancho que queremos tomar en función del dispositivo que ingrese en nuestro sitio web.

En HTML5 se introduce justamente el elemento `<meta name="viewport" content="width=device-width, initial-scale=1.0">` que es el que nos va a definir, el ancho de pantalla que vamos a tomar: `content="width=device-width, initial-scale=1.0"` y la escala inicial que vamos a definir.
Sin el elemento `meta name="viewport"` ya tendríamos una traba para poder hacer nuestro sitio responsive, con lo cual, veamos en html cómo se ve esto:

* Mostraremos unos ejemplos que dan en [W3Schools](https://www.w3schools.com/tags/tag_meta.asp "Ir a W3Schools"), la cual tiene un ejemplo sin la etiqueta `meta` de la ventana gráfica y otro con la etiqueta `meta` de ventana gráfica

Podemos verlos e inspeccionarlos con la consola del desarrollador y ponerle la vista de celular, veremos que la imagen que está simulando ser una pantalla de celular, podemos ver que la imagen de la página se hace muy pequeña, pero con el otro ejemplo, simulando la misma pantalla del teléfono, pero con el `<meta name="viewport" content="width=device-width, initial-scale=1.0">` habilitado, nos podemos fijar cómo cambia la disposición de la imagen en relación con el tamaño de la pantalla.

hagamos un ejemplo nuestro para que se vea la implementación:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <title>Sin Viewport</title>
</head>
<body>
  <p>Para poder entender mejor este ejemplo se lo debe mirar en una pantalla de teléfono o tablet</p>
  <img src="https://www.w3schools.com/css/img_chania.jpg" alt="Calle vacía">

  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus quo nam deleniti at reiciendis corrupti ex culpa quaerat molestiae quibusdam maxime distinctio esse voluptate reprehenderit, similique ad corporis vero delectus! Eos commodi possimus sequi debitis dolores tenetur autem harum minus impedit ducimus ut sunt accusamus vero quisquam mollitia quo ipsam eveniet sint in, illum laudantium vitae. Pariatur libero vero maiores porro quaerat est eaque veritatis, ratione excepturi eius explicabo debitis, sequi at aliquam, earum quidem beatae. Consectetur, iste quaerat. Qui deleniti a harum laudantium officia expedita voluptate architecto modi velit non unde nobis error minus amet praesentium quae id commodi, quidem ea, dolor corporis nostrum. Asperiores tempore facilis sequi tenetur quidem ullam accusantium itaque possimus cum. Maxime quaerat deserunt amet.</p>
</body>
</html>
```
Con esto podemos llegar a entender el porqué del `<meta name="viewport" content="width=device-width, initial-scale=1.0">`.

La clave del aprendizaje es, no solo de observar lo que se tiene en diferentes páginas que nos ayudan como referencia, la clave está en la implementación, que es cuando nosotros lo implementamos en un documento .html, recordemos que el *responsive design* es de HTML y CSS.

No es necesario memorizarnos todos los `tags`, no tiene mucho sentido justamente porque los editores de texto ya vienen con una plantilla armadita con lo que vamos a necesitar para trabajar, en este caso con *responsive web design*.

```html
<!DOCTYPE html>
<html lang="es">

  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <!-- Aqui tenemos definido el name="viewport" que dice: tomá el ancho del dispositivo "width=device-width" cual escala inicial es de aspecto 1.0 "initial-scale=1.0" -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Con Viewport</title>
  </head>

  <body>
    <p>Para poder entender mejor este ejemplo se lo debe mirar en una pantalla de teléfono o tablet</p>
    <img src="https://www.w3schools.com/css/img_chania.jpg" alt="Calle vacía">

    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus quo nam deleniti at reiciendis corrupti ex
      culpa quaerat molestiae quibusdam maxime distinctio esse voluptate reprehenderit, similique ad corporis vero
      delectus! Eos commodi possimus sequi debitis dolores tenetur autem harum minus impedit ducimus ut sunt accusamus
      vero quisquam mollitia quo ipsam eveniet sint in, illum laudantium vitae. Pariatur libero vero maiores porro
      quaerat est eaque veritatis, ratione excepturi eius explicabo debitis, sequi at aliquam, earum quidem beatae.
      Consectetur, iste quaerat. Qui deleniti a harum laudantium officia expedita voluptate architecto modi velit non
      unde nobis error minus amet praesentium quae id commodi, quidem ea, dolor corporis nostrum. Asperiores tempore
      facilis sequi tenetur quidem ullam accusantium itaque possimus cum. Maxime quaerat deserunt amet.</p>
  </body>
</html>
```
O sea, lo que hace es tomar el ancho de pantalla en este ejemplo visto desde una virtualización de un celular con la consola del desarrollador, lo está tomando al 100%, por lo tanto la imagen que cuando no se trabajaba con el `viewport` no tomaba el ancho de pantalla completo, ahora ´si lo hace.

Hay algunas aclaraciones cuando uno trabaja con el *responsive web design* que hay que ir teniendo en cuenta,, una de esas es:

* Nunca hagas un sitio responsivo en el cual el usuario tenga que scrollear nunca tenga que ser de izquierda a derecha o viceversa, el scrollear siempre debe ser de arriba hacia abajo y viceversa, hacer eso empeora la experiencia de usuario.

Continuando con las aclaraciones, hay más cuestiones conceptuales que tenemos que entender, si trabajamos con una lista de "grilla" (*CSS grid*), que es tomar un tamaño del ancho de pantalla y a esta pantalla la vamos a dividir en columnas, y así de a poquito hay que empezar a pensar en columnas.

A ver, yo tengo una página y por lo general lo que se hace es trabajar con una grilla `grid` que dependiendo del *Framework* que vayamos a implementar, debemos ser consientes que cada uno de los *Frameworks* trabajan con una grilla de determinada cantidad de columnas. Visualizamos el porqué se trabaja con columnas.

Nosotros diremos, cuando esté trabajando en *desktop* quiero que este elemento tome 12 columnas, cuando esté trabajando en *phone* tome 3 columnas, obviamente debemos estar pensando en columnas en función de la grilla total, por lo general la grilla suele estar entre 12 a 16 columnas y tiene un ancho total del 100%, a medida que el usuario achica o agranda la pantalla, se tiene que ir re adaptando y eso es lo que lo hace responsivo a la pantalla en la cual se está visualizando.

![](/media/GridDesktop.svg)

Veamos el cómo se hace un sitio responsivo.

## Construir una grilla responsiva

Para poder construir una grilla responsiva, o sea, que nosotros podamos definir una grilla mediante CSS, cuánto queremos que abarque cada columna, para eso lo que debemos hacer es definir:

```css
*{
  dox-sizing: border-box;
}
```
Con esto se garantiza que el `padding` y el `border` estén incluidos en el total del ``width`` y el ``height`` de los elementos, lo que pasaría sin esto es, que este espacio no estará contemplado y cuando coloquemos un porcentaje se nos agrandará más de lo esperado por eso es que se define.

Trabajando con responsivo, considerando como reglas de oro:

  * *meta viewport*
  * trabajar con asterisco `*`

```CSS
.menu{
  /* Con esto, lo que define es que el elemento de la izquierda va a tener 25% y va a estar flotando en el margen izquierdo*/
  width: 25%;
  float: left;
}
  /* El contenido principal va a tener un ancho del 75%  y también flotará en el margen izquierdo  */
.main{
  width: 75%;
  float: left;
}
```
El código para un mejor entendimiento:

```html
<!DOCTYPE html>
<html lang="en">

  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="/styles/grid.css">
    <title>Grid CSS</title>
  </head>

  <body>

    <div class="header">
      <h1>Chania</h1>
    </div>

    <div class="menu">
      <ul>
        <li>The Flight</li>
        <li>The City</li>
        <li>The Island</li>
        <li>The Food</li>
      </ul>
    </div>

    <div class="main">
      <h1>The City</h1>
      <p>Chania is the capital of the Chania region on the island of Crete. The city can be divided in two parts, the
        old town and the modern city.</p>
      <p>Resize the browser window to see how the content respond to the resizing.</p>
    </div>

  </body>

</html>
```
El CSS

```CSS
* {
  box-sizing: border-box;
}

.header {
  border: 1px solid red;
  padding: 15px;
}

.menu {
  width: 25%;
  float: left;
  padding: 15px;
  border: 1px solid red;
}

.main {
  width: 75%;
  float: left;
  padding: 15px;
  border: 1px solid red;
}
```
En el ejemplo podemos ver que a la izquierda de la página está el `menu`, y en la consola del desarrollador nos muestra las propiedades:

```CSS
.menu {
  width: 25%;
  float: left;
  padding: 15px;
  border: 1px solid red;
}
```
Y si comparamos con el `main` notamos que los dos flotan hacia la izquierda, cosa que no se puede porque se estuvieran sobre poniendo uno sobre de otro, por lo cual, primero se posiciona uno, luego viene el siguiente.

Por último, si nosotros quisiéramos construir una grilla propia, lo que debemos definir es cuántas columnas queremos que tenga esa grilla, en el ejemplo que veremos corresponde a una grilla estándar de 12 columnas:

```css
.col-1 {width: 8.33%;}
.col-2 {width: 16.66%;}
.col-3 {width: 25%;}
.col-4 {width: 33.33%;}
.col-5 {width: 41.66%;}
.col-6 {width: 50%;}
.col-7 {width: 58.33%;}
.col-8 {width: 66.66%;}
.col-9 {width: 75%;}
.col-10 {width: 83.33%;}
.col-11 {width: 91.66%;}
.col-12 {width: 100%;}
```
Aquí hace que, el 100% de la pantalla se debe dividir por 12 columnas = 8.33%, por lo tanto cada columna debe tener un ancho de 8.33%

Con esta medida definimos que la clase de columna 1 `.col-1` debe tener el ancho de 8.33% `{width: 8.33%}` y vamos sumando columna por columna, recordar que para cada una de las cantidades de columnas, una clase que acompañe y defina cual es el ancho que debe abordar.

## Media queries
Las *media queries*("consultas de medios") son útiles cuando deseas modificar tu página web o aplicación en función del tipo de dispositivo, o de características y parámetros específicos (como la resolución de la pantalla o el ancho del ``viewport`` del navegador)

Es una regla de CSS que va a incluir propiedades si algún tipo de condición es verdadera, consisten de un tipo de medio opcional y una o más expresiones de características de medios. Varias consultas se pueden combinar utilizando operadores lógicos. No distinguen entre mayúsculas y minúsculas.

Sintaxis:

```CSS
@media (max-width: 600px) {
  .facet_sidebar {
    display: none;
  }
}
```
En este ejemplo, se define una clase que solo aplicará para dispositivos cuyo ancho máximo tengan 600px.

Nosotros estuvimos trabajando con CSS y aún no estábamos pensando en que dispositivo estamos apuntando, era para cualquier pantalla, justamente lo que hacen HTML5 y CSS3 es esta regla de `@media`.

Le decimos al navegador que está ingresando sea celular, monitor, tablet, smart tv; que reglas queremos que aplique para cuando entre la pantalla en cuestión, no es lo mismo una pantalla de hasta 600 px que entre una computadora conn una resolución de 1300 px.

En el ejemplo haremos que, cuando entre una pantalla, cuyo ancho máximo sea de hasta 600px el color de fondo tiene que ser celeste, si no aplica un verde claro:

```CSS
body{
  background-color: lightgreen;
}
@media only screen and (max-width: 600px){
  body {
    background-color: lightblue;
  }
}
```
Aqui podemos asociar el concepto de responsivo al tamaño de pantalla, acá lo podemos ver a 600px de ancho, 600px o menos será celeste, 601px a más será de color verge claro.

Si hacemos un recuento de las cosas que estuvimos repasando, HTML estructura, CSS diseño y *responsive*.

Veamos ahora todos los `@media` en [MDN](https://developer.mozilla.org/es/docs/Web/CSS/Media_Queries/Using_media_queries "Ir a la página de MDN") donde vamos a tener la documentación ofical

```html
<!-- CSS media query on a link element -->
<link rel="stylesheet" media="(max-width: 800px)" href="example.css" />

<!-- CSS media query within a style sheet -->
<style>
@media (max-width: 600px) {
  /* Aquí utilizamos clases */
  .facet_sidebar {
    display: none;
  }
}
</style>
```
### **`and`**
El operador `and` es usado para colocar múltiples funciones multimedia. Un query básico con el tipo de medio especificado como `all` puede lucir así:

    @media (min-width: 700px) {...}

Si se quiere aplicar query si la pantalla está en formato horizontal, usted puede utilizar el operador `and` y colocar:

    @media (min-width: 700px) and (orientation: landscape) {...}

la siguiente query solo retorna verdadero si la ventana tiene un ancho de 700px o más y la pantalla esta en formato horizontal. Ahora si usted quiere aplicar esta opción solo si tipo de medio es TV, usted puede utilizar la siguiente cadena:

    @media tv and (min-width: 700px) and (orientation: landscape) {...}

Esta query solo se aplica si el tipo de medio es TV, la ventana tiene 700px de ancho o mas y la pantalla esta en formato horizontal.

No olvidar que para cada pantalla en la que estemos trabajando debemos definir las clases que queremos aplicar. Esto supone mucho tiempo de desarrollo, con lo cual debemos considerar lo siguiente, cuando se trabaje en un proyecto y un cliente nos diga, quiero un proyecto *full responsive*.

## Full Responsive

Están hablando de dispositivo, celular, tablet y escritorio.

Una buena práctica es empezar a diseñar empezando por el de celular, luego tablet y así hasta arriba, pero si el cliente dice que quiere los `@media` todos tuyos (todos desarrollados), y eso lleva mucho tiempo, porque nosotros debemos armar para cada dispositivo como se va a ver el sitio (estructura), la capa de presentación CSS, pero es un CSS por cada dispositivo, por familia de tamaño estándar de pantalla a la que estemos apuntando, recomendación es: que se cotice correctamente un proyecto de esa magnitud, porque es mucho tiempo de desarrollo, y lo segundo es preguntar si es posible utilizar alguna librería *full responsive*. Cuando digo librería *full responsive* vamos a encontrar en el mercado, [Bootstrap](https://getbootstrap.com/ "Ir a la página oficial de Bootstrap") y nos va a permitir con definiciones de clases, crear sitios responsivos sin tener que andar escribiendo todos los `@media` para todos, lo mismo sucede con [Foundation](https://get.foundation/ "Ir a la página oficial de Foundation") y recientemente con [Tailwind](https://tailwindcss.com/ "Ir a la página oficial de Tailwind"). 

Acá lo importante o que se recomienda mucho, es que una vez visto todo lo básico para hacer un sitio *full responsive*, entonces lo primero que tenemos que tener en cuenta es la parte teórica, de esa parte teórica ya sabemos `viewport` y `@media`, sabiendo esto ya podemos crear cualquier sitio responsivo sin usar una librería, pero, cuál es el beneficio con estas librerías?, que ya vienen un montón de clases dadas y nosotros podemos trabajar, de hecho en tema de grillas con Bootstrap todo eso ya lo trae resuelto.

Una sugerencia es, investigar, lo que no se puede saber es el tema de *viewport*, `grid` y `@media`, de ahí para adelante se puede conocer, Googlear si hay mas *Frameworks*, y lo otro muy importante es seguirlos en redes sociales, para ir viendo cómo se van actualizando, que es lo nuevo que se puede hacer, que es lo que no estamos pudiendo hacer, porque cada proyecto que se realice, va a ser distinto y las especificaciones de cada uno va a cambiar, habrán clientes flexibles que dejen trabajar con librerías. lo cual nos permitirá ahorrar muchísimo tiempo.

### **``**
### **``**
```
```
```
```


---

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/03.1SelectoresTipografiasIDClass.md "Capa de Presentación II")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/05AlojamientoYTipoDeServidores.md "Alojamiento y Tipo de Servidores")


[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[_Subir_ **&#11165;**](#extendiendo-css-y-frameworks "Ir al título")
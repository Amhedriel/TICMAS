# Capa de presentación

  [**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/02.1webSemantica.md "Capa de presentación")
  [_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
  [Siguiente **&#129042;**](/desarrolloDePaginasWeb/03.1SelectoresTipografiasIDClass.md "Capa de Presentación II")
  
  ---

* [CSS](#css "CSS")
* [Sintaxis](#sintaxis "Sintaxis de CSS")
* [Elemento **`<style></style>`**](#elemento-stylestyle "Elemento style")
* [Estilos internos](#estilos-internos "Estilos internos")
* [Estilos en línea](#estilos-en-línea "Estilos en línea")
* [Externo](#externo "Estilo externo")
* [Comentarios](#comentarios "Comentarios en CSS")
* [CSS Box Model](#css-box-model "Modelo de caja")
    * [Content](#content "Content")
    * [Padding](#padding "Padding")
    * [Border](#border "Border")
    * [Margin](#margin "Margin")
* [Manipulación de propiedades por sectores](#manipulación-de-propiedades-por-sectores "Manipulación de propiedades por sectores")
* [Cierre](#cierre "Cierre")

En este módulo aplicaremos estilos a los documentos HTML, de manera tal que puedas diseñar  tus páginas con color, tipografías, espaciados y demás personalizaciones.

La capa de presentación, aplicada a través de CSS, te permitirá customizar los documentos y hacer diseños a medida. Verás las distintas formas de aplicar CSS, Buenas prácticas, *box model*  y conceptos clave para seguir adelante.

Hasta ahora se estuvo trabajando con la estructura del cómo escribir correctamente un documento HTML, ahora profundizaremos con la capa de presentación, para que la página web comience a tener un diseño más amigable y como nosotros lo queremos.

## CSS

CSS *(Cascading Styles Sheets)* u Hojas de Estilos en Cascada, nos va a permitir aplicar los estilos que nosotros queremos, de manera selectiva a los elementos HTMl.

## Sintaxis

Tenemos 3 formas de insertar una hoja de estilo:

* CSS Interno
* CSS en Línea
* CSS Externos

Digamos que nosotros queremos dar algo de estilo a uno de nuestros elemento de HTML, como ejemplo, queremos que nuestro título principal `h1{}` tenga letras de color azul `color: blue;` y el tamaño de fuente tenga 12 pixeles de tamaño `font-size: 12px;`

<br>

![](/media/SintaxisCSS.svg)

Hagamos un nuevo ejemplo pero con código y desde un documento .css.

Lo que haremos en un principio es utilizar un nuevo elemento para enmarcar lo que van a ser las propiedades de nuestro elemento HTML.

## Elemento **`<style></style>`**

Es un elemento necesario para poder tener estilos CSS, dentro de nuestro documento HTML o fuera del mismo, que sería el método más recomendado.

```html
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS</title>

  <style>
    h1{color: blue; font-size: 12px;}
  </style>
  
</head>
<body>
    <h1>El título principal</h1>

  <p>Este es un párrafo.</p>

  <h2>Un título secundario o subtítulo</h2>

  <p>Otro párrafo</p>
</body>
```
Veremos que nuestro elemento ``h1`` Es azul y tiene un tamaño de 12 px.

En la consola del desarrollador podemos ver, en la parte derecha de la consola la pestaña de **Styles** lo que nos permitirá ver y hacer cambios en las propiedades y valores de cada elemento que tengamos en CSS.

No es necesario aprenderse todas las propiedades de CSS, como ayuda se puede utilizar esta [referencia](https://htmlcheatsheet.com/css/ "HTML cheat-sheet")

## Estilos internos
Se puede usar una hoja de estilo interna si una sola página HTML tiene un estilo único.

El estilo interno se define dentro del elemento `<style></style>`, en la sección de `<head></head>`.

Ahora agregaremos algunos elementos a nuestro documento html.

```HTML
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS</title>
  <style>
    h1{
      color: blue;
      font-size: 12px;
    }

    p{
      color: red;
    }

  </style>
</head>
<body>
  <h1>El título principal</h1>

  <p>Este es un párrafo.</p>

  <h2>Un título secundario o subtítulo</h2>

  <p>Otro párrafo</p>
</body>
```
En este caso le dijimos que al elemento `p` le queremos aplicar el color rojo `red` a su contenido.

Ahora cambiaremos el `h1` para que tenga una mejor presentación.

```css
    h1{
      color: blue;
      font-weight: bold;
    }
```
Cual es el problema con esto?, que si creamos un nuevo documento .html y necesitamos que su `h1` y sus `p` tengan las mismas propiedades y valores, tendríamos que escribirlos de nuevo en cada una de los documentos que vayamos creando.

Crear estilos internos se considera una mala práctica, cuando se tiene más de un documento html que generalmente al desarrollar páginas web no tendremos unicamente un documento html, habrán muchos y con diferentes valores.

## Estilos en línea
Se utiliza un estilo en línea para aplicar un estilo a un solo elemento.

Para usar estilos en línea, agregue el atributo de estilo al elemento relevante. El atributo de estilo puede contener cualquier propiedad CSS.

No es la mejor práctica, porque esto no solamente queda atado a el elemento y se complica estar escribiendo propiedades css dentro de los elementos HTML, ya que la idea de CSS es poder reutilizar el código que se escribe.

```html
<body>
  <h1 style="color: cyan; font-weight: bold; border: 1px solid;">El título principal</h1>

  <p style="color: coral;">Este es un párrafo.</p>

  <h2>Un título secundario o subtítulo</h2>

  <p style="color: coral;">Otro párrafo</p>
</body>
```
A fines prácticos podemos observar directamente el HTML con el CSS que le estamos aplicando.

## Externo
Lo ideal es tener hojas de estilo externas que nos sirva para las múltiples páginas html que nosotros tengamos.

Se recomienda crear una carpeta en el proyecto, de manera estándar se lo llama ``styles``, en este directorio nosotros meteremos todos los archivos que vienen a ser nuestras hojas de estilos, dentro de este archivos creamos un archivo con nombre: ``styles.css`` que se diría que es el estándar.

CSS no es un lenguaje de marcado, es un documento que referencie a las etiquetas de HTML.

Ahora lo que debemos hacer es referenciar el archivo externo recién creado al mismo documento HTML: `<link rel="stylesheet" type="text/css" href="/styles/styles.css"/>` en el `head`:

```html
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Enlazar una hoja de estilos CSS al documento html -->
  <link rel="stylesheet" type="text/css" href="/styles/styles.css" />

  <title>CSS</title>
</head>
<body>
  <h1>El título principal</h1>

  <p>Este es un párrafo.</p>

  <h2>Un título secundario o subtítulo</h2>

  <p>Otro párrafo</p>
</body>
```
Lo que vemos es el elemento `<link>` que se conecta con una hoja de estilo ``rel="stylesheet"`` que es de tipo texto de css `type="text/css"` y lo referenciamos en dónde se encuentra nuestro archivo .css `href="styles/styles.css"`, la URL puede ser absoluta o relativa, en este caso es justamente esta última.

Este es el documento css:

```css
h1 {
  color: blue;
  font-weight: bold;
}

p {
  color: red;
}
```

Ahora, revisando el documento HTML podemos observar que estamos trabajando con CSS desde el archivo .css, al utilizar *Live Server* podemos observar que ya tiene los estilos que colocamos en el documento de CSS.

Los beneficios son el poder reutilizar código, si creáramos otro documento .html en nuestro proyecto, le agregáramos el vínculo de nuestro archivo .css veríamos que sus elementos tendrían las mismas propiedades que tenemos definidas en la hoja de estilos externa.

Podemos inspeccionar los elementos con la consola del desarrollador en la pestaña de *styles* y ver las propiedades que les está aplicando a los elementos, lo que nos está mostrando en que documento están definidas esas propiedades, además de información como en qué líneas están definidas esas propiedades dentro de ese documento, con *click* nos lleva a ver ese documento.

Recordemos que podemos hacer cambios en esta consola y probar cambios que queramos probar.

## Comentarios

Para poder tener comentarios en los documentos de CSS debemos encerrar los mensajes entre `/*` y `*/` como en JS
```css

/*
Esto es un comentario dentro de CSS
*/ 
```
Al desarrollar páginas web es necesario comentar y separar código para poder tener un orden, asi ayudarnos o ayudar a quienes vean nuestro código fuente.

---

## CSS Box Model
Ahora veremos el modelo de cajas o *CSS Box Model* que es el cómo consideramos a todos los elementos dentro de CSS. Todos los elementos de HTML pueden ser considerados como cajas.

Podemos ver una página web y empezar a dividir sus apartados o secciones por cajas, si observamos la de [w3schools](https://www.w3schools.com/css/ "Ir a W3C") podemos observar la barra de navegación es una caja, el menú lateral izquierdo es otra, el contenido central es otro y el margen derecho es otra columna. Estas cajas tiene en común una serie de propiedades:

* **Content**
* **Padding**
* **Border**
* **Margin**

![](/media/BoxModel.svg)
Ahora explicaremos un poco sobre estos *shorthands*

### Content
Creamos un nuevo documento .html con un elemento `h1`, enlacemos a nuestro documento de estilos `<link rel="stylesheet" type="text/css" href="/styles/styles.css" />`
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" type="text/css" href="/styles/styles.css" />
  <title>CSS: Box Model</title>
</head>
<body>
  <h1>Este es un título</h1>
</body>
</html>
```
Cuando se habla del **contenido** en *Box Model* es el "contenido" que tiene ese elemento HTML dentro de sí mismo, en este caso es un título.

### Padding
El **padding** viene a ser como una sección transparente, es un área limpia al rededor del contenido, es todo lo que está entre el contenido y la parte imaginaria transparente hasta llegar al **borde**.

### Border

El **border** es justamente un borde o línea que encierra o lo que encapsula al **padding** y al **content**.

### Margin

El **Margin** es un área transparente que se encuentra por fuera del **border**, rodeando al **padding** y al **content**.

Si nosotros revisamos con *Live Server* el documento HTML que creamos, abrimos la consola del desarrollador y nos posicionamos sobre el elemento `h1` podemos dejar el puntero quieto hasta que aparezca la información emergente de nuestro elemento, donde nos Muestra las propiedades CSS que tenemos habilitadas, nosotros tomábamos las propiedades de *Box Model* como nos venía por defecto en el navegador, a partir de ahora nosotros somos los que le vamos a dar estas propiedades y asignarles los valores que nosotros queremos.

Por ahora solamente estamos trabajando cambiando el color en hexadecimal, la tipografía que por ser el título principal tiene 32px, Y el **margin**, que es el área naranja que aparece tanto arriba como abajo del contenido.

Lo importante es pensar que todos los elementos son cajas a las cuales les vamos a ir aplicando las propiedades y valores que nosotros queramos a través de CSS.

Ahora queremos que el ``border`` del título principal con un grosor de 1px, sea visible y de color negro; el `padding` sea de 5px, el `margin` de 30px

```css
h1 {
  color: blue;
  font-weight: bold;
  border: 1px solid black;
  padding: 5px;
  margin: 30px;
}
```
Yendo a la página podemos ver los cambios realizados, para entender más podemos ver el elemento con la consola de desarrollo; hacer algunos ejemplos pueden ayudar a la comprensión con diferentes elementos.

De momento nosotros, al revisar la página, podemos observar el *Box Model* de nuestro elemento `h1`, primero el "contenido", que es lo que escribimos en él `Este es un título`, con el "padding" que separa del texto del "borde" con un tamaño de 5px, rodeando este "padding" podemos ver el "borde" que tiene 1px de ancho arriba, derecha, abajo e izquierda (en sentido de las agujas del reloj),, que es visible y estático `solid` y de color negro `black`, y sobre de este "borde" se encuentra el "margen" que separa al elemento `h1` por 30px en las 4 direcciones. Todo esto se puede modificar, se recomienda revisar la documentación oficial de [w3schools](https://www.w3schools.com/css/ "Ir a W3C") o de [Mozilla](https://developer.mozilla.org/es/docs/Learn/CSS "Ir a Mozilla") y probar los diferentes valores que se les pueden dar a las propiedades que se mostraron en el ejemplo anterior.

## Manipulación de propiedades por sectores

Una manera de poder manipular este *Box Model*  cada lado por separado de la caja, arriba, derecha, abajo, izquierda, es decir a cada uno de los 4 lados posibles separados, digamos: el margen superior que sea de 5px y el margen inferior que sea de 30px, esto es posible si indicamos en las propiedades de CSS el lado que quiere especificar, como dijimos, un `margin`:

```css
/* valor para margen arriba */
  margin-top: ;

/* valor para margen derecho */
  margin-right: ;

/* valor para margen abajo */
  margin-bottom: ;

/* valor para margen izquierdo */
  margin-left: ;
```
A estas propiedades les podemos dar valores distintos y estos se verán reflejados en la página HTML vinculada.

```CSS
h1 {
  color: blue;
  font-weight: bold;
  border: 1px solid black;
  padding: 5px;
  /* Valores personalizados de margin por cada lado */
  margin-top: 40px;
  margin-right: 10px;
  margin-bottom: 20px;
  margin-left: 10px;
}
```
Cuando vemos el documento con la consola del desarrollador nos fijamos que ya no está igual en todos sus lados, fijémonos en el contorno naranja, arriba que es el más grande tenemos 40px, a la derecha 10px, abajo 20 y a la izquierda 10px. Es posible hacer lo mismo con `padding`:

```CSS
h1 {
  color: blue;
  font-weight: bold;
  border: 1px solid black;
  padding: 5px;
  /* Valores personalizados de margin por cada lado */
  margin-top: 40px;
  margin-right: 10px;
  margin-bottom: 20px;
  margin-left: 10px;
  /* Valores personalizados de padding por cada lado */
  padding-top: 20px;
  padding-right: 20px;
  padding-bottom: 15px;
  padding-left: 15px;
}
```
Recargamos la página y volvemos a inspeccionar el elemento, vemos que ahora tenemos padding con los valores que indicamos arriba 20px, derecha 20px, abajo 15px e izquierda 15px.

Por lo general, como para tener una regla memo técnica es: arriba, derecha, abajo e izquierda, así es como se leen el orden de las propiedades, y otra opción de definir todo esto, si nos fijamos en el `margin` del elemento nos dice: `margin 40px 10px 20px`, este shorthand nos indica que: el `top` es de 40px, el 10px es por el lado derecho `right` e izquierdo `left` y el `bottom` es de 20px, aparecen 3 valores y no 4 a diferencia de `padding`, lo que sucede es que ambos lados són iguales `left`\/`right` por lo tanto su notación puede ser más corta. 

Podemos hacer todos estos cambios en `padding` cambiando sus valores con una sola línea con su *short hand* `padding: 20px 15px 20px 15px;` que representas las 4 direcciones con cada valor es sentido delo reloj, `top`, `right`, `bottom`, `left`. Pero aún podemos escribirlo de manera más corta y tener el mismo resultado:

```css
h1 {
  color: blue;
  font-weight: bold;
  border: 1px solid black;
  padding: 5px;
  /* Valores personalizados de margin por cada lado */
  margin-top: 40px;
  margin-right: 10px;
  margin-bottom: 20px;
  margin-left: 10px;
  /* Valores personalizados de padding por cada lado */
  padding: 20px 15px
}
```
Con este último `padding: 20px 15px;` Estamos haciendo lo mismo que con el `padding` anterior.

Ahora trabajaremos en un elemento `section`

```html
<body>
  <h1>Este es un título</h1>
  <section>
    
  </section>
</body>
```
Veamos el CSS

```CSS
section{
  width: 300px;
  border: 15px solid green;
  padding: 50px;
  margin: 20px;
}
```
Podemos ver que el contenido del elemento `section` está vacío, pero aún asi le estamos aplicando con CSS varias propiedades: ``width: 300px;`` - `border: 15px solid green;` - `padding: 50px;` - `margin: 20px;`

Si miramos nuestra página, lo que estamos viendo es justamente cómo empiezo a darle formato a estas cajas, utilizamos el elemento `section` y a este elemento le aplique algunas propiedades, y esas propiedades se ven reflejadas en la página web.

Para ir dejando conceptos que son la base de todo lo que sigue, es entender el modelo de cajas es fundamental al momento de trabajar con CSS, porque dentro de este `section` cómo ejemplo llegaríamos a tener más elementos dentro, como por ejemplo:

```html
<body>
  <section>
    <h1>Este es un título</h1>
    <!-- El Lorem Ipsum ayuda mucho para relleno de contenido -->
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, consequatur illum nisi adipisci, non sit eum vel dolorum quibusdam nemo libero laudantium quia minus recusandae cumque repellendus, maxime molestias nihil.
    Nostrum debitis hic velit. Modi repellendus obcaecati exercitationem nobis, ducimus harum, illum autem commodi eaque repellat assumenda tempora quod dicta ad, quidem doloremque optio reprehenderit reiciendis aliquam ratione voluptatum debitis.
    Cum esse molestias ex itaque facere corporis facilis optio ullam consequatur eligendi nemo rerum fuga dolorum nisi, eos iste vitae sapiente dolore. Aliquam at autem quasi alias. Minus, ipsum soluta.</p>
    <ul>
      <li>Elemento 1</li>
      <li>Elemento 2</li>
      <li>Elemento 3</li>
    </ul>
  </section>
</body>
```
Volvemos a nuestra página y nos fijamos como ahora es más visual lo que estamos haciendo, porque ahora comenzamos a trabajar con cajas adentro de cajas, por eso es tán importante el entender el *Box Model*, porque con el modelo de cajas nosotros vamos a empezar a entender que propiedades le aplicamos a cada caja, que espacios queremos que tome cada una de esas cajas y cómo lo vamos posicionando con las propiedades de CSS, con este ejemplo básico armamos la caja `section` y adentro colocamos otras cajas `h1` con sus respectivas propiedades, `p` otra caja con propiedades propias igualmente, y una lista desordenada `ul` con sus respectivos índices `li` que aún no tienen modificadas sus propiedades.

## Cierre

Lo ideal sería seguir practicando, imaginar y bajar a papel cómo estructurar el CV que vamos a desarrollar y empezar a pensar en cuáles van a ser las cajas que van a estar conformando ese documento, una vez terminada la estructura (HTML) pasaremos a la capa de presentación (CSS) para darle un poco de diseño y que visualmente se vea mejor que sólo teniendo por defecto el lenguaje de marcado.
```
```

---

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/02.1webSemantica.md "Capa de presentación")
 [Siguiente **&#129042;**](/desarrolloDePaginasWeb/03.1SelectoresTipografiasIDClass.md "Capa de Presentación II")


[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[_Subir_ **&#11165;**](#capa-de-presentación "Ir al título")

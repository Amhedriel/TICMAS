# Capa de presentación
En este módulo aplicaremos estilos a los documentos HTML, de manera tal que puedas diseñar  tus páginas con color, tipografías, espaciados y demás personalizaciones.

La capa de presentación, aplicada a través de CSS, te permitirá customizar los documentos y hacer diseños a medida. Verás las distintas formas de aplicar CSS, Buenas prácticas, *box model*  y conceptos clave para seguir adelante.

Hasta ahora se estuvo trabajando con la estructura del cómo escribir correctamente un documento HTML, ahora profundizaremos con la capa de presentación, para que la página web comience a tener un diseño más amigable y como nosotros lo queremos.

## CSS

CSS *(Cascading Styles Sheets)* u Hojas de Estilos en Cascada, nos va a permitir aplicar los estilos que nosotros queremos, de manera selectiva a los elementos HTMl.

## Sintaxis
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

```
```
```
```

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/02.1webSemantica.md "Capa de presentación")
[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/04ExtendiendoCSSYSusFrameworks.md "Extendiendo CSS y Frameworks")

---

---

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/02.1webSemantica.md "Capa de presentación")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/04ExtendiendoCSSYSusFrameworks.md "Extendiendo CSS y Frameworks")


[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[_Subir_ **&#11165;**](#capa-de-presentación "Ir al título")
ubuntu-release-upgrader-core

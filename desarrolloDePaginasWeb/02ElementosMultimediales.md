# Elementos Multi Mediales
[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/01.1ElementosDeBloqueDeLinea.md "Elementos de Bloque y elementos de Línea")
[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/03CapaDePresentaci%C3%B3n.md "Capa de presentación")

---
Módulo 1

* Elementos multimedia
    * Video
    * Audio
    * Insertar video de You Tube

# HTML multimedia

Lo que se denomina multimedia en la web es audio, música, videos y animaciones.

Las páginas web suelen contener elementos multimedia de diferentes tipos y formatos.

## **`video`**

Veamos como implementar esta etiqueta.

El elemento `video`, muestra un video en HTML.

```html
  <title>Video HTML</title>
</head>
<body>
  <video width="320" height="240" controls>
    <source src="/movie.mp4" type="video/mp4">
    <source src="/movie.webm" type="video/webm">
    Tu navegador no soporta la reproducción del video.
  </video>
</body>
```

Tomamos el atributo ``src`` del tag ``<video>`` y en su lugar incluimos elementos separados ``<source >`` que apuntan a sus propias fuentes. En este caso el browser irá a los elementos ``<source >`` y reproducirá el primero de los elementos que el codec soporte. Incluir fuentes WebM y MP4 debería bastar para reproducir el video en la mayoría de los browsers en estos días.

Nosotros podemos controlar el tamaño del reproductor de video con el ancho `width=""` y el alto `height=""` e incluso colocar algunos más, en este caso utilizamos `controls`.


### Atributo **`autoplay`**
Un atributo booleano; el video comenzará a reproducirse automáticamente tan pronto como sea posible, sin detenerse para terminar de cargar los datos.

Un poco molesto si tiene el sonido habilitado, últimamente los navegadores lo reproducen automáticamente pero sin audio.

### Atributo **`buffered`**
Un atributo que se puede leer para determinar qué intervalos de tiempo del multimedia se han almacenado en buffer. Este atributo contiene un objeto ``TimeRanges``.

### Atributo **`controls`**
Le permite al usuario controlar la reproducción de video, incluyendo volumen, búsqueda y pausar/reanudar reproducción; maximizar, descargar, velocidad de reproducción y *picture and picture*, al menos en el navegador *Edge* y *Chrome*.

### Atributo **`height`**
La altura del área de visualización del vídeo en píxeles CSS.

### Atributo **`loop`**
Un atributo booleano; si se especifica, al alcanzar el final del video, buscaremos automáticamente hasta el principio.

### Atributo **`muted`**
Un atributo booleano que indica por defecto el audio del video. si está, el audio será inicialmente silenciado

### Atributo **`preload`**
El objetivo de este atributo enumerado es proporcionar una sugerencia al navegador 
sobre qué cree el autor que llevará a la mejor experiencia para el usuario.

  * **`none`**: sugiere bien que el autor cree que el usuario no tendrá que consultar ese video, bien que el servidor desea minimizar su tráfico; es decir, esta sugerencia indica que no se debe almacenar en caché este video.

  * **`metadata`**: sugiere que aunque el autor piensa que el usuario no tendrá que consultar este video, es razonable capturar los metadatos (p. ej. longitud).

  * **`auto`**: sugiere que el usuario necesita tener prioridad; es decir, esta sugerencia indica que, si es necesario, se puede descargar el video completo, incluso aunque el usuario no vaya a usarlo.

  * **`empty string`**: que es un sinónimo del valor auto, y será mostrado si el browser desde el que se está accediendo a la página no soporta el elemento \<video>, permitiéndonos proveer un fallback para browsers más antiguos. Puede ser de la manera que se quiera; en este caso proporcionamos un link directo al archivo de video, por lo que el usuario puede al menos acceder de alguna manera, independientemente del browser que esté usando..

Si no está configurado, su valor predeterminado está definido por el navegador, aunque la especificación aconseje que se establezca a ``metadata``.

### Atributo **`poster`**
Una URL que indica un marco de póster para mostrar el resultado hasta que el usuario reproduzca o busque. Si este atributo no se especifica, no se muestra nada hasta que el primer cuadro está disponible, entonces se muestra el primer marco como el marco de póster.

### Atributo **`src`**
La URL del vídeo que se va a insertar. Es opcional; podrás optar, en su lugar, por el elemento \<source> dentro del bloque de vídeo para especificar el video que se va a incrustar.

### Atributo **`width`**
La anchura del área de visualización del vídeo en píxeles CSS.

Las compensaciones de tiempo se especifican actualmente como valores float que representan el número de segundos que se va a compensar.

## Videos externos
Podemos utilizar el URL para enlazar nuestro documento.

```html
  <title>Video HTML</title>
</head>
<body>
  <video width="320" height="240" controls>
    <source src="/movie.mp4" type="video/mp4">
    <source src="https://www.youtube.com/watch?v=5Mv5xoz08Mo&t=1s" type="ytvideo/mp4">
    Tu navegador no soporta la reproducción del video.
  </video>
</body>
```
Se recomienda tener 2 videos iguale con 2 formatos distintos, por si tiene incompatibilidad con alguno de estos.
---

[**&#11176;** _Anterior_ &#11007;](/desarrolloDePaginasWeb/01.1ElementosDeBloqueDeLinea.md "Elementos de Bloque y elementos de Línea")
[Siguiente **&#129042;**](/desarrolloDePaginasWeb/03CapaDePresentaci%C3%B3n.md "Capa de presentación")

[_Volver_ **&ldca;**](/desarrolloDePaginasWeb/README.md "Regresar a página Principal")
[_Subir_ **&#11165;**](#elementos-multi-mediales "Ir al título")

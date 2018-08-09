title: Web Components
output: index.html
controls: false

--

# Web Components
## ¡El HTML ha muerto, Larga vida al HTML!

--

### El 'por qué' de los Web Components

Los web components son un estándar del W3C que **nos permiten desglosar el desarrollo de aplicaciones web** en pequeños contenedores agnósticos que encapsulan *marcado*, *código JavasScript* y *estilos CSS*, recibiendo el nombre de componentes.

Esto nos permite **reutilizarlos en diferentes partes de nuestras aplicaciones** y también para exponer nuestros servicios en otras aplicaciones con simplemente un tag HTML.

--

### Elementos de un Web Component

* Templates

* Custom Elements

* Shadow DOM

* HTMLImports

--

### Templates

Los Templates son un elemento de HTML5 que nos permiten crear plantillas para presentar los datos, y son nativos del navegador. En nuestro HTML tendríamos algo como lo siguiente:

```html
<template id="profileTemplate">

  <div class="profile">

    <img src="" class="profile__img">

    <div class="profile__name"></div>

    <div class="profile__social"></div>

  </div>

</template>
```

--

### Custom Elements

Los Custom Elements o elementos personalizados nos permiten **definir nuestro propio etiquetado de elemento HTML**

```html
<template id="profileTemplate">
  <div class="profile">
    <img src="" class="profile__img">
    <div class="profile__name"></div>
    <div class="profile__social"></div>
  </div>
</template>

<script>
  var MyElementProto = Object.create(HTMLElement.prototype);
  window.MyElement = document.registerElement('user-profile', {
    prototype: MyElementProto
    // other props
  });
</script>
```

--

### Shadow DOM

El Shadow DOM es el DOM que **encapsula nuestro componente**. No pertenece al DOM original del documento o página web, si no que se encuentra dentro del componente que hemos creado. Tiene su propio ámbito de ejecución y su propio estilo CSS. Piensa en ello como un DOM anidado al DOM primario de la página.

en el inspector web veriamos algo como esto:

```html
▾<user-profile>
  ▾#shadow-root (user-agent)

  <div class="profile">
    <img src="" class="profile__img">
    <div class="profile__name"></div>
    <div class="profile__social"></div>
  </div>

 </user-profile>
```

--

### HTML Imports

Al igual que en CSS podemos importar archivos externos con *@import* y en JavaScript usando *require*, con HTML Imports podemos importar ficheros HTML que contengan los web components.

```html
<link rel="import" href="user-profile.html">

```

--

### Beneficios de los Web Components

En esencia, un componente es una pieza de código preelaborado que encapsula alguna funcionalidad expuesta a través de interfaces estándar. Los componentes son los *ingredientes de las aplicaciones*, que se juntan y combinan para llevar a cabo una tarea.

--

#### El paradigma de ensamblar componentes y escribir código para hacer que estos componentes funcionen se conoce como Desarrollo de Software Basado en Componentes. El uso de este paradigma posee algunas ventajas:

* Reutilización del software

* Simplifica las pruebas.

* Simplifica el mantenimiento del sistema.

* Mayor calidad.

--

### Frameworks

A través de **Polyfills** podemos utilizar el estándar en prácticamente cualquier navegador y combinándolos con la librería **Polymer** (también desarrollada por Google) o **Stencil.js** (desarrollada por el equipo de ionic) nos permite crear web components de una forma sencilla, compartirlos y utilizarlos en los navegadores.

--

## Gracias!

![Gracias](thanks.gif)
# Box Shadow CSS3

CSS3 incluye una propiedad denominada `box-shadow` que nos permite establecer a un elemento el efecto de sombra.

```css
.elemento {
box-shadow: 2px 2px 5px #999;
}
```

Desafortunadamente, esta propiedad sólo está disponible en los navegadores que más se preocupan por los estándares. El navegador Safari incluye la propiedad con el nombre `-webkit-box-shadow` y Firefox 3.1 la incluye con el nombre `-moz-box-shadow`.

```css
.elemento {
  -webkit-box-shadow: 2px 2px 5px #999;
  -moz-box-shadow: 2px 2px 5px #999;
}
```

Por su parte, el navegador Internet Explorer dispone de su propio mecanismo para crear sombras. La solución se basa en el uso de los filtros, un mecanismo que no forma parte del estándar de CSS y que permiten aplicar operaciones complejas a los elementos de la página.

```css
.elemento {
  filter: shadow(color=#999999, direction=135, strength=2);
}
```
# Como lo usamos.

Para nuestro ejemplo solo usaremos la propiedad CSS3 `box-shadow`, para ello definiremos un elemento `div` y le asignaremos la clase `.elem-shadow`; nos permitirá agregarle propiedades generales a este elemento.

También asignaremos a nuestro elemento div las clases `.top`, `.right`, `.bottom`, `.left`, `.all` sgún corresponda; esto nos permitirá decidir la dirección de la sombra.

Esto nos quedía de la siguiente manera:

#### HTML.

```html
<!--Sombra en la parte superior-->
<div class="elem-shadow top">
    <span>TOP</span>
</div>

<!--Sombra lado derecho del elemento-->
<div class="elem-shadow right">
    <span>RIGHT</span>
</div>

<!--Sombra en la parte inferior del elemento-->
<div class="elem-shadow bottom">
    <span>BOTTOM</span>
</div>

<!--Sombra lado izquierdo del elemento-->
<div class="elem-shadow left">
    <span>LEFT</span>
</div>

<!--Sombra al rededor de todo el elemento-->
<div class="elem-shadow all">
    <span>ALL</span>
</div>
```

#### Styles.

```css
.elem-shadow {
	height: 160px;
	width: 280px;
	margin: 20px;
	border: 1px solid #ccc;

	line-height: 160px;
	white-space: nowrap;
	text-align: center;

	display: inline-block;
}

.elem-shadow span {
	font-family: 'Arial';
	font-weight: 700;
	font-size: 40px;
	color: #ccc;
}

.top {
	box-shadow: 0 -5px 5px -5px #666;
}

.right {
	box-shadow: 5px 0 5px -5px #666;
}

.bottom {
	box-shadow: 0 5px 5px -5px #666;
}

.left {
	box-shadow: -5px 0 5px -5px #666;
}

.all {
	box-shadow: 0 0 5px #666;
}
```

También hay una técnica para generar sombras con imagenes pero ese es otro tema, ademas ya es pasado de moda.

Saludos;
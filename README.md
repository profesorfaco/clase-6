# Fran <3
### Clase 6

#### Resumen 

Primero nos acercamos a **HTML** explorando algunas etiquetas (*tags*) y sus correspondientes atributos, para poder definir [los elementos HTML](https://developer.mozilla.org/es/docs/Web/HTML/Elemento) que, a su vez, definen los contenidos de cada página web.

Entre los elementos explorados hay una grupo particular que no podemos descuidar, que son los metadatos. Con ellos podemos hacer definiciones claves respecto de los caracteres y la proporción de ventana de navegador que utilizará nuestra página web. Con ellos también podemos presentar la página para ser ubicada por los buscadores y compartida en redes sociales (https://megatags.co/).

Luego nos acercamos a **CSS** explorando [distintas propiedades](https://developer.mozilla.org/es/docs/Web/CSS/Referencia_CSS#%C3%8Dndice_de_palabras_clave), con sus correspondientes valores, para poder definir las reglas CSS que, a su vez, definen la visualización de los contenidos de cada página web. 

Sumamos también, desde CSS, la posibilidad de usar familias tipográficas específicas con https://fonts.google.com/ y https://fontawesome.com/, que se aprovechan de la regla [@font-face](https://css-tricks.com/snippets/css/using-font-face/)

Estas exploraciones las hemos facilitado mediante Bootstrap: *framework* para el diseño de sitios y aplicaciones web *responsive*, que ofrece la definición previa de una amplia gama de componentes, que podemos consultar en https://getbootstrap.com/docs/4.3/getting-started/introduction/

Muchos de los componentes de Bootstrap requieren el uso de JavaScrip para funcionar. Específicamente, requiere de las bibliotecas jQuery, Popper y una biblioteca de Bootstrap.

#### jQuery

Entre las bibliotecas de JavaScript que se utilizan en Bootstrap, la más popular es jQuery. Esta biblioteca nos permite simplificar la manera de manipular el DOM, para agregar interacción y dinamismo a cada página web.

La sintaxis de jQuery, simplificada, es `$(selector).acción()`

El signo `$` indica el uso de jQuery
El `(selector)` indica qué elemento(s) será(n) afectado(s)
La `acción()` después del punto indica el modo en que se afectará(n) tal(es) elementos

Por ejemplo, puedo escribir `$(".test").hide()` para indicar que quiero esconder (*hide*) a todos los elementos con clase `test`. ¿Pero bajo qué condiciones quiero esconderlos? Esa condición aún no la defino, y podría hacerlo de la siguiente manera:
 
```
$("button").click(function(){
  $(".test").hide(1000);
});
```

Esto dice que al presionar el botón, se esconda (*hide*) todo elemento con clase `test`, y que eso se demore 1000 milisegundos.

Una recomendación para el uso de jQuery es escribirlo en un contexto que asegure que el documente esté completamente cargado:

```
$(document).ready(function(){

  // escribe lo que quieras aquí dentro

});
```

Y como jQuery es una biblioteca de JavaScript, corresponde "adjuntarla" al documento donde se le quiera usar, y luego complementarla con el uso específico requerido, entre las etiquetas `<script></script>`, por ejemplo:

```
<button type="button">¡Desaparece!</button>
<p class="test">Creo que voy a desaparecer</p>

<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>

<script>
$(document).ready(function(){
	$("button").click(function(){
	  $(".test").hide(1000);
	});
});
</script>
```


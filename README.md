# 1. Selectores
Un selector CSS es el patrón que indica al navegador qué elementos HTML deben recibir los estilos definidos en una regla, estos pueden ser simples o compuestos. Además cuando múltiples reglas coinciden con un mismo elemento la especificidad define qué regla va a prevalecer. 
## 1.1 Selectores simples 
Los selectores simples son la unidad más básica de selección en CSS. Según la especificación oficial del W3C (Selectors Level 3, 2018), un selector simple describe una condición única que un elemento debe cumplir para ser seleccionado.

De acuerdo con Grant (2017), los selectores simples se dividen en:

- ## *Selectores de tipo*
También denominado selector de etiqueta o elemento, ya que aplica estilos a todos los elementos de un mismo tipo (párrafos, títulos, divs, etc.).
 *Ejemplo.*
Si se desea que todos los párrafos tengan el mismo color de texto y tamaño de letra, se usaría: 
```css
p {
  color: blue;
  font-size: 16px;
}
```
 - ## *Selectores de clase*
Sirve para aplicar estilos a uno o varios elementos HTML que tengan el mismo atributo class, comienza con un punto (.)
 *Ejemplo.*
Se implementan 3 clases, "importante" tiene definido el texto en rojo y negrita, "nota" texto en azul e inclinado, "advertencia" texto con fondo amarillo.
```css
 .importante {
  color: red;
  font-weight: bold;
 }
 .nota {
  color: blue;
  font-style: italic;
}
 .advertencia {
  background-color: yellow;
  color: black;
  padding: 5px;
}
```
- ## *Selectores de ID*
El selector de ID en CSS se escribe con "#" seguido del nombre del identificador. A diferencia del selector de clase, un ID es único y solo puede asignarse a un elemento dentro de la página, lo que permite seleccionarlo y aplicarle estilos específicos de forma exclusiva.
  *Ejemplo*
Se dan 2 tipo de ID, "titulo-principal" y "parrafo-destacado", cada uno con sus especificaciones.
```css
   #titulo-principal {
  color: darkgreen;
  font-size: 32px;
  text-align: center;
}
#parrafo-destacado {
  background-color: lightyellow;
  border: 2px solid orange;
  padding: 10px;
}
 ```
- ## *Selector universal*
Se indica con un asterisco (*). Selecciona todo el contenido del documento. 
*Ejemplo*
```css
 * {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
color: greenyellow;
}
```
- ## *Selector de atributo*
 Selecciona elementos que tienen un atributo específico, con la opción de filtrar por valor.
 *Ejemplo*
 ```css
/* Todos los enlaces que terminan en .pdf */
a[href$=".pdf"] {
  color: red;
  font-weight: bold;
}

/* Todos los enlaces externos (que empiezan con https) */
a[href^="https"] {
  color: green;
}
```

## 1.2 Selectores compuestos
Los selectores compuestos en CSS surgen de la combinación de dos o más selectores simples que se aplican sobre un mismo elemento. Según Haverbeke (2018) , estos selectores permiten aumentar la especificidad.

Según W3C (2018) y Grant (2017), los selectores compuestos pueden tomar varias formas:

- Elemento + Clase
```css
p.intro {
  font-size: 18px;
  color: darkblue;
}
```
- Elemento + ID
```css
h1#titulo {
  text-align: center;
  color: crimson;
}

 ``` 
- Varios atributos
 ``` css
input[type="text"][required] {
  border: 2px solid blue;
  background-color: #eef;
}
 ```
- Cadena de clases
``` css
.btn.primario.grande {
  background-color: green;
  color: white;
  padding: 10px 20px;
}

/* Botón con clases: btn + secundario + chico */
.btn.secundario.chico {
  background-color: gray;
  color: white;
  padding: 5px 10px;
}
```
## 1.3 Especificidad
La especificidad es el algoritmo que utiliza el navegador para decidir qué valor de propiedad se aplica a un elemento. La especificidad se basa únicamente en las reglas de coincidencia, compuestas por diferentes tipos de selectores CSS (MDN Web Docs, 2024).
Es decir, la especificidad es un cálculo que determina qué estilo se aplica cuando varias reglas coinciden sobre el  mismo elemento.
## 1.3.1 Jerarquía de especificidad

Los estilos en línea tienen la mayor especificidad. Además, los ID son más específicos que las clases, los atributos y las pseudoclases, que a su vez son más específicos que los elementos y los pseudoelementos (FreeCodeCamp, 2021).

[![Orden de especificidad](https://cms-assets.tutsplus.com/uploads/users/30/posts/34141/image/spec-02.svg "Orden de especificidad")](https://cms-assets.tutsplus.com/uploads/users/30/posts/34141/image/spec-02.svg "Orden de especificidad")

## 1.3.2 Cómo se calcula 
La especificidad se calcula como un valor de cuatro partes (a, b, c, d). Los estilos en línea contribuyen a A, los ID a B, las clases/atributos/pseudoclases a C, y los nombres de elementos/pseudoelementos a D (GeeksforGeeks, 2022).
- Ejemplo
```css
/* Selector de tipo → especificidad (0,0,0,1) */
p {
  color: blue;
}
/* Selector de clase → especificidad (0,0,1,0) */
.aviso {
  color: green;
}
/* Selector de dos clases → especificidad (0,0,2,0) */
.aviso.destacado {
  color: orange;
}
/* Selector de ID + tipo → especificidad (0,1,0,1) */
#contenedor p {
  color: red;
}
```
## 1.3.3 Importancia 
En (Web Docs, 2024) menciona que comprender la especificidad es crucial para dominar CSS, ya que permite a los desarrolladores predecir cómo los cambios en la hoja de estilo afectarán la representación final de la página.
## 2. Propiedades de texto y fuentes
Las propiedades de texto y tipografía en CSS permiten controlar la presentación, legibilidad y estética del contenido web. 
## 2.1 Propiedades de texto 
Las propiedades de texto en CSS abarcan la manipulación de alineación, espaciado, decoración y transformación.
- color: define el color del texto, esencial para el contraste y accesibilidad.
- text-align: controla la alineación del contenido (left, right, center, justify).
- text-decoration: permite aplicar decoraciones como subrayado, tachado o sobrelínea.
- text-transform: gestiona mayúsculas y minúsculas (uppercase, lowercase, capitalize).
- letter-spacing: define la distancia entre caracteres.
- line-height: establece la altura de línea, influyendo en la legibilidad.
- word-spacing: controla la distancia entre palabras.
white-space: regula cómo se muestran los espacios y saltos de línea.

```css 
.texto1 {
  text-align: center;       
  text-transform: uppercase;
  color: darkblue;     
}

.texto2 {
  text-decoration: underline; 
  letter-spacing: 2px;       
  color: green;
}

.texto3 {
  text-align: justify;   
  line-height: 1.8;      
  color: #555;            
}
```
## 2.2 Propiedades de fuentes
Las propiedades de fuente determinan la tipografía, el tamaño, el grosor y el estilo del texto.
- font-family: establece la tipografía; puede usar fuentes genéricas (serif, sans-serif, monospace) o personalizadas.
- font-size: controla el tamaño de la fuente, puede expresarse en px, em, rem, %.
- font-style: define variantes como normal, italic o oblique.
- font-weight: controla el grosor, desde valores numéricos (100–900) hasta palabras clave (normal, bold).
- font-variant: habilita versalitas (small-caps).
- font: propiedad abreviada que permite definir varias características en una sola línea.
Grant (2017) menciona que las  propiedades de las fuentes establecen la base tipográfica de un diseño. La elección del tamaño y el grosor de la fuente es crucial no solo para la imagen de marca, sino también para la legibilidad y la accesibilidad.

```css 

.texto1 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 18px;       
  font-weight: bold;     
}


.texto2 {
  font-family: "Times New Roman", serif; 
  font-size: 1.2em;      
  font-style: italic;    
  font-variant: small-caps; 
}
```

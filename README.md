# 1. Selectores simples, compuestos y especificidad
Un selector CSS es el patrón que indica al navegador qué elementos HTML deben recibir los estilos definidos en una regla, estos pueden ser simples o compuestos. Además cuando múltiples reglas coinciden con un mismo elemento la especificidad define qué regla va a prevalecer. 
## 1.1 Selectores simples 
## 1.1.1 Selectores de tipo
También denominado selector de etiqueta o elemento, ya que aplica estilos a todos los elementos de un mismo tipo (párrafos, títulos, divs, etc.).
- *Ejemplo.*
Si se desea que todos los párrafos tengan el mismo color de texto y tamaño de letra, se usaría: 
```css
p {
  color: blue;
  font-size: 16px;
}
```
## 1.1.2 Selectores de clase
Sirve para aplicar estilos a uno o varios elementos HTML que tengan el mismo atributo class, comienza con un punto (.)
- *Ejemplo.*
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
## 1.1.3 Selectores de ID
El selector de ID en CSS se escribe con "#" seguido del nombre del identificador. A diferencia del selector de clase, un ID es único y solo puede asignarse a un elemento dentro de la página, lo que permite seleccionarlo y aplicarle estilos específicos de forma exclusiva.
- *Ejemplo*
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
## 1.1.4 Selector universal
Se indica con un asterisco (*). Selecciona todo el contenido del documento. 
- *Ejemplo*
```css
 * {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
color: greenyellow;
}
```
## 1.2 Selectores compuestos
Un selector compuesto es una secuencia de selectores simples que se mezclan sin cin combinar intermedios, es decir todos los selectores simples se aplican simultáneamente al mismo elemento. 
- Elemento + Clase
```css
p.intro {
  font-size: 18px;
  color: darkblue;
}
```
- ELEMENTO + ID
```css
h1#titulo {
  text-align: center;
  color: crimson;
}

 ``` 

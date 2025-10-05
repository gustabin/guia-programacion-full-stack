2.3. Introducción a CSS3: selectores, propiedades y unidades
2.3.1. ¿Qué es CSS3?
CSS3 (Cascading Style Sheets, nivel 3) es la tercera versión de CSS y permite definir cómo se va a mostrar el contenido en una página web. CSS3 amplía y mejora las funcionalidades de sus versiones anteriores con nuevas propiedades y características para lograr una mayor flexibilidad y control sobre el diseño de la página.
2.3.2. Selectores en CSS
Los selectores son patrones utilizados para seleccionar los elementos HTML a los que se les aplicarán los estilos definidos en las reglas CSS.
Tipos de selectores
Selector de elemento (tipo): Se selecciona un tipo de elemento HTML.
p {
    color: blue;
}
Este ejemplo selecciona todos los elementos <p> y les aplica el color azul.
Selector de clase: Se selecciona un grupo de elementos que comparten una clase.
.mi-clase {
    font-size: 18px;
} 
Los elementos que tienen la clase mi-clase aplicarán el estilo indicado.
Selector de ID: Se selecciona un único elemento con un ID específico.
#mi-id {
    background-color: yellow;
}

Solo el elemento con el ID mi-id tendrá el fondo amarillo.
Selector universal: Se seleccionan todos los elementos dentro de la página.
* {
    margin: 0;
    padding: 0;
}

Este selector aplica el estilo a todos los elementos HTML, eliminando los márgenes y rellenos por defecto.
Selectores combinados:
Selector de descendiente: Aplica el estilo a los elementos dentro de otro.
div p {
    color: green;
}

Los elementos <p> dentro de un <div> serán de color verde.
Selector de hijo directo: Se seleccionan elementos que son hijos directos de otro.
div > p {
    color: red;
}
Solo los elementos <p> que son hijos directos de <div> tendrán el color rojo.
Selector de atributo: Se seleccionan elementos con un atributo específico.
a[href] {
    color: orange;
}

Este selector selecciona todos los elementos <a> que tienen el atributo href y les aplica un color naranja.
Propiedades en CSS
Las propiedades de CSS definen qué características o aspectos de los elementos HTML se van a modificar. Cada propiedad tiene un valor asociado que puede ser modificado para conseguir el diseño deseado.
Propiedades comunes
1.	Color y Fondo
color: Define el color del texto.
background-color: Define el color de fondo de un elemento.
p {
    color: red;
    background-color: yellow;
}
 
2.	Tipografía
font-family: Define la fuente del texto.
font-size: Define el tamaño de la fuente.
font-weight: Define el grosor de la fuente.
p {
    font-family: Arial, sans-serif;
    font-size: 16px;
    font-weight: bold;
}

3.	Espaciado
margin: Define el espacio exterior de un elemento (fuera del borde).
padding: Define el espacio interior de un elemento (dentro del borde).
div {
    margin: 20px;
    padding: 15px;
}

4.	Bordes
border: Define un borde alrededor de un elemento.
border-radius: Define el radio de las esquinas redondeadas de un elemento.
div {
    border: 2px solid black;
    border-radius: 10px;
} 
5.	Visualización
display: Define cómo se muestra un elemento.
block: El elemento ocupa toda la línea.
inline: El elemento ocupa solo el espacio necesario.
inline-block: Comportamiento mixto entre block e inline.
none: El elemento no se muestra.
div {
    display: block;
}

Unidades en CSS
Las unidades en CSS son los valores que se asignan a las propiedades. Existen diferentes tipos de unidades que se pueden usar según el contexto.
Unidades absolutas
px: Píxeles. Una unidad fija que no depende del tamaño de la pantalla.
pt: Puntos. Usada principalmente para impresoras.
Unidades relativas
em: Relativa al tamaño de la fuente del elemento actual.
rem: Relativa al tamaño de la fuente raíz (normalmente <html>).
%: Relativa al contenedor del elemento.
 
Unidades de vista
vw  (viewport width): 1% del ancho de la ventana de visualización.
vh (viewport height): 1% de la altura de la ventana de visualización.
vmin y vmax: 1% de la vista más pequeña (vmin) o más grande (vmax).
Ejemplo práctico
Vamos a ver un ejemplo sencillo usando los conceptos que hemos cubierto:
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ejemplo CSS3</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            font-size: 16px;
            background-color: lightgray;
            margin: 0;
            padding: 0;
        }
        h1 {
            color: #333;
            text-align: center;
        }
        p {
            color: #555;
            margin: 20px;
            padding: 15px;
            background-color: white;
            border: 1px solid #ccc;
            border-radius: 8px;
        }
        /* Media Query para pantallas pequeñas */
        @media (max-width: 600px) {
            body {
                font-size: 14px;
            }
            p {
                margin: 10px;
                padding: 10px;
            }
        }
    </style>
</head>
<body>
    <h1>Bienvenido al Curso de CSS3</h1>
    <p>Este es un párrafo de ejemplo para demostrar cómo se pueden aplicar estilos CSS3 a los elementos HTML.</p>
</body>
</html>

________________________________________
 
Resumen
En este tema hemos cubierto:
Los selectores CSS: para aplicar estilos a elementos específicos.
Las propiedades CSS: que permiten definir el estilo de los elementos (colores, tipografía, espaciado, etc.).
Las unidades CSS: tanto absolutas como relativas y cómo se usan para establecer valores en propiedades.
2.4. Diseño responsivo con media queries
2.4.1. ¿Qué es el diseño responsivo?
El diseño responsivo (o responsive design) es una técnica de diseño web que permite que las páginas web se adapten de manera eficiente a diferentes tamaños de pantalla y dispositivos, como computadoras de escritorio, tabletas y teléfonos móviles. El objetivo es ofrecer una experiencia de usuario consistente y óptima, sin importar el dispositivo que se esté utilizando para acceder al sitio web.
2.4.2. Media queries en CSS
Las media queries son una característica clave de CSS3 que permiten aplicar diferentes estilos CSS dependiendo de las características del dispositivo o la ventana del navegador, como su tamaño, orientación o resolución.
Sintaxis básica de una media query
@media (condición) {
  /* Estilos CSS que se aplicarán si se cumple la condición */
}

La condición es un test que verifica las características del dispositivo, como el ancho de la pantalla, la resolución o la orientación.
2.4.3. Condiciones comunes en media queries
1.	max-width y min-width: Estas condiciones permiten aplicar estilos CSS dependiendo del tamaño máximo o mínimo de la ventana del navegador.
max-width: Se aplica si el ancho de la ventana es menor o igual al valor especificado.
min-width: Se aplica si el ancho de la ventana es mayor o igual al valor especificado.
Ejemplo:
/* Si el ancho de la pantalla es menor o igual a 600px */
@media (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}

2.	orientation: Permite aplicar estilos según la orientación del dispositivo, ya sea landscape (horizontal) o portrait (vertical).
Ejemplo:
/* Si el dispositivo está en modo horizontal */
@media (orientation: landscape) {
    body {
        font-size: 1.5rem;
    }
}

3.	resolution: Se utiliza para ajustar los estilos según la resolución del dispositivo, como en pantallas de alta densidad de píxeles (por ejemplo, Retina).
Ejemplo:
/* Para pantallas de alta resolución */
@media (min-resolution: 2dppx) {
    img {
        width: 100%;
    }
}
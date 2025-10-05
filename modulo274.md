2.7.4. Ejercicio 4: Estilos avanzados con CSS3
Objetivo: Usar propiedades avanzadas de CSS3, como Sass/SCSS, CSS Grid y Flexbox para mejorar el diseño.
Instrucciones:
Crea un archivo de estilo SCSS (por ejemplo, styles.scss) y compílalo en un archivo CSS.
Usa variables SCSS para definir colores y márgenes.
Aplica CSS Grid para organizar las secciones de la página y Flexbox para alinear los iconos de FontAwesome de manera adecuada.
Ejemplo de código SCSS:
/* styles.scss */
$primary-color: #3498db;
$secondary-color: #2ecc71;
$padding: 20px;
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    padding: 0;
    margin: 0;
}
header {
    background-color: $primary-color;
    color: white;
    padding: $padding;
    text-align: center;
}
section {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    padding: $padding;
    background-color: white;
}
footer {
    background-color: $secondary-color;
    color: white;
    text-align: center;
    padding: $padding;
}

/* Estilos para los iconos */
i.fas {
    font-size: 30px;
    margin-right: 10px;
}

/* Responsive design */
@media screen and (max-width: 600px) {
    section {
        grid-template-columns: 1fr;
    }
}

2.7.5. Conclusión de los ejercicios
Estos ejercicios prácticos son una excelente manera de repasar y reforzar los conceptos del Módulo 2. Te permiten familiarizarte con la estructura básica de HTML, la creación de estilos CSS y la inclusión de iconos de FontAwesome. Al completarlos, habrás dado un paso importante en el desarrollo de páginas web interactivas y bien estructuradas.

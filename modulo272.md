2.7.2. Ejercicio 2: Diseño básico con CSS3
Objetivo: Crear un diseño simple con CSS3 que incluya selectores, propiedades, unidades y diseño responsivo con media queries.
Instrucciones:
Crea un archivo CSS llamado styles.css y vincúlalo a tu documento HTML.
Aplica estilos a la página web, utilizando selectores para aplicar diferentes estilos a los elementos <header>, <h1>, <section>, y <footer>.
Utiliza media queries para hacer que el contenido sea responsivo en pantallas pequeñas (como móviles).
Ejemplo de código CSS:
/* styles.css */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: white;
    padding: 20px;
    text-align: center;
}

h1 {
    margin: 0;
}

section {
    padding: 20px;
    background-color: #fff;
    margin: 10px;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px;
}

/* Diseño responsivo */
@media screen and (max-width: 600px) {
    header {
        font-size: 14px;
    }

    section {
        margin: 5px;
    }
}

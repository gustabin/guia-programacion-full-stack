2.2.1. ¿Qué Son las Etiquetas Semánticas?
Las etiquetas semánticas son aquellas que proporcionan significado sobre el contenido que contienen. A diferencia de las etiquetas genéricas (como <div> o <span>), las etiquetas semánticas describen el propósito del contenido, lo que mejora la accesibilidad, el SEO y la mantenibilidad del código.
Por ejemplo, en lugar de envolver un encabezado en un <div>, se debe usar la etiqueta <header> para indicar que es una sección de encabezado.
2.2.2. Principales Etiquetas Semánticas en HTML5
<header>: Representa la cabecera de un documento o sección. Generalmente contiene el logo, el título, los menús de navegación, etc.
<header>
    <h1>Bienvenidos a mi sitio web</h1>
    <nav>
        <ul>
            <li><a href="#">Inicio</a></li>
            <li><a href="#">Sobre nosotros</a></li>
            <li><a href="#">Contacto</a></li>
        </ul>
    </nav>
</header>

<footer>: Define el pie de página de un documento o sección. Usualmente contiene información como derechos de autor, enlaces de contacto, etc.
<footer>
    <p>&copy; 2025 Mi Página Web. Todos los derechos reservados.</p>
</footer>
<article>: Representa un contenido independiente y autónomo que podría ser distribuido de forma independiente. Se utiliza para entradas de blog, noticias, artículos, etc.
<article>
    <h2>Noticia Importante</h2>
    <p>Este es el contenido de la noticia...</p>
</article>

<section>: Representa una sección temática de un documento. Se utiliza para agrupar contenido relacionado. No debe confundirse con <div>, que es solo un contenedor genérico.
<section>
    <h2>Sobre Nosotros</h2>
    <p>Somos una empresa dedicada a...</p>
</section>
<nav>: Indica una sección de navegación. Se utiliza para agrupar enlaces de navegación.
<nav>
    <ul>
        <li><a href="#">Inicio</a></li>
        <li><a href="#">Servicios</a></li>
        <li><a href="#">Contácto</a></li>
    </ul>
</nav>
<aside>: Define contenido secundario o complementario que está relacionado con el contenido principal. Se utiliza para barras laterales o notas al margen.
<aside>
    <h3>Noticias Relacionadas</h3>
    <ul>
        <li><a href="#">Noticia 1</a></li>
        <li><a href="#">Noticia 2</a></li>
    </ul>
</aside>

<main>: Representa el contenido principal de un documento. Debería ser único por página y no debe contener elementos repetitivos como encabezados o pies de página.
<main>
    <h2>Contenido Principal</h2>
    <p>Este es el contenido más relevante de la página...</p>
</main>


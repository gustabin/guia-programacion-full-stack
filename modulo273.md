2.7.3. Ejercicio 3: Uso de iconos con FontAwesome
Objetivo: Incorporar iconos de FontAwesome en tu página web para mejorar la interacción y estética.
Instrucciones:
Agrega el CDN de FontAwesome en el archivo HTML.
Dentro del archivo <section>, agrega dos iconos usando las clases de FontAwesome:
•	Un icono para representar "inicio".
•	Un icono para representar "contacto".
Aplica clases CSS para cambiar el tamaño de los iconos y agregarles color.
Ejemplo de código HTML y CSS:
<!-- index.html -->
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Página Web</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
</head>
<body>

<header>
    <h1>Bienvenido a mi página web</h1>
</header>

<main>
    <section>
        <h2>Mis tecnologías favoritas</h2>
        <ul>
            <li><i class="fas fa-home"></i> HTML5</li>
            <li><i class="fas fa-paint-brush"></i> CSS3</li>
            <li><i class="fas fa-code"></i> JavaScript</li>
        </ul>
    </section>
</main>

<footer>
    <p>&copy; 2025 Mi Página Web</p>
</footer>

</body>
</html>
/* styles.css */
.fas {
    font-size: 20px;
    color: #333;
    margin-right: 8px;
}

Módulo 1: Introducción al Desarrollo Web
1.1. Introducción a la Programación Web
1. ¿Qué es la Programación Web?
La programación web es el proceso de crear aplicaciones accesibles a través de navegadores. Puede ser un simple sitio estático o una aplicación interactiva y dinámica.
2. Simulación de una Conversación con un Cliente
📌 Escenario: Un cliente te contacta porque quiere una página web para su negocio, pero no entiende mucho de tecnología.
💬 Cliente: "Quiero una web para vender mis productos. ¿Qué necesito?"
👨‍💻 Tú: "Para eso debemos construir un sistema con dos partes: el Front-end, que es lo que los usuarios ven e interactúan, y el backend, que maneja la lógica y la base de datos."
💬 Cliente: "Ah, entiendo. ¿Y cómo lo hacen?"
👨‍💻 Tú: "Usamos tecnologías como HTML, CSS y JavaScript para el Front-end, y PHP, Node.js o Python para el backend, por ejemplo. También una base de datos como MySQL para almacenar la información de tus productos."
➡️ Ejemplo de Código Básico en HTML + CSS:
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Tienda Online</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        .producto { border: 1px solid #ccc; padding: 10px; display: inline-block; margin: 10px; }
    </style>
</head>
<body>
    <h1>Bienvenido a Mi Tienda Online</h1>
    <div class="producto">
        <h2>Producto 1</h2>
        <p>Precio: $100</p>
        <button>Comprar</button>
    </div>
</body>
</html>
🎯 Este código crea una simple página web con un producto. Más adelante agregaremos interactividad con JavaScript y conectaremos con un backend.
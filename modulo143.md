1.4.3. Creando un Proyecto Web desde Cero
🔹 Paso 1: Crea la estructura de carpetas en 
     C:\xampp\htdocs\mi_proyecto.

🔹 Paso 2: Crea index.php y agrega el siguiente código básico:
<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Proyecto Web</title>
    <link rel="stylesheet" href="assets/css/style.css">
</head>

<body>
    <?php include 'includes/header.php'; ?>
    <h1>Bienvenido a mi proyecto web</h1>
    <?php include 'includes/footer.php'; ?>
</body>
</html>


🔹 Paso 3: Crea includes/header.php:
<header>
    <nav>
        <ul>
            <li><a href="index.php">Inicio</a></li>
            <li><a href="pages/contacto.php">Contacto</a></li>
        </ul>
    </nav>
</header>
🔹 Paso 4: Crea includes/footer.php:
<footer>
    <p>&copy; <?php echo date('Y'); ?> Mi Proyecto Web</p>
</footer>
🔹 Paso 5: Crea assets/css/style.css:
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    text-align: center;
}

header {
    background-color: #007bff;
    color: white;
    padding: 10px;
}

🔹Paso 6: Prueba el proyecto en http://localhost/mi_proyecto.
________________________________________
 
Buenas Prácticas en la Organización del Proyecto
✅ Separar el código Front-end y backend para evitar confusión.
✅ Usar nombres descriptivos en archivos y carpetas.
✅ Incluir comentarios en el código para mejorar la comprensión.
✅ Mantener una estructura modular para facilitar la reutilización.
📌Resumen:
•	Aprendimos a estructurar un proyecto web correctamente.
•	Creamos un sistema modular con header.php y footer.php.
•	Probamos nuestra estructura en un servidor local con XAMPP.


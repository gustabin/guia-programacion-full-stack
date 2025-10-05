4.5: Validación y Sanitización de Datos
La validación y sanitización de datos es esencial para evitar errores y vulnerabilidades en aplicaciones web. Permiten asegurarnos de que los datos ingresados por los usuarios sean correctos y seguros antes de almacenarlos o procesarlos.
________________________________________


Diferencia entre Validación y Sanitización
Característica	Validación	Sanitización
Propósito	Verificar si los datos cumplen con un formato o regla específica	Limpiar datos para eliminar caracteres peligrosos o no deseados
Ejemplo	Asegurar que un email sea válido (usuario@dominio.com)	Eliminar etiquetas HTML de una entrada para evitar XSS
Función Principal	filter_var(), preg_match(), strlen()	htmlspecialchars(), strip_tags(), filter_var()
________________________________________
Validación de Datos con PHP
Validar Email
📌 Ejemplo de validación con filter_var()
$email = "usuario@dominio.com";

if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
    echo "Email válido.";
} else {
    echo "Email no válido.";
}
✅ Explicación: FILTER_VALIDATE_EMAIL verifica que el email tenga un formato válido.
Validar Números Enteros
📌 Ejemplo de validación de número
$edad = "25";

if (filter_var($edad, FILTER_VALIDATE_INT)) {
    echo "Edad válida.";
} else {
    echo "Edad no válida.";
}

✅ Evita que se ingresen caracteres en campos numéricos.
________________________________________
Validar Longitud de un Campo
📌 Ejemplo con strlen()
$nombre = "Juan";

if (strlen($nombre) > 3 && strlen($nombre) < 50) {
    echo "Nombre válido.";
} else {
    echo "El nombre debe tener entre 3 y 50 caracteres.";
}
 
✅ Útil para evitar nombres demasiado cortos o largos.
________________________________________
Sanitización de Datos con PHP
Sanitizar un Email
📌 Eliminar caracteres no permitidos
$email = "usuario<script>@dominio.com";
$email_sanitizado = filter_var($email, FILTER_SANITIZE_EMAIL);

echo $email_sanitizado; // Salida: usuario@dominio.com

✅ Esto elimina etiquetas <script>, espacios y caracteres inválidos.
________________________________________
Eliminar Etiquetas HTML para Prevenir XSS
📌 Uso de strip_tags() y htmlspecialchars()
$comentario = "<script>alert('Hackeado');</script> Hola!";
$seguro = strip_tags($comentario); 
echo $seguro; // Salida: "Hola!"

$seguro_html = htmlspecialchars($comentario, ENT_QUOTES);
echo $seguro_html; // Evita que las etiquetas se ejecuten en HTML
 
✅ Protege contra ataques de Cross-Site Scripting (XSS).
________________________________________
Sanitizar Entradas de Formularios
📌 Ejemplo de limpieza de datos de un formulario
$nombre = trim($_POST['nombre']); // Elimina espacios en blanco
$nombre = stripslashes($nombre);  // Quita barras invertidas
$nombre = htmlspecialchars($nombre, ENT_QUOTES); // Evita ejecución de HTML y JS

✅ Protege contra inyección de código malicioso.
Validación y Sanitización en un Formulario Completo
📌 Ejemplo de formulario seguro con PHP
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $nombre = trim($_POST["nombre"]);
    $email = trim($_POST["email"]);
    $edad = $_POST["edad"];

    // Validaciones
    if (empty($nombre) || strlen($nombre) < 3 || strlen($nombre) > 50) {
        die("Nombre no válido.");
    }

    if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
        die("Email no válido.");
    }

    if (!filter_var($edad, FILTER_VALIDATE_INT)) {
        die("Edad no válida.");
    }

    // Sanitización
    $nombre = htmlspecialchars($nombre, ENT_QUOTES);
    $email = filter_var($email, FILTER_SANITIZE_EMAIL);
    echo "Datos válidos y sanitizados correctamente.";
}
?>
<form method="POST">
    Nombre: <input type="text" name="nombre" required><br>
    Email: <input type="email" name="email" required><br>
    Edad: <input type="number" name="edad" required><br>
    <button type="submit">Enviar</button>
</form>

✅ Este formulario evita ataques XSS y protege los datos antes de guardarlos en la base de datos.
________________________________________



 
Resumen de Funciones Útiles
Función	Propósito
filter_var($email, FILTER_VALIDATE_EMAIL)	Verifica si un email es válido
filter_var($edad, FILTER_VALIDATE_INT)	Verifica si un número es entero
htmlspecialchars($dato, ENT_QUOTES)	Escapa caracteres peligrosos en HTML
strip_tags($dato)	Elimina etiquetas HTML y PHP
filter_var($dato, FILTER_SANITIZE_STRING)	Limpia caracteres no deseados de una cadena
trim($dato)	Elimina espacios en blanco al inicio y final

🛑 Errores Comunes y Cómo Evitarlos
❌ Error: No validar la entrada del usuario.
✅ Solución: Siempre usar filter_var(), preg_match() o validaciones personalizadas.
❌ Error: Insertar datos sin sanitización.
✅ Solución: Usar htmlspecialchars(), strip_tags() y mysqli_real_escape_string().
❌ Error: No usar trim(), lo que permite espacios en campos requeridos.
✅ Solución: Aplicar trim() antes de validar los datos.
 
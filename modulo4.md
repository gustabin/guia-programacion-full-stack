Módulo 4: PHP y MySQL
4.1. Introducción a PHP y Sintaxis Básica
PHP (Hypertext Preprocessor) es un lenguaje de programación del lado del servidor ampliamente utilizado para el desarrollo web. Permite generar contenido dinámico, interactuar con bases de datos y gestionar sesiones de usuarios.
PHP es un lenguaje de programación de código abierto, especialmente adecuado para el desarrollo web. Se utiliza para crear páginas web dinámicas que pueden interactuar con bases de datos y realizar tareas en el lado del servidor.
Ventajas de PHP
•	Código abierto y gratuito: Puedes usarlo sin costos adicionales.
•	Fácil de aprender: Comparado con otros lenguajes, su curva de aprendizaje es rápida.
•	Acceso a bases de datos: Facilmente se integra con sistemas de gestión de bases de datos como MySQL.
•	Comunidad activa: Existe una gran comunidad que lo desarrolla y mejora constantemente.
________________________________________
 
1. Instalación y Configuración de PHP
Antes de comenzar, asegúrate de tener un entorno de desarrollo configurado. Puedes usar XAMPP o Laragon para ejecutar PHP en tu máquina local.
🔹 Verificar instalación: Crea un archivo info.php en htdocs con el siguiente contenido:
<?php
phpinfo();
?>

Abre el navegador y accede a http://localhost/info.php para verificar la instalación de PHP.
________________________________________
2. Sintaxis Básica de PHP
🔹 Estructura de un script PHP:
<?php
// Código PHP aquí
// Comentario de una línea
/* Comentario
   de múltiples líneas */
echo "Hola, mundo"; // Imprime en pantalla
?>

PHP admite dos tipos de comentarios: de una línea (//) y de varias líneas (/* */).
 
🔹 Variables y tipos de datos en PHP:
<?php
$nombre = "Juan";  // String
$edad = 30;        // Entero
$precio = 10.5;    // Float
$activo = true;    // Booleano

echo "Nombre: $nombre, Edad: $edad, Precio: $precio, Activo: $activo";
?>

Las variables en PHP comienzan con $. Los nombres de variables son sensibles a mayúsculas y minúsculas.

🔹 Operadores básicos en PHP:
Operador	Descripción	Ejemplo
+	Suma	$a + $b
-	Resta	$a - $b
*	Multiplicación	$a * $b
/	División	$a / $b
.	Concatenación	"Hola " . "Mundo"
________________________________________

 
🔹 Estructuras de control en PHP:
<?php
$edad = 18;
if ($edad >= 18) {
    echo "Eres mayor de edad";
} else {
    echo "Eres menor de edad";
}
?>
🔹 Bucles en PHP:
// Bucle for
for ($i = 1; $i <= 5; $i++) {
    echo "Número: $i <br>";
}

// Bucle while
$j = 1;
while ($j <= 5) {
    echo "Número: $j <br>";
    $j++;
}
________________________________________
3. Funciones en PHP
Las funciones permiten organizar el código en bloques reutilizables.
<?php
function saludar($nombre) {
    return "Hola, $nombre";
}

echo saludar("Carlos");
?>

La función echo se utiliza para mostrar texto o variables en pantalla.
Cada instrucción en PHP debe terminar con un punto y coma (;).
________________________________________
4. Buenas Prácticas en PHP
✅ Usar nombres de variables descriptivos.
✅ Utilizar comentarios para documentar el código.
✅ Evitar el uso de echo dentro de estructuras de control (usar return).
✅ Habilitar error_reporting(E_ALL) en desarrollo para detectar errores.
________________________________________
📌 Resumen:
•	Instalamos y configuramos PHP en XAMPP.
•	Aprendimos la sintaxis básica de PHP.
•	Vimos estructuras de control, bucles y funciones.

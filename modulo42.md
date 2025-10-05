4.2. Conexión a MySQL usando MySQLi
Para que nuestras aplicaciones web interactúen con bases de datos, necesitamos establecer una conexión entre PHP y MySQL. Esto se puede hacer usando MySQLi (MySQL Improved) o PDO. En este módulo, usaremos MySQLi.
________________________________________
4.2.1. Configuración de MySQL y Creación de Base de Datos
Antes de conectarnos, necesitamos una base de datos. Para ello, sigue estos pasos en phpMyAdmin (incluido en XAMPP):
Abre http://localhost/phpmyadmin/.
Haz clic en Bases de datos y crea una nueva llamada mi_app.
Dentro de mi_app, crea una tabla llamada usuarios con las siguientes columnas:
Campo	Tipo	Longitud	Atributos
id	INT	11	AUTO_INCREMENT, PRIMARY KEY
nombre	VARCHAR	100	NOT NULL
email	VARCHAR	100	NOT NULL, UNIQUE
clave	VARCHAR	255	NOT NULL
________________________________________
4.2.2. Conectando PHP a MySQL con MySQLi
Ahora crearemos un archivo conexion.php para gestionar la conexión.
<?php
$servidor = "localhost";
$usuario = "root";
$clave = "";
$base_datos = "mi_app";

// Crear conexión
$conexion = new mysqli($servidor, $usuario, $clave, $base_datos);

// Verificar conexión
if ($conexion->connect_error) {
    die("Error en la conexión: " . $conexion->connect_error);
}

echo "Conexión exitosa a la base de datos";
?>

📌Explicación del código:
•	Se define el servidor, usuario, contraseña y base de datos.
•	Se crea un objeto mysqli para conectar a MySQL.
•	Se verifica si hay un error en la conexión y se muestra un mensaje.
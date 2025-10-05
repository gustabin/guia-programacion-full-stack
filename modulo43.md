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
________________________________________

4.3. Creación de Bases de Datos y Tablas
Para almacenar y gestionar datos en nuestra aplicación web, necesitamos una base de datos bien estructurada. En este tema, aprenderemos a crear bases de datos y tablas utilizando phpMyAdmin y MySQL desde PHP.
________________________________________
1. Creación de una Base de Datos con phpMyAdmin
Para crear una base de datos en phpMyAdmin (XAMPP):
1.	Abre http://localhost/phpmyadmin/ en tu navegador.
2.	Haz clic en la pestaña Bases de datos.
3.	Escribe mi_app en el campo de nombre y presiona Crear. 
 
💡 Consejo: Usa nombres de bases de datos en minúsculas y sin espacios para evitar problemas de compatibilidad.
________________________________________
2. Creación de Tablas en phpMyAdmin
Dentro de la base de datos mi_app:
1.	Haz clic en la base de datos mi_app.
2.	En el campo Nombre de la tabla, escribe usuarios.
3.	Define las siguientes columnas:
Nombre	Tipo	Longitud	Atributos
id	INT	11	PRIMARY KEY, AUTO_INCREMENT
nombre	VARCHAR	100	NOT NULL
email	VARCHAR	100	NOT NULL, UNIQUE
clave	VARCHAR	255	NOT NULL
fecha_registro	TIMESTAMP	-	DEFAULT CURRENT_TIMESTAMP
4.	Haz clic en Guardar.
✅ ¡Tabla creada exitosamente!

3. Creación de Base de Datos y Tablas con Código SQL
También podemos crear bases de datos y tablas usando código SQL.
 
Crear la base de datos
CREATE DATABASE mi_app;

Seleccionar la base de datos
USE mi_app;

Crear la tabla usuarios
CREATE TABLE usuarios (
    id INT(11) AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    clave VARCHAR(255) NOT NULL,
    fecha_registro TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
📌 Explicación de los campos:
•	id: Identificador único de usuario (clave primaria).
•	nombre: Nombre del usuario.
•	email: Correo electrónico, debe ser único.
•	clave: Contraseña encriptada.
•	fecha_registro: Fecha y hora de registro del usuario.
________________________________________
📌 Resumen:
•	Creamos una base de datos y una tabla con phpMyAdmin.
•	Usamos comandos SQL para crear bases de datos y tablas.

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

4.4. Consultas SQL: SELECT, INSERT, UPDATE, DELETE
Ahora que tenemos nuestra base de datos y la tabla usuarios, aprenderemos a interactuar con los datos utilizando consultas SQL en phpMyAdmin, SQL puro y PHP con MySQLi.
________________________________________
1. INSERT: Insertar Datos en una Tabla
Para agregar usuarios a la tabla usuarios, usamos la consulta INSERT INTO.
📌Ejemplo en SQL:
INSERT INTO usuarios (nombre, email, clave) 
VALUES ('Juan Pérez', 'juan@example.com', '123456');
📌Ejemplo en PHP:
<?php
$conexion = new mysqli("localhost", "root", "", "mi_app");

if ($conexion->connect_error) {
    die("Error en la conexión: " . $conexion->connect_error);
}

$sql = "INSERT INTO usuarios (nombre, email, clave) VALUES ('Ana Gómez', 'ana@example.com', 'clave123')";

if ($conexion->query($sql) === TRUE) {
    echo "Usuario registrado con éxito";
} else {
    echo "Error: " . $conexion->error;
}

$conexion->close();
?>
✅ Notas:
•	No se especifica id porque es AUTO_INCREMENT.
•	Clave se almacena en texto plano (pero luego la encriptaremos con password_hash()).
________________________________________
2. SELECT: Consultar Datos de una Tabla
La consulta SELECT nos permite obtener datos de la base de datos.
📌 Ejemplo en SQL: Obtener todos los usuarios
SELECT * FROM usuarios;

📌 Ejemplo en PHP: Obtener y mostrar los usuarios
<?php
$conexion = new mysqli("localhost", "root", "", "mi_app");

$sql = "SELECT id, nombre, email, fecha_registro FROM usuarios";
$resultado = $conexion->query($sql);

if ($resultado->num_rows > 0) {
    while ($fila = $resultado->fetch_assoc()) {
        echo "ID: " . $fila["id"] . " - Nombre: " . $fila["nombre"] . " - Email: " . $fila["email"] . "<br>";
    }
} else {
    echo "No hay usuarios registrados";
}

$conexion->close();
?>
✅ Notas:
•	fetch_assoc() obtiene los resultados como un array asociativo.
•	num_rows verifica si hay datos en la tabla.
3. UPDATE: Modificar Datos de un Registro
Para actualizar datos, usamos UPDATE.
📌 Ejemplo en SQL: Cambiar el nombre de un usuario
UPDATE usuarios SET nombre = 'Juan P. Gómez' WHERE email = 'juan@example.com';

📌 Ejemplo en PHP: Actualizar datos
<?php
$conexion = new mysqli("localhost", "root", "", "mi_app");

$sql = "UPDATE usuarios SET nombre='Ana G. López' WHERE email='ana@example.com'";
if ($conexion->query($sql) === TRUE) {
    echo "Registro actualizado con éxito";
} else {
    echo "Error al actualizar: " . $conexion->error;
}
$conexion->close();
?> 
✅ Notas:
•	Sin WHERE, la actualización afecta todos los registros.
•	Siempre usa cláusulas WHERE para evitar errores.
________________________________________
4. DELETE: Eliminar un Registro
Para borrar datos, usamos DELETE.
📌 Ejemplo en SQL: Borrar un usuario
DELETE FROM usuarios WHERE email = 'juan@example.com';

📌 Ejemplo en PHP: Eliminar un usuario
<?php
$conexion = new mysqli("localhost", "root", "", "mi_app");

$sql = "DELETE FROM usuarios WHERE email='ana@example.com'";

if ($conexion->query($sql) === TRUE) {
    echo "Usuario eliminado con éxito";
} else {
    echo "Error al eliminar: " . $conexion->error;
}

$conexion->close();
?>
 
✅ Notas:
•	Sin WHERE se eliminan TODOS los registros.
•	Usa LIMIT 1 si solo quieres eliminar un solo registro:
DELETE FROM usuarios WHERE email = 'juan@example.com' LIMIT 1;
________________________________________
Resumen
Operación	SQL	PHP
INSERT	INSERT INTO usuarios (...) VALUES (...);	$conexion->query($sql);
SELECT	SELECT * FROM usuarios;	$resultado = $conexion->query($sql);
UPDATE	UPDATE usuarios SET campo = valor WHERE condición;	$conexion->query($sql);
DELETE	DELETE FROM usuarios WHERE condición;	$conexion->query($sql);

1.2.2. Simulación de una Aplicación Web con Front-end y Backend
📌Escenario: Un usuario visita una tienda en línea y compra un producto. Veamos qué sucede en cada parte del sistema.
🔹 Front-end (Lo que ve el usuario)
•	Se muestra un catálogo con productos.
•	El usuario hace clic en "Comprar".
•	Aparece un mensaje de confirmación.
🔹 Backend (Lo que ocurre en el servidor)
•	Se verifica si el producto está en stock.
•	Se descuenta la cantidad en la base de datos.
•	Se genera un número de pedido y se envía un correo de confirmación.
➡️ Código de Front-end (HTML + JavaScript)
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tienda Online</title>
    <script>
        function comprar() {
            fetch("backend.php?producto=1")
            .then(response => response.json())
            .then(data => alert(data.mensaje))
            .catch(error => console.log("Error:", error));
        }
    </script>
</head>
<body>
<h1>Tienda Online</h1>
    <p>Producto: Laptop - $500</p>
    <button onclick="comprar()">Comprar</button>
</body>
</html>
Código de Backend (PHP + Simulación de Base de Datos)
<?php
// Simulación de base de datos
$stock = 5; 
if (isset($_GET['producto']) && $stock > 0) {
    $stock--;
    echo json_encode(["mensaje" => "Compra realizada con éxito. Stock restante: $stock"]);
} else {
    echo json_encode(["mensaje" => "Producto agotado"]);
}
?> 
🎯 Resumen:
•	El Front-end se encarga de mostrar la información y permitir la interacción.
•	El backend procesa la información y realiza las operaciones necesarias.
•	Ambos trabajan juntos para ofrecer una experiencia funcional y eficiente.

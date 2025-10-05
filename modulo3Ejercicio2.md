Ejercicio 2: Validación de formulario con JavaScript
Crea un formulario donde el usuario deba ingresar su nombre y correo electrónico. Si los campos están vacíos, muestra una alerta.
📌HTML
<form id="formulario">
    <input type="text" id="nombre" placeholder="Nombre">
    <input type="email" id="correo" placeholder="Correo electrónico">
    <button type="submit">Enviar</button>
</form>
<p id="error" style="color: red;"></p>

📌JavaScript
document.getElementById("formulario").addEventListener("submit", function(event) {
    event.preventDefault();
    
    let nombre = document.getElementById("nombre").value;
    let correo = document.getElementById("correo").value;
    let mensajeError = document.getElementById("error");

    if (nombre === "" || correo === "") {
        mensajeError.innerText = "Todos los campos son obligatorios.";
    } else {
        mensajeError.innerText = "";
        alert("Formulario enviado con éxito.");
    }
});
Explicación:
•	Se obtiene el formulario y se previene su envío con event.preventDefault().
•	Se validan los campos y, si están vacíos, se muestra un mensaje de error.
•	Si los datos son correctos, se muestra una alerta de éxito.

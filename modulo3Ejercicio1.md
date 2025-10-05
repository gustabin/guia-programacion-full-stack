4.9. Integración de SweetAlert con AJAX
SweetAlert puede usarse junto con AJAX para interactuar con servidores.
Ejemplo: Enviar datos a un servidor con AJAX
Swal.fire({
    title: "Ingresa tu correo",
    input: "email",
    inputPlaceholder: "correo@example.com",
    showCancelButton: true,
    confirmButtonText: "Enviar"
}).then((result) => {
    if (result.value) {
        $.post("servidor.php", { email: result.value }, function(response) {
            Swal.fire("¡Correo enviado!", response, "success");
        });
    }
});
Resumen de conceptos clave
•	SweetAlert es una librería de JavaScript para crear alertas interactivas y atractivas.
•	Se puede instalar mediante una CDN o con npm.
•	Ofrece múltiples opciones de personalización: iconos, botones, imágenes y temporizadores.
•	Permite manejar eventos como confirmaciones y cancelaciones.
•	Se puede usar con formularios y capturas de entrada.
•	Se integra con AJAX para interactuar con servidores.

3.6. Uso de console.log() para depuración
________________________________________
3.6.1. ¿Qué es console.log() y por qué es útil?
console.log() es una herramienta esencial en JavaScript que permite imprimir información en la consola del navegador. Es ampliamente utilizada para depurar código, inspeccionar variables y entender el flujo de ejecución de un programa.
Ejemplo básico:
console.log("¡Hola, mundo!");

Cuando ejecutas este código en el navegador, verás el mensaje en la consola (F12 → Consola en Chrome o Edge).
________________________________________
 
3.6.2. Uso básico de console.log()
Puedes imprimir valores de variables para inspeccionarlas:
let nombre = "Juan";
console.log("El nombre es:", nombre);
Salida en la consola:
El nombre es: Juan
También puedes imprimir números y realizar cálculos:
console.log(5 + 3); // 8
console.log("El resultado de 10 * 2 es:", 10 * 2);

________________________________________
3.6.3. Depuración con console.log()
Para seguir el flujo de un programa, puedes insertar mensajes en distintas partes del código:
function sumar(a, b) {
    console.log("Ejecutando la función sumar con:", a, b);
    return a + b;
}
let resultado = sumar(5, 7);
console.log("El resultado es:", resultado);

Esto ayuda a verificar qué valores están entrando y saliendo de una función.
________________________________________
 
3.6.4. Uso de console.warn() y console.error()
Además de console.log(), puedes usar otros métodos de la consola:
console.warn(): Muestra advertencias.
console.error(): Muestra errores en rojo.
Ejemplo:
console.warn("¡Cuidado! Esta es una advertencia.");
console.error("Error: Algo salió mal.");

Esto ayuda a diferenciar mensajes importantes en la consola.
________________________________________
3.6.5. Inspección de objetos y arreglos con console.table()
Si trabajas con objetos o arreglos, console.table() es muy útil.
Ejemplo con un objeto:
let usuario = { nombre: "Ana", edad: 30, ciudad: "Buenos Aires" };
console.table(usuario);
Ejemplo con un arreglo:
let colores = ["Rojo", "Verde", "Azul"];
console.table(colores);

Esto mostrará una tabla con los datos en la consola.
________________________________________
3.6.6. Uso de console.group() para organizar mensajes
Si necesitas agrupar mensajes en la consola, puedes usar console.group() y console.groupEnd().
 
Ejemplo:
console.group("Información del usuario");
console.log("Nombre: Juan");
console.log("Edad: 28");
console.log("Ciudad: Madrid");
console.groupEnd();

Esto mostrará los mensajes dentro de un grupo colapsable en la consola.
________________________________________
3.6.7. Uso de console.time() y console.timeEnd() para medir tiempos de ejecución
Si quieres saber cuánto tiempo tarda un bloque de código en ejecutarse, puedes usar:
console.time("Tiempo de ejecución");
for (let i = 0; i < 1000000; i++) {} // Bucle que consume tiempo
console.timeEnd("Tiempo de ejecución");

Esto mostrará en la consola cuánto tiempo tomó la ejecución del código.
________________________________________
Resumen de conceptos clave
✔console.log() es la herramienta principal para depuración.
✔console.warn() y console.error() ayudan a identificar advertencias y errores.
✔console.table() es útil para visualizar objetos y arreglos.
✔console.group() permite organizar mensajes en la consola.
✔console.time() mide tiempos de ejecución. 
3.7. Ejercicios y ejemplos prácticos
Ahora pondremos en práctica lo aprendido en JavaScript y jQuery con una serie de ejercicios que abarcan manipulación del DOM, eventos, validación de formularios y más.

Ejercicio 1: Interactuar con el DOM
Crea un botón que cambie el texto de un párrafo cuando se haga clic.
📌HTML
<p id="mensaje">Haz clic en el botón para cambiar este mensaje.</p>
<button id="cambiarTexto">Cambiar Mensaje</button>

📌JavaScript
document.getElementById("cambiarTexto").addEventListener("click", function() {
    document.getElementById("mensaje").innerText = "¡El mensaje ha cambiado!";
});

Explicación:
•	Se obtiene el botón por su id.
•	Se agrega un addEventListener para escuchar el clic.
•	Se cambia el texto del párrafo con innerText.
________________________________________

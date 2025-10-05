3.3.3. Validación básica con JavaScript
La validación básica en JavaScript se puede hacer utilizando condiciones if para comprobar los valores de los campos del formulario.
Validación de un campo obligatorio: Asegurarse de que un campo no esté vacío es una de las validaciones más comunes.
const formulario = document.getElementById("miFormulario");
formulario.addEventListener("submit", function(event) {
    const nombre = document.getElementById("nombre").value;
    if (nombre === "") {
        alert("El campo nombre es obligatorio.");
        event.preventDefault();  // Previene el envío del formulario
    }
});

Validación de formato de correo electrónico: Podemos validar que el valor ingresado en un campo sea un correo electrónico válido usando expresiones regulares.
formulario.addEventListener("submit", function(event) {
    const email = document.getElementById("email").value;
    const regexEmail = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
    if (!regexEmail.test(email)) {
        alert("Por favor ingresa un correo electrónico válido.");
        event.preventDefault();
    }
});
3.3.4. Validación de contraseñas
Para validar contraseñas, normalmente se requiere:
Longitud mínima.
Carácter especial.
Al menos una letra mayúscula.
Al menos un número.
Aquí hay un ejemplo de cómo hacerlo con una expresión regular:
formulario.addEventListener("submit", function(event) {
    const password = document.getElementById("password").value;
    const regexPassword = /^(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/;
    if (!regexPassword.test(password)) {
        alert("La contraseña debe tener al menos 8 caracteres, una mayúscula, un número y un carácter especial.");
        event.preventDefault();
    }
});
3.3.5. Validación de campos numéricos
Es común tener campos donde solo se deben ingresar números, como la edad o el teléfono.
formulario.addEventListener("submit", function(event) {
    const edad = document.getElementById("edad").value;
    if (isNaN(edad) || edad < 18) {
        alert("La edad debe ser un número y mayor o igual a 18.");
        event.preventDefault();
    }
});
3.3.6. Mostrar errores de validación
Para mejorar la experiencia del usuario, se puede mostrar un mensaje de error junto al campo que no pasa la validación. Esto se puede hacer manipulando el DOM.
formulario.addEventListener("submit", function(event) {
    const nombre = document.getElementById("nombre").value;
    const mensajeError = document.getElementById("errorNombre");
    
    if (nombre === "") {
        mensajeError.textContent = "El campo nombre es obligatorio.";
        mensajeError.style.color = "red";
        event.preventDefault();
    } else {
        mensajeError.textContent = "";
    }
});
3.3.7. Usando HTML5 para validación
HTML5 introduce varios atributos de validación que pueden facilitar la validación en el lado del cliente, como required, pattern, min, max, type, etc.
Ejemplo de un formulario con validación básica utilizando HTML5:
<form id="miFormulario">
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" required>
    <br><br>

    <label for="email">Correo Electrónico:</label>
    <input type="email" id="email" name="email" required>
    <br><br>

    <label for="password">Contraseña:</label>
    <input type="password" id="password" name="password" minlength="8" required>
    <br><br>

    <input type="submit" value="Enviar">
</form>
required: El campo no puede estar vacío.
type="email": Verifica que el valor sea una dirección de correo electrónico válida.
minlength: Asegura que la contraseña tenga al menos 8 caracteres.
Resumen de conceptos clave:
•	Validación del lado del cliente: Garantiza que los datos sean correctos antes de enviarlos al servidor, mejorando la experiencia del usuario.
•	Validación básica: Usando JavaScript y HTML5 para asegurarse de que los campos no estén vacíos, tengan el formato correcto, y cumplan con las reglas definidas (por ejemplo, longitud de contraseñas).
•	Mensajes de error: Es importante proporcionar retroalimentación visual al usuario si hay errores en la validación.
•	HTML5: Utilizar los atributos de validación nativos como required, pattern, type, etc., facilita el proceso.

3.4. Introducción a jQuery y su sintaxis
jQuery es una librería de JavaScript que simplifica tareas complejas como la manipulación del DOM, la creación de animaciones, la gestión de eventos y la comunicación con el servidor (AJAX). Aunque hoy en día muchos desarrolladores prefieren trabajar con JavaScript puro o frameworks modernos como React, Angular o Vue, jQuery sigue siendo muy popular debido a su facilidad de uso y amplia compatibilidad con navegadores.
________________________________________
3.4.1. ¿Qué es jQuery?
jQuery es una librería de JavaScript que facilita la manipulación de elementos HTML, la gestión de eventos, la animación y las interacciones con el servidor. Permite realizar tareas de desarrollo web de forma más sencilla y con menos líneas de código que utilizando JavaScript puro.
Algunas de las funcionalidades que jQuery hace fáciles incluyen:
•	Selección de elementos HTML.
•	Modificación de elementos y atributos.
•	Manejo de eventos.
•	Animaciones.
•	AJAX (para realizar peticiones HTTP sin recargar la página).
3.4.2. Incluir jQuery en tu proyecto
Para usar jQuery, debes incluir la librería en tu proyecto. Puedes hacerlo de dos maneras:
Incluirla desde una CDN (Content Delivery Network), como la de Google:
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

Descargarla e incluirla localmente en tu proyecto. Puedes descargarla desde el sitio oficial de jQuery aquí.
________________________________________
3.4.3. Sintaxis básica de jQuery
La sintaxis de jQuery es bastante simple y se basa en el uso de un selector CSS para seleccionar elementos HTML, seguido de una acción que se aplica a esos elementos.
Selector básico: Se usa el signo de dólar ($) seguido del selector de CSS para seleccionar los elementos HTML.
$(selector)
Ejemplo simple: Seleccionar un elemento con el id "miElemento" y cambiar su color de fondo:
$("#miElemento").css("background-color", "red");
$("#miElemento") selecciona el elemento con el id miElemento.
.css("background-color", "red") cambia el color de fondo de ese elemento a rojo.
________________________________________
 
3.4.4. Manipulación del DOM con jQuery
Una de las principales funcionalidades de jQuery es la manipulación del DOM, que te permite cambiar el contenido y estilo de los elementos de una página web de manera sencilla.
Cambiar el texto de un elemento:
$("#miElemento").text("Nuevo texto");

Cambiar el contenido HTML de un elemento:
$("#miElemento").html("<b>Nuevo contenido HTML</b>");
Añadir o eliminar clases CSS:
Añadir una clase:
$("#miElemento").addClass("nuevaClase");

Eliminar una clase:
$("#miElemento").removeClass("nuevaClase");

Cambiar atributos de un elemento:
$("#miElemento").attr("href", "https://www.nuevo-enlace.com");
________________________________________
3.4.5. Manejo de eventos con jQuery
jQuery facilita la gestión de eventos como click, mouseover, keyup, etc., de forma más sencilla que con JavaScript puro.
Eventos de clic:
$("#miBoton").click(function() {
    alert("¡Se hizo clic en el botón!");
});

Eventos de teclado:
Evento keyup:
$("#miInput").keyup(function() {
    console.log("Tecla presionada: " + $(this).val());
});
Eventos de mouse:
Evento mouseenter:
$("#miElemento").mouseenter(function() {
    $(this).css("background-color", "yellow");
});
________________________________________
3.4.6. Animaciones con jQuery
jQuery proporciona métodos simples para animar elementos HTML sin necesidad de utilizar código complejo de CSS o JavaScript.
Desaparecer un elemento:
$("#miElemento").fadeOut(1000);  // Desaparece en 1 segundo

Aparecer un elemento:
$("#miElemento").fadeIn(1000);  // Aparece en 1 segundo

Deslizar hacia abajo:
$("#miElemento").slideDown(1000);  // Desliza hacia abajo en 1 segundo

Deslizar hacia arriba:
$("#miElemento").slideUp(1000);  // Desliza hacia arriba en 1 segundo
________________________________________
3.4.7. jQuery y AJAX
jQuery también facilita la realización de peticiones AJAX, lo que te permite actualizar parte de la página sin tener que recargarla.
Realizar una solicitud GET con jQuery:
$.get("url-del-servicio", function(data) {
    $("#resultado").html(data);
});
Realizar una solicitud POST con jQuery:
$.post("url-del-servicio", { nombre: "Juan", edad: 30 }, function(response) {
    console.log(response);
});
Resumen de conceptos clave:
•	jQuery: Una librería de JavaScript que facilita la manipulación del DOM, el manejo de eventos, las animaciones y la comunicación AJAX.
•	Sintaxis básica: Usar el signo $ para seleccionar elementos y aplicarles acciones.
•	Manipulación del DOM: Cambiar el contenido, atributos y estilos de los elementos.
•	Manejo de eventos: Gestionar interacciones con el usuario como clics, teclas presionadas y movimiento del ratón.
•	Animaciones: Crear efectos visuales simples para mejorar la interacción con el usuario.
•	AJAX: Realizar peticiones asíncronas para actualizar partes de la página sin recargarla.

3.5. Uso de SweetAlert para alertas interactivas
SweetAlert es una librería de JavaScript que permite mostrar alertas más atractivas y funcionales en comparación con las alertas estándar (alert()) de JavaScript. Con SweetAlert puedes personalizar mensajes emergentes con botones, imágenes, temporizadores y distintos estilos.
________________________________________
3.5.1. ¿Qué es SweetAlert?
SweetAlert es una alternativa mejorada al alert() tradicional de JavaScript. Permite mostrar alertas con diseños atractivos y personalizables, además de admitir iconos, botones personalizados y múltiples tipos de mensajes.
Ejemplo de una alerta tradicional con JavaScript
alert("¡Esto es una alerta!");

Este tipo de alerta es funcional pero poco atractiva visualmente.
Ejemplo de una alerta con SweetAlert
Swal.fire("¡Hola!", "Esto es una alerta con SweetAlert", "success");

Esta versión tiene un diseño mucho más atractivo, con colores y animaciones.
________________________________________
3.5.2. Instalación de SweetAlert
Para usar SweetAlert en un proyecto, puedes incluir la librería de dos formas:
1. Incluir desde una CDN (recomendada)
Agrega este script en tu archivo HTML, dentro del <head> o antes de cerrar el <body>:
<script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
2. Instalar con npm (para proyectos más avanzados)
Si trabajas en un entorno con Node.js, puedes instalar SweetAlert con:
npm install sweetalert2

Luego, lo importas en tu archivo JavaScript:
import Swal from 'sweetalert2';

3. Uso básico de SweetAlert
Para mostrar una alerta con SweetAlert, usas la función Swal.fire() pasando diferentes parámetros:
Swal.fire("¡Hola!", "Esto es un mensaje personalizado", "info");

Los tres parámetros principales son:
•	Título: "¡Hola!"
•	Texto del mensaje: "Esto es un mensaje personalizado"
•	Tipo de icono: "success", "error", "warning", "info", "question"
 
4. Personalización de alertas
SweetAlert permite personalizar las alertas con opciones avanzadas.
4.1. Alerta con título, mensaje y botón personalizado
Swal.fire({
    title: "¡Bienvenido!",
    text: "Esto es un mensaje de bienvenida personalizado.",
    icon: "success",
    confirmButtonText: "Aceptar"
});
4.2. Alerta con un temporizador (desaparece sola)
Swal.fire({
    title: "Cargando...",
    text: "Espera unos segundos",
    icon: "info",
    timer: 3000, // Se cierra en 3 segundos
    showConfirmButton: false
});
4.3. Alerta con botón de confirmación y cancelación
Swal.fire({
    title: "¿Estás seguro?",
    text: "No podrás revertir esta acción",
    icon: "warning",
    showCancelButton: true,
    confirmButtonText: "Sí, eliminar",
    cancelButtonText: "Cancelar"
});

4.4. Alerta con imagen personalizada
Swal.fire({
    title: "¡Mira esto!",
    text: "Puedes agregar una imagen personalizada",
    imageUrl: "https://via.placeholder.com/150",
    imageWidth: 150,
    imageHeight: 150,
    imageAlt: "Imagen personalizada"
});
________________________________________

4.5. Uso de eventos y respuestas del usuario
Puedes manejar lo que sucede cuando el usuario confirma o cancela una alerta.
Swal.fire({
    title: "¿Quieres continuar?",
    text: "Haz clic en Aceptar o Cancelar",
    icon: "question",
    showCancelButton: true,
    confirmButtonText: "Aceptar",
    cancelButtonText: "Cancelar"
}).then((result) => {
    if (result.isConfirmed) {
        Swal.fire("¡Acción confirmada!", "", "success");
    } else if (result.dismiss === Swal.DismissReason.cancel) {
        Swal.fire("Acción cancelada", "", "error");
    }
});

4.6. Combinar SweetAlert con formularios y entradas de usuario
SweetAlert permite capturar información del usuario mediante cuadros de entrada.
4.7. Alerta con un campo de entrada de texto
Swal.fire({
    title: "Ingresa tu nombre",
    input: "text",
    inputPlaceholder: "Escribe tu nombre aquí",
    showCancelButton: true,
    confirmButtonText: "Guardar",
    cancelButtonText: "Cancelar"
}).then((result) => {
    if (result.value) {
        Swal.fire(`¡Hola, ${result.value}!`, "", "success");
    }
});
4.8. Alerta con selección de opciones
Swal.fire({
    title: "Selecciona una opción",
    input: "select",
    inputOptions: {
        rojo: "Rojo",
        azul: "Azul",
        verde: "Verde"
    },
    inputPlaceholder: "Elige un color",
    showCancelButton: true
}).then((result) => {
    if (result.value) {
        Swal.fire(`Elegiste: ${result.value}`, "", "success");
    }
});
________________________________________
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


Ejercicio 3: Uso de jQuery para animaciones
Agregaremos un efecto de fadeIn() y fadeOut() a un párrafo con jQuery.
📌HTML
<p id="texto">Este es un mensaje oculto.</p>
<button id="mostrar">Mostrar</button>
<button id="ocultar">Ocultar</button>

📌JavaScript (con jQuery)
$(document).ready(function() {
    $("#texto").hide();
    $("#mostrar").click(function() {
        $("#texto").fadeIn();
    });
    $("#ocultar").click(function() {
        $("#texto").fadeOut();
    });
}); 
Explicación:
•	$("#texto").hide(); oculta el mensaje al cargar la página.
•	$("#mostrar").click(function() { $("#texto").fadeIn(); }); hace que el mensaje aparezca suavemente.
•	$("#ocultar").click(function() { $("#texto").fadeOut(); }); oculta el mensaje con un efecto de desvanecimiento.


Ejercicio 4: Contador de caracteres en un textarea
Cuando el usuario escriba en un textarea, mostramos la cantidad de caracteres en tiempo real.
📌HTML
<textarea id="comentario" rows="4" cols="50" placeholder="Escribe tu comentario..."></textarea>
<p>Caracteres: <span id="contador">0</span></p>

📌JavaScript
document.getElementById("comentario").addEventListener("input", function() {
    let caracteres = this.value.length;
    document.getElementById("contador").innerText = caracteres;
});

Explicación:
•	Input detecta cada cambio en el textarea.
•	this.value.length obtiene el número de caracteres ingresados.
•	Se actualiza el innerText del contador en tiempo real.

Ejercicio 5: Cambio dinámico de tema (modo oscuro y claro)
Permite alternar entre un modo oscuro y claro con un botón.
📌HTML
<button id="modoOscuro">Activar Modo Oscuro</button>

📌CSS
.dark-mode {
    background-color: black;
    color: white;
}

📌JavaScript
document.getElementById("modoOscuro").addEventListener("click", function() {
    document.body.classList.toggle("dark-mode");
});

Explicación:
•	Se usa classList.toggle("dark-mode") para agregar o quitar la clase dark-mode.
•	Si el modo oscuro está activo, el fondo se vuelve negro y el texto blanco.
•	Si el usuario vuelve a hacer clic, se desactiva el modo oscuro.
 
Resumen de ejercicios
✅Manipulación del DOM con innerText y addEventListener.
✅Validación de formularios evitando envíos con preventDefault().
✅Animaciones con jQuery usando fadeIn() y fadeOut().
✅Contador de caracteres actualizando la UI en tiempo real.
✅Cambio de tema dinámico con classList.toggle().

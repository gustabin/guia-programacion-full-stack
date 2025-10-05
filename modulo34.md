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

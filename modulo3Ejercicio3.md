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

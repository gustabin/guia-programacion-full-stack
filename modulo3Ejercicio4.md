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

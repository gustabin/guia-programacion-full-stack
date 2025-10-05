2.4.4. Uso de media queries para diseño responsivo
La idea principal es que tu diseño se ajuste a diferentes dispositivos utilizando min-width y max-width dentro de las media queries. Aquí tienes un ejemplo de cómo podrías escribir CSS para diferentes tamaños de pantalla:
/* Estilo por defecto (para pantallas grandes) */
body {
    font-size: 18px;
    margin: 20px;
}

/* Para pantallas medianas (tabletas) */
@media (max-width: 768px) {
    body {
        font-size: 16px;
        margin: 10px;
    }
}

/* Para pantallas pequeñas (móviles) */
@media (max-width: 480px) {
    body {
        font-size: 14px;
        margin: 5px;
    }
}

En este ejemplo:
•	Si la pantalla tiene más de 768px de ancho, se aplicarán los estilos por defecto.
•	Si la pantalla tiene 768px o menos de ancho (como en tabletas), se aplicarán los estilos dentro de la media query.
•	Si la pantalla tiene 480px o menos de ancho (como en móviles), se aplicarán los estilos correspondientes a esa resolución.
2.4.5. Prácticas recomendadas con media queries
Comienza con un diseño móvil primero: La técnica de Mobile-First (móvil primero) implica escribir los estilos básicos para dispositivos pequeños y luego usar media queries para ajustar el diseño para dispositivos más grandes.
/* Estilos por defecto (móviles) */
body {
    font-size: 14px;
}

/* Para pantallas más grandes (tabletas, escritorios) */
@media (min-width: 768px) {
    body {
        font-size: 16px;
    }
}

@media (min-width: 1024px) {
    body {
        font-size: 18px;
    }
}

Evita los valores fijos: Los valores absolutos como px deben ser usados con precaución. Usa unidades relativas como em, rem o % para hacer tu diseño más flexible.
Prueba en diferentes dispositivos: Asegúrate de probar cómo se ve tu página en diferentes tamaños de pantalla para garantizar que el diseño sea realmente responsivo.
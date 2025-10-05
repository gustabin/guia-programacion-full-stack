2.5. Uso de Bootstrap para el diseño y maquetación
2.5.1. ¿Qué es Bootstrap?
Bootstrap es un framework Front-end de código abierto que permite diseñar sitios web y aplicaciones móviles de manera rápida y fácil. Fue creado por Mark Otto y Jacob Thornton en Twitter, y su objetivo es proporcionar un conjunto de herramientas CSS, JavaScript y componentes predefinidos para hacer que el desarrollo web sea más eficiente y rápido.
Bootstrap utiliza un sistema de rejillas (grid system) basado en 12 columnas, lo que facilita la creación de diseños flexibles y responsivos.
2.5.2. Instalación de Bootstrap
Existen varias formas de incluir Bootstrap en tu proyecto:
Uso de CDN (Content Delivery Network): Puedes incluir Bootstrap simplemente añadiendo los siguientes enlaces en el archivo HTML:
<link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.0.4/dist/umd/popper.min.js"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
Descarga local: Si prefieres descargar Bootstrap y almacenarlo localmente, puedes obtener los archivos desde Bootstrap's official website. Después, solo necesitas vincularlos a tu HTML.

2.5.3. Sistema de rejillas (Grid System)
El sistema de rejillas de Bootstrap es fundamental para la creación de diseños responsivos. Permite dividir la página en 12 columnas de igual ancho, y con estas columnas podemos crear un diseño fluido y adaptativo.
La sintaxis básica de la rejilla es la siguiente:
<div class="row">
    <div class="col-md-4">Contenido 1</div>
    <div class="col-md-4">Contenido 2</div>
    <div class="col-md-4">Contenido 3</div>
</div>

Aquí se están utilizando columnas de tamaño mediano (md), que ocupan un tercio del espacio cada una. En total, las tres columnas suman 12 (4 + 4 + 4).
2.5.4. Breakpoints en Bootstrap
Bootstrap tiene varios puntos de ruptura (breakpoints) que permiten definir cómo se verá el contenido dependiendo del tamaño de la pantalla. Los puntos de ruptura de Bootstrap son:
col-xs-: Para pantallas extra pequeñas (hasta 576px).
col-sm-: Para pantallas pequeñas (hasta 768px).
col-md-: Para pantallas medianas (hasta 992px).
col-lg-: Para pantallas grandes (hasta 1200px).
col-xl-: Para pantallas extra grandes (más de 1200px).
Ejemplo:
<div class="row">
    <div class="col-xs-12 col-sm-6 col-md-4 col-lg-3">Contenido 1</div>
    <div class="col-xs-12 col-sm-6 col-md-4 col-lg-3">Contenido 2</div>
    <div class="col-xs-12 col-sm-6 col-md-4 col-lg-3">Contenido 3</div>
    <div class="col-xs-12 col-sm-6 col-md-4 col-lg-3">Contenido 4</div>
</div>
Este código asegura que las columnas ocupen el 100% del ancho en pantallas pequeñas (extra pequeñas y pequeñas), el 50% en pantallas medianas, el 33% en pantallas grandes y el 25% en pantallas extra grandes.
 
2.5.5. Componentes básicos de Bootstrap
Bootstrap también proporciona una serie de componentes predefinidos para mejorar la estética y funcionalidad de la página, tales como:
Botones:
<button type="button" class="btn btn-primary">Botón Primario</button>
<button type="button" class="btn btn-secondary">Botón Secundario</button>

Tarjetas (Cards): Las tarjetas son elementos de contenido con un diseño atractivo y organizado.
<div class="card" style="width: 18rem;">
  <img src="https://via.placeholder.com/150" class="card-img-top" alt="Imagen">
  <div class="card-body">
    <h5 class="card-title">Título de la tarjeta</h5>
    <p class="card-text">Algunas quick example text para construir el contenido de la tarjeta y hacer que se vea más atractivo.</p>
    <a href="#" class="btn btn-primary">Ir a alguna parte</a>
  </div>
</div>

Formularios:
<form>
  <div class="form-group">
    <label for="exampleInputEmail1">Dirección de correo electrónico</label>
    <input type="email" class="form-control" id="exampleInputEmail1" placeholder="Ingrese correo">
  </div>
  <div class="form-group">
    <label for="exampleInputPassword1">Contraseña</label>
    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Contraseña">
  </div>
  <button type="submit" class="btn btn-primary">Enviar</button>
</form>

Navbars (Barras de navegación): Bootstrap tiene componentes de barra de navegación que pueden ser fácilmente personalizados.
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav">
      <li class="nav-item active">
        <a class="nav-link" href="#">Inicio <span class="sr-only">(actual)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Características</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Precios</a>
      </li>
    </ul>
  </div>
</nav>

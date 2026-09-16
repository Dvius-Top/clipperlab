<!-- ============================================================
     ÍNDICE.HTML — TU PRIMERA PÁGINA WEB
     ============================================================
     Todo lo que está entre estos símbolos <!-- ... --> es un
     COMENTARIO: el navegador lo ignora, sirve solo para que TÚ
     entiendas el código. Lee los comentarios de arriba a abajo.
 
     Una página web tiene 3 lenguajes:
       - HTML  = la ESTRUCTURA (títulos, textos, botones)
       - CSS   = el DISEÑO (colores, tamaños, posición)
       - JS    = la INTERACTIVIDAD (por ahora no la usamos)
 
     En este archivo el HTML y el CSS conviven en un solo lugar
     para que sea fácil de leer. Más adelante los separarás.
============================================================ -->
 
<!DOCTYPE html>
<!-- Esta línea le avisa al navegador: "esto es una página HTML moderna". Siempre va primero. -->
 
<html lang="es">
<!-- Todo el contenido vive dentro de <html>. lang="es" dice que está en español. -->
 
<head>
  <!-- El <head> es la parte INVISIBLE: información sobre la página, no contenido que se ve. -->
 
  <meta charset="UTF-8">
  <!-- Permite tildes y ñ (á, é, ñ) sin que se vean rotas. -->
 
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Hace que la página se vea bien también en el celular. NO la borres. -->
 
  <title>BarberTop — Barbería y Academia</title>
  <!-- Este texto aparece en la pestaña del navegador. -->
 
  <!-- Traemos dos tipografías gratis desde Google Fonts (opcional pero se ve mejor): -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@500;700&family=Inter:wght@400;600&display=swap" rel="stylesheet">
 
  <!-- ========================================================
       AQUÍ EMPIEZA EL CSS (el DISEÑO). Todo lo que está entre
       <style> y </style> define cómo SE VE la página.
       En CSS: seleccionas un elemento y le das propiedades.
       ======================================================== -->
  <style>
 
    /* Las "variables" guardan tus colores en un solo lugar.
       Si cambias un color aquí, cambia en toda la página. */
    :root {
      --carbon:  #17181a;   /* fondo oscuro, casi negro   */
      --crema:   #f4f1ea;   /* texto claro                */
      --laton:   #c9a227;   /* dorado/latón, tu color de acento */
      --gris:    #9a9a9a;   /* texto secundario           */
    }
 
    /* El "*" significa TODOS los elementos. Esto los ordena a todos igual. */
    * {
      margin: 0;            /* quita márgenes que trae el navegador por defecto */
      padding: 0;
      box-sizing: border-box; /* hace que los tamaños se calculen de forma lógica */
    }
 
    /* <body> es todo lo VISIBLE de la página. Le damos el fondo y la letra base. */
    body {
      background-color: var(--carbon);
      color: var(--crema);
      font-family: 'Inter', sans-serif;  /* letra para los párrafos */
      line-height: 1.6;                  /* espacio entre líneas, más legible */
    }
 
    /* Una "clase" (.algo) es una etiqueta que TÚ pones para diseñar un bloque.
       Abajo, en el HTML, verás elementos con class="contenedor", etc. */
 
    .contenedor {
      max-width: 900px;    /* la página no se estira más de 900px */
      margin: 0 auto;      /* centra el contenido horizontalmente */
      padding: 0 24px;     /* aire a los lados para que no pegue al borde */
    }
 
    /* ---- LA CABECERA (el menú de arriba) ---- */
    header {
      padding: 24px 0;
      border-bottom: 1px solid rgba(255,255,255,0.1); /* línea sutil abajo */
    }
    .logo {
      font-family: 'Oswald', sans-serif; /* letra fuerte para el nombre */
      font-size: 24px;
      font-weight: 700;
      letter-spacing: 1px;
      color: var(--crema);
    }
    .logo span { color: var(--laton); } /* pinta solo una parte del nombre de dorado */
 
    /* ---- EL HÉROE (lo primero grande que se ve) ---- */
    .hero {
      padding: 100px 0;
      text-align: center;
    }
    .hero h1 {
      font-family: 'Oswald', sans-serif;
      font-size: 56px;      /* título muy grande */
      line-height: 1.1;
      margin-bottom: 16px;
    }
    .hero p {
      color: var(--gris);
      font-size: 18px;
      max-width: 520px;      /* el párrafo no se estira demasiado (se lee mejor) */
      margin: 0 auto 32px;   /* centrado y con espacio abajo */
    }
 
    /* Un BOTÓN. La clase .boton se puede reusar en toda la página. */
    .boton {
      display: inline-block;
      background-color: var(--laton);
      color: var(--carbon);
      font-weight: 600;
      padding: 14px 32px;
      border-radius: 4px;
      text-decoration: none;   /* quita el subrayado del enlace */
    }
    .boton:hover {             /* :hover = cuando pasas el mouse por encima */
      opacity: 0.85;
    }
 
    /* ---- SECCIÓN DE SERVICIOS ---- */
    .servicios {
      padding: 80px 0;
      border-top: 1px solid rgba(255,255,255,0.1);
    }
    .servicios h2 {
      font-family: 'Oswald', sans-serif;
      font-size: 32px;
      margin-bottom: 32px;
    }
    /* Esto crea una grilla de 3 columnas para las tarjetas. */
    .grilla {
      display: grid;
      grid-template-columns: repeat(3, 1fr); /* 3 columnas iguales */
      gap: 20px;                              /* espacio entre tarjetas */
    }
    .tarjeta {
      background-color: rgba(255,255,255,0.04);
      padding: 28px;
      border-radius: 6px;
    }
    .tarjeta h3 {
      color: var(--laton);
      margin-bottom: 8px;
      font-family: 'Oswald', sans-serif;
    }
 
    /* ---- PIE DE PÁGINA ---- */
    footer {
      padding: 40px 0;
      text-align: center;
      color: var(--gris);
      font-size: 14px;
      border-top: 1px solid rgba(255,255,255,0.1);
    }
 
    /* ---- RESPONSIVE: se activa SOLO en pantallas chicas (celular) ----
       Aquí las 3 columnas se convierten en 1 para que quepan. */
    @media (max-width: 640px) {
      .hero h1 { font-size: 38px; }
      .grilla  { grid-template-columns: 1fr; }
    }
 
  </style>
</head>
 
<!-- ==========================================================
     AQUÍ EMPIEZA EL <body>: TODO LO QUE SE VE EN LA PANTALLA.
     Cada bloque de abajo usa las clases definidas arriba en CSS.
     ========================================================== -->
<body>
 
  <!-- CABECERA con el nombre de tu marca -->
  <header>
    <div class="contenedor">
      <div class="logo">Barber<span>Top</span></div>
    </div>
  </header>
 
  <!-- HÉROE: el mensaje principal. <h1> es el título más importante de la página. -->
  <section class="hero">
    <div class="contenedor">
      <h1>Cortes con oficio,<br>estilo de verdad</h1>
      <p>Barbería y academia en Santiago. Reserva tu hora o aprende el oficio con nosotros.</p>
      <!-- <a> es un enlace. href="#" es un enlace vacío por ahora. -->
      <a href="#" class="boton">Reservar hora</a>
    </div>
  </section>
 
  <!-- SERVICIOS: tres tarjetas de ejemplo. Copia una <div class="tarjeta"> para agregar más. -->
  <section class="servicios">
    <div class="contenedor">
      <h2>Servicios</h2>
      <div class="grilla">
 
        <div class="tarjeta">
          <h3>Corte clásico</h3>
          <p>Corte a máquina y tijera, terminado a navaja.</p>
        </div>
 
        <div class="tarjeta">
          <h3>Barba</h3>
          <p>Perfilado, toalla caliente y aceites.</p>
        </div>
 
        <div class="tarjeta">
          <h3>Academia</h3>
          <p>Curso presencial de barbería desde cero.</p>
        </div>
 
      </div>
    </div>
  </section>
 
  <!-- PIE DE PÁGINA -->
  <footer>
    <div class="contenedor">
      BarberTop · Av. Nueva Providencia 2160, Santiago · Metro Los Leones
    </div>
  </footer>
 
</body>
</html>

 

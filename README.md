<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nariño: Corazón del Sur | Turismo y Cultura</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
</head>
<body>

    <header>
        <nav>
            <div class="logo">Nariño Mágico</div>
            <ul>
                <li><a href="#lugares">Sitios</a></li>
                <li><a href="#itinerario">Itinerario</a></li>
                <li><a href="#mapa">Mapa</a></li>
            </ul>
        </nav>
        <div class="hero">
            <h1>Descubre el Sur Profundo</h1>
            <p>Religión, Volcanes y Tradiciones Ancestrales</p>
        </div>
    </header>

    <section id="cultura">
        <h2>Cultura y Ancestralidad</h2>
        <div class="grid">
            <article>
                <h3>Carnaval de Negros y Blancos</h3>
                <p>Patrimonio Inmaterial de la Humanidad. Una explosión de arte y libertad.</p>
            </article>
            <article>
                <h3>Barniz de Pasto</h3>
                <p>Técnica única en el mundo de origen prehispánico (Mopa-Mopa).</p>
            </article>
        </div>
    </section>

    <section id="itinerario">
        <h2>Plan de 5 Días en Nariño</h2>
        <table border="1">
            <tr>
                <th>Día</th>
                <th>Actividad</th>
                <th>Lugar</th>
            </tr>
            <tr>
                <td>1</td>
                <td>Ruta de los Museos y Templos</td>
                <td>Pasto (Ciudad Teológica)</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Aventura en el Volcán</td>
                <td>Laguna de la Cocha</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Fe y Arquitectura</td>
                <td>Santuario de Las Lajas (Ipiales)</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Naturaleza Volcánica</td>
                <td>Azufrales del Volcán Azufral</td>
            </tr>
            <tr>
                <td>5</td>
                <td>Tradición Cafetera</td>
                <td>Visita a fincas en la Unión</td>
            </tr>
        </table>
    </section>

    <section id="mapa-section">
        <h2>Rutas Turísticas</h2>
        <p>Explora cómo llegar a los puntos clave desde Pasto.</p>
        <div id="map" style="height: 400px; width: 100%;"></div>
    </section>

    <footer>
        <p>&copy; 2026 Turismo Nariño - Hecho con ❤️ para el mundo.</p>
    </footer>

    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
    <script>
        var map = L.map('map').setView([1.2136, -77.2811], 9); // Coordenadas de Pasto
        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(map);

        // Marcadores
        L.marker([1.2136, -77.2811]).addTo(map).bindPopup('Pasto: Capital Sorpresa');
        L.marker([0.8053, -77.5861]).addTo(map).bindPopup('Santuario de Las Lajas');
        L.marker([1.1025, -77.1511]).addTo(map).bindPopup('Laguna de la Cocha');
    </script>
</body>
</html>

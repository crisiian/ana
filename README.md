<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nariño: Corazón del Sur | Guía Turística</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />

    <style>
        /* CSS UNIFICADO */
        :root {
            --verde-pastuso: #2d5a27;
            --dorado-barniz: #d4a373;
            --oscuro: #1a1a1a;
            --blanco: #ffffff;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Montserrat', sans-serif;
            line-height: 1.6;
            color: var(--oscuro);
            background-color: #f4f4f4;
        }

        header {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), 
                        url('https://images.unsplash.com/photo-1582650859079-ee6391318a45?q=80&w=1500&auto=format&fit=crop');
            background-size: cover;
            background-position: center;
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: var(--blanco);
            padding: 20px;
        }

        h1 { font-family: 'Playfair Display', serif; font-size: 3.5rem; margin-bottom: 10px; }
        .subtitle { font-size: 1.2rem; font-weight: 300; letter-spacing: 2px; }

        section { padding: 60px 20px; max-width: 1100px; margin: auto; }
        h2 { font-family: 'Playfair Display', serif; color: var(--verde-pastuso); font-size: 2.5rem; margin-bottom: 30px; text-align: center; }

        /* Estilo de Tarjetas de Cultura */
        .grid-cultura {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .card {
            background: var(--blanco);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            border-top: 5px solid var(--dorado-barniz);
        }

        /* Tabla de Itinerario */
        .tabla-contenedor { overflow-x: auto; margin-top: 20px; }
        table { width: 100%; border-collapse: collapse; background: var(--blanco); }
        th, td { padding: 15px; text-align: left; border: 1px solid #ddd; }
        th { background: var(--verde-pastuso); color: var(--blanco); }
        tr:nth-child(even) { background: #f9f9f9; }

        /* Mapa */
        #map { height: 500px; width: 100%; border-radius: 15px; box-shadow: 0 5px 20px rgba(0,0,0,0.2); }

        footer {
            background: var(--oscuro);
            color: var(--blanco);
            text-align: center;
            padding: 40px 20px;
            margin-top: 50px;
        }

        @media (max-width: 768px) {
            h1 { font-size: 2.2rem; }
        }
    </style>
</head>
<body>

    <header>
        <p class="subtitle">EXPERIENCIA ANCESTRAL</p>
        <h1>Nariño, Tierra de Volcanes</h1>
        <p>Donde la fe se encuentra con la montaña y el arte con la historia.</p>
    </header>

    <section id="tradiciones">
        <h2>Cultura y Misticismo</h2>
        <div class="grid-cultura">
            <div class="card">
                <h3>🎭 Carnaval de Negros y Blancos</h3>
                <p>La fiesta más grande del sur de Colombia. Una mezcla de ritos andinos, españoles y africanos que celebra la diversidad.</p>
            </div>
            <div class="card">
                <h3>🏺 Barniz de Pasto</h3>
                <p>El Mopa-Mopa es una resina vegetal usada desde tiempos ancestrales para decorar madera. Único en el mundo.</p>
            </div>
            <div class="card">
                <h3>⛪ Fe y Religión</h3>
                <p>Conocida como la "Ciudad Teológica", Pasto alberga templos con arquitectura colonial y republicana impresionante.</p>
            </div>
        </div>
    </section>

    <section id="itinerario">
        <h2>Itinerario de 5 Días: Ruta del Sur</h2>
        <div class="tabla-contenedor">
            <table>
                <thead>
                    <tr>
                        <th>Día</th>
                        <th>Ruta Principal</th>
                        <th>Lo que verás</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>1</td>
                        <td>Pasto Ciudad Teológica</td>
                        <td>Museo del Oro, Templo de San Juan, Plaza de Nariño.</td>
                    </tr>
                    <tr>
                        <td>2</td>
                        <td>La Laguna de la Cocha</td>
                        <td>Hospedaje en El Encano, Isla La Corota y comida típica (Trucha).</td>
                    </tr>
                    <tr>
                        <td>3</td>
                        <td>Ipiales: El Milagro del Abismo</td>
                        <td>Santuario de Las Lajas y paso fronterizo de Rumichaca.</td>
                    </tr>
                    <tr>
                        <td>4</td>
                        <td>Volcán Azufral</td>
                        <td>Caminata a la Laguna Verde (Punto de energía ancestral).</td>
                    </tr>
                    <tr>
                        <td>5</td>
                        <td>Ruta del Café y Tradición</td>
                        <td>Visita al municipio de La Unión para conocer el mejor café de altura.</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </section>

    <section id="rutas">
        <h2>Mapa de Rutas y Destinos</h2>
        <p style="text-align: center; margin-bottom: 20px;">Interactúa con el mapa para ver los puntos clave desde Pasto.</p>
        <div id="map"></div>
    </section>

    <footer>
        <p><strong>Nariño Mágico 2026</strong></p>
        <p>Proyecto educativo para el fomento del turismo regional.</p>
    </footer>

    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
    <script>
        // Inicializar Mapa centrado en Nariño
        var map = L.map('map').setView([1.1000, -77.3000], 9);

        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '© OpenStreetMap'
        }).addTo(map);

        // Marcadores de Sitios Turísticos
        var sitios = [
            { nombre: "Pasto: Capital Sorpresa", coord: [1.2136, -77.2811] },
            { nombre: "Santuario de Las Lajas (Ipiales)", coord: [0.8053, -77.5861] },
            { nombre: "Laguna de la Cocha", coord: [1.1025, -77.1511] },
            { nombre: "Volcán Azufral / Laguna Verde", coord: [1.0833, -77.6833] },
            { nombre: "La Unión: Ruta del Café", coord: [1.6063, -77.1302] }
        ];

        sitios.forEach(function(sitio) {
            L.marker(sitio.coord).addTo(map)
                .bindPopup("<b>" + sitio.nombre + "</b><br>Punto clave de la ruta.");
        });
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Reciclatorios</title>

<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>

<style>

    section h2{
        color: #c8facc;
    }

    section h3{
        color; #eaffea;
    }

    section ul, section ol{
        margin-left: 20px;
    }


html{ scroll-behavior: smooth; }

body{
    margin: 0;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    background-color: #3f6b3f;
}

#map{ height: 400px; }

.header-top{
    background-color: #a8c3a0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 30px;
}

.header-top h1{ margin: 0; }

.logos{ display: flex; gap: 20px; }
.logos img{ width: 100px; }

.menu{
    background-color: #6c8f5e;
    display: flex;
    justify-content: center;
    gap: 40px;
    padding: 15px;
}

.menu a{
    text-decoration: none;
    color: black;
    font-weight: bold;
}

.principal{ padding: 50px; }

.grid{
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 15px;
}

.item-grande{ grid-row: span 2; }
.item-grande img{
    width: 100%;
    height: 415px;
    object-fit: cover;
}

.grid img{
    width: 100%;
    height: 200px;
    object-fit: cover;
}

section{ padding: 80px 40px; color: white; }

.zona-juego{
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
}

.objetos, .botes{
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.item{
    background-color: white;
    color: black;
    padding: 10px;
    cursor: grab;
    text-align: center;
}

.bote{
    background-color: #a8c3a0;
    padding: 20px;
    text-align: center;
    min-width: 120px;
}

    
</style>
</head>

<body>


<!-- BLOQUE 1 -->
<div class="header-top">
    <h1>RECICLATORIOS</h1>

    <div class="logos">
        <img src="https://tse3.mm.bing.net/th/id/OIP.JNYfxsVM5y-gSFeQdWdvngHaHa?rs=1&pid=ImgDetMain&o=7&rm=3">
        <img src="https://tse3.mm.bing.net/th/id/OIP.YrmhDxy7KanKF2sCm--b2QHaIu?rs=1&pid=ImgDetMain&o=7&rm=3">
    </div>
</div>

<!-- BLOQUE 2 -->
<div class="menu">
    <a href="#aprende">Aprende a reciclar</a>
    <a href="#donde">Dónde reciclar</a>
    <a href="#mapa">Mapa</a>
    <a href="#objetivo">Nuestro objetivo</a>
    <a href="#conocenos">Conócenos</a>
    <a href="#juegos">Juegos</a>
</div>

<!-- BLOQUE 3 -->
<div class="principal">

<div class="grid">

<div class="item-grande">
    <img src="https://tse3.mm.bing.net/th/id/OIP.Ld0ALVeHBe08o-T9SRUs5AHaE7?rs=1&pid=ImgDetMain&o=7&rm=3">
    <p>Aprende a reciclar y ayuda al planeta con pequeñas acciones.</p>
</div>

<img src="https://tse2.mm.bing.net/th/id/OIP.KJrVSaeZ5UEDqn-Ak5e67gHaE8?rs=1&pid=ImgDetMain&o=7&rm=3">
<img src="https://th.bing.com/th/id/R.25e599134090c3340f86e24701401ce1?rik=KUwtahbccyCVYw&pid=ImgRaw&r=0">

</div>
</div>

<!-- JUEGOS -->
<section id="juegos">
<h2>Juegos</h2>

<h3>Quiz ♻️</h3>
<p id="pregunta"></p>
<div id="opciones"></div>
<p id="resultado"></p>
<button onclick="siguientePregunta()">Siguiente</button>

<hr>

<h3>Arrastra el residuo al bote correcto ♻️</h3>

<div class="zona-juego">
    <div class="objetos">
        <div class="item" draggable="true" id="plastico1">Botella</div>
        <div class="item" draggable="true" id="organico1">Cáscara</div>
        <div class="item" draggable="true" id="vidrio1">Vidrio</div>
        <div class="item" draggable="true" id="papel1">Periódico</div>
    </div>

    <div class="botes">
        <div class="bote" data-tipo="plastico">Plástico</div>
        <div class="bote" data-tipo="organico">Orgánico</div>
        <div class="bote" data-tipo="vidrio">Vidrio</div>
        <div class="bote" data-tipo="papel">Papel</div>
    </div>
</div>

<p id="resultadoDrag"></p>
</section>

<!-- SECCIONES -->
<section id="aprende">

<h2>Aprende a reciclar</h2>

<h3>Guía completa para el reciclaje de residuos: plástico, orgánicos, vidrio y papel</h3>

<p>
El reciclaje es una de las estrategias más efectivas para reducir el impacto ambiental generado por los residuos sólidos. 
A través de la correcta separación, tratamiento y reutilización de materiales, es posible disminuir la contaminación, 
ahorrar recursos naturales y fomentar un modelo de desarrollo sostenible.
</p>

<p>
Esta guía explica cómo reciclar adecuadamente los principales tipos de residuos: plásticos, orgánicos, vidrio y papel, 
así como su importancia y procesos.
</p>

<hr>

<h2>¿Por qué es importante reciclar?</h2>

<ul>
<li>Reducir la cantidad de basura en vertederos</li>
<li>Disminuir la contaminación del aire, suelo y agua</li>
<li>Ahorrar energía en la producción de nuevos materiales</li>
<li>Conservar recursos naturales como madera, agua y minerales</li>
<li>Fomentar una cultura ambiental responsable</li>
</ul>

<hr>

<h2>Reciclaje de plásticos</h2>

<p>
Los plásticos son materiales derivados del petróleo y están presentes en envases, botellas, bolsas y productos de uso diario.
</p>

<h3>¿Cómo reciclar plástico correctamente?</h3>

<ol>
<li>Separar los plásticos de otros residuos</li>
<li>Enjuagar los envases</li>
<li>Retirar tapas o etiquetas</li>
<li>Clasificar por tipo</li>
<li>Depositar en el contenedor correcto</li>
</ol>

<h3>Beneficios</h3>

<ul>
<li>Reduce la contaminación</li>
<li>Disminuye el uso de petróleo</li>
<li>Ahorra energía</li>
</ul>

<hr>

<h2>Reciclaje de residuos orgánicos</h2>

<p>Incluyen restos de comida, cáscaras y hojas.</p>

<h3>¿Cómo reciclarlos?</h3>

<ol>
<li>Separar residuos orgánicos</li>
<li>Usar una compostera</li>
<li>Mezclar residuos húmedos y secos</li>
<li>Mantener ventilación</li>
<li>Esperar a que se forme abono</li>
</ol>

<h3>Beneficios</h3>

<ul>
<li>Reduce basura</li>
<li>Produce fertilizante natural</li>
<li>Disminuye contaminación</li>
</ul>

<hr>

<h2>Reciclaje de vidrio</h2>

<h3>¿Cómo reciclar vidrio?</h3>

<ol>
<li>Separar por color</li>
<li>Lavar envases</li>
<li>No mezclar con cerámica</li>
<li>Depositar en contenedores</li>
</ol>

<h3>Beneficios</h3>

<ul>
<li>100% reciclable</li>
<li>Ahorra energía</li>
<li>Reduce emisiones</li>
</ul>

<hr>

<h2>Reciclaje de papel y cartón</h2>

<h3>¿Cómo reciclar papel?</h3>

<ol>
<li>Separar papel limpio</li>
<li>Evitar humedad</li>
<li>No incluir papel sucio</li>
<li>Depositar correctamente</li>
</ol>

<h3>Beneficios</h3>

<ul>
<li>Reduce tala de árboles</li>
<li>Ahorra agua</li>
<li>Disminuye contaminación</li>
</ul>

<hr>

<h2>Recomendaciones generales</h2>

<ul>
<li>Separar residuos desde casa</li>
<li>Reducir el consumo</li>
<li>Reutilizar materiales</li>
<li>Participar en programas de reciclaje</li>
</ul>

<hr>

<h2>Conclusión</h2>

<p>
El reciclaje es una responsabilidad compartida. Adoptar hábitos correctos ayuda a cuidar el medio ambiente y a construir un futuro más sostenible.
</p>

</section>

<section id="donde">
<h2>Dónde reciclar</h2>
<p>Actualmente disponemos informacion de solo los centros de reciclaje de la ciudad de Reynosa, Tamaulipas.</p>
</section>

<section id="mapa">
    <h2>Mapa de reciclaje 🗺️</h2>
    <p>Ubicación de puntos de reciclaje.</p>

    <div id="map"></div>
</section>

<section id="objetivo">
<h2>Nuestro objetivo</h2>
<p>Concientizar sobre el reciclaje y informar de manera divertida a jovenes estudiantes acerca de la educacion ambiental, ademas de servir como recurso digital para la educacion y formacion ambiental de jovenes estudiantes de preparatoria y de secundaria. </p>
</section>

<section id="conocenos">
<h2>Conócenos</h2>
<p>Somos estudiantes del CETIS 71, que esta en Reynosa, Tamaulipas. Somos estudiantes de la carrera tecnica de administracion de recursos humanos, con nuestra tutora, la ing. Miriam Janeth Hernandez Guerrero, formamos esta pagina en respuesta a un proyecto escuela-comunidad (PEC), el cual este esta enfocado en brindar apoyo a diferentes problematicas de la comunidad del pais, en esta ocacion la pagina respoinde al tema de manejo de residuos solidos.</p>
</section>

<script>

// MAPA
var map = L.map('map').setView([25.78, -100.18], 13);

L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
  attribution: '&copy; OpenStreetMap contributors'
}).addTo(map);

L.marker([25.78, -100.18]).addTo(map)
  .bindPopup('Aquí estás 🚩')
  .openPopup();

    // CENTROS DE RECICLAJE EN REYNOSA
var lugares = [
    {
        nombre: "FYMERSA - Centro de metales ♻️",
        coords: [26.084526395888336, -98.29755461861764],
        info: "Recibe metales"
    },
    {
        nombre: "CORSA Recicladora ♻️",
        coords: [26.08932324746204, -98.31992874226934],
        info: "Materiales ferrosos y no ferrosos"
    },
    {
        nombre: "PLASTIREYSA ♻️",
        coords: [26.051331045072637, -98.3733933937469],
        info: "Centro de reciclaje de plástico"
    }
];

// AGREGAR MARCADORES
lugares.forEach(lugar => {
    L.marker(lugar.coords)
      .addTo(map)
      .bindPopup(`<b>${lugar.nombre}</b><br>${lugar.info}`);
});

var grupo = L.featureGroup(
    lugares.map(lugar => L.marker(lugar.coords))
);

map.fitBounds(grupo.getBounds());
    
// QUIZ
const preguntas = [
{
    pregunta: "¿Qué significan las 3R?",
    opciones: ["Reciclar, Reducir, Reutilizar", "Reubicar, Reducir, Reciclar", "Reutilizar, Rapidez, Reubicar"],
    correcta: 0
},
{
    pregunta: "¿Qué es el PET?",
    opciones: ["Polímero de Energía Térmica", "Polietileno Tereftalato", "Plástico transparente"],
    correcta: 1
}
];

let indice = 0;
let puntaje = 0;

function cargarPregunta(){
    const p = document.getElementById("pregunta");
    const op = document.getElementById("opciones");
    op.innerHTML = "";

    p.textContent = preguntas[indice].pregunta;

    preguntas[indice].opciones.forEach((o,i)=>{
        const btn = document.createElement("button");
        btn.textContent = o;
        btn.onclick = ()=>verificar(i);
        op.appendChild(btn);
    });
}

function verificar(i){
    const r = document.getElementById("resultado");
    if(i===preguntas[indice].correcta){
        r.textContent = "¡Correcto! ✅";
        puntaje++;
    } else {
        r.textContent = "Incorrecto ❌";
    }
}

function siguientePregunta(){
    indice++;
    if(indice < preguntas.length){
        cargarPregunta();
    } else {
        document.getElementById("juegos").innerHTML = `<h3>Terminaste 🎉</h3><p>Puntaje: ${puntaje}</p>`;
    }
}

cargarPregunta();

// DRAG & DROP
const items = document.querySelectorAll(".item");
const botes = document.querySelectorAll(".bote");
let arrastrado = null;

items.forEach(item => {
    item.addEventListener("dragstart", () => {
        arrastrado = item;
    });
});

botes.forEach(bote => {
    bote.addEventListener("dragover", (e) => e.preventDefault());

    bote.addEventListener("drop", () => {
        const tipoBote = bote.getAttribute("data-tipo");
        const idItem = arrastrado.id;

        let correcto = idItem.includes(tipoBote);
        const resultado = document.getElementById("resultadoDrag");

        if(correcto){
            resultado.textContent = "¡Correcto! ✅";
            arrastrado.style.display = "none";
        } else {
            resultado.textContent = "Incorrecto ❌";
        }
    });
});
</script>

</body>

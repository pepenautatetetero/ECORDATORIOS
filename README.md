<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Ecordatorios</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>

<style>

#registro form{
    background: #6c8f5e;
    padding: 20px;
    max-width: 300px;
}

    
#registro form{
    background: #6c8f5e;
    padding: 20px;
    max-width: 400px;
    margin: auto;
}
    
    section h2{
        color: #c8facc;
    }

    section h3{
    color: #eaffea;
}

    section ul, section ol{
        margin-left: 20px;
    }
    
.header-top{
    background-color: #a8c3a0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 30px 60px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
}
    
html{ scroll-behavior: smooth; }

body{
    margin: 0;
    font-family: 'Segoe UI', Tahoma, sans-serif;
    background: linear-gradient(180deg, #2e5e2e, #3f6b3f);
}
    
body.verde {
    background: linear-gradient(180deg, #2e5e2e, #3f6b3f);
}

body.azul {
    background: linear-gradient(180deg, #2e4e5e, #3f5f6b);
}

body.oscuro {
    background: #121212;
}
    
#map{ height: 400px; }

.header-top{
    background: linear-gradient(90deg, #a8c3a0, #6c8f5e);
    border-bottom: 3px solid #4a6b4a;
}

.header-top h1{ margin: 0; }

.logos{ display: flex; gap: 20px; }
.logos img{ width: 100px; }

.menu{
    background-color: #6c8f5e;
    display: flex;
    justify-content: center;
    flex-wrap: wrap; 
    gap: 20px;
    padding: 15px;
}

.menu a{
    text-decoration: none;
    color: black;
    font-weight: bold;
    transition: 0.3s;
}

.menu a:hover{
    color: white;
    transform: scale(1.1);
}

.principal{
    padding: 50px;
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}

.grid{
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
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

section{
    padding: 60px 20px;
    max-width: 1200px;
    margin: 40px auto;
    background: rgba(255,255,255,0.05);
    border-radius: 20px;
    box-shadow: 0 10px 25px rgba(0,0,0,0.3);
    backdrop-filter: blur(5px);
}
    section{
    padding: 60px 20px;
}
    section{
    color: white;
}    
    
.zona-juego{
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
    flex-wrap: wrap;
    gap: 20px;
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

.contenedor{
    max-width: 1200px;
    margin: auto;
    background: rgba(0,0,0,0.15);
    padding: 30px;
    border-radius: 15px;
}    

.grid img, .item-grande img{
    border-radius: 15px;
    transition: 0.3s;
}

.grid img:hover{
    transform: scale(1.05);
}

.item{
    border-radius: 10px;
    transition: 0.2s;
}

.item:hover{
    transform: scale(1.05);
    background: #dfffe0;
}

.bote{
    border-radius: 15px;
    transition: 0.2s;
}

.bote:hover{
    background: #c8facc;
}

#registro form{
    border-radius: 20px;
    box-shadow: 0 10px 20px rgba(0,0,0,0.3);
}

button{
    background: #c8facc;
    cursor: pointer;
    font-weight: bold;
}

button:hover{
    background: #a8f0b0;
}

#racha{
    font-size: 30px;
    color: #c8facc;
    font-weight: bold;
}   
section{
    animation: aparecer 0.6s ease;
}

@keyframes aparecer{
    from{
        opacity: 0;
        transform: translateY(20px);
    }
    to{
        opacity: 1;
        transform: translateY(0);
    }
}
    
/* 📱 CELULARES */
@media (max-width: 768px){

    .header-top{
        flex-direction: column;
        text-align: center;
        padding: 20px;
    }

    .logos img{
        width: 70px;
    }

    .menu{
        flex-direction: column;
        gap: 10px;
    }

    .principal{
        padding: 20px;
    }

    .grid{
        grid-template-columns: 1fr;
    }

    .item-grande img{
        height: auto;
    }

    .zona-juego{
        flex-direction: column;
        align-items: center;
    }

    .botes{
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
    }

    .bote{
        min-width: 100px;
        padding: 10px;
    }

    section{
        margin: 20px 10px;
        padding: 30px 15px;
    }

    #map{
        height: 300px;
    }
}    

    button{
    width: 100%;
    padding: 12px;
    font-size: 16px;
    height: auto;
}

</style>
</head>

<body>


<!-- BLOQUE 1 -->
<div class="header-top">
    <h1>Ecordatorios</h1>

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
    <a href="#registro">Registro de reciclaje</a>
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
<div class="contenedor">
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
</div>
</section>

<!-- Registro -->
<section id="registro">
    <div class="contenedor">
        <h2>Registro de reciclaje ♻️</h2>

<form id="formReciclaje">
    <label>¿Qué reciclaste?</label><br>
    <select id="tipo">
        <option value="plastico">Plástico</option>
        <option value="vidrio">Vidrio</option>
        <option value="papel">Papel</option>
        <option value="organico">Orgánico</option>
    </select><br><br>

    <label>¿Cómo te sentiste?</label><br>
    <select id="sentimiento">
        <option value="bien">😊 Bien</option>
        <option value="normal">😐 Normal</option>
        <option value="mal">😞 Mal</option>
    </select><br><br>

    <button type="submit">Registrar reciclaje</button>
</form>

<h3>🔥 Racha actual: <span id="racha">0</span> días</h3>
<h3>⭐ Puntos: <span id="puntos">0</span></h3>
<h3>🏆 Nivel: <span id="nivel">Novato</span></h3>

<h3>🎖️ Insignias</h3>
<ul id="insignias"></ul>
<h3>Historial</h3>
<ul id="historial"></ul>

<h3> Skins desbloqueables</h3>

<button onclick="cambiarTema('verde')">Verde</button>
<button onclick="cambiarTema('azul')">Azul</button>
<button onclick="cambiarTema('oscuro')">Oscuro</button>

<!-- SECCIONES -->
<section id="aprende">
<div class="contenedor">
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

</div>
</section>

<section id="donde">
    <div class="contenedor">
        <h2>Dónde reciclar</h2>
<p>Actualmente disponemos informacion de solo los centros de reciclaje de la ciudad de Reynosa, Tamaulipas.</p>
</section>

<section id="mapa">
    <div class="contenedor">
        <h2>Mapa de reciclaje 🗺️</h2>
    <p>Ubicación de puntos de reciclaje.</p>

    <div id="map"></div>
</div>
</section>

<section id="objetivo">
<div class="contenedor">
<h2>Nuestro objetivo</h2>

<p>
El objetivo principal de este proyecto es concientizar a la comunidad estudiantil sobre la importancia del reciclaje y el cuidado del medio ambiente. 
A través de esta plataforma, se busca proporcionar información clara, accesible y atractiva que motive a los jóvenes a adoptar hábitos responsables en su vida diaria.
</p>

<p>
Además, se pretende informar de manera dinámica y entretenida a estudiantes de nivel secundaria y preparatoria acerca de la educación ambiental, 
utilizando herramientas interactivas como juegos, mapas y contenido visual. De esta forma, el aprendizaje no solo se vuelve más efectivo, 
sino también más interesante y fácil de comprender.
</p>

<p>
Otro de los objetivos es servir como un recurso digital educativo que pueda ser utilizado tanto por alumnos como por docentes, 
apoyando el proceso de enseñanza-aprendizaje en temas relacionados con el reciclaje, la separación de residuos y la sostenibilidad.
</p>

<p>
También se busca fomentar una cultura ambiental responsable, en la que los estudiantes comprendan el impacto de sus acciones en el entorno 
y se conviertan en agentes de cambio dentro de su comunidad, promoviendo prácticas como reducir, reutilizar y reciclar.
</p>

<p>
Finalmente, este proyecto aspira a contribuir a la formación de una sociedad más consciente, comprometida con el cuidado del planeta 
y preparada para enfrentar los desafíos ambientales actuales y futuros.
</p>

</div>
</section>

<section id="conocenos">
<div class="contenedor">
<h2>Conócenos</h2>

<p>Somos estudiantes del CETIS 71, ubicado en Reynosa, Tamaulipas. Formamos parte de la carrera técnica en Administración de Recursos Humanos y trabajamos en conjunto con nuestra tutora, la Ing. Miriam Janeth Hernández Guerrero, para desarrollar este proyecto educativo.</p>

<p>Esta página fue creada como respuesta a un proyecto escuela–comunidad (PEC), el cual tiene como objetivo principal contribuir a la solución de distintas problemáticas que afectan a la sociedad. En nuestro caso, decidimos enfocarnos en el manejo de residuos sólidos, una situación que impacta directamente al medio ambiente y a la calidad de vida de las personas.</p>

<p>
A través de este sitio web buscamos brindar información clara, útil y accesible sobre el reciclaje, así como fomentar la conciencia ambiental en jóvenes estudiantes. También integramos herramientas interactivas, como juegos y mapas, para hacer el aprendizaje más dinámico e interesante.
</p>

<p>
Como equipo, nos comprometemos a promover valores como la responsabilidad, el respeto por el entorno y la participación activa en el cuidado del planeta. Creemos que pequeños cambios en los hábitos diarios pueden generar un gran impacto a largo plazo.
</p>

<p>
Este proyecto no solo representa una actividad académica, sino también una oportunidad para aportar algo positivo a nuestra comunidad y motivar a otros a sumarse al cuidado del medio ambiente.
</p>

<h3>Integrantes</h3>
<ul>
<li>De La Cruz Cruz Angel David</li>
<li>Banda Guerrero Ana Sofia</li>
<li>Epigmenio Borbolla Estrella</li>
<li>Ramirez Ramos Melanie Zayle</li>
<li>Uvalle Dominguez Dylan Eduardo</li>   
</ul>

</div>
</section>

<section id="comentarios">
<div class="contenedor">
    <h2>Comentarios 💬</h2>
    <p> NO DEBES DE COLOCAR PALABRAS MAL SONANTES </p>

    <form id="formComentario">
        <input type="text" id="nombre" placeholder="Tu nombre" required><br><br>
        <textarea id="mensaje" placeholder="Escribe un comentario..." required></textarea><br><br>
        <button type="submit">Enviar</button>
    </form>

    <hr>

    <div id="listaComentarios"></div>
</div>
</section>

comentarios



<script type="module">

    // ===== FIREBASE IMPORTS (VERSIÓN WEB) =====
import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js";
import {
    getFirestore,
    collection,
    addDoc,
    onSnapshot,
    query,
    orderBy
} from "https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore.js";

const firebaseConfig = {
  apiKey: "AIzaSyDw2Ilq75kQrf5trROBqqRyhwgAeMRYQKQ",
  authDomain: "ecordatorios.firebaseapp.com",
  projectId: "ecordatorios",
  storageBucket: "ecordatorios.firebasestorage.app",
  messagingSenderId: "872970549143",
  appId: "1:872970549143:web:42f094e018078d0b9a76d2",
  measurementId: "G-YFVZ1PMTT1"
};

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);

const comentariosRef = collection(db, "comentarios");
    
// 📤 ENVIAR COMENTARIO
document.getElementById("formComentario").addEventListener("submit", async (e) => {
    e.preventDefault();

    const nombre = document.getElementById("nombre").value.trim();
    const mensaje = document.getElementById("mensaje").value.trim();

    // palabras prohibidas
    const malasPalabras = ["idiota", "estupido", "tonto", "spam"];

    const contieneMalas = malasPalabras.some(p =>
        mensaje.toLowerCase().includes(p)
    );

    if (contieneMalas) {
        alert("⚠️ Tu comentario contiene lenguaje no permitido.");
        return;
    }

    if (mensaje.length < 3) {
        alert("⚠️ El comentario es muy corto.");
        return;
    }

    await addDoc(comentariosRef, {
        nombre,
        mensaje,
        fecha: Date.now()
    });

    e.target.reset();
});

    const lista = document.getElementById("listaComentarios");

const q = query(comentariosRef, orderBy("fecha", "desc"));

onSnapshot(q, (snapshot) => {
    lista.innerHTML = "";

    snapshot.forEach(doc => {
        const c = doc.data();

        const div = document.createElement("div");
        div.style.background = "rgba(255,255,255,0.1)";
        div.style.margin = "10px 0";
        div.style.padding = "10px";
        div.style.borderRadius = "10px";

        div.innerHTML = `
            <b>${c.nombre}</b><br>
            <p>${c.mensaje}</p>
        `;

        lista.appendChild(div);
    });
});    
// MAPA
var map = L.map('map').setView([26.0926, -98.2770], 13);

L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
  attribution: '&copy; OpenStreetMap contributors'
}).addTo(map);

map.locate({setView: true, maxZoom: 16});

map.on('locationfound', function(e) {
    L.marker(e.latlng).addTo(map)
      .bindPopup('Estás aquí 📍')
      .openPopup();
});

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
},
    {
    pregunta: "¿Cuantos años tarda una botella de plastico en descomponerse?",
    opciones: ["100", "10", "500"],
    correcta: 2
},
{
    pregunta: "¿Cuantas veces el papel puede reciclarse?",
    opciones: ["7", "2", "5"],
    correcta: 0
},
    
    {
    pregunta: "¿Qué pais ocupa el primer lugar del ranking de paises mas comprometidos con el reciclaje?",
    opciones: ["Suiza", "Japon", "Alemania"],
    correcta: 0
},
{
    pregunta: "Que pais es el que contamina mas?",
    opciones: ["India", "China", "Francia"],
    correcta: 1
}]


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
    window.siguientePregunta = siguientePregunta;
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
function cambiarTema(tema){
    document.body.classList.remove("verde", "azul", "oscuro");
    document.body.classList.add(tema);
    localStorage.setItem("tema", tema);
}

function cargarTema(){
    const tema = localStorage.getItem("tema") || "verde";

    document.body.classList.remove("verde", "azul", "oscuro");
    document.body.classList.add(tema);
}

window.cambiarTema = cambiarTema;
window.cargarTema = cargarTema;
    
// ===== REGISTRO DE RECICLAJE =====
// ===== FUNCIONES =====

function notificacionRacha(racha){
    if ("Notification" in window && Notification.permission === "granted") {
        new Notification("♻️ Reciclaje", {
            body: `🔥 Llevas ${racha} días reciclando`,
            icon: "https://cdn-icons-png.flaticon.com/512/2909/2909767.png"
        });
    }
}

function obtenerNivel(puntos){
    if(puntos >= 200) return "🌍 Maestro del Reciclaje";
    if(puntos >= 100) return "♻️ Experto";
    if(puntos >= 50) return "🌱 Intermedio";
    return "🟢 Novato";
}

function verificarInsignias(puntos, racha, insignias){
    if(puntos >= 50 && !insignias.includes("🎯 Primeros 50")){
        insignias.push("🎯 Primeros 50");
    }

    if(puntos >= 100 && !insignias.includes("💯 Centenario")){
        insignias.push("💯 Centenario");
    }

    if(racha >= 7 && !insignias.includes("🔥 7 días seguidos")){
        insignias.push("🔥 7 días seguidos");
    }

    localStorage.setItem("insignias", JSON.stringify(insignias));
}

// ===== APP =====

document.addEventListener("DOMContentLoaded", function(){

    cargarTema();
    cargarPregunta(); 
    cargarTema();
    
    const form = document.getElementById("formReciclaje");
    const historialUI = document.getElementById("historial");
    const rachaUI = document.getElementById("racha");

    let registros = JSON.parse(localStorage.getItem("registros")) || [];
    let racha = parseInt(localStorage.getItem("racha")) || 0;
    let ultimaFecha = localStorage.getItem("ultimaFecha") || null;
    let puntos = parseInt(localStorage.getItem("puntos")) || 0;
    let insignias = JSON.parse(localStorage.getItem("insignias")) || [];

    actualizarUI();

    form.addEventListener("submit", function(e){
        e.preventDefault();

        const tipo = document.getElementById("tipo").value;
        const sentimiento = document.getElementById("sentimiento").value;
        const hoy = new Date().toDateString();

        let rachaAnterior = racha;

        registros.push({ tipo, sentimiento, fecha: hoy });
        localStorage.setItem("registros", JSON.stringify(registros));

        if(ultimaFecha){
            let ayer = new Date();
            ayer.setDate(ayer.getDate() - 1);

            if(new Date(ultimaFecha).toDateString() === ayer.toDateString()){
                racha++;
            } else if(new Date(ultimaFecha).toDateString() !== hoy){
                racha = 1;
            }
        } else {
            racha = 1;
        }

        ultimaFecha = hoy;

        localStorage.setItem("racha", racha);
        localStorage.setItem("ultimaFecha", ultimaFecha);

        puntos += 10;
        if(sentimiento === "bien"){
            puntos += 5;
        }

        localStorage.setItem("puntos", puntos);

        verificarInsignias(puntos, racha, insignias);

        if(racha > rachaAnterior){
            if (Notification.permission !== "granted") {
                Notification.requestPermission();
            }
            notificacionRacha(racha);
        }

        actualizarUI();
        form.reset();
    });

    function actualizarUI(){
        historialUI.innerHTML = "";

        registros.slice().reverse().forEach(r => {
            const li = document.createElement("li");
            li.textContent = `${r.fecha} - ${r.tipo} - ${r.sentimiento}`;
            historialUI.appendChild(li);
        });

        rachaUI.textContent = racha;
        document.getElementById("puntos").textContent = puntos;
        document.getElementById("nivel").textContent = obtenerNivel(puntos);

        const lista = document.getElementById("insignias");
        lista.innerHTML = "";

        insignias.forEach(i => {
            const li = document.createElement("li");
            li.textContent = i;
            lista.appendChild(li);
        });
    }

});


</script>
    
</body>

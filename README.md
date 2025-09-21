<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Para Camila 💛</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', sans-serif;
      color: #333;
      min-height: 100vh;
      text-align: center;
      overflow: hidden;
      background: linear-gradient(to bottom, #fffde7, #fff9c4);
    }
    .pantalla-inicio {
      position: fixed;
      top: 0; left: 0;
      width: 100vw; height: 100vh;
      background: #070911;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      z-index: 10;
      transition: opacity 1s;
      overflow: hidden;
    }
    .bienvenida-titulo {
      font-size: 2.4em;
      color: #ffd600;
      font-weight: bold;
      margin-bottom: 18px;
      background: #070911dd;
      border-radius: 20px;
      padding: 22px 28px;
      box-shadow: 0 4px 22px #222;
      border: 2px solid #ffd600;
      max-width: 90vw;
      letter-spacing: 1px;
    }
    .autor {
      color: #90caf9;
      font-weight: bold;
      font-size: 1.05em;
      margin-bottom: 20px;
      margin-top: -8px;
      letter-spacing: 1px;
      text-shadow: 0 2px 12px #1565c077;
    }
    .btn-inicio {
      background-color: #ffd600;
      border: none;
      padding: 18px 38px;
      font-size: 1.35em;
      color: #333;
      border-radius: 14px;
      cursor: pointer;
      transition: all 0.3s;
      font-weight: bold;
      box-shadow: 0 6px 22px #ffd60055;
      margin-top: 16px;
    }
    .btn-inicio:hover {
      background-color: #ffee58;
      transform: scale(1.07);
      color: #d4a300;
    }
    /* Meteoros horizontales animados de derecha a izquierda */
    .meteoro {
      position: absolute;
      top: 0;
      left: 110vw;
      width: 140px;
      height: 22px;
      pointer-events: none;
      z-index: 20;
      opacity: 0.92;
      transform: rotate(15deg) perspective(300px) rotateY(-10deg);
      animation-name: meteoroAnim;
      animation-timing-function: cubic-bezier(.5,.1,.6,1.1);
      animation-iteration-count: 1;
    }
    @keyframes meteoroAnim {
      0% {left: 110vw; opacity: 0; filter: blur(10px); transform: rotate(15deg) scale(0.8) perspective(300px) rotateY(-13deg);}
      10% {opacity: 1; filter: blur(0px);}
      80% {left: 15vw; opacity: 1; filter: blur(1px); transform: rotate(17deg) scale(1.08) perspective(300px) rotateY(-4deg);}
      100% {left: -180px; opacity: 0; filter: blur(10px); transform: rotate(15deg) scale(0.7) perspective(300px) rotateY(8deg);}
    }
    .nucleo-meteoro, .cola-meteoro, .destello-meteoro { /* igual que antes */ }
    .margarita-creciendo {
      position: absolute;
      bottom: 40px;
      z-index: 12;
      width: 120px;
      height: 270px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-end;
      opacity: 1;
      transition: opacity 1.2s;
    }
    .margarita-creciendo.izq { left: 40px; }
    .margarita-creciendo.der { right: 40px; }
    .margarita-creciendo.oculto { opacity: 0; }
    .parte { opacity: 0; transition: opacity 0.7s; position: absolute; left: 50%; transform: translateX(-50%);}
    .parte.visible { opacity: 1; }
    .tallo { top: 60px;}
    .raiz { top: 240px;}
    .hoja { top: 125px;}
    .hoja.izq { left: 44px; transform: rotate(-22deg);}
    .hoja.der { left: 68px; transform: rotate(22deg);}
    .flor { top: 25px; left: 50%; transform: translateX(-50%);}
    #corazones {
      position: fixed;
      top:0;left:0;width:100vw;height:100vh;pointer-events:none;z-index:1;
    }
    .brillo-flor {
      position: absolute;
      left: 50%;
      top: 47px;
      transform: translateX(-50%);
      width: 38px;
      height: 38px;
      pointer-events: none;
      z-index: 100;
      border-radius: 50%;
      background: radial-gradient(circle, #fffde7aa 0%, #fffde700 80%);
      opacity: 0.7;
      animation: brilloFlor 2.2s infinite;
      display: none;
    }
    @keyframes brilloFlor {
      0% { opacity: 0.15;}
      50% { opacity: 0.65;}
      100% { opacity: 0.15;}
    }
    .mariposa {
      position: absolute;
      width: 48px;
      height: 48px;
      z-index: 13;
      pointer-events: none;
      opacity: 0.94;
      animation: mariposaMove 8s infinite linear;
    }
    .mariposa.izq { left: 10px; top: 140px; animation-delay: 0s;}
    .mariposa.der { right: 10px; top: 170px; animation-delay: 4s;}
    @keyframes mariposaMove {
      0% { transform: translateY(0) scale(1) rotate(-7deg);}
      20% { transform: translateY(-22px) scale(1.08) rotate(7deg);}
      40% { transform: translateY(-8px) scale(0.97) rotate(-13deg);}
      60% { transform: translateY(-26px) scale(1.09) rotate(10deg);}
      80% { transform: translateY(-22px) scale(1.03) rotate(-5deg);}
      100% { transform: translateY(0) scale(1) rotate(-7deg);}
    }
    .ala { transform-origin: center center; animation: alaFlap 1s infinite alternate;}
    @keyframes alaFlap { 0% { transform: scaleY(1.0);} 50% { transform: scaleY(1.24);} 100% { transform: scaleY(1.0);} }
    .contenido {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      width: 100vw;
      position: relative;
      background: linear-gradient(135deg, #ffe082 0%, #f8bbd0 40%, #b3e5fc 70%, #fffde7 100%);
      animation: fondoColorido 8s ease-in-out infinite alternate;
      transition: background 1s;
    }
    @keyframes fondoColorido {
      0% {background: linear-gradient(135deg, #ffe082 0%, #f8bbd0 40%, #b3e5fc 70%, #fffde7 100%);}
      100% {background: linear-gradient(135deg, #fff9c4 0%, #ffecb3 35%, #b2dfdb 80%, #f8bbd0 100%);}
    }
    .contenido-interno {
      background: #fffde7e0;
      box-shadow: 0 2px 18px #ffe08255;
      border-radius: 24px;
      padding: 36px 28px 32px 28px;
      max-width: 420px;
      display: inline-block;
      margin-top: 30px;
      position: relative;
      z-index: 10;
    }
    h1 {
      color: #fdd835;
      font-size: 2.2em;
      margin-bottom: 0.15em;
      text-shadow: 0 1px 10px #fffde766;
      margin-top: 0;
    }
    .camila {
      font-weight: bold;
      color: #ffd600;
      font-size: 1.1em;
    }
    .autor-final {
      color: #1565c0;
      font-weight: bold;
      font-size: 1.1em;
      margin: 14px 0 0 0;
      text-shadow: 0 2px 12px #90caf9aa;
      letter-spacing: 1px;
    }
    .frase-corta {
      font-size: 1.15em;
      color: #ffb300;
      font-weight: bold;
      margin-top: 14px;
      margin-bottom: 8px;
      background: #fffde7ee;
      border-radius: 12px;
      padding: 8px 12px;
      box-shadow: 0 2px 12px #ffd54f44;
      border: 1px solid #ffe082;
      display: inline-block;
      min-width: 220px;
      max-width: 340px;
      animation: fraseAnim 2.5s linear infinite alternate;
    }
    @keyframes fraseAnim {
      0% {box-shadow: 0 2px 12px #ffd54f44;}
      100% {box-shadow: 0 2px 22px #81d4fa66;}
    }
    p {
      font-size: 1.07em;
      margin-bottom: 1em;
      max-width: 350px;
      background: #fffde7cc;
      border-radius: 12px;
      padding: 8px 14px;
      box-shadow: 0 2px 12px #ffe08233;
      border: 1px solid #ffe082;
      margin-left: auto;
      margin-right: auto;
      animation: fraseAnim 3s linear infinite alternate;
    }
    button {
      background-color: #fdd835;
      border: none;
      padding: 10px 24px;
      font-size: 1.03em;
      color: #333;
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.3s ease;
      margin-top: 8px;
      font-weight: bold;
      box-shadow: 0 2px 10px #ffee5866;
    }
    button:hover {
      background-color: #b3e5fc;
      color: #1565c0;
      transform: scale(1.07);
      box-shadow: 0 2px 18px #81d4fa66;
    }
    .message {
      display: none;
      font-size: 1.09em;
      margin-top: 16px;
      color: #4caf50;
      animation: fadeIn 2s ease forwards;
      font-weight: bold;
      background: #fffde7ee;
      border-radius: 14px;
      padding: 10px 14px;
      box-shadow: 0 2px 14px #ffe08244;
      border: 1px solid #ffe082;
      max-width: 300px;
      margin-left: auto;
      margin-right: auto;
      animation: mensajeAnim 3s linear infinite alternate;
    }
    @keyframes mensajeAnim {
      0% {box-shadow: 0 2px 14px #ffe08244;}
      100% {box-shadow: 0 2px 18px #b3e5fc77;}
    }
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    .flowers {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 2;
      overflow: hidden;
    }
    .margarita { position: absolute; width: 40px; height: 40px; will-change: transform, opacity; z-index: 2; pointer-events: none; opacity: 0.93;}
    .mensaje-sorpresa {
      display: none;
      position: absolute;
      left: 50%;
      top: 52%;
      transform: translate(-50%,-50%);
      z-index: 999;
      background: linear-gradient(135deg,#fffde7 60%,#ffe082 100%);
      border-radius: 18px;
      box-shadow: 0 2px 18px #ffd60088;
      border: 2px solid #ffd600;
      padding: 28px 20px 18px 20px;
      font-size: 1.09em;
      color: #ffb300;
      max-width: 320px;
      font-weight: bold;
      animation: fadeIn 1s;
      text-align: center;
      margin-top: -20px;
    }
    .mensaje-sorpresa .cerrar {
      margin-top: 14px;
      font-size: 1.05em;
      background: #ffd600;
      border: none;
      border-radius: 10px;
      padding: 7px 18px;
      cursor: pointer;
      color: #333;
      font-weight: bold;
      box-shadow: 0 2px 12px #ffd60044;
    }
    .mensaje-sorpresa .cerrar:hover {
      background: #ffecb3;
      color: #1565c0;
    }
    @media (max-width: 600px) {
      .contenido-interno {max-width:90vw;padding:16px;}
      h1{font-size:1.2em;}
      .frase-corta{min-width:120px;}
      .mensaje-sorpresa{max-width:94vw;}
    }
  </style>
</head>
<body>
  <div id="corazones"></div>
  <div class="mariposa izq">
    <svg width="48" height="48" viewBox="0 0 48 48">
      <ellipse class="ala" cx="17" cy="18" rx="13" ry="18" fill="#f48fb1"/>
      <ellipse class="ala" cx="27" cy="18" rx="13" ry="18" fill="#b3e5fc"/>
      <ellipse cx="22" cy="34" rx="7" ry="13" fill="#fff176"/>
      <circle cx="24" cy="26" r="7" fill="#ffb300"/>
      <ellipse cx="24" cy="21" rx="2.5" ry="5" fill="#fff3e0"/>
      <rect x="22" y="31" width="4" height="18" rx="2" fill="#8d6e63"/>
      <rect x="23" y="8" width="2" height="18" rx="1" fill="#8d6e63"/>
    </svg>
  </div>
  <div class="mariposa der">
    <svg width="48" height="48" viewBox="0 0 48 48">
      <ellipse class="ala" cx="31" cy="20" rx="13" ry="18" fill="#ce93d8"/>
      <ellipse class="ala" cx="11" cy="20" rx="13" ry="18" fill="#ffcc80"/>
      <ellipse cx="24" cy="34" rx="7" ry="13" fill="#80deea"/>
      <circle cx="24" cy="26" r="7" fill="#f06292"/>
      <ellipse cx="24" cy="21" rx="2.5" ry="5" fill="#fff3e0"/>
      <rect x="22" y="31" width="4" height="18" rx="2" fill="#8d6e63"/>
      <rect x="23" y="8" width="2" height="18" rx="1" fill="#8d6e63"/>
    </svg>
  </div>
  <div class="pantalla-inicio" id="pantallaInicio">
    <div class="bienvenida-titulo">Hola, estas flores amarillas son para ti 💛</div>
    <div class="autor">De: Danfer Huaroto</div>
    <button class="btn-inicio" onclick="mostrarContenido()">Ver flores amarillas</button>
    <div id="meteorosContainer"></div>
    <div class="margarita-creciendo izq" id="margaritaIzq">
      <svg class="parte raiz" width="50" height="40">
        <path d="M25,0 Q23,15 25,23 Q27,15 25,0" stroke="#7e5c1e" stroke-width="3" fill="none"/>
      </svg>
      <svg class="parte tallo" width="12" height="210">
        <rect x="6" y="0" width="2.5" height="210" fill="#4caf50" rx="2"/>
      </svg>
      <svg class="parte hoja izq" width="32" height="32">
        <ellipse cx="18" cy="18" rx="10" ry="18" fill="#388e3c" />
      </svg>
      <svg class="parte hoja der" width="32" height="32">
        <ellipse cx="14" cy="18" rx="10" ry="18" fill="#388e3c" />
      </svg>
      <svg class="parte flor" width="80" height="80">
        <g>
          <ellipse cx="40" cy="20" rx="14" ry="24" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
          <ellipse cx="40" cy="60" rx="14" ry="24" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
          <ellipse cx="20" cy="40" rx="24" ry="14" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
          <ellipse cx="60" cy="40" rx="24" ry="14" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
          <circle cx="40" cy="40" r="18" fill="#ffd600" stroke="#ffa000" stroke-width="4"/>
        </g>
      </svg>
    </div>
    <div class="margarita-creciendo der" id="margaritaDer">
      <svg class="parte raiz" width="50" height="40">
        <path d="M25,0 Q23,15 25,23 Q27,15 25,0" stroke="#7e5c1e" stroke-width="3" fill="none"/>
      </svg>
      <svg class="parte tallo" width="12" height="210">
        <rect x="6" y="0" width="2.5" height="210" fill="#4caf50" rx="2"/>
      </svg>
      <svg class="parte hoja izq" width="32" height="32">
        <ellipse cx="18" cy="18" rx="10" ry="18" fill="#388e3c" />
      </svg>
      <svg class="parte hoja der" width="32" height="32">
        <ellipse cx="14" cy="18" rx="10" ry="18" fill="#388e3c" />
      </svg>
      <svg class="parte flor" width="80" height="80">
        <g>
          <ellipse cx="40" cy="20" rx="14" ry="24" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
          <ellipse cx="40" cy="60" rx="14" ry="24" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
          <ellipse cx="20" cy="40" rx="24" ry="14" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
          <ellipse cx="60" cy="40" rx="24" ry="14" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
          <circle cx="40" cy="40" r="18" fill="#ffd600" stroke="#ffa000" stroke-width="4"/>
        </g>
      </svg>
    </div>
  </div>
  <div class="contenido" id="contenidoPrincipal">
    <div class="contenido-interno">
      <h1>🌼 Para <span class="camila">Camila Hernández</span> 🌼</h1>
      <div style="position:relative;display:inline-block;">
        <svg id="florPrincipal" width="80" height="80" style="cursor:pointer;">
          <g>
            <ellipse cx="40" cy="20" rx="14" ry="24" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
            <ellipse cx="40" cy="60" rx="14" ry="24" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
            <ellipse cx="20" cy="40" rx="24" ry="14" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
            <ellipse cx="60" cy="40" rx="24" ry="14" fill="#fffde7" stroke="#ffe082" stroke-width="2"/>
            <circle id="centroFlor" cx="40" cy="40" r="18" fill="#ffd600" stroke="#ffa000" stroke-width="4"/>
          </g>
        </svg>
        <div class="brillo-flor" id="brilloFlor"></div>
      </div>
      <div class="frase-corta" id="fraseCorta">
        Eres la razón por la que sonrío cada día.
      </div>
      <p>
        Sé que estamos lejos, trabajas casi 12 horas, llegas cansada del trabajo y no tenemos tiempo casi de vernos.<br>
        Y creo que la mejor manera de entenderte es esperándote y eso dice mucho que me importas.
      </p>
      <button onclick="mostrarMensaje()">Haz click si tú también me amas 💛</button>
      <div class="message" id="mensaje">💛 ¡Sabía que sí! Gracias por estar en mi vida, Camila. 💛</div>
      <div class="autor-final">De: Danfer Huaroto</div>
    </div>
    <div class="mensaje-sorpresa" id="mensajeSorpresa">
      <span id="textoSorpresa"></span>
      <br>
      <button class="cerrar" onclick="cerrarSorpresa()">Cerrar</button>
    </div>
  </div>
  <div class="flowers" id="flores"></div>
  <iframe 
    id="player" 
    src="https://www.youtube.com/embed/wnJ6LuUFpMo?autoplay=1&loop=1&playlist=wnJ6LuUFpMo&controls=0&mute=1"
    allow="autoplay"
    frameborder="0"
    allowfullscreen
  ></iframe>
  <script>
    function mostrarContenido() {
      document.getElementById('pantallaInicio').style.opacity = 0;
      document.getElementById('margaritaIzq').classList.add('oculto');
      document.getElementById('margaritaDer').classList.add('oculto');
      setTimeout(function() {
        document.getElementById('pantallaInicio').style.display = 'none';
        document.getElementById('contenidoPrincipal').style.display = 'flex';
      }, 950);
    }
    function mostrarMensaje() {
      document.getElementById('mensaje').style.display = 'block';
    }
    const frases = [
      "Eres la razón por la que sonrío cada día.",
      "No hay distancia que apague lo que siento por ti.",
      "Cada momento contigo es único y especial.",
      "Tu presencia ilumina mi vida como el sol a las flores.",
      "Eres mi fuerza y mi mayor inspiración.",
      "Contigo aprendí lo que es amar de verdad.",
      "Te amo más de lo que las palabras pueden expresar.",
      "Tu felicidad es mi mayor deseo.",
      "Gracias por existir y por elegirme cada día.",
      "Por ti, soy mejor persona.",
      "Te pienso a cada instante.",
      "No hay nada más valioso que tu compañía.",
      "Eres mi sueño hecho realidad.",
      "Siempre serás mi prioridad.",
      "Te extraño en cada amanecer y en cada noche.",
      "Sin ti, los días serían grises.",
      "Eres mi refugio y mi alegría.",
      "Me importas más de lo que imaginas.",
      "Tu amor es mi tesoro más grande.",
      "Por siempre juntos, aunque el tiempo sea difícil.",
    ];
    let fraseIndex = 0;
    function cambiarFrase() {
      fraseIndex = (fraseIndex + 1) % frases.length;
      document.getElementById('fraseCorta').textContent = frases[fraseIndex];
    }
    setInterval(cambiarFrase, 4000);

    // Lluvia de margaritas amarillas SVG
    function crearMargarita() {
      const flores = document.getElementById('flores');
      const margarita = document.createElement('div');
      margarita.className = 'margarita';
      const size = 32 + Math.random() * 20;
      margarita.style.width = size + "px";
      margarita.style.height = size + "px";
      margarita.style.left = Math.random() * (window.innerWidth - size) + "px";
      margarita.style.top = "-50px";
      margarita.style.opacity = 0.85 + Math.random() * 0.15;
      margarita.innerHTML = `
        <svg width="${size}" height="${size}" viewBox="0 0 40 40">
          <g>
            <ellipse cx="20" cy="10" rx="6" ry="14" fill="#fffde7" stroke="#ffe082" stroke-width="1"/>
            <ellipse cx="20" cy="30" rx="6" ry="14" fill="#fffde7" stroke="#ffe082" stroke-width="1"/>
            <ellipse cx="10" cy="20" rx="14" ry="6" fill="#fffde7" stroke="#ffe082" stroke-width="1"/>
            <ellipse cx="30" cy="20" rx="14" ry="6" fill="#fffde7" stroke="#ffe082" stroke-width="1"/>
            <ellipse cx="29" cy="29" rx="9" ry="4" fill="#fffde7" stroke="#ffe082" stroke-width="1"/>
            <ellipse cx="11" cy="29" rx="9" ry="4" fill="#fffde7" stroke="#ffe082" stroke-width="1"/>
            <ellipse cx="11" cy="11" rx="9" ry="4" fill="#fffde7" stroke="#ffe082" stroke-width="1"/>
            <ellipse cx="29" cy="11" rx="9" ry="4" fill="#fffde7" stroke="#ffe082" stroke-width="1"/>
            <circle cx="20" cy="20" r="8" fill="#ffd600" stroke="#ffa000" stroke-width="2"/>
          </g>
        </svg>
      `;
      flores.appendChild(margarita);
      let velocidad = 1 + Math.random() * 2;
      let giro = Math.random() * 2 - 1;
      let posY = -50;
      let posX = parseFloat(margarita.style.left);
      function animar() {
        posY += velocidad;
        posX += giro;
        margarita.style.top = posY + 'px';
        margarita.style.left = posX + 'px';
        margarita.style.transform = `rotate(${posY * giro * 2}deg)`;
        if (posY < window.innerHeight + 40) {
          requestAnimationFrame(animar);
        } else {
          margarita.remove();
        }
      }
      animar();
    }
    setInterval(() => crearMargarita(), 350);

    // Meteoros horizontales de derecha a izquierda al inicio
    function crearMeteoro() {
      const meteorosContainer = document.getElementById('meteorosContainer');
      const meteoro = document.createElement('div');
      meteoro.className = 'meteoro';
      let initialTop = Math.random() * (window.innerHeight * 0.7) + 30;
      meteoro.style.top = initialTop + "px";
      let dur = 1.1 + Math.random() * 1.2;
      meteoro.style.animationDuration = dur + "s";
      meteoro.style.animationDelay = (Math.random() * 0.7) + "s";
      meteoro.innerHTML = `
        <div class="nucleo-meteoro"></div>
        <div class="cola-meteoro"></div>
        <div class="destello-meteoro"></div>
      `;
      meteorosContainer.appendChild(meteoro);
      setTimeout(() => {
        meteoro.remove();
      }, (dur + 0.8) * 1000);
    }
    let meteorosInterval;
    function iniciarLluviaMeteoros() {
      let cantidad = 0;
      meteorosInterval = setInterval(() => {
        crearMeteoro();
        cantidad++;
        if (cantidad > 16) clearInterval(meteorosInterval);
      }, 220);
    }
    iniciarLluviaMeteoros();

    // Animación secuencial de margarita SVG
    function animarMargarita(id) {
      const partes = document.querySelectorAll(`#${id} .parte`);
      let paso = 0;
      function siguiente() {
        if (paso < partes.length) {
          partes[paso].classList.add('visible');
          paso++;
          setTimeout(siguiente, 600 + paso*150);
        }
      }
      siguiente();
    }
    animarMargarita('margaritaIzq');
    animarMargarita('margaritaDer');

    // Corazones flotando de diferentes colores
    const coloresCorazon = [
      "#f44336", "#e91e63", "#2196f3", "#ffd600", "#ff9800", "#ce93d8", "#81d4fa", "#ffb300"
    ];
    function crearCorazon() {
      const corazones = document.getElementById('corazones');
      const corazon = document.createElement('div');
      corazon.innerHTML = "&#10084;";
      corazon.style.position = 'fixed';
      corazon.style.left = (Math.random() * window.innerWidth) + 'px';
      corazon.style.top = window.innerHeight + 'px';
      corazon.style.fontSize = (22 + Math.random()*18) + 'px';
      corazon.style.opacity = 0.7 + Math.random()*0.3;
      corazon.style.color = coloresCorazon[Math.floor(Math.random()*coloresCorazon.length)];
      corazones.appendChild(corazon);
      let posY = window.innerHeight;
      function animar() {
        posY -= 2.2 + Math.random();
        corazon.style.top = posY + 'px';
        if (posY > -30) {
          requestAnimationFrame(animar);
        } else {
          corazon.remove();
        }
      }
      animar();
    }
    setInterval(crearCorazon, 600);

    // Mensajes sorpresa motivacionales y románticos
    const frasesSorpresa = [
      "🌼 ¡Eres la mejor tutora! Tu paciencia y dedicación transforman vidas cada día.",
      "💛 Recuerda: eres capaz de todo lo que te propones. ¡Tu esfuerzo vale oro!",
      "🌈 Aunque el día esté difícil, tu sonrisa ilumina el colegio.",
      "🌻 Los niños tienen suerte de tener una guía tan especial como tú.",
      "💐 Cuando te canses, piensa en todo lo bonito que logras cada día.",
      "✨ ¡Ánimo! Tu trabajo deja huellas que duran toda la vida.",
      "💛 Te amo y admiro tu fortaleza y tu ternura. ¡Sigue brillando!",
      "🌼 Si el estrés te visita, recuerda que eres mi heroína y mi inspiración.",
      "💖 Además de una gran tutora, eres el amor de mi vida.",
      "🌸 Mañana será mejor, y hoy también lo es porque existes tú.",
      "💛 ¡Eres valiente, fuerte y hermosa por dentro y por fuera!",
      "🌻 Te mereces todo lo bueno que la vida puede dar. Te amo mucho.",
      "💐 Gracias por tu esfuerzo, tu cariño y tu amor. ¡No te rindas!",
      "✨ Cada día contigo es especial, incluso cuando sólo puedo animarte desde lejos.",
      "💖 ¡Te admiro más de lo que imaginas!",
      "🌼 Cuando el día sea largo, piensa que alguien te espera, te ama y te admira.",
      "💛 Tu trabajo importa, tu amor es luz y tu vida es ejemplo.",
    ];
    let sorpresaIndex = 0;
    document.getElementById('florPrincipal').addEventListener('mouseenter', function() {
      document.getElementById('brilloFlor').style.display = 'block';
    });
    document.getElementById('florPrincipal').addEventListener('mouseleave', function() {
      document.getElementById('brilloFlor').style.display = 'none';
    });
    document.getElementById('florPrincipal').addEventListener('click', function() {
      document.getElementById('textoSorpresa').textContent = frasesSorpresa[sorpresaIndex];
      document.getElementById('mensajeSorpresa').style.display = 'block';
      sorpresaIndex = (sorpresaIndex + 1) % frasesSorpresa.length;
    });
    function cerrarSorpresa() {
      document.getElementById('mensajeSorpresa').style.display = 'none';
    }
  </script>
</body>
</html>

[index.html.html](https://github.com/user-attachments/files/22438895/index.html.html)
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>🌼 Para ti 💛</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      width: 100vw;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: "Georgia", serif;
      color: #fff;
      background: url('https://i.pinimg.com/originals/4c/f5/60/4cf560f9eb6b4472f22c3dbd208f1b28.gif') no-repeat center center fixed;
      background-size: cover;
      background-color: pink;
      overflow: hidden;
      animation: fadein 2s;
    }
    @keyframes fadein {
      from {opacity: 0;}
      to {opacity: 1;}
    }
    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 90%;
      max-width: 1200px;
      background-color: rgba(0, 0, 0, 0.9);
      border-radius: 20px;
      box-shadow: 0 0 40px rgba(255, 0, 100, 0.9);
      padding: 40px;
      z-index: 2;
      position: relative;
    }
    .left {
      flex: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }
    .left img {
      width: 100%;
      max-width: 500px;
      border-radius: 20px;
      box-shadow: 0 0 30px rgba(255, 255, 0, 0.8);
      animation: brillos 2s infinite alternate;
    }
    @keyframes brillos {
      0% { box-shadow: 0 0 15px gold; }
      100% { box-shadow: 0 0 40px yellow; }
    }
    .right {
      flex: 1;
      padding-left: 40px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: flex-start;
    }
    .right h1 {
      font-size: 2.5em;
      margin-bottom: 20px;
      color: #ffeb3b;
      text-shadow: 2px 2px 6px #000;
    }
    .poema {
      font-size: 1.4em;
      line-height: 1.8;
      color: #fff;
      text-shadow: 2px 2px 5px #000;
      border-left: 3px solid #ffeb3b;
      padding-left: 10px;
    }
    .hidden {
      display: none;
      margin-top: 20px;
      font-size: 1.3em;
      color: #ffccff;
      text-shadow: 1px 1px 3px #000;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      border: none;
      background: #ff4081;
      color: white;
      font-size: 1em;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.2s;
    }
    button:hover {
      transform: scale(1.1);
      background: #f50057;
    }
    /* corazones y globos flotantes */
    .flotante {
      position: fixed;
      bottom: -30px;
      animation: subir 6s linear infinite;
      z-index: 1;
    }
    @keyframes subir {
      0% { transform: translateY(0) scale(1); opacity: 1; }
      100% { transform: translateY(-110vh) scale(0.5); opacity: 0; }
    }
  </style>
</head>
<body>
  <audio id="musica" loop>
  <source src="musica.mp3" type="audio/mpeg">
</audio>

<script>
  // Música empieza al primer clic
  document.body.addEventListener("click", () => {
    const audio = document.getElementById("musica");
    audio.play();
  }, { once: true });
</script>

  </audio>

  <!-- contenedor principal -->
  <div class="container">
    <div class="left">
      <!-- 🌹 tu imagen HD de Pinterest -->
      <img src="rosas_hd.jpg" alt="Ramo de rosas amarillas">
    </div>
    <div class="right">
      <h1>🌼 Para ti, mi amor 🌼</h1>
      <div class="poema" id="poema"></div>
      <button onclick="mostrarMensaje()">💌 Mensaje secreto</button>
      <div id="secreto" class="hidden">Eres lo mejor que me pasó en la vida 💛</div>
    </div>
  </div>

  <!-- script corazones + globos + texto animado -->
  <script>
    // Corazones y globos flotantes
    function crearFlotante() {
      const elem = document.createElement("div");
      elem.classList.add("flotante");
      const opciones = ["❤️","💖","💛","🎈","💘"];
      elem.innerHTML = opciones[Math.floor(Math.random()*opciones.length)];
      elem.style.left = Math.random() * 100 + "vw";
      elem.style.fontSize = (Math.random() * 20 + 15) + "px";
      elem.style.animationDuration = (Math.random() * 3 + 3) + "s";
      document.body.appendChild(elem);
      setTimeout(() => { elem.remove(); }, 6000);
    }
    setInterval(crearFlotante, 400);

    // Texto máquina de escribir
    const texto = [
      "Un ramo de rosas amarillas te entrego,",
      "como prueba del amor que siento,",
      "cada pétalo guarda un “te quiero”,",
      "y en mi corazón vives a cada momento. 💛"
    ];
    let i = 0;
    function escribirPoema() {
      if (i < texto.length) {
        const linea = document.createElement("p");
        linea.textContent = texto[i];
        document.getElementById("poema").appendChild(linea);
        i++;
        setTimeout(escribirPoema, 2000);
      }
    }
    escribirPoema();

    // Mensaje secreto
    function mostrarMensaje() {
      document.getElementById("secreto").style.display = "block";
    }
  </script>
</body>
</html>

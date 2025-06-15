<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Convite Festa Junina - Berçário</title>
  <style>
    body {
      font-family: 'Comic Sans MS', cursive;
      background: #fff8e1;
      margin: 0;
      padding: 0;
      text-align: center;
    }

    header {
      background: #ffcc80;
      padding: 20px;
      border-bottom: 5px dashed #ff6f00;
    }

    h1 {
      color: #d84315;
      font-size: 2.5em;
    }

    .convite {
      padding: 30px;
      background: #fff3e0;
      margin: 20px auto;
      width: 80%;
      border: 5px double #ffb300;
      border-radius: 20px;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
      position: relative;
    }

    .decoracao {
      position: absolute;
      width: 60px;
      height: 60px;
    }

    .decoracao.chapeu1 {
      top: -30px;
      left: -30px;
      transform: rotate(-15deg);
    }

    .decoracao.chapeu2 {
      bottom: -30px;
      right: -30px;
      transform: rotate(20deg);
    }

    .confete {
      position: absolute;
      width: 10px;
      height: 10px;
      background: red;
      border-radius: 50%;
      animation: cair 3s infinite;
    }

    @keyframes cair {
      0% { top: -10px; opacity: 1; }
      100% { top: 100%; opacity: 0; }
    }

    .fitas {
      display: flex;
      justify-content: center;
      margin: 10px 0;
    }

    .fitas div {
      width: 15px;
      height: 60px;
      margin: 0 5px;
      border-radius: 5px;
    }

    .amarela { background: #ffd600; }
    .azul { background: #2962ff; }
    .rosa { background: #f06292; }
    .verde { background: #00c853; }
  </style>
</head>
<body>
  <header>
    <h1>Convite Especial para a Festa Junina!</h1>
    <div class="fitas">
      <div class="amarela"></div>
      <div class="azul"></div>
      <div class="rosa"></div>
      <div class="verde"></div>
    </div>
  </header>

  <div class="convite">
    <img src="https://img.icons8.com/emoji/48/straw-hat.png" class="decoracao chapeu1" alt="Chapeu de palha">
    <img src="https://img.icons8.com/emoji/48/straw-hat.png" class="decoracao chapeu2" alt="Chapeu de palha">

    <p><strong>Queridos pais,</strong></p>
    <p>
      Vocês estão convidados para uma animada Festa Junina no nosso berçário!
    </p>
    <p>
      Teremos muita música, brincadeiras, comidas típicas e muita alegria!
        Treinar com essa musica para o dia da festa :)
    </p>
    <p>
      <strong>Data:</strong> 28 de junho<br>
      
      <strong>Local:</strong> Escola Benecdita
    </p>
    <p>
      Esperamos vocês com trajes típicos e muita animação!  
    </p>
    <p>
      Com carinho,<br>
      <strong>Professora Hermínia Regina</strong>
    </p>

    <!-- Vídeo da música incorporado -->
    <div style="margin-top: 30px;">
      <iframe width="360" height="215"
              src="https://www.youtube.com/embed/0NYDvwzL3lw?autoplay=1&loop=1&playlist=0NYDvwzL3lw"
              title="Música Festa Junina"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen>
      </iframe>
    </div>
  </div>

  <!-- Confetes decorativos -->
  <script>
    for (let i = 0; i < 50; i++) {
      const confete = document.createElement('div');
      confete.className = 'confete';
      confete.style.left = Math.random() * 100 + '%';
      confete.style.background = ['#ff1744', '#f50057', '#ff9100', '#00e676'][Math.floor(Math.random() * 4)];
      confete.style.animationDelay = Math.random() * 5 + 's';
      document.body.appendChild(confete);
    }
  </script>
</body>
</html>

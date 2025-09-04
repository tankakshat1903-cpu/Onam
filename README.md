<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Onam, Ente Chellam</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(to bottom, #fff8e7, #ffe4b5);
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      text-align: center;
    }

    /* Envelope */
    .envelope {
      width: 90vw;
      max-width: 350px;
      height: 220px;
      background: #d2691e;
      position: relative;
      border-radius: 10px;
      cursor: pointer;
      box-shadow: 0 5px 20px rgba(0,0,0,0.3);
    }

    .flap {
      width: 0;
      height: 0;
      border-left: 50% solid transparent;
      border-right: 50% solid transparent;
      border-bottom: 110px solid #a0522d;
      position: absolute;
      top: 0;
      left: 0;
      transition: transform 1s;
      transform-origin: top;
    }

    .envelope.open .flap {
      transform: rotateX(180deg);
    }

    /* Letter */
    .letter {
      width: 85%;
      min-height: 250px;
      background: #fffef9;
      position: absolute;
      top: 15px;
      left: 50%;
      transform: translateX(-50%) translateY(100%);
      border-radius: 10px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.25);
      transition: transform 1.5s ease;
      padding: 20px;
      box-sizing: border-box;
      overflow-y: auto;
    }

    /* Letter slides up just enough to be visible */
    .envelope.open .letter {
      transform: translateX(-50%) translateY(-40%);
    }

    h1 {
      color: #d2691e;
      font-size: 1.5em;
      margin-bottom: 15px;
      text-shadow: 0 0 8px #ffcc00;
    }

    p {
      font-size: 1.1em;
      line-height: 1.6;
      margin: 10px 0;
    }

    footer {
      margin-top: 15px;
      font-style: italic;
      font-size: 1em;
      color: #444;
    }

    /* Floating flowers */
    .flower {
      position: absolute;
      top: -50px;
      font-size: 2em;
      animation: fall linear infinite;
      opacity: 0.9;
    }

    @keyframes fall {
      0% { transform: translateY(-50px) rotate(0deg); opacity: 1; }
      100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
    }
  </style>
</head>
<body>

  <!-- Envelope -->
  <div class="envelope" onclick="this.classList.toggle('open')">
    <div class="flap"></div>
    <div class="letter">
      <h1>🌸 Happy Onam, Ente Chellam 🌸</h1>
      <p>
        I know in this special festival I am not with you,<br>
        but my blessings and love are always with you. 🌸
      </p>
      <p>
        This festival brings colors of joy and new moments of happiness,<br>
        and I wish your life always shines with the same light. ✨
      </p>
      <p>
        Today is for you celebrate, smile, and enjoy every bit of Onam. ❤️
      </p>
      <footer> Akshat</footer>
    </div>
  </div>

  <!-- Floating flowers -->
  <script>
    const flowers = ["🌸","🌼","🌺","💮"];
    for (let i = 0; i < 25; i++) {
      let flower = document.createElement("div");
      flower.className = "flower";
      flower.innerText = flowers[Math.floor(Math.random()*flowers.length)];
      flower.style.left = Math.random() * 100 + "vw";
      flower.style.animationDuration = (5 + Math.random() * 5) + "s";
      flower.style.fontSize = (1 + Math.random() * 2) + "em";
      document.body.appendChild(flower);
    }
  </script>
</body>
</html>

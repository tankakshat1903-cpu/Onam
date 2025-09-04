<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Onam 💌</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(#fff8e1, #ffecb3);
      overflow: hidden;
      font-family: 'Georgia', serif;
      text-align: center;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    /* Center container */
    .container {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

    /* Tap to open text */
    .tap-text {
      font-size: 22px;
      font-weight: bold;
      color: #8b4513;
      cursor: pointer;
      animation: blink 1.2s infinite;
    }
    @keyframes blink {
      50% { opacity: 0.4; }
    }

    /* Message card */
    .message-card {
      max-width: 350px;
      padding: 25px;
      background: #fffdf5;
      border: 2px solid gold;
      border-radius: 12px;
      box-shadow: 0 6px 15px rgba(0,0,0,0.25);
      font-size: 16px;
      line-height: 1.6;
      color: #333;
      opacity: 0;
      transform: translateY(30px);
      transition: all 1.5s ease;
      display: none;
    }
    .show-message {
      display: block;
      opacity: 1;
      transform: translateY(0);
    }

    /* Falling flowers */
    .flower {
      position: absolute;
      top: -50px;
      font-size: 22px;
      animation: fall linear infinite;
    }
    @keyframes fall {
      0% { transform: translateY(-50px) rotate(0deg); opacity: 1; }
      100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
    }
  </style>
</head>
<body>

  <div class="container">
    <div id="tapText" class="tap-text">👉 Tap here 💌</div>

    <div id="message" class="message-card">
      <p><b>Happy Onam, my dear Mole ❤️</b></p>
      <p>I know in this special festival I am not with you,<br>
      but my blessings and love are always with you. 🌸</p>
      <p>This festival brings colors of joy and new moments of happiness,<br>
      and I wish your life always shines with the same light. ✨</p>
      <p>Today is for you celebrate, smile, and enjoy every bit of Onam. ❤️</p>
      <p><b>Akshat</b></p>
    </div>
  </div>

  <!-- Music -->
  <audio id="music" loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_69e4b5c6e4.mp3?filename=kerala-traditional-instrumental-10446.mp3" type="audio/mpeg">
  </audio>

  <script>
    const tapText = document.getElementById("tapText");
    const message = document.getElementById("message");
    const music = document.getElementById("music");

    tapText.addEventListener("click", () => {
      tapText.style.display = "none";     // hide tap text
      message.style.display = "block";    // show card
      setTimeout(() => message.classList.add("show-message"), 50);
      music.play();
    });

    // Falling flowers
    function createFlower() {
      const flower = document.createElement("div");
      flower.classList.add("flower");
      flower.innerText = "🌸";
      flower.style.left = Math.random() * 100 + "vw";
      flower.style.animationDuration = (3 + Math.random() * 5) + "s";
      document.body.appendChild(flower);
      setTimeout(() => flower.remove(), 8000);
    }
    setInterval(createFlower, 800);
  </script>

</body>
</html>

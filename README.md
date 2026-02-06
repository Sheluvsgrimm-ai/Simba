<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Valentine?</title>
  <style>
    body {
      height: 100vh;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: Arial, sans-serif;
      overflow: hidden;
    }

    .box {
      text-align: center;
      background: white;
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
      z-index: 2;
    }

    h1 {
      margin-bottom: 30px;
    }

    button {
      font-size: 18px;
      padding: 12px 25px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      margin: 10px;
    }

    #yes {
      background: #ff4d88;
      color: white;
    }

    #no {
      background: #ddd;
      position: absolute;
    }

    /* Meme screen */
    .meme {
      display: none;
      position: fixed;
      inset: 0;
      background: black;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      z-index: 10;
    }

    .meme img {
      max-width: 90%;
      max-height: 70%;
      border-radius: 15px;
    }

    .meme h2 {
      color: white;
      margin-top: 20px;
      font-size: 28px;
      text-align: center;
    }
  </style>
</head>
<body>

  <div class="box" id="questionBox">
    <h1>Will you be my Valentine? 💖</h1>
    <button id="yes">Yes</button>
    <button id="no">No</button>
  </div>

  <!-- Meme Screen -->
  <div class="meme" id="memeScreen">
    <img src="https://i.imgflip.com/6n7z5k.jpg" alt="Meme">
    <h2>I knew you'd say YES 😌💘</h2>
  </div>

  <!-- Music -->
  <audio id="music">
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
  </audio>

  <script>
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    const box = document.getElementById("questionBox");
    const meme = document.getElementById("memeScreen");
    const music = document.getElementById("music");

    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 100);

      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    });

    yesBtn.addEventListener("click", () => {
      box.style.display = "none";
      meme.style.display = "flex";
      music.play();
    });
  </script>

</body>
</html>

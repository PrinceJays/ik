<!DOCTYPE html>
<html>
<head>
  <title>For My Budi ❤️</title>
  <style>
    body {
      margin: 0;
      overflow: hidden;
      background: linear-gradient(to right, #1e3c72, #2a5298);
      font-family: Arial, sans-serif;
      color: white;
      text-align: center;
    }

    #gameArea {
      position: relative;
      width: 100vw;
      height: 100vh;
    }

    #player {
      position: absolute;
      font-size: 40px;
      left: 50px;
      top: 50px;
    }

    .heart {
      position: absolute;
      font-size: 30px;
    }

    #messageBox {
      display: none;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: white;
      color: black;
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(0,0,0,0.4);
      width: 300px;
    }

    button {
      padding: 10px 20px;
      font-size: 18px;
      margin-top: 15px;
      border-radius: 8px;
      border: none;
      cursor: pointer;
      background-color: #ff4d6d;
      color: white;
    }
  </style>
</head>
<body>

<h2>Iksha, collect all the hearts ❤️</h2>

<div id="gameArea">
  <div id="player">🧍</div>
  <div class="heart" style="left:200px; top:150px;">❤️</div>
  <div class="heart" style="left:400px; top:300px;">❤️</div>
  <div class="heart" style="left:600px; top:120px;">❤️</div>
  <div class="heart" style="left:800px; top:350px;">❤️</div>
</div>

<div id="messageBox">
  <h2>My Budi ❤️</h2>
  <p>Iksha Thamsang,</p>
  <p>You unlocked my heart.</p>
  <p>Will you be my forever Player 2? 💍</p>
  <button onclick="alert('Best decision ever, My Budi ❤️')">YES</button>
</div>

<script>
  const player = document.getElementById("player");
  const hearts = document.querySelectorAll(".heart");
  const messageBox = document.getElementById("messageBox");

  let playerX = 50;
  let playerY = 50;
  let collected = 0;

  document.addEventListener("keydown", function(e) {
    if (e.key === "ArrowUp") playerY -= 20;
    if (e.key === "ArrowDown") playerY += 20;
    if (e.key === "ArrowLeft") playerX -= 20;
    if (e.key === "ArrowRight") playerX += 20;

    player.style.left = playerX + "px";
    player.style.top = playerY + "px";

    hearts.forEach((heart) => {
      const hx = heart.offsetLeft;
      const hy = heart.offsetTop;

      if (Math.abs(playerX - hx) < 30 && Math.abs(playerY - hy) < 30) {
        heart.style.display = "none";
        collected++;
      }

      if (collected === hearts.length) {
        messageBox.style.display = "block";
      }
    });
  });
</script>

</body>
</html>

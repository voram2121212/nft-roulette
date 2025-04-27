<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NFT Рулетка</title>
  <style>
    body {
      background: #111;
      color: #fff;
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 50px 20px;
    }
    h1 {
      margin-bottom: 30px;
      font-size: 2em;
    }
    #roulette {
      margin: 20px auto;
      font-size: 1.5em;
      min-height: 50px;
    }
    button {
      padding: 15px 25px;
      font-size: 18px;
      border: none;
      background-color: #ff4081;
      color: white;
      border-radius: 10px;
      cursor: pointer;
      margin-top: 30px;
    }
  </style>
</head>
<body>
  <h1>🎁 NFT Рулетка 🎁</h1>
  <div id="roulette">Готов?</div>
  <button onclick="startRoulette()">Запустить!</button>

  <script src="https://telegram.org/js/telegram-web-app.js"></script>
  <script>
    const prizes = [
      "NFT Котик 🐱",
      "NFT Робот 🤖",
      "NFT Самурай 🗡️",
      "NFT Единорог 🦄",
      "NFT Дракон 🐲",
      "NFT Картина 🎨",
      "NFT Земля 🏞️"
    ];

    let rouletteInterval;

    function startRoulette() {
      let counter = 0;
      if (rouletteInterval) clearInterval(rouletteInterval);

      rouletteInterval = setInterval(() => {
        document.getElementById('roulette').innerText = prizes[Math.floor(Math.random() * prizes.length)];
        counter++;
        if (counter > 20) { // через ~2 секунды остановка
          clearInterval(rouletteInterval);
          // можно добавить звук победы или анимацию
        }
      }, 100);
    }
  </script>
</body>
</html>

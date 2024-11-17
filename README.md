<!DOCTYPE html>
<html lang="hu">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Szerencsekerék</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f4f4f4;
    }

    .wheel-container {
      position: relative;
      width: 300px;
      height: 300px;
      border-radius: 50%;
      border: 10px solid #000;
      overflow: hidden;
      background: conic-gradient(
        #ff6347 0deg 60deg,
        #ffeb3b 60deg 120deg,
        #4caf50 120deg 180deg,
        #2196f3 180deg 240deg,
        #ff9800 240deg 300deg,
        #9c27b0 300deg 360deg
      );
    }

    .wheel {
      position: absolute;
      width: 100%;
      height: 100%;
      transform-origin: center;
      transition: transform 3s ease-out;
    }

    .wheel div {
      position: absolute;
      width: 100%;
      height: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      font-size: 20px;
      font-weight: bold;
    }

    .spinner-btn {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #4caf50;
      color: white;
      border: none;
      font-size: 18px;
      cursor: pointer;
      border-radius: 5px;
    }

    .spinner-btn:hover {
      background-color: #45a049;
    }
  </style>
</head>
<body>
  <div class="wheel-container">
    <div class="wheel" id="wheel">
      <div style="transform: rotate(0deg)">10</div>
      <div style="transform: rotate(60deg)">20</div>
      <div style="transform: rotate(120deg)">30</div>
      <div style="transform: rotate(180deg)">40</div>
      <div style="transform: rotate(240deg)">50</div>
      <div style="transform: rotate(300deg)">60</div>
    </div>
  </div>
  <button class="spinner-btn" onclick="spinWheel()">Pörgetés</button>

  <script>
    function spinWheel() {
      var wheel = document.getElementById('wheel');
      var randomDeg = Math.floor(Math.random() * 360) + 1800; // Random pörgetés
      wheel.style.transition = 'transform 3s ease-out'; // Animáció
      wheel.style.transform = 'rotate(' + randomDeg + 'deg)';
    }
  </script>
</body>
</html>

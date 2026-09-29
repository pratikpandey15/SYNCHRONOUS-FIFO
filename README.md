<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Synchronous FIFO 3D Vibe</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #0b0d17;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: 'Courier New', Courier, monospace;
      perspective: 1000px;
      overflow: hidden;
    }

    .chip-container {
      width: 300px;
      height: 400px;
      transform-style: preserve-3d;
      animation: rotateChip 8s infinite linear;
    }

    .face {
      position: absolute;
      width: 100%;
      height: 100%;
      background: rgba(10, 20, 30, 0.9);
      border: 3px solid #00ff7f;
      box-shadow: 0 0 30px #00ff7f, inset 0 0 20px #00ff7f;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      border-radius: 15px;
      backface-visibility: hidden;
      color: white;
    }

    /* Front side - Active */
    .face-front {
      transform: rotateY(0deg);
    }

    /* Back side - Status */
    .face-back {
      transform: rotateY(180deg);
      border-color: #ff0055;
      box-shadow: 0 0 30px #ff0055, inset 0 0 20px #ff0055;
    }

    h1 {
      font-size: 2.5rem;
      margin: 0;
      text-shadow: 0 0 10px currentColor;
    }

    .front-title { color: #00ff7f; }
    .back-title { color: #ff0055; }

    p {
      font-size: 1.2rem;
      letter-spacing: 2px;
      margin-top: 10px;
    }

    .pins {
      position: absolute;
      width: 120%;
      display: flex;
      justify-content: space-between;
      top: 20%;
      height: 60%;
      z-index: -1;
    }

    .pin-col {
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      width: 20px;
    }

    .pin {
      width: 100%;
      height: 10px;
      background: silver;
      box-shadow: 0 0 5px white;
    }

    @keyframes rotateChip {
      from { transform: rotateY(0deg) rotateX(10deg); }
      to { transform: rotateY(360deg) rotateX(10deg); }
    }
  </style>
</head>
<body>

  <div class="chip-container">
    <div class="pins">
      <div class="pin-col">
        <div class="pin"></div><div class="pin"></div><div class="pin"></div><div class="pin"></div><div class="pin"></div>
      </div>
      <div class="pin-col">
        <div class="pin"></div><div class="pin"></div><div class="pin"></div><div class="pin"></div><div class="pin"></div>
      </div>
    </div>
    
    <!-- Front Face -->
    <div class="face face-front">
      <h1 class="front-title">SYNC<br>FIFO</h1>
      <p>VERILOG RTL</p>
    </div>

    <!-- Back Face -->
    <div class="face face-back">
      <h1 class="back-title">STATUS</h1>
      <p>FULL : 1<br>EMPTY : 0</p>
    </div>
  </div>

</body>
</html>

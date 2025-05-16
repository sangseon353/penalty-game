# penalty-game
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <title>축구 승부차기</title>
  <style>
    body {
      font-family: sans-serif;
      background: #4CAF50;
      color: white;
      text-align: center;
      margin: 0;
      padding-top: 100px;
    }
    h1 {
      font-size: 64px;
      margin: 40px 0;
    }
    .buttons {
      margin: 30px;
    }
    .buttons button {
      font-size: 20px;
      margin: 0 15px;
      padding: 10px 20px;
      cursor: pointer;
    }
    #result {
      font-size: 64px;
      font-weight: bold;
      margin: 50px 0;
    }
    #retry {
      font-size: 14px;
      position: fixed;
      bottom: 10px;
      right: 10px;
      display: none;
    }
  </style>
</head>
<body>
  <h2>공을 어디로 찰까요?</h2>
  <div class="buttons">
    <button onclick="kick('left')">왼쪽</button>
    <button onclick="kick('center')">가운데</button>
    <button onclick="kick('right')">오른쪽</button>
  </div>
  <div id="result"></div>
  <button id="retry" onclick="resetGame()">다시하기</button>

  <script>
    function kick(playerChoice) {
      const directions = ['left', 'center', 'right'];
      const keeperChoice = directions[Math.floor(Math.random() * 3)];
      const resultText = document.getElementById("result");
      const retryButton = document.getElementById("retry");

      if (playerChoice === keeperChoice) {
        resultText.textContent = "실축";
      } else {
        resultText.textContent = "GOAL!!";
      }

      retryButton.style.display = "block";
      document.querySelector('.buttons').style.display = "none";
    }

    function resetGame() {
      document.getElementById("result").textContent = "";
      document.getElementById("retry").style.display = "none";
      document.querySelector('.buttons').style.display = "block";
    }
  </script>
</body>
</html>

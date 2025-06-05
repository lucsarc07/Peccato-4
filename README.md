<html lang="it">
<head>
  <meta charset="UTF-8">
  <style>
    /* Layout di base */
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      flex-direction: column;
    }

    .enigma {
      background-color: rgba(255, 255, 255, 0.05);
      padding: 30px 40px;
      border-radius: 20px;
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.4);
      text-align: center;
      max-width: 400px;
      width: 90%;
      margin: 20px auto;
      transition: all 0.3s ease-in-out;
    }

    h2 {
      font-size: 28px;
      margin-bottom: 20px;
      letter-spacing: 2px;
      color: #00d4ff;
    }

    input[type="text"] {
      padding: 12px;
      width: 80%;
      border: none;
      border-radius: 8px;
      margin-bottom: 15px;
      font-size: 16px;
      text-align: center;
    }

    button {
      background: #00d4ff;
      border: none;
      padding: 12px 20px;
      font-size: 16px;
      border-radius: 10px;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    button:hover {
      background: #00bcd4;
    }

    .output {
      display: none;
      font-family: 'Georgia', serif;
      font-size: 150px;
      color: #ffd700;
      font-weight: bold;
      margin: 30px 0;
      animation: pop 0.8s ease forwards;
    }

    .next-button {
      margin-top: 20px;
      font-size: 16px;
      font-weight: bold;
      letter-spacing: 1px;
      background: #4caf50;
      color: white;
    }

    .next-button:hover {
      background: #43a047;
    }

    @keyframes pop {
      0% {
        transform: scale(0.5);
        opacity: 0;
      }
      100% {
        transform: scale(1);
        opacity: 1;
      }
    }
  </style>
</head>
<body>

  <!-- Enigma 1 -->
  <div class="enigma" id="enigma1">
    <input type="text" id="answer1" placeholder="Scrivi la risposta..." />
    <button onclick="checkAnswer('enigma1', 'answer1', ['lussuria'], 'output1', 'next1')">Controlla</button>
  </div>

  <!-- Output -->
  <p class="output" id="output1">C</p>

<script>
  function checkAnswer(enigmaId, inputId, correctAnswers, outputId, nextButtonId) {
    const input = document.getElementById(inputId).value.trim().toLowerCase();
    if (correctAnswers.includes(input)) {
      document.getElementById(enigmaId).style.display = "none";
      document.getElementById(outputId).style.display = 'block';
      document.getElementById(nextButtonId).style.display = "inline-block";
    } else {
      alert("Sbagliato, riprova");
    }
  }

  function goToNext(currentId, buttonId, nextId) {
    document.getElementById(currentId).style.display = "none";
    document.getElementById(buttonId).style.display = "none";
    document.getElementById(nextId)?.classList.add('active');
  }
</script>

</body>
</html>

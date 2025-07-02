<!DOCTYPE html>
<html lang="ro">
<head>
  <meta charset="UTF-8" />
  <title>daiuuwtrack</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f9f9f9;
      padding: 50px;
      color: #222;
    }
    h1 {
      font-size: 48px;
      font-weight: 900;
      margin-bottom: 5px;
      letter-spacing: 2px;
    }
    h2 {
      font-size: 20px;
      font-weight: 400;
      color: #666;
      margin-top: 0;
      margin-bottom: 30px;
    }
    input[type="text"] {
      padding: 12px;
      width: 320px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 4px;
      margin-right: 10px;
    }
    button {
      padding: 12px 25px;
      font-size: 16px;
      border: none;
      background-color: #0077ff;
      color: white;
      border-radius: 4px;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    button:hover {
      background-color: #005fcc;
    }
    #result {
      margin-top: 30px;
      font-size: 18px;
      font-weight: 600;
      color: #333;
      min-height: 24px;
    }
  </style>
</head>
<body>
  <h1>DAIUUW.TRACK</h1>
  <h2>safe and easy</h2>
  <form id="trackForm">
    <input type="text" id="trackingCode" placeholder="Introduceți codul de tracking" required />
    <button type="submit">Caută</button>
  </form>
  <div id="result"></div>

  <script>
    const fakeStatuses = [
      "Status: Pachetul a fost preluat de curier.",
      "Status: În tranzit către hub-ul central.",
      "Status: Sosit în București, în procesare.",
      "Status: În curs de livrare.",
      "Status: Livrat cu succes."
    ];

    document.getElementById('trackForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const code = document.getElementById('trackingCode').value.trim();
      if (!code) {
        document.getElementById('result').innerText = "Te rog introdu un cod valid.";
        return;
      }

      const randomStatus = fakeStatuses[Math.floor(Math.random() * fakeStatuses.length)];

      document.getElementById('result').innerText = "Căutare status pentru: " + code + "...";
      setTimeout(() => {
        document.getElementById('result').innerText = randomStatus;
      }, 1200);
    });
  </script>
</body>
</html>

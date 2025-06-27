<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculadora de Materiales</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #e0e0e0;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
    }

    .container {
      background-color: #f5f5f5;
      padding: 30px 20px;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
      text-align: center;
      width: 90%;
      max-width: 400px;
    }

    h2 {
      color: #333;
      margin-bottom: 15px;
      font-size: 22px;
    }

    p {
      color: #444;
      font-size: 16px;
      margin: 10px 0;
    }

    input[type="number"] {
      width: 100%;
      padding: 12px;
      margin: 10px 0 20px 0;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
      background-color: #fafafa;
      outline: none;
      transition: border-color 0.3s;
    }

    input[type="number"]:focus {
      border-color: #888;
    }

    button {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      background-color: #555;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #333;
    }

    #resultado {
      margin-top: 25px;
      color: #222;
      font-size: 16px;
    }

    ul {
      padding: 0;
      list-style: none;
      margin-top: 15px;
    }

    ul li {
      background-color: #ddd;
      padding: 10px 15px;
      margin-bottom: 8px;
      border-radius: 8px;
      color: #333;
      font-weight: 500;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Calculadora de Materiales</h2>
    <p>Ingresa los metros de cable a utilizar:</p>
    <input type="number" id="metrosCable" min="0" placeholder="Ejemplo: 15">
    <button onclick="calcularMateriales()">Calcular</button>
    <div id="resultado"></div>
  </div>

  <script>
    function calcularMateriales() {
      const metros = parseFloat(document.getElementById('metrosCable').value);

      if (isNaN(metros) || metros <= 0) {
        document.getElementById('resultado').innerHTML = "<p style='color:red;'>Por favor, ingresa un número válido de metros.</p>";
        return;
      }

      const tubos = Math.ceil(metros / 3);
      const coples = tubos * 2;
      const abrazaderas = tubos * 2;

      document.getElementById('resultado').innerHTML = `
        <p><strong>Para ${metros} metros de cable necesitarás:</strong></p>
        <ul>
          <li>${tubos} tubo(s)</li>
          <li>${coples} coples </li>
          <li>${abrazaderas} abrazaderas omega </li>
        </ul>
      `;
    }
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>InvestSmart - Seu Guia de Investimentos</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: linear-gradient(135deg, #0a2540, #1b3a57);
      color: #333;
    }

    header {
      color: white;
      padding: 40px 20px;
      text-align: center;
    }

    header h1 {
      margin: 0;
      font-size: 2.5em;
    }

    nav {
      background: rgba(255,255,255,0.1);
      padding: 10px;
      text-align: center;
    }

    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }

    .container {
      padding: 20px;
      max-width: 1000px;
      margin: auto;
    }

    .card {
      background: white;
      padding: 20px;
      margin: 20px 0;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      transition: 0.2s;
    }

    .card:hover {
      transform: translateY(-5px);
    }

    button {
      background: #0a2540;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 8px;
      cursor: pointer;
      transition: 0.2s;
    }

    button:hover {
      background: #1b3a57;
      transform: scale(1.05);
    }

    input {
      padding: 10px;
      margin: 5px;
      width: 120px;
    }

    footer {
      color: white;
      text-align: center;
      padding: 20px;
    }
  </style>
</head>
<body>
  <header>
    <h1>InvestSmart</h1>
    <p>Aprenda a investir e multiplicar seu dinheiro</p>
  </header>

  <nav>
    <a href="#">Início</a>
    <a href="#">Investimentos</a>
    <a href="#">Simulador</a>
    <a href="#">Contato</a>
  </nav>

  <div class="container">
    <div class="card">
      <h2>🚀 Comece a Investir</h2>
      <p>Invista com inteligência: Tesouro, Ações, Fundos Imobiliários e mais.</p>
    </div>

    <div class="card">
      <h2>💰 Tipos de Investimento</h2>
      <ul>
        <li>Tesouro Direto (seguro)</li>
        <li>Fundos Imobiliários (renda mensal)</li>
        <li>Ações (crescimento)</li>
        <li>Criptomoedas (alto risco)</li>
      </ul>
    </div>

    <div class="card">
      <h2>📊 Simulador de Investimento</h2>
      <p>Veja quanto seu dinheiro pode crescer:</p>
      <input type="number" id="valor" placeholder="R$ mensal">
      <input type="number" id="anos" placeholder="anos">
      <button onclick="calcular()">Calcular</button>
      <p id="resultado"></p>
    </div>
  </div>

  <footer>
    <p>© 2026 InvestSmart - Todos os direitos reservados</p>
  </footer>

  <script>
    function calcular() {
      let valor = parseFloat(document.getElementById('valor').value);
      let anos = parseFloat(document.getElementById('anos').value);

      if (isNaN(valor) || isNaN(anos)) {
        document.getElementById('resultado').innerText =
          'Preencha todos os campos corretamente!';
        return;
      }

      let taxa = 0.10 / 12;
      let meses = anos * 12;
      let total = 0;

      for (let i = 0; i < meses; i++) {
        total = (total + valor) * (1 + taxa);
      }

      let investido = valor * meses;
      let lucro = total - investido;

      document.getElementById('resultado').innerHTML =
        `Total: R$ ${total.toFixed(2)} <br>
         Investido: R$ ${investido.toFixed(2)} <br>
         Lucro: R$ ${lucro.toFixed(2)}`;
    }
  </script>
</body>
</html>

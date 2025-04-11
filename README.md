- 👋 Hi, I’m @criptoarbitragemHG
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
criptoarbitragemHG/criptoarbitragemHG is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
index.html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Arbitragem de Criptomoedas</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>Oportunidades de Arbitragem</h1>
  <div id="arbitrage-table">
    <!-- Tabela será inserida aqui -->
  </div>
  <script src="script.js"></script>
</body>
</html>
style.css
body {
  font-family: Arial, sans-serif;
  margin: 20px;
  background-color: #f4f4f4;
}

h1 {
  text-align: center;
}

#arbitrage-table {
  margin-top: 20px;
}
script.js
// Exemplo de integração com a API pública da Binance
async function fetchPrices() {
  try {
    const response = await fetch('https://api.binance.com/api/v3/ticker/price');
    const data = await response.json();
    // Filtrar pares relevantes, por exemplo, BTC/USDT
    const btcPrice = data.find(item => item.symbol === 'BTCUSDT');
    document.getElementById('arbitrage-table').innerHTML = `
      <p>Preço BTC/USDT na Binance: $${parseFloat(btcPrice.price).toFixed(2)}</p>
    `;
  } catch (error) {
    console.error('Erro ao buscar dados da Binance:', error);
  }
}

fetchPrices();



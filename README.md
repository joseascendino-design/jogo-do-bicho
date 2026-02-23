<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jogo do Bicho da Família Ascendino – Vintage</title>
  <style>
    body {
      font-family: 'Courier New', Courier, monospace; /* Fonte retro */
      background: #fffacd; /* Amarelo papel velho */
      color: #000;
      margin: 0;
      padding: 20px;
      text-align: center;
    }
    h1 {
      color: #8b4513; /* Marrom vintage */
      font-size: 2.5em;
      margin-bottom: 10px;
    }
    .tabela-bichos {
      display: grid;
      grid-template-columns: repeat(5, 1fr);
      gap: 10px;
      max-width: 1000px;
      margin: 20px auto;
    }
    .bicho {
      background: #f5f5dc; /* Bege papel antigo */
      border: 3px solid #8b4513;
      border-radius: 8px;
      padding: 10px;
      font-size: 1.1em;
      box-shadow: 4px 4px 8px rgba(0,0,0,0.3); /* Sombra vintage */
    }
    .bicho strong { font-size: 1.4em; }
    .numero { font-size: 0.9em; color: #555; }
    button {
      background: #ff4500;
      color: white;
      border: none;
      padding: 20px 40px;
      font-size: 1.8em;
      border-radius: 12px;
      cursor: pointer;
      margin: 30px 0;
      box-shadow: 0 6px 12px rgba(0,0,0,0.4);
    }
    button:hover { background: #ff6347; }
    #resultado {
      font-size: 1.8em;
      background: #90ee90;
      border: 4px solid #006400;
      border-radius: 12px;
      padding: 30px;
      max-width: 800px;
      margin: 20px auto;
      min-height: 150px;
    }
  </style>
</head>
<body>
  <h1>Jogo do Bicho da Família Ascendino 🐒🐴 – Edição Vintage!</h1>
  <p>Sorteio aleatório caseiro – só diversão, sem Federal!</p>

  <div class="tabela-bichos">
    <div class="bicho"><strong>🐦 01 - Avestruz</strong><br><span class="numero">01 02 03 04</span></div>
    <div class="bicho"><strong>🦅 02 - Águia</strong><br><span class="numero">05 06 07 08</span></div>
    <div class="bicho"><strong>🐴 03 - Burro</strong><br><span class="numero">09 10 11 12</span></div>
    <div class="bicho"><strong>🦋 04 - Borboleta</strong><br><span class="numero">13 14 15 16</span></div>
    <div class="bicho"><strong>🐶 05 - Cachorro</strong><br><span class="numero">17 18 19 20</span></div>
    
    <div class="bicho"><strong>🐐 06 - Cabra</strong><br><span class="numero">21 22 23 24</span></div>
    <div class="bicho"><strong>🐑 07 - Carneiro</strong><br><span class="numero">25 26 27 28</span></div>
    <div class="bicho"><strong>🐪 08 - Camelo</strong><br><span class="numero">29 30 31 32</span></div>
    <div class="bicho"><strong>🐍 09 - Cobra</strong><br><span class="numero">33 34 35 36</span></div>
    <div class="bicho"><strong>🐰 10 - Coelho</strong><br><span class="numero">37 38 39 40</span></div>
    
    <div class="bicho"><strong>🐎 11 - Cavalo</strong><br><span class="numero">41 42 43 44</span></div>
    <div class="bicho"><strong>🐘 12 - Elefante</strong><br><span class="numero">45 46 47 48</span></div>
    <div class="bicho"><strong>🐓 13 - Galo</strong><br><span class="numero">49 50 51 52</span></div>
    <div class="bicho"><strong>🐱 14 - Gato</strong><br><span class="numero">53 54 55 56</span></div>
    <div class="bicho"><strong>🐊 15 - Jacaré</strong><br><span class="numero">57 58 59 60</span></div>
    
    <div class="bicho"><strong>🦁 16 - Leão</strong><br><span class="numero">61 62 63 64</span></div>
    <div class="bicho"><strong>🐒 17 - Macaco</strong><br><span class="numero">65 66 67 68</span></div>
    <div class="bicho"><strong>🐷 18 - Porco</strong><br><span class="numero">69 70 71 72</span></div>
    <div class="bicho"><strong>🦚 19 - Pavão</strong><br><span class="numero">73 74 75 76</span></div>
    <div class="bicho"><strong>🦃 20 - Peru</strong><br><span class="numero">77 78 79 80</span></div>
    
    <div class="bicho"><strong>🐂 21 - Touro</strong><br><span class="numero">81 82 83 84</span></div>
    <div class="bicho"><strong>🐅 22 - Tigre</strong><br><span class="numero">85 86 87 88</span></div>
    <div class="bicho"><strong>🐻 23 - Urso</strong><br><span class="numero">89 90 91 92</span></div>
    <div class="bicho"><strong>🦌 24 - Veado</strong><br><span class="numero">93 94 95 96</span></div>
    <div class="bicho"><strong>🐄 25 - Vaca</strong><br><span class="numero">97 98 99 00</span></div>
  </div>

  <button onclick="sortear()">SORTEAR O BICHO DA VEZ! 🎲</button>

  <div id="resultado">Clique no botão acima pra sortear os resultados vintage da família!</div>

  <script>
    function randomMilhar() { return Math.floor(Math.random() * 10000); }
    function formatar(num) { return String(num).padStart(4, '0'); }

    function sortear() {
      const milhar1 = formatar(randomMilhar());
      const milhar2 = formatar(randomMilhar());
      const milhar3 = formatar(randomMilhar());
      const milhar4 = formatar(randomMilhar());
      const milhar5 = formatar(randomMilhar());

      const dezena = milhar5.slice(-2); // Últimos 2 dígitos do 5º prêmio
      const grupo = Math.floor(parseInt(dezena) / 4);
      const bichos = ["Avestruz", "Águia", "Burro", "Borboleta", "Cachorro", "Cabra", "Carneiro", "Camelo", "Cobra", "Coelho", "Cavalo", "Elefante", "Galo", "Gato", "Jacaré", "Leão", "Macaco", "Porco", "Pavão", "Peru", "Touro", "Tigre", "Urso", "Veado", "Vaca"];
      const bichoVencedor = bichos[grupo];

      document.getElementById("resultado").innerHTML = `
        <strong>Resultados Vintage do Sorteio:</strong><br><br>
        1º: ${milhar1} | 2º: ${milhar2} | 3º: ${milhar3}<br>
        4º: ${milhar4} | 5º: ${milhar5}<br><br>
        <span style="font-size: 2em; color: #006400;">
          Dezena: ${dezena} → ${grupo + 1} - ${bichoVencedor} 🏆
        </span>
      `;
    }
  </script>
</body>
</html># jogo-do-bicho
BRINCADEIRA DE FAMILIA

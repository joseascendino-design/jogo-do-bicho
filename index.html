<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🎲 Jogo do Bicho da Família</title>
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@400;600;800;900&family=Fredoka+One&display=swap" rel="stylesheet">
<style>
:root {
  --verde-escuro: #0d5c2e;
  --verde: #1a7a3c;
  --verde-claro: #25a050;
  --amarelo: #f5c518;
  --laranja: #f07e16;
  --vermelho: #d93025;
  --azul: #1565c0;
  --creme: #fff8e7;
  --dourado: #d4a017;
  --branco: #ffffff;
  --sombra: 0 8px 32px rgba(0,0,0,0.25);
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: 'Baloo 2', cursive;
  background: var(--verde-escuro);
  background-image:
    radial-gradient(ellipse at 15% 15%, rgba(245,197,24,0.12) 0%, transparent 55%),
    radial-gradient(ellipse at 85% 85%, rgba(255,255,255,0.05) 0%, transparent 55%),
    repeating-linear-gradient(0deg, transparent, transparent 60px, rgba(0,0,0,0.03) 60px, rgba(0,0,0,0.03) 61px),
    repeating-linear-gradient(90deg, transparent, transparent 60px, rgba(0,0,0,0.03) 60px, rgba(0,0,0,0.03) 61px);
  min-height: 100vh;
  color: var(--branco);
  overflow-x: hidden;
}

/* ========== HEADER ========== */
header {
  text-align: center;
  padding: 28px 20px 16px;
  position: relative;
}

.header-decoration {
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 6px;
  background: repeating-linear-gradient(90deg, var(--amarelo) 0px, var(--amarelo) 20px, var(--laranja) 20px, var(--laranja) 40px, var(--vermelho) 40px, var(--vermelho) 60px, var(--verde-claro) 60px, var(--verde-claro) 80px);
}

header h1 {
  font-family: 'Fredoka One', cursive;
  font-size: clamp(2.2rem, 6vw, 4rem);
  color: var(--amarelo);
  text-shadow: 3px 3px 0 var(--verde-escuro), 5px 5px 0 rgba(0,0,0,0.3);
  letter-spacing: 2px;
  animation: titleBounce 0.8s ease-out;
}

header p.subtitle {
  font-size: 1.1rem;
  color: rgba(255,255,255,0.85);
  margin-top: 4px;
  font-weight: 600;
}

@keyframes titleBounce {
  0% { transform: scale(0.5) rotate(-5deg); opacity: 0; }
  70% { transform: scale(1.08) rotate(1deg); }
  100% { transform: scale(1) rotate(0deg); opacity: 1; }
}

/* ========== MAIN CONTAINER ========== */
main {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 16px 60px;
}

/* ========== TABS ========== */
.tabs {
  display: flex;
  gap: 8px;
  justify-content: center;
  margin-bottom: 28px;
  flex-wrap: wrap;
}

.tab-btn {
  font-family: 'Baloo 2', cursive;
  font-size: 1rem;
  font-weight: 800;
  padding: 10px 24px;
  border: 3px solid rgba(255,255,255,0.3);
  border-radius: 50px;
  background: rgba(255,255,255,0.1);
  color: white;
  cursor: pointer;
  transition: all 0.2s;
  backdrop-filter: blur(4px);
}
.tab-btn:hover { background: rgba(255,255,255,0.2); transform: translateY(-2px); }
.tab-btn.active {
  background: var(--amarelo);
  color: var(--verde-escuro);
  border-color: var(--amarelo);
  box-shadow: 0 4px 20px rgba(245,197,24,0.4);
  transform: translateY(-2px);
}

/* ========== PANELS ========== */
.panel { display: none; animation: fadeIn 0.35s ease; }
.panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: translateY(0); } }

/* ========== SORTEIO PANEL ========== */
.sorteio-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 28px;
}

.drum-wrapper {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.drum {
  width: 240px;
  height: 240px;
  border-radius: 50%;
  background: radial-gradient(circle at 35% 35%, #5d4e37, #2c1f0e);
  border: 8px solid var(--dourado);
  box-shadow: 0 0 0 4px rgba(0,0,0,0.3), inset 0 8px 20px rgba(255,255,255,0.1), 0 20px 50px rgba(0,0,0,0.4);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: transform 0.15s;
  position: relative;
  overflow: hidden;
}

.drum::before {
  content: '';
  position: absolute;
  top: 8%; left: 8%;
  width: 30%; height: 30%;
  background: radial-gradient(circle, rgba(255,255,255,0.25), transparent);
  border-radius: 50%;
}

.drum-inner {
  font-size: 5rem;
  transition: transform 0.3s;
  filter: drop-shadow(0 4px 8px rgba(0,0,0,0.5));
  user-select: none;
}

.drum:hover { transform: scale(1.04); }
.drum:active { transform: scale(0.97); }
.drum.spinning .drum-inner { animation: spin 0.1s linear infinite; }

@keyframes spin {
  0% { transform: rotate(-15deg) scale(0.8); opacity: 0.5; }
  50% { transform: rotate(15deg) scale(1.1); opacity: 1; }
  100% { transform: rotate(-15deg) scale(0.8); opacity: 0.5; }
}

.drum-label {
  font-family: 'Fredoka One', cursive;
  font-size: 1rem;
  color: var(--dourado);
  text-align: center;
  letter-spacing: 1px;
}

/* Resultado */
.resultado-box {
  background: linear-gradient(135deg, rgba(255,255,255,0.12), rgba(255,255,255,0.05));
  border: 3px solid var(--amarelo);
  border-radius: 24px;
  padding: 28px 44px;
  text-align: center;
  min-width: 320px;
  backdrop-filter: blur(10px);
  box-shadow: var(--sombra), 0 0 0 1px rgba(255,255,255,0.1);
  transition: all 0.4s;
}

.resultado-box.hidden { opacity: 0.4; filter: blur(2px); }
.resultado-box.revealed { opacity: 1; filter: none; animation: revealPop 0.5s cubic-bezier(0.34, 1.56, 0.64, 1); }

@keyframes revealPop {
  0% { transform: scale(0.7); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}

.resultado-emoji { font-size: 5rem; display: block; margin-bottom: 8px; }
.resultado-nome {
  font-family: 'Fredoka One', cursive;
  font-size: 2.4rem;
  color: var(--amarelo);
  text-shadow: 2px 2px 0 var(--verde-escuro);
}
.resultado-grupo {
  font-size: 1.1rem;
  color: rgba(255,255,255,0.7);
  margin-top: 6px;
}
.resultado-numeros {
  margin-top: 12px;
  display: flex;
  gap: 10px;
  justify-content: center;
  flex-wrap: wrap;
}
.num-badge {
  background: var(--verde-escuro);
  border: 2px solid var(--dourado);
  border-radius: 12px;
  padding: 4px 14px;
  font-weight: 800;
  font-size: 1.1rem;
  color: var(--amarelo);
}

.btn-sortear {
  font-family: 'Fredoka One', cursive;
  font-size: 1.6rem;
  padding: 18px 56px;
  background: linear-gradient(135deg, var(--amarelo), var(--laranja));
  color: var(--verde-escuro);
  border: none;
  border-radius: 60px;
  cursor: pointer;
  box-shadow: 0 6px 24px rgba(240,126,22,0.5), 0 0 0 4px rgba(245,197,24,0.2);
  transition: all 0.2s;
  letter-spacing: 1px;
}
.btn-sortear:hover { transform: translateY(-4px) scale(1.03); box-shadow: 0 12px 32px rgba(240,126,22,0.6); }
.btn-sortear:active { transform: translateY(0) scale(0.97); }
.btn-sortear:disabled { opacity: 0.6; cursor: not-allowed; transform: none; }

/* Histórico */
.historico-wrap {
  width: 100%;
  max-width: 600px;
}
.historico-titulo {
  font-family: 'Fredoka One', cursive;
  font-size: 1.3rem;
  color: var(--amarelo);
  margin-bottom: 10px;
  text-align: center;
}
.historico-lista {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  justify-content: center;
  min-height: 44px;
}
.hist-item {
  background: rgba(255,255,255,0.1);
  border: 2px solid rgba(255,255,255,0.2);
  border-radius: 50px;
  padding: 5px 16px;
  font-size: 1rem;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 6px;
  animation: popIn 0.3s ease;
}
@keyframes popIn { from { transform: scale(0); } to { transform: scale(1); } }

/* ========== TABELA PANEL ========== */
.tabela-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  gap: 14px;
}

.animal-card {
  background: linear-gradient(135deg, rgba(255,255,255,0.13), rgba(255,255,255,0.05));
  border: 2px solid rgba(255,255,255,0.18);
  border-radius: 20px;
  padding: 16px 12px;
  text-align: center;
  cursor: pointer;
  transition: all 0.2s;
  backdrop-filter: blur(4px);
  position: relative;
  overflow: hidden;
}

.animal-card::before {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, transparent, rgba(255,255,255,0.05));
  opacity: 0;
  transition: opacity 0.2s;
}

.animal-card:hover {
  transform: translateY(-6px) scale(1.03);
  border-color: var(--amarelo);
  box-shadow: 0 12px 32px rgba(0,0,0,0.3), 0 0 0 2px rgba(245,197,24,0.3);
}
.animal-card:hover::before { opacity: 1; }

.animal-card.destaque {
  border-color: var(--amarelo);
  background: linear-gradient(135deg, rgba(245,197,24,0.25), rgba(245,197,24,0.08));
  box-shadow: 0 0 0 3px rgba(245,197,24,0.4), 0 8px 24px rgba(0,0,0,0.2);
  animation: cardGlow 1s ease-in-out infinite alternate;
}

@keyframes cardGlow {
  from { box-shadow: 0 0 0 3px rgba(245,197,24,0.4), 0 8px 24px rgba(0,0,0,0.2); }
  to { box-shadow: 0 0 0 6px rgba(245,197,24,0.7), 0 12px 32px rgba(245,197,24,0.2); }
}

.card-emoji { font-size: 3rem; margin-bottom: 6px; display: block; }
.card-grupo {
  font-family: 'Fredoka One', cursive;
  font-size: 0.85rem;
  color: var(--amarelo);
  background: var(--verde-escuro);
  border-radius: 50px;
  padding: 2px 10px;
  display: inline-block;
  margin-bottom: 4px;
}
.card-nome {
  font-weight: 800;
  font-size: 1rem;
  color: white;
  display: block;
  margin-bottom: 4px;
}
.card-nums {
  font-size: 0.78rem;
  color: rgba(255,255,255,0.6);
  font-weight: 600;
}

/* ========== APOSTAR PANEL ========== */
.apostar-section {
  max-width: 700px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.apostar-titulo {
  font-family: 'Fredoka One', cursive;
  font-size: 1.8rem;
  color: var(--amarelo);
  text-align: center;
  text-shadow: 2px 2px 0 var(--verde-escuro);
}

.escolha-animal {
  background: rgba(255,255,255,0.08);
  border-radius: 20px;
  padding: 20px;
  border: 2px solid rgba(255,255,255,0.15);
}

.escolha-animal h3 {
  font-weight: 800;
  margin-bottom: 14px;
  font-size: 1.1rem;
  color: rgba(255,255,255,0.9);
}

.mini-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(70px, 1fr));
  gap: 8px;
}

.mini-card {
  background: rgba(255,255,255,0.1);
  border: 2px solid rgba(255,255,255,0.15);
  border-radius: 14px;
  padding: 8px 4px;
  text-align: center;
  cursor: pointer;
  transition: all 0.15s;
  font-size: 0.72rem;
  font-weight: 700;
}
.mini-card:hover { background: rgba(255,255,255,0.2); transform: scale(1.05); }
.mini-card.selecionado {
  background: linear-gradient(135deg, var(--amarelo), var(--laranja));
  border-color: var(--amarelo);
  color: var(--verde-escuro);
  font-weight: 900;
  transform: scale(1.08);
  box-shadow: 0 4px 14px rgba(245,197,24,0.4);
}
.mini-card span { font-size: 1.5rem; display: block; }

.apostas-lista {
  background: rgba(255,255,255,0.08);
  border-radius: 20px;
  padding: 20px;
  border: 2px solid rgba(255,255,255,0.15);
}
.apostas-lista h3 { font-weight: 800; margin-bottom: 14px; font-size: 1.1rem; }

.aposta-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(255,255,255,0.07);
  border-radius: 14px;
  padding: 10px 16px;
  margin-bottom: 8px;
  font-weight: 700;
  font-size: 0.95rem;
  animation: popIn 0.3s ease;
}
.aposta-item .aposta-animal { display: flex; align-items: center; gap: 8px; }
.aposta-item .btn-remover {
  background: var(--vermelho);
  border: none;
  border-radius: 50%;
  width: 28px; height: 28px;
  color: white;
  font-size: 1rem;
  cursor: pointer;
  display: flex; align-items: center; justify-content: center;
  transition: transform 0.15s;
}
.aposta-item .btn-remover:hover { transform: scale(1.15); }

.btn-adicionar {
  font-family: 'Fredoka One', cursive;
  font-size: 1.1rem;
  padding: 12px 32px;
  background: linear-gradient(135deg, var(--verde-claro), var(--verde));
  color: white;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  box-shadow: 0 4px 16px rgba(0,0,0,0.3);
  transition: all 0.2s;
  width: 100%;
  margin-top: 8px;
}
.btn-adicionar:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,0,0,0.3); }

.btn-revelar {
  font-family: 'Fredoka One', cursive;
  font-size: 1.4rem;
  padding: 16px 40px;
  background: linear-gradient(135deg, var(--vermelho), #c0392b);
  color: white;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  box-shadow: 0 6px 24px rgba(217,48,37,0.5);
  transition: all 0.2s;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}
.btn-revelar:hover { transform: translateY(-4px); box-shadow: 0 12px 32px rgba(217,48,37,0.6); }
.btn-revelar:disabled { opacity: 0.5; cursor: not-allowed; transform: none; }

/* Resultado apostas */
.resultado-apostas {
  background: linear-gradient(135deg, rgba(255,255,255,0.12), rgba(255,255,255,0.06));
  border: 3px solid var(--amarelo);
  border-radius: 24px;
  padding: 24px;
  display: none;
  animation: revealPop 0.5s ease;
}
.resultado-apostas h3 {
  font-family: 'Fredoka One', cursive;
  font-size: 1.6rem;
  color: var(--amarelo);
  text-align: center;
  margin-bottom: 16px;
}
.aposta-resultado-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 16px;
  border-radius: 14px;
  margin-bottom: 8px;
  font-weight: 800;
  font-size: 1rem;
}
.aposta-resultado-item.ganhou {
  background: linear-gradient(90deg, rgba(37,160,80,0.4), rgba(37,160,80,0.1));
  border: 2px solid var(--verde-claro);
}
.aposta-resultado-item.perdeu {
  background: rgba(255,255,255,0.05);
  border: 2px solid rgba(255,255,255,0.1);
  opacity: 0.7;
}
.tag-ganhou {
  background: var(--verde-claro);
  color: white;
  border-radius: 50px;
  padding: 3px 14px;
  font-size: 0.85rem;
}
.tag-perdeu {
  background: rgba(255,255,255,0.2);
  color: rgba(255,255,255,0.7);
  border-radius: 50px;
  padding: 3px 14px;
  font-size: 0.85rem;
}

/* ========== CONFETTI ========== */
.confetti-container {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  pointer-events: none;
  z-index: 9999;
  overflow: hidden;
}
.confetti-piece {
  position: absolute;
  width: 12px; height: 12px;
  border-radius: 2px;
  animation: confettiFall linear forwards;
}
@keyframes confettiFall {
  0% { transform: translateY(-20px) rotate(0deg); opacity: 1; }
  100% { transform: translateY(110vh) rotate(720deg); opacity: 0; }
}

/* ========== PLACAR ========== */
.placar-box {
  background: rgba(255,255,255,0.08);
  border-radius: 20px;
  padding: 20px;
  border: 2px solid rgba(255,255,255,0.15);
  max-width: 700px;
  margin: 0 auto;
}
.placar-titulo {
  font-family: 'Fredoka One', cursive;
  font-size: 1.5rem;
  color: var(--amarelo);
  text-align: center;
  margin-bottom: 16px;
}
.placar-lista { display: flex; flex-direction: column; gap: 8px; }
.placar-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(255,255,255,0.07);
  border-radius: 14px;
  padding: 10px 18px;
  font-weight: 700;
  font-size: 1rem;
}
.placar-item:first-child { background: linear-gradient(90deg, rgba(245,197,24,0.3), rgba(245,197,24,0.05)); border: 2px solid rgba(245,197,24,0.4); }
.placar-wins { color: var(--amarelo); font-family: 'Fredoka One', cursive; font-size: 1.2rem; }

.btn-limpar-placar {
  font-family: 'Fredoka One', cursive;
  padding: 10px 28px;
  background: rgba(255,255,255,0.1);
  color: rgba(255,255,255,0.7);
  border: 2px solid rgba(255,255,255,0.2);
  border-radius: 50px;
  cursor: pointer;
  margin-top: 16px;
  display: block;
  margin-left: auto;
  transition: all 0.2s;
}
.btn-limpar-placar:hover { background: rgba(255,255,255,0.2); }

.empty-msg {
  text-align: center;
  color: rgba(255,255,255,0.4);
  font-size: 1rem;
  padding: 20px;
}

/* ========== MODAL ========== */
.modal-overlay {
  position: fixed; inset: 0;
  background: rgba(0,0,0,0.7);
  backdrop-filter: blur(6px);
  z-index: 1000;
  display: none;
  align-items: center;
  justify-content: center;
}
.modal-overlay.open { display: flex; }
.modal {
  background: linear-gradient(145deg, #1a4a2a, #0d3320);
  border: 3px solid var(--amarelo);
  border-radius: 28px;
  padding: 36px;
  max-width: 420px;
  width: 92%;
  text-align: center;
  animation: revealPop 0.4s ease;
  box-shadow: 0 24px 64px rgba(0,0,0,0.6), 0 0 0 1px rgba(255,255,255,0.1);
}
.modal-emoji { font-size: 5rem; margin-bottom: 12px; }
.modal h2 { font-family: 'Fredoka One', cursive; font-size: 2rem; color: var(--amarelo); margin-bottom: 8px; }
.modal p { color: rgba(255,255,255,0.8); margin-bottom: 6px; font-size: 1rem; }
.modal-nums { display: flex; gap: 10px; justify-content: center; flex-wrap: wrap; margin: 14px 0; }
.btn-fechar-modal {
  font-family: 'Fredoka One', cursive;
  font-size: 1.1rem;
  padding: 12px 36px;
  background: var(--amarelo);
  color: var(--verde-escuro);
  border: none;
  border-radius: 50px;
  cursor: pointer;
  margin-top: 12px;
  transition: all 0.2s;
}
.btn-fechar-modal:hover { transform: scale(1.05); }

/* ========== INPUT JOGADOR ========== */
.jogador-input-wrap {
  display: flex;
  gap: 10px;
  align-items: center;
  margin-bottom: 8px;
}
.jogador-input-wrap label { font-weight: 700; font-size: 0.95rem; white-space: nowrap; }
.jogador-input {
  font-family: 'Baloo 2', cursive;
  font-size: 1rem;
  font-weight: 700;
  padding: 8px 16px;
  background: rgba(255,255,255,0.12);
  border: 2px solid rgba(255,255,255,0.25);
  border-radius: 50px;
  color: white;
  outline: none;
  flex: 1;
  transition: border-color 0.2s;
}
.jogador-input::placeholder { color: rgba(255,255,255,0.4); }
.jogador-input:focus { border-color: var(--amarelo); }

/* ========== RESPONSIVO ========== */
@media (max-width: 600px) {
  .resultado-box { min-width: unset; padding: 20px 20px; }
  .tabela-grid { grid-template-columns: repeat(auto-fill, minmax(130px, 1fr)); gap: 10px; }
  .mini-grid { grid-template-columns: repeat(auto-fill, minmax(60px, 1fr)); }
}

/* Starfield animation */
.star {
  position: fixed;
  border-radius: 50%;
  background: white;
  opacity: 0;
  animation: twinkle linear infinite;
  pointer-events: none;
  z-index: 0;
}
@keyframes twinkle {
  0%, 100% { opacity: 0; transform: scale(0.5); }
  50% { opacity: 0.4; transform: scale(1); }
}
</style>
</head>
<body>

<div class="confetti-container" id="confettiContainer"></div>

<!-- Stars -->
<div id="stars"></div>

<header>
  <div class="header-decoration"></div>
  <h1>🎲 JOGO DO BICHO 🎲</h1>
  <p class="subtitle">🌟 A diversão da família — onde estiver! 🌟</p>
</header>

<main>
  <!-- TABS -->
  <div class="tabs">
    <button class="tab-btn active" onclick="showPanel('sorteio')">🎰 Sortear</button>
    <button class="tab-btn" onclick="showPanel('apostar')">🃏 Apostar</button>
    <button class="tab-btn" onclick="showPanel('tabela')">📋 Tabela</button>
    <button class="tab-btn" onclick="showPanel('placar')">🏆 Placar</button>
  </div>

  <!-- ===== SORTEIO PANEL ===== -->
  <div class="panel active" id="panel-sorteio">
    <div class="sorteio-container">
      <div class="drum-wrapper">
        <div class="drum" id="drumEl" onclick="iniciarSorteio()">
          <div class="drum-inner" id="drumEmoji">🎰</div>
        </div>
        <div class="drum-label">CLIQUE NA URNA PARA SORTEAR!</div>
      </div>

      <button class="btn-sortear" id="btnSortear" onclick="iniciarSorteio()">
        🎲 GIRAR A URNA!
      </button>

      <div class="resultado-box hidden" id="resultadoBox">
        <span class="resultado-emoji" id="resEmoji">🎰</span>
        <div class="resultado-nome" id="resNome">—</div>
        <div class="resultado-grupo" id="resGrupo">—</div>
        <div class="resultado-numeros" id="resNumeros"></div>
      </div>

      <div class="historico-wrap">
        <div class="historico-titulo">🕐 Últimos sorteios</div>
        <div class="historico-lista" id="historicoLista">
          <span class="empty-msg" style="font-size:0.9rem">Nenhum sorteio ainda</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ===== APOSTAR PANEL ===== -->
  <div class="panel" id="panel-apostar">
    <div class="apostar-section">
      <div class="apostar-titulo">🃏 Faça suas apostas!</div>

      <div class="escolha-animal" style="padding-bottom:12px">
        <div class="jogador-input-wrap">
          <label>👤 Jogador:</label>
          <input type="text" class="jogador-input" id="nomeJogador" placeholder="Seu nome..." maxlength="20">
        </div>
        <h3>🐾 Escolha um animal:</h3>
        <div class="mini-grid" id="miniGrid"></div>
        <button class="btn-adicionar" onclick="adicionarAposta()">✅ Adicionar aposta</button>
      </div>

      <div class="apostas-lista">
        <h3>📝 Apostas da rodada:</h3>
        <div id="listaApostas"><div class="empty-msg">Nenhuma aposta ainda</div></div>
      </div>

      <button class="btn-revelar" id="btnRevelar" onclick="revelarResultadoApostas()" disabled>
        🎰 REVELAR RESULTADO!
      </button>

      <div class="resultado-apostas" id="resultadoApostas">
        <h3 id="resApostasTitle">🎊 Resultado!</h3>
        <div id="resApostasList"></div>
      </div>
    </div>
  </div>

  <!-- ===== TABELA PANEL ===== -->
  <div class="panel" id="panel-tabela">
    <div class="tabela-grid" id="tabelaGrid"></div>
  </div>

  <!-- ===== PLACAR PANEL ===== -->
  <div class="panel" id="panel-placar">
    <div class="placar-box">
      <div class="placar-titulo">🏆 Placar de Vitórias</div>
      <div class="placar-lista" id="placarLista">
        <div class="empty-msg">Nenhuma vitória ainda. Vamos jogar!</div>
      </div>
      <button class="btn-limpar-placar" onclick="limparPlacar()">🗑️ Zerar placar</button>
    </div>
  </div>
</main>

<!-- Modal animal detalhes -->
<div class="modal-overlay" id="modalOverlay" onclick="fecharModal(event)">
  <div class="modal">
    <div class="modal-emoji" id="modalEmoji">🐯</div>
    <h2 id="modalNome">Animal</h2>
    <p id="modalGrupo">Grupo X</p>
    <div class="modal-nums" id="modalNums"></div>
    <button class="btn-fechar-modal" onclick="fecharModal(null, true)">Fechar</button>
  </div>
</div>

<script>
// ========== DADOS DO JOGO DO BICHO ==========
const ANIMAIS = [
  { grupo: 1,  nome: 'Avestruz',   emoji: '🦚', numeros: [1, 2, 3, 4] },
  { grupo: 2,  nome: 'Águia',      emoji: '🦅', numeros: [5, 6, 7, 8] },
  { grupo: 3,  nome: 'Burro',      emoji: '🫏', numeros: [9, 10, 11, 12] },
  { grupo: 4,  nome: 'Borboleta',  emoji: '🦋', numeros: [13, 14, 15, 16] },
  { grupo: 5,  nome: 'Cachorro',   emoji: '🐶', numeros: [17, 18, 19, 20] },
  { grupo: 6,  nome: 'Cabra',      emoji: '🐐', numeros: [21, 22, 23, 24] },
  { grupo: 7,  nome: 'Carneiro',   emoji: '🐑', numeros: [25, 26, 27, 28] },
  { grupo: 8,  nome: 'Camelo',     emoji: '🐪', numeros: [29, 30, 31, 32] },
  { grupo: 9,  nome: 'Cobra',      emoji: '🐍', numeros: [33, 34, 35, 36] },
  { grupo: 10, nome: 'Coelho',     emoji: '🐰', numeros: [37, 38, 39, 40] },
  { grupo: 11, nome: 'Cavalo',     emoji: '🐴', numeros: [41, 42, 43, 44] },
  { grupo: 12, nome: 'Elefante',   emoji: '🐘', numeros: [45, 46, 47, 48] },
  { grupo: 13, nome: 'Galo',       emoji: '🐓', numeros: [49, 50, 51, 52] },
  { grupo: 14, nome: 'Gato',       emoji: '🐱', numeros: [53, 54, 55, 56] },
  { grupo: 15, nome: 'Jacaré',     emoji: '🐊', numeros: [57, 58, 59, 60] },
  { grupo: 16, nome: 'Leão',       emoji: '🦁', numeros: [61, 62, 63, 64] },
  { grupo: 17, nome: 'Macaco',     emoji: '🐵', numeros: [65, 66, 67, 68] },
  { grupo: 18, nome: 'Porco',      emoji: '🐷', numeros: [69, 70, 71, 72] },
  { grupo: 19, nome: 'Pavão',      emoji: '🦜', numeros: [73, 74, 75, 76] },
  { grupo: 20, nome: 'Peru',       emoji: '🦃', numeros: [77, 78, 79, 80] },
  { grupo: 21, nome: 'Touro',      emoji: '🐂', numeros: [81, 82, 83, 84] },
  { grupo: 22, nome: 'Tigre',      emoji: '🐯', numeros: [85, 86, 87, 88] },
  { grupo: 23, nome: 'Urso',       emoji: '🐻', numeros: [89, 90, 91, 92] },
  { grupo: 24, nome: 'Veado',      emoji: '🦌', numeros: [93, 94, 95, 96] },
  { grupo: 25, nome: 'Vaca',       emoji: '🐄', numeros: [97, 98, 99, 0] }
];

// ========== STATE ==========
let sorteioAtual = null;
let historico = [];
let apostas = [];
let placar = JSON.parse(localStorage.getItem('jb_placar') || '{}');
let animalSelecionado = null;
let sorteando = false;

// ========== INICIALIZAÇÃO ==========
document.addEventListener('DOMContentLoaded', () => {
  criarEstrelas();
  renderizarTabela();
  renderizarMiniGrid();
  atualizarPlacar();
});

function criarEstrelas() {
  const cont = document.getElementById('stars');
  for (let i = 0; i < 30; i++) {
    const s = document.createElement('div');
    s.className = 'star';
    s.style.cssText = `
      width: ${Math.random()*3+1}px;
      height: ${Math.random()*3+1}px;
      left: ${Math.random()*100}%;
      top: ${Math.random()*100}%;
      animation-duration: ${Math.random()*4+3}s;
      animation-delay: ${Math.random()*5}s;
    `;
    cont.appendChild(s);
  }
}

// ========== TABS ==========
function showPanel(id) {
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  event.currentTarget.classList.add('active');
}

// ========== SORTEIO ==========
function iniciarSorteio() {
  if (sorteando) return;
  sorteando = true;
  const drum = document.getElementById('drumEl');
  const drumEmoji = document.getElementById('drumEmoji');
  const btn = document.getElementById('btnSortear');
  const resBox = document.getElementById('resultadoBox');

  btn.disabled = true;
  drum.classList.add('spinning');
  resBox.classList.remove('revealed');
  resBox.classList.add('hidden');

  // Embaralha emojis enquanto gira
  let tick = 0;
  const interval = setInterval(() => {
    drumEmoji.textContent = ANIMAIS[Math.floor(Math.random() * ANIMAIS.length)].emoji;
    tick++;
  }, 80);

  setTimeout(() => {
    clearInterval(interval);
    drum.classList.remove('spinning');

    // Sorteia resultado
    const sorteado = ANIMAIS[Math.floor(Math.random() * ANIMAIS.length)];
    sorteioAtual = sorteado;
    drumEmoji.textContent = sorteado.emoji;

    // Atualiza resultado
    document.getElementById('resEmoji').textContent = sorteado.emoji;
    document.getElementById('resNome').textContent = sorteado.nome;
    document.getElementById('resGrupo').textContent = `Grupo ${String(sorteado.grupo).padStart(2,'0')}`;
    const numsEl = document.getElementById('resNumeros');
    numsEl.innerHTML = sorteado.numeros.map(n =>
      `<span class="num-badge">${String(n).padStart(2,'0')}</span>`
    ).join('');

    resBox.classList.remove('hidden');
    resBox.classList.add('revealed');

    // Histórico
    adicionarHistorico(sorteado);

    // Destaque na tabela
    destacarAnimalTabela(sorteado.grupo);

    btn.disabled = false;
    sorteando = false;
  }, 2000);
}

function adicionarHistorico(animal) {
  historico.unshift(animal);
  if (historico.length > 8) historico.pop();

  const lista = document.getElementById('historicoLista');
  lista.innerHTML = historico.map(a =>
    `<div class="hist-item">${a.emoji} <span>${a.nome}</span></div>`
  ).join('');
}

function destacarAnimalTabela(grupo) {
  document.querySelectorAll('.animal-card').forEach(c => c.classList.remove('destaque'));
  const card = document.querySelector(`.animal-card[data-grupo="${grupo}"]`);
  if (card) card.classList.add('destaque');
}

// ========== TABELA ==========
function renderizarTabela() {
  const grid = document.getElementById('tabelaGrid');
  grid.innerHTML = ANIMAIS.map(a => `
    <div class="animal-card" data-grupo="${a.grupo}" onclick="abrirModal(${a.grupo})">
      <span class="card-emoji">${a.emoji}</span>
      <span class="card-grupo">Grupo ${String(a.grupo).padStart(2,'0')}</span>
      <span class="card-nome">${a.nome}</span>
      <div class="card-nums">${a.numeros.map(n => String(n).padStart(2,'0')).join(' · ')}</div>
    </div>
  `).join('');
}

// ========== MODAL ==========
function abrirModal(grupo) {
  const a = ANIMAIS.find(x => x.grupo === grupo);
  document.getElementById('modalEmoji').textContent = a.emoji;
  document.getElementById('modalNome').textContent = a.nome;
  document.getElementById('modalGrupo').textContent = `Grupo ${String(a.grupo).padStart(2,'0')}`;
  document.getElementById('modalNums').innerHTML = a.numeros.map(n =>
    `<span class="num-badge">${String(n).padStart(2,'0')}</span>`
  ).join('');
  document.getElementById('modalOverlay').classList.add('open');
}

function fecharModal(e, force) {
  if (force || e?.target?.id === 'modalOverlay') {
    document.getElementById('modalOverlay').classList.remove('open');
  }
}

// ========== MINI GRID / APOSTAS ==========
function renderizarMiniGrid() {
  const grid = document.getElementById('miniGrid');
  grid.innerHTML = ANIMAIS.map(a => `
    <div class="mini-card" data-grupo="${a.grupo}" onclick="selecionarAnimal(${a.grupo})">
      <span>${a.emoji}</span>
      ${a.nome}
    </div>
  `).join('');
}

function selecionarAnimal(grupo) {
  animalSelecionado = ANIMAIS.find(a => a.grupo === grupo);
  document.querySelectorAll('.mini-card').forEach(c => c.classList.remove('selecionado'));
  document.querySelector(`.mini-card[data-grupo="${grupo}"]`).classList.add('selecionado');
}

function adicionarAposta() {
  const nome = document.getElementById('nomeJogador').value.trim() || 'Anônimo';
  if (!animalSelecionado) {
    alert('Escolha um animal primeiro! 🐾');
    return;
  }
  apostas.push({ nome, animal: animalSelecionado });
  animalSelecionado = null;
  document.querySelectorAll('.mini-card').forEach(c => c.classList.remove('selecionado'));
  renderizarApostas();
  document.getElementById('btnRevelar').disabled = false;
  document.getElementById('resultadoApostas').style.display = 'none';
}

function removerAposta(idx) {
  apostas.splice(idx, 1);
  renderizarApostas();
  if (apostas.length === 0) {
    document.getElementById('btnRevelar').disabled = true;
  }
}

function renderizarApostas() {
  const lista = document.getElementById('listaApostas');
  if (apostas.length === 0) {
    lista.innerHTML = '<div class="empty-msg">Nenhuma aposta ainda</div>';
    return;
  }
  lista.innerHTML = apostas.map((ap, i) => `
    <div class="aposta-item">
      <div class="aposta-animal">
        <span style="font-size:1.6rem">${ap.animal.emoji}</span>
        <span><strong>${ap.nome}</strong> aposta em <strong>${ap.animal.nome}</strong></span>
      </div>
      <button class="btn-remover" onclick="removerAposta(${i})">✕</button>
    </div>
  `).join('');
}

function revelarResultadoApostas() {
  // Faz sorteio automático
  const sorteado = ANIMAIS[Math.floor(Math.random() * ANIMAIS.length)];
  sorteioAtual = sorteado;

  const resDiv = document.getElementById('resultadoApostas');
  const title = document.getElementById('resApostasTitle');
  const list = document.getElementById('resApostasList');

  let algumGanhou = false;
  const html = apostas.map(ap => {
    const ganhou = ap.animal.grupo === sorteado.grupo;
    if (ganhou) { algumGanhou = true; registrarVitoria(ap.nome); }
    return `
      <div class="aposta-resultado-item ${ganhou ? 'ganhou' : 'perdeu'}">
        <span style="font-size:1.8rem">${ap.animal.emoji}</span>
        <span style="flex:1"><strong>${ap.nome}</strong> — ${ap.animal.nome}</span>
        <span class="${ganhou ? 'tag-ganhou' : 'tag-perdeu'}">${ganhou ? '🎊 GANHOU!' : '😔 Perdeu'}</span>
      </div>
    `;
  }).join('');

  title.innerHTML = `🎰 Sorteado: ${sorteado.emoji} <strong>${sorteado.nome}</strong> (Grupo ${String(sorteado.grupo).padStart(2,'0')})`;
  list.innerHTML = html;
  resDiv.style.display = 'block';

  if (algumGanhou) {
    setTimeout(() => lancarConfetti(), 300);
    atualizarPlacar();
  }
}

// ========== PLACAR ==========
function registrarVitoria(nome) {
  placar[nome] = (placar[nome] || 0) + 1;
  localStorage.setItem('jb_placar', JSON.stringify(placar));
}

function atualizarPlacar() {
  const lista = document.getElementById('placarLista');
  const sorted = Object.entries(placar).sort((a, b) => b[1] - a[1]);
  if (sorted.length === 0) {
    lista.innerHTML = '<div class="empty-msg">Nenhuma vitória ainda. Vamos jogar!</div>';
    return;
  }
  const medals = ['🥇', '🥈', '🥉'];
  lista.innerHTML = sorted.map(([nome, wins], i) => `
    <div class="placar-item">
      <span>${medals[i] || '🏅'} ${nome}</span>
      <span class="placar-wins">${wins} vitória${wins !== 1 ? 's' : ''}</span>
    </div>
  `).join('');
}

function limparPlacar() {
  if (confirm('Zerar o placar de vitórias? Essa ação não pode ser desfeita!')) {
    placar = {};
    localStorage.removeItem('jb_placar');
    atualizarPlacar();
  }
}

// ========== CONFETTI ==========
function lancarConfetti() {
  const container = document.getElementById('confettiContainer');
  const colors = ['#f5c518','#f07e16','#d93025','#25a050','#1565c0','#6a1b9a','#ffffff'];
  for (let i = 0; i < 80; i++) {
    const piece = document.createElement('div');
    piece.className = 'confetti-piece';
    piece.style.cssText = `
      left: ${Math.random() * 100}%;
      top: -10px;
      background: ${colors[Math.floor(Math.random() * colors.length)]};
      width: ${Math.random() * 10 + 6}px;
      height: ${Math.random() * 10 + 6}px;
      border-radius: ${Math.random() > 0.5 ? '50%' : '2px'};
      animation-duration: ${Math.random() * 2 + 1.5}s;
      animation-delay: ${Math.random() * 0.8}s;
    `;
    container.appendChild(piece);
    setTimeout(() => piece.remove(), 4000);
  }
}
</script>
</body>
</html>

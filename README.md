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

/* ===== HEADER ===== */
header {
  text-align: center;
  padding: 24px 20px 12px;
  position: relative;
}
.header-decoration {
  position: absolute; top: 0; left: 0; right: 0; height: 6px;
  background: repeating-linear-gradient(90deg,
    var(--amarelo) 0px, var(--amarelo) 20px,
    var(--laranja) 20px, var(--laranja) 40px,
    var(--vermelho) 40px, var(--vermelho) 60px,
    var(--verde-claro) 60px, var(--verde-claro) 80px);
}
header h1 {
  font-family: 'Fredoka One', cursive;
  font-size: clamp(2rem, 6vw, 3.6rem);
  color: var(--amarelo);
  text-shadow: 3px 3px 0 var(--verde-escuro), 5px 5px 0 rgba(0,0,0,0.3);
  letter-spacing: 2px;
  animation: titleBounce 0.8s ease-out;
}
header p.subtitle { font-size: 1rem; color: rgba(255,255,255,0.85); margin-top: 4px; font-weight: 600; }

@keyframes titleBounce {
  0% { transform: scale(0.5) rotate(-5deg); opacity: 0; }
  70% { transform: scale(1.08) rotate(1deg); }
  100% { transform: scale(1) rotate(0deg); opacity: 1; }
}

/* ===== LAYOUT PRINCIPAL ===== */
main {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 14px 60px;
  display: grid;
  grid-template-columns: 1fr 300px;
  gap: 20px;
  align-items: start;
}
@media (max-width: 780px) {
  main { grid-template-columns: 1fr; }
  .sidebar { order: -1; }
}

/* ===== SIDEBAR - JOGADORES ===== */
.sidebar { display: flex; flex-direction: column; gap: 16px; }

.jogadores-box {
  background: linear-gradient(135deg, rgba(255,255,255,0.1), rgba(255,255,255,0.05));
  border: 2px solid rgba(245,197,24,0.4);
  border-radius: 20px;
  padding: 18px;
  backdrop-filter: blur(6px);
}
.jogadores-box h2 {
  font-family: 'Fredoka One', cursive;
  font-size: 1.2rem;
  color: var(--amarelo);
  margin-bottom: 12px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.jogador-badge {
  display: flex;
  align-items: center;
  gap: 10px;
  background: rgba(255,255,255,0.08);
  border-radius: 50px;
  padding: 8px 14px;
  margin-bottom: 8px;
  font-weight: 700;
  font-size: 0.95rem;
  animation: popIn 0.3s ease;
  border: 2px solid rgba(255,255,255,0.1);
}
.jogador-badge.responsavel {
  background: linear-gradient(90deg, rgba(245,197,24,0.3), rgba(245,197,24,0.1));
  border-color: rgba(245,197,24,0.5);
}
.jogador-badge .animal-aposta {
  margin-left: auto;
  font-size: 1.3rem;
}
.badge-coroa { color: var(--amarelo); font-size: 1.1rem; }

.empty-jogadores {
  text-align: center;
  color: rgba(255,255,255,0.4);
  font-size: 0.9rem;
  padding: 10px;
}

/* ===== TABS ===== */
.tabs-wrap { grid-column: 1 / -1; }
.tabs {
  display: flex;
  gap: 8px;
  justify-content: center;
  margin-bottom: 20px;
  flex-wrap: wrap;
}
.tab-btn {
  font-family: 'Baloo 2', cursive;
  font-size: 1rem;
  font-weight: 800;
  padding: 10px 22px;
  border: 3px solid rgba(255,255,255,0.3);
  border-radius: 50px;
  background: rgba(255,255,255,0.1);
  color: white;
  cursor: pointer;
  transition: all 0.2s;
}
.tab-btn:hover { background: rgba(255,255,255,0.2); transform: translateY(-2px); }
.tab-btn.active {
  background: var(--amarelo);
  color: var(--verde-escuro);
  border-color: var(--amarelo);
  box-shadow: 0 4px 20px rgba(245,197,24,0.4);
  transform: translateY(-2px);
}

/* ===== PANELS ===== */
.content-area { min-width: 0; }
.panel { display: none; animation: fadeIn 0.35s ease; }
.panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: translateY(0); } }
@keyframes popIn { from { transform: scale(0); opacity: 0; } to { transform: scale(1); opacity: 1; } }

/* ===== APOSTAR PANEL ===== */
.apostar-section { display: flex; flex-direction: column; gap: 18px; }
.section-box {
  background: linear-gradient(135deg, rgba(255,255,255,0.1), rgba(255,255,255,0.04));
  border: 2px solid rgba(255,255,255,0.15);
  border-radius: 20px;
  padding: 20px;
  backdrop-filter: blur(4px);
}
.section-box h3 {
  font-family: 'Fredoka One', cursive;
  font-size: 1.2rem;
  color: var(--amarelo);
  margin-bottom: 14px;
}

/* Input jogador */
.input-row { display: flex; gap: 10px; align-items: center; flex-wrap: wrap; }
.input-row label { font-weight: 800; font-size: 0.95rem; white-space: nowrap; }
.jogo-input {
  font-family: 'Baloo 2', cursive;
  font-size: 1rem;
  font-weight: 700;
  padding: 10px 18px;
  background: rgba(255,255,255,0.12);
  border: 2px solid rgba(255,255,255,0.25);
  border-radius: 50px;
  color: white;
  outline: none;
  flex: 1;
  min-width: 140px;
  transition: border-color 0.2s;
}
.jogo-input::placeholder { color: rgba(255,255,255,0.4); }
.jogo-input:focus { border-color: var(--amarelo); }

.checkbox-row {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-top: 10px;
  background: rgba(245,197,24,0.1);
  border: 2px solid rgba(245,197,24,0.3);
  border-radius: 14px;
  padding: 10px 16px;
  cursor: pointer;
}
.checkbox-row input { width: 18px; height: 18px; cursor: pointer; accent-color: var(--amarelo); }
.checkbox-row label { font-weight: 800; color: var(--amarelo); cursor: pointer; font-size: 0.95rem; }

/* Mini grid animais */
.mini-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(72px, 1fr));
  gap: 8px;
}
.mini-card {
  background: rgba(255,255,255,0.08);
  border: 2px solid rgba(255,255,255,0.15);
  border-radius: 14px;
  padding: 8px 4px;
  text-align: center;
  cursor: pointer;
  transition: all 0.15s;
  font-size: 0.7rem;
  font-weight: 700;
  line-height: 1.3;
}
.mini-card:hover { background: rgba(255,255,255,0.2); transform: scale(1.06); }
.mini-card.selecionado {
  background: linear-gradient(135deg, var(--amarelo), var(--laranja));
  border-color: var(--amarelo);
  color: var(--verde-escuro);
  font-weight: 900;
  transform: scale(1.08);
  box-shadow: 0 4px 14px rgba(245,197,24,0.4);
}
.mini-card span { font-size: 1.5rem; display: block; }

/* Botões */
.btn {
  font-family: 'Fredoka One', cursive;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.2s;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}
.btn:hover { transform: translateY(-3px); }
.btn:active { transform: translateY(0) scale(0.97); }
.btn:disabled { opacity: 0.5; cursor: not-allowed; transform: none !important; }

.btn-verde {
  font-size: 1.1rem; padding: 12px 28px;
  background: linear-gradient(135deg, var(--verde-claro), var(--verde));
  color: white;
  box-shadow: 0 4px 16px rgba(0,0,0,0.3);
  width: 100%; margin-top: 10px;
}
.btn-amarelo {
  font-size: 1.5rem; padding: 16px 40px;
  background: linear-gradient(135deg, var(--amarelo), var(--laranja));
  color: var(--verde-escuro);
  box-shadow: 0 6px 24px rgba(240,126,22,0.5);
  width: 100%;
}
.btn-vermelho {
  font-size: 1.4rem; padding: 16px 40px;
  background: linear-gradient(135deg, var(--vermelho), #c0392b);
  color: white;
  box-shadow: 0 6px 24px rgba(217,48,37,0.5);
  width: 100%;
}
.btn-cinza {
  font-size: 0.9rem; padding: 8px 20px;
  background: rgba(255,255,255,0.1);
  color: rgba(255,255,255,0.7);
  border: 2px solid rgba(255,255,255,0.2);
}

/* Lista apostas */
.aposta-item {
  display: flex;
  align-items: center;
  gap: 10px;
  background: rgba(255,255,255,0.07);
  border-radius: 14px;
  padding: 10px 14px;
  margin-bottom: 8px;
  font-weight: 700;
  font-size: 0.9rem;
  animation: popIn 0.3s ease;
}
.aposta-item .btn-remover {
  background: var(--vermelho); border: none; border-radius: 50%;
  width: 26px; height: 26px; color: white; font-size: 0.9rem;
  cursor: pointer; display: flex; align-items: center; justify-content: center;
  margin-left: auto; transition: transform 0.15s; flex-shrink: 0;
}
.aposta-item .btn-remover:hover { transform: scale(1.2); }

/* ===== RESUMO PRÉ-SORTEIO ===== */
.resumo-box {
  background: linear-gradient(135deg, rgba(245,197,24,0.15), rgba(245,197,24,0.05));
  border: 3px solid rgba(245,197,24,0.5);
  border-radius: 20px;
  padding: 20px;
  margin-bottom: 16px;
}
.resumo-box h3 {
  font-family: 'Fredoka One', cursive;
  font-size: 1.3rem;
  color: var(--amarelo);
  margin-bottom: 14px;
  text-align: center;
}
.resumo-animal-item {
  display: flex;
  align-items: center;
  gap: 12px;
  background: rgba(255,255,255,0.08);
  border-radius: 14px;
  padding: 10px 16px;
  margin-bottom: 8px;
  border: 2px solid rgba(255,255,255,0.1);
}
.resumo-apostadores {
  font-size: 0.85rem;
  color: rgba(255,255,255,0.7);
  font-weight: 600;
}
.resumo-animal-nome {
  font-weight: 900;
  font-size: 1rem;
}
.resumo-emoji { font-size: 2rem; }

/* ===== SORTEIO PANEL ===== */
.sorteio-container { display: flex; flex-direction: column; align-items: center; gap: 24px; }

.drum {
  width: 200px; height: 200px;
  border-radius: 50%;
  background: radial-gradient(circle at 35% 35%, #5d4e37, #2c1f0e);
  border: 8px solid var(--dourado);
  box-shadow: 0 0 0 4px rgba(0,0,0,0.3), inset 0 8px 20px rgba(255,255,255,0.1), 0 20px 50px rgba(0,0,0,0.4);
  display: flex; align-items: center; justify-content: center;
  cursor: pointer; transition: transform 0.15s; position: relative; overflow: hidden;
}
.drum::before {
  content: ''; position: absolute; top: 8%; left: 8%;
  width: 30%; height: 30%;
  background: radial-gradient(circle, rgba(255,255,255,0.25), transparent);
  border-radius: 50%;
}
.drum-inner {
  font-size: 4.5rem; transition: transform 0.3s;
  filter: drop-shadow(0 4px 8px rgba(0,0,0,0.5)); user-select: none;
}
.drum:hover { transform: scale(1.04); }
.drum:active { transform: scale(0.97); }
.drum.spinning .drum-inner { animation: drumSpin 0.1s linear infinite; }
@keyframes drumSpin {
  0% { transform: rotate(-15deg) scale(0.8); opacity: 0.5; }
  50% { transform: rotate(15deg) scale(1.1); }
  100% { transform: rotate(-15deg) scale(0.8); opacity: 0.5; }
}
.drum-label { font-family: 'Fredoka One', cursive; font-size: 0.95rem; color: var(--dourado); text-align: center; }

/* Resultado */
.resultado-box {
  background: linear-gradient(135deg, rgba(255,255,255,0.12), rgba(255,255,255,0.05));
  border: 3px solid var(--amarelo);
  border-radius: 24px;
  padding: 24px 36px;
  text-align: center;
  width: 100%;
  max-width: 480px;
  backdrop-filter: blur(10px);
  transition: all 0.4s;
}
.resultado-box.hidden { opacity: 0.3; filter: blur(2px); }
.resultado-box.revealed { animation: revealPop 0.5s cubic-bezier(0.34,1.56,0.64,1); }
@keyframes revealPop {
  0% { transform: scale(0.7); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}
.resultado-emoji { font-size: 5rem; display: block; margin-bottom: 8px; }
.resultado-nome { font-family: 'Fredoka One', cursive; font-size: 2.2rem; color: var(--amarelo); text-shadow: 2px 2px 0 var(--verde-escuro); }
.resultado-grupo { font-size: 1rem; color: rgba(255,255,255,0.7); margin-top: 4px; }
.resultado-numeros { margin-top: 12px; display: flex; gap: 8px; justify-content: center; flex-wrap: wrap; }
.num-badge {
  background: var(--verde-escuro); border: 2px solid var(--dourado);
  border-radius: 12px; padding: 3px 12px;
  font-weight: 800; font-size: 1rem; color: var(--amarelo);
}

/* Resultado apostas */
.resultado-apostas-lista { width: 100%; max-width: 480px; }
.resultado-apostas-lista h3 {
  font-family: 'Fredoka One', cursive; font-size: 1.3rem;
  color: var(--amarelo); text-align: center; margin-bottom: 12px;
}
.aposta-resultado-item {
  display: flex; align-items: center; gap: 10px;
  padding: 10px 16px; border-radius: 14px; margin-bottom: 8px;
  font-weight: 800; font-size: 0.95rem; animation: popIn 0.4s ease;
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
.tag-resultado {
  margin-left: auto; border-radius: 50px; padding: 3px 12px; font-size: 0.82rem; white-space: nowrap;
}
.tag-ganhou { background: var(--verde-claro); color: white; }
.tag-perdeu { background: rgba(255,255,255,0.15); color: rgba(255,255,255,0.6); }

/* ===== TABELA ===== */
.tabela-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(140px, 1fr)); gap: 12px; }
.animal-card {
  background: linear-gradient(135deg, rgba(255,255,255,0.12), rgba(255,255,255,0.05));
  border: 2px solid rgba(255,255,255,0.18);
  border-radius: 18px; padding: 14px 10px; text-align: center;
  cursor: pointer; transition: all 0.2s; backdrop-filter: blur(4px);
}
.animal-card:hover { transform: translateY(-5px) scale(1.03); border-color: var(--amarelo); box-shadow: 0 10px 28px rgba(0,0,0,0.3); }
.animal-card.destaque {
  border-color: var(--amarelo);
  background: linear-gradient(135deg, rgba(245,197,24,0.25), rgba(245,197,24,0.08));
  animation: cardGlow 1s ease-in-out infinite alternate;
}
@keyframes cardGlow {
  from { box-shadow: 0 0 0 3px rgba(245,197,24,0.4); }
  to { box-shadow: 0 0 0 6px rgba(245,197,24,0.7); }
}
.card-emoji { font-size: 2.8rem; margin-bottom: 5px; display: block; }
.card-grupo { font-family: 'Fredoka One', cursive; font-size: 0.78rem; color: var(--amarelo); background: var(--verde-escuro); border-radius: 50px; padding: 2px 9px; display: inline-block; margin-bottom: 3px; }
.card-nome { font-weight: 800; font-size: 0.92rem; color: white; display: block; margin-bottom: 3px; }
.card-nums { font-size: 0.72rem; color: rgba(255,255,255,0.6); font-weight: 600; }

/* ===== PLACAR ===== */
.placar-box { background: rgba(255,255,255,0.08); border-radius: 20px; padding: 20px; border: 2px solid rgba(255,255,255,0.15); }
.placar-titulo { font-family: 'Fredoka One', cursive; font-size: 1.5rem; color: var(--amarelo); text-align: center; margin-bottom: 16px; }
.placar-item {
  display: flex; justify-content: space-between; align-items: center;
  background: rgba(255,255,255,0.07); border-radius: 14px;
  padding: 10px 18px; margin-bottom: 8px; font-weight: 700; font-size: 1rem;
}
.placar-item:first-child { background: linear-gradient(90deg, rgba(245,197,24,0.3), rgba(245,197,24,0.05)); border: 2px solid rgba(245,197,24,0.4); }
.placar-wins { color: var(--amarelo); font-family: 'Fredoka One', cursive; font-size: 1.2rem; }

/* ===== MODAL ===== */
.modal-overlay {
  position: fixed; inset: 0; background: rgba(0,0,0,0.7);
  backdrop-filter: blur(6px); z-index: 1000;
  display: none; align-items: center; justify-content: center;
}
.modal-overlay.open { display: flex; }
.modal {
  background: linear-gradient(145deg, #1a4a2a, #0d3320);
  border: 3px solid var(--amarelo); border-radius: 28px;
  padding: 32px; max-width: 380px; width: 92%;
  text-align: center; animation: revealPop 0.4s ease;
  box-shadow: 0 24px 64px rgba(0,0,0,0.6);
}
.modal-emoji { font-size: 4.5rem; margin-bottom: 10px; }
.modal h2 { font-family: 'Fredoka One', cursive; font-size: 1.8rem; color: var(--amarelo); margin-bottom: 6px; }
.modal p { color: rgba(255,255,255,0.8); margin-bottom: 4px; }
.modal-nums { display: flex; gap: 8px; justify-content: center; flex-wrap: wrap; margin: 12px 0; }

/* ===== NOVA RODADA ===== */
.nova-rodada-box { text-align: center; padding: 20px; }
.nova-rodada-box p { color: rgba(255,255,255,0.7); margin-bottom: 16px; font-size: 1rem; }

/* ===== CONFETTI ===== */
.confetti-container { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 9999; overflow: hidden; }
.confetti-piece { position: absolute; border-radius: 2px; animation: confettiFall linear forwards; }
@keyframes confettiFall {
  0% { transform: translateY(-20px) rotate(0deg); opacity: 1; }
  100% { transform: translateY(110vh) rotate(720deg); opacity: 0; }
}

.empty-msg { text-align: center; color: rgba(255,255,255,0.4); font-size: 0.9rem; padding: 14px; }

/* Aviso responsável */
.aviso-responsavel {
  background: linear-gradient(90deg, rgba(245,197,24,0.2), rgba(245,197,24,0.05));
  border: 2px solid rgba(245,197,24,0.5);
  border-radius: 14px; padding: 12px 16px;
  font-size: 0.9rem; color: var(--amarelo); font-weight: 700;
  text-align: center; margin-bottom: 8px;
}

/* Step indicator */
.step-indicator {
  display: flex; gap: 8px; justify-content: center;
  margin-bottom: 20px; flex-wrap: wrap;
}
.step {
  display: flex; align-items: center; gap: 6px;
  font-size: 0.85rem; font-weight: 700;
  color: rgba(255,255,255,0.4);
}
.step.done { color: var(--verde-claro); }
.step.active { color: var(--amarelo); }
.step-num {
  width: 26px; height: 26px; border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 0.8rem; font-weight: 900;
  background: rgba(255,255,255,0.1);
}
.step.done .step-num { background: var(--verde-claro); color: white; }
.step.active .step-num { background: var(--amarelo); color: var(--verde-escuro); }
.step-arrow { color: rgba(255,255,255,0.25); font-size: 0.8rem; }
</style>
</head>
<body>
<div class="confetti-container" id="confettiContainer"></div>

<header>
  <div class="header-decoration"></div>
  <h1>🎲 JOGO DO BICHO 🎲</h1>
  <p class="subtitle">🌟 A diversão da família — onde estiver! 🌟</p>
</header>

<div style="max-width:1100px;margin:0 auto;padding:0 14px;">
  <div class="tabs">
    <button class="tab-btn active" onclick="showTab('apostar', this)">🃏 Apostar</button>
    <button class="tab-btn" onclick="showTab('sorteio', this)">🎰 Sortear</button>
    <button class="tab-btn" onclick="showTab('tabela', this)">📋 Tabela</button>
    <button class="tab-btn" onclick="showTab('placar', this)">🏆 Placar</button>
  </div>
</div>

<main>
  <!-- ===== SIDEBAR ===== -->
  <div class="sidebar" style="order:2">

    <div class="jogadores-box">
      <h2>👥 Jogadores da Rodada</h2>
      <div id="jogadoresLista">
        <div class="empty-jogadores">Nenhum jogador ainda.<br>Adicione apostas!</div>
      </div>
    </div>

    <div class="jogadores-box" id="historicoBox" style="display:none">
      <h2>🕐 Últimos Sorteios</h2>
      <div id="historicoLista"></div>
    </div>

  </div>

  <!-- ===== CONTEÚDO PRINCIPAL ===== -->
  <div class="content-area" style="order:1">

    <!-- ===== APOSTAR ===== -->
    <div class="panel active" id="panel-apostar">
      <div class="apostar-section">

        <div class="step-indicator">
          <div class="step active" id="step1"><div class="step-num">1</div> Adicionar apostas</div>
          <div class="step-arrow">▶</div>
          <div class="step" id="step2"><div class="step-num">2</div> Revelar resultado</div>
          <div class="step-arrow">▶</div>
          <div class="step" id="step3"><div class="step-num">3</div> Nova rodada</div>
        </div>

        <!-- Formulário aposta -->
        <div class="section-box" id="formAposta">
          <h3>➕ Nova Aposta</h3>
          <div class="input-row">
            <label>👤 Nome:</label>
            <input type="text" class="jogo-input" id="nomeJogador" placeholder="Nome do jogador..." maxlength="20">
          </div>
          <div class="checkbox-row" onclick="toggleResponsavel()">
            <input type="checkbox" id="chkResponsavel">
            <label for="chkResponsavel">👑 Este jogador é o RESPONSÁVEL pelo sorteio</label>
          </div>
          <h3 style="margin-top:14px">🐾 Escolha o animal:</h3>
          <div class="mini-grid" id="miniGrid"></div>
          <button class="btn btn-verde" onclick="adicionarAposta()">✅ Adicionar aposta</button>
        </div>

        <!-- Lista apostas -->
        <div class="section-box">
          <h3>📝 Apostas desta rodada:</h3>
          <div id="listaApostas"><div class="empty-msg">Nenhuma aposta ainda</div></div>
          <button class="btn btn-vermelho" id="btnIrSortear" style="margin-top:12px" onclick="irParaSorteio()" disabled>
            🎰 PRONTO! IR PARA O SORTEIO
          </button>
        </div>

      </div>
    </div>

    <!-- ===== SORTEIO ===== -->
    <div class="panel" id="panel-sorteio">
      <div class="sorteio-container">

        <!-- Resumo apostas -->
        <div class="resumo-box" id="resumoApostas" style="width:100%;max-width:500px">
          <h3>🐾 Animais apostados nesta rodada:</h3>
          <div id="resumoLista"></div>
        </div>

        <div id="avisoResponsavel" class="aviso-responsavel" style="width:100%;max-width:500px;display:none"></div>

        <div>
          <div class="drum" id="drumEl" onclick="iniciarSorteio()">
            <div class="drum-inner" id="drumEmoji">🎰</div>
          </div>
          <div class="drum-label" style="margin-top:10px">CLIQUE NA URNA PARA SORTEAR!</div>
        </div>

        <button class="btn btn-amarelo" id="btnSortear" onclick="iniciarSorteio()" style="max-width:360px">
          🎲 GIRAR A URNA!
        </button>

        <div class="resultado-box hidden" id="resultadoBox" style="display:none">
          <span class="resultado-emoji" id="resEmoji">🎰</span>
          <div class="resultado-nome" id="resNome">—</div>
          <div class="resultado-grupo" id="resGrupo">—</div>
          <div class="resultado-numeros" id="resNumeros"></div>
        </div>

        <div class="resultado-apostas-lista" id="resultadoApostasList" style="display:none">
          <h3 id="resApostasTitle">🎊 Resultado das apostas!</h3>
          <div id="resApostasItens"></div>
        </div>

        <div class="nova-rodada-box" id="novaRodadaBox" style="display:none">
          <p>Quer jogar de novo? Clique abaixo para iniciar uma nova rodada!</p>
          <button class="btn btn-verde" onclick="novaRodada()" style="max-width:320px;display:flex;margin:0 auto">
            🔄 NOVA RODADA
          </button>
        </div>

      </div>
    </div>

    <!-- ===== TABELA ===== -->
    <div class="panel" id="panel-tabela">
      <div class="tabela-grid" id="tabelaGrid"></div>
    </div>

    <!-- ===== PLACAR ===== -->
    <div class="panel" id="panel-placar">
      <div class="placar-box">
        <div class="placar-titulo">🏆 Placar de Vitórias</div>
        <div id="placarLista"><div class="empty-msg">Nenhuma vitória ainda!</div></div>
        <button class="btn btn-cinza" onclick="limparPlacar()" style="margin-top:14px;margin-left:auto;display:block">
          🗑️ Zerar placar
        </button>
      </div>
    </div>

  </div>
</main>

<!-- Modal animal -->
<div class="modal-overlay" id="modalOverlay" onclick="fecharModal(event)">
  <div class="modal">
    <div class="modal-emoji" id="modalEmoji"></div>
    <h2 id="modalNome"></h2>
    <p id="modalGrupo"></p>
    <div class="modal-nums" id="modalNums"></div>
    <button class="btn btn-amarelo" onclick="fecharModal(null,true)" style="max-width:200px;margin:12px auto 0;font-size:1rem;padding:10px 28px">Fechar</button>
  </div>
</div>

<script>
// ========== DADOS ==========
const ANIMAIS = [
  { grupo:1,  nome:'Avestruz',  emoji:'🦚', numeros:[1,2,3,4] },
  { grupo:2,  nome:'Águia',     emoji:'🦅', numeros:[5,6,7,8] },
  { grupo:3,  nome:'Burro',     emoji:'🫏', numeros:[9,10,11,12] },
  { grupo:4,  nome:'Borboleta', emoji:'🦋', numeros:[13,14,15,16] },
  { grupo:5,  nome:'Cachorro',  emoji:'🐶', numeros:[17,18,19,20] },
  { grupo:6,  nome:'Cabra',     emoji:'🐐', numeros:[21,22,23,24] },
  { grupo:7,  nome:'Carneiro',  emoji:'🐑', numeros:[25,26,27,28] },
  { grupo:8,  nome:'Camelo',    emoji:'🐪', numeros:[29,30,31,32] },
  { grupo:9,  nome:'Cobra',     emoji:'🐍', numeros:[33,34,35,36] },
  { grupo:10, nome:'Coelho',    emoji:'🐰', numeros:[37,38,39,40] },
  { grupo:11, nome:'Cavalo',    emoji:'🐴', numeros:[41,42,43,44] },
  { grupo:12, nome:'Elefante',  emoji:'🐘', numeros:[45,46,47,48] },
  { grupo:13, nome:'Galo',      emoji:'🐓', numeros:[49,50,51,52] },
  { grupo:14, nome:'Gato',      emoji:'🐱', numeros:[53,54,55,56] },
  { grupo:15, nome:'Jacaré',    emoji:'🐊', numeros:[57,58,59,60] },
  { grupo:16, nome:'Leão',      emoji:'🦁', numeros:[61,62,63,64] },
  { grupo:17, nome:'Macaco',    emoji:'🐵', numeros:[65,66,67,68] },
  { grupo:18, nome:'Porco',     emoji:'🐷', numeros:[69,70,71,72] },
  { grupo:19, nome:'Pavão',     emoji:'🦜', numeros:[73,74,75,76] },
  { grupo:20, nome:'Peru',      emoji:'🦃', numeros:[77,78,79,80] },
  { grupo:21, nome:'Touro',     emoji:'🐂', numeros:[81,82,83,84] },
  { grupo:22, nome:'Tigre',     emoji:'🐯', numeros:[85,86,87,88] },
  { grupo:23, nome:'Urso',      emoji:'🐻', numeros:[89,90,91,92] },
  { grupo:24, nome:'Veado',     emoji:'🦌', numeros:[93,94,95,96] },
  { grupo:25, nome:'Vaca',      emoji:'🐄', numeros:[97,98,99,0] }
];

// ========== STATE ==========
let apostas = [];
let animalSelecionado = null;
let sorteando = false;
let jasorteou = false;
let placar = JSON.parse(localStorage.getItem('jb_placar') || '{}');
let historico = [];

// ========== INIT ==========
document.addEventListener('DOMContentLoaded', () => {
  renderizarMiniGrid();
  renderizarTabela();
  atualizarPlacar();
});

// ========== TABS ==========
function showTab(id, btn) {
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  btn.classList.add('active');
}

// ========== MINI GRID ==========
function renderizarMiniGrid() {
  document.getElementById('miniGrid').innerHTML = ANIMAIS.map(a =>
    `<div class="mini-card" data-grupo="${a.grupo}" onclick="selecionarAnimal(${a.grupo})">
      <span>${a.emoji}</span>${a.nome}
    </div>`
  ).join('');
}

function selecionarAnimal(grupo) {
  animalSelecionado = ANIMAIS.find(a => a.grupo === grupo);
  document.querySelectorAll('.mini-card').forEach(c => c.classList.remove('selecionado'));
  document.querySelector(`.mini-card[data-grupo="${grupo}"]`).classList.add('selecionado');
}

function toggleResponsavel() {
  const chk = document.getElementById('chkResponsavel');
  chk.checked = !chk.checked;
}

// ========== APOSTAS ==========
function adicionarAposta() {
  const nome = document.getElementById('nomeJogador').value.trim();
  const isResponsavel = document.getElementById('chkResponsavel').checked;

  if (!nome) { alert('Digite o nome do jogador! 👤'); return; }
  if (!animalSelecionado) { alert('Escolha um animal! 🐾'); return; }

  // Verifica se já tem responsável
  if (isResponsavel && apostas.some(a => a.responsavel)) {
    alert('Já existe um responsável pelo sorteio! (' + apostas.find(a=>a.responsavel).nome + ')');
    document.getElementById('chkResponsavel').checked = false;
    return;
  }

  // Verifica nome duplicado
  if (apostas.some(a => a.nome.toLowerCase() === nome.toLowerCase())) {
    alert('Este jogador já fez sua aposta! Cada pessoa aposta uma vez por rodada. 😊');
    return;
  }

  apostas.push({ nome, animal: animalSelecionado, responsavel: isResponsavel });

  // Limpa form
  document.getElementById('nomeJogador').value = '';
  document.getElementById('chkResponsavel').checked = false;
  animalSelecionado = null;
  document.querySelectorAll('.mini-card').forEach(c => c.classList.remove('selecionado'));

  renderizarApostas();
  renderizarJogadoresSidebar();
  document.getElementById('btnIrSortear').disabled = apostas.length === 0;
}

function removerAposta(idx) {
  apostas.splice(idx, 1);
  renderizarApostas();
  renderizarJogadoresSidebar();
  document.getElementById('btnIrSortear').disabled = apostas.length === 0;
}

function renderizarApostas() {
  const el = document.getElementById('listaApostas');
  if (apostas.length === 0) {
    el.innerHTML = '<div class="empty-msg">Nenhuma aposta ainda</div>';
    return;
  }
  el.innerHTML = apostas.map((ap, i) => `
    <div class="aposta-item">
      <span style="font-size:1.5rem">${ap.animal.emoji}</span>
      <span>
        ${ap.responsavel ? '👑 ' : ''}<strong>${ap.nome}</strong>
        → <strong>${ap.animal.nome}</strong>
        ${ap.responsavel ? '<br><small style="color:var(--amarelo);font-size:0.75rem">Responsável pelo sorteio</small>' : ''}
      </span>
      <button class="btn-remover" onclick="removerAposta(${i})">✕</button>
    </div>
  `).join('');
}

function renderizarJogadoresSidebar() {
  const el = document.getElementById('jogadoresLista');
  if (apostas.length === 0) {
    el.innerHTML = '<div class="empty-jogadores">Nenhum jogador ainda.<br>Adicione apostas!</div>';
    return;
  }
  el.innerHTML = apostas.map(ap => `
    <div class="jogador-badge ${ap.responsavel ? 'responsavel' : ''}">
      ${ap.responsavel ? '<span class="badge-coroa">👑</span>' : '👤'}
      <span>${ap.nome}</span>
      <span class="animal-aposta">${ap.animal.emoji}</span>
    </div>
  `).join('');
}

// ========== IR PARA SORTEIO ==========
function irParaSorteio() {
  // Muda para aba sorteio
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.getElementById('panel-sorteio').classList.add('active');
  document.querySelectorAll('.tab-btn')[1].classList.add('active');

  // Monta resumo
  renderizarResumo();

  // Aviso responsável
  const resp = apostas.find(a => a.responsavel);
  const avisoEl = document.getElementById('avisoResponsavel');
  if (resp) {
    avisoEl.style.display = 'block';
    avisoEl.innerHTML = `👑 <strong>${resp.nome}</strong> é o responsável pelo sorteio!`;
  } else {
    avisoEl.style.display = 'none';
  }

  // Reset resultado
  document.getElementById('resultadoBox').style.display = 'none';
  document.getElementById('resultadoApostasList').style.display = 'none';
  document.getElementById('novaRodadaBox').style.display = 'none';
  document.getElementById('btnSortear').disabled = false;
  jasorteou = false;
}

function renderizarResumo() {
  // Agrupa por animal
  const grupos = {};
  apostas.forEach(ap => {
    const key = ap.animal.grupo;
    if (!grupos[key]) grupos[key] = { animal: ap.animal, apostadores: [] };
    grupos[key].apostadores.push(ap.nome);
  });

  const el = document.getElementById('resumoLista');
  el.innerHTML = Object.values(grupos).map(g => `
    <div class="resumo-animal-item">
      <span class="resumo-emoji">${g.animal.emoji}</span>
      <div>
        <div class="resumo-animal-nome">${g.animal.nome} <small style="color:var(--amarelo);font-size:0.8rem">(Grupo ${String(g.animal.grupo).padStart(2,'0')})</small></div>
        <div class="resumo-apostadores">Apostou: ${g.apostadores.join(', ')}</div>
      </div>
    </div>
  `).join('');
}

// ========== SORTEIO ==========
function iniciarSorteio() {
  if (sorteando || jasorteou) return;
  if (apostas.length === 0) { alert('Adicione apostas primeiro!'); return; }

  sorteando = true;
  const drum = document.getElementById('drumEl');
  const drumEmoji = document.getElementById('drumEmoji');
  const btnSortear = document.getElementById('btnSortear');

  btnSortear.disabled = true;
  drum.classList.add('spinning');

  let tick = 0;
  const interval = setInterval(() => {
    drumEmoji.textContent = ANIMAIS[Math.floor(Math.random() * ANIMAIS.length)].emoji;
    tick++;
  }, 80);

  setTimeout(() => {
    clearInterval(interval);
    drum.classList.remove('spinning');

    const sorteado = ANIMAIS[Math.floor(Math.random() * ANIMAIS.length)];
    drumEmoji.textContent = sorteado.emoji;

    // Mostra resultado
    const resBox = document.getElementById('resultadoBox');
    document.getElementById('resEmoji').textContent = sorteado.emoji;
    document.getElementById('resNome').textContent = sorteado.nome;
    document.getElementById('resGrupo').textContent = `Grupo ${String(sorteado.grupo).padStart(2,'0')}`;
    document.getElementById('resNumeros').innerHTML = sorteado.numeros.map(n =>
      `<span class="num-badge">${String(n).padStart(2,'0')}</span>`
    ).join('');
    resBox.style.display = 'block';
    resBox.classList.remove('hidden');
    resBox.classList.add('revealed');

    // Resultado apostas
    let algumGanhou = false;
    const itens = apostas.map(ap => {
      const ganhou = ap.animal.grupo === sorteado.grupo;
      if (ganhou) { algumGanhou = true; registrarVitoria(ap.nome); }
      return `
        <div class="aposta-resultado-item ${ganhou ? 'ganhou' : 'perdeu'}">
          <span style="font-size:1.6rem">${ap.animal.emoji}</span>
          <span>${ap.responsavel ? '👑 ' : ''}<strong>${ap.nome}</strong> — ${ap.animal.nome}</span>
          <span class="tag-resultado ${ganhou ? 'tag-ganhou' : 'tag-perdeu'}">${ganhou ? '🎊 GANHOU!' : '😔 Perdeu'}</span>
        </div>
      `;
    }).join('');

    document.getElementById('resApostasTitle').innerHTML = `🎰 Sorteado: ${sorteado.emoji} <strong>${sorteado.nome}</strong>`;
    document.getElementById('resApostasItens').innerHTML = itens;
    document.getElementById('resultadoApostasList').style.display = 'block';

    if (algumGanhou) { setTimeout(lancarConfetti, 400); atualizarPlacar(); }

    // Destaque tabela
    document.querySelectorAll('.animal-card').forEach(c => c.classList.remove('destaque'));
    const card = document.querySelector(`.animal-card[data-grupo="${sorteado.grupo}"]`);
    if (card) card.classList.add('destaque');

    // Histórico
    historico.unshift(sorteado);
    if (historico.length > 6) historico.pop();
    document.getElementById('historicoBox').style.display = 'block';
    document.getElementById('historicoLista').innerHTML = historico.map(a =>
      `<div class="jogador-badge">${a.emoji} <span>${a.nome}</span></div>`
    ).join('');

    document.getElementById('novaRodadaBox').style.display = 'block';
    sorteando = false;
    jasorteou = true;
  }, 2200);
}

// ========== NOVA RODADA ==========
function novaRodada() {
  apostas = [];
  animalSelecionado = null;
  jasorteou = false;

  renderizarApostas();
  renderizarJogadoresSidebar();
  document.getElementById('btnIrSortear').disabled = true;
  document.getElementById('drumEmoji').textContent = '🎰';
  document.querySelectorAll('.mini-card').forEach(c => c.classList.remove('selecionado'));

  // Atualiza steps
  document.getElementById('step1').className = 'step active';
  document.getElementById('step2').className = 'step';
  document.getElementById('step3').className = 'step';

  // Vai para aba apostar
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.getElementById('panel-apostar').classList.add('active');
  document.querySelectorAll('.tab-btn')[0].classList.add('active');
}

// ========== TABELA ==========
function renderizarTabela() {
  document.getElementById('tabelaGrid').innerHTML = ANIMAIS.map(a => `
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
  if (force || e?.target?.id === 'modalOverlay') document.getElementById('modalOverlay').classList.remove('open');
}

// ========== PLACAR ==========
function registrarVitoria(nome) {
  placar[nome] = (placar[nome] || 0) + 1;
  localStorage.setItem('jb_placar', JSON.stringify(placar));
}
function atualizarPlacar() {
  const el = document.getElementById('placarLista');
  const sorted = Object.entries(placar).sort((a,b) => b[1]-a[1]);
  if (sorted.length === 0) { el.innerHTML = '<div class="empty-msg">Nenhuma vitória ainda!</div>'; return; }
  const medals = ['🥇','🥈','🥉'];
  el.innerHTML = sorted.map(([nome, wins], i) => `
    <div class="placar-item">
      <span>${medals[i]||'🏅'} ${nome}</span>
      <span class="placar-wins">${wins} vitória${wins!==1?'s':''}</span>
    </div>
  `).join('');
}
function limparPlacar() {
  if (confirm('Zerar o placar?')) {
    placar = {};
    localStorage.removeItem('jb_placar');
    atualizarPlacar();
  }
}

// ========== CONFETTI ==========
function lancarConfetti() {
  const container = document.getElementById('confettiContainer');
  const colors = ['#f5c518','#f07e16','#d93025','#25a050','#1565c0','#6a1b9a','#ffffff'];
  for (let i = 0; i < 100; i++) {
    const p = document.createElement('div');
    p.className = 'confetti-piece';
    p.style.cssText = `
      left:${Math.random()*100}%; top:-10px;
      background:${colors[Math.floor(Math.random()*colors.length)]};
      width:${Math.random()*10+6}px; height:${Math.random()*10+6}px;
      border-radius:${Math.random()>0.5?'50%':'2px'};
      animation-duration:${Math.random()*2+1.5}s;
      animation-delay:${Math.random()*0.8}s;
    `;
    container.appendChild(p);
    setTimeout(() => p.remove(), 4000);
  }
}
</script>
</body>
</html>

<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jogo do Bicho da Familia</title>
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@400;600;800;900&family=Fredoka+One&display=swap" rel="stylesheet">
<style>
:root{--vd:#0d5c2e;--v:#1a7a3c;--vc:#25a050;--am:#f5c518;--la:#f07e16;--vm:#d93025;--do:#d4a017;}
*{box-sizing:border-box;margin:0;padding:0;}
body{font-family:'Baloo 2',cursive;background:var(--vd);background-image:radial-gradient(ellipse at 15% 15%,rgba(245,197,24,.12) 0%,transparent 55%),radial-gradient(ellipse at 85% 85%,rgba(255,255,255,.05) 0%,transparent 55%);min-height:100vh;color:#fff;overflow-x:hidden;}
header{text-align:center;padding:22px 20px 10px;position:relative;}
.hd{position:absolute;top:0;left:0;right:0;height:6px;background:repeating-linear-gradient(90deg,var(--am) 0,var(--am) 20px,var(--la) 20px,var(--la) 40px,var(--vm) 40px,var(--vm) 60px,var(--vc) 60px,var(--vc) 80px);}
h1{font-family:'Fredoka One',cursive;font-size:clamp(2rem,6vw,3.4rem);color:var(--am);text-shadow:3px 3px 0 var(--vd),5px 5px 0 rgba(0,0,0,.3);letter-spacing:2px;animation:tb .8s ease-out;}
.sub{font-size:1rem;color:rgba(255,255,255,.85);margin-top:4px;font-weight:600;}
@keyframes tb{0%{transform:scale(.5) rotate(-5deg);opacity:0}70%{transform:scale(1.08) rotate(1deg)}100%{transform:scale(1) rotate(0);opacity:1}}
@keyframes pi{from{transform:scale(0);opacity:0}to{transform:scale(1);opacity:1}}
@keyframes rp{0%{transform:scale(.7);opacity:0}100%{transform:scale(1);opacity:1}}
@keyframes fi{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}
@keyframes ds{0%{transform:rotate(-15deg) scale(.8);opacity:.5}50%{transform:rotate(15deg) scale(1.1)}100%{transform:rotate(-15deg) scale(.8);opacity:.5}}
@keyframes cg{from{box-shadow:0 0 0 3px rgba(245,197,24,.4)}to{box-shadow:0 0 0 6px rgba(245,197,24,.7)}}
@keyframes cf{0%{transform:translateY(-20px) rotate(0);opacity:1}100%{transform:translateY(110vh) rotate(720deg);opacity:0}}

/* JOGADORES TOPO */
.jp{max-width:900px;margin:14px auto 0;padding:0 14px;}
.jc{background:linear-gradient(135deg,rgba(245,197,24,.2),rgba(245,197,24,.06));border:2px solid rgba(245,197,24,.6);border-radius:20px;padding:14px 18px;}
.jt{font-family:'Fredoka One',cursive;font-size:1.1rem;color:var(--am);margin-bottom:10px;}
.jl{display:flex;flex-wrap:wrap;gap:8px;min-height:36px;align-items:center;}
.chip{display:flex;align-items:center;gap:6px;background:rgba(255,255,255,.12);border:2px solid rgba(255,255,255,.2);border-radius:50px;padding:6px 14px;font-size:.95rem;font-weight:700;animation:pi .3s ease;white-space:nowrap;}
.chip.resp{background:linear-gradient(90deg,rgba(245,197,24,.4),rgba(245,197,24,.15));border-color:var(--am);color:var(--am);font-size:1rem;}
.chip-a{font-size:1.3rem;}
.sj{color:rgba(255,255,255,.4);font-size:.9rem;font-style:italic;}

/* TABS */
.tw{max-width:900px;margin:14px auto 0;padding:0 14px;}
.tabs{display:flex;gap:8px;justify-content:center;flex-wrap:wrap;margin-bottom:16px;}
.tb2{font-family:'Baloo 2',cursive;font-size:1rem;font-weight:800;padding:10px 22px;border:3px solid rgba(255,255,255,.3);border-radius:50px;background:rgba(255,255,255,.1);color:#fff;cursor:pointer;transition:all .2s;}
.tb2:hover{background:rgba(255,255,255,.2);transform:translateY(-2px);}
.tb2.active{background:var(--am);color:var(--vd);border-color:var(--am);box-shadow:0 4px 20px rgba(245,197,24,.4);transform:translateY(-2px);}

.cw{max-width:900px;margin:0 auto;padding:0 14px 60px;}
.panel{display:none;animation:fi .3s ease;}
.panel.active{display:block;}
.sb{background:linear-gradient(135deg,rgba(255,255,255,.1),rgba(255,255,255,.04));border:2px solid rgba(255,255,255,.15);border-radius:20px;padding:20px;margin-bottom:16px;}
.sb h3{font-family:'Fredoka One',cursive;font-size:1.2rem;color:var(--am);margin-bottom:14px;}
.ir{display:flex;gap:10px;align-items:center;flex-wrap:wrap;margin-bottom:12px;}
.ir label{font-weight:800;font-size:.95rem;white-space:nowrap;}
.ji{font-family:'Baloo 2',cursive;font-size:1rem;font-weight:700;padding:10px 18px;background:rgba(255,255,255,.12);border:2px solid rgba(255,255,255,.25);border-radius:50px;color:#fff;outline:none;flex:1;min-width:160px;transition:border-color .2s;}
.ji::placeholder{color:rgba(255,255,255,.4);}
.ji:focus{border-color:var(--am);}
.cr{display:flex;align-items:center;gap:10px;background:rgba(245,197,24,.1);border:2px solid rgba(245,197,24,.3);border-radius:14px;padding:10px 16px;cursor:pointer;margin-bottom:14px;}
.cr input{width:18px;height:18px;cursor:pointer;accent-color:var(--am);}
.cr label{font-weight:800;color:var(--am);cursor:pointer;font-size:.95rem;}
.mg{display:grid;grid-template-columns:repeat(auto-fill,minmax(80px,1fr));gap:8px;margin-bottom:12px;}
.mc{background:rgba(255,255,255,.08);border:2px solid rgba(255,255,255,.15);border-radius:14px;padding:8px 4px;text-align:center;cursor:pointer;transition:all .15s;font-size:.72rem;font-weight:700;}
.mc:hover{background:rgba(255,255,255,.2);transform:scale(1.06);}
.mc.sel{background:linear-gradient(135deg,var(--am),var(--la));border-color:var(--am);color:var(--vd);font-weight:900;transform:scale(1.08);box-shadow:0 4px 14px rgba(245,197,24,.4);}
.mc span{font-size:1.6rem;display:block;margin-bottom:2px;}
.btn{font-family:'Fredoka One',cursive;border:none;border-radius:50px;cursor:pointer;transition:all .2s;display:flex;align-items:center;justify-content:center;gap:8px;width:100%;}
.btn:hover{transform:translateY(-3px);}
.btn:active{transform:scale(.97);}
.btn:disabled{opacity:.5;cursor:not-allowed;transform:none!important;}
.bv{font-size:1.1rem;padding:13px 28px;background:linear-gradient(135deg,var(--vc),var(--v));color:#fff;box-shadow:0 4px 16px rgba(0,0,0,.3);margin-top:4px;}
.ba{font-size:1.5rem;padding:16px 40px;background:linear-gradient(135deg,var(--am),var(--la));color:var(--vd);box-shadow:0 6px 24px rgba(240,126,22,.5);}
.bvm{font-size:1.3rem;padding:14px 36px;background:linear-gradient(135deg,var(--vm),#c0392b);color:#fff;box-shadow:0 6px 24px rgba(217,48,37,.5);margin-top:12px;}
.bc{font-size:.9rem;padding:8px 20px;background:rgba(255,255,255,.1);color:rgba(255,255,255,.7);border:2px solid rgba(255,255,255,.2);width:auto;}
.ai{display:flex;align-items:center;gap:10px;background:rgba(255,255,255,.07);border-radius:14px;padding:10px 14px;margin-bottom:8px;font-weight:700;font-size:.92rem;animation:pi .3s ease;}
.br2{background:var(--vm);border:none;border-radius:50%;width:28px;height:28px;color:#fff;font-size:.9rem;cursor:pointer;display:flex;align-items:center;justify-content:center;margin-left:auto;flex-shrink:0;transition:transform .15s;}
.br2:hover{transform:scale(1.2);}

/* RESUMO */
.rb{background:linear-gradient(135deg,rgba(245,197,24,.15),rgba(245,197,24,.04));border:3px solid rgba(245,197,24,.5);border-radius:20px;padding:18px;margin-bottom:18px;width:100%;}
.rb h3{font-family:'Fredoka One',cursive;font-size:1.2rem;color:var(--am);margin-bottom:12px;text-align:center;}
.ri{display:flex;align-items:center;gap:12px;background:rgba(255,255,255,.08);border-radius:14px;padding:10px 14px;margin-bottom:8px;border:2px solid rgba(255,255,255,.1);}
.re{font-size:2rem;}
.rn{font-weight:900;font-size:1rem;}
.rap{font-size:.82rem;color:rgba(255,255,255,.65);font-weight:600;margin-top:2px;}
.ar{background:linear-gradient(90deg,rgba(245,197,24,.25),rgba(245,197,24,.05));border:2px solid rgba(245,197,24,.6);border-radius:14px;padding:14px 18px;text-align:center;font-weight:800;color:var(--am);font-size:1.05rem;margin-bottom:18px;width:100%;}

/* DRUM */
.sc{display:flex;flex-direction:column;align-items:center;gap:20px;}
.drum{width:190px;height:190px;border-radius:50%;background:radial-gradient(circle at 35% 35%,#5d4e37,#2c1f0e);border:8px solid var(--do);box-shadow:0 0 0 4px rgba(0,0,0,.3),inset 0 8px 20px rgba(255,255,255,.1),0 20px 50px rgba(0,0,0,.4);display:flex;align-items:center;justify-content:center;cursor:pointer;transition:transform .15s;position:relative;overflow:hidden;}
.drum::before{content:'';position:absolute;top:8%;left:8%;width:30%;height:30%;background:radial-gradient(circle,rgba(255,255,255,.25),transparent);border-radius:50%;}
.di{font-size:4.5rem;filter:drop-shadow(0 4px 8px rgba(0,0,0,.5));user-select:none;}
.drum:hover{transform:scale(1.05);}
.drum.spin .di{animation:ds .1s linear infinite;}
.dl{font-family:'Fredoka One',cursive;font-size:.95rem;color:var(--do);text-align:center;margin-top:8px;}
.resx{background:linear-gradient(135deg,rgba(255,255,255,.12),rgba(255,255,255,.05));border:3px solid var(--am);border-radius:24px;padding:24px 32px;text-align:center;width:100%;animation:rp .5s cubic-bezier(.34,1.56,.64,1);}
.ree{font-size:5rem;display:block;margin-bottom:8px;}
.ren{font-family:'Fredoka One',cursive;font-size:2.2rem;color:var(--am);text-shadow:2px 2px 0 var(--vd);}
.reg{font-size:1rem;color:rgba(255,255,255,.7);margin-top:4px;}
.renum{margin-top:12px;display:flex;gap:8px;justify-content:center;flex-wrap:wrap;}
.nb{background:var(--vd);border:2px solid var(--do);border-radius:12px;padding:3px 12px;font-weight:800;font-size:1rem;color:var(--am);}
.rat{font-family:'Fredoka One',cursive;font-size:1.3rem;color:var(--am);text-align:center;margin-bottom:12px;}
.ari{display:flex;align-items:center;gap:10px;padding:10px 14px;border-radius:14px;margin-bottom:8px;font-weight:800;font-size:.95rem;animation:pi .4s ease;}
.ari.g{background:linear-gradient(90deg,rgba(37,160,80,.4),rgba(37,160,80,.1));border:2px solid var(--vc);}
.ari.p{background:rgba(255,255,255,.05);border:2px solid rgba(255,255,255,.1);opacity:.7;}
.tg{margin-left:auto;border-radius:50px;padding:3px 12px;font-size:.82rem;white-space:nowrap;}
.tgg{background:var(--vc);color:#fff;}
.tgp{background:rgba(255,255,255,.15);color:rgba(255,255,255,.6);}

/* TABELA */
.tg2{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:12px;}
.ac{background:linear-gradient(135deg,rgba(255,255,255,.12),rgba(255,255,255,.05));border:2px solid rgba(255,255,255,.18);border-radius:18px;padding:14px 10px;text-align:center;cursor:pointer;transition:all .2s;}
.ac:hover{transform:translateY(-5px);border-color:var(--am);box-shadow:0 10px 28px rgba(0,0,0,.3);}
.ac.dest{border-color:var(--am);background:linear-gradient(135deg,rgba(245,197,24,.25),rgba(245,197,24,.08));animation:cg 1s ease-in-out infinite alternate;}
.ace{font-size:2.8rem;margin-bottom:5px;display:block;}
.acg{font-family:'Fredoka One',cursive;font-size:.78rem;color:var(--am);background:var(--vd);border-radius:50px;padding:2px 9px;display:inline-block;margin-bottom:3px;}
.acn{font-weight:800;font-size:.92rem;color:#fff;display:block;margin-bottom:3px;}
.acnu{font-size:.72rem;color:rgba(255,255,255,.6);font-weight:600;}

/* PLACAR */
.pb{background:rgba(255,255,255,.08);border-radius:20px;padding:20px;border:2px solid rgba(255,255,255,.15);}
.pt{font-family:'Fredoka One',cursive;font-size:1.5rem;color:var(--am);text-align:center;margin-bottom:16px;}
.pi2{display:flex;justify-content:space-between;align-items:center;background:rgba(255,255,255,.07);border-radius:14px;padding:10px 18px;margin-bottom:8px;font-weight:700;}
.pi2:first-child{background:linear-gradient(90deg,rgba(245,197,24,.3),rgba(245,197,24,.05));border:2px solid rgba(245,197,24,.4);}
.pw{color:var(--am);font-family:'Fredoka One',cursive;font-size:1.2rem;}
.mo{position:fixed;inset:0;background:rgba(0,0,0,.7);backdrop-filter:blur(6px);z-index:1000;display:none;align-items:center;justify-content:center;}
.mo.open{display:flex;}
.md{background:linear-gradient(145deg,#1a4a2a,#0d3320);border:3px solid var(--am);border-radius:28px;padding:32px;max-width:360px;width:92%;text-align:center;animation:rp .4s ease;}
.me{font-size:4.5rem;margin-bottom:10px;}
.md h2{font-family:'Fredoka One',cursive;font-size:1.8rem;color:var(--am);margin-bottom:6px;}
.md p{color:rgba(255,255,255,.8);margin-bottom:4px;}
.mnu{display:flex;gap:8px;justify-content:center;flex-wrap:wrap;margin:12px 0;}
.cc{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:9999;overflow:hidden;}
.cp{position:absolute;border-radius:2px;animation:cf linear forwards;}
.em{text-align:center;color:rgba(255,255,255,.4);font-size:.9rem;padding:12px;}
.nrc{text-align:center;padding:10px 0 4px;}
.nrc p{color:rgba(255,255,255,.7);margin-bottom:14px;}
</style>
</head>
<body>
<div class="cc" id="cc"></div>
<header>
<div class="hd"></div>
<h1>&#127922; JOGO DO BICHO &#127922;</h1>
<p class="sub">&#127775; A diversao da familia - onde estiver! &#127775;</p>
</header>

<div class="jp">
<div class="jc">
<div class="jt">&#128101; Jogadores da Rodada:</div>
<div class="jl" id="jl"><span class="sj">Nenhum jogador ainda - adicione apostas na aba Apostar</span></div>
</div>
</div>

<div class="tw">
<div class="tabs">
<button class="tb2 active" onclick="showTab('ap',this)">&#127183; Apostar</button>
<button class="tb2" onclick="showTab('so',this)">&#127920; Sortear</button>
<button class="tb2" onclick="showTab('ta',this)">&#128203; Tabela</button>
<button class="tb2" onclick="showTab('pl',this)">&#127942; Placar</button>
</div>
</div>

<div class="cw">
<div class="panel active" id="panel-ap">
<div class="sb">
<h3>&#10133; Nova Aposta</h3>
<div class="ir"><label>&#128100; Nome:</label><input type="text" class="ji" id="nj" placeholder="Nome do jogador..." maxlength="20"></div>
<div class="cr" onclick="tgr()"><input type="checkbox" id="cr"><label for="cr">&#128081; Este jogador e o RESPONSAVEL pelo sorteio</label></div>
<h3>&#128062; Escolha o animal:</h3>
<div class="mg" id="mg"></div>
<button class="btn bv" onclick="add()">&#9989; Adicionar aposta</button>
</div>
<div class="sb">
<h3>&#128221; Apostas desta rodada:</h3>
<div id="la"><div class="em">Nenhuma aposta ainda</div></div>
<button class="btn bvm" id="bis" onclick="irs()" disabled>&#127920; PRONTO! IR PARA O SORTEIO</button>
</div>
</div>

<div class="panel" id="panel-so">
<div class="sc">
<div class="rb" id="rb"><h3>&#128062; Animais apostados nesta rodada:</h3><div id="rl"></div></div>
<div class="ar" id="ar" style="display:none"></div>
<div><div class="drum" id="drum" onclick="sort()"><div class="di" id="de">&#127920;</div></div><div class="dl">CLIQUE NA URNA PARA SORTEAR!</div></div>
<button class="btn ba" id="bs" onclick="sort()" style="max-width:360px">&#127922; GIRAR A URNA!</button>
<div id="resb" style="display:none;width:100%"><div class="resx"><span class="ree" id="re"></span><div class="ren" id="rn"></div><div class="reg" id="rg"></div><div class="renum" id="rnu"></div></div></div>
<div id="rab" style="display:none;width:100%"><div class="sb"><div class="rat" id="rat"></div><div id="rai"></div></div></div>
<div id="nrb" style="display:none;width:100%"><div class="nrc"><p>Quer jogar de novo? Clique para iniciar uma nova rodada!</p><button class="btn bv" onclick="nova()" style="max-width:320px;margin:0 auto">&#128260; NOVA RODADA</button></div></div>
</div>
</div>

<div class="panel" id="panel-ta"><div class="tg2" id="tg"></div></div>

<div class="panel" id="panel-pl">
<div class="pb"><div class="pt">&#127942; Placar de Vitorias</div><div id="plista"><div class="em">Nenhuma vitoria ainda!</div></div>
<div style="text-align:right;margin-top:12px"><button class="btn bc" onclick="lp()">&#128465;&#65039; Zerar placar</button></div>
</div>
</div>
</div>

<div class="mo" id="mo" onclick="fm(event)">
<div class="md"><div class="me" id="moe"></div><h2 id="mon"></h2><p id="mog"></p><div class="mnu" id="monu"></div>
<button class="btn ba" onclick="fm(null,true)" style="max-width:180px;margin:10px auto 0;font-size:1rem;padding:10px 24px">Fechar</button>
</div>
</div>

<script>
const A=[
{g:1,n:'Avestruz',e:'🦚',nu:[1,2,3,4]},{g:2,n:'Aguia',e:'🦅',nu:[5,6,7,8]},{g:3,n:'Burro',e:'🫏',nu:[9,10,11,12]},
{g:4,n:'Borboleta',e:'🦋',nu:[13,14,15,16]},{g:5,n:'Cachorro',e:'🐶',nu:[17,18,19,20]},{g:6,n:'Cabra',e:'🐐',nu:[21,22,23,24]},
{g:7,n:'Carneiro',e:'🐑',nu:[25,26,27,28]},{g:8,n:'Camelo',e:'🐪',nu:[29,30,31,32]},{g:9,n:'Cobra',e:'🐍',nu:[33,34,35,36]},
{g:10,n:'Coelho',e:'🐰',nu:[37,38,39,40]},{g:11,n:'Cavalo',e:'🐴',nu:[41,42,43,44]},{g:12,n:'Elefante',e:'🐘',nu:[45,46,47,48]},
{g:13,n:'Galo',e:'🐓',nu:[49,50,51,52]},{g:14,n:'Gato',e:'🐱',nu:[53,54,55,56]},{g:15,n:'Jacara',e:'🐊',nu:[57,58,59,60]},
{g:16,n:'Leao',e:'🦁',nu:[61,62,63,64]},{g:17,n:'Macaco',e:'🐵',nu:[65,66,67,68]},{g:18,n:'Porco',e:'🐷',nu:[69,70,71,72]},
{g:19,n:'Pavao',e:'🦜',nu:[73,74,75,76]},{g:20,n:'Peru',e:'🦃',nu:[77,78,79,80]},{g:21,n:'Touro',e:'🐂',nu:[81,82,83,84]},
{g:22,n:'Tigre',e:'🐯',nu:[85,86,87,88]},{g:23,n:'Urso',e:'🐻',nu:[89,90,91,92]},{g:24,n:'Veado',e:'🦌',nu:[93,94,95,96]},
{g:25,n:'Vaca',e:'🐄',nu:[97,98,99,0]}
];
let ap=[],as=null,sd=false,js=false,pl=JSON.parse(localStorage.getItem('jbp')||'{}');
document.addEventListener('DOMContentLoaded',()=>{rmg();rt();rpl();});

function showTab(id,btn){
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.tb2').forEach(b=>b.classList.remove('active'));
  document.getElementById('panel-'+id).classList.add('active');
  btn.classList.add('active');
}
function rmg(){
  document.getElementById('mg').innerHTML=A.map(a=>`<div class="mc" data-g="${a.g}" onclick="sa(${a.g})"><span>${a.e}</span>${a.n}</div>`).join('');
}
function sa(g){
  as=A.find(a=>a.g===g);
  document.querySelectorAll('.mc').forEach(c=>c.classList.remove('sel'));
  document.querySelector(`.mc[data-g="${g}"]`).classList.add('sel');
}
function tgr(){const c=document.getElementById('cr');c.checked=!c.checked;}
function add(){
  const nm=document.getElementById('nj').value.trim();
  const isr=document.getElementById('cr').checked;
  if(!nm){alert('Digite o nome! 👤');return;}
  if(!as){alert('Escolha um animal! 🐾');return;}
  if(isr&&ap.some(a=>a.r)){alert('Ja existe um responsavel: '+ap.find(a=>a.r).nm);document.getElementById('cr').checked=false;return;}
  if(ap.some(a=>a.nm.toLowerCase()===nm.toLowerCase())){alert('Este jogador ja apostou!');return;}
  ap.push({nm,a:as,r:isr});
  document.getElementById('nj').value='';
  document.getElementById('cr').checked=false;
  as=null;
  document.querySelectorAll('.mc').forEach(c=>c.classList.remove('sel'));
  rla();rjt();
  document.getElementById('bis').disabled=false;
}
function rem(i){ap.splice(i,1);rla();rjt();document.getElementById('bis').disabled=ap.length===0;}
function rla(){
  const el=document.getElementById('la');
  if(!ap.length){el.innerHTML='<div class="em">Nenhuma aposta ainda</div>';return;}
  el.innerHTML=ap.map((a,i)=>`<div class="ai"><span style="font-size:1.5rem">${a.a.e}</span><span>${a.r?'👑 ':''}<strong>${a.nm}</strong> → <strong>${a.a.n}</strong>${a.r?'<br><small style="color:var(--am);font-size:.75rem">Responsavel pelo sorteio</small>':''}</span><button class="br2" onclick="rem(${i})">✕</button></div>`).join('');
}
function rjt(){
  const el=document.getElementById('jl');
  if(!ap.length){el.innerHTML='<span class="sj">Nenhum jogador ainda - adicione apostas na aba Apostar</span>';return;}
  el.innerHTML=ap.map(a=>`<div class="chip ${a.r?'resp':''}"><span>${a.r?'👑':'👤'}</span><span>${a.nm}</span><span class="chip-a">${a.a.e}</span></div>`).join('');
}
function irs(){
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.tb2').forEach(b=>b.classList.remove('active'));
  document.getElementById('panel-so').classList.add('active');
  document.querySelectorAll('.tb2')[1].classList.add('active');
  const gs={};
  ap.forEach(a=>{const k=a.a.g;if(!gs[k])gs[k]={a:a.a,nms:[]};gs[k].nms.push(a.nm+(a.r?' 👑':''));});
  document.getElementById('rl').innerHTML=Object.values(gs).map(g=>`<div class="ri"><span class="re">${g.a.e}</span><div><div class="rn">${g.a.n} <small style="color:var(--am);font-size:.8rem">(Grupo ${String(g.a.g).padStart(2,'0')})</small></div><div class="rap">Apostou: ${g.nms.join(', ')}</div></div></div>`).join('');
  const resp=ap.find(a=>a.r);
  const ar=document.getElementById('ar');
  if(resp){ar.style.display='block';ar.innerHTML='👑 <strong>'+resp.nm+'</strong> e o responsavel - so ele gira a urna!';}
  else{ar.style.display='none';}
  document.getElementById('resb').style.display='none';
  document.getElementById('rab').style.display='none';
  document.getElementById('nrb').style.display='none';
  document.getElementById('bs').disabled=false;
  js=false;
}
function sort(){
  if(sd||js)return;
  if(!ap.length){alert('Adicione apostas primeiro!');return;}
  sd=true;
  const drum=document.getElementById('drum');
  const de=document.getElementById('de');
  document.getElementById('bs').disabled=true;
  drum.classList.add('spin');
  const iv=setInterval(()=>{de.textContent=A[Math.floor(Math.random()*A.length)].e;},80);
  setTimeout(()=>{
    clearInterval(iv);drum.classList.remove('spin');
    const s=A[Math.floor(Math.random()*A.length)];
    de.textContent=s.e;
    document.getElementById('re').textContent=s.e;
    document.getElementById('rn').textContent=s.n;
    document.getElementById('rg').textContent='Grupo '+String(s.g).padStart(2,'0');
    document.getElementById('rnu').innerHTML=s.nu.map(n=>`<span class="nb">${String(n).padStart(2,'0')}</span>`).join('');
    document.getElementById('resb').style.display='block';
    let gn=false;
    document.getElementById('rat').innerHTML='🎰 Sorteado: '+s.e+' <strong>'+s.n+'</strong>';
    document.getElementById('rai').innerHTML=ap.map(a=>{
      const w=a.a.g===s.g;
      if(w){gn=true;rv(a.nm);}
      return `<div class="ari ${w?'g':'p'}"><span style="font-size:1.5rem">${a.a.e}</span><span>${a.r?'👑 ':''}<strong>${a.nm}</strong> - ${a.a.n}</span><span class="tg ${w?'tgg':'tgp'}">${w?'🎊 GANHOU!':'😔 Perdeu'}</span></div>`;
    }).join('');
    document.getElementById('rab').style.display='block';
    if(gn){setTimeout(conf,400);rpl();}
    document.querySelectorAll('.ac').forEach(c=>c.classList.remove('dest'));
    const cd=document.querySelector(`.ac[data-g="${s.g}"]`);
    if(cd)cd.classList.add('dest');
    document.getElementById('nrb').style.display='block';
    sd=false;js=true;
  },2200);
}
function nova(){
  ap=[];as=null;js=false;
  rla();rjt();
  document.getElementById('bis').disabled=true;
  document.getElementById('de').textContent='🎰';
  document.querySelectorAll('.mc').forEach(c=>c.classList.remove('sel'));
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.tb2').forEach(b=>b.classList.remove('active'));
  document.getElementById('panel-ap').classList.add('active');
  document.querySelectorAll('.tb2')[0].classList.add('active');
}
function rt(){
  document.getElementById('tg').innerHTML=A.map(a=>`<div class="ac" data-g="${a.g}" onclick="am(${a.g})"><span class="ace">${a.e}</span><span class="acg">Grupo ${String(a.g).padStart(2,'0')}</span><span class="acn">${a.n}</span><div class="acnu">${a.nu.map(n=>String(n).padStart(2,'0')).join(' · ')}</div></div>`).join('');
}
function am(g){
  const a=A.find(x=>x.g===g);
  document.getElementById('moe').textContent=a.e;
  document.getElementById('mon').textContent=a.n;
  document.getElementById('mog').textContent='Grupo '+String(a.g).padStart(2,'0');
  document.getElementById('monu').innerHTML=a.nu.map(n=>`<span class="nb">${String(n).padStart(2,'0')}</span>`).join('');
  document.getElementById('mo').classList.add('open');
}
function fm(e,f){if(f||e?.target?.id==='mo')document.getElementById('mo').classList.remove('open');}
function rv(nm){pl[nm]=(pl[nm]||0)+1;localStorage.setItem('jbp',JSON.stringify(pl));}
function rpl(){
  const el=document.getElementById('plista');
  const s=Object.entries(pl).sort((a,b)=>b[1]-a[1]);
  if(!s.length){el.innerHTML='<div class="em">Nenhuma vitoria ainda!</div>';return;}
  const m=['🥇','🥈','🥉'];
  el.innerHTML=s.map(([nm,w],i)=>`<div class="pi2"><span>${m[i]||'🏅'} ${nm}</span><span class="pw">${w} vitoria${w!==1?'s':''}</span></div>`).join('');
}
function lp(){if(confirm('Zerar o placar?')){pl={};localStorage.removeItem('jbp');rpl();}}
function conf(){
  const c=document.getElementById('cc');
  const cls=['#f5c518','#f07e16','#d93025','#25a050','#1565c0','#6a1b9a','#ffffff'];
  for(let i=0;i<100;i++){
    const p=document.createElement('div');p.className='cp';
    p.style.cssText=`left:${Math.random()*100}%;top:-10px;background:${cls[Math.floor(Math.random()*cls.length)]};width:${Math.random()*10+6}px;height:${Math.random()*10+6}px;border-radius:${Math.random()>.5?'50%':'2px'};animation-duration:${Math.random()*2+1.5}s;animation-delay:${Math.random()*.8}s;`;
    c.appendChild(p);setTimeout(()=>p.remove(),4000);
  }
}
</script>
</body>
</html>

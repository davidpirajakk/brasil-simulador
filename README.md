<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Brasil 2026</title>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap" rel="stylesheet">
<style>
:root{--bg:#0c0c0e;--bg2:#141416;--bg3:#1c1c20;--border:rgba(255,255,255,0.07);--border2:rgba(255,255,255,0.14);--text:#eeece6;--text2:#888680;--text3:#444240;--accent:#d4a843;--red:#c94848;--green:#4cad7a;--blue:#4c7ec9;--f:'Roboto',sans-serif;}
*{margin:0;padding:0;box-sizing:border-box;}
body{background:var(--bg);color:var(--text);font-family:var(--f);font-size:15px;line-height:1.65;min-height:100vh;}
.hidden{display:none!important;}
#s-intro{min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:3rem 1.5rem;position:relative;overflow:hidden;}
#s-intro::before{content:'';position:absolute;width:600px;height:600px;border-radius:50%;background:radial-gradient(circle,rgba(212,168,67,0.06) 0%,transparent 70%);top:50%;left:50%;transform:translate(-50%,-50%);pointer-events:none;}
.i-kicker{font-size:10px;font-weight:500;letter-spacing:.35em;color:var(--accent);text-transform:uppercase;margin-bottom:1.5rem;opacity:0;animation:up .7s .1s forwards;}
.i-h1{font-size:clamp(4rem,12vw,9rem);font-weight:900;line-height:.9;text-align:center;margin-bottom:1rem;opacity:0;animation:up .7s .25s forwards;}
.i-h1 em{color:var(--accent);font-style:normal;}
.i-sub{font-size:1rem;font-weight:300;color:var(--text2);text-align:center;margin-bottom:3.5rem;opacity:0;animation:up .7s .4s forwards;}
.i-btn{font-size:11px;font-weight:500;letter-spacing:.15em;text-transform:uppercase;padding:12px 32px;border:.5px solid var(--accent);border-radius:2px;background:transparent;color:var(--accent);cursor:pointer;transition:background .2s;opacity:0;animation:up .7s .55s forwards;}
.i-btn:hover{background:rgba(212,168,67,.1);}
#s-apikey{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:2rem;}
.box{max-width:480px;width:100%;}
.box h2{font-size:1.8rem;font-weight:700;margin-bottom:.5rem;}
.box p{color:var(--text2);font-size:14px;margin-bottom:1.5rem;line-height:1.6;}
.box a{color:var(--accent);}
.flabel{font-size:10px;font-weight:500;letter-spacing:.2em;color:var(--text3);text-transform:uppercase;margin-bottom:6px;display:block;}
.finput{width:100%;background:var(--bg2);border:.5px solid var(--border2);border-radius:3px;padding:10px 14px;color:var(--text);font-family:var(--f);font-size:13px;outline:none;transition:border-color .2s;margin-bottom:1rem;}
.finput:focus{border-color:var(--accent);}
.btn{width:100%;padding:12px;background:transparent;border:.5px solid var(--accent);border-radius:2px;color:var(--accent);font-family:var(--f);font-size:11px;font-weight:500;letter-spacing:.15em;text-transform:uppercase;cursor:pointer;transition:background .2s;}
.btn:hover{background:rgba(212,168,67,.1);}
.err{color:var(--red);font-size:12px;margin-top:.5rem;display:none;}
#s-party{min-height:100vh;padding:3rem 1.5rem;max-width:1100px;margin:0 auto;}
.stitle{font-size:2rem;font-weight:700;margin-bottom:.4rem;}
.ssub{color:var(--text2);font-size:14px;font-weight:300;margin-bottom:2.5rem;}
.pgrid{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:1px;border:.5px solid var(--border);border-radius:4px;overflow:hidden;margin-bottom:2rem;}
.pcard{background:var(--bg2);padding:1.5rem;cursor:pointer;transition:background .2s;border-bottom:2px solid transparent;display:flex;flex-direction:column;}
.pcard:hover{background:var(--bg3);}
.pcard.sel{background:var(--bg3);}
.pnum{font-size:10px;font-weight:500;color:var(--text3);letter-spacing:.1em;margin-bottom:.4rem;}
.pname{font-size:1.1rem;font-weight:700;margin-bottom:.1rem;}
.pcand{font-size:12px;font-weight:500;margin-bottom:.3rem;}
.pvies{font-size:11px;font-weight:300;color:var(--text3);margin-bottom:.75rem;}
.pdesc{font-size:12px;color:var(--text2);line-height:1.5;margin-bottom:1rem;flex:1;}
.pdiff{font-size:9px;font-weight:500;letter-spacing:.1em;padding:2px 8px;border-radius:2px;border:.5px solid;text-transform:uppercase;}
.de{border-color:var(--green);color:var(--green);}
.dm{border-color:var(--accent);color:var(--accent);}
.dh{border-color:var(--red);color:var(--red);}
.ppct{font-size:1.4rem;font-weight:700;margin-top:.75rem;}
.confirm-row{display:flex;justify-content:flex-end;}
.btn-sm{width:230px;padding:12px;background:transparent;border:.5px solid var(--accent);border-radius:2px;color:var(--accent);font-family:var(--f);font-size:11px;font-weight:500;letter-spacing:.15em;text-transform:uppercase;cursor:pointer;transition:background .2s;}
.btn-sm:hover{background:rgba(212,168,67,.1);}
.btn-sm:disabled{opacity:.3;cursor:not-allowed;}
#s-game{min-height:100vh;display:flex;flex-direction:column;}
.gh{display:flex;align-items:center;justify-content:space-between;padding:.6rem 1.5rem;border-bottom:.5px solid var(--border);background:var(--bg2);flex-wrap:wrap;gap:.75rem;}
.ghl{display:flex;align-items:center;gap:1rem;}
.glogo{font-size:1rem;font-weight:700;}
.glogo span{color:var(--accent);}
.gcand{font-size:11px;color:var(--text2);border-left:.5px solid var(--border2);padding-left:1rem;}
.gstats{display:flex;gap:1.25rem;align-items:center;flex-wrap:wrap;}
.gstat{text-align:center;}
.gsl{font-size:8px;font-weight:500;letter-spacing:.18em;color:var(--text3);text-transform:uppercase;display:block;}
.gsv{font-size:14px;font-weight:500;}
.gsv.g{color:var(--green);}
.gsv.w{color:var(--accent);}
.gsv.b{color:var(--red);}
.fbadge{font-size:9px;font-weight:500;letter-spacing:.15em;text-transform:uppercase;padding:2px 8px;border-radius:2px;border:.5px solid var(--accent);color:var(--accent);}
.gbody{display:grid;grid-template-columns:1fr 300px;flex:1;}
.gnarr{display:flex;flex-direction:column;border-right:.5px solid var(--border);}
.nfeed{flex:1;overflow-y:auto;padding:1.5rem;display:flex;flex-direction:column;gap:1.25rem;min-height:400px;max-height:calc(100vh - 220px);}
.nmeta{font-size:9px;font-weight:500;letter-spacing:.15em;color:var(--text3);text-transform:uppercase;margin-bottom:.4rem;}
.ntext{font-size:15px;font-weight:400;line-height:1.75;}
.nact{font-size:14px;font-weight:300;color:var(--text2);padding:.5rem 0 .5rem 1rem;border-left:2px solid var(--border2);margin-top:.5rem;}
.aiload{display:flex;align-items:center;gap:8px;padding:1rem 0;color:var(--text3);font-size:11px;}
.aidot{width:4px;height:4px;border-radius:50%;background:var(--accent);animation:blink 1.2s infinite;}
.aidot:nth-child(2){animation-delay:.2s;}
.aidot:nth-child(3){animation-delay:.4s;}
.giarea{border-top:.5px solid var(--border);padding:1rem 1.5rem;background:var(--bg2);}
.ihint{font-size:9px;font-weight:500;letter-spacing:.15em;color:var(--text3);text-transform:uppercase;margin-bottom:6px;}
.irow{display:flex;gap:8px;align-items:flex-end;}
.ginput{flex:1;background:var(--bg3);border:.5px solid var(--border2);border-radius:3px;padding:10px 14px;color:var(--text);font-family:var(--f);font-size:14px;outline:none;resize:none;min-height:44px;max-height:120px;transition:border-color .2s;overflow-y:auto;}
.ginput:focus{border-color:var(--accent);}
.gsend{background:transparent;border:.5px solid var(--accent);border-radius:3px;padding:10px 16px;color:var(--accent);font-family:var(--f);font-size:11px;font-weight:500;cursor:pointer;transition:background .15s;white-space:nowrap;height:44px;}
.gsend:hover{background:rgba(212,168,67,.1);}
.gsend:disabled{opacity:.3;cursor:not-allowed;}
.gpanel{display:flex;flex-direction:column;overflow-y:auto;background:var(--bg2);}
.pblock{padding:1rem 1.25rem;border-bottom:.5px solid var(--border);}
.plabel{font-size:8px;font-weight:500;letter-spacing:.2em;color:var(--text3);text-transform:uppercase;margin-bottom:.75rem;display:block;}
.bignum{font-size:3rem;font-weight:700;line-height:1;}
.ind{margin-bottom:9px;}
.indh{display:flex;justify-content:space-between;margin-bottom:3px;}
.indn{font-size:11px;color:var(--text2);}
.indv{font-size:11px;font-weight:500;}
.indb{height:2px;background:var(--border);border-radius:1px;overflow:hidden;}
.indf{height:100%;border-radius:1px;transition:width .5s;}
.agitem{display:flex;gap:8px;margin-bottom:8px;align-items:flex-start;}
.agck{font-size:10px;font-weight:500;margin-top:2px;flex-shrink:0;}
.agck.done{color:var(--green);}
.agck.open{color:var(--text3);}
.agtx{font-size:12px;color:var(--text2);line-height:1.4;}
.rvrow{display:flex;align-items:center;gap:8px;margin-bottom:7px;}
.rvp{font-size:10px;font-weight:500;width:56px;flex-shrink:0;}
.rvbw{flex:1;height:3px;background:var(--border);border-radius:2px;overflow:hidden;}
.rvf{height:100%;border-radius:2px;transition:width .5s;}
.rvpct{font-size:10px;color:var(--text3);width:32px;text-align:right;}
.legitem{display:flex;align-items:center;gap:4px;font-size:10px;color:var(--text2);}
.legdot{width:7px;height:7px;border-radius:1px;display:inline-block;flex-shrink:0;}
#s-end{min-height:100vh;display:flex;align-items:center;justify-content:center;flex-direction:column;padding:3rem 1.5rem;text-align:center;}
.eresult{font-size:clamp(3rem,8vw,6rem);font-weight:900;line-height:1;margin-bottom:1rem;}
.eresult.win{color:var(--accent);}
.eresult.lose{color:var(--red);}
.enarr{max-width:560px;font-weight:300;color:var(--text2);font-size:15px;line-height:1.7;margin-bottom:2rem;}
.egrid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;max-width:480px;width:100%;border:.5px solid var(--border);border-radius:4px;overflow:hidden;margin-bottom:2rem;}
.estat{background:var(--bg2);padding:1.25rem;}
.esl{font-size:8px;font-weight:500;letter-spacing:.15em;color:var(--text3);text-transform:uppercase;margin-bottom:4px;}
.esv{font-size:2rem;font-weight:700;}
.btngh{font-size:10px;font-weight:500;letter-spacing:.15em;text-transform:uppercase;padding:10px 24px;border:.5px solid var(--border2);border-radius:2px;background:transparent;color:var(--text2);cursor:pointer;transition:color .15s,border-color .15s;}
.btngh:hover{color:var(--text);border-color:var(--text2);}
@keyframes up{from{opacity:0;transform:translateY(12px)}to{opacity:1;transform:translateY(0)}}
@keyframes blink{0%,80%,100%{opacity:.2}40%{opacity:1}}
::-webkit-scrollbar{width:3px;}
::-webkit-scrollbar-track{background:transparent;}
::-webkit-scrollbar-thumb{background:var(--border2);border-radius:2px;}
@media(max-width:680px){.gbody{grid-template-columns:1fr}.gpanel{border-top:.5px solid var(--border)}}
</style>
</head>
<body>

<div id="s-intro">
  <p class="i-kicker">Brasil · Eleições 2026</p>
  <h1 class="i-h1">BRASIL<br><em>2026</em></h1>
  <p class="i-sub">O poder está à espera. Você sabe o que fazer com ele?</p>
  <button class="i-btn" onclick="goTo('s-apikey')">Entrar no jogo ?</button>
</div>

<div id="s-apikey" class="hidden">
  <div class="box">
    <h2>Configure a IA</h2>
    <p>O jogo usa o Google Gemini para narrar os acontecimentos em tempo real.<br><br>
    Não tem uma chave? <a href="https://aistudio.google.com" target="_blank">Crie gratuitamente em aistudio.google.com</a> — sem cartão.</p>
    <label class="flabel">Gemini API Key</label>
    <input class="finput" type="password" id="api-key-input" placeholder="AIza..." />
    <p style="font-size:12px;color:var(--text3);margin-bottom:1rem;">A chave fica salva só no seu navegador.</p>
    <button class="btn" onclick="saveApiKey()">Confirmar e continuar ?</button>
    <p id="apikey-err" class="err">Chave inválida. Verifique e tente novamente.</p>
  </div>
</div>

<div id="s-party" class="hidden">
  <h2 class="stitle">Escolha seu partido</h2>
  <p class="ssub">Cada partido tem sua agenda, sua base e seus objetivos. Escolha com cuidado.</p>
  <div class="pgrid" id="party-grid"></div>
  <div class="confirm-row">
    <button class="btn-sm" id="party-btn" onclick="confirmParty()" disabled>Jogar com este partido ?</button>
  </div>
</div>

<div id="s-game" class="hidden">
  <header class="gh">
    <div class="ghl">
      <div class="glogo">Brasil <span>2026</span></div>
      <div class="gcand" id="gcand">—</div>
      <span class="fbadge" id="fbadge">Campanha</span>
    </div>
    <div class="gstats">
      <div class="gstat"><span class="gsl">Votos/Aprov.</span><div class="gsv" id="hv">—</div></div>
      <div class="gstat"><span class="gsl">Congresso</span><div class="gsv" id="hc">—</div></div>
      <div class="gstat"><span class="gsl">Rodada</span><div class="gsv" id="hr">1/25</div></div>
    </div>
  </header>
  <div class="gbody">
    <div class="gnarr">
      <div class="nfeed" id="nfeed"></div>
      <div class="giarea">
        <p class="ihint">Sua decisão — descreva o que o partido faz</p>
        <div class="irow">
          <textarea class="ginput" id="pinput" rows="1"
            placeholder="Ex: Vamos focar a campanha no Nordeste, começando pelo Ceará..."
            onkeydown="handleKey(event)"></textarea>
          <button class="gsend" id="sbtn" onclick="sendAction()">Enviar ?</button>
        </div>
      </div>
    </div>
    <div class="gpanel">
      <div class="pblock">
        <span class="plabel" id="vlabel">Intenção de votos</span>
        <div class="bignum" id="bignum">—</div>
      </div>
      <div class="pblock">
        <span class="plabel">Mapa eleitoral</span>
        <div id="minimap"></div>
        <div style="display:flex;flex-wrap:wrap;gap:6px;margin-top:6px;">
          <div class="legitem"><div class="legdot" id="legdot"></div>Seu partido</div>
          <div class="legitem"><div class="legdot" style="background:#8b2020"></div>Oposição</div>
          <div class="legitem"><div class="legdot" style="background:#5a5020"></div>Disputado</div>
        </div>
      </div>
      <div class="pblock">
        <span class="plabel">Pesquisa eleitoral</span>
        <div id="rivals"></div>
      </div>
      <div class="pblock" id="indblock" style="display:none">
        <span class="plabel">Indicadores nacionais</span>
        <div id="inds"></div>
      </div>
      <div class="pblock">
        <span class="plabel">Agenda do partido</span>
        <div id="agenda"></div>
      </div>
    </div>
  </div>
</div>

<div id="s-end" class="hidden">
  <p style="font-size:10px;font-weight:500;letter-spacing:.2em;color:var(--text3);margin-bottom:1.5rem;">RESULTADO FINAL · BRASIL 2026</p>
  <div class="eresult" id="etitle"></div>
  <div class="enarr" id="enarr"></div>
  <div class="egrid" id="egrid"></div>
  <button class="btngh" onclick="location.reload()">Jogar novamente</button>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/7.8.5/d3.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/topojson/3.0.2/topojson.min.js"></script>
<script>
const PARTIES={
  PT:{nome:'PT',full:'Partido dos Trabalhadores',num:13,candidato:'Lula',vies:'Centro-esquerda trabalhista',
    desc:'Lula busca um novo mandato. Base sólida no Nordeste e nos sindicatos. Favorito nas pesquisas, mas enfrenta polarização intensa.',
    cor:'#c94848',pct:34,dif:'Médio',dclass:'dm',
    agenda:['Ampliar programas de transferência de renda','Reforma trabalhista pró-trabalhador','Fortalecer o SUS e educação pública','Política industrial e reindustrialização','Política externa Sul-Sul e BRICS'],
    pp:'O candidato é Lula, do PT (nº 13). Centro-esquerda trabalhista. Base: Nordeste, sindicatos, movimentos sociais, classe C. Favorito com 34%. Lula é experiente e carismático. Prioridades: programas sociais, direitos trabalhistas, saúde, educação, política externa Sul-Sul. O jogador controla as decisões estratégicas do partido.'},
  PSOL:{nome:'PSOL',full:'Partido Socialismo e Liberdade',num:50,candidato:'Erika Hilton',vies:'Esquerda progressista',
    desc:'Erika Hilton lidera a candidatura progressista. Jovens urbanos, pautas de direitos e identidade forte. Pode definir quem vence no 2º turno.',
    cor:'#c97c48',pct:12,dif:'Difícil',dclass:'dh',
    agenda:['Direitos LGBTQIA+ e política de gênero','Reforma agrária e habitação popular','Desmilitarização da polícia','Renda básica universal','Política climática radical'],
    pp:'A candidata é Erika Hilton, do PSOL (nº 50). Esquerda progressista. Base: jovens urbanos, LGBTQIA+, universitários, periferia progressista. Com 12%, pode ser kingmaker no 2º turno. Erika é carismática e direta. Prioridades: direitos progressistas, habitação, desmilitarização, renda básica, clima. O jogador controla as decisões estratégicas do partido.'},
  UP:{nome:'UP',full:'Unidade Popular',num:80,candidato:'Jones Manoel',vies:'Esquerda revolucionária',
    desc:'Jones Manoel, o mais à esquerda. Começa com 6% — a run mais difícil e mais recompensadora. Mobilização popular como estratégia central.',
    cor:'#4cad7a',pct:6,dif:'Muito difícil',dclass:'dh',
    agenda:['Nationalização de setores estratégicos','Reforma agrária radical e imediata','Auditoria da dívida pública','Constituinte para nova Constituição','Soberania alimentar'],
    pp:'O candidato é Jones Manoel, da UP (nº 80). Esquerda revolucionária. Base: movimentos populares, sem-terra, trabalhadores informais. Com 6%, é o grande azarão. Intelectual e combativo. Prioridades: nationalização, reforma agrária, auditoria da dívida, constituinte. Sem alianças com conservadores. O jogador controla as decisões estratégicas do partido.'},
  PL:{nome:'PL',full:'Partido Liberal',num:22,candidato:'Nikolas Ferreira',vies:'Centro-direita conservadora',
    desc:'Nikolas Ferreira, fenômeno das redes sociais. Segundo favorito com base sólida no Sul e nos evangélicos. Joga no antagonismo ao PT.',
    cor:'#4c7ec9',pct:28,dif:'Médio',dclass:'dm',
    agenda:['Privatizações e estado mínimo','Segurança pública e penas mais duras','Pauta conservadora nos costumes','Apoio ao agronegócio e ruralismo','Reforma previdenciária e fiscal'],
    pp:'O candidato é Nikolas Ferreira, do PL (nº 22). Centro-direita. Base: Sul do Brasil, agronegócio, evangélicos, classe média conservadora. Com 28%, principal rival do PT. Nikolas é jovem, articulado nas redes e combativo nos debates. Prioridades: privatizações, segurança, agenda conservadora, agro, reforma fiscal. O jogador controla as decisões estratégicas do partido.'},
  MISSAO:{nome:'Missão',full:'Partido Missão',num:14,candidato:'Renan Santos',vies:'Direita disruptiva e radical',
    desc:'Renan Santos e o MBL. Outsider com alcance digital enorme. Combate ao crime organizado, reformas radicais e estilo confrontacional.',
    cor:'#9c48c9',pct:10,dif:'Difícil',dclass:'dh',
    agenda:['Guerra total ao crime organizado','Reformas radicais no Estado','Liberdade econômica e desburocratização','Combate ao marxismo cultural','Transparência radical e anti-corrupção'],
    pp:'O candidato é Renan Santos, do Partido Missão (nº 14), fundado pelo MBL. Direita disruptiva. Base: jovens de direita nas redes, antipetistas urbanos, liberais econômicos. Com 10%, é o outsider confrontacional. Renan provoca e polariza por estratégia — nunca recua publicamente. Prioridades: combate ao crime, reformas radicais, liberdade econômica, anti-corrupção. O jogador controla as decisões estratégicas do partido.'},
};

let G={apiKey:'',partido:null,fase:'campanha',rodada:1,total:25,votos:0,aprovacao:0,cong:40,pib:2.5,inf:5.2,hist:[],agCumprida:[],
  rivais:{PT:{cor:'#c94848',pct:34,cand:'Lula'},PL:{cor:'#4c7ec9',pct:28,cand:'Nikolas'},PSOL:{cor:'#c97c48',pct:12,cand:'Erika'},MISSAO:{cor:'#9c48c9',pct:10,cand:'Renan'},UP:{cor:'#4cad7a',pct:6,cand:'Jones'},Outros:{cor:'#444240',pct:10,cand:''}}};

let selKey=null;

function goTo(id){document.querySelectorAll('[id^="s-"]').forEach(e=>e.classList.add('hidden'));document.getElementById(id).classList.remove('hidden');}

function saveApiKey(){
  const k=document.getElementById('api-key-input').value.trim();
  if(k.length<10){document.getElementById('apikey-err').style.display='block';return;}
  G.apiKey=k;document.getElementById('apikey-err').style.display='none';
  buildPartyGrid();goTo('s-party');
}

function buildPartyGrid(){
  const g=document.getElementById('party-grid');g.innerHTML='';
  Object.entries(PARTIES).forEach(([k,p])=>{
    const c=document.createElement('div');c.className='pcard';
    c.innerHTML=`<div class="pnum">Nº ${p.num}</div>
      <div class="pname" style="color:${p.cor}">${p.nome}</div>
      <div class="pcand" style="color:${p.cor}cc">${p.candidato}</div>
      <div class="pvies">${p.vies}</div>
      <div class="pdesc">${p.desc}</div>
      <div style="display:flex;align-items:center;justify-content:space-between;margin-top:.75rem">
        <span class="pdiff ${p.dclass}">${p.dif}</span>
        <div class="ppct" style="color:${p.cor}">${p.pct}%</div>
      </div>`;
    c.addEventListener('mouseenter',()=>{if(!c.classList.contains('sel'))c.style.borderBottom=`2px solid ${p.cor}55`;});
    c.addEventListener('mouseleave',()=>{if(!c.classList.contains('sel'))c.style.borderBottom='2px solid transparent';});
    c.addEventListener('click',()=>{
      selKey=k;
      document.querySelectorAll('.pcard').forEach(x=>{x.classList.remove('sel');x.style.borderBottom='2px solid transparent';});
      c.classList.add('sel');c.style.borderBottom=`2px solid ${p.cor}`;
      document.getElementById('party-btn').disabled=false;
    });
    g.appendChild(c);
  });
}

function confirmParty(){
  if(!selKey)return;
  G.partido=PARTIES[selKey];G.votos=G.partido.pct;
  delete G.rivais[selKey];
  initGame();goTo('s-game');
}

function initGame(){
  document.getElementById('gcand').textContent=`${G.partido.candidato} · ${G.partido.nome}`;
  document.getElementById('legdot').style.background=G.partido.cor;
  loadMap();updatePanel();renderAgenda();
  callIA(firstPrompt(),true);
}

function firstPrompt(){
  const rv=Object.entries(G.rivais).filter(([k])=>k!=='Outros').map(([k,v])=>`${v.cand} (${k}) ${v.pct}%`).join(', ');
  return `Você é o narrador de Brasil 2026, simulador político sobre as eleições presidenciais brasileiras de 2026.

PARTIDO: ${G.partido.full} (nº ${G.partido.num})
CANDIDATO: ${G.partido.candidato}
PERFIL: ${G.partido.pp}

CONTEXTO:
- Ano: 2026, Brasil
- Fase: Campanha eleitoral (5 rodadas até o 1º turno)
- Pesquisa: ${G.votos}%
- Rivais: ${rv}

REGRAS DE NARRAÇÃO:
- Português brasileiro autêntico
- Tom que mistura jornalismo político, drama e ironia brasileira
- Seja específico: estados reais, situações verossímeis do Brasil de 2026
- Termine SEMPRE com uma situação concreta que exige decisão do jogador
- Máximo 4 parágrafos
- Refira-se sempre pelo nome: ${G.partido.candidato}
- O jogador controla o partido, não é o candidato — use "o partido", "a campanha", "a equipe"

Narre o início da campanha de ${G.partido.candidato} e apresente a primeira decisão estratégica.`;
}

async function callIA(prompt,first=false){
  setInput(false);showLoad();
  try{
    const url=`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${G.apiKey}`;
    const res=await fetch(url,{method:'POST',headers:{'Content-Type':'application/json'},
      body:JSON.stringify({contents:[{parts:[{text:prompt}]}],generationConfig:{maxOutputTokens:800,temperature:0.85}})});
    const data=await res.json();
    const txt=data.candidates?.[0]?.content?.parts?.[0]?.text||'Erro ao obter resposta.';
    removeLoad();addNarr(txt,first?'início da campanha':'rodada '+G.rodada);setInput(true);updateHeader();
  }catch(e){
    removeLoad();addNarr('? Erro de conexão. Verifique sua chave e tente novamente.','erro');setInput(true);
  }
}

async function sendAction(){
  const input=document.getElementById('pinput');
  const acao=input.value.trim();if(!acao)return;
  addAct(acao);input.value='';
  G.hist.push({r:G.rodada,acao,fase:G.fase});
  G.rodada++;
  if(G.fase==='campanha'&&G.rodada>5){G.fase='eleicao1';document.getElementById('fbadge').textContent='1º Turno';}
  else if(G.fase==='eleicao1'&&G.rodada>7){G.fase='inter';document.getElementById('fbadge').textContent='Entre Turnos';}
  else if(G.fase==='inter'&&G.rodada>9){G.fase='eleicao2';document.getElementById('fbadge').textContent='2º Turno';}
  else if(G.fase==='eleicao2'&&G.rodada>10){
    G.fase='governo';document.getElementById('fbadge').textContent='Governo';
    document.getElementById('indblock').style.display='block';
    document.getElementById('vlabel').textContent='Aprovação';
    G.aprovacao=G.votos;G.cong=Math.min(65,G.votos*1.2);
  }else if(G.fase==='governo'&&G.rodada>25){endGame();return;}
  updateNumbers(acao);
  await callIA(ctxPrompt(acao));
  updatePanel();renderAgenda();
}

function ctxPrompt(acao){
  const ul=G.hist.slice(-3).map(h=>`R${h.r} (${h.fase}): "${h.acao}"`).join('\n');
  const fd={
    campanha:`Campanha — rodada ${G.rodada-1}/5. Faltam ${Math.max(0,6-G.rodada)} rodadas para o 1º turno.`,
    eleicao1:'Primeiro turno das eleições presidenciais de 2026.',
    inter:'Entre os dois turnos — negociação de apoios.',
    eleicao2:'Segundo turno — decisão final do eleitorado.',
    governo:`Governo federal — ano ${Math.ceil((G.rodada-10)/5)}, rodada ${G.rodada-10}/16 do mandato.`,
  }[G.fase]||G.fase;
  const nums=G.fase==='governo'
    ?`Aprovação: ${Math.round(G.aprovacao)}% | PIB: ${G.pib.toFixed(1)}% | Inflação: ${G.inf.toFixed(1)}% | Congresso: ${Math.round(G.cong)}%`
    :`Votos: ${Math.round(G.votos)}% | Rivais: ${Object.entries(G.rivais).filter(([k])=>k!=='Outros').map(([k,v])=>`${v.cand} ${Math.round(v.pct)}%`).join(', ')}`;
  return `Narrador de Brasil 2026.
CANDIDATO: ${G.partido.candidato} | PARTIDO: ${G.partido.full}
PERFIL: ${G.partido.pp}
FASE: ${fd}
DADOS: ${nums}
HISTÓRICO:\n${ul}
DECISÃO: "${acao}"

INSTRUÇÃO: Narre as consequências desta decisão de forma vívida e específica ao Brasil. Mostre reações de aliados, rivais, imprensa e população. Inclua um desdobramento inesperado que exige nova decisão. Máximo 4 parágrafos. Tom: jornalístico, cinematográfico, irônico quando couber. Não invente números além dos fornecidos. Refira-se por: ${G.partido.candidato}. Use "o partido", "a campanha", "a equipe" — o jogador controla o partido.`;
}

function updateNumbers(acao){
  const a=acao.toLowerCase();
  if(G.fase!=='governo'){
    let d=(Math.random()-.4)*3;
    if(a.includes('nordeste')||a.includes('social'))d+=1.5;
    if(a.includes('segurança')||a.includes('crime'))d+=1;
    if(a.includes('economia')||a.includes('emprego'))d+=.8;
    if(a.includes('debate')||a.includes('confronto'))d+=Math.random()>.5?2:-2;
    G.votos=Math.max(2,Math.min(70,G.votos+d));
    Object.values(G.rivais).forEach(r=>{r.pct=Math.max(1,r.pct-d*.35);});
  }else{
    let dap=(Math.random()-.5)*4;
    if(a.includes('social')||a.includes('saúde')||a.includes('educação'))dap+=2;
    if(a.includes('privatiz')||a.includes('corte'))dap-=2;
    G.aprovacao=Math.max(10,Math.min(90,G.aprovacao+dap));
    G.pib=Math.max(-3,Math.min(8,G.pib+(Math.random()-.45)*.5));
    G.inf=Math.max(1,Math.min(25,G.inf+(Math.random()-.55)*.6));
    G.cong=Math.max(15,Math.min(75,G.cong+(Math.random()-.5)*3));
  }
}

function addNarr(txt,label){
  const f=document.getElementById('nfeed');
  const e=document.createElement('div');
  e.innerHTML=`<div class="nmeta">${label}</div><div class="ntext">${txt.replace(/\n/g,'<br>')}</div>`;
  f.appendChild(e);f.scrollTop=f.scrollHeight;
}
function addAct(acao){
  const f=document.getElementById('nfeed');
  const e=document.createElement('div');
  e.innerHTML=`<div class="nact">? "${acao}"</div>`;
  f.appendChild(e);f.scrollTop=f.scrollHeight;
}
function showLoad(){
  const f=document.getElementById('nfeed');
  const e=document.createElement('div');e.id='aiload';e.className='aiload';
  e.innerHTML=`<div class="aidot"></div><div class="aidot"></div><div class="aidot"></div><span>narrando...</span>`;
  f.appendChild(e);f.scrollTop=f.scrollHeight;
}
function removeLoad(){const e=document.getElementById('aiload');if(e)e.remove();}
function setInput(on){document.getElementById('pinput').disabled=!on;document.getElementById('sbtn').disabled=!on;}
function handleKey(e){if(e.key==='Enter'&&!e.shiftKey){e.preventDefault();sendAction();}}

function updateHeader(){
  const vEl=document.getElementById('hv');
  const v=G.fase==='governo'?Math.round(G.aprovacao):Math.round(G.votos);
  vEl.textContent=v+'%';vEl.className='gsv '+(v>=45?'g':v>=28?'w':'b');
  const cEl=document.getElementById('hc');const c=Math.round(G.cong);
  cEl.textContent=c+'%';cEl.className='gsv '+(c>=50?'g':c>=35?'w':'b');
  document.getElementById('hr').textContent=`${G.rodada}/${G.total}`;
}

function updatePanel(){
  const bn=document.getElementById('bignum');
  const v=G.fase==='governo'?G.aprovacao:G.votos;
  bn.textContent=Math.round(v)+'%';bn.style.color=G.partido?.cor||'var(--accent)';
  const rv=document.getElementById('rivals');
  if(G.fase!=='governo'){
    const all={[G.partido?.nome||'?']:{cor:G.partido?.cor,pct:G.votos,cand:G.partido?.candidato},...G.rivais};
    rv.innerHTML=Object.entries(all).sort((a,b)=>b[1].pct-a[1].pct).map(([n,d])=>`
      <div class="rvrow"><span class="rvp" style="color:${d.cor}">${n}</span>
      <div class="rvbw"><div class="rvf" style="width:${Math.min(100,d.pct)}%;background:${d.cor}"></div></div>
      <span class="rvpct">${Math.round(d.pct)}%</span></div>`).join('');
  }else{rv.innerHTML=`<span style="font-size:12px;color:var(--text3)">Eleição concluída</span>`;}
  if(G.fase==='governo'){
    document.getElementById('inds').innerHTML=[
      {n:'PIB',v:(G.pib>=0?'+':'')+G.pib.toFixed(1)+'%',b:Math.min(100,Math.max(0,(G.pib+3)*12)),c:'var(--green)'},
      {n:'Inflação',v:G.inf.toFixed(1)+'%',b:Math.min(100,G.inf*4),c:'var(--red)'},
      {n:'Congresso',v:Math.round(G.cong)+'%',b:G.cong,c:'var(--blue)'},
    ].map(i=>`<div class="ind"><div class="indh"><span class="indn">${i.n}</span><span class="indv" style="color:${i.c}">${i.v}</span></div><div class="indb"><div class="indf" style="width:${i.b}%;background:${i.c}"></div></div></div>`).join('');
  }
}

function renderAgenda(){
  if(!G.partido)return;
  document.getElementById('agenda').innerHTML=G.partido.agenda.map((item,i)=>{
    const done=G.agCumprida.includes(i);
    return `<div class="agitem"><span class="agck ${done?'done':'open'}">${done?'?':'?'}</span><span class="agtx" style="${done?'color:var(--text3);text-decoration:line-through':''}">${item}</span></div>`;
  }).join('');
}

function estadoCor(nome){
  if(!G.partido)return'#333';
  const ne=['Bahia','Ceará','Maranhão','Piauí','Pernambuco','Rio Grande do Norte','Sergipe','Alagoas','Paraíba'];
  const sul=['Rio Grande do Sul','Santa Catarina','Paraná'];
  const co=['Goiás','Mato Grosso','Mato Grosso do Sul','Distrito Federal'];
  const p=G.partido.nome;
  if(['PT','PSOL','UP'].includes(p)){
    if(ne.includes(nome))return G.partido.cor;
    if(sul.includes(nome)||co.includes(nome))return'#8b2020';
    return'#5a5020';
  }
  if(sul.includes(nome)||co.includes(nome))return G.partido.cor;
  if(ne.includes(nome))return'#8b2020';
  return'#5a5020';
}

function loadMap(){
  d3.json('https://cdn.jsdelivr.net/npm/datamaps@0.5.10/src/js/data/bra.topo.json').then(topo=>{
    const key=Object.keys(topo.objects)[0];
    const feats=topojson.feature(topo,topo.objects[key]).features;
    const c=document.getElementById('minimap');
    const w=c.offsetWidth||260,h=w*.95;
    const svg=d3.select('#minimap').append('svg').attr('viewBox',`0 0 ${w} ${h}`).attr('width','100%');
    const proj=d3.geoMercator().fitSize([w,h],topojson.feature(topo,topo.objects[key]));
    svg.selectAll('path').data(feats).join('path')
      .attr('d',d3.geoPath(proj))
      .attr('fill',d=>estadoCor(d.properties.name))
      .attr('stroke','#0c0c0e').attr('stroke-width',.6);
  });
}

async function endGame(){
  setInput(false);
  const ganhou=G.aprovacao>=45&&G.cong>=35;
  let legado='O mandato chegou ao fim.';
  try{
    const url=`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${G.apiKey}`;
    const res=await fetch(url,{method:'POST',headers:{'Content-Type':'application/json'},
      body:JSON.stringify({contents:[{parts:[{text:`Narrador de Brasil 2026. O mandato de ${G.partido.candidato} (${G.partido.nome}) acabou.
Aprovação: ${Math.round(G.aprovacao)}% | PIB: ${G.pib.toFixed(1)}% | Inflação: ${G.inf.toFixed(1)}% | Congresso: ${Math.round(G.cong)}%
${ganhou?'Foi reeleito.':'Perdeu a reeleição.'}
Escreva um parágrafo épico sobre o legado deste governo. Tom literário e jornalístico.`}]}],generationConfig:{maxOutputTokens:300}})});
    const d=await res.json();
    legado=d.candidates?.[0]?.content?.parts?.[0]?.text||legado;
  }catch(e){}
  goTo('s-end');
  document.getElementById('etitle').textContent=ganhou?'Reeleito.':'Derrota.';
  document.getElementById('etitle').className='eresult '+(ganhou?'win':'lose');
  document.getElementById('enarr').textContent=legado;
  document.getElementById('egrid').innerHTML=[
    {l:'Aprovação',v:Math.round(G.aprovacao)+'%',c:G.aprovacao>=45?'var(--green)':'var(--red)'},
    {l:'PIB final',v:G.pib.toFixed(1)+'%',c:'var(--text)'},
    {l:'Congresso',v:Math.round(G.cong)+'%',c:'var(--text)'},
  ].map(s=>`<div class="estat"><div class="esl">${s.l}</div><div class="esv" style="color:${s.c}">${s.v}</div></div>`).join('');
}
</script>
</body>
</html>

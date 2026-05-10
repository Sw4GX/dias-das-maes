<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Feliz Dia das Mães 💗</title>
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600;700&family=Lora:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;}
body{
  background:linear-gradient(160deg,#fff0f5 0%,#ffe4ee 60%,#ffd6e7 100%);
  min-height:100vh;
  font-family:'Lora',Georgia,serif;
  display:flex;flex-direction:column;align-items:center;
  padding:0 0 60px;
  position:relative;overflow-x:hidden;
}
.petals{position:fixed;inset:0;pointer-events:none;overflow:hidden;z-index:0;}
.petal{position:absolute;animation:fall linear infinite;opacity:0.5;}
@keyframes fall{
  0%{transform:translateY(-20px) rotate(0deg);opacity:0;}
  10%{opacity:0.6;}90%{opacity:0.3;}
  100%{transform:translateY(105vh) rotate(400deg);opacity:0;}
}
.hero{
  width:100%;background:linear-gradient(180deg,#e8175a,#a80828);
  padding:40px 24px 52px;text-align:center;
  clip-path:ellipse(100% 88% at 50% 12%);
  position:relative;z-index:1;
}
.hero-small{font-family:'Lora',serif;font-size:12px;letter-spacing:4px;text-transform:uppercase;color:rgba(255,255,255,.75);margin-bottom:10px;}
.hero-big{font-family:'Dancing Script',cursive;font-size:clamp(36px,9vw,64px);color:#fff;font-weight:700;line-height:1.15;text-shadow:0 2px 24px rgba(0,0,0,.2);}
.hero-sub{font-family:'Dancing Script',cursive;font-size:22px;color:rgba(255,255,255,.88);margin-top:8px;}

.progress-row{display:flex;gap:10px;margin:20px 0 0;z-index:2;position:relative;}
.prog-dot{width:13px;height:13px;border-radius:50%;background:#ffc2d4;border:2px solid #e8175a;transition:background .4s,transform .3s;}
.prog-dot.done{background:#e8175a;transform:scale(1.2);}
.prog-dot.current{background:#ff6b8a;border-color:#c8103a;animation:dotPulse 1s infinite;}
@keyframes dotPulse{0%,100%{transform:scale(1);}50%{transform:scale(1.35);}}

.card{
  background:#fff;border-radius:22px;
  padding:32px 28px 26px;
  margin:18px 20px 0;
  box-shadow:0 6px 36px rgba(200,16,58,.13);
  border:1.5px solid #ffc2d4;
  text-align:center;
  max-width:500px;width:calc(100% - 40px);
  z-index:2;position:relative;
  animation:slideIn .4s ease;
}
@keyframes slideIn{from{opacity:0;transform:translateY(22px);}to{opacity:1;transform:translateY(0);}}

.charada-num{font-family:'Dancing Script',cursive;font-size:15px;color:#e8175a;letter-spacing:2px;margin-bottom:14px;}
.charada-text{font-family:'Lora',serif;font-style:italic;font-size:18px;color:#5a1025;line-height:1.75;margin-bottom:22px;}
.options{display:flex;flex-direction:column;gap:11px;}
.opt-btn{
  font-family:'Lora',serif;font-size:15px;color:#8a1030;
  padding:13px 18px;border:1.5px solid #ffc2d4;border-radius:13px;
  background:#fff8fb;cursor:pointer;transition:all .25s;text-align:left;
}
.opt-btn:hover{background:#fff0f5;border-color:#e8175a;}
.opt-btn.correct{background:#fff0f5;border-color:#e8175a;color:#c8103a;font-weight:600;}
.opt-btn.wrong{background:#fff5f5;border-color:#ffaaaa;color:#cc4444;}
.opt-btn:disabled{cursor:default;}

.feedback{margin-top:18px;font-family:'Dancing Script',cursive;font-size:23px;animation:popIn .3s ease;min-height:28px;}
@keyframes popIn{from{transform:scale(0.6);opacity:0;}to{transform:scale(1);opacity:1;}}
.feedback.ok{color:#e8175a;}
.feedback.no{color:#cc4444;}

.next-btn{
  margin-top:20px;font-family:'Dancing Script',cursive;font-size:21px;
  color:#fff;background:linear-gradient(135deg,#e8175a,#a80828);
  border:none;border-radius:13px;padding:13px 36px;cursor:pointer;
  box-shadow:0 4px 18px rgba(200,16,58,.28);
  transition:transform .2s,box-shadow .2s;display:none;
}
.next-btn:hover{transform:translateY(-2px);box-shadow:0 8px 24px rgba(200,16,58,.38);}

/* Surpresa final */
.surprise{
  display:none;flex-direction:column;align-items:center;
  margin:14px 20px 0;max-width:500px;width:calc(100% - 40px);
  z-index:2;position:relative;
}
.surprise.visible{display:flex;animation:slideIn .6s ease;}

.score-badge{
  background:linear-gradient(135deg,#e8175a,#a80828);
  color:#fff;border-radius:999px;padding:10px 28px;
  font-family:'Dancing Script',cursive;font-size:20px;
  margin-bottom:14px;
  box-shadow:0 4px 16px rgba(200,16,58,.25);
}
.surprise-title{
  font-family:'Dancing Script',cursive;font-size:clamp(34px,8vw,56px);
  color:#c8103a;font-weight:700;text-align:center;margin-bottom:14px;
  animation:pulse 2s infinite;
}
@keyframes pulse{0%,100%{transform:scale(1);}50%{transform:scale(1.04);}}

.surprise-msg{
  background:#fff;border-radius:22px;padding:32px 28px 24px;
  border:1.5px solid #ffc2d4;box-shadow:0 6px 36px rgba(200,16,58,.12);
  text-align:center;width:100%;position:relative;
}
.surprise-msg::before{
  content:'"';font-family:'Dancing Script',cursive;font-size:80px;
  color:#ffd6e7;position:absolute;top:-8px;left:16px;line-height:1;
}
.surprise-msg p{font-family:'Lora',serif;font-style:italic;font-size:17px;color:#5a1025;line-height:1.85;}
.surprise-msg .sign{font-family:'Dancing Script',cursive;font-size:26px;color:#c8103a;margin-top:16px;font-weight:700;}

.hearts-row{display:flex;gap:12px;margin-top:16px;flex-wrap:wrap;justify-content:center;}
.heart-chip{
  background:#fff;border:1.5px solid #ffc2d4;border-radius:999px;
  padding:9px 20px;font-family:'Dancing Script',cursive;
  font-size:18px;color:#c8103a;animation:floatChip 3s ease-in-out infinite;
}
.heart-chip:nth-child(2){animation-delay:.35s;}
.heart-chip:nth-child(3){animation-delay:.7s;}
@keyframes floatChip{0%,100%{transform:translateY(0);}50%{transform:translateY(-7px);}}

canvas{display:block;margin:18px auto 0;}
</style>
</head>
<body>

<div class="petals" id="petals"></div>

<div class="hero">
  <div class="hero-small">✦ Dia das Mães ✦</div>
  <div class="hero-big">Descubra a surpresa!</div>
  <div class="hero-sub">Responda as charadas para revelar 💗</div>
</div>

<div class="progress-row" id="progressRow"></div>

<div class="card" id="charadaCard">
  <div class="charada-num" id="charadaNum"></div>
  <div class="charada-text" id="charadaText"></div>
  <div class="options" id="options"></div>
  <div class="feedback" id="feedback"></div>
  <button class="next-btn" id="nextBtn" onclick="next()">Próxima ➜</button>
</div>

<div class="surprise" id="surprise">
  <div class="score-badge" id="scoreBadge"></div>
  <div class="surprise-title">Feliz Dia das Mães! 🌹</div>
  <div class="surprise-msg">
    <p>
      Mãe, você é minha força, meu lar e minha maior inspiração.<br>
      Cada dia ao seu lado é um presente que nunca vou esquecer.<br>
      Obrigado por tudo — pelo amor, pelo colo e por ser perfeita do jeito que você é.
    </p>
    <div class="sign">Te amo infinito ❤</div>
  </div>
  <div class="hearts-row">
    <div class="heart-chip">Para sempre 🌸</div>
    <div class="heart-chip">Com amor 💕</div>
    <div class="heart-chip">Só você 🌹</div>
  </div>
  <canvas id="hc" width="320" height="300"></canvas>
</div>

<script>
var charadas = [
  {
    q: "Quem nunca dorme quando você está doente, esquece o próprio cansaço para cuidar de você e tem o abraço mais gostoso do mundo?",
    opts: ["Uma enfermeira", "Sua mãe", "Uma fada", "Uma amiga"],
    ans: 1,
    ok: "Exatamente! Ninguém cuida como ela 💗",
    no: "Pensa melhor... quem está sempre lá por você?"
  },
  {
    q: "Sou feita de beijos, conselhos e cafuné. Carrego você no coração desde antes de você nascer. Quem sou eu?",
    opts: ["A vovó", "A saudade", "A sua mãe", "O amor"],
    ans: 2,
    ok: "Isso mesmo! É ela, sempre ela 🌸",
    no: "Quase! Pensa em quem te carregou por 9 meses..."
  },
  {
    q: "Choro quando você chora, rio quando você ri, e mesmo quando brigo com você, faço isso por amor. O que sou eu?",
    opts: ["Um espelho", "O coração de mãe", "Uma saudade", "O tempo"],
    ans: 1,
    ok: "O coração de mãe é assim mesmo — sente tudo! 💓",
    no: "Pense no que une mãe e filho para sempre..."
  },
  {
    q: "Tenho mil formas: às vezes é um prato de comida, às vezes uma bronca, às vezes um silêncio que acolhe. O que sou eu?",
    opts: ["A paciência", "O amor de mãe", "A amizade", "A fé"],
    ans: 1,
    ok: "O amor de mãe tem mil formas e todas são perfeitas! 🌹",
    no: "Só uma coisa tem tantas formas de aparecer na vida de um filho..."
  },
  {
    q: "Sou a primeira voz que você ouviu, a primeira mão que te segurou, e a última pessoa no mundo que desistiria de você. Quem sou?",
    opts: ["Um anjo", "Sua mãe", "O destino", "Um sonho"],
    ans: 1,
    ok: "Ela esteve lá desde o primeiro segundo 💖",
    no: "Quem estava lá antes mesmo de você abrir os olhos?"
  }
];

var current = 0, answered = false, score = 0;

function buildProgress(){
  var row = document.getElementById('progressRow');
  row.innerHTML = '';
  charadas.forEach(function(_,i){
    var d = document.createElement('div');
    d.className = 'prog-dot' + (i < current ? ' done' : (i === current ? ' current' : ''));
    row.appendChild(d);
  });
}

function loadCharada(){
  answered = false;
  var c = charadas[current];
  document.getElementById('charadaNum').textContent = 'Charada ' + (current+1) + ' de ' + charadas.length;
  document.getElementById('charadaText').textContent = c.q;
  document.getElementById('feedback').textContent = '';
  document.getElementById('feedback').className = 'feedback';
  document.getElementById('nextBtn').style.display = 'none';

  var opts = document.getElementById('options');
  opts.innerHTML = '';
  c.opts.forEach(function(opt, i){
    var btn = document.createElement('button');
    btn.className = 'opt-btn';
    btn.textContent = opt;
    btn.onclick = function(){ answer(i); };
    opts.appendChild(btn);
  });
  buildProgress();
}

function answer(idx){
  if(answered) return;
  answered = true;
  var c = charadas[current];
  var btns = document.querySelectorAll('.opt-btn');
  btns.forEach(function(b){ b.disabled = true; });
  var fb = document.getElementById('feedback');
  if(idx === c.ans){ btns[idx].classList.add('correct'); fb.textContent = c.ok; fb.className = 'feedback ok'; score++; }
  else { btns[idx].classList.add('wrong'); btns[c.ans].classList.add('correct'); fb.textContent = c.no; fb.className = 'feedback no'; }
  var nb = document.getElementById('nextBtn');
  nb.style.display = 'inline-block';
  nb.textContent = current >= charadas.length - 1 ? '🎁 Ver a surpresa!' : 'Próxima ➜';
}

function next(){
  current++;
  if(current >= charadas.length){ showSurprise(); return; }
  var card = document.getElementById('charadaCard');
  card.style.animation = 'none';
  void card.offsetWidth;
  card.style.animation = 'slideIn .4s ease';
  loadCharada();
}

function showSurprise(){
  document.getElementById('charadaCard').style.display = 'none';
  document.getElementById('progressRow').style.display = 'none';
  var s = document.getElementById('surprise');
  s.classList.add('visible');
  document.getElementById('scoreBadge').textContent = 'Você acertou ' + score + ' de ' + charadas.length + ' charadas! 🎉';
  startHeartCanvas();
  launchConfetti();
}

function startHeartCanvas(){
  var cv = document.getElementById('hc');
  var ctx = cv.getContext('2d');
  var W=320,H=300,PHRASE="I Love You  ",OX=W/2,OY=H/2+10;
  function hx(t){return 16*Math.pow(Math.sin(t),3);}
  function hy(t){return -(13*Math.cos(t)-5*Math.cos(2*t)-2*Math.cos(3*t)-Math.cos(4*t));}
  var LAYERS=[{scale:11,fs:8,c:'#e8175a'},{scale:7.8,fs:6.5,c:'#c8103a'},{scale:4.5,fs:5.5,c:'#ff6b8a'}];
  var N=2400;
  function buildC(sc){
    var pts=[];
    for(var i=0;i<=N;i++){var t=(i/N)*2*Math.PI;pts.push({x:OX+hx(t)*sc,y:OY+hy(t)*sc});}
    var segs=[],tot=0,cum=[0];
    for(var i=0;i<N;i++){var dx=pts[i+1].x-pts[i].x,dy=pts[i+1].y-pts[i].y,d=Math.sqrt(dx*dx+dy*dy);segs.push(d);tot+=d;cum.push(cum[i]+d);}
    return{pts,segs,tot,cum};
  }
  function getPt(c,s){
    s=((s%c.tot)+c.tot)%c.tot;
    var lo=0,hi=c.segs.length-1;
    while(lo<hi){var m=(lo+hi)>>1;if(c.cum[m+1]<s)lo=m+1;else hi=m;}
    var f=c.segs[lo]>0?(s-c.cum[lo])/c.segs[lo]:0;
    var p1=c.pts[lo],p2=c.pts[lo+1]||c.pts[lo];
    return{x:p1.x+f*(p2.x-p1.x),y:p1.y+f*(p2.y-p1.y),angle:Math.atan2(p2.y-p1.y,p2.x-p1.x)};
  }
  var curves=LAYERS.map(function(l){return buildC(l.scale);});
  var layerData=LAYERS.map(function(layer,li){
    var curve=curves[li];
    ctx.font='bold '+layer.fs+'px Georgia,serif';
    var cw=PHRASE.split('').map(function(c){return{ch:c,w:ctx.measureText(c).width};});
    var pw=cw.reduce(function(a,b){return a+b.w;},0);
    var count=Math.max(1,Math.floor(curve.tot/pw));
    var spacing=curve.tot/count;
    var all=[];
    for(var r=0;r<count;r++){
      var base=r*spacing,local=0;
      for(var ci=0;ci<cw.length;ci++){
        var s=base+local+cw[ci].w/2;
        all.push({s,ch:cw[ci].ch,color:layer.c});
        local+=cw[ci].w;
      }
    }
    return{all,count,fs:layer.fs};
  });
  var totalG=layerData.reduce(function(a,l){return a+l.count;},0);
  function ease(t){return t<1?1-Math.pow(1-t,3):1;}
  var prog=0,DUR=2800,st=null,pausing=false;
  function draw(p){
    ctx.clearRect(0,0,W,H);
    var rem=Math.floor(ease(p)*totalG);
    LAYERS.forEach(function(layer,li){
      var ld=layerData[li];
      var vg=Math.min(rem,ld.count);rem-=vg;
      ctx.font='bold '+ld.fs+'px Georgia,serif';
      ctx.textAlign='center';ctx.textBaseline='middle';
      var vc=Math.floor(vg*(ld.all.length/ld.count));
      for(var i=0;i<Math.min(vc,ld.all.length);i++){
        var item=ld.all[i];
        var pt=getPt(curves[li],item.s);
        ctx.fillStyle=item.color;
        ctx.save();ctx.translate(pt.x,pt.y);ctx.rotate(pt.angle+Math.PI/2);
        ctx.fillText(item.ch,0,0);ctx.restore();
      }
    });
  }
  function loop(ts){
    if(!st)st=ts;
    if(!pausing){
      prog=Math.min((ts-st)/DUR,1);draw(prog);
      if(prog>=1){pausing=true;draw(1);setTimeout(function(){st=null;prog=0;pausing=false;requestAnimationFrame(loop);},2500);return;}
    }
    requestAnimationFrame(loop);
  }
  requestAnimationFrame(loop);
}

function launchConfetti(){
  var el=document.getElementById('petals');
  var extra=['🎉','🎊','💖','🌸','🌺','🌷','✨','💝','🥰'];
  for(var i=0;i<28;i++){
    var p=document.createElement('span');
    p.className='petal';
    p.textContent=extra[i%extra.length];
    p.style.left=(Math.random()*100)+'%';
    p.style.animationDuration=(2+Math.random()*4)+'s';
    p.style.animationDelay=(Math.random()*3)+'s';
    p.style.fontSize=(14+Math.random()*16)+'px';
    el.appendChild(p);
  }
}

// petals iniciais
(function(){
  var el=document.getElementById('petals');
  var arr=['🌸','🌺','🌷','💗','💕','🌹'];
  for(var i=0;i<18;i++){
    var p=document.createElement('span');
    p.className='petal';
    p.textContent=arr[i%arr.length];
    p.style.left=(Math.random()*100)+'%';
    p.style.animationDuration=(5+Math.random()*7)+'s';
    p.style.animationDelay=(Math.random()*9)+'s';
    p.style.fontSize=(10+Math.random()*12)+'px';
    el.appendChild(p);
  }
})();

loadCharada();
</script>
</body>
</html>

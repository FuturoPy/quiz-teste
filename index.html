<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Quiz Escolar 🎓</title>
<style>
body { margin:0; padding:0; font-family:"Comic Sans MS", Arial, sans-serif; background-color:black; overflow:hidden; }

/* Tela Inicial */
#tela-inicial {
  position: fixed; top:0; left:0; width:100%; height:100%;
  background-image:url('https://uploads.onecompiler.io/444jywmud/444jyqxv3/inico%20de%20tela.png');
  background-size:cover; background-position:center; z-index:0; transition:opacity 1s ease;
}
#particles { position: fixed; top:0; left:0; width:100%; height:100%; pointer-events:none; z-index:1; }
#start-btn {
  position: fixed; top:55%; left:50%; transform:translate(-50%,-50%);
  font-size:36px; font-weight:bold; color:white; background-color: rgba(0,0,0,0.6);
  border:none; border-radius:15px; padding:20px 60px; cursor:pointer; transition:0.3s; z-index:10;
}
#start-btn:hover{ color:#00ffff; }

/* Quiz */
.quiz-container {
  display:none; width:100%; height:100vh;
  background-image:url('https://uploads.onecompiler.io/444jywmud/444jyqxv3/sala%20de%20aulas.png');
  background-size:cover; background-position:center; display:flex; justify-content:center; align-items:center; opacity:0; transition:opacity 1s ease;
}
.area-jogo { display:flex; justify-content:center; align-items:center; gap:50px; }
.professor { width:350px; height:450px; background-size:contain; background-repeat:no-repeat; background-position:bottom center; animation: idle 3s ease-in-out infinite; display:none; }
@keyframes idle{0%{transform:translateY(0);}50%{transform:translateY(-4px);}100%{transform:translateY(0);} }
@keyframes shake{0%{transform:translateX(0)}20%{transform:translateX(-8px)}40%{transform:translateX(8px)}60%{transform:translateX(-6px)}80%{transform:translateX(6px)}100%{transform:translateX(0)}}
@keyframes jump{0%{transform:translateY(0)}30%{transform:translateY(-18px)}60%{transform:translateY(0)}100%{transform:translateY(0)}}

/* Quadro */
.quadro-fundo { width:600px; height:400px; display:flex; flex-direction:column; justify-content:center; align-items:center; text-align:center; color:white; text-shadow:2px 2px 4px black,0 0 3px white; padding:20px; }
#question { font-size:22px; margin-bottom:20px; }
#answers { display:flex; flex-direction:column; gap:12px; width:100%; align-items:center; justify-content:center; }
#answers button { background-color:transparent; color:white; border:2px solid #ffffff30; border-radius:10px; padding:12px 20px; font-size:18px; cursor:pointer; text-align:center; transition:0.3s; width:80%; }
#answers button:hover { background-color:rgba(255,255,255,0.2); transform:scale(1.05);}
.feedback { font-size:22px; font-weight:bold; margin-top:15px; text-shadow:1px 1px 2px black,0 0 3px white;}
.correct { color:#00ff99; }
.wrong { color:#ff9999; }

/* Professor Login */
#professor-login { position:fixed; top:10px; left:50%; transform:translateX(-50%); background:rgba(0,0,0,0.7); color:white; padding:15px; border-radius:15px; z-index:20; }
#cadastro-perguntas { display:none; position:fixed; top:10px; left:50%; transform:translateX(-50%); background:rgba(0,0,0,0.7); color:white; padding:20px; border-radius:15px; z-index:20; max-height:60vh; overflow-y:auto; }
#cadastro-perguntas input, #cadastro-perguntas select { margin:5px; padding:5px; border-radius:5px; border:none; }
#cadastro-perguntas button { margin-top:5px; padding:5px 10px; border-radius:10px; cursor:pointer; }
</style>
</head>
<body>

<div id="tela-inicial"><canvas id="particles"></canvas></div>
<button id="start-btn">START</button>

<!-- Login professor -->
<div id="professor-login">
  <input type="password" id="senha-professor" placeholder="Senha professor"/>
  <button onclick="entrarProfessor()">Entrar</button>
</div>

<!-- Cadastro de perguntas -->
<div id="cadastro-perguntas">
  <h3>Adicionar Pergunta</h3>
  <input type="text" id="nova-pergunta" placeholder="Digite a pergunta"/>
  <input type="text" id="alt1" placeholder="Alternativa 1"/>
  <input type="text" id="alt2" placeholder="Alternativa 2"/>
  <input type="text" id="alt3" placeholder="Alternativa 3"/>
  <select id="certa">
    <option value="0">Alternativa 1</option>
    <option value="1">Alternativa 2</option>
    <option value="2">Alternativa 3</option>
  </select>
  <button onclick="adicionarPergunta()">Adicionar Pergunta</button>
</div>

<div class="quiz-container" id="quiz-container">
  <div class="area-jogo">
    <div class="professor" id="professor"></div>
    <div class="quadro-fundo">
      <div id="question"></div>
      <div id="answers"></div>
      <div id="feedback" class="feedback"></div>
    </div>
  </div>
</div>

<script>
// PARTICULAS
const canvas = document.getElementById("particles"), ctx = canvas.getContext("2d");
canvas.width = window.innerWidth; canvas.height = window.innerHeight;
window.addEventListener('resize',()=>{canvas.width=window.innerWidth; canvas.height=window.innerHeight;});
let mouse={x:null,y:null}; window.addEventListener('mousemove',e=>{mouse.x=e.x; mouse.y=e.y;});

class Particle{
  constructor(){
    this.x=Math.random()*canvas.width; this.y=Math.random()*canvas.height;
    this.size=Math.random()*2+1; this.baseSize=this.size;
    this.speedX=(Math.random()-0.5)*0.5; this.speedY=(Math.random()-0.5)*0.5;
    this.opacity=Math.random()*0.7+0.3; this.baseOpacity=this.opacity;
  }
  update(){
    this.x+=this.speedX; this.y+=this.speedY;
    if(this.x<0||this.x>canvas.width) this.speedX*=-1;
    if(this.y<0||this.y>canvas.height) this.speedY*=-1;
    if(mouse.x && mouse.y){
      let dx=mouse.x-this.x, dy=mouse.y-this.y, dist=Math.sqrt(dx*dx+dy*dy);
      if(dist<100){ this.size=this.baseSize+(100-dist)/30; this.opacity=Math.min(1,this.baseOpacity+(100-dist)/100);}
      else{this.size=this.baseSize; this.opacity=this.baseOpacity;}
    }
  }
  draw(){ ctx.fillStyle=`rgba(255,255,150,${this.opacity})`; ctx.beginPath(); ctx.arc(this.x,this.y,this.size,0,Math.PI*2); ctx.fill();}
}
const particlesArray=[]; for(let i=0;i<80;i++) particlesArray.push(new Particle());
function animateParticles(){ctx.clearRect(0,0,canvas.width,canvas.height); particlesArray.forEach(p=>{p.update();p.draw();}); requestAnimationFrame(animateParticles);}
animateParticles();

// PROFESSORA
let imgFrames=[
  "https://uploads.onecompiler.io/444jywmud/444jyqxv3/professora%20frame%201.png",
  "https://uploads.onecompiler.io/444jywmud/444jyqxv3/professora%20frame%202.png",
  "https://uploads.onecompiler.io/444jywmud/444jyqxv3/professora%20frame%203.png"
];
let imgCerta="https://uploads.onecompiler.io/444jywmud/444jyqxv3/joinhaa.png";
let imgErrada="https://uploads.onecompiler.io/444jywmud/444jyqxv3/errada.png";

let perguntas=[], indice=0, pontuacao=0, escreverVelocidade=100;
let professorEl=document.getElementById("professor"); let feedback=document.getElementById("feedback"); 
let quizContainer=document.getElementById("quiz-container"); let telaInicial=document.getElementById("tela-inicial"); 
let startBtn=document.getElementById("start-btn");

// Login professor
function entrarProfessor(){
  const senha=document.getElementById("senha-professor").value;
  if(senha==="1234"){ document.getElementById("cadastro-perguntas").style.display="block"; }
}

// Adicionar pergunta
function adicionarPergunta(){
  const pergunta=document.getElementById("nova-pergunta").value;
  const opcoes=[document.getElementById("alt1").value,document.getElementById("alt2").value,document.getElementById("alt3").value];
  const certa=parseInt(document.getElementById("certa").value);
  if(!pergunta||opcoes.some(o=>o==="")) return alert("Preencha todos os campos!");
  perguntas.push({pergunta,opcoes,certa});
  document.getElementById("nova-pergunta").value=""; document.getElementById("alt1").value=""; document.getElementById("alt2").value=""; document.getElementById("alt3").value="";
  atualizarCadastro();
}

// Atualiza cadastro
function atualizarCadastro(){
  const cadastro=document.getElementById("cadastro-perguntas");
  cadastro.querySelectorAll("div.pergunta-item")?.forEach(el=>el.remove());
  perguntas.forEach((p,i)=>{
    const div=document.createElement("div");
    div.className="pergunta-item";
    div.style.border="1px solid white"; div.style.margin="5px"; div.style.padding="5px"; div.style.borderRadius="5px";
    div.style.cursor="pointer";
    div.innerHTML=`<b>Pergunta ${i+1}:</b> ${p.pergunta}`;
    div.onclick=()=>{
      document.getElementById("nova-pergunta").value=p.pergunta;
      document.getElementById("alt1").value=p.opcoes[0];
      document.getElementById("alt2").value=p.opcoes[1];
      document.getElementById("alt3").value=p.opcoes[2];
      document.getElementById("certa").value=p.certa;
      perguntas.splice(i,1);
      atualizarCadastro();
    }
    cadastro.appendChild(div);
  });
}

// Start
startBtn.onclick=()=>{
  if(perguntas.length===0) return alert("Adicione pelo menos uma pergunta!");
  telaInicial.style.opacity=0; startBtn.style.opacity=0;
  setTimeout(()=>{
    telaInicial.style.display="none"; 
    document.getElementById("professor-login").style.display="none"; 
    document.getElementById("cadastro-perguntas").style.display="none";
    quizContainer.style.display="flex"; setTimeout(()=>quizContainer.style.opacity=1,50); professorEl.style.display="block"; mostrarPergunta();
  },1000);
};

// Perguntas
let escreverIntervalo=null;
async function escreverNoQuadro(elemento,texto){
  elemento.textContent=""; if(escreverIntervalo) clearInterval(escreverIntervalo);
  return new Promise(resolve=>{
    let i=0,frameIndex=0;
    escreverIntervalo=setInterval(()=>{
      elemento.textContent+=texto[i];
      professorEl.style.backgroundImage=`url(${imgFrames[frameIndex]})`;
      frameIndex=(frameIndex+1)%imgFrames.length; i++;
      if(i>=texto.length){ clearInterval(escreverIntervalo); escreverIntervalo=null; professorEl.style.backgroundImage=`url(${imgFrames[0]})`; resolve(); }
    },escreverVelocidade);
  });
}

async function mostrarPergunta(){
  const q=perguntas[indice]; const respostasDiv=document.getElementById("answers"); respostasDiv.innerHTML=""; feedback.textContent="";
  await escreverNoQuadro(document.getElementById("question"),q.pergunta);
  q.opcoes.forEach((opcao,i)=>{ const btn=document.createElement("button"); btn.textContent=opcao; btn.onclick=()=>checkAnswer(i===q.certa); respostasDiv.appendChild(btn); });
}

// Corrigido: professora sem glitch
function checkAnswer(certa){
  professorEl.style.animation = ""; // remove animação antiga
  if(certa){
    pontuacao++;
    feedback.textContent="Muito bem!";
    feedback.className="feedback correct";
    professorEl.style.backgroundImage=`url(${imgCerta})`;
    professorEl.style.animation="jump 0.6s";
    setTimeout(()=>{
      professorEl.style.animation="idle 3s ease-in-out infinite";
      professorEl.style.backgroundImage=`url(${imgFrames[0]})`;
      indice++;
      if(indice<perguntas.length) mostrarPergunta(); else mostrarFim();
    },600);
  } else {
    feedback.textContent="Tente novamente!";
    feedback.className="feedback wrong";
    professorEl.style.backgroundImage=`url(${imgErrada})`;
    professorEl.style.animation="shake 0.5s";
    setTimeout(()=>{
      professorEl.style.animation="idle 3s ease-in-out infinite";
      professorEl.style.backgroundImage=`url(${imgFrames[0]})`;
      indice++;
      if(indice<perguntas.length) mostrarPergunta(); else mostrarFim();
    },500);
  }
}

// Mostrar fim
function mostrarFim(){
  quizContainer.style.display = "none";

  if(pontuacao === perguntas.length){
    // Tela de conquista
    let fimDiv = document.createElement("div");
    fimDiv.style.position = "fixed";
    fimDiv.style.top = "0";
    fimDiv.style.left = "0";
    fimDiv.style.width = "100%";
    fimDiv.style.height = "100%";
    fimDiv.style.display = "flex";
    fimDiv.style.flexDirection = "column";
    fimDiv.style.justifyContent = "center";
    fimDiv.style.alignItems = "center";
    fimDiv.style.backgroundImage = "url('https://uploads.onecompiler.io/444jywmud/444jyqxv3/tela%20final.png')";
    fimDiv.style.backgroundSize = "cover";
    fimDiv.style.backgroundPosition = "center";
    fimDiv.style.color = "white";
    fimDiv.style.fontSize = "28px";
    fimDiv.id = "tela-fim";

    fimDiv.innerHTML = "Parabéns! Você desbloqueou uma conquista: <b>Nota 10</b><br>";

    let imgConquista = document.createElement("img");
    imgConquista.src = "https://uploads.onecompiler.io/444jywmud/444jyqxv3/Captura%20de%20tela%202025-11-14%20003933.png";
    imgConquista.style.width = "200px";
    imgConquista.style.marginTop = "15px";
    fimDiv.appendChild(imgConquista);

    let btnVoltar = document.createElement("img");
    btnVoltar.src = "https://uploads.onecompiler.io/444jywmud/444jyqxv3/botao%20de%20voltar.png";
    btnVoltar.style.width = "200px";
    btnVoltar.style.cursor = "pointer";
    btnVoltar.style.marginTop = "50px";
    btnVoltar.onclick = () => {
      fimDiv.remove();
      resetarJogo();
    };
    fimDiv.appendChild(btnVoltar);

    document.body.appendChild(fimDiv);
  } else {
    // Se não acertou tudo, volta direto para a tela inicial
    resetarJogo();
  }
}

// Função para resetar o jogo e voltar para a tela inicial
function resetarJogo(){
  telaInicial.style.display = "block";
  telaInicial.style.opacity = 1;
  startBtn.style.opacity = 1;

  indice = 0;
  pontuacao = 0;

  professorEl.style.display = "block";
  professorEl.style.backgroundImage = `url(${imgFrames[0]})`;
  professorEl.style.animation = "idle 3s ease-in-out infinite";

  document.getElementById("question").textContent = "";
  document.getElementById("answers").innerHTML = "";
  feedback.textContent = "";

  // Remove qualquer tela de fim que esteja no DOM
  const fimExistente = document.getElementById("tela-fim");
  if(fimExistente) fimExistente.remove();
}

// ESC para sair do modo professor
document.addEventListener('keydown', (e) => {
    if (e.key === 'Escape') {
        const cadastro = document.getElementById("cadastro-perguntas");
        const login = document.getElementById("professor-login");
        const senhaInput = document.getElementById("senha-professor");

        cadastro.style.display = "none";
        login.style.display = "block";
        senhaInput.value = "";
    }
});
</script>
</body>
</html>

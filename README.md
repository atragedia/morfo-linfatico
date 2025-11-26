<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simulado – Sistema Linfático (15 questões)</title>
<style>
body {font-family:'Segoe UI',Arial,sans-serif;background:#f6f8fa;color:#222;margin:0;padding:0;}
.container {max-width:820px;margin:auto;background:#fff;box-shadow:0 2px 14px rgba(0,0,0,0.08);border-radius:10px;padding:30px 24px;margin-top:36px;}
h1{text-align:center;color:#117a8b;}
button{background:#117a8b;color:#fff;border:none;padding:12px 24px;border-radius:7px;font-size:1.1rem;margin:16px auto;display:block;cursor:pointer;transition:background 0.2s;}
button:hover{background:#0e606b;}
.question-text{font-size:1.18rem;margin-bottom:18px;color:#1b4f72;}
.options label{display:block;background:#f4f6f9;padding:12px 14px;margin-bottom:10px;border-radius:6px;cursor:pointer;}
.feedback{margin-top:14px;font-weight:bold;border-radius:6px;padding:12px;display:none;}
.correct{background:#e9f7ef;color:#155724;border:1px solid #c3e6cb;}
.incorrect{background:#fdecea;color:#7a1f1f;border:1px solid #f5c6cb;}
.result-item{background:#f9f9f9;padding:10px;border-radius:6px;margin-bottom:10px;}
</style>
</head>
<body>
<div class="container" id="main">
  <h1>Simulado – Sistema Linfático (15 questões)</h1>
  <button id="start">Iniciar Avaliação</button>
</div>
<script>
const data = [
{
text:`1. Paciente com insuficiência cardíaca congestiva apresenta edema periférico persistente, mesmo após uso de diuréticos. Pergunta: Qual função do sistema linfático está diretamente relacionada à resolução desse quadro?`,
options:[
{text:"Transporte de lipídios e vitaminas lipossolúveis",value:"a"},
{text:"Resposta imune contra microrganismos",value:"b"},
{text:"Drenagem do excesso de líquido intersticial para o sangue",value:"c"},
{text:"Produção de células sanguíneas na medula óssea",value:"d"}
],
correct:"c",
explanation:"O sistema linfático recolhe o excesso de líquido intersticial e o devolve à circulação venosa; quando essa drenagem falha, ocorre edema."
},
{
text:`2. Paciente com síndrome de má absorção intestinal apresenta deficiência de vitaminas A, D, E e K. Pergunta: Qual estrutura linfática é responsável por esse transporte?`,
options:[
{text:"Linfonodos mesentéricos",value:"a"},
{text:"Lacteais (capilares linfáticos intestinais)",value:"b"},
{text:"Troncos lombares",value:"c"},
{text:"Baço",value:"d"}
],
correct:"b",
explanation:"Os lacteais absorvem lipídios e vitaminas lipossolúveis na forma de quilomícrons, essenciais para sua distribuição pelo corpo."
},
{
text:`3. Paciente apresenta linfadenopatia cervical dolorosa após infecção bacteriana. Pergunta: Qual é a principal função dos linfonodos nesse contexto?`,
options:[
{text:"Produzir hemácias e plaquetas",value:"a"},
{text:"Filtrar a linfa e ativar resposta imune específica",value:"b"},
{text:"Regular a pressão osmótica do plasma",value:"c"},
{text:"Transportar lipídios absorvidos no intestino",value:"d"}
],
correct:"b",
explanation:"Os linfonodos filtram a linfa, retêm patógenos e ativam linfócitos T e B para combater infecções."
},
{
text:`4. Paciente apresenta obstrução do ducto torácico após trauma abdominal. Pergunta: Qual região do corpo terá maior comprometimento na drenagem linfática?`,
options:[
{text:"Apenas membros inferiores",value:"a"},
{text:"Lado superior direito do corpo",value:"b"},
{text:"Lado superior esquerdo e todo corpo abaixo das costelas",value:"c"},
{text:"Região abdominal isolada",value:"d"}
],
correct:"c",
explanation:"O ducto torácico drena todo o corpo, exceto o quadrante superior direito; sua obstrução compromete ampla drenagem."
},
{
text:`5. Paciente submetido à mastectomia radical apresenta linfedema em membro superior direito. Pergunta: Qual ducto linfático está mais provavelmente comprometido?`,
options:[
{text:"Ducto torácico",value:"a"},
{text:"Ducto linfático direito",value:"b"},
{text:"Tronco intestinal",value:"c"},
{text:"Tronco broncomediastinal esquerdo",value:"d"}
],
correct:"b",
explanation:"O ducto linfático direito drena o membro superior direito, parte direita do tórax e cabeça."
},
{
text:`6. Paciente com imunodeficiência congênita apresenta falha na maturação de linfócitos T. Pergunta: Qual órgão linfático primário está comprometido?`,
options:[
{text:"Baço",value:"a"},
{text:"Timo",value:"b"},
{text:"Linfonodos",value:"c"},
{text:"Medula óssea vermelha",value:"d"}
],
correct:"b",
explanation:"O timo é o órgão onde linfócitos T amadurecem e se tornam imunocompetentes."
},
{
text:`7. Paciente apresenta esplenomegalia após infecção sistêmica prolongada. Pergunta: Qual função do baço está mais relacionada a esse achado?`,
options:[
{text:"Produção de hemácias em adultos",value:"a"},
{text:"Filtragem do sangue e ativação da resposta imune",value:"b"},
{text:"Transporte de lipídios da dieta",value:"c"},
{text:"Maturação de linfócitos T",value:"d"}
],
correct:"b",
explanation:"O baço filtra o sangue, fagocita patógenos e ativa linfócitos durante infecções."
},
{
text:`8. Paciente em quimioterapia apresenta pancitopenia. Pergunta: Qual órgão linfático primário responsável pela formação de células sanguíneas está comprometido?`,
options:[
{text:"Baço",value:"a"},
{text:"Medula óssea vermelha",value:"b"},
{text:"Timo",value:"c"},
{text:"Linfonodos",value:"d"}
],
correct:"b",
explanation:"A medula óssea vermelha produz hemácias, leucócitos e plaquetas; sua supressão causa pancitopenia."
},
{
text:`9. Paciente apresenta linfoma intestinal com acometimento de placas de Peyer. Pergunta: Em qual região anatômica essas estruturas estão localizadas?`,
options:[
{text:"Estômago",value:"a"},
{text:"Intestino delgado",value:"b"},
{text:"Intestino grosso",value:"c"},
{text:"Fígado",value:"d"}
],
correct:"b",
explanation:"As placas de Peyer são aglomerados linfáticos presentes no íleo, porção do intestino delgado."
},
{
text:`10. Paciente apresenta sangramento prolongado associado à deficiência de proteínas plasmáticas. Qual proteína plasmática está diretamente envolvida na coagulação?`,
options:[
{text:"Albumina",value:"a"},
{text:"Globulina",value:"b"},
{text:"Fibrinogênio",value:"c"},
{text:"Hemoglobina",value:"d"}
],
correct:"c",
explanation:"O fibrinogênio é convertido em fibrina para formar a rede do coágulo sanguíneo."
},
{
text:`11. Paciente apresenta hipoproteinemia grave por doença hepática crônica. Qual proteína plasmática é mais afetada e responsável pela manutenção da pressão coloidosmótica?`,
options:[
{text:"Albumina",value:"a"},
{text:"Globulina",value:"b"},
{text:"Fibrinogênio",value:"c"},
{text:"Imunoglobulina G",value:"d"}
],
correct:"a",
explanation:"A albumina exerce papel crucial na retenção de líquido dentro dos vasos sanguíneos."
},
{
text:`12. Paciente apresenta anemia grave com redução de eritrócitos, mas leucócitos e plaquetas preservados. Qual célula progenitora está comprometida?`,
options:[
{text:"ECFC (eritrocítica)",value:"a"},
{text:"LCFC (linfocítica)",value:"b"},
{text:"MCFC (monocítica)",value:"c"},
{text:"GCFC (granulocítica)",value:"d"}
],
correct:"a",
explanation:"A progenitora eritrocítica gera hemácias; sua falha reduz apenas eritrócitos."
},
{
text:`13. Paciente apresenta leucocitose com predomínio de neutrófilos após infecção bacteriana. Qual célula precursora está envolvida?`,
options:[
{text:"Linfoblasto",value:"a"},
{text:"Mielócito neutrófilo",value:"b"},
{text:"Eritroblasto",value:"c"},
{text:"Megacarioblasto",value:"d"}
],
correct:"b",
explanation:"O mielócito neutrofílico é estágio intermediário na formação dos neutrófilos maduros."
},
{
text:`14. Paciente apresenta eosinofilia após quadro de parasitose intestinal. Pergunta: Qual célula progenitora da medula óssea está envolvida?`,
options:[
{text:"EoCFC (eosinofílica)",value:"a"},
{text:"Célula basofílica formadora de colônia",value:"b"},
{text:"Célula linfocítica formadora de colônia",value:"c"},
{text:"Célula monocítica formadora de colônia",value:"d"}
],
correct:"a",
explanation:"A EoCFC é a progenitora responsável pela formação de eosinófilos, que aumentam em infecções parasitárias."
},
{
text:`15. Paciente apresenta imunodeficiência humoral com baixa produção de anticorpos. Pergunta: Qual componente plasmático está diretamente relacionado à neutralização de antígenos?`,
options:[
{text:"Albumina",value:"a"},
{text:"Globulinas (imunoglobulinas)",value:"b"},
{text:"Fibrinogênio",value:"c"},
{text:"Hemoglobina",value:"d"}
],
correct:"b",
explanation:"As globulinas (especialmente IgG, IgA, IgM) são anticorpos responsáveis pela neutralização de patógenos."
}
];
const pointsPerQuestion = 2;
let current = 0, score = 0, userAnswers = [];

const main = document.getElementById("main");
const start = document.getElementById("start");

start.addEventListener("click", () => showQuestion());

function showQuestion() {
  const q = data[current];
  main.innerHTML = `
    <div class="question-text"><b>QUESTÃO ${current+1} (${pointsPerQuestion} pts):</b><br>${q.text}</div>
    <div class="options">
      ${q.options.map(o => `<label><input type="radio" name="opt" value="${o.value}"> ${o.text}</label>`).join("")}
    </div>
    <button id="check" class="btn-check">Verificar</button>
    <div id="fb" class="feedback"></div>
    <p class="small">Questão ${current+1} de ${data.length}</p>
  `;
  document.getElementById("check").addEventListener("click", () => check(q));
}

function check(q) {
  const selected = document.querySelector('input[name="opt"]:checked');
  const fb = document.getElementById("fb");

  if (!selected) {
    fb.textContent = "Selecione uma opção!";
    fb.className = "feedback incorrect";
    fb.style.display = "block";
    return;
  }

  const chosen = selected.value;

  userAnswers.push({
    question: q.text,
    chosen,
    correct: q.correct,
    explanation: q.explanation
  });

  if (chosen === q.correct) {
    score += pointsPerQuestion;
    fb.className = "feedback correct";
    fb.innerHTML = "✅ Correto! " + q.explanation;
  } else {
    fb.className = "feedback incorrect";
    fb.innerHTML = "❌ Incorreto. " + q.explanation;
  }

  fb.style.display = "block";

  setTimeout(() => {
    current++;
    current < data.length ? showQuestion() : showResult();
  }, 1100);
}

function showResult() {
  let html = `
    <h2 style="text-align:center;color:#117a8b">Resultado Final</h2>
    <p style="text-align:center;font-size:1.1rem">Sua nota: <b>${score} / ${data.length * pointsPerQuestion}</b></p>
    <div class="result-list">
  `;

  userAnswers.forEach((a, i) => {
    html += `
      <div class="result-item">
        <b>${i+1}. ${a.question}</b><br>
        ${a.chosen === a.correct
          ? `<span style="color:green">✔ Você acertou (alternativa ${a.correct.toUpperCase()}).</span>`
          : `<span style="color:red">✘ Você marcou ${a.chosen.toUpperCase()}, o correto era ${a.correct.toUpperCase()}.</span>`}
        <br><em>Explicação:</em> ${a.explanation}
      </div>
    `;
  });

  html += `</div>
    <button onclick="location.reload()" style="display:block;margin:16px auto;padding:10px 16px;border-radius:8px;background:#117a8b;color:#fff;border:none;cursor:pointer">
      Refazer Avaliação
    </button>`;

  main.innerHTML = html;
}
</script>
</body>
</html>

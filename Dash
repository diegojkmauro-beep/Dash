<!doctype html>
<html lang="pt-br">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <title>Dashboard Escolar – 6º Ano (Plano de Estudos Completo)</title>
  <style>
    :root{
      --bg:#0f1220; --panel:#151a2e; --soft:#1b2140; --muted:#a6b0cf; --text:#e7ecff; --brand:#6ea8fe;
      --ok:#7ee787; --warn:#ffd175; --bad:#ff8182; --card:#12162b; --accent:#8b9dff;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{margin:0;background:linear-gradient(180deg,var(--bg),#0b0e1a);color:var(--text);font:14px/1.4 system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial}
    a{color:var(--brand);text-decoration:none}
    .app{display:grid;grid-template-columns:280px 1fr;min-height:100vh}
    .sidebar{background:linear-gradient(180deg,var(--panel),#0f1330);padding:16px;border-right:1px solid #21264a}
    .logo{display:flex;align-items:center;gap:8px;font-weight:700}
    .logo .dot{width:10px;height:10px;border-radius:50%;background:var(--brand);box-shadow:0 0 16px var(--brand)}
    .search{margin:14px 0 8px}
    .search input{width:100%;padding:10px 12px;border-radius:10px;border:1px solid #2a2f57;background:#0d1130;color:var(--text)}
    .subjects{display:flex;flex-direction:column;gap:8px;margin-top:8px;max-height:calc(100vh - 180px);overflow:auto;padding-right:4px}
    .subj{padding:10px 12px;border-radius:12px;background:var(--soft);border:1px solid #232a52;cursor:pointer;display:flex;align-items:center;justify-content:space-between;gap:8px}
    .subj.active{outline:2px solid var(--brand);background:#13183a}
    .subj small{color:var(--muted)}
    .main{padding:18px 22px}
    .header{display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap}
    .title{font-size:20px;font-weight:700}
    .tabs{display:flex;gap:8px;flex-wrap:wrap}
    .tab{padding:8px 12px;border:1px solid #2a2f57;border-radius:10px;background:#0e1331;cursor:pointer;color:var(--muted)}
    .tab.active{background:var(--soft);color:var(--text);border-color:#3a4180}
    .grid{display:grid;gap:12px}
    .cards-3{grid-template-columns:repeat(3,minmax(0,1fr))}
    @media(max-width:1000px){.app{grid-template-columns:1fr}.sidebar{position:sticky;top:0}.cards-3{grid-template-columns:1fr}}
    .card{background:linear-gradient(180deg,#121738,#0b1030);border:1px solid #27306a;border-radius:16px;padding:14px}
    .card h3{margin:0 0 10px 0;font-size:16px}
    .muted{color:var(--muted)}
    .row{display:flex;align-items:center;justify-content:space-between;gap:8px}
    .pill{display:inline-flex;align-items:center;gap:6px;padding:2px 8px;border-radius:999px;background:#0e1436;border:1px solid #2e3675;color:var(--muted);font-size:12px}
    .btn{background:var(--brand);color:#04102b;border:none;border-radius:10px;padding:10px 12px;font-weight:700;cursor:pointer}
    .btn.secondary{background:#10163b;color:var(--text);border:1px solid #2a2f57}
    .btn:disabled{opacity:.6;cursor:not-allowed}
    .list{display:flex;flex-direction:column;gap:8px}
    .lesson{padding:10px;border-radius:12px;background:#0f1536;border:1px solid #2a2f57;cursor:pointer}
    .lesson .small{font-size:12px;color:var(--muted)}
    .lesson.active{outline:2px solid var(--accent);background:#0f1440}
    .split{display:grid;grid-template-columns:1.1fr .9fr;gap:12px}
    @media(max-width:1200px){.split{grid-template-columns:1fr}}
    .mm-root{display:flex;flex-wrap:wrap;gap:10px}
    .mm-node{background:#0f1438;border:1px dashed #35408a;padding:10px;border-radius:12px;min-width:180px}
    .mm-node b{display:block;margin-bottom:6px}
    .quiz{display:flex;flex-direction:column;gap:10px}
    .q{padding:12px;border:1px solid #334080;background:#0d1235;border-radius:12px}
    .q h4{margin:0 0 8px}
    .choices{display:flex;flex-direction:column;gap:6px;margin-top:4px}
    .choices label{display:flex;gap:8px;align-items:flex-start}
    .kpi{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:10px}
    .k{padding:10px;border-radius:12px;background:#0c1232;border:1px solid #2a2f57}
    .k b{font-size:18px}
    .footer{margin-top:10px;display:flex;gap:8px;flex-wrap:wrap}
    .hr{height:1px;background:#2a2f57;margin:12px 0;border:none}
    .notice{font-size:12px;color:var(--muted)}
  </style>
</head>
<body>
<div class="app">
  <aside class="sidebar">
    <div class="logo"><span class="dot"></span> <span>Dashboard 6º Ano</span></div>
    <div class="search"><input id="search" placeholder="Buscar matéria ou aula..."/></div>
    <div class="subjects" id="subjectList"></div>
    <div style="margin-top:10px" class="notice">Versão HTML offline. Para publicar, suba este arquivo em um serviço como GitHub Pages, Netlify ou Vercel.</div>
  </aside>

  <main class="main">
    <div class="header">
      <div class="title">Plano de Estudos – 6º Ano</div>
      <div class="tabs">
        <button class="tab active" data-tab="plano">Plano</button>
        <button class="tab" data-tab="simulado">Simulado</button>
        <button class="tab" data-tab="mapa">Mapa Mental</button>
      </div>
    </div>

    <div class="hr"></div>

    <section id="content">
      <!-- Conteúdo dinâmico -->
    </section>
  </main>
</div>

<script>
// -----------------------------
// DADOS – 7 disciplinas × 5 aulas
// Cada aula: summary[], mindmap[], questionBank[] (parcial, engine completa 20)
// -----------------------------
const CURRICULUM = [
  {
    id: "portugues",
    nome: "Língua Portuguesa",
    aulas: [
      {
        titulo: "Leitura e Interpretação de Crônicas",
        summary: [
          "Crônica é um texto curto sobre situações do cotidiano.",
          "Linguagem simples, muitas vezes com humor e reflexão.",
          "Observe narrador, acontecimento e sentimento do autor."
        ],
        mindmap: [
          {titulo:"Crônica", itens:["Cotidiano","Linguagem simples","Humor/Reflexão","Narrador","Interpretação: quem/que/sentimento"]}
        ],
        questionBank: [
          {type:"mcq", prompt:"O que caracteriza uma crônica?", choices:["Relato científico","Texto cotidiano e breve","Manual de instruções","Romance longo"], answer:1},
          {type:"tf", prompt:"A crônica pode misturar humor e crítica.", answer:true},
          {type:"open", prompt:"Identifique o narrador em uma crônica lida em aula."},
          {type:"open", prompt:"Escreva o tema central de uma crônica sobre o ônibus lotado."},
          {type:"mcq", prompt:"A linguagem típica da crônica é:", choices:["Coloquial","Formal científica","Poética clássica","Técnica"], answer:0},
          {type:"tf", prompt:"Crônicas nunca trazem reflexões.", answer:false},
          {type:"open", prompt:"Explique como o sentimento do autor aparece na crônica."},
          {type:"mcq", prompt:"Crônicas costumam tratar de:", choices:["Mitologia","Cotidiano","Teoria quântica","Programação"], answer:1},
          {type:"tf", prompt:"Uma crônica precisa ser muito longa.", answer:false},
          {type:"open", prompt:"Escreva um exemplo de fato cotidiano que poderia virar crônica."}
        ]
      },
      {
        titulo: "Narrativa e Personagem",
        summary: [
          "Narrativa conta uma história: narrador, personagens, tempo, espaço, enredo.",
          "Personagens podem ser principais, secundários e figurantes.",
          "Todo enredo tem início, desenvolvimento e desfecho."
        ],
        mindmap: [{titulo:"Narrativa", itens:["Narrador","Personagens","Tempo","Espaço","Enredo (começo-meio-fim)"]}],
        questionBank: [
          {type:"open", prompt:"Liste os cinco elementos básicos da narrativa."},
          {type:"mcq", prompt:"Quem conta a história?", choices:["Personagem","Narrador","Autor","Leitor"], answer:1},
          {type:"tf", prompt:"Toda narrativa tem começo, meio e fim.", answer:true},
          {type:"open", prompt:"Classifique um personagem como principal ou secundário e justifique."},
          {type:"mcq", prompt:"Qual elemento indica onde a história acontece?", choices:["Tempo","Espaço","Enredo","Narrador"], answer:1},
          {type:"tf", prompt:"Figurantes são personagens sem função na história.", answer:false},
          {type:"open", prompt:"Escreva um breve enredo de 3 frases."},
          {type:"mcq", prompt:"Qual opção é um conflito narrativo?", choices:["Descrever o cenário","Apresentar a capa","Dificuldade do herói","Nomear o autor"], answer:2},
          {type:"tf", prompt:"Narrador sempre é personagem.", answer:false},
          {type:"open", prompt:"Explique a diferença entre narrador e autor."}
        ]
      },
      {
        titulo: "Texto Instrucional",
        summary: [
          "Explica como fazer algo (receitas, manuais, regras de jogo).",
          "Linguagem clara com verbos no imperativo: misture, organize, corte.",
          "Estrutura comum: materiais + passos."
        ],
        mindmap: [{titulo:"Texto Instrucional", itens:["Finalidade: ensinar","Materiais","Passos","Imperativo"]}],
        questionBank: [
          {type:"mcq", prompt:"Qual a finalidade do texto instrucional?", choices:["Contar histórias","Ensinar a fazer algo","Mostrar sentimentos","Opinar"], answer:1},
          {type:"open", prompt:"Encontre 3 verbos no imperativo em um texto instrucional."},
          {type:"tf", prompt:"Todo texto instrucional usa linguagem figurada.", answer:false},
          {type:"open", prompt:"Crie 4 passos para 'Como organizar a mochila'."},
          {type:"mcq", prompt:"Qual item costuma aparecer?", choices:["Rima","Materiais","Versos","Diálogos"], answer:1},
          {type:"tf", prompt:"Receitas são exemplos de texto instrucional.", answer:true},
          {type:"open", prompt:"Reescreva um passo pouco claro de modo mais objetivo."},
          {type:"mcq", prompt:"O modo de preparo é parte da:", choices:["Introdução","Conclusão","Passos","Legenda"], answer:2},
          {type:"tf", prompt:"Manuais e regras de jogo são textos instrucionais.", answer:true},
          {type:"open", prompt:"Liste materiais para um experimento simples com água."}
        ]
      },
      {
        titulo: "Linguagem Figurada (Metáfora e Comparação)",
        summary: [
          "Metáfora substitui uma palavra por outra: 'meu coração é de pedra'.",
          "Comparação usa conectivos: 'rápido como um raio'.",
          "Torna o texto expressivo e criativo."
        ],
        mindmap: [{titulo:"Linguagem Figurada", itens:["Metáfora: substitui","Comparação: conectivos","Expressividade"]}],
        questionBank: [
          {type:"open", prompt:"Identifique uma metáfora em: 'A vida é um sopro'."},
          {type:"tf", prompt:"Comparação sempre tem conectivo.", answer:true},
          {type:"mcq", prompt:"'Ela é uma flor' é:", choices:["Metáfora","Comparação","Personificação","Hipérbole"], answer:0},
          {type:"open", prompt:"Crie uma comparação usando 'como' para velocidade."},
          {type:"tf", prompt:"Metáfora e comparação são iguais.", answer:false},
          {type:"mcq", prompt:"'Firme como uma rocha' é:", choices:["Metáfora","Comparação","Ironia","Apóstrofe"], answer:1},
          {type:"open", prompt:"Explique por que a linguagem figurada ajuda a entender sentimentos."},
          {type:"tf", prompt:"Linguagem figurada aparece só em poesias.", answer:false},
          {type:"mcq", prompt:"Conectivo típico de comparação:", choices:["Entretanto","Como","Quando","Mas"], answer:1},
          {type:"open", prompt:"Reescreva uma frase literal em versão metafórica."}
        ]
      },
      {
        titulo: "Produção de Texto Opinativo",
        summary: [
          "Autor defende um ponto de vista com argumentos.",
          "Estrutura: introdução (opinião), desenvolvimento (argumentos), conclusão (reforço).",
          "Conectivos: porque, portanto, assim."
        ],
        mindmap: [{titulo:"Texto Opinativo", itens:["Introdução: opinião","Desenvolvimento: argumentos","Conclusão: reforço","Conectivos lógicos"]}],
        questionBank: [
          {type:"mcq", prompt:"O que caracteriza um texto opinativo?", choices:["Relatar fatos neutros","Defender um ponto de vista","Ensinar a fazer algo","Descrever cenários"], answer:1},
          {type:"open", prompt:"Escreva uma opinião sobre uso de uniforme escolar."},
          {type:"tf", prompt:"Não é necessário apresentar argumentos.", answer:false},
          {type:"open", prompt:"Liste 3 conectivos úteis em textos opinativos."},
          {type:"mcq", prompt:"Parte do texto que apresenta argumentos:", choices:["Introdução","Desenvolvimento","Conclusão","Título"], answer:1},
          {type:"tf", prompt:"Conclusão reforça a ideia principal.", answer:true},
          {type:"open", prompt:"Reescreva um argumento deixando-o mais convincente."},
          {type:"mcq", prompt:"Qual NÃO é conectivo lógico:", choices:["Porque","Portanto","Talvez","Assim"], answer:2},
          {type:"tf", prompt:"Opinião e argumento são sinônimos.", answer:false},
          {type:"open", prompt:"Dê um exemplo de contra-argumento educado."}
        ]
      }
    ]
  },
  {
    id: "matematica",
    nome: "Matemática",
    aulas: [
      {
        titulo: "Números Inteiros e Operações",
        summary: [
          "Inteiros incluem negativos, zero e positivos.",
          "Regras de sinais para soma e multiplicação.",
          "Situações do cotidiano com números negativos."
        ],
        mindmap: [{titulo:"Inteiros", itens:["Negativos","Zero","Positivos","Regras de sinais","Operações"]}],
        questionBank: [
          {type:"mcq", prompt:"O oposto de −7 é:", choices:["−7","0","+7","−14"], answer:2},
          {type:"tf", prompt:"−5 + (−3) = −8.", answer:true},
          {type:"open", prompt:"Resolva: (−2) × (−4)"},
          {type:"open", prompt:"Descreva uma situação com número negativo no dia a dia."},
          {type:"mcq", prompt:"10 − (−5) =", choices:["15","−15","5","−5"], answer:0},
          {type:"tf", prompt:"Somar dois negativos dá positivo.", answer:false},
          {type:"open", prompt:"Classifique −12, 0 e 9 como negativos, zero ou positivos."},
          {type:"mcq", prompt:"(−3) × (+4) =", choices:["−12","+12","−7","+7"], answer:0},
          {type:"tf", prompt:"Zero é neutro na adição.", answer:true},
          {type:"open", prompt:"Explique por que (−2)×(−2)=+4."}
        ]
      },
      {
        titulo: "Frações e Equivalência",
        summary: [
          "Frações representam parte de um todo.",
          "Frações equivalentes têm o mesmo valor.",
          "Para simplificar, divida numerador e denominador pelo mesmo número."
        ],
        mindmap: [{titulo:"Frações", itens:["Numerador/Denominador","Equivalentes","Simplificação","Exemplos práticos"]}],
        questionBank: [
          {type:"mcq", prompt:"Fração equivalente a 3/6:", choices:["1/2","2/3","3/4","6/3"], answer:0},
          {type:"open", prompt:"Simplifique 12/16."},
          {type:"tf", prompt:"5/10 = 1/2.", answer:true},
          {type:"open", prompt:"Transforme 0,5 em fração."},
          {type:"open", prompt:"Dê um exemplo de fração no cotidiano."},
          {type:"mcq", prompt:"Maior fração:", choices:["3/5","4/5","1/5","2/5"], answer:1},
          {type:"tf", prompt:"2/4 e 1/2 são diferentes.", answer:false},
          {type:"open", prompt:"Explique o que é simplificar uma fração."},
          {type:"mcq", prompt:"2/3 = x/21. x =", choices:["12","14","18","7"], answer:2},
          {type:"open", prompt:"Crie duas frações equivalentes a 2/3."}
        ]
      },
      {
        titulo: "Razão e Proporção",
        summary: [
          "Razão compara duas grandezas (a/b).",
          "Proporção é igualdade entre razões.",
          "Aplicações: receitas, escalas de mapas."
        ],
        mindmap: [{titulo:"Razão e Proporção", itens:["Razão","Proporção","Regra de 3","Escalas"]}],
        questionBank: [
          {type:"mcq", prompt:"A razão entre 10 e 5 é:", choices:["2","1/2","15","50"], answer:0},
          {type:"tf", prompt:"2/4 = 1/2 é proporção.", answer:true},
          {type:"open", prompt:"Se 2 copos servem 4 pessoas, quantos copos para 8?"},
          {type:"open", prompt:"Resolva: 3/5 = x/20."},
          {type:"open", prompt:"Explique o que é escala em mapas."},
          {type:"mcq", prompt:"Proporção correta:", choices:["2/3 = 4/9","3/4 = 6/8","1/2 = 2/3","2/5 = 3/5"], answer:1},
          {type:"tf", prompt:"Regra de três serve para proporções.", answer:true},
          {type:"open", prompt:"Monte uma razão para comparar 12 maçãs e 3 peras."},
          {type:"mcq", prompt:"Em 1:100.000, 1 cm equivale a:", choices:["1 m","10 m","1 km","10 km"], answer:2},
          {type:"open", prompt:"Explique uma situação do dia a dia com razão."}
        ]
      },
      {
        titulo: "Porcentagem",
        summary: [
          "Porcentagem é 'tanto por 100' (%).",
          "50% = metade; 25% = um quarto.",
          "Cálculo: (parte ÷ total) × 100."
        ],
        mindmap: [{titulo:"Porcentagem", itens:["Definição","Cálculo","Descontos","Equivalências"]}],
        questionBank: [
          {type:"mcq", prompt:"50% de 200 =", choices:["25","50","100","150"], answer:2},
          {type:"tf", prompt:"25% de 40 = 10.", answer:true},
          {type:"open", prompt:"Calcule 10% de 300."},
          {type:"open", prompt:"Produto de R$50 com 20% de desconto: valor final?"},
          {type:"open", prompt:"Explique o que significa 100%."},
          {type:"mcq", prompt:"Qual é 30% de 90?", choices:["18","21","27","30"], answer:2},
          {type:"tf", prompt:"10% de 100 é 5.", answer:false},
          {type:"open", prompt:"Dê um exemplo de porcentagem no cotidiano."},
          {type:"mcq", prompt:"Qual fração equivale a 25%?", choices:["1/2","1/3","1/4","1/5"], answer:2},
          {type:"open", prompt:"Explique diferença entre porcentagem e ponto percentual."}
        ]
      },
      {
        titulo: "Expressões Algébricas e Equações Simples",
        summary: [
          "Expressões usam letras como incógnitas.",
          "Equações são igualdades com incógnitas; resolver é encontrar o valor.",
          "Ex.: 2x + 3 = 7 → x = 2."
        ],
        mindmap: [{titulo:"Álgebra", itens:["Expressões","Incógnitas","Equações","Resolver"]}],
        questionBank: [
          {type:"open", prompt:"Resolva: x + 5 = 10."},
          {type:"mcq", prompt:"Em 2x = 12, x =", choices:["2","4","6","12"], answer:2},
          {type:"tf", prompt:"3x + 2 = 11 → x = 3.", answer:true},
          {type:"open", prompt:"Escreva: 'o dobro de um número mais 3'."},
          {type:"open", prompt:"Resolva: 5x − 10 = 0."},
          {type:"mcq", prompt:"Se x=2, 3x+1 =", choices:["5","6","7","8"], answer:2},
          {type:"tf", prompt:"2x = x + x.", answer:true},
          {type:"open", prompt:"Dê um exemplo de equação do cotidiano."},
          {type:"mcq", prompt:"Em x−4=9, x =", choices:["5","9","13","4"], answer:2},
          {type:"open", prompt:"Explique como isolar a incógnita."}
        ]
      }
    ]
  },
  {
    id: "ciencias",
    nome: "Ciências",
    aulas: [
      {
        titulo: "A Célula e Suas Partes",
        summary: [
          "Célula é a menor unidade da vida.",
          "Membrana protege e controla entradas/saídas.",
          "Núcleo controla atividades e abriga o DNA.",
          "Diferenças entre célula animal e vegetal."
        ],
        mindmap: [{titulo:"Célula", itens:["Membrana","Citoplasma","Núcleo","Animal × Vegetal"]}],
        questionBank: [
          {type:"mcq", prompt:"Qual organela é o 'cérebro' da célula?", choices:["Citoplasma","Núcleo","Ribossomo","Mitocôndria"], answer:1},
          {type:"tf", prompt:"Cloroplasto só existe em células vegetais.", answer:true},
          {type:"open", prompt:"Função da membrana plasmática."},
          {type:"mcq", prompt:"Onde fica o DNA?", choices:["Citoplasma","Núcleo","Parede celular","Mitocôndria"], answer:1},
          {type:"open", prompt:"Desenhe e nomeie 2 diferenças entre célula animal e vegetal."},
          {type:"tf", prompt:"Todas as células possuem núcleo.", answer:false},
          {type:"open", prompt:"Explique o papel do citoplasma."},
          {type:"mcq", prompt:"Organela exclusiva de plantas:", choices:["Cloroplasto","Ribossomo","Lisossomo","Centríolo"], answer:0},
          {type:"tf", prompt:"Membrana regula trocas com o meio.", answer:true},
          {type:"open", prompt:"Relacione DNA e características dos seres vivos."}
        ]
      },
      {
        titulo: "Ecossistemas e Cadeias Alimentares",
        summary: [
          "Ecossistema: seres vivos + ambiente.",
          "Cadeia alimentar: produtor → consumidor → decompositor.",
          "Energia flui; matéria circula."
        ],
        mindmap: [{titulo:"Ecossistema", itens:["Produtor","Consumidor","Decompositor","Fluxo de energia"]}],
        questionBank: [
          {type:"mcq", prompt:"Quem produz energia no ecossistema?", choices:["Animais","Plantas","Fungos","Bactérias"], answer:1},
          {type:"tf", prompt:"O homem é sempre consumidor primário.", answer:false},
          {type:"open", prompt:"Exemplo de cadeia alimentar com 3 níveis."},
          {type:"open", prompt:"Diferença entre produtor e consumidor."},
          {type:"mcq", prompt:"Decompositores são:", choices:["Plantas","Fungos e bactérias","Carnívoros","Peixes"], answer:1},
          {type:"tf", prompt:"Em cadeias, a energia aumenta no topo.", answer:false},
          {type:"open", prompt:"Explique por que há menos energia em níveis superiores."},
          {type:"mcq", prompt:"Produtores realizam:", choices:["Respiração","Fotossíntese","Digestão externa","Fermentação"], answer:1},
          {type:"tf", prompt:"Matéria não circula nos ecossistemas.", answer:false},
          {type:"open", prompt:"Esquematize uma teia alimentar simples."}
        ]
      },
      {
        titulo: "Água e Ar",
        summary: [
          "Ciclo da água: evaporação, condensação, precipitação, infiltração.",
          "Ar é mistura de gases: N₂, O₂, CO₂.",
          "Poluição compromete qualidade e saúde."
        ],
        mindmap: [{titulo:"Água e Ar", itens:["Ciclo da água","Composição do ar","Poluição","Importância"]}],
        questionBank: [
          {type:"mcq", prompt:"Gás mais abundante no ar:", choices:["O₂","CO₂","N₂","H₂"], answer:2},
          {type:"tf", prompt:"Evaporação é líquido → gasoso.", answer:true},
          {type:"open", prompt:"Duas consequências da poluição da água."},
          {type:"open", prompt:"Importância do oxigênio para os seres vivos."},
          {type:"mcq", prompt:"Chuva corresponde a:", choices:["Evaporação","Condensação","Precipitação","Infiltração"], answer:2},
          {type:"tf", prompt:"Ar puro é 100% oxigênio.", answer:false},
          {type:"open", prompt:"Explique condensação no ciclo da água."},
          {type:"mcq", prompt:"Poluente atmosférico:", choices:["Poeira natural","Material particulado","Vapor d'água","Nitrogênio"], answer:1},
          {type:"tf", prompt:"Infiltração alimenta aquíferos.", answer:true},
          {type:"open", prompt:"Liste práticas para economizar água."}
        ]
      },
      {
        titulo: "Corpo Humano: Sistemas",
        summary: [
          "Sistemas trabalham integrados: digestório, respiratório, circulatório, excretor.",
          "Digestório transforma alimentos; respiratório troca gases; circulatório transporta; excretor elimina resíduos."
        ],
        mindmap: [{titulo:"Corpo Humano", itens:["Digestório","Respiratório","Circulatório","Excretor","Integração"]}],
        questionBank: [
          {type:"mcq", prompt:"Qual sistema faz a digestão?", choices:["Respiratório","Digestório","Circulatório","Nervoso"], answer:1},
          {type:"tf", prompt:"Pulmão é do sistema circulatório.", answer:false},
          {type:"open", prompt:"Função do coração."},
          {type:"open", prompt:"Cite um órgão do sistema excretor."},
          {type:"mcq", prompt:"O sangue leva:", choices:["Somente O₂","Somente nutrientes","O₂ e nutrientes","Apenas hormônios"], answer:2},
          {type:"tf", prompt:"Sistemas funcionam isolados.", answer:false},
          {type:"open", prompt:"Explique a troca gasosa nos alvéolos."},
          {type:"mcq", prompt:"Órgão do sistema digestório:", choices:["Rim","Fígado","Pulmão","Coração"], answer:1},
          {type:"tf", prompt:"Urina é produto do excretor.", answer:true},
          {type:"open", prompt:"Relacione respiração e circulação."}
        ]
      },
      {
        titulo: "Energia e Suas Transformações",
        summary: [
          "Energia é a capacidade de realizar trabalho.",
          "Tipos: mecânica, térmica, elétrica, luminosa, química.",
          "Energia não se cria nem se destrói; transforma-se."
        ],
        mindmap: [{titulo:"Energia", itens:["Tipos","Transformações","Exemplos","Conservação"]}],
        questionBank: [
          {type:"mcq", prompt:"A energia da comida é:", choices:["Mecânica","Química","Térmica","Luminosa"], answer:1},
          {type:"tf", prompt:"Energia pode ser criada.", answer:false},
          {type:"open", prompt:"Exemplo de transformação de energia em casa."},
          {type:"mcq", prompt:"Energia de uma bola em movimento:", choices:["Potencial","Cinética","Química","Térmica"], answer:1},
          {type:"open", prompt:"Explique a lei da conservação da energia."},
          {type:"tf", prompt:"Lâmpada: elétrica → luminosa (+ térmica).", answer:true},
          {type:"open", prompt:"Classifique 3 aparelhos e suas energias de entrada/saída."},
          {type:"mcq", prompt:"Fonte renovável:", choices:["Carvão","Petróleo","Solar","Gás"], answer:2},
          {type:"tf", prompt:"Todas as transformações são 100% eficientes.", answer:false},
          {type:"open", prompt:"Por que há perdas em forma de calor?"}
        ]
      }
    ]
  },
  {
    id: "historia",
    nome: "História",
    aulas: [
      {
        titulo: "Povos da Antiguidade: Egito Antigo",
        summary: [
          "Egito no nordeste da África, às margens do Nilo.",
          "Sociedade em camadas: faraó, sacerdotes, escribas, soldados, artesãos, camponeses.",
          "Religião politeísta; escrita hieroglífica; pirâmides."
        ],
        mindmap: [{titulo:"Egito Antigo", itens:["Nilo","Sociedade em pirâmide","Politeísmo","Cultura e escrita"]}],
        questionBank: [
          {type:"mcq", prompt:"Rio que possibilitou o Egito Antigo:", choices:["Tigre","Eufrates","Nilo","Jordão"], answer:2},
          {type:"tf", prompt:"O faraó era considerado um deus vivo.", answer:true},
          {type:"open", prompt:"Importância das cheias do Nilo."},
          {type:"open", prompt:"Cite duas classes sociais do Egito Antigo."},
          {type:"mcq", prompt:"Escrita egípcia:", choices:["Cuneiforme","Hieróglifo","Grega","Latina"], answer:1},
          {type:"tf", prompt:"Egípcios eram monoteístas.", answer:false},
          {type:"open", prompt:"Explique o papel dos escribas."},
          {type:"mcq", prompt:"Construções simbólicas:", choices:["Muralhas","Pirâmides","Templos gregos","Anfiteatros"], answer:1},
          {type:"tf", prompt:"Camponeses estavam no topo da hierarquia.", answer:false},
          {type:"open", prompt:"Relacione religião e poder do faraó."}
        ]
      },
      {
        titulo: "Grécia Antiga",
        summary: [
          "Península Balcânica com cidades-estado (pólis).",
          "Atenas (democracia) vs Esparta (militarismo).",
          "Contribuições: filosofia, teatro, Olimpíadas, mitologia."
        ],
        mindmap: [{titulo:"Grécia Antiga", itens:["Pólis","Atenas x Esparta","Cultura","Mitologia"]}],
        questionBank: [
          {type:"open", prompt:"Qual a principal característica política de Atenas?"},
          {type:"tf", prompt:"Esparta era conhecida pela vida militar.", answer:true},
          {type:"open", prompt:"Cite uma contribuição cultural da Grécia Antiga."},
          {type:"mcq", prompt:"Os Jogos Olímpicos surgiram em:", choices:["Roma","Esparta","Olímpia","Egito"], answer:2},
          {type:"open", prompt:"Defina pólis."},
          {type:"tf", prompt:"Mitologia grega não influenciou a cultura.", answer:false},
          {type:"open", prompt:"Compare democracia ateniense e atual."},
          {type:"mcq", prompt:"Filósofo grego:", choices:["Sócrates","Cícero","Nero","Ramsés"], answer:0},
          {type:"tf", prompt:"Teatro foi importante na Grécia.", answer:true},
          {type:"open", prompt:"Explique a educação em Esparta."}
        ]
      },
      {
        titulo: "Roma Antiga",
        summary: [
          "Surgiu na Península Itálica: Monarquia → República → Império.",
          "Sociedade: patrícios, plebeus, escravos.",
          "Contribuições: direito romano, estradas, aquedutos."
        ],
        mindmap: [{titulo:"Roma Antiga", itens:["Fases","Sociedade","Direito","Arquitetura"]}],
        questionBank: [
          {type:"mcq", prompt:"Fase final de Roma:", choices:["República","Império","Monarquia","Democracia"], answer:1},
          {type:"tf", prompt:"Patrícios eram a elite romana.", answer:true},
          {type:"open", prompt:"Duas construções importantes dos romanos."},
          {type:"open", prompt:"Papel do Senado Romano."},
          {type:"open", prompt:"Quem foi Júlio César?"},
          {type:"tf", prompt:"Plebeus eram escravizados por lei.", answer:false},
          {type:"mcq", prompt:"Via romana é:", choices:["Leis","Estrada","Templo","Aqüeduto"], answer:1},
          {type:"tf", prompt:"Aquedutos levavam água às cidades.", answer:true},
          {type:"open", prompt:"Explique a transição República → Império."},
          {type:"open", prompt:"Relacione o direito romano com leis atuais."}
        ]
      },
      {
        titulo: "Idade Média",
        summary: [
          "Período entre queda de Roma e início da Idade Moderna.",
          "Sociedade feudal: reis, nobres, servos; Igreja com grande poder.",
          "Cruzadas, peste negra, universidades."
        ],
        mindmap: [{titulo:"Idade Média", itens:["Feudalismo","Igreja","Cruzadas","Peste Negra","Universidades"]}],
        questionBank: [
          {type:"mcq", prompt:"Sistema econômico medieval:", choices:["Capitalismo","Mercantilismo","Feudalismo","Comunismo"], answer:2},
          {type:"tf", prompt:"A Igreja tinha poder político e religioso.", answer:true},
          {type:"open", prompt:"Relação entre senhores e servos."},
          {type:"open", prompt:"Uma consequência das Cruzadas."},
          {type:"open", prompt:"O que foi a peste negra?"},
          {type:"tf", prompt:"Universidades surgiram nesse período.", answer:true},
          {type:"mcq", prompt:"Classe trabalhadora na base:", choices:["Nobreza","Clero","Servos","Comerciantes"], answer:2},
          {type:"tf", prompt:"Feudos eram cidades comerciais.", answer:false},
          {type:"open", prompt:"Explique o papel da Igreja no cotidiano."},
          {type:"open", prompt:"Causas da crise do feudalismo."}
        ]
      },
      {
        titulo: "Formação do Brasil Colônia",
        summary: [
          "Chegada portuguesa em 1500; exploração do pau-brasil; depois açúcar.",
          "Capitanias hereditárias e governo-geral.",
          "Trabalho indígena e escravização africana."
        ],
        mindmap: [{titulo:"Brasil Colônia", itens:["Pau-brasil","Açúcar","Capitanias","Governo-geral","Trabalho escravizado"]}],
        questionBank: [
          {type:"mcq", prompt:"Primeiro produto explorado:", choices:["Açúcar","Pau-brasil","Ouro","Café"], answer:1},
          {type:"tf", prompt:"Mão de obra indígena foi substituída por africana.", answer:true},
          {type:"open", prompt:"Explique as capitanias hereditárias."},
          {type:"open", prompt:"Quem foi Tomé de Souza?"},
          {type:"open", prompt:"Duas consequências da colonização."},
          {type:"tf", prompt:"Ouro foi base inicial da economia.", answer:false},
          {type:"mcq", prompt:"Região com engenhos de açúcar:", choices:["Sertão","Litoral nordestino","Sul","Centro-Oeste"], answer:1},
          {type:"tf", prompt:"Governo-geral centralizou a administração.", answer:true},
          {type:"open", prompt:"Impactos da escravidão na sociedade."},
          {type:"open", prompt:"Relacione colonização com a urbanização posterior."}
        ]
      }
    ]
  },
  {
    id: "geografia",
    nome: "Geografia",
    aulas: [
      {
        titulo: "Cartografia: Mapas e Escalas",
        summary: [
          "Mapa é representação reduzida da Terra.",
          "Elementos: título, legenda, escala, orientação.",
          "Escala relaciona distância real e no mapa."
        ],
        mindmap: [{titulo:"Mapa", itens:["Título","Legenda","Escala","Rosa dos ventos"]}],
        questionBank: [
          {type:"mcq", prompt:"A rosa dos ventos indica:", choices:["Distância","Orientação","Relevo","População"], answer:1},
          {type:"tf", prompt:"Escala maior mostra mais detalhes.", answer:true},
          {type:"open", prompt:"Função da legenda em um mapa."},
          {type:"open", prompt:"Desenhe os quatro pontos cardeais."},
          {type:"mcq", prompt:"Mapa 1:50.000 → 1 cm é:", choices:["50 m","50 km","500 m","500 km"], answer:1},
          {type:"tf", prompt:"Escalas não mudam as proporções.", answer:false},
          {type:"open", prompt:"Explique diferença entre planta e mapa."},
          {type:"mcq", prompt:"Coordenada mede:", choices:["Altura","Localização","Temperatura","Relevo"], answer:1},
          {type:"tf", prompt:"Título informa tema do mapa.", answer:true},
          {type:"open", prompt:"Dê um exemplo de uso de escala no cotidiano."}
        ]
      },
      {
        titulo: "Relevo da Terra",
        summary: [
          "Relevo: montanhas, planaltos, planícies, depressões.",
          "Agentes internos (tectônica) e externos (erosão).",
          "Relevo brasileiro variado: planaltos e planícies."
        ],
        mindmap: [{titulo:"Relevo", itens:["Montanhas","Planaltos","Planícies","Depressões","Agentes"]}],
        questionBank: [
          {type:"open", prompt:"Cite 4 tipos principais de relevo."},
          {type:"tf", prompt:"Chuvas ajudam a desgastar o relevo.", answer:true},
          {type:"mcq", prompt:"Serra do Mar é exemplo de:", choices:["Planície","Planalto","Montanha","Depressão"], answer:2},
          {type:"open", prompt:"Diferença entre planalto e planície."},
          {type:"tf", prompt:"Relevo não muda com o tempo.", answer:false},
          {type:"mcq", prompt:"Agente interno:", choices:["Vento","Chuvas","Tectonismo","Rios"], answer:2},
          {type:"tf", prompt:"Planícies são áreas planas baixas.", answer:true},
          {type:"open", prompt:"Explique erosão."},
          {type:"mcq", prompt:"Depressões são áreas:", choices:["Altas","Abaixo do entorno","Com neve","Florestadas"], answer:1},
          {type:"open", prompt:"Dê exemplos de relevo no Brasil."}
        ]
      },
      {
        titulo: "Clima e Vegetação",
        summary: [
          "Clima: conjunto de condições do tempo ao longo dos anos.",
          "Elementos: temperatura, umidade, ventos, chuvas.",
          "Vegetação: floresta amazônica, cerrado, caatinga, mata atlântica, pampas, pantanal."
        ],
        mindmap: [{titulo:"Clima/Vegetação", itens:["Elementos do clima","Tipos de clima no Brasil","Biomas"]}],
        questionBank: [
          {type:"mcq", prompt:"Clima da Amazônia:", choices:["Semiárido","Equatorial","Subtropical","Tropical de altitude"], answer:1},
          {type:"tf", prompt:"Vegetação e clima estão relacionados.", answer:true},
          {type:"open", prompt:"Uma característica da caatinga."},
          {type:"open", prompt:"Defina clima."},
          {type:"mcq", prompt:"Mata Atlântica está associada a clima:", choices:["Equatorial","Tropical úmido","Semiárido","Subtropical seco"], answer:1},
          {type:"tf", prompt:"Cerrado ocorre apenas no sul.", answer:false},
          {type:"open", prompt:"Explique um elemento do clima."},
          {type:"mcq", prompt:"Bioma inundável:", choices:["Pantanal","Pampas","Caatinga","Amazônia"], answer:0},
          {type:"tf", prompt:"Pampas têm campos abertos.", answer:true},
          {type:"open", prompt:"Cite relações clima-vegetação no Brasil."}
        ]
      },
      {
        titulo: "População e Urbanização",
        summary: [
          "População: número de habitantes; densidade, crescimento, migração.",
          "Urbanização: crescimento das cidades e seus problemas."
        ],
        mindmap: [{titulo:"População/Urbanização", itens:["Densidade","Migração","Êxodo rural","Problemas urbanos"]}],
        questionBank: [
          {type:"open", prompt:"Defina densidade demográfica."},
          {type:"mcq", prompt:"Urbanização é:", choices:["Aumento da população rural","Crescimento das cidades","Desmatamento","Turismo urbano"], answer:1},
          {type:"tf", prompt:"Migração interna é mudar de país.", answer:false},
          {type:"open", prompt:"Dois problemas da urbanização acelerada."},
          {type:"open", prompt:"Explique êxodo rural."},
          {type:"tf", prompt:"Densidade = população/área.", answer:true},
          {type:"mcq", prompt:"Fluxo do campo à cidade:", choices:["Imigração","Emigração","Êxodo rural","Mobilidade",], answer:2},
          {type:"tf", prompt:"Crescimento urbano não impacta trânsito.", answer:false},
          {type:"open", prompt:"Sugira soluções para um problema urbano."},
          {type:"open", prompt:"Explique migração sazonal."}
        ]
      },
      {
        titulo: "Recursos Naturais e Meio Ambiente",
        summary: [
          "Recursos: água, solo, minerais, florestas, petróleo.",
          "Uso sustentável e problemas: desmatamento, poluição, aquecimento global."
        ],
        mindmap: [{titulo:"Meio Ambiente", itens:["Recursos","Problemas","Soluções"]}],
        questionBank: [
          {type:"open", prompt:"Cite três recursos naturais."},
          {type:"mcq", prompt:"Recurso renovável é:", choices:["Que não se esgota","Que pode ser recuperado pela natureza","Que nunca acaba","Que só existe em minas"], answer:1},
          {type:"tf", prompt:"Petróleo é não renovável.", answer:true},
          {type:"open", prompt:"Defina sustentabilidade."},
          {type:"open", prompt:"Uma prática de preservação ambiental."},
          {type:"tf", prompt:"Reciclagem reduz lixo.", answer:true},
          {type:"mcq", prompt:"Exemplo de energia limpa:", choices:["Carvão","Solar","Petróleo","Lenha"], answer:1},
          {type:"tf", prompt:"Desmatamento não afeta clima.", answer:false},
          {type:"open", prompt:"Explique efeito estufa."},
          {type:"open", prompt:"Dê exemplos de uso responsável da água."}
        ]
      }
    ]
  },
  {
    id: "ingles",
    nome: "Inglês",
    aulas: [
      {
        titulo: "Greetings & Introductions",
        summary: [
          "Greetings: Hello, Hi, Good morning.",
          "Introductions: My name is…, I am…, Nice to meet you.",
          "Perguntas: What's your name? How are you?"
        ],
        mindmap: [{titulo:"Greetings", itens:["Hello/Hi","Good morning","My name is…","Nice to meet you","Questions"]}],
        questionBank: [
          {type:"mcq", prompt:"Resposta para “What’s your name?”", choices:["I am fine.","My name is Ana.","I am 12.","Hello!"], answer:1},
          {type:"tf", prompt:"“Nice to meet you” = Prazer em conhecê-lo.", answer:true},
          {type:"open", prompt:"Traduza: Good evening."},
          {type:"open", prompt:"Escreva como você se apresenta em inglês."},
          {type:"open", prompt:"Complete: ____ name is John."},
          {type:"tf", prompt:"'Hi' é mais formal que 'Hello'.", answer:false},
          {type:"mcq", prompt:"Pergunta correta:", choices:["Where you name?","What's your name?","How old are name?","Who is name?"], answer:1},
          {type:"open", prompt:"Traduza: How are you?"},
          {type:"tf", prompt:"Good night é usado para cumprimentar ao chegar.", answer:false},
          {type:"open", prompt:"Crie um diálogo curto de apresentação."}
        ]
      },
      {
        titulo: "Verb To Be (Simple Present)",
        summary: [
          "To be: am/are/is.",
          "Negativa: am not / isn’t / aren’t; pergunta: Are you…? Is he…?",
          "Concordância sujeito-verbo."
        ],
        mindmap: [{titulo:"To Be", itens:["am/is/are","Negativa","Interrogativa","Concordância"]}],
        questionBank: [
          {type:"mcq", prompt:"They ___ my friends.", choices:["is","am","are","be"], answer:2},
          {type:"tf", prompt:"He are a student. (correta)", answer:false},
          {type:"open", prompt:"Complete: I ___ Brazilian."},
          {type:"open", prompt:"Forma negativa: She is a teacher."},
          {type:"open", prompt:"Pergunta: Ele é seu amigo?"},
          {type:"tf", prompt:"Am é usado com I.", answer:true},
          {type:"mcq", prompt:"We ___ happy.", choices:["is","are","am","be"], answer:1},
          {type:"open", prompt:"Escreva 3 frases com 'to be'."},
          {type:"tf", prompt:"'Are you' inicia perguntas.", answer:true},
          {type:"open", prompt:"Traduza: They are from Brazil."}
        ]
      },
      {
        titulo: "School Vocabulary",
        summary: [
          "Palavras: book, notebook, pen, pencil, eraser, desk, teacher, student.",
          "Frases: Can I borrow a pen? Where is my book?",
          "There is / There are."
        ],
        mindmap: [{titulo:"School", itens:["Objects","People","Useful phrases","There is/are"]}],
        questionBank: [
          {type:"mcq", prompt:"'Lápis' em inglês:", choices:["Pen","Pencil","Eraser","Book"], answer:1},
          {type:"tf", prompt:"Teacher = aluno.", answer:false},
          {type:"open", prompt:"Traduza: There is a notebook on the desk."},
          {type:"open", prompt:"Complete: Can I borrow your ____? (caneta)"},
          {type:"open", prompt:"Liste 5 objetos escolares em inglês."},
          {type:"tf", prompt:"Student = estudante.", answer:true},
          {type:"mcq", prompt:"'Borracha' em inglês:", choices:["Book","Desk","Eraser","Notebook"], answer:2},
          {type:"open", prompt:"Crie 2 frases com there is/are."},
          {type:"tf", prompt:"Desk = caderno.", answer:false},
          {type:"open", prompt:"Traduza: Where is the teacher?"}
        ]
      },
      {
        titulo: "Days of the Week & Daily Routine",
        summary: [
          "Dias: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday.",
          "Rotina: wake up, go to school, study, play, sleep.",
          "Simple Present em rotinas: I go to school on Monday."
        ],
        mindmap: [{titulo:"Routine", itens:["Days of week","Common verbs","Simple Present + on"]}],
        questionBank: [
          {type:"mcq", prompt:"Primeiro dia da semana em inglês:", choices:["Sunday","Monday","Saturday","Friday"], answer:1},
          {type:"tf", prompt:"'Friday' = quarta-feira.", answer:false},
          {type:"open", prompt:"Complete: I ____ up at 7 o'clock."},
          {type:"open", prompt:"Traduza: I play soccer on Sunday."},
          {type:"open", prompt:"Liste 3 atividades da sua rotina em inglês."},
          {type:"tf", prompt:"'On' é usado antes de dias da semana.", answer:true},
          {type:"mcq", prompt:"'Dormir' em inglês:", choices:["Study","Wake","Sleep","Play"], answer:2},
          {type:"open", prompt:"Escreva 2 frases com dias + rotina."},
          {type:"tf", prompt:"Monday é fim de semana.", answer:false},
          {type:"open", prompt:"Traduza: We study on Thursday."}
        ]
      },
      {
        titulo: "Simple Present (Actions and Habits)",
        summary: [
          "Ações do dia a dia; he/she/it adiciona -s.",
          "Negativa: don't / doesn't; perguntas com do/does."
        ],
        mindmap: [{titulo:"Simple Present", itens:["Afirmativa","He/She/It + s","Negativa","Perguntas Do/Does"]}],
        questionBank: [
          {type:"mcq", prompt:"She ___ English every day.", choices:["study","studies","studying","studied"], answer:1},
          {type:"tf", prompt:"I doesn't play tennis. (correta)", answer:false},
          {type:"open", prompt:"Complete: They ____ soccer."},
          {type:"open", prompt:"Negativa: He reads books."},
          {type:"open", prompt:"Pergunta: Você gosta de música?"},
          {type:"tf", prompt:"Does é usado com he/she/it.", answer:true},
          {type:"mcq", prompt:"'Gostar' com I:", choices:["I likes","I like","I liking","I liked"], answer:1},
          {type:"open", prompt:"Escreva 3 frases afirmativas no Simple Present."},
          {type:"tf", prompt:"Don't é usado com I/you/we/they.", answer:true},
          {type:"open", prompt:"Traduza: Does she play volleyball?"}
        ]
      }
    ]
  },
  {
    id: "espanhol",
    nome: "Espanhol",
    aulas: [
      {
        titulo: "Saludos",
        summary: [
          "Saudações: Hola, Buenos días, Buenas tardes, Buenas noches.",
          "Despedidas: Adiós, Hasta luego, Chau."
        ],
        mindmap: [{titulo:"Saludos/Despedidas", itens:["Hola","Buenos días","Buenas tardes","Buenas noches","Adiós","Hasta luego","Chau"]}],
        questionBank: [
          {type:"mcq", prompt:"'Boa noite' em espanhol:", choices:["Buenas tardes","Buenas noches","Buenos días","Chau"], answer:1},
          {type:"tf", prompt:"'Hola' significa olá.", answer:true},
          {type:"open", prompt:"Traduza: Hasta luego."},
          {type:"open", prompt:"Escreva duas despedidas em espanhol."},
          {type:"open", prompt:"Complete: ____, ¿cómo estás?"},
          {type:"tf", prompt:"'Adiós' é saudação inicial.", answer:false},
          {type:"mcq", prompt:"'Boa tarde' em espanhol:", choices:["Buenos días","Buenas tardes","Buenas noches","Hola"], answer:1},
          {type:"open", prompt:"Crie 1 diálogo curto de apresentação."},
          {type:"tf", prompt:"'Chau' não é usado em espanhol.", answer:false},
          {type:"open", prompt:"Traduza: Buenos días, profesor."}
        ]
      },
      {
        titulo: "Presentaciones",
        summary: [
          "¿Cómo te llamas? → Me llamo…",
          "Tengo 12 años; Soy de Brasil."
        ],
        mindmap: [{titulo:"Presentaciones", itens:["¿Cómo te llamas?","Me llamo…","Tengo ... anos","Soy de…"]}],
        questionBank: [
          {type:"mcq", prompt:"Resposta para ¿Cómo te llamas?", choices:["Tengo 12 años","Soy de Brasil","Me llamo Juan","Hola, buenas tardes"], answer:2},
          {type:"tf", prompt:"'Soy de Brasil' = Sou do Brasil.", answer:true},
          {type:"open", prompt:"Complete: Tengo ____ años. (12)"},
          {type:"open", prompt:"Traduza: Me llamo Pedro."},
          {type:"open", prompt:"Faça uma apresentação curta."},
          {type:"tf", prompt:"'¿Cómo te llamas?' pergunta a idade.", answer:false},
          {type:"mcq", prompt:"'De onde você é?':", choices:["¿Cómo estás?","¿De dónde eres?","¿Cuántos años tienes?","¿Qué tal?"], answer:1},
          {type:"open", prompt:"Responda: ¿De dónde eres?"},
          {type:"tf", prompt:"'Tengo' significa 'eu sou'.", answer:false},
          {type:"open", prompt:"Crie 3 frases com 'soy' e 'tengo'."}
        ]
      },
      {
        titulo: "Números y Colores",
        summary: [
          "Números: uno, dos, tres, cuatro, cinco…",
          "Cores: rojo, azul, verde, amarillo, negro, blanco."
        ],
        mindmap: [{titulo:"Números/Colores", itens:["1–20","rojo","azul","verde","amarillo","negro","blanco"]}],
        questionBank: [
          {type:"mcq", prompt:"'Cinco' significa:", choices:["4","5","6","7"], answer:1},
          {type:"tf", prompt:"'Azul' significa 'amarelo'.", answer:false},
          {type:"open", prompt:"Traduza: verde."},
          {type:"open", prompt:"Complete: Tengo ____ libros. (3)"},
          {type:"open", prompt:"Escreva cinco cores em espanhol."},
          {type:"tf", prompt:"'Blanco' é branco.", answer:true},
          {type:"mcq", prompt:"Cor do limão maduro:", choices:["rojo","azul","amarillo","negro"], answer:2},
          {type:"open", prompt:"Conte de 1 a 10 em espanhol."},
          {type:"tf", prompt:"'Negro' é preto.", answer:true},
          {type:"open", prompt:"Crie frases usando 3 cores."}
        ]
      },
      {
        titulo: "Verbos Regulares no Presente",
        summary: [
          "Verbos terminados em -ar, -er, -ir: hablar, comer, vivir.",
          "Conjugação: yo hablo, tú hablas, él/ella habla, nosotros hablamos, ellos hablan."
        ],
        mindmap: [{titulo:"Verbos regulares", itens:["-ar (hablar)","-er (comer)","-ir (vivir)","Presente"]}],
        questionBank: [
          {type:"mcq", prompt:"Nosotros ___ español.", choices:["hablas","hablamos","hablo","hablan"], answer:1},
          {type:"tf", prompt:"'Yo como' = eu como.", answer:true},
          {type:"open", prompt:"Conjugue 'vivir' na 1ª pessoa."},
          {type:"open", prompt:"Traduza: Ella habla inglés."},
          {type:"open", prompt:"Complete: Tú ____ (comer) pizza."},
          {type:"tf", prompt:"'-ar' indica passado.", answer:false},
          {type:"mcq", prompt:"Verbo -er:", choices:["hablar","comer","vivir","andar"], answer:1},
          {type:"open", prompt:"Escreva 3 frases com 'hablar'."},
          {type:"tf", prompt:"'Vivimos' é nós vivemos.", answer:true},
          {type:"open", prompt:"Crie uma tabela de conjugação de 'comer'."}
        ]
      },
      {
        titulo: "Vocabulario del Día a Día",
        summary: [
          "Família: madre, padre, hermano, hermana, abuelos.",
          "Casa: casa, habitación, cocina, baño.",
          "Escola: escuela, libro, profesor, alumno."
        ],
        mindmap: [{titulo:"Vocabulario cotidiano", itens:["Familia","Casa","Escuela"]}],
        questionBank: [
          {type:"mcq", prompt:"'Hermano' significa:", choices:["Pai","Irmão","Filho","Primo"], answer:1},
          {type:"tf", prompt:"'Profesor' = professor.", answer:true},
          {type:"open", prompt:"Traduza: Mi casa tiene una cocina grande."},
          {type:"open", prompt:"Três palavras de família em espanhol."},
          {type:"open", prompt:"Complete: El ____ está en la escuela. (aluno)"},
          {type:"tf", prompt:"'Abuelos' são tios.", answer:false},
          {type:"mcq", prompt:"'Banheiro' em espanhol:", choices:["habitación","cocina","baño","casa"], answer:2},
          {type:"open", prompt:"Crie frases com 'libro' e 'profesor'."},
          {type:"tf", prompt:"'Escuela' é escola.", answer:true},
          {type:"open", prompt:"Faça um diálogo curto com vocabulário da casa."}
        ]
      }
    ]
  }
];

// -----------------------------
// RENDERIZAÇÃO
// -----------------------------
let state = {
  subjectId: CURRICULUM[0].id,
  lessonIndex: 0,
  tab: "plano",
  search: ""
};

function $(sel, root=document){return root.querySelector(sel)}
function $all(sel, root=document){return [...root.querySelectorAll(sel)]}

function renderSidebar(){
  const list = $("#subjectList");
  list.innerHTML = "";
  const q = state.search.toLowerCase().trim();
  CURRICULUM.filter(s => s.nome.toLowerCase().includes(q) || s.aulas.some(a=>a.titulo.toLowerCase().includes(q))).forEach(s => {
    const el = document.createElement("div");
    el.className = "subj" + (s.id===state.subjectId ? " active" : "");
    const aulasCount = s.aulas.length;
    el.innerHTML = `<div>${s.nome}</div><small>${aulasCount} aulas</small>`;
    el.onclick = () => { state.subjectId = s.id; state.lessonIndex = 0; render(); };
    list.appendChild(el);
  });
}

function renderContent(){
  const subject = CURRICULUM.find(s=>s.id===state.subjectId);
  const lesson = subject.aulas[state.lessonIndex];
  const content = $("#content");
  const tabs = $all(".tab");
  tabs.forEach(t=>t.classList.toggle("active", t.dataset.tab===state.tab));

  // Cabeçalho com seleção de aula
  let lessonsHTML = subject.aulas.map((a,i)=>`
    <div class="lesson ${i===state.lessonIndex?"active":""}" onclick="(function(){state.lessonIndex=${i}; render();})()">
      <div><b>${a.titulo}</b></div>
      <div class="small">${a.summary[0]}</div>
    </div>
  `).join("");

  // KPI simples
  const kpi = `
    <div class="kpi">
      <div class="k"><div class="muted">Aulas</div><b>${subject.aulas.length}</b></div>
      <div class="k"><div class="muted">Questões/Simulado</div><b>20</b></div>
      <div class="k"><div class="muted">Mapa Mental</div><b>${lesson.mindmap.reduce((n,m)=>n+m.itens.length,0)} nós</b></div>
    </div>
  `;

  // Painéis por tab
  let panel = "";
  if(state.tab==="plano"){
    panel = `
      <div class="split">
        <div class="card">
          <h3>Resumo da Aula</h3>
          <ul>${lesson.summary.map(s=>`<li>${s}</li>`).join("")}</ul>
          <div class="footer">
            <button class="btn" onclick="generateQuiz(true)">Gerar simulado (20)</button>
            <button class="btn secondary" onclick="window.print()">Imprimir</button>
          </div>
        </div>
        <div class="card">
          <h3>Mapa Mental (esboço)</h3>
          <div class="mm-root">
            ${lesson.mindmap.map(m=>`
              <div class="mm-node"><b>${m.titulo}</b>${m.itens.map(i=>`<div>• ${i}</div>`).join("")}</div>
            `).join("")}
          </div>
        </div>
      </div>
      <div class="hr"></div>
      ${kpi}
      <div class="hr"></div>
      <div class="card notice">Dica: use a revisão espaçada (1, 3 e 7 dias) e faça o simulado após ler o resumo.</div>
    `;
  }
  else if(state.tab==="simulado"){
    panel = `
      <div class="card">
        <h3>Simulado – ${subject.nome} / ${lesson.titulo}</h3>
        <div class="footer">
          <button class="btn" onclick="generateQuiz(true)">Gerar simulado (20)</button>
          <button class="btn secondary" onclick="toggleAnswers()">Mostrar/ocultar gabarito</button>
        </div>
        <div id="quiz" class="quiz" style="margin-top:10px"></div>
      </div>
    `;
  }
  else if(state.tab==="mapa"){
    panel = `
      <div class="card">
        <h3>Mapa Mental – ${subject.nome} / ${lesson.titulo}</h3>
        <div class="mm-root">
          ${lesson.mindmap.map(m=>`
            <div class="mm-node"><b>${m.titulo}</b>${m.itens.map(i=>`<div>• ${i}</div>`).join("")}</div>
          `).join("")}
        </div>
      </div>
    `;
  }

  content.innerHTML = `
    <div class="grid cards-3">
      <div class="card">
        <h3>${subject.nome}</h3>
        <div class="muted">Selecione a aula:</div>
        <div class="list">${lessonsHTML}</div>
      </div>
      <div class="card" style="grid-column: span 2 / auto;">${panel}</div>
    </div>
  `;

  if(state.tab==="simulado") generateQuiz(false);
}

function shuffle(a){ for(let i=a.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[a[i],a[j]]=[a[j],a[i]]} return a }

function synthesizeQuestions(base, lesson){
  // Completa até 20 perguntas gerando prompts curtos a partir do resumo e do mapa mental
  const qs = [...base];
  const facts = (lesson.summary||[]).concat(lesson.mindmap.flatMap(m=>m.itens||[]));
  let i = 0;
  while(qs.length < 20){
    const f = facts[i % facts.length];
    if(!f){break}
    if(qs.length % 3 === 0){
      qs.push({type:"tf", prompt:`${f} (verdadeiro ou falso?)`, answer:true});
    }else if(qs.length % 3 === 1){
      qs.push({type:"open", prompt:`Explique com suas palavras: ${f}`});
    }else{
      // MCQ simples com distratores genéricos
      const stem = `Sobre: ${f}`;
      qs.push({type:"mcq", prompt:stem, choices:["Correto","Incorreto","Sem relação","Não sei"], answer:0});
    }
    i++;
    if(i>100) break;
  }
  return qs.slice(0,20);
}

function renderQuiz(questions){
  const wrap = $("#quiz");
  wrap.innerHTML = "";
  questions.forEach((q,idx)=>{
    const el = document.createElement("div");
    el.className = "q";
    const n = idx+1;
    const head = `<h4>${n}. ${q.type.toUpperCase()}</h4><div>${q.prompt}</div>`;
    let body = "";
    if(q.type==="mcq"){
      body = `<div class="choices">
        ${q.choices.map((c,i)=>`
          <label><input type="radio" name="q${idx}" value="${i}"/> <span>${c}</span></label>
        `).join("")}
      </div>
      <div class="muted answer" style="display:none">Gabarito: ${q.choices[q.answer] ?? "-"}</div>`;
    }else if(q.type==="tf"){
      body = `<div class="choices">
        <label><input type="radio" name="q${idx}" value="true"/> Verdadeiro</label>
        <label><input type="radio" name="q${idx}" value="false"/> Falso</label>
      </div>
      <div class="muted answer" style="display:none">Gabarito: ${q.answer ? "Verdadeiro" : "Falso"}</div>`;
    }else{
      body = `<div class="choices">
        <textarea rows="3" style="width:100%;background:#0a1130;color:var(--text);border:1px solid #2a2f57;border-radius:8px;padding:8px" placeholder="Escreva sua resposta..."></textarea>
      </div>`;
    }
    el.innerHTML = head + body;
    wrap.appendChild(el);
  });
}

function generateQuiz(force){
  const subject = CURRICULUM.find(s=>s.id===state.subjectId);
  const lesson = subject.aulas[state.lessonIndex];
  const qs = synthesizeQuestions(lesson.questionBank, lesson);
  if(state.tab!=="simulado" && force){ state.tab="simulado"; renderContent(); }
  renderQuiz(shuffle(qs));
}

function toggleAnswers(){
  $all(".answer").forEach(el=>{
    el.style.display = el.style.display==="none" ? "block" : "none";
  });
}

function render(){ renderSidebar(); renderContent(); }
render();

// Eventos UI
$("#search").addEventListener("input", (e)=>{ state.search = e.target.value; renderSidebar(); });
$all(".tab").forEach(t=> t.addEventListener("click", ()=>{ state.tab = t.dataset.tab; renderContent(); }));
</script>
</body>
</html>

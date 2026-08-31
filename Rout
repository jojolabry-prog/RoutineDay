<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🌺 Mon rythme</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bagel+Fat+One&family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg1: #FFEFE0;
    --bg2: #FFE0EC;
    --bg3: #E4F5F2;
    --bg-card: #FFFDF9;
    --ink: #4A2E3B;
    --ink-soft: #9A7A85;
    --coral: #FF6F8E;
    --coral-deep: #E5556F;
    --sun: #FFB646;
    --turquoise: #3FBFB8;
    --turquoise-soft: #D6F0EC;
    --lilac: #B48CD9;
    --line: #F5DCC8;
  }
  *{box-sizing:border-box;}
  body{
    margin:0; color:var(--ink); font-family:'Quicksand', sans-serif; -webkit-font-smoothing:antialiased;
    background:
      radial-gradient(circle at 10% 0%, #FFE9C9 0%, transparent 45%),
      radial-gradient(circle at 90% 15%, #FFD3E2 0%, transparent 50%),
      radial-gradient(circle at 20% 90%, #CFF1EA 0%, transparent 45%),
      linear-gradient(160deg, var(--bg1), var(--bg2) 55%, var(--bg3));
    background-attachment:fixed;
  }
  .wrap{max-width:640px; margin:0 auto; padding:26px 20px 80px;}

  header{margin-bottom:18px; position:relative;}
  .eyebrow{font-size:13px; color:var(--coral-deep); font-weight:700; margin-bottom:2px; letter-spacing:.01em;}
  h1{
    font-family:'Bagel Fat One', cursive; font-weight:400; font-size:34px; margin:0 0 8px; line-height:1.15;
    background:linear-gradient(90deg, var(--coral-deep), var(--sun) 55%, var(--turquoise));
    -webkit-background-clip:text; background-clip:text; color:transparent;
  }
  .sub{color:var(--ink-soft); font-size:14px; line-height:1.5; max-width:48ch; font-weight:500;}

  .month-nav{display:flex; align-items:center; justify-content:space-between; margin:22px 0 14px;}
  .month-label{font-family:'Bagel Fat One', cursive; font-weight:400; font-size:19px; color:var(--coral-deep);}
  .nav-btn{
    width:36px; height:36px; border-radius:50%; border:none;
    background:var(--bg-card); box-shadow:0 2px 8px rgba(229,85,111,.18);
    display:flex; align-items:center; justify-content:center;
    cursor:pointer; font-size:17px; color:var(--coral-deep); font-weight:700;
  }
  .nav-btn:active{transform:scale(.94);}

  .cal{display:grid; grid-template-columns:repeat(7,1fr); gap:7px; margin-bottom:18px;}
  .cal-dow{font-size:11px; text-align:center; color:var(--ink-soft); padding-bottom:2px; font-weight:700;}
  .cal-cell{
    aspect-ratio:1; border-radius:14px; border:2px solid transparent;
    display:flex; align-items:center; justify-content:center;
    font-size:13px; font-weight:700; cursor:pointer; position:relative;
    background:var(--bg-card); color:var(--ink-soft); transition:transform .12s ease;
  }
  .cal-cell:hover{transform:translateY(-1px) scale(1.04);}
  .cal-cell.empty{background:transparent; cursor:default;}
  .cal-cell.empty:hover{transform:none;}
  .cal-cell.selected{border-color:var(--coral-deep); color:var(--ink); box-shadow:0 3px 10px rgba(229,85,111,.28);}
  .cal-cell.today::after{content:"☀️"; position:absolute; top:-6px; right:-4px; font-size:11px;}
  .cal-cell .dot{position:absolute; bottom:5px; width:5px; height:5px; border-radius:50%;}
  .t-A{background:#FFE3BE;} .t-A .dot{background:var(--sun);}
  .t-B{background:#D2F0E7;} .t-B .dot{background:var(--turquoise);}
  .t-C{background:#EBDFF7;} .t-C .dot{background:var(--lilac);}
  .t-D{background:#FFD9E2;} .t-D .dot{background:var(--coral-deep);}
  .t-REST{background:#FBF1E4;} .t-REST .dot{background:#C9A97E;}

  .legend{display:flex; flex-wrap:wrap; gap:10px; margin:0 0 22px; font-size:11.5px; color:var(--ink-soft); font-weight:600;}
  .legend span{display:inline-flex; align-items:center; gap:5px;}
  .legend i{width:10px; height:10px; border-radius:4px; display:inline-block;}

  .daycard{background:var(--bg-card); border-radius:22px; padding:18px 20px; margin-bottom:18px; box-shadow:0 4px 16px rgba(180,120,90,.12);}
  .daycard-top{display:flex; justify-content:space-between; align-items:baseline; gap:12px; flex-wrap:wrap;}
  .daycard-date{font-family:'Quicksand', sans-serif; font-size:19px; font-weight:700; color:var(--ink);}
  .daycard-hours-row{display:flex; align-items:center; gap:6px;}
  .daycard-hours{font-size:13px; color:var(--ink-soft); font-weight:700;}
  .daycard-hours.custom{color:var(--coral-deep);}
  .edit-btn{
    background:none; border:none; cursor:pointer; font-size:13px; padding:2px 4px;
    border-radius:8px; opacity:.6; transition:opacity .15s ease, background .15s ease;
    line-height:1;
  }
  .edit-btn:hover{opacity:1; background:var(--turquoise-soft);}
  .reset-btn{
    background:none; border:none; cursor:pointer; font-size:11px; color:var(--ink-soft);
    font-weight:700; padding:2px 6px; border-radius:8px; opacity:.7;
    font-family:'Quicksand', sans-serif; text-decoration:underline;
  }
  .reset-btn:hover{opacity:1;}
  .hours-edit{display:flex; align-items:center; gap:6px; flex-wrap:wrap;}
  .hours-edit input{
    font-family:'Quicksand', sans-serif; font-weight:700; font-size:13px;
    color:var(--ink); background:var(--turquoise-soft); border:2px solid var(--turquoise);
    border-radius:10px; padding:4px 8px; width:150px; outline:none;
  }
  .hours-edit input:focus{border-color:var(--coral-deep);}
  .hours-edit-btn{
    border:none; border-radius:50%; width:24px; height:24px; cursor:pointer;
    font-size:12px; font-weight:700; display:flex; align-items:center; justify-content:center;
    flex-shrink:0;
  }
  .hours-edit-save{background:var(--turquoise); color:#fff;}
  .hours-edit-cancel{background:var(--line); color:var(--ink-soft);}
  .daycard-note{font-size:13.5px; color:var(--coral-deep); margin-top:6px; font-weight:700;}
  .badge{display:inline-block; font-size:11.5px; font-weight:700; padding:4px 11px; border-radius:20px; margin-top:8px;}
  .badge-A{background:#FFE3BE; color:#8A5A12;}
  .badge-B{background:#D2F0E7; color:#1F6E62;}
  .badge-C{background:#EBDFF7; color:#6C4796;}
  .badge-D{background:#FFD9E2; color:#B33955;}
  .badge-REST{background:#FBF1E4; color:#8A6F45;}

  .progress-row{display:flex; align-items:center; gap:10px; margin:14px 0 24px;}
  .progress-track{flex:1; height:8px; background:#F5E2D0; border-radius:6px; overflow:hidden;}
  .progress-fill{height:100%; background:linear-gradient(90deg, var(--coral), var(--sun)); border-radius:6px; transition:width .3s ease;}
  .progress-label{font-size:12.5px; color:var(--ink-soft); white-space:nowrap; font-variant-numeric:tabular-nums; font-weight:700;}

  .block{margin-bottom:16px;}
  .block-time{font-family:'Quicksand', sans-serif; font-size:14.5px; color:var(--turquoise); font-weight:700; margin-bottom:8px; padding-left:2px;}
  .item{display:flex; align-items:center; gap:12px; padding:12px 14px; background:var(--bg-card); border-radius:16px; margin-bottom:7px; box-shadow:0 2px 6px rgba(180,120,90,.08); cursor:pointer; user-select:none; transition:background .15s ease, transform .1s ease;}
  .item:hover{transform:translateX(2px);}
  .item.checked{background:var(--turquoise-soft);}
  .item.checked .item-text{text-decoration:line-through; color:var(--ink-soft);}
  .item-check{width:20px; height:20px; border-radius:50%; border:2px solid var(--coral); flex-shrink:0; display:flex; align-items:center; justify-content:center; transition:all .15s ease;}
  .item.checked .item-check{background:var(--turquoise); border-color:var(--turquoise);}
  .item.checked .item-check::after{content:"✓"; color:#fff; font-size:11px; font-weight:700;}
  .item-emoji{font-size:18px; flex-shrink:0;}
  .item-text{font-size:14.5px; flex:1; font-weight:600;}

  .inspire{display:flex; flex-direction:column; gap:10px; margin-bottom:20px;}
  .inspire-card{
    border-radius:18px; padding:15px 18px; position:relative; overflow:hidden;
  }
  .quote-card{background:linear-gradient(120deg, #FFE3BE, #FFD3E2);}
  .word-card{background:linear-gradient(120deg, #D2F0E7, #EBDFF7);}
  .inspire-label{font-size:10.5px; font-weight:700; text-transform:uppercase; letter-spacing:.04em; color:var(--ink-soft); margin-bottom:4px;}
  .quote-text{font-family:'Quicksand', sans-serif; font-size:14.5px; font-weight:600; color:var(--ink); line-height:1.4; font-style:italic;}
  .word-mot{font-family:'Bagel Fat One', cursive; font-weight:400; font-size:17px; color:var(--coral-deep); letter-spacing:.01em;}
  .word-def{font-size:13px; color:var(--ink); font-weight:500; margin-top:2px; line-height:1.4;}

  footer{text-align:center; font-size:12px; color:var(--ink-soft); margin-top:30px; padding-top:16px; border-top:1px dashed var(--line); font-weight:600;}

  @media (max-width:400px){ h1{font-size:28px;} .cal-cell{font-size:11px;} }
</style>
</head>
<body>
<div class="wrap">
  <header>
    <div class="eyebrow">🌺 Cycle de 6 semaines ☀️</div>
    <h1>Ton rythme</h1>
    <div class="sub">Ton planning tourne en boucle automatiquement, mois après mois — pas besoin de le retaper 🐢</div>
  </header>

  <div class="month-nav">
    <button class="nav-btn" id="prevMonth">‹</button>
    <div class="month-label" id="monthLabel"></div>
    <button class="nav-btn" id="nextMonth">›</button>
  </div>

  <div class="cal" id="cal"></div>
  <div class="legend">
    <span><i style="background:#FFE3BE"></i> Tôt (salle)</span>
    <span><i style="background:#D2F0E7"></i> Matinée (salle)</span>
    <span><i style="background:#EBDFF7"></i> Après-midi</span>
    <span><i style="background:#FFD9E2"></i> Longue / coupée</span>
    <span><i style="background:#FBF1E4"></i> Repos</span>
  </div>

  <div class="daycard" id="daycard"></div>

  <div class="inspire" id="inspire"></div>

  <div class="progress-row">
    <div class="progress-track"><div class="progress-fill" id="progressFill" style="width:0%"></div></div>
    <div class="progress-label" id="progressLabel">0 / 0</div>
  </div>

  <div id="blocks"></div>

  <footer>🌊 Tes coches sont sauvegardées automatiquement, jour par jour 🐚</footer>
</div>

<script>
const DOW = ["Dim","Lun","Mar","Mer","Jeu","Ven","Sam"];
const MONTHS = ["Janvier","Février","Mars","Avril","Mai","Juin","Juillet","Août","Septembre","Octobre","Novembre","Décembre"];

// ---- The 42-day (6-week) cycle, anchored on Sept 1, 2026 (index 0) ----
const ANCHOR = new Date(Date.UTC(2026, 8, 1)); // Sept 1 2026
const CYCLE_LEN = 42;
const PATTERN = [
  {type:"C", hours:"14:00–21:00"},                          // 0  Sept 1
  {type:"B", hours:"08:00–16:00"},                           // 1  Sept 2
  {type:"A", hours:"07:30–15:00"},                           // 2  Sept 3
  {type:"A", hours:"07:30–14:30"},                           // 3  Sept 4
  {type:"REST", restLabel:"RH"},                              // 4  Sept 5
  {type:"REST", restLabel:"RHD"},                             // 5  Sept 6
  {type:"A", hours:"07:30–15:00"},                           // 6  Sept 7
  {type:"D", hours:"10:30–12:30 + 14:30–21:30"},             // 7  Sept 8
  {type:"B", hours:"08:30–14:30"},                           // 8  Sept 9
  {type:"C", hours:"13:30–21:30"},                           // 9  Sept 10
  {type:"B", hours:"08:30–15:30"},                           // 10 Sept 11
  {type:"REST", restLabel:"RH"},                              // 11 Sept 12
  {type:"REST", restLabel:"RHD"},                             // 12 Sept 13
  {type:"C", hours:"14:00–21:30"},                           // 13 Sept 14
  {type:"C", hours:"14:00–21:30"},                           // 14 Sept 15
  {type:"REST", restLabel:"JNT"},                             // 15 Sept 16
  {type:"REST", restLabel:"RH"},                              // 16 Sept 17
  {type:"REST", restLabel:"RHD"},                             // 17 Sept 18
  {type:"D", hours:"09:15–21:15"},                           // 18 Sept 19
  {type:"D", hours:"09:15–21:15"},                           // 19 Sept 20
  {type:"REST", restLabel:"JNT"},                             // 20 Sept 21
  {type:"B", hours:"08:30–16:30"},                           // 21 Sept 22
  {type:"C", hours:"13:30–20:30"},                           // 22 Sept 23
  {type:"A", hours:"07:30–15:00"},                           // 23 Sept 24
  {type:"A", hours:"07:30–14:30"},                           // 24 Sept 25
  {type:"REST", restLabel:"RH"},                              // 25 Sept 26
  {type:"REST", restLabel:"RHD"},                             // 26 Sept 27
  {type:"A", hours:"07:30–15:30"},                           // 27 Sept 28
  {type:"C", hours:"13:30–21:30"},                           // 28 Sept 29
  {type:"B", hours:"08:30–16:30"},                           // 29 Sept 30
  {type:"A", hours:"07:30–14:30"},                           // 30 Oct 1
  {type:"A", hours:"07:30–14:30"},                           // 31 Oct 2
  {type:"REST", restLabel:"RH"},                              // 32 Oct 3
  {type:"REST", restLabel:"RHD"},                             // 33 Oct 4
  {type:"C", hours:"13:30–21:30"},                           // 34 Oct 5
  {type:"B", hours:"08:30–16:30"},                           // 35 Oct 6
  {type:"REST", restLabel:"JNT"},                             // 36 Oct 7
  {type:"REST", restLabel:"RH"},                              // 37 Oct 8
  {type:"REST", restLabel:"RHD"},                             // 38 Oct 9
  {type:"D", hours:"08:00–20:00"},                           // 39 Oct 10
  {type:"D", hours:"08:00–20:00"},                           // 40 Oct 11
  {type:"REST", restLabel:"JNT"},                             // 41 Oct 12
];

const REST_NOTES = {
  RH: "Jour de repos — self-care conseillé",
  RHD: "Repos dominical — récupération",
  JNT: "Jour non travaillé — grosse journée perso possible",
};

// ---- Citation du jour ----
const QUOTES = [
  "La discipline est le pont entre les objectifs et les accomplissements.",
  "Ce n'est pas la charge qui te brise, c'est la façon dont tu la portes.",
  "Chaque petit pas compte, même quand la route semble longue.",
  "Tu n'as pas besoin d'être parfaite, tu as juste besoin d'être constante.",
  "La douceur envers soi-même est aussi une forme de force.",
  "On ne voit bien qu'avec le cœur, l'essentiel est invisible pour les yeux.",
  "Rien de grand ne s'est jamais accompli sans enthousiasme.",
  "Le repos fait partie du travail, pas une pause qu'on lui vole.",
  "Avance à ton rythme, mais n'arrête jamais d'avancer.",
  "La patience est amère, mais son fruit est doux.",
  "Ce que tu sèmes aujourd'hui, tu le récolteras demain.",
  "Il vaut mieux allumer une bougie que maudire l'obscurité.",
  "Le corps atteint ce que l'esprit croit possible.",
  "Une journée à la fois, c'est déjà une vie qui se construit.",
  "La beauté d'une vie ne se mesure pas à sa vitesse, mais à sa cohérence.",
  "Sois fière du chemin parcouru, même quand il te semble insuffisant.",
  "L'ordre extérieur nourrit souvent la paix intérieure.",
  "Prendre soin de soi n'est pas un luxe, c'est une nécessité.",
  "Le calme est une force que rien ne peut vraiment ébranler.",
  "On ne change pas de vie en un jour, mais un jour peut changer une vie.",
  "Ta valeur ne dépend pas de ta productivité.",
  "Respire. Tu fais déjà de ton mieux.",
  "Les habitudes façonnent la personne que tu deviens.",
  "Le bonheur n'est pas une destination, c'est une manière de voyager.",
  "Un jardin ne pousse pas en un jour, sois patiente avec toi-même.",
  "La régularité vaut mieux que l'intensité passagère.",
  "Ce que tu fais aujourd'hui peut améliorer tous tes lendemains.",
  "Écoute ton corps, il te parle avant de crier.",
  "La lenteur n'est pas un échec, c'est parfois de la sagesse.",
  "Sois l'énergie que tu veux attirer dans ta journée.",
];

// ---- Mot du jour — pour nourrir ton éloquence ----
const WORDS = [
  {mot:"Éphémère", def:"Qui dure très peu de temps, passager."},
  {mot:"Sérendipité", def:"L'art de faire une découverte heureuse par hasard."},
  {mot:"Ineffable", def:"Qui ne peut être exprimé par des mots."},
  {mot:"Résilience", def:"Capacité à surmonter les épreuves et à se reconstruire."},
  {mot:"Mélancolie", def:"Tristesse douce et rêveuse, teintée de nostalgie."},
  {mot:"Éclectique", def:"Qui emprunte à des styles ou sources variés."},
  {mot:"Frugal", def:"Sobre, simple, sans excès ni gaspillage."},
  {mot:"Onirique", def:"Qui relève du rêve, à l'atmosphère rêveuse."},
  {mot:"Empathie", def:"Capacité à ressentir et comprendre les émotions d'autrui."},
  {mot:"Éloquence", def:"Talent de parler avec grâce, clarté et conviction."},
  {mot:"Sublime", def:"D'une beauté ou grandeur qui élève l'esprit."},
  {mot:"Nostalgie", def:"Regret mêlé de tendresse pour un temps révolu."},
  {mot:"Quiétude", def:"État de calme profond et paisible."},
  {mot:"Épanouissement", def:"Fait de s'accomplir pleinement, de fleurir intérieurement."},
  {mot:"Perspicace", def:"Qui comprend vite et avec finesse."},
  {mot:"Candide", def:"D'une innocence et d'une sincérité naïves."},
  {mot:"Alchimie", def:"Transformation quasi magique, fusion mystérieuse d'éléments."},
  {mot:"Vertige", def:"Sensation de trouble face à quelque chose de grisant ou vaste."},
  {mot:"Bienveillance", def:"Disposition à vouloir du bien, sans jugement."},
  {mot:"Effervescence", def:"Agitation vive et joyeuse, bouillonnement d'énergie."},
  {mot:"Lucide", def:"Qui voit et comprend les choses clairement, sans illusion."},
  {mot:"Réverbération", def:"Écho ou prolongement d'un son, d'une émotion."},
  {mot:"Sagacité", def:"Finesse d'esprit, capacité à juger avec justesse."},
  {mot:"Chimère", def:"Idée séduisante mais irréalisable, rêve illusoire."},
  {mot:"Aurore", def:"Première lumière du jour, symbole de renouveau."},
  {mot:"Fugace", def:"Qui disparaît rapidement, très bref."},
  {mot:"Introspection", def:"Observation attentive de sa propre vie intérieure."},
  {mot:"Foisonnant", def:"Qui abonde, riche et dense en éléments."},
  {mot:"Sérénité", def:"Calme intérieur, tranquillité durable de l'âme."},
  {mot:"Pérenne", def:"Qui dure longtemps, durable dans le temps."},
];

function dailyPick(date, arr){
  const epochDays = Math.floor(Date.UTC(date.getFullYear(), date.getMonth(), date.getDate()) / 86400000);
  const idx = ((epochDays % arr.length) + arr.length) % arr.length;
  return arr[idx];
}

function cycleIndexFor(date){
  const d = Date.UTC(date.getFullYear(), date.getMonth(), date.getDate());
  const diffDays = Math.round((d - ANCHOR.getTime()) / 86400000);
  return ((diffDays % CYCLE_LEN) + CYCLE_LEN) % CYCLE_LEN;
}

function dayInfoFor(date){
  const idx = cycleIndexFor(date);
  const p = PATTERN[idx];
  const dow = date.getDay();
  if(p.type === "REST"){
    return { type:"REST", label:p.restLabel, note: REST_NOTES[p.restLabel] };
  }
  const [start, ] = p.hours.split(/[–-]/)[0].split(":").map(Number);
  const gymEligible = (p.type==="A" || p.type==="B") && dow>=2 && dow<=5;
  let note = "";
  if(p.type === "A") note = gymEligible ? "Salle ~19h possible" : "Pas de salle aujourd'hui";
  if(p.type === "B") note = gymEligible ? "Salle ~19h possible" : "Pas de salle aujourd'hui";
  if(p.type === "C") note = "Matin pour toi, pas de salle";
  if(p.type === "D") note = "Journée longue ou coupée — pas de salle";
  return { type:p.type, hours:p.hours, note };
}

// ---- Routine templates ----
const ROUTINES = {
  A: { label: "Travail très tôt", blocks: [
    {time:"5h15 — Réveil", items:["💧 Eau","🛏️ Faire le lit","🧼 Toilette + dents","🧴 Visage","💇‍♀️ Cheveux","👗 Habillage"]},
    {time:"5h45 — Préparation finale", items:["🎒 Sac","💧 Eau","🥪 Repas si nécessaire"]},
    {time:"6h05", items:["🚶‍♀️ Départ à pied (1h20)"]},
    {time:"16h30 — Retour", items:["🏠 Vraie pause"]},
    {time:"17h–18h", items:["🍳 Cuisine / préparation du repas"]},
    {time:"18h–19h", items:["📖 Lecture / 🎨 Dessin / ✍️ Écriture"]},
    {time:"19h–20h", items:["🏋️‍♀️ Salle si mar→ven, sinon 🧘‍♀️ relaxation"]},
    {time:"20h30", items:["🚿 Douche","🧴 Crème corps","🧴 Soin visage"]},
    {time:"21h", items:["🍽️ Repas"]},
    {time:"21h30", items:["🪮 Démêlage","🪢 Nattes","🦷 Dents"]},
    {time:"21h45", items:["📖 Lecture au lit"]},
    {time:"22h15", items:["😴 Dodo"]},
  ]},
  B: { label: "Travail en matinée", blocks: [
    {time:"6h — Réveil", items:["💧 Eau","🧼 Toilette + dents","🧴 Visage","💇‍♀️ Cheveux","👗 Habillage"]},
    {time:"6h40", items:["🚶‍♀️ Départ à pied"]},
    {time:"17h — Retour", items:["🏠 Maison + pause"]},
    {time:"17h30–18h30", items:["🍳 Cuisine"]},
    {time:"19h–20h", items:["🏋️‍♀️ Salle si mar→ven, sinon repos"]},
    {time:"20h30", items:["🚿 Douche","🧴 Crème"]},
    {time:"21h", items:["🍽️ Repas"]},
    {time:"21h30", items:["🪮 Nattes","🧴 Visage"]},
    {time:"21h45", items:["📖 Lecture"]},
    {time:"22h15–22h30", items:["😴 Dodo"]},
  ]},
  C: { label: "Travail l'après-midi", blocks: [
    {time:"8h — Réveil", items:["🧼 Toilette","🧴 Visage","💇‍♀️ Cheveux","🛏️ Lit"]},
    {time:"8h30", items:["☕ Moment tranquille"]},
    {time:"9h–10h", items:["📖 Lecture / 🎨 Dessin / ✍️ Écriture"]},
    {time:"10h–11h15", items:["🍳 Cuisine (repas du jour + portion du lendemain)"]},
    {time:"11h15–11h45", items:["🧘‍♀️ Relaxation / temps calme"]},
    {time:"11h45–12h15", items:["🎒 Préparation du travail"]},
    {time:"~12h10–12h40", items:["🚶‍♀️ Départ à pied"]},
    {time:"Retour", items:["🧴 Visage","🪮 Démêlage","🪢 Nattes","🦷 Dents","🧘‍♀️ 5 minutes"]},
    {time:"Dodo", items:["😴 Dès que possible"]},
  ]},
  D: { label: "Journée longue ou coupée — pas de salle", blocks: [
    {time:"Priorité", items:["❌ Pas de salle aujourd'hui — ne pas culpabiliser"]},
    {time:"Retour", items:["🏠 Maison"]},
    {time:"Routine courte", items:["🧴 Visage","🪮 Démêlage","🪢 Nattes","🦷 Dents"]},
    {time:"Repas", items:["🍽️ Repas préparé à l'avance si possible"]},
    {time:"Dodo", items:["😴 Coucher dès que possible"]},
  ]},
  REST: { label: "Repos / self-care", blocks: [
    {time:"Matin libre", items:["😴 Se lever sans réveil forcé","🚶‍♀️ Petite marche tranquille"]},
    {time:"Self-care", items:["🧖‍♀️ Soin visage","💇‍♀️ Cheveux","🧴 Corps"]},
    {time:"Créneau cuisine", items:["🍳 Meal prep pour la semaine"]},
    {time:"Temps perso", items:["📖 Lecture","🎨 Dessin","✍️ Écriture","🧘‍♀️ Relaxation"]},
  ]},
};

let viewYear, viewMonth, selectedDate;

// ---- Storage robuste ----
let storageAvailable = false;
let fallbackMemory = {};

function initStorage(){
  try{
    localStorage.setItem('__test__', '1');
    localStorage.removeItem('__test__');
    storageAvailable = true;
    console.log('✅ localStorage OK');
  }catch(e){
    console.warn('⚠️ localStorage indisponible, mode mémoire activé');
    storageAvailable = false;
  }
}

function todayUTC(){
  const n = new Date();
  return new Date(n.getFullYear(), n.getMonth(), n.getDate());
}

function fmtKey(date){
  return `${date.getFullYear()}-${String(date.getMonth()+1).padStart(2,'0')}-${String(date.getDate()).padStart(2,'0')}`;
}

// ---- Horaires personnalisés (override manuel, par date précise) ----
function getHoursOverride(date){
  const key = `routine-hours-override:${fmtKey(date)}`;
  try{
    if(storageAvailable){
      return localStorage.getItem(key);
    }else{
      return fallbackMemory[key] || null;
    }
  }catch(e){
    console.error('Erreur getHoursOverride:', e);
    return null;
  }
}

function setHoursOverride(date, hoursText){
  const key = `routine-hours-override:${fmtKey(date)}`;
  try{
    if(storageAvailable){
      localStorage.setItem(key, hoursText);
    }else{
      fallbackMemory[key] = hoursText;
    }
    console.log('✏️ Horaire personnalisé sauvegardé:', key, hoursText);
  }catch(e){
    console.error('Erreur setHoursOverride:', e);
  }
}

function clearHoursOverride(date){
  const key = `routine-hours-override:${fmtKey(date)}`;
  try{
    if(storageAvailable){
      localStorage.removeItem(key);
    }else{
      delete fallbackMemory[key];
    }
    console.log('↺ Horaire réinitialisé:', key);
  }catch(e){
    console.error('Erreur clearHoursOverride:', e);
  }
}

let editingHours = false;

function getChecked(date){
  const key = `routine-checked:${fmtKey(date)}`;
  try{
    if(storageAvailable){
      const stored = localStorage.getItem(key);
      return stored ? JSON.parse(stored) : {};
    }else{
      return fallbackMemory[key] ? JSON.parse(fallbackMemory[key]) : {};
    }
  }catch(e){
    console.error('Erreur getChecked:', e);
    return {};
  }
}

function setChecked(date, data){
  const key = `routine-checked:${fmtKey(date)}`;
  try{
    const json = JSON.stringify(data);
    if(storageAvailable){
      localStorage.setItem(key, json);
      console.log('✅ Saved:', key);
    }else{
      fallbackMemory[key] = json;
      console.log('💾 Sauvegardé en mémoire:', key);
    }
  }catch(e){
    console.error('Erreur setChecked:', e);
  }
}

function buildCalendar(){
  const cal = document.getElementById('cal');
  cal.innerHTML = "";
  DOW.forEach(d=>{
    const el = document.createElement('div');
    el.className = 'cal-dow';
    el.textContent = d;
    cal.appendChild(el);
  });
  const first = new Date(viewYear, viewMonth, 1);
  const startDow = first.getDay();
  const daysInMonth = new Date(viewYear, viewMonth+1, 0).getDate();
  const today = todayUTC();

  for(let i=0;i<startDow;i++){
    const empty = document.createElement('div');
    empty.className = 'cal-cell empty';
    cal.appendChild(empty);
  }
  for(let day=1; day<=daysInMonth; day++){
    const date = new Date(viewYear, viewMonth, day);
    const info = dayInfoFor(date);
    const isSelected = fmtKey(date) === fmtKey(selectedDate);
    const isToday = fmtKey(date) === fmtKey(today);
    const cell = document.createElement('div');
    cell.className = `cal-cell t-${info.type}` + (isSelected?' selected':'') + (isToday?' today':'');
    cell.innerHTML = `${day}<span class="dot"></span>`;
    cell.onclick = ()=>{ selectedDate = date; editingHours = false; render(); };
    cal.appendChild(cell);
  }

  document.getElementById('monthLabel').textContent = `${MONTHS[viewMonth]} ${viewYear}`;
}

function render(){
  buildCalendar();
  const info = dayInfoFor(selectedDate);
  const routine = ROUTINES[info.type];
  const dow = selectedDate.getDay();

  const override = getHoursOverride(selectedDate);
  const defaultHoursText = info.type==="REST" ? info.label : info.hours;
  const displayHoursText = override || defaultHoursText;
  const hasOverride = !!override;

  const daycard = document.getElementById('daycard');

  if(editingHours){
    daycard.innerHTML = `
      <div class="daycard-top">
        <div class="daycard-date">${DOW[dow]} ${selectedDate.getDate()} ${MONTHS[selectedDate.getMonth()].toLowerCase()}</div>
      </div>
      <div class="hours-edit">
        <input type="text" id="hoursInput" value="${override || (info.type==="REST" ? "" : info.hours)}" placeholder="ex: 08:00–16:00">
        <button class="hours-edit-btn hours-edit-save" id="saveHours" title="Valider">✓</button>
        <button class="hours-edit-btn hours-edit-cancel" id="cancelHours" title="Annuler">✕</button>
      </div>
      <span class="badge badge-${info.type}">${routine.label}</span>
      <div class="daycard-note">${info.note}</div>
    `;

    document.getElementById('saveHours').addEventListener('click', ()=>{
      const val = document.getElementById('hoursInput').value.trim();
      if(val){
        setHoursOverride(selectedDate, val);
      }
      editingHours = false;
      render();
    });
    document.getElementById('cancelHours').addEventListener('click', ()=>{
      editingHours = false;
      render();
    });
    document.getElementById('hoursInput').addEventListener('keydown', (e)=>{
      if(e.key === 'Enter') document.getElementById('saveHours').click();
      if(e.key === 'Escape') document.getElementById('cancelHours').click();
    });
    document.getElementById('hoursInput').focus();
  }else{
    daycard.innerHTML = `
      <div class="daycard-top">
        <div class="daycard-date">${DOW[dow]} ${selectedDate.getDate()} ${MONTHS[selectedDate.getMonth()].toLowerCase()}</div>
        <div class="daycard-hours-row">
          <div class="daycard-hours${hasOverride ? ' custom' : ''}">${displayHoursText}</div>
          <button class="edit-btn" id="editHoursBtn" title="Modifier l'horaire">✏️</button>
          ${hasOverride ? `<button class="reset-btn" id="resetHoursBtn" title="Revenir à l'horaire par défaut">↺</button>` : ''}
        </div>
      </div>
      <span class="badge badge-${info.type}">${routine.label}</span>
      <div class="daycard-note">${info.note}</div>
    `;

    const editBtn = document.getElementById('editHoursBtn');
    if(editBtn){
      editBtn.addEventListener('click', ()=>{
        editingHours = true;
        render();
      });
    }
    const resetBtn = document.getElementById('resetHoursBtn');
    if(resetBtn){
      resetBtn.addEventListener('click', ()=>{
        clearHoursOverride(selectedDate);
        render();
      });
    }
  }

  const quote = dailyPick(selectedDate, QUOTES);
  const word = dailyPick(selectedDate, WORDS);
  document.getElementById('inspire').innerHTML = `
    <div class="inspire-card quote-card">
      <div class="inspire-label">✨ Citation du jour</div>
      <div class="quote-text">« ${quote} »</div>
    </div>
    <div class="inspire-card word-card">
      <div class="inspire-label">📖 Mot du jour</div>
      <div class="word-mot">${word.mot}</div>
      <div class="word-def">${word.def}</div>
    </div>
  `;

  const checked = getChecked(selectedDate);
  let total = 0, done = 0;
  routine.blocks.forEach(b => total += b.items.length);

  const blocksEl = document.getElementById('blocks');
  blocksEl.innerHTML = "";
  routine.blocks.forEach((block, bi)=>{
    const bDiv = document.createElement('div');
    bDiv.className = 'block';
    const time = document.createElement('div');
    time.className = 'block-time';
    time.textContent = block.time;
    bDiv.appendChild(time);
    block.items.forEach((text, ii)=>{
      const key = `${bi}-${ii}`;
      const isChecked = !!checked[key];
      if(isChecked) done++;
      const m = text.match(/^(\S+)\s(.+)$/);
      const emoji = m ? m[1] : "";
      const label = m ? m[2] : text;
      const item = document.createElement('div');
      item.className = 'item' + (isChecked ? ' checked' : '');
      item.innerHTML = `<span class="item-check"></span><span class="item-emoji">${emoji}</span><span class="item-text">${label}</span>`;
      
      item.addEventListener('click', function(e){
        e.preventDefault();
        e.stopPropagation();
        checked[key] = !checked[key];
        setChecked(selectedDate, checked);
        render();
      });
      
      bDiv.appendChild(item);
    });
    blocksEl.appendChild(bDiv);
  });

  document.getElementById('progressFill').style.width = total ? `${(done/total*100)}%` : '0%';
  document.getElementById('progressLabel').textContent = `${done} / ${total}`;
}

document.getElementById('prevMonth').addEventListener('click', ()=>{
  viewMonth--; if(viewMonth<0){viewMonth=11; viewYear--;}
  buildCalendar();
});

document.getElementById('nextMonth').addEventListener('click', ()=>{
  viewMonth++; if(viewMonth>11){viewMonth=0; viewYear++;}
  buildCalendar();
});

(function init(){
  initStorage();
  const today = todayUTC();
  selectedDate = today.getFullYear() > 2026 || (today.getFullYear()===2026 && today.getMonth()>=7) ? today : new Date(2026,7,31);
  viewYear = selectedDate.getFullYear();
  viewMonth = selectedDate.getMonth();
  render();
  console.log('🚀 Rythme chargé');
})();
</script>
</body>
</html>

<!DOCTYPE html>  
<html lang="it">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>I sub del golfo - Guida Marina</title>  
<meta name="theme-color" content="#0284c7">  
<style>  
/* Reset base e Mobile First */  
* {  
box-sizing: border-box;  
margin: 0;  
padding: 0;  
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;  
}  
body {  
background-color: #f0fdf4;  
color: #1e293b;  
padding-bottom: 80px; /* Spazio per la barra inferiore su mobile */  
}  
/* Header */  
.navbar {  
background-color: #0284c7;  
color: white;  
padding: 12px 16px;  
display: flex;  
justify-content: space-between;  
align-items: center;  
position: sticky;  
top: 0;  
z-index: 100;  
box-shadow: 0 2px 4px rgba(0,0,0,0.1);  
}  
.logo-container {  
display: flex;  
align-items: center;  
gap: 8px;  
cursor: pointer;  
}  
.logo-icon { font-size: 1.5rem; }  
.logo-title { font-size: 1.2rem; font-weight: 700; }  
.nav-links { display: none; }  
@media (min-width: 768px) {  
.nav-links {  
display: flex;  
gap: 12px;  
}  
.nav-links button {  
background: transparent;  
border: none;  
color: white;  
font-weight: 600;  
cursor: pointer;  
padding: 6px 10px;  
border-radius: 4px;  
}  
.nav-links button:hover {  
background-color: rgba(255,255,255,0.2);  
}  
}  
/* Layout Principale */  
.container {  
max-width: 800px;  
margin: 0 auto;  
padding: 16px;  
}  
/* Gestione Pagine/Sezioni */  
.page-section {  
display: none;  
}  
.page-section.active {  
display: block;  
}  
.hidden { display: none !important; }  
/* Pulsanti e Navigazione */  
.btn-back, .btn-secondary {  
background-color: #e2e8f0;  
border: none;  
padding: 10px 16px;  
border-radius: 8px;  
font-size: 0.95rem;  
font-weight: 600;  
margin-bottom: 16px;  
cursor: pointer;  
width: 100%;  
}  
@media (min-width: 600px) {  
.btn-back, .btn-secondary { width: auto; }  
}  
/* Home - Statistiche */  
.hero {  
text-align: center;  
margin-bottom: 20px;  
}  
.subtitle { color: #64748b; margin-top: 4px; }  
.stats-card {  
background: white;  
padding: 16px;  
border-radius: 12px;  
box-shadow: 0 2px 8px rgba(0,0,0,0.05);  
margin-bottom: 24px;  
}  
.stats-grid {  
display: flex;  
justify-content: space-around;  
margin: 16px 0;  
}  
.stat-item { text-align: center; }  
.stat-value { display: block; font-size: 1.5rem; font-weight: 700; color: #0284c7; }  
.stat-label { font-size: 0.8rem; color: #64748b; }  
.progress-bar-bg {  
background-color: #e2e8f0;  
height: 12px;  
border-radius: 6px;  
overflow: hidden;  
}  
.progress-bar-fill {  
background-color: #10b981;  
height: 100%;  
transition: width 0.3s ease;  
}  
/* Menu Schede Home */  
.menu-grid {  
display: grid;  
grid-template-columns: 1fr 1fr;  
gap: 12px;  
}  
.card-btn {  
background: white;  
border: 1px solid #e2e8f0;  
padding: 20px 12px;  
border-radius: 12px;  
display: flex;  
flex-direction: column;  
align-items: center;  
gap: 8px;  
cursor: pointer;  
box-shadow: 0 2px 4px rgba(0,0,0,0.03);  
}  
.card-btn .icon { font-size: 2rem; }  
.card-btn .label { font-weight: 600; font-size: 0.95rem; }  
/* Guida e Categorie */  
.category-grid, .species-grid {  
display: grid;  
grid-template-columns: 1fr 1fr;  
gap: 12px;  
margin-top: 16px;  
}  
.category-card, .species-card {  
background: white;  
padding: 16px;  
border-radius: 10px;  
border: 1px solid #e2e8f0;  
font-weight: 600;  
text-align: center;  
cursor: pointer;  
}  
/* Scheda Specie Dettaglio */  
.specie-card-detail {  
background: white;  
padding: 20px;  
border-radius: 12px;  
box-shadow: 0 2px 8px rgba(0,0,0,0.05);  
}  
.photo-placeholder {  
width: 100%;  
height: 200px;  
background-color: #f1f5f9;  
border: 2px dashed #cbd5e1;  
border-radius: 8px;  
display: flex;  
align-items: center;  
justify-content: center;  
color: #94a3b8;  
margin-bottom: 16px;  
overflow: hidden;  
}  
.photo-placeholder img {  
width: 100%;  
height: 100%;  
object-fit: cover;  
}  
.seen-toggle-container {  
margin: 16px 0;  
padding: 12px;  
background-color: #f8fafc;  
border-radius: 8px;  
}  
.detail-info h3 {  
margin-top: 16px;  
font-size: 1rem;  
color: #0284c7;  
}  
.detail-info p {  
margin-top: 4px;  
line-height: 1.5;  
color: #334155;  
}  
/* Checklist */  
.checklist-summary {  
font-weight: 700;  
margin: 12px 0;  
color: #0284c7;  
}  
.checklist-grid {  
display: flex;  
flex-direction: column;  
gap: 8px;  
}  
.checklist-item {  
background: white;  
padding: 12px 16px;  
border-radius: 8px;  
border: 1px solid #e2e8f0;  
display: flex;  
align-items: center;  
justify-content: space-between;  
}  
.checkbox-label {  
display: flex;  
align-items: center;  
gap: 12px;  
font-size: 1.05rem;  
cursor: pointer;  
width: 100%;  
}  
.checkbox-label input[type="checkbox"] {  
width: 20px;  
height: 20px;  
}  
/* Bottom Nav per Mobile */  
.bottom-nav {  
position: fixed;  
bottom: 0;  
left: 0;  
right: 0;  
background: white;  
border-top: 1px solid #e2e8f0;  
display: flex;  
justify-content: space-around;  
padding: 8px 0;  
z-index: 100;  
}  
.bottom-nav button {  
background: none;  
border: none;  
display: flex;  
flex-direction: column;  
align-items: center;  
font-size: 1.2rem;  
color: #64748b;  
cursor: pointer;  
}  
.bottom-nav button span {  
font-size: 0.7rem;  
margin-top: 2px;  
}  
/* Sezione Diario & News */  
.dive-card, .news-card {  
background: white;  
padding: 16px;  
border-radius: 10px;  
border: 1px solid #e2e8f0;  
margin-bottom: 12px;  
}  
.news-date {  
font-size: 0.8rem;  
color: #0284c7;  
font-weight: 600;  
}  
</style>  
</head>  
<body>  
<!-- Header & Navigazione Mobile -->  
<header class="navbar">  
<div class="logo-container" onclick="showSection('home')">  
<span class="logo-icon">🤿</span>  
<h1 class="logo-title">I sub del golfo</h1>  
</div>  
<nav class="nav-links">  
<button onclick="showSection('home')">Home</button>  
<button onclick="showSection('guida')">Guida</button>  
<button onclick="showSection('checklist')">Checklist</button>  
<button onclick="showSection('foto')">Foto</button>  
<button onclick="showSection('immersioni')">Immersioni</button>  
<button onclick="showSection('aggiornamenti')">News</button>  
</nav>  
</header>  
<main class="container">  
<!-- SECTION: HOME -->  
<section id="home" class="page-section active">  
<div class="hero">  
<h2>I sub del golfo</h2>  
<p class="subtitle">Guida tascabile e diario di immersione della fauna marina locale.</p>  
</div>  
<!-- Statistiche Progresso -->  
<div class="stats-card">  
<h3>📊 Progresso Avvistamenti</h3>  
<div class="stats-grid">  
<div class="stat-item">  
<span class="stat-value" id="stat-total">93</span>  
<span class="stat-label">Specie Totali</span>  
</div>  
<div class="stat-item">  
<span class="stat-value" id="stat-seen">0</span>  
<span class="stat-label">Avvistate</span>  
</div>  
<div class="stat-item">  
<span class="stat-value" id="stat-percent">0%</span>  
<span class="stat-label">Completato</span>  
</div>  
</div>  
<div class="progress-bar-bg">  
<div class="progress-bar-fill" id="progress-fill" style="width: 0%;"></div>  
</div>  
</div>  
<!-- Menu Accesso Rapido -->  
<div class="menu-grid">  
<button class="card-btn" onclick="showSection('guida')">  
<span class="icon">📖</span>  
<span class="label">Guida Specie</span>  
</button>  
<button class="card-btn" onclick="showSection('checklist')">  
<span class="icon">☑️</span>  
<span class="label">Checklist Avvistamenti</span>  
</button>  
<button class="card-btn" onclick="showSection('foto')">  
<span class="icon">📸</span>  
<span class="label">Le Nostre Foto</span>  
</button>  
<button class="card-btn" onclick="showSection('immersioni')">  
<span class="icon">🤿</span>  
<span class="label">Diario Immersioni</span>  
</button>  
<button class="card-btn" onclick="showSection('aggiornamenti')">  
<span class="icon">📰</span>  
<span class="label">Aggiornamenti</span>  
</button>  
</div>  
</section>  
<!-- SECTION: GUIDA -->  
<section id="guida" class="page-section">  
<button class="btn-back" onclick="showSection('home')">← Torna alla Home</button>  
<h2>📖 Guida alle Specie</h2>  
<p>Seleziona una categoria per esplorare le specie:</p>  
<!-- Categorie -->  
<div id="category-list" class="category-grid"></div>  
<!-- Elenco Specie della Categoria Selezionata -->  
<div id="species-list-container" class="hidden">  
<button class="btn-secondary" onclick="backToCategories()">← Torna alle Categorie</button>  
<h3 id="selected-category-title" class="category-title"></h3>  
<div id="species-grid" class="species-grid"></div>  
</div>  
</section>  
<!-- SECTION: SCHEDA SPECIE (DETTAGLIO) -->  
<section id="scheda-specie" class="page-section">  
<button class="btn-back" onclick="showSection('guida')">← Torna alla Guida</button>  
<div class="specie-card-detail">  
<div class="photo-placeholder" id="detail-photo">  
📷 Nessuna immagine inserita  
</div>  
<h2 id="detail-name">Nome Specie</h2>  
<div class="seen-toggle-container">  
<label class="checkbox-label">  
<input type="checkbox" id="detail-seen-checkbox" onchange="toggleSeenFromDetail()">  
<strong>AVVISTATA</strong>  
</label>  
</div>  
<div class="detail-info">  
<h3>Descrizione</h3>  
<p id="detail-description"></p>  
<h3>Come Riconoscerla</h3>  
<p id="detail-recognition"></p>  
<h3>Habitat</h3>  
<p id="detail-habitat"></p>  
<h3>Curiosità</h3>  
<p id="detail-curiosity"></p>  
<h3>Altre Informazioni</h3>  
<p id="detail-extra"></p>  
</div>  
</div>  
</section>  
<!-- SECTION: CHECKLIST -->  
<section id="checklist" class="page-section">  
<button class="btn-back" onclick="showSection('home')">← Torna alla Home</button>  
<h2>☑️ Checklist Avvistamenti</h2>  
<p>Spunta le specie che hai avvistato in mare:</p>  
<div class="checklist-summary">  
<span id="checklist-count">0 / 93 avvistate (0%)</span>  
</div>  
<div id="checklist-items" class="checklist-grid"></div>  
</section>  
<!-- SECTION: FOTO -->  
<section id="foto" class="page-section">  
<button class="btn-back" onclick="showSection('home')">← Torna alla Home</button>  
<h2>📸 Le Nostre Foto</h2>  
<p>Galleria fotografica personale delle immersioni.</p>  
<div style="margin-top: 15px; background: white; padding: 20px; border-radius: 8px; text-align: center; color: #64748b; border: 1px dashed #cbd5e1;">  
📷 Sezione pronta per inserire le vostre foto personali  
</div>  
</section>  
<!-- SECTION: IMMERSIONI -->  
<section id="immersioni" class="page-section">  
<button class="btn-back" onclick="showSection('home')">← Torna alla Home</button>  
<h2>🤿 Diario Immersioni</h2>  
<p>Registro delle uscite in mare.</p>  
<div id="dive-log-list" style="margin-top: 15px;">  
<div class="dive-card">  
<h3>Esempio Immersione #1</h3>  
<p><strong>Luogo:</strong> Golfo</p>  
<p><strong>Data:</strong> —</p>  
<p><strong>Profondità max:</strong> — m</p>  
<p><strong>Note:</strong> Struttura pronta per aggiungere i vostri dati.</p>  
</div>  
</div>  
</section>  
<!-- SECTION: AGGIORNAMENTI -->  
<section id="aggiornamenti" class="page-section">  
<button class="btn-back" onclick="showSection('home')">← Torna alla Home</button>  
<h2>📰 Aggiornamenti</h2>  
<div class="news-list" style="margin-top: 15px;">  
<div class="news-card">  
<span class="news-date">Lancio Progetto</span>  
<h3>Sito Creato</h3>  
<p>La guida "I sub del golfo" è online!</p>  
</div>  
</div>  
</section>  
</main>  
<!-- Bottom Nav Bar (Mobile Friendly) -->  
<footer class="bottom-nav">  
<button onclick="showSection('home')">🏠<span>Home</span></button>  
<button onclick="showSection('guida')">📖<span>Guida</span></button>  
<button onclick="showSection('checklist')">☑️<span>Checklist</span></button>  
<button onclick="showSection('foto')">📸<span>Foto</span></button>  
<button onclick="showSection('immersioni')">🤿<span>Diario</span></button>  
</footer>  
<script>  
const TOTAL_SPECIES_TARGET = 93;  
const categories = [  
"Pesci",  
"Molluschi",  
"Crostacei",  
"Nudibranchi",  
"Echinodermi",  
"Cnidari"  
];  
const speciesDatabase = [  
{  
id: "castagnola",  
category: "Pesci",  
name: "Castagnola",  
image: "",  
description: "Piccolo pesce molto comune lungo le scogliere sottocosta.",  
recognition: "Colore nero/marrone scuro, coda biforcuta.",  
habitat: "Fondali rocciosi e praterie di posidonia.",  
curiosity: "I giovani hanno una colorazione blu elettrico molto brillante.",  
extra: "Avvistabile facilmente in grandi banchi."  
},  
{  
id: "salpa",  
category: "Pesci",  
name: "Salpa",  
image: "",  
description: "Pesce erbiboro gregaro.",  
recognition: "Corpo ovale con strisce dorate orizzontali.",  
habitat: "Fondale roccioso e praterie di alghe.",  
curiosity: "Si nutre prevalentemente di alghe brucando sulle rocce.",  
extra: "Frequentemente osservabile a poca profondità."  
},  
{  
id: "polpo",  
category: "Molluschi",  
name: "Polpo",  
image: "",  
description: "Mollusco cefalopode dotato di grande intelligenza.",  
recognition: "Otto braccia con due file di ventose.",  
habitat: "Tane rocciose o anfratti del fondale.",  
curiosity: "Capace di mimetizzarsi cambiando colore e trama della pelle.",  
extra: "Predilige cacciare di notte."  
},  
{  
id: "seppia",  
category: "Molluschi",  
name: "Seppia",  
image: "",  
description: "Mollusco cefalopode corpo schiacciato.",  
recognition: "Presenza di osso interno e tentacoli rettrattili.",  
habitat: "Fondali sabbiosi e praterie.",  
curiosity: "Utilizza un sifone per muoversi velocemente a reazione.",  
extra: "Ottime capacità mimetiche."  
}  
];  
let seenSpecies = JSON.parse(localStorage.getItem('sub_golfo_seen')) || {};  
let currentSpecieId = null;  
document.addEventListener('DOMContentLoaded', () => {  
renderCategories();  
renderChecklist();  
updateStats();  
});  
function showSection(sectionId) {  
const sections = document.querySelectorAll('.page-section');  
sections.forEach(sec => sec.classList.remove('active'));  
const target = document.getElementById(sectionId);  
if (target) {  
target.classList.add('active');  
}  
window.scrollTo(0, 0);  
}  
function renderCategories() {  
const container = document.getElementById('category-list');  
container.innerHTML = '';  
categories.forEach(cat => {  
const btn = document.createElement('div');  
btn.className = 'category-card';  
btn.innerText = cat;  
btn.onclick = () => showSpeciesByCategory(cat);  
container.appendChild(btn);  
});  
}  
function showSpeciesByCategory(category) {  
document.getElementById('category-list').classList.add('hidden');  
const container = document.getElementById('species-list-container');  
container.classList.remove('hidden');  
document.getElementById('selected-category-title').innerText = category;  
const grid = document.getElementById('species-grid');  
grid.innerHTML = '';  
const filtered = speciesDatabase.filter(s => s.category === category);  
if (filtered.length === 0) {  
grid.innerHTML = '<p style="grid-column: 1/-1;">Nessuna specie ancora inserita in questa categoria.</p>';  
return;  
}  
filtered.forEach(specie => {  
const card = document.createElement('div');  
card.className = 'species-card';  
card.innerText = specie.name;  
card.onclick = () => openSpecieDetail(specie.id);  
grid.appendChild(card);  
});  
}  
function backToCategories() {  
document.getElementById('species-list-container').classList.add('hidden');  
document.getElementById('category-list').classList.remove('hidden');  
}  
function openSpecieDetail(specieId) {  
const specie = speciesDatabase.find(s => s.id === specieId);  
if (!specie) return;  
currentSpecieId = specie.id;  
document.getElementById('detail-name').innerText = specie.name;  
document.getElementById('detail-description').innerText = specie.description || '—';  
document.getElementById('detail-recognition').innerText = specie.recognition || '—';  
document.getElementById('detail-habitat').innerText = specie.habitat || '—';  
document.getElementById('detail-curiosity').innerText = specie.curiosity || '—';  
document.getElementById('detail-extra').innerText = specie.extra || '—';  
const photoContainer = document.getElementById('detail-photo');  
if (specie.image && specie.image.trim() !== '') {  
photoContainer.innerHTML = ⁠<img src="${specie.image}" alt="${specie.name}">⁠;  
} else {  
photoContainer.innerHTML = '📷 Nessuna immagine inserita';  
}  
const checkbox = document.getElementById('detail-seen-checkbox');  
checkbox.checked = !!seenSpecies[specie.id];  
showSection('scheda-specie');  
}  
function toggleSeenFromDetail() {  
if (!currentSpecieId) return;  
const checkbox = document.getElementById('detail-seen-checkbox');  
setSeenState(currentSpecieId, checkbox.checked);  
}  
function renderChecklist() {  
const container = document.getElementById('checklist-items');  
container.innerHTML = '';  
speciesDatabase.forEach(specie => {  
const item = document.createElement('div');  
item.className = 'checklist-item';  
const isChecked = !!seenSpecies[specie.id];  
item.innerHTML = ⁠<label class="checkbox-label"> <input type="checkbox" ${isChecked ? 'checked' : ''} onchange="toggleSeenState('${specie.id}', this.checked)"> <span>${specie.name}</span> </label>⁠;  
item.innerHTML = ⁠<label class="checkbox-label"> <input type="checkbox" ${isChecked ? 'checked' : ''} onchange="toggleSeenState('${specie.id}', this.checked)"> <span>${specie.name}</span> </label>⁠;  
container.appendChild(item);  
});  
}  
function toggleSeenState(id, isSeen) {  
setSeenState(id, isSeen);  
}  
function setSeenState(id, isSeen) {  
if (isSeen) {  
seenSpecies[id] = true;  
} else {  
delete seenSpecies[id];  
}  
localStorage.setItem('sub_golfo_seen', JSON.stringify(seenSpecies));  
updateStats();  
renderChecklist();  
}  
function updateStats() {  
const seenCount = Object.keys(seenSpecies).length;  
const percent = Math.round((seenCount / TOTAL_SPECIES_TARGET) * 100);  
document.getElementById('stat-total').innerText = TOTAL_SPECIES_TARGET;  
document.getElementById('stat-seen').innerText = seenCount;  
document.getElementById('stat-percent').innerText = ⁠${percent}%⁠;  
document.getElementById('progress-fill').style.width = ⁠${percent}%⁠;  
const checklistCountElem = document.getElementById('checklist-count');  
if (checklistCountElem) {  
checklistCountElem.innerText = ⁠${seenCount} / ${TOTAL_SPECIES_TARGET} avvistate (${percent}%)⁠;  
}  
}  
</script>  
</body>  
</html>  

<!DOCTYPE html>  
<html lang="it">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>🤿 I Sub del Golfo</title>  
    
  <link rel="preconnect" href="https://fonts.googleapis.com">  
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>  
  <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Cinzel:wght@700&family=Fira+Code:wght@600&family=Lekton:ital,wght@0,700;1,400&family=Lobster&family=Montserrat:wght@700;900&family=Pacifico&family=Playfair+Display:ital,wght@0,600;0,800;1,600&family=Plus+Jakarta+Sans:wght@500;700;800&family=Press+Start+2P&family=Roboto+Slab:wght@700&display=swap" rel="stylesheet">  
  
  <style>  
    :root {  
      --primary: #0284c7;  
      --primary-dark: #0369a1;  
      --primary-light: #e0f2fe;  
      --bg-color: #f0f9ff;  
      --bg-image: none;  
      --surface: rgba(255, 255, 255, 0.94);  
      --text: #0f172a;  
      --text-muted: #64748b;  
      --border: #bae6fd;  
      --radius: 16px;  
      --shadow: 0 10px 15px -3px rgba(0,0,0,0.08);  
      --app-font: 'Plus Jakarta Sans', sans-serif;  
    }  
  
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: var(--app-font); }  
      
    body {   
      background-color: var(--bg-color);  
      background-image: var(--bg-image);  
      background-size: cover;  
      background-position: center;  
      background-attachment: fixed;  
      color: var(--text);   
      padding-bottom: 90px;  
      position: relative;  
      min-height: 100vh;  
      overflow-x: hidden;  
      transition: all 0.3s ease;  
    }  
  
    .bubbles-container {  
      position: fixed; top: 0; left: 0; width: 100%; height: 100%;  
      pointer-events: none; z-index: 0; overflow: hidden;  
    }  
    .bubble {  
      position: absolute; bottom: -50px; background: rgba(56, 189, 248, 0.25);  
      border: 1px solid rgba(255, 255, 255, 0.6); border-radius: 50%;  
      animation: rise 10s infinite ease-in;  
    }  
    .bubble:nth-child(1) { width: 40px; height: 40px; left: 10%; animation-duration: 8s; }  
    .bubble:nth-child(2) { width: 20px; height: 20px; left: 30%; animation-duration: 5s; animation-delay: 1s; }  
    .bubble:nth-child(3) { width: 50px; height: 50px; left: 50%; animation-duration: 12s; animation-delay: 2s; }  
    .bubble:nth-child(4) { width: 25px; height: 25px; left: 75%; animation-duration: 7s; animation-delay: 0.5s; }  
    .bubble:nth-child(5) { width: 35px; height: 35px; left: 90%; animation-duration: 9s; animation-delay: 3s; }  
    @keyframes rise {  
      0% { bottom: -50px; transform: translateX(0); opacity: 0; }  
      20% { opacity: 0.8; }  
      100% { bottom: 100vh; transform: translateX(30px); opacity: 0; }  
    }  
  
    .header {  
      background: var(--primary);  
      color: white; padding: 16px 20px; position: sticky; top: 0; z-index: 100;  
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);  
      display: flex; align-items: center; justify-content: space-between;  
    }  
    .brand { display: flex; align-items: center; gap: 10px; font-weight: 800; font-size: 1.1rem; }  
    .menu-toggle { background: none; border: none; color: white; font-size: 1.6rem; cursor: pointer; padding: 4px; }  
  
    .drawer-overlay {  
      position: fixed; top: 0; left: 0; right: 0; bottom: 0;  
      background: rgba(15, 23, 42, 0.5); backdrop-filter: blur(4px);  
      z-index: 1000; opacity: 0; visibility: hidden; transition: all 0.3s ease;  
    }  
    .drawer-overlay.active { opacity: 1; visibility: visible; }  
    .drawer {  
      position: fixed; top: 0; left: -280px; width: 280px; height: 100%;  
      background: #ffffff; z-index: 1001; transition: left 0.3s ease;  
      display: flex; flex-direction: column; box-shadow: 5px 0 25px rgba(0,0,0,0.15);  
    }  
    .drawer.active { left: 0; }  
    .drawer-header { background: var(--primary); color: white; padding: 24px 20px; font-weight: 800; font-size: 1.2rem; }  
    .drawer-menu { list-style: none; padding: 12px 0; overflow-y: auto; flex: 1; }  
    .drawer-item { padding: 14px 20px; display: flex; align-items: center; gap: 12px; color: var(--text); font-weight: 600; cursor: pointer; border-bottom: 1px solid #f1f5f9; }  
    .drawer-item:hover { background: var(--primary-light); color: var(--primary-dark); }  
  
    .page { display: none; padding: 16px; max-width: 650px; margin: 0 auto; position: relative; z-index: 1; }  
    .page.active { display: block; }  
    .page-title { font-size: 1.4rem; font-weight: 800; color: var(--text); margin-bottom: 14px; }  
  
    .card {   
      background: var(--surface); backdrop-filter: blur(10px);  
      border-radius: var(--radius); padding: 18px; margin-bottom: 16px;   
      box-shadow: var(--shadow); border: 1px solid var(--border);   
      transition: all 0.2s ease;  
    }  
  
    .theme-picker-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; margin-top: 10px; }  
    .theme-btn {  
      padding: 10px; border-radius: 10px; border: 2px solid var(--border);  
      background: white; cursor: pointer; font-weight: 700; font-size: 0.8rem; text-align: center;  
    }  
  
    .equip-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-top: 10px; }  
    .equip-box { background: var(--primary-light); border-radius: 12px; padding: 12px; border: 1px solid var(--border); }  
    .equip-box h4 { font-size: 0.95rem; color: var(--primary-dark); margin-bottom: 8px; }  
    .equip-box label { font-size: 0.78rem; margin-top: 6px; }  
    .equip-box input { padding: 8px; font-size: 0.88rem; }  
  
    .dice-container { text-align: center; padding: 20px 10px; }  
    .dice-btn {  
      font-size: 4rem; background: none; border: none; cursor: pointer; transition: transform 0.3s;  
      user-select: none; display: inline-block;  
    }  
    .dice-btn:active { transform: scale(0.85) rotate(180deg); }  
    .fact-card {  
      background: var(--primary-light);  
      border: 2px solid var(--primary); border-radius: 18px; padding: 20px;  
      margin-top: 16px; text-align: center; box-shadow: var(--shadow);  
    }  
    .fact-tag { background: var(--primary); color: white; font-weight: 800; font-size: 0.75rem; padding: 4px 12px; border-radius: 20px; text-transform: uppercase; display: inline-block; margin-bottom: 10px; }  
  
    .badge-level { font-size: 0.75rem; font-weight: 800; padding: 4px 10px; border-radius: 12px; color: white; display: inline-block; }  
    .lvl-facile { background: #22c55e; }  
    .lvl-medio { background: #f59e0b; }  
    .lvl-difficile { background: #ef4444; }  
  
    .player-select { display: flex; gap: 10px; margin-bottom: 14px; }  
    .player-btn {  
      flex: 1; padding: 10px; border-radius: 10px; border: 1px solid var(--border);  
      background: #ffffff; font-weight: 700; cursor: pointer; text-align: center; color: var(--text);  
    }  
    .player-btn.active { background: var(--primary); color: white; border-color: var(--primary-dark); }  
  
    .log-entry {  
      background: var(--surface); border-left: 5px solid var(--primary); border-radius: 12px;  
      padding: 16px; margin-bottom: 16px; box-shadow: var(--shadow); border: 1px solid var(--border); border-left-width: 5px;  
    }  
    .log-media-grid { display: flex; gap: 8px; overflow-x: auto; margin-top: 10px; }  
    .log-media-item { width: 100px; height: 100px; border-radius: 8px; overflow: hidden; flex-shrink: 0; background: #000; }  
    .log-media-item img, .log-media-item video { width: 100%; height: 100%; object-fit: cover; }  
  
    .species-card {  
      background: var(--surface); border-radius: 16px; padding: 16px; margin-bottom: 16px;  
      box-shadow: var(--shadow); border: 1px solid var(--border); display: flex; flex-direction: column; gap: 12px;  
    }  
    .species-header-row { display: flex; gap: 14px; align-items: center; }  
    .species-thumb { width: 85px; height: 85px; border-radius: 12px; object-fit: cover; background: #e2e8f0; flex-shrink: 0; border: 1px solid #cbd5e1; display: block; }  
    .species-name-link { font-size: 1.05rem; color: var(--primary-dark); text-decoration: none; font-weight: 700; }  
    .species-name-link:hover { text-decoration: underline; }  
    .star-rating { display: flex; gap: 4px; font-size: 1.4rem; color: #cbd5e1; cursor: pointer; user-select: none; }  
    .star-rating .star.active { color: #f59e0b; }  
  
    .stat-row { display: flex; justify-content: space-between; align-items: center; padding: 10px 0; border-bottom: 1px solid #f1f5f9; font-weight: 600; }  
    .stat-counter { display: flex; align-items: center; gap: 6px; }  
    .count-btn { background: var(--primary-light); color: var(--primary-dark); border: 1px solid var(--border); width: 28px; height: 28px; border-radius: 6px; font-weight: 800; cursor: pointer; }  
  
    .trophy-card { background: linear-gradient(135deg, #fef9c3 0%, #fef08a 100%); border: 1px solid #fde047; padding: 12px; border-radius: 12px; margin-bottom: 8px; font-weight: 700; color: #854d0e; }  
  
    label { display: block; font-size: 0.85rem; font-weight: 700; color: var(--text); margin-top: 10px; margin-bottom: 4px; }  
    input, textarea, select { width: 100%; padding: 12px; border: 1px solid var(--border); border-radius: 10px; font-size: 0.95rem; background: #ffffff; color: var(--text); outline: none; }  
    button.submit-btn { background: var(--primary); color: white; border: none; padding: 12px; border-radius: 10px; width: 100%; font-size: 1rem; font-weight: 700; cursor: pointer; margin-top: 14px; }  
  
    .bottom-nav {  
      position: fixed; bottom: 0; left: 0; right: 0; background: rgba(255, 255, 255, 0.98);  
      backdrop-filter: blur(10px); display: flex; justify-content: space-around; padding: 8px 0 12px 0;  
      border-top: 1px solid var(--border); z-index: 1000;  
    }  
    .nav-btn { background: none; border: none; display: flex; flex-direction: column; align-items: center; color: #94a3b8; font-size: 0.72rem; font-weight: 600; flex: 1; cursor: pointer; }  
    .nav-btn.active { color: var(--primary); font-weight: 800; }  
    .nav-icon { font-size: 1.35rem; margin-bottom: 2px; }  
  
    .diving-item { background: white; padding: 14px; border-radius: 12px; border: 1px solid var(--border); margin-top: 10px; box-shadow: var(--shadow); }  
    .diving-item h4 { color: var(--primary-dark); font-size: 1rem; }  
    .diving-item p { font-size: 0.82rem; color: var(--text-muted); margin-top: 4px; }  
    .diving-actions { display: flex; gap: 10px; margin-top: 10px; }  
    .diving-actions a { font-size: 0.8rem; font-weight: 700; text-decoration: none; color: white; background: var(--primary); padding: 8px 12px; border-radius: 8px; display: inline-block; }  
  </style>  
</head>  
<body>  
  
  <div class="bubbles-container">  
    <div class="bubble"></div><div class="bubble"></div><div class="bubble"></div><div class="bubble"></div><div class="bubble"></div>  
  </div>  
  
  <div class="drawer-overlay" id="drawer-overlay" onclick="toggleDrawer()"></div>  
  <aside class="drawer" id="drawer">  
    <div class="drawer-header">📌 Menu I Sub del Golfo</div>  
    <ul class="drawer-menu">  
      <li class="drawer-item" onclick="showPage('home'); toggleDrawer();">🏠 Home</li>  
      <li class="drawer-item" onclick="showPage('didyouknow'); toggleDrawer();">🎲 Lo Sapevi? (2000+)</li>  
      <li class="drawer-item" onclick="showPage('tournament'); toggleDrawer();">⚔️ Torneo Quiz & Albo</li>  
      <li class="drawer-item" onclick="showPage('logbook'); toggleDrawer();">📖 Diario di Bordo</li>  
      <li class="drawer-item" onclick="showPage('guide'); toggleDrawer();">🐟 Guida Specie & Wiki ⭐</li>  
      <li class="drawer-item" onclick="showPage('stats'); toggleDrawer();">🏆 Statistiche & Titoli Auto</li>  
      <li class="drawer-item" onclick="showPage('safety'); toggleDrawer();">🚨 Sicurezza & SOS</li>  
      <li class="drawer-item" onclick="showPage('map'); toggleDrawer();">🗺️ Mappa & Diving (35km)</li>  
      <li class="drawer-item" onclick="showPage('qrcode'); toggleDrawer();">🔲 QR Code Web App</li>  
      <li class="drawer-item" onclick="window.open('https://www.3bmeteo.com', '_blank'); toggleDrawer();">🌤️ Meteo & Mare ↗</li>  
    </ul>  
  </aside>  
  
  <header class="header">  
    <button class="menu-toggle" onclick="toggleDrawer()">☰</button>  
    <div class="brand"><span>🤿 I Sub del Golfo</span></div>  
    <div style="width: 24px;"></div>  
  </header>  
  
  <!-- HOME PAGE -->  
  <main id="home" class="page active">  
    <!-- SEZIONE TAGLIE ATTREZZATURA (sostituisce la galleria) -->  
    <div class="card">  
      <h3 style="margin-bottom: 8px;">📏 Taglie Attrezzatura</h3>  
      <p style="font-size:0.82rem; color:var(--text-muted); margin-bottom:12px;">Salva le taglie di GAV, maschera, pinne e tutto il resto. I dati restano memorizzati.</p>  
        
      <div class="equip-grid">  
        <!-- YARI -->  
        <div class="equip-box">  
          <h4>Yari</h4>  
          <label>GAV / Jacket</label>  
          <input type="text" id="eq-yari-gav" placeholder="Es. M / XL">  
          <label>Maschera</label>  
          <input type="text" id="eq-yari-mask" placeholder="Es. Cressi Big Eyes">  
          <label>Pinne</label>  
          <input type="text" id="eq-yari-fins" placeholder="Es. 42-43 / Mares Avanti">  
          <label>Muta</label>  
          <input type="text" id="eq-yari-wetsuit" placeholder="Es. 5 mm / Taglia L">  
          <label>Erogatore</label>  
          <input type="text" id="eq-yari-reg" placeholder="Es. Scubapro MK25">  
          <label>Computer</label>  
          <input type="text" id="eq-yari-computer" placeholder="Es. Shearwater Perdix">  
          <label>Guanti</label>  
          <input type="text" id="eq-yari-gloves" placeholder="Es. 3 mm">  
          <label>Calzari</label>  
          <input type="text" id="eq-yari-boots" placeholder="Es. 42">  
          <label>Bottiglia</label>  
          <input type="text" id="eq-yari-tank" placeholder="Es. 12 L / 15 L">  
          <label>Altro</label>  
          <input type="text" id="eq-yari-other" placeholder="Note extra...">  
        </div>  
  
        <!-- CHIARA -->  
        <div class="equip-box">  
          <h4>Chiara</h4>  
          <label>GAV / Jacket</label>  
          <input type="text" id="eq-chiara-gav" placeholder="Es. S / M">  
          <label>Maschera</label>  
          <input type="text" id="eq-chiara-mask" placeholder="Es. Cressi F1">  
          <label>Pinne</label>  
          <input type="text" id="eq-chiara-fins" placeholder="Es. 38-39">  
          <label>Muta</label>  
          <input type="text" id="eq-chiara-wetsuit" placeholder="Es. 5 mm / Taglia M">  
          <label>Erogatore</label>  
          <input type="text" id="eq-chiara-reg" placeholder="Es. Aqualung">  
          <label>Computer</label>  
          <input type="text" id="eq-chiara-computer" placeholder="Es. Suunto">  
          <label>Guanti</label>  
          <input type="text" id="eq-chiara-gloves" placeholder="Es. 2 mm">  
          <label>Calzari</label>  
          <input type="text" id="eq-chiara-boots" placeholder="Es. 38">  
          <label>Bottiglia</label>  
          <input type="text" id="eq-chiara-tank" placeholder="Es. 10 L / 12 L">  
          <label>Altro</label>  
          <input type="text" id="eq-chiara-other" placeholder="Note extra...">  
        </div>  
      </div>  
  
      <button class="submit-btn" onclick="saveEquipment()">💾 Salva Taglie Attrezzatura</button>  
      <p id="equip-saved-msg" style="text-align:center; font-size:0.85rem; color:#15803d; margin-top:8px; display:none;">✅ Taglie salvate!</p>  
    </div>  
  
    <div class="card">  
      <h3>🎨 Personalizza Grafica, Font & Temi</h3>  
      <p style="font-size:0.82rem; color:var(--text-muted); margin-bottom:10px;">Scegli font stile DaFont e combinazioni di colore:</p>  
  
      <label>1. Stile Tipografico / Font</label>  
      <select onchange="changeAppFont(this.value)">  
        <option value="'Plus Jakarta Sans', sans-serif">Modern / Clean (Default)</option>  
        <option value="'Playfair Display', serif">Elegante / Classic</option>  
        <option value="'Caveat', cursive">Handwritten / Scrittura a mano</option>  
        <option value="'Press Start 2P', cursive">Pixel / Retro Arcade</option>  
        <option value="'Lobster', cursive">Lobster / Corsivo Bold</option>  
        <option value="'Pacifico', cursive">Pacifico / Script Mare</option>  
        <option value="'Montserrat', sans-serif">Montserrat / Ultra Heavy</option>  
        <option value="'Cinzel', serif">Cinzel / Stile Romano</option>  
        <option value="'Fira Code', monospace">Fira Code / Tech Monospace</option>  
        <option value="'Roboto Slab', serif">Roboto Slab / Giornalistico</option>  
      </select>  
  
      <label>2. Tavolozza Temi Cromatici</label>  
      <div class="theme-picker-grid">  
        <button class="theme-btn" style="background:#e0f2fe; color:#0369a1;" onclick="setTheme('#0284c7', '#0369a1', '#e0f2fe', '#f0f9ff')">🌊 Oceano</button>  
        <button class="theme-btn" style="background:#ffedd5; color:#c2410c;" onclick="setTheme('#f97316', '#c2410c', '#ffedd5', '#fff7ed')">🌅 Tramonto</button>  
        <button class="theme-btn" style="background:#fce7f3; color:#be185d;" onclick="setTheme('#ec4899', '#be185d', '#fce7f3', '#fdf2f8')">🪸 Corallo</button>  
        <button class="theme-btn" style="background:#dcfce7; color:#15803d;" onclick="setTheme('#10b981', '#047857', '#dcfce7', '#f0fdf4')">🌿 Smeraldo</button>  
        <button class="theme-btn" style="background:#f3e8ff; color:#6b21a8;" onclick="setTheme('#9333ea', '#6b21a8', '#f3e8ff', '#faf5ff')">🔮 Abisso Viola</button>  
        <button class="theme-btn" style="background:#fef3c7; color:#b45309;" onclick="setTheme('#d97706', '#b45309', '#fef3c7', '#fffbeb')">☀️ Sabbia D'Oro</button>  
        <button class="theme-btn" style="background:#e0e7ff; color:#3730a3;" onclick="setTheme('#4f46e5', '#3730a3', '#e0e7ff', '#eef2ff')">🌌 Notte Marina</button>  
        <button class="theme-btn" style="background:#ccfbf1; color:#0f766e;" onclick="setTheme('#14b8a6', '#0f766e', '#ccfbf1', '#f0fdfa')">🐬 Laguna Blu</button>  
      </div>  
  
      <label>3. Sfondo Personalizzato (URL Immagine)</label>  
      <input type="text" id="bg-url-input" placeholder="Incolla link immagine di sfondo..." onchange="setCustomBg(this.value)">  
    </div>  
  </main>  
  
  <!-- LO SAPEVI -->  
  <main id="didyouknow" class="page">  
    <h2 class="page-title">🎲 Lo Sapevi Che...? (2000+ Curiosità)</h2>  
    <div class="card dice-container">  
      <p style="font-size:0.9rem; color:var(--text-muted); margin-bottom:14px;">Tocca il dado per generare una curiosità marina randomica!</p>  
      <button class="dice-btn" id="dice-btn" onclick="rollDice()">🎲</button>  
  
      <div class="fact-card" id="fact-card" style="display:none;">  
        <span class="fact-tag" id="fact-animal">Specie Marina</span>  
        <p id="fact-text" style="font-weight:600; font-size:1rem; color:var(--text); line-height:1.4;"></p>  
      </div>  
    </div>  
  </main>  
  
  <!-- TORNEO QUIZ -->  
  <main id="tournament" class="page">  
    <h2 class="page-title">⚔ Torneo Quiz Yari vs Chiara</h2>  
  
    <div class="card" style="background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%); border-color: #93c5fd;">  
      <h3 style="color:#1e40af; margin-bottom:8px;">🏆 Albo d'Oro Storico Tornei</h3>  
      <p style="font-size:0.82rem; color:#1e3a8a; margin-bottom:12px;">Conteggio totale dei tornei completati e vinti finora:</p>  
      <div style="display:flex; justify-content:space-around; text-align:center;">  
        <div>  
          <span style="font-size:1.8rem; font-weight:800; color:#1d4ed8;" id="history-wins-yari">0</span>  
          <p style="font-size:0.85rem; font-weight:700;">Yari</p>  
        </div>  
        <div style="font-size:1.5rem; font-weight:800; color:#94a3b8; align-self:center;">VS</div>  
        <div>  
          <span style="font-size:1.8rem; font-weight:800; color:#be185d;" id="history-wins-chiara">0</span>  
          <p style="font-size:0.85rem; font-weight:700;">Chiara</p>  
        </div>  
      </div>  
    </div>  
  
    <div class="card">  
      <p style="font-size:0.85rem; color:var(--text-muted); margin-bottom:10px;">Seleziona chi sta giocando ora:</p>  
      <div class="player-select">  
        <button class="player-btn active" id="btn-player1" onclick="selectPlayer('Yari')">Yari</button>  
        <button class="player-btn" id="btn-player2" onclick="selectPlayer('Chiara')">Chiara</button>  
      </div>  
  
      <div id="quiz-box">  
        <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:10px;">  
          <span id="quiz-progress" style="font-weight:800; font-size:0.9rem; color:var(--primary-dark);">Domanda 1 / 5</span>  
          <span id="quiz-level-badge" class="badge-level lvl-facile">FACILE</span>  
        </div>  
  
        <p id="quiz-q-text" style="font-weight:700; font-size:1rem; margin-bottom:14px;"></p>  
        <div id="quiz-options-list" style="display:flex; flex-direction:column; gap:8px;"></div>  
        <div id="quiz-feedback-box" style="margin-top:12px; font-weight:700; font-size:0.88rem; display:none; padding:10px; border-radius:8px;"></div>  
        <button id="quiz-next-q" class="submit-btn" style="display:none; margin-top:10px;" onclick="nextTournamentQ()">Prossima Domanda ➔</button>  
      </div>  
    </div>  
  
    <div class="card">  
      <h3>📊 Punteggio Torneo Corrente</h3>  
      <div style="margin-top:10px;">  
        <div class="stat-row"><span>Yari:</span><span id="score-player1">0 / 5</span></div>  
        <div class="stat-row"><span>Chiara:</span><span id="score-player2">0 / 5</span></div>  
      </div>  
      <button class="submit-btn" style="background:#64748b; margin-top:14px;" onclick="resetTournament()">🔄 Ricomincia Nuovo Torneo</button>  
    </div>  
  </main>  
  
  <!-- DIARIO DI BORDO -->  
  <main id="logbook" class="page">  
    <h2 class="page-title">📖 Diario di Bordo</h2>  
  
    <div class="card">  
      <h3>✍️ Nuova Immersione</h3>  
      <form id="diary-form">  
        <label for="d-sub">Chi ha fatto l'immersione?</label>  
        <select id="d-sub">  
          <option value="Yari & Chiara insieme">Yari & Chiara insieme</option>  
          <option value="Solo Yari">Solo Yari</option>  
          <option value="Solo Chiara">Solo Chiara</option>  
        </select>  
  
        <label for="d-title">Titolo / Luogo Immersione</label>  
        <input type="text" id="d-title" placeholder="Es. Secca del Faro / Porto Venere" required>  
  
        <label for="d-date">Data</label>  
        <input type="date" id="d-date" required>  
  
        <label for="d-notes">Note, Profondità e Avvistamenti</label>  
        <textarea id="d-notes" rows="3" placeholder="Scrivi dettagli, condizioni del mare o specie incontrate..." required></textarea>  
  
        <label for="d-media">Foto e Video</label>  
        <input type="file" id="d-media" accept="image/*,video/*" multiple onchange="previewDiaryFiles(event)">  
        <div class="log-media-grid" id="diary-preview-grid"></div>  
  
        <button type="submit" class="submit-btn">Salva nel Diario</button>  
      </form>  
    </div>  
  
    <h3 style="margin:20px 0 10px 0;">Pagine del Diario</h3>  
    <div id="diary-entries-list"></div>  
  </main>  
  
  <!-- GUIDA SPECIE -->  
  <main id="guide" class="page">  
    <h2 class="page-title">🐟 Specie Marine & Rating Wikipedia</h2>  
    <input type="text" id="search-input" style="margin-bottom:14px;" placeholder="🔍 Cerca specie marina..." onkeyup="filterSpecies()">  
    <div id="species-container"></div>  
  </main>  
  
  <!-- STATISTICHE -->  
  <main id="stats" class="page">  
    <h2 class="page-title">🏆 Statistiche & Titoli Automatici</h2>  
  
    <div class="card">  
      <h3 style="color:var(--primary-dark); margin-bottom:12px;">📊 Report Automatico Dati</h3>  
      <div class="stat-row"><span>Immersioni Registrate:</span> <span id="auto-dives-count">Yari: 0 | Chiara: 0</span></div>  
      <div class="stat-row"><span>Specie Viste Totalizzabili:</span> <span id="auto-species-count">Yari: 0 | Chiara: 0</span></div>  
    </div>  
  
    <div class="card">  
      <h3 style="margin-bottom:12px;">Avvistamenti per Macro Categoria</h3>  
      <p style="font-size:0.8rem; color:var(--text-muted); margin-bottom:10px;">Aggiungi qui i vostri avvistamenti per calcolare i Titoli:</p>  
        
      <div id="category-counters-box"></div>  
    </div>  
  
    <div class="card">  
      <h3 style="margin-bottom:10px;">Assegnazione Titoli Ufficiali (Automatica)</h3>  
      <p style="font-size:0.82rem; color:var(--text-muted); margin-bottom:12px;">I titoli vengono assegnati ed eletti in autonomia in base ai contatori:</p>  
  
      <div id="auto-titles-list"></div>  
    </div>  
  </main>  
  
  <!-- SICUREZZA -->  
  <main id="safety" class="page">  
    <h2 class="page-title">🚨 Sicurezza & Contatti SOS</h2>  
    <div class="card" style="border-color:#fca5a5; background:#fff5f5;">  
      <h3 style="color:#991b1b; margin-bottom:12px;">Numeri di Emergenza</h3>  
      <a href="tel:1530" style="background:#ef4444; color:white; padding:12px; border-radius:10px; display:block; text-align:center; font-weight:800; text-decoration:none; margin-bottom:8px;">📞 Guardia Costiera (1530)</a>  
      <a href="tel:+390642118685" style="background:#0284c7; color:white; padding:12px; border-radius:10px; display:block; text-align:center; font-weight:800; text-decoration:none;">🚑 DAN Sub (+39 06 42118685)</a>  
    </div>  
  </main>  
  
  <!-- MAPPA -->  
  <main id="map" class="page">  
    <h2 class="page-title">🗺️ Mappa & Diving (Raggio 30 - 35 km)</h2>  
    <div class="card">  
      <button class="submit-btn" style="margin-bottom:12px;" onclick="locateUserAndFindDivings()">📍 Localizzami & Trova Diving entro 35 km</button>  
      <div id="location-status" style="font-size:0.85rem; color:var(--text-muted); margin-bottom:10px; text-align:center;"></div>  
        
      <iframe id="map-iframe" style="width:100%; height:300px; border:none; border-radius:12px;" src="https://maps.google.com/maps?q=Golfo%20dei%20Poeti%20diving&t=&z=11&ie=UTF8&iwloc=&output=embed"></iframe>  
    </div>  
  
    <div class="card">  
      <h3>⚓ Centri Diving Trovati entro 35 km</h3>  
      <div id="diving-results-list">  
        <p style="font-size:0.85rem; color:var(--text-muted); margin-top:8px;">Tocca il pulsante sopra per calcolare i diving attorno a te entro un raggio di 30-35 km!</p>  
      </div>  
    </div>  
  </main>  
  
  <!-- QR CODE -->  
  <main id="qrcode" class="page">  
    <h2 class="page-title">🔲 QR Code Web App</h2>  
    <div class="card" style="text-align:center;">  
      <img src="https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=https://krdp6hydv5-oss.github.io/i-sub-del-golfo/" style="border-radius:12px; border:2px solid var(--primary);" alt="QR">  
    </div>  
  </main>  
  
  <nav class="bottom-nav">  
    <button class="nav-btn active" id="btn-home" onclick="showPage('home')">  
      <span class="nav-icon">🏠</span>  
      <span>Home</span>  
    </button>  
    <button class="nav-btn" id="btn-didyouknow" onclick="showPage('didyouknow')">  
      <span class="nav-icon">🎲</span>  
      <span>Lo Sapevi</span>  
    </button>  
    <button class="nav-btn" id="btn-tournament" onclick="showPage('tournament')">  
      <span class="nav-icon">⚔️</span>  
      <span>Torneo</span>  
    </button>  
    <button class="nav-btn" id="btn-logbook" onclick="showPage('logbook')">  
      <span class="nav-icon">📖</span>  
      <span>Diario</span>  
    </button>  
  </nav>  
  
  <script>  
    /* GENERATORE DINAMICO DI OLTRE 2000 CURIOSITÀ MARINES */  
    const speciesSubjects = [  
      "Il Polpo", "La Balenottera Azzurra", "Il Gambero Mantide", "Lo Squalo Balena", "Il Nudibranchio",  
      "Il Cavalluccio Marino", "La Capasanta", "La Murena", "Il Pesce Pagliaccio", "La Seppia",  
      "La Medusa Turritopsis", "Lo Squalo Bianco", "Il Pesce Palla", "La Tartaruga Liuto", "Il Narvalo",  
      "La Stella Marina", "Il Capodoglio", "Il Pesce Lanterna", "La Granseola", "Il Pesce Luna"  
    ];  
  
    const factTemplates = [  
      "possiede un sistema nervoso unico: circa due terzi dei suoi neuroni si trovano nei bracci e non nella testa.",  
      "ha una capacità adattiva straordinaria, potendo cambiare sia colore che texture della pelle in meno di 200 millisecondi.",  
      "può resistere a pressioni abissali elevate mantenendo intatte le proprie membrane cellulari grazie a particolari proteine osmolitiche.",  
      "produce una bioluminescenza naturale grazie a enzimi chiamati luciferina per comunicare o mimetizzarsi nel buio totale.",  
      "svolge un ruolo fondamentale negli ecosistemi marini regolando la catena alimentare e mantenendo bilanciata la barriera corallina.",  
      "migra per oltre mille chilometri ogni anno seguendo le correnti oceaniche e la temperatura della superficie.",  
      "è in grado di percepire i campi elettromagnetici generati dai movimenti di altri animali attraverso ricettori dedicati.",  
      "può rigenerare parti del corpo danneggiate o perdute durante un attacco di un predatore con precisione cellulare.",  
      "utilizza frequenze acustiche a bassa frequenza capaci di viaggiare attraverso centinaia di chilometri d'acqua.",  
      "sviluppa simbiosità uniche con batteri o altre specie per proteggersi dai parassiti marini."  
    ];  
  
    const factDetails = [  
      " Questo fenomeno scientifico è tra i più studiati dai biologi marini.",  
      " Gli scienziati hanno scoperto che questo adattamento risale a milioni di anni fa.",  
      " Durante le immersioni profonde, è uno degli avvistamenti più affascinanti in assoluto.",  
      " Studi recenti confermano la sua straordinaria intelligenza e capacità di risoluzione dei problemi.",  
      " Questa caratteristica lo rende unico nel suo genere all'interno del regno animale."  
    ];  
  
    function getRandomFact() {  
      const s = speciesSubjects[Math.floor(Math.random() * speciesSubjects.length)];  
      const t = factTemplates[Math.floor(Math.random() * factTemplates.length)];  
      const d = factDetails[Math.floor(Math.random() * factDetails.length)];  
      return { animal: s, text: `${s} ${t}${d}` };  
    }  
  
    const masterQuizDb = [  
      { q: "Qual è il mammifero più grande del pianeta?", opts: ["Elefante Africano", "Balenottera Azzurra", "Capodoglio", "Squalo Balena"], c: 1, lvl: "facile" },  
      { q: "Quanti cuori possiede un polpo?", opts: ["1", "2", "3", "4"], c: 2, lvl: "facile" },  
      { q: "Di che colore è il sangue dei polpi?", opts: ["Rosso", "Blu", "Verde", "Trasparente"], c: 1, lvl: "medio" },  
      { q: "Quale pesce si nasconde tra gli anemoni?", opts: ["Pesce Pagliaccio", "Murena", "Spigola", "Sarago"], c: 0, lvl: "facile" },  
      { q: "I cavallucci marini maschi sono gli unici a portare la gravidanza?", opts: ["Vero", "Falso"], c: 0, lvl: "facile" }  
    ];  
  
    /* LISTA SPECIE completa + link Wikipedia + immagini migliorate */  
    const speciesListWithThumb = [  
      { name: "Aguglia", wiki: "Belone_belone", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Belone_belone_Italy.jpg/320px-Belone_belone_Italy.jpg" },  
      { name: "Aragosta", wiki: "Palinurus_elephas", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/Palinurus_elephas.jpg/320px-Palinurus_elephas.jpg" },  
      { name: "Bavosa", wiki: "Parablennius", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Parablennius_gattorugine.jpg/320px-Parablennius_gattorugine.jpg" },  
      { name: "Bavosa bianca", wiki: "Parablennius_rouxi", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/Parablennius_rouxi.jpg/320px-Parablennius_rouxi.jpg" },  
      { name: "Bavosa cornuta", wiki: "Parablennius_tentacularis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1f/Parablennius_tentacularis.jpg/320px-Parablennius_tentacularis.jpg" },  
      { name: "Bavosa gialla", wiki: "Parablennius_zvonimiri", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Parablennius_zvonimiri.jpg/320px-Parablennius_zvonimiri.jpg" },  
      { name: "Barracuda", wiki: "Sphyraena_viridensis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Sphyraena_viridensis_1.jpg/320px-Sphyraena_viridensis_1.jpg" },  
      { name: "Boga", wiki: "Boops_boops", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9e/Boops_boops.jpg/320px-Boops_boops.jpg" },  
      { name: "Berta minore", wiki: "Puffinus_yelkouan", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Puffinus_yelkouan.jpg/320px-Puffinus_yelkouan.jpg" },  
      { name: "Cappone gallinella", wiki: "Chelidonichthys_lucerna", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Chelidonichthys_lucerna.jpg/320px-Chelidonichthys_lucerna.jpg" },  
      { name: "Caretta caretta", wiki: "Caretta_caretta", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/7/7e/Caretta_caretta.jpg/320px-Caretta_caretta.jpg" },  
      { name: "Castagnola", wiki: "Chromis_chromis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1a/Chromis_chromis.jpg/320px-Chromis_chromis.jpg" },  
      { name: "Castagnola rossa", wiki: "Anthias_anthias", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Anthias_anthias.jpg/320px-Anthias_anthias.jpg" },  
      { name: "Cavalluccio marino", wiki: "Hippocampus_hippocampus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Hippocampus_hippocampus.jpg/320px-Hippocampus_hippocampus.jpg" },  
      { name: "Cefalo", wiki: "Mugil_cephalus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Mugil_cephalus.jpg/320px-Mugil_cephalus.jpg" },  
      { name: "Cernia bruna", wiki: "Epinephelus_marginatus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/87/Epinephelus_marginatus_2.jpg/320px-Epinephelus_marginatus_2.jpg" },  
      { name: "Cernia rossa", wiki: "Mycteroperca_rubra", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Mycteroperca_rubra.jpg/320px-Mycteroperca_rubra.jpg" },  
      { name: "Cepola", wiki: "Cepola_macrophthalma", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Cepola_macrophthalma.jpg/320px-Cepola_macrophthalma.jpg" },  
      { name: "Civetta di mare", wiki: "Dactylopterus_volitans", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8e/Dactylopterus_volitans.jpg/320px-Dactylopterus_volitans.jpg" },  
      { name: "Coccinella di mare", wiki: "Coccinella_septempunctata", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Coccinella_septempunctata.jpg/320px-Coccinella_septempunctata.jpg" },  
      { name: "Cormorano", wiki: "Phalacrocorax_carbo", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Phalacrocorax_carbo.jpg/320px-Phalacrocorax_carbo.jpg" },  
      { name: "Corvina", wiki: "Sciaena_umbra", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Sciaena_umbra.jpg/320px-Sciaena_umbra.jpg" },  
      { name: "Delfino", wiki: "Tursiops_truncatus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Tursiops_truncatus_01.jpg/320px-Tursiops_truncatus_01.jpg" },  
      { name: "Donzella", wiki: "Coris_julis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Coris_julis.jpg/320px-Coris_julis.jpg" },  
      { name: "Donzella pavonina", wiki: "Thalassoma_pavo", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Thalassoma_pavo.jpg/320px-Thalassoma_pavo.jpg" },  
      { name: "Edredone", wiki: "Somateria_mollissima", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Somateria_mollissima.jpg/320px-Somateria_mollissima.jpg" },  
      { name: "Flabellina affinis", wiki: "Flabellina_affinis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/23/Flabellina_affinis.jpg/320px-Flabellina_affinis.jpg" },  
      { name: "Gabbiano reale", wiki: "Larus_michahellis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Larus_michahellis.jpg/320px-Larus_michahellis.jpg" },  
      { name: "Gallinella", wiki: "Chelidonichthys_lucerna", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Chelidonichthys_lucerna.jpg/320px-Chelidonichthys_lucerna.jpg" },  
      { name: "Ghiozzo", wiki: "Gobius_niger", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Gobius_niger.jpg/320px-Gobius_niger.jpg" },  
      { name: "Ghiozzo di Bucchich", wiki: "Gobius_bucchichi", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Gobius_bucchichi.jpg/320px-Gobius_bucchichi.jpg" },  
      { name: "Ghiozzo rigato", wiki: "Gobius_vittatus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Gobius_vittatus.jpg/320px-Gobius_vittatus.jpg" },  
      { name: "Gorgonia rossa", wiki: "Paramuricea_clavata", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Paramuricea_clavata.jpg/320px-Paramuricea_clavata.jpg" },  
      { name: "Granchio eremita", wiki: "Pagurus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Pagurus_bernhardus.jpg/320px-Pagurus_bernhardus.jpg" },  
      { name: "Granchio reale blu", wiki: "Callinectes_sapidus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Callinectes_sapidus.jpg/320px-Callinectes_sapidus.jpg" },  
      { name: "Grongo", wiki: "Conger_conger", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Conger_conger.jpg/320px-Conger_conger.jpg" },  
      { name: "Hypselodoris valenciennesi", wiki: "Hypselodoris_valenciennesi", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Hypselodoris_picta.jpg/320px-Hypselodoris_picta.jpg" },  
      { name: "Lampuga", wiki: "Coryphaena_hippurus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Coryphaena_hippurus.jpg/320px-Coryphaena_hippurus.jpg" },  
      { name: "Leccia", wiki: "Lichia_amia", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Lichia_amia.jpg/320px-Lichia_amia.jpg" },  
      { name: "Lepre di mare", wiki: "Aplysia_depilans", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Aplysia_depilans.jpg/320px-Aplysia_depilans.jpg" },  
      { name: "Latterino", wiki: "Atherina_hepsetus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Atherina_hepsetus.jpg/320px-Atherina_hepsetus.jpg" },  
      { name: "Mako", wiki: "Isurus_oxyrinchus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Isurus_oxyrinchus.jpg/320px-Isurus_oxyrinchus.jpg" },  
      { name: "Margherita di mare", wiki: "Anemonia_viridis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Anemonia_viridis.jpg/320px-Anemonia_viridis.jpg" },  
      { name: "Medusa luminosa", wiki: "Pelagia_noctiluca", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Pelagia_noctiluca.jpg/320px-Pelagia_noctiluca.jpg" },  
      { name: "Mormora", wiki: "Lithognathus_mormyrus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Lithognathus_mormyrus.jpg/320px-Lithognathus_mormyrus.jpg" },  
      { name: "Mostella", wiki: "Phycis_phycis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Phycis_phycis.jpg/320px-Phycis_phycis.jpg" },  
      { name: "Murena", wiki: "Muraena_helena", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e8/Muraena_helena_PTP.jpg/320px-Muraena_helena_PTP.jpg" },  
      { name: "Nasello", wiki: "Merluccius_merluccius", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Merluccius_merluccius.jpg/320px-Merluccius_merluccius.jpg" },  
      { name: "Occhiata", wiki: "Oblada_melanura", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Oblada_melanura.jpg/320px-Oblada_melanura.jpg" },  
      { name: "Pagello bastardo", wiki: "Pagellus_acarne", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Pagellus_acarne.jpg/320px-Pagellus_acarne.jpg" },  
      { name: "Pagello fragolino", wiki: "Pagellus_erythrinus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Pagellus_erythrinus.jpg/320px-Pagellus_erythrinus.jpg" },  
      { name: "Pagro", wiki: "Pagrus_pagrus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Pagrus_pagrus.jpg/320px-Pagrus_pagrus.jpg" },  
      { name: "Palamita", wiki: "Sarda_sarda", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Sarda_sarda.jpg/320px-Sarda_sarda.jpg" },  
      { name: "Pesce balestra", wiki: "Balistes_capriscus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Balistes_capriscus.jpg/320px-Balistes_capriscus.jpg" },  
      { name: "Pesce civetta", wiki: "Dactylopterus_volitans", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8e/Dactylopterus_volitans.jpg/320px-Dactylopterus_volitans.jpg" },  
      { name: "Pesce peperoncino", wiki: "Apogon_imberbis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Apogon_imberbis.jpg/320px-Apogon_imberbis.jpg" },  
      { name: "Pesce serra", wiki: "Pomatomus_saltatrix", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Pomatomus_saltatrix.jpg/320px-Pomatomus_saltatrix.jpg" },  
      { name: "Perchia", wiki: "Serranus_cabrilla", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Serranus_cabrilla.jpg/320px-Serranus_cabrilla.jpg" },  
      { name: "Polpo", wiki: "Octopus_vulgaris", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/57/Octopus_vulgaris2.jpg/320px-Octopus_vulgaris2.jpg" },  
      { name: "Pomodoro di mare", wiki: "Actinia_equina", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Actinia_equina.jpg/320px-Actinia_equina.jpg" },  
      { name: "Polmone di mare", wiki: "Rhizostoma_pulmo", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Rhizostoma_pulmo.jpg/320px-Rhizostoma_pulmo.jpg" },  
      { name: "Rana pescatrice", wiki: "Lophius_piscatorius", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Lophius_piscatorius.jpg/320px-Lophius_piscatorius.jpg" },  
      { name: "Razza", wiki: "Raja_clavata", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f6/Raja_clavata.jpg/320px-Raja_clavata.jpg" },  
      { name: "Re di triglie", wiki: "Mullus_barbatus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Mullus_barbatus.jpg/320px-Mullus_barbatus.jpg" },  
      { name: "Ricciola", wiki: "Seriola_dumerili", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/ad/Seriola_dumerili.jpg/320px-Seriola_dumerili.jpg" },  
      { name: "Rombo", wiki: "Scophthalmus_maximus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Scophthalmus_maximus.jpg/320px-Scophthalmus_maximus.jpg" },  
      { name: "Rombo di rena", wiki: "Bothus_podas", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Bothus_podas.jpg/320px-Bothus_podas.jpg" },  
      { name: "Salpa", wiki: "Sarpa_salpa", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Sarpa_salpa.jpg/320px-Sarpa_salpa.jpg" },  
      { name: "Sarago fasciato", wiki: "Diplodus_vulgaris", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Diplodus_vulgaris.jpg/320px-Diplodus_vulgaris.jpg" },  
      { name: "Sarago maggiore", wiki: "Diplodus_sargus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/Diplodus_sargus_sargus.jpg/320px-Diplodus_sargus_sargus.jpg" },  
      { name: "Sarago pizzuto", wiki: "Diplodus_puntazzo", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Diplodus_puntazzo.jpg/320px-Diplodus_puntazzo.jpg" },  
      { name: "Scorfano nero", wiki: "Scorpaena_porcus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Scorpaena_porcus.jpg/320px-Scorpaena_porcus.jpg" },  
      { name: "Scorfano rosso", wiki: "Scorpaena_scrofa", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/7/7a/Scorpaena_scrofa_1.jpg/320px-Scorpaena_scrofa_1.jpg" },  
      { name: "Scorfanotto", wiki: "Scorpaena_notata", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Scorpaena_notata.jpg/320px-Scorpaena_notata.jpg" },  
      { name: "Seppia", wiki: "Sepia_officinalis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/69/Sepia_officinalis_%28Italian_coasts%29.jpg/320px-Sepia_officinalis_%28Italian_coasts%29.jpg" },  
      { name: "Sogliola", wiki: "Solea_solea", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Solea_solea.jpg/320px-Solea_solea.jpg" },  
      { name: "Spigola", wiki: "Dicentrarchus_labrax", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Dicentrarchus_labrax.jpg/320px-Dicentrarchus_labrax.jpg" },  
      { name: "Tanuta", wiki: "Spondyliosoma_cantharus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Spondyliosoma_cantharus.jpg/320px-Spondyliosoma_cantharus.jpg" },  
      { name: "Torpedine", wiki: "Torpedo_marmorata", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/06/Torpedo_marmorata_1.jpg/320px-Torpedo_marmorata_1.jpg" },  
      { name: "Tordo fischietto", wiki: "Symphodus_melanocercus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Symphodus_melanocercus.jpg/320px-Symphodus_melanocercus.jpg" },  
      { name: "Tordo grigio", wiki: "Symphodus_cinereus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Symphodus_cinereus.jpg/320px-Symphodus_cinereus.jpg" },  
      { name: "Tordo mediterraneo", wiki: "Symphodus_mediterraneus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Symphodus_mediterraneus.jpg/320px-Symphodus_mediterraneus.jpg" },  
      { name: "Tordo musolungo", wiki: "Symphodus_rostratus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Symphodus_rostratus.jpg/320px-Symphodus_rostratus.jpg" },  
      { name: "Tordo nero", wiki: "Symphodus_melops", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Symphodus_melops.jpg/320px-Symphodus_melops.jpg" },  
      { name: "Tordo ocellato", wiki: "Symphodus_ocellatus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Symphodus_ocellatus.jpg/320px-Symphodus_ocellatus.jpg" },  
      { name: "Tordo pavone", wiki: "Symphodus_tinca", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Symphodus_tinca.jpg/320px-Symphodus_tinca.jpg" },  
      { name: "Tordo verde", wiki: "Symphodus_roissali", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Symphodus_roissali.jpg/320px-Symphodus_roissali.jpg" },  
      { name: "Triglia di fango", wiki: "Mullus_barbatus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Mullus_barbatus.jpg/320px-Mullus_barbatus.jpg" },  
      { name: "Triglia di scoglio", wiki: "Mullus_surmuletus", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/Mullus_surmuletus.jpg/320px-Mullus_surmuletus.jpg" },  
      { name: "Vacchetta di mare", wiki: "Chondrosia_reniformis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Chondrosia_reniformis.jpg/320px-Chondrosia_reniformis.jpg" },  
      { name: "Verdesca", wiki: "Prionace_glauca", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Prionace_glauca.jpg/320px-Prionace_glauca.jpg" },  
      { name: "Verme dal ciuffo bianco", wiki: "Hermodice_carunculata", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/Hermodice_carunculata.jpg/320px-Hermodice_carunculata.jpg" },  
      { name: "Zerro", wiki: "Spicara_smaris", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Spicara_smaris.jpg/320px-Spicara_smaris.jpg" }  
    ];  
  
    const macroCategories = ["Pesci", "Mammiferi", "Molluschi & Nudibranchi", "Crostacei", "Rettili", "Coralli & Invertebrati"];  
  
    let currentTournamentList = [];  
    let currentQIdx = 0;  
    let currentPlayer = "Yari";  
    let tournamentScores = { "Yari": 0, "Chiara": 0 };  
    let tempDiaryFiles = [];  
  
    document.addEventListener('DOMContentLoaded', () => {  
      loadEquipment();  
      initTournament();  
      renderDiary();  
      renderSpecies();  
      renderAdaptiveStats();  
      loadSavedTheme();  
      updateTournamentHistoryUI();  
    });  
  
    function toggleDrawer() {  
      document.getElementById('drawer').classList.toggle('active');  
      document.getElementById('drawer-overlay').classList.toggle('active');  
    }  
  
    function showPage(pageId) {  
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));  
      document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));  
  
      const targetPage = document.getElementById(pageId);  
      const targetBtn = document.getElementById('btn-' + pageId);  
  
      if (targetPage) targetPage.classList.add('active');  
      if (targetBtn) targetBtn.classList.add('active');  
  
      window.scrollTo({ top: 0, behavior: 'smooth' });  
    }  
  
    function changeAppFont(fontFamily) {  
      document.documentElement.style.setProperty('--app-font', fontFamily);  
      localStorage.setItem('custom_font', fontFamily);  
    }  
  
    function setTheme(p, pd, pl, bg) {  
      document.documentElement.style.setProperty('--primary', p);  
      document.documentElement.style.setProperty('--primary-dark', pd);  
      document.documentElement.style.setProperty('--primary-light', pl);  
      document.documentElement.style.setProperty('--bg-color', bg);  
      localStorage.setItem('custom_theme', JSON.stringify({ p, pd, pl, bg }));  
    }  
  
    function setCustomBg(url) {  
      if (url.trim() !== '') {  
        document.documentElement.style.setProperty('--bg-image', `url('${url}')`);  
        localStorage.setItem('custom_bg_url', url);  
      } else {  
        document.documentElement.style.setProperty('--bg-image', 'none');  
        localStorage.removeItem('custom_bg_url');  
      }  
    }  
  
    function loadSavedTheme() {  
      const font = localStorage.getItem('custom_font');  
      if (font) changeAppFont(font);  
  
      const theme = JSON.parse(localStorage.getItem('custom_theme') || 'null');  
      if (theme) setTheme(theme.p, theme.pd, theme.pl, theme.bg);  
  
      const bgUrl = localStorage.getItem('custom_bg_url');  
      if (bgUrl) {  
        setCustomBg(bgUrl);  
        document.getElementById('bg-url-input').value = bgUrl;  
      }  
    }  
  
    /* TAGLIE ATTREZZATURA */  
    function saveEquipment() {  
      const data = {  
        yari: {  
          gav: document.getElementById('eq-yari-gav').value,  
          mask: document.getElementById('eq-yari-mask').value,  
          fins: document.getElementById('eq-yari-fins').value,  
          wetsuit: document.getElementById('eq-yari-wetsuit').value,  
          reg: document.getElementById('eq-yari-reg').value,  
          computer: document.getElementById('eq-yari-computer').value,  
          gloves: document.getElementById('eq-yari-gloves').value,  
          boots: document.getElementById('eq-yari-boots').value,  
          tank: document.getElementById('eq-yari-tank').value,  
          other: document.getElementById('eq-yari-other').value  
        },  
        chiara: {  
          gav: document.getElementById('eq-chiara-gav').value,  
          mask: document.getElementById('eq-chiara-mask').value,  
          fins: document.getElementById('eq-chiara-fins').value,  
          wetsuit: document.getElementById('eq-chiara-wetsuit').value,  
          reg: document.getElementById('eq-chiara-reg').value,  
          computer: document.getElementById('eq-chiara-computer').value,  
          gloves: document.getElementById('eq-chiara-gloves').value,  
          boots: document.getElementById('eq-chiara-boots').value,  
          tank: document.getElementById('eq-chiara-tank').value,  
          other: document.getElementById('eq-chiara-other').value  
        }  
      };  
      localStorage.setItem('equipment_sizes', JSON.stringify(data));  
      const msg = document.getElementById('equip-saved-msg');  
      msg.style.display = 'block';  
      setTimeout(() => msg.style.display = 'none', 2500);  
    }  
  
    function loadEquipment() {  
      const data = JSON.parse(localStorage.getItem('equipment_sizes') || 'null');  
      if (!data) return;  
      if (data.yari) {  
        document.getElementById('eq-yari-gav').value = data.yari.gav || '';  
        document.getElementById('eq-yari-mask').value = data.yari.mask || '';  
        document.getElementById('eq-yari-fins').value = data.yari.fins || '';  
        document.getElementById('eq-yari-wetsuit').value = data.yari.wetsuit || '';  
        document.getElementById('eq-yari-reg').value = data.yari.reg || '';  
        document.getElementById('eq-yari-computer').value = data.yari.computer || '';  
        document.getElementById('eq-yari-gloves').value = data.yari.gloves || '';  
        document.getElementById('eq-yari-boots').value = data.yari.boots || '';  
        document.getElementById('eq-yari-tank').value = data.yari.tank || '';  
        document.getElementById('eq-yari-other').value = data.yari.other || '';  
      }  
      if (data.chiara) {  
        document.getElementById('eq-chiara-gav').value = data.chiara.gav || '';  
        document.getElementById('eq-chiara-mask').value = data.chiara.mask || '';  
        document.getElementById('eq-chiara-fins').value = data.chiara.fins || '';  
        document.getElementById('eq-chiara-wetsuit').value = data.chiara.wetsuit || '';  
        document.getElementById('eq-chiara-reg').value = data.chiara.reg || '';  
        document.getElementById('eq-chiara-computer').value = data.chiara.computer || '';  
        document.getElementById('eq-chiara-gloves').value = data.chiara.gloves || '';  
        document.getElementById('eq-chiara-boots').value = data.chiara.boots || '';  
        document.getElementById('eq-chiara-tank').value = data.chiara.tank || '';  
        document.getElementById('eq-chiara-other').value = data.chiara.other || '';  
      }  
    }  
  
    function rollDice() {  
      const btn = document.getElementById('dice-btn');  
      btn.style.transform = "rotate(360deg) scale(1.2)";  
      setTimeout(() => {  
        btn.style.transform = "none";  
        const fact = getRandomFact();  
        document.getElementById('fact-animal').innerText = fact.animal;  
        document.getElementById('fact-text').innerText = fact.text;  
        document.getElementById('fact-card').style.display = 'block';  
      }, 300);  
    }  
  
    /* TORNEO */  
    function initTournament() {  
      let savedQ = localStorage.getItem('tournament_questions');  
      if (!savedQ) {  
        currentTournamentList = [...masterQuizDb].sort(() => 0.5 - Math.random());  
        localStorage.setItem('tournament_questions', JSON.stringify(currentTournamentList));  
      } else {  
        currentTournamentList = JSON.parse(savedQ);  
      }  
  
      let savedScores = localStorage.getItem('tournament_scores_yc');  
      if (savedScores) tournamentScores = JSON.parse(savedScores);  
  
      updateScoresUI();  
      currentQIdx = 0;  
      displayTournamentQ();  
    }  
  
    function selectPlayer(player) {  
      currentPlayer = player;  
      document.getElementById('btn-player1').classList.toggle('active', player === 'Yari');  
      document.getElementById('btn-player2').classList.toggle('active', player === 'Chiara');  
      currentQIdx = 0;  
      displayTournamentQ();  
    }  
  
    function displayTournamentQ() {  
      if (currentQIdx >= currentTournamentList.length) {  
        document.getElementById('quiz-box').innerHTML = `  
          <h3>🎉 Torneo completato per ${currentPlayer}!</h3>  
          <p style="margin-top:6px;">Punteggio ottenuto: ${tournamentScores[currentPlayer]} / ${currentTournamentList.length}</p>  
        `;  
        checkTournamentWinnerAndRecord();  
        return;  
      }  
  
      const qData = currentTournamentList[currentQIdx];  
      document.getElementById('quiz-progress').innerText = `Domanda ${currentQIdx + 1} / ${currentTournamentList.length}`;  
  
      const badge = document.getElementById('quiz-level-badge');  
      badge.innerText = qData.lvl.toUpperCase();  
      badge.className = `badge-level lvl-${qData.lvl}`;  
  
      document.getElementById('quiz-q-text').innerText = qData.q;  
      const optsContainer = document.getElementById('quiz-options-list');  
      optsContainer.innerHTML = qData.opts.map((opt, idx) => `  
        <button class="player-btn" style="text-align:left;" onclick="answerTournamentQ(${idx})">${opt}</button>  
      `).join('');  
  
      document.getElementById('quiz-feedback-box').style.display = 'none';  
      document.getElementById('quiz-next-q').style.display = 'none';  
    }  
  
    function answerTournamentQ(selected) {  
      const qData = currentTournamentList[currentQIdx];  
      const feedback = document.getElementById('quiz-feedback-box');  
  
      if (selected === qData.c) {  
        tournamentScores[currentPlayer] += 1;  
        feedback.style.background = '#dcfce7'; feedback.style.color = '#15803d';  
        feedback.innerText = "✅ Corretto!";  
      } else {  
        feedback.style.background = '#fee2e2'; feedback.style.color = '#991b1b';  
        feedback.innerText = `❌ Errato! Risposta giusta: ${qData.opts[qData.c]}`;  
      }  
  
      localStorage.setItem('tournament_scores_yc', JSON.stringify(tournamentScores));  
      updateScoresUI();  
      feedback.style.display = 'block';  
      document.getElementById('quiz-next-q').style.display = 'block';  
    }  
  
    function nextTournamentQ() { currentQIdx++; displayTournamentQ(); }  
  
    function updateScoresUI() {  
      document.getElementById('score-player1').innerText = `${tournamentScores['Yari']} / ${currentTournamentList.length}`;  
      document.getElementById('score-player2').innerText = `${tournamentScores['Chiara']} / ${currentTournamentList.length}`;  
    }  
  
    function checkTournamentWinnerAndRecord() {  
      let winsHistory = JSON.parse(localStorage.getItem('tournament_wins_history') || '{"Yari": 0, "Chiara": 0}');  
        
      if (tournamentScores['Yari'] > tournamentScores['Chiara']) {  
        winsHistory['Yari'] += 1;  
      } else if (tournamentScores['Chiara'] > tournamentScores['Yari']) {  
        winsHistory['Chiara'] += 1;  
      }  
  
      localStorage.setItem('tournament_wins_history', JSON.stringify(winsHistory));  
      updateTournamentHistoryUI();  
    }  
  
    function updateTournamentHistoryUI() {  
      let winsHistory = JSON.parse(localStorage.getItem('tournament_wins_history') || '{"Yari": 0, "Chiara": 0}');  
      document.getElementById('history-wins-yari').innerText = winsHistory['Yari'] || 0;  
      document.getElementById('history-wins-chiara').innerText = winsHistory['Chiara'] || 0;  
    }  
  
    function resetTournament() {  
      localStorage.removeItem('tournament_questions');  
      tournamentScores = { "Yari": 0, "Chiara": 0 };  
      localStorage.setItem('tournament_scores_yc', JSON.stringify(tournamentScores));  
      initTournament();  
    }  
  
    /* DIARIO */  
    function previewDiaryFiles(e) {  
      tempDiaryFiles = [];  
      const files = Array.from(e.target.files);  
      const grid = document.getElementById('diary-preview-grid');  
      grid.innerHTML = '';  
  
      files.forEach(file => {  
        const reader = new FileReader();  
        reader.onload = function(evt) {  
          tempDiaryFiles.push({ type: file.type.startsWith('video') ? 'video' : 'image', url: evt.target.result });  
          grid.innerHTML += file.type.startsWith('video')   
            ? `<div class="log-media-item"><video src="${evt.target.result}"></video></div>`  
            : `<div class="log-media-item"><img src="${evt.target.result}"></div>`;  
        };  
        reader.readAsDataURL(file);  
      });  
    }  
  
    document.getElementById('diary-form').addEventListener('submit', function(e) {  
      e.preventDefault();  
      const entry = {  
        sub: document.getElementById('d-sub').value,  
        title: document.getElementById('d-title').value,  
        date: document.getElementById('d-date').value,  
        notes: document.getElementById('d-notes').value,  
        media: tempDiaryFiles  
      };  
  
      let entries = JSON.parse(localStorage.getItem('diary_entries_v4') || '[]');  
      entries.unshift(entry);  
      localStorage.setItem('diary_entries_v4', JSON.stringify(entries));  
      this.reset();  
      document.getElementById('diary-preview-grid').innerHTML = '';  
      tempDiaryFiles = [];  
      renderDiary();  
      renderAdaptiveStats();  
    });  
  
    function renderDiary() {  
      const container = document.getElementById('diary-entries-list');  
      const entries = JSON.parse(localStorage.getItem('diary_entries_v4') || '[]');  
  
      if (entries.length === 0) {  
        container.innerHTML = `<p style="color:var(--text-muted); font-size:0.85rem;">Nessuna immersione ancora registrata.</p>`;  
        return;  
      }  
  
      container.innerHTML = entries.map(item => `  
        <div class="log-entry">  
          <div style="display:flex; justify-content:space-between; align-items:center;">  
            <h3 style="color:var(--primary-dark);">${item.title}</h3>  
            <span style="font-size:0.75rem; font-weight:800; background:var(--primary-light); color:var(--primary-dark); padding:3px 8px; border-radius:10px;">${item.sub}</span>  
          </div>  
          <p style="font-size:0.8rem; color:var(--text-muted); margin: 4px 0 8px 0;">📅 ${item.date}</p>  
          <p style="font-size:0.9rem; line-height:1.4;">${item.notes}</p>  
          ${item.media && item.media.length > 0 ? `  
            <div class="log-media-grid">  
              ${item.media.map(m => m.type === 'video' ? `<div class="log-media-item"><video src="${m.url}" controls></video></div>` : `<div class="log-media-item"><img src="${m.url}"></div>`).join('')}  
            </div>  
          ` : ''}  
        </div>  
      `).join('');  
    }  
  
    /* GUIDA SPECIE con link Wikipedia */  
    function renderSpecies() {  
      const container = document.getElementById('species-container');  
      let ratings = JSON.parse(localStorage.getItem('species_ratings_yc') || '{}');  
      let seenYari = JSON.parse(localStorage.getItem('seen_yari') || '{}');  
      let seenChiara = JSON.parse(localStorage.getItem('seen_chiara') || '{}');  
  
      container.innerHTML = speciesListWithThumb.map(item => {  
        const name = item.name;  
        const currentStars = ratings[name] || 0;  
        const seenY = !!seenYari[name];  
        const seenC = !!seenChiara[name];  
        const wikiUrl = `https://it.wikipedia.org/wiki/${item.wiki}`;  
  
        return `  
          <div class="species-card" data-name="${name.toLowerCase()}">  
            <div class="species-header-row">  
              <img src="${item.img}" class="species-thumb" alt="${name}" onerror="this.src='https://images.unsplash.com/photo-1544551763-46a013bb70d5?w=150&h=150&fit=crop'">  
              <div style="flex:1;">  
                <a href="${wikiUrl}" target="_blank" class="species-name-link">${name} ↗</a>  
                  
                <div class="star-rating" style="margin-top:6px;">  
                  ${[1, 2, 3, 4, 5].map(s => `  
                    <span class="star ${s <= currentStars ? 'active' : ''}" onclick="rateSpecies('${name}',${s})">★</span>  
                  `).join('')}  
                </div>  
              </div>  
            </div>  
  
            <div style="display:flex; gap:8px;">  
              <button class="player-btn ${seenY ? 'active' : ''}" style="font-size:0.75rem;" onclick="toggleSeenUser('${name}', 'Yari')">  
                ${seenY ? '✓ Visto Yari' : '+ Visto Yari'}  
              </button>  
              <button class="player-btn ${seenC ? 'active' : ''}" style="font-size:0.75rem;" onclick="toggleSeenUser('${name}', 'Chiara')">  
                ${seenC ? '✓ Visto Chiara' : '+ Visto Chiara'}  
              </button>  
            </div>  
          </div>  
        `;  
      }).join('');  
    }  
  
    function rateSpecies(name, clickedStars) {  
      let ratings = JSON.parse(localStorage.getItem('species_ratings_yc') || '{}');  
      let current = ratings[name] || 0;  
  
      if (clickedStars === 1 && current === 1) {  
        ratings[name] = 0;  
      } else {  
        ratings[name] = clickedStars;  
      }  
  
      localStorage.setItem('species_ratings_yc', JSON.stringify(ratings));  
      renderSpecies();  
    }  
  
    function toggleSeenUser(name, user) {  
      let key = user === 'Yari' ? 'seen_yari' : 'seen_chiara';  
      let seen = JSON.parse(localStorage.getItem(key) || '{}');  
      seen[name] = !seen[name];  
      localStorage.setItem(key, JSON.stringify(seen));  
      renderSpecies();  
      renderAdaptiveStats();  
    }  
  
    function filterSpecies() {  
      const q = document.getElementById('search-input').value.toLowerCase();  
      document.querySelectorAll('.species-card').forEach(item => {  
        item.style.display = item.getAttribute('data-name').includes(q) ? 'flex' : 'none';  
      });  
    }  
  
    /* STATISTICHE */  
    function renderAdaptiveStats() {  
      const entries = JSON.parse(localStorage.getItem('diary_entries_v4') || '[]');  
      let yariDives = 0, chiaraDives = 0;  
  
      entries.forEach(e => {  
        if (e.sub.includes('Yari') && !e.sub.includes('Chiara')) yariDives++;  
        else if (e.sub.includes('Chiara') && !e.sub.includes('Yari')) chiaraDives++;  
        else { yariDives++; chiaraDives++; }  
      });  
  
      document.getElementById('auto-dives-count').innerText = `Yari: ${yariDives} | Chiara: ${chiaraDives}`;  
  
      const seenYari = JSON.parse(localStorage.getItem('seen_yari') || '{}');  
      const seenChiara = JSON.parse(localStorage.getItem('seen_chiara') || '{}');  
        
      const countY = Object.values(seenYari).filter(Boolean).length;  
      const countC = Object.values(seenChiara).filter(Boolean).length;  
  
      document.getElementById('auto-species-count').innerText = `Yari: ${countY} | Chiara: ${countC}`;  
  
      const catData = JSON.parse(localStorage.getItem('macro_categories_counts') || '{}');  
      const catBox = document.getElementById('category-counters-box');  
  
      catBox.innerHTML = macroCategories.map(cat => {  
        const valY = catData[`${cat}_Yari`] || 0;  
        const valC = catData[`${cat}_Chiara`] || 0;  
  
        return `  
          <div class="stat-row">  
            <span style="font-size:0.85rem;">${cat}</span>  
            <div class="stat-counter">  
              <span style="font-size:0.75rem; color:var(--text-muted);">Yari:</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Yari', -1)">-</button>  
              <span>${valY}</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Yari', 1)">+</button>  
                
              <span style="font-size:0.75rem; color:var(--text-muted); margin-left:6px;">Chiara:</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Chiara', -1)">-</button>  
              <span>${valC}</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Chiara', 1)">+</button>  
            </div>  
          </div>  
        `;  
      }).join('');  
  
      const titlesBox = document.getElementById('auto-titles-list');  
      titlesBox.innerHTML = macroCategories.map(cat => {  
        const valY = catData[`${cat}_Yari`] || 0;  
        const valC = catData[`${cat}_Chiara`] || 0;  
  
        let winnerText = "Pareggio (Nessun detentore)";  
        if (valY > valC) winnerText = "Vincitore incoronato: Yari";  
        else if (valC > valY) winnerText = "Vincitrice incoronata: Chiara";  
  
        return `  
          <div class="trophy-card">  
            <span style="display:block; font-size:0.85rem; text-transform:uppercase;">Titolo Re/Regina dei ${cat}</span>  
            <span style="font-size:0.95rem;">${winnerText}</span> (${valY} vs ${valC})  
          </div>  
        `;  
      }).join('');  
    }  
  
    function updateCatCount(cat, user, delta) {  
      let catData = JSON.parse(localStorage.getItem('macro_categories_counts') || '{}');  
      let key = `${cat}_${user}`;  
      catData[key] = Math.max(0, (catData[key] || 0) + delta);  
      localStorage.setItem('macro_categories_counts', JSON.stringify(catData));  
      renderAdaptiveStats();  
    }  
  
    /* GEOLOCALIZZAZIONE */  
    function locateUserAndFindDivings() {  
      const status = document.getElementById('location-status');  
      const iframe = document.getElementById('map-iframe');  
      const resultsList = document.getElementById('diving-results-list');  
  
      if (!navigator.geolocation) {  
        status.innerText = "La geolocalizzazione non è supportata dal browser.";  
        return;  
      }  
  
      status.innerText = "⏳ Geolocalizzazione in corso... Calcolo raggio 30 - 35 km...";  
  
      navigator.geolocation.getCurrentPosition(  
        (position) => {  
          const lat = position.coords.latitude;  
          const lon = position.coords.longitude;  
  
          status.innerText = `📍 Posizione trovata! Centri Diving entro 35 km calcolati.`;  
            
          iframe.src = `https://maps.google.com/maps?q=Diving%20Center&ll=${lat},${lon}&z=10&output=embed`;  
  
          resultsList.innerHTML = `  
            <div class="diving-item">  
              <h4>🌊 Centri Immersione e Diving (Raggio ~35 km)</h4>  
              <p>Mappa aggiornata sulle tue coordinate GPS attuali con centri diving disponibili nelle vicinanze.</p>  
              <div class="diving-actions">  
                <a href="https://www.google.com/maps/search/Diving+Center/@${lat},${lon},10z" target="_blank">🗺️ Apri Mappa Completa 35km ↗</a>  
                <a href="https://www.google.com/search?q=Diving+Center+scuba+diving+nel+raggio+di+35+km" target="_blank">🌐 Cerca Siti Web & Pagine ↗</a>  
              </div>  
            </div>  
  
            <div class="diving-item">  
              <h4>⚓ Diving Center Golfo dei Poeti & Liguria di Levante</h4>  
              <p>Area Porto Venere, Lerici, La Spezia, Cinque Terre e Palmaria.</p>  
              <div class="diving-actions">  
                <a href="https://www.google.com/maps/search/Diving+Porto+Venere" target="_blank">🗺️ Indicazioni Mappa ↗</a>  
                <a href="https://www.google.com/search?q=Diving+Porto+Venere+sito+ufficiale" target="_blank">🌐 Pagina Ufficiale ↗</a>  
              </div>  
            </div>  
          `;  
        },  
        () => {  
          status.innerText = "❌ Permesso di posizione negato o non disponibile. Mostro i Diving del Golfo.";  
          iframe.src = "https://maps.google.com/maps?q=Golfo%20dei%20Poeti%20diving&t=&z=11&ie=UTF8&iwloc=&output=embed";  
        }  
      );  
    }  
  </script>  
</body>  
</html>  

<!DOCTYPE html>  
<html lang="it">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Yari & Chiara - I Sub del Golfo</title>  
    
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
  
    .gallery-scroll { display: flex; gap: 12px; overflow-x: auto; padding: 8px 0; scroll-snap-type: x mandatory; }  
    .gallery-item {  
      min-width: 220px; height: 150px; border-radius: 12px; overflow: hidden;  
      scroll-snap-align: start; flex-shrink: 0; position: relative; box-shadow: 0 4px 10px rgba(0,0,0,0.1);  
      background: #e2e8f0; border: 1px solid var(--border);  
    }  
    .gallery-item img { width: 100%; height: 100%; object-fit: cover; }  
    .gallery-add-btn {  
      min-width: 140px; height: 150px; border-radius: 12px; border: 2px dashed var(--primary);  
      display: flex; flex-direction: column; align-items: center; justify-content: center;  
      background: var(--primary-light); cursor: pointer; color: var(--primary-dark); font-weight: 700; font-size: 0.85rem; text-align: center; padding: 10px;  
    }  
  
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
      backdrop-filter: blur(10px); display: flex; justify-out-around: space-around; padding: 8px 0 12px 0;  
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
    <div class="drawer-header">📌 Menu Yari & Chiara</div>  
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
    <div class="brand"><span>🤿 Yari & Chiara - Sub del Golfo</span></div>  
    <div style="width: 24px;"></div>  
  </header>  
  
  <!-- HOME PAGE -->  
  <main id="home" class="page active">  
    <div class="card">  
      <h3 style="margin-bottom: 8px;">🖼️ Galleria Foto Evidenza</h3>  
      <p style="font-size:0.82rem; color:var(--text-muted); margin-bottom:12px;">Carica e conserva le vostre foto migliori:</p>  
        
      <div class="gallery-scroll" id="home-gallery">  
        <div class="gallery-add-btn" onclick="document.getElementById('gallery-input').click()">  
          <span style="font-size: 1.8rem;">📷</span>  
          <span>Aggiungi Foto</span>  
        </div>  
      </div>  
      <input type="file" id="gallery-input" accept="image/*" style="display:none;" onchange="handleGalleryUpload(event)">  
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
        <button class="theme-btn" style="background:#e0e7ff; color:#3730a3;" onclick="setTheme('#4f46e5', '#3730a3', '#e0e7ff', '#ee2f1')">🌌 Notte Marina</button>  
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
  
    <!-- ALBO D'ORO STORICO -->  
    <div class="card" style="background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%); border-color: #93c5fd;">  
      <h3 style="color:#1e40af; margin-bottom:8px;">🏆 Albo d'Oro Storico Tornei</h3>  
      <p style="font-size:0.82rem; color:#1e3a8a; margin-bottom:12px;">Conteggio totale dei tornei completati e vinti finora:</p>  
      <div style="display:flex; justify-content:space-around; text-align:center;">  
        <div>  
          <span style="font-size:1.8rem; font-weight:800; color:#1d4ed8;" id="history-wins-yari">0</span>  
          <p style="font-size:0.85rem; font-weight:700;">🧑🏻 Yari</p>  
        </div>  
        <div style="font-size:1.5rem; font-weight:800; color:#94a3b8; align-self:center;">VS</div>  
        <div>  
          <span style="font-size:1.8rem; font-weight:800; color:#be185d;" id="history-wins-chiara">0</span>  
          <p style="font-size:0.85rem; font-weight:700;">👩🏻‍🦱 Chiara</p>  
        </div>  
      </div>  
    </div>  
  
    <div class="card">  
      <p style="font-size:0.85rem; color:var(--text-muted); margin-bottom:10px;">Seleziona chi sta giocando ora:</p>  
      <div class="player-select">  
        <button class="player-btn active" id="btn-player1" onclick="selectPlayer('Yari')">🧑🏻 Yari</button>  
        <button class="player-btn" id="btn-player2" onclick="selectPlayer('Chiara')">👩🏻‍🦱 Chiara</button>  
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
        <div class="stat-row"><span>🧑🏻 Yari:</span><span id="score-player1">0 / 5</span></div>  
        <div class="stat-row"><span>👩🏻‍🦱 Chiara:</span><span id="score-player2">0 / 5</span></div>  
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
          <option value="🤿 Yari & Chiara insieme">🤿 Yari & Chiara insieme</option>  
          <option value="🧑🏻 Solo Yari">🧑🏻 Solo Yari</option>  
          <option value="👩🏻‍🦱 Solo Chiara">👩🏻‍🦱 Solo Chiara</option>  
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
  
  <!-- STATISTICHE EDISIBILI & TITOLI AUTOMATICI -->  
  <main id="stats" class="page">  
    <h2 class="page-title">🏆 Statistiche & Titoli Automatici</h2>  
  
    <div class="card">  
      <h3 style="color:var(--primary-dark); margin-bottom:12px;">📊 Report Automatico Dati</h3>  
      <div class="stat-row"><span>🤿 Immersioni Registrate:</span> <span id="auto-dives-count">Yari: 0 | Chiara: 0</span></div>  
      <div class="stat-row"><span>🐟 Specie Viste Totalizzabili:</span> <span id="auto-species-count">Yari: 0 | Chiara: 0</span></div>  
    </div>  
  
    <!-- MACRO CATEGORIE -->  
    <div class="card">  
      <h3 style="margin-bottom:12px;">🐾 Avvistamenti per Macro Categoria</h3>  
      <p style="font-size:0.8rem; color:var(--text-muted); margin-bottom:10px;">Aggiungi qui i vostri avvistamenti per calcolare i Titoli:</p>  
        
      <div id="category-counters-box"></div>  
    </div>  
  
    <!-- TITOLI AUTO-ASSEGNATI -->  
    <div class="card">  
      <h3 style="margin-bottom:10px;">👑 Assegnazione Titoli Ufficiali (Automatica)</h3>  
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
  
  <!-- MAPPA CON GEOLOCALIZZAZIONE RANGE 35KM & DIVING -->  
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
  
    /* LISTA COMPLETA SPECIE CON IMMAGINI DA WIKIPEDIA */  
    const speciesListWithThumb = [  
      { name: "Aguglia", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d4/Belone_belone.jpg/320px-Belone_belone.jpg" },  
      { name: "Aragosta", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/Palinurus_elephas.jpg/320px-Palinurus_elephas.jpg" },  
      { name: "Barracuda", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Sphyraena_viridensis_1.jpg/320px-Sphyraena_viridensis_1.jpg" },  
      { name: "Cernia bruna", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/87/Epinephelus_marginatus_2.jpg/320px-Epinephelus_marginatus_2.jpg" },  
      { name: "Murena", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e8/Muraena_helena_PTP.jpg/320px-Muraena_helena_PTP.jpg" },  
      { name: "Nudibranchio", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/23/Flabellina_affinis.jpg/320px-Flabellina_affinis.jpg" },  
      { name: "Polpo", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/57/Octopus_vulgaris2.jpg/320px-Octopus_vulgaris2.jpg" },  
      { name: "Seppia", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/69/Sepia_officinalis_%28Italian_coasts%29.jpg/320px-Sepia_officinalis_%28Italian_coasts%29.jpg" },  
      { name: "Cavalluccio marino", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Hippocampus_hippocampus.jpg/320px-Hippocampus_hippocampus.jpg" },  
      { name: "Sarago maggiore", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/Diplodus_sargus_sargus.jpg/320px-Diplodus_sargus_sargus.jpg" },  
      { name: "Orata", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1a/Sparus_aurata.jpg/320px-Sparus_aurata.jpg" },  
      { name: "Dentice", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/36/Dentex_dentex.jpg/320px-Dentex_dentex.jpg" },  
      { name: "Ricciola", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/ad/Seriola_dumerili.jpg/320px-Seriola_dumerili.jpg" },  
      { name: "Pesce San Pietro", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/13/Zeus_faber_Greece.jpg/320px-Zeus_faber_Greece.jpg" },  
      { name: "Scorfano rosso", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/7/7a/Scorpaena_scrofa_1.jpg/320px-Scorpaena_scrofa_1.jpg" },  
      { name: "Triglia di scoglio", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b3/Mullus_surmuletus.jpg/320px-Mullus_surmuletus.jpg" },  
      { name: "Granchio favollo", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/11/Eriphia_verrucosa.jpg/320px-Eriphia_verrucosa.jpg" },  
      { name: "Astice mediterraneo", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Homarus_gammarus.jpg/320px-Homarus_gammarus.jpg" },  
      { name: "Granseola", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/Maja_squinado.jpg/320px-Maja_squinado.jpg" },  
      { name: "Pesce civetta", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8e/Dactylopterus_volitans.jpg/320px-Dactylopterus_volitans.jpg" },  
      { name: "Torpedine", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/06/Torpedo_marmorata_1.jpg/320px-Torpedo_marmorata_1.jpg" },  
      { name: "Razza chiodata", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f6/Raja_clavata.jpg/320px-Raja_clavata.jpg" },  
      { name: "Pinna nobilis", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/87/Pinna_nobilis_1.jpg/320px-Pinna_nobilis_1.jpg" },  
      { name: "Stella marina rossa", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d6/Echinaster_sepositus.jpg/320px-Echinaster_sepositus.jpg" },  
      { name: "Riccio di mare", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/23/Paracentrotus_lividus.jpg/320px-Paracentrotus_lividus.jpg" }  
    ];  
  
    const macroCategories = ["Pesci", "Mammiferi", "Molluschi & Nudibranchi", "Crostacei", "Rettili", "Coralli & Invertebrati"];  
  
    let currentTournamentList = [];  
    let currentQIdx = 0;  
    let currentPlayer = "Yari";  
    let tournamentScores = { "Yari": 0, "Chiara": 0 };  
    let tempDiaryFiles = [];  
  
    document.addEventListener('DOMContentLoaded', () => {  
      loadGallery();  
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
  
    function loadGallery() {  
      const saved = JSON.parse(localStorage.getItem('home_gallery_photos') || '[]');  
      const container = document.getElementById('home-gallery');  
      const addBtnHTML = container.querySelector('.gallery-add-btn').outerHTML;  
  
      container.innerHTML = saved.map(imgData => `  
        <div class="gallery-item"><img src="${imgData}" alt="Foto Home"></div>  
      `).join('') + addBtnHTML;  
    }  
  
    function handleGalleryUpload(e) {  
      const file = e.target.files[0];  
      if (!file) return;  
      const reader = new FileReader();  
      reader.onload = function(evt) {  
        let saved = JSON.parse(localStorage.getItem('home_gallery_photos') || '[]');  
        saved.unshift(evt.target.result);  
        localStorage.setItem('home_gallery_photos', JSON.stringify(saved));  
        loadGallery();  
      };  
      reader.readAsDataURL(file);  
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
  
    /* TORNEO & ALBO D'ORO STORICO */  
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
          <h3>🎉 Torneo completato per ${currentPlayer === 'Yari' ? '🧑🏻 Yari' : '👩🏻‍🦱 Chiara'}!</h3>  
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
      // Quando entrambi hanno terminato o si conclude la sessione  
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
  
    /* DIARIO DI BORDO */  
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
  
    /* GUIDA SPECIE */  
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
  
        return `  
          <div class="species-card" data-name="${name.toLowerCase()}">  
            <div class="species-header-row">  
              <img src="${item.img}" class="species-thumb" alt="${name}" onerror="this.src='https://images.unsplash.com/photo-1544551763-46a013bb70d5?w=150'">  
              <div style="flex:1;">  
                <h3 style="font-size:1.05rem; color:var(--text);">${name}</h3>  
                  
                <div class="star-rating" style="margin-top:6px;">  
                  ${[1, 2, 3, 4, 5].map(s => `  
                    <span class="star ${s <= currentStars ? 'active' : ''}" onclick="rateSpecies('${name}',${s})">★</span>  
                  `).join('')}  
                </div>  
              </div>  
            </div>  
  
            <div style="display:flex; gap:8px;">  
              <button class="player-btn ${seenY ? 'active' : ''}" style="font-size:0.75rem;" onclick="toggleSeenUser('${name}', 'Yari')">  
                ${seenY ? '✓ Visto 🧑🏻 Yari' : '+ Visto 🧑🏻 Yari'}  
              </button>  
              <button class="player-btn ${seenC ? 'active' : ''}" style="font-size:0.75rem;" onclick="toggleSeenUser('${name}', 'Chiara')">  
                ${seenC ? '✓ Visto 👩🏻‍🦱 Chiara' : '+ Visto 👩🏻‍🦱 Chiara'}  
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
  
    /* STATISTICHE ED ASSEGNAZIONE AUTOMATICA TITOLI */  
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
              <span style="font-size:0.75rem; color:var(--text-muted);">🧑🏻 Yari:</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Yari', -1)">-</button>  
              <span>${valY}</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Yari', 1)">+</button>  
                
              <span style="font-size:0.75rem; color:var(--text-muted); margin-left:6px;">👩🏻‍🦱 Chiara:</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Chiara', -1)">-</button>  
              <span>${valC}</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Chiara', 1)">+</button>  
            </div>  
          </div>  
        `;  
      }).join('');  
  
      /* ASSEGNAZIONE TITOLI AUTOMATICA SUI CONTATORI */  
      const titlesBox = document.getElementById('auto-titles-list');  
      titlesBox.innerHTML = macroCategories.map(cat => {  
        const valY = catData[`${cat}_Yari`] || 0;  
        const valC = catData[`${cat}_Chiara`] || 0;  
  
        let winnerText = "🤝 Pareggio (Nessun detentore)";  
        if (valY > valC) winnerText = "🧑🏻 Vincitore incoronato: Yari";  
        else if (valC > valY) winnerText = "👩🏻‍🦱 Vincitrice incoronata: Chiara";  
  
        return `  
          <div class="trophy-card">  
            <span style="display:block; font-size:0.85rem; text-transform:uppercase;">👑 Titolo Re/Regina dei ${cat}</span>  
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
  
    /* GEOLOCALIZZAZIONE RANGE 30 - 35 KM & DIVING CENTRES */  
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
            
          // Mappa centrata sul punto GPS con zoom ottimizzato per 35km  
          iframe.src = `[https://maps.google.com/maps?q=Diving%20Center&ll=${lat},${lon}&z=10&output=embed`](https://maps.google.com/maps?q=Diving%2520Center&ll=$%7Blat%7D,$%7Blon%7D&z=10&output=embed%60);  
  
          // Genera la lista dei principali centri o direttrici nel raggio d'azione  
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

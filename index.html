<!DOCTYPE html>  
<html lang="it">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Yari & Chiara - I Sub del Golfo</title>  
    
  <link rel="preconnect" href="https://fonts.googleapis.com">  
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>  
  <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Playfair+Display:ital,wght@0,600;0,800;1,600&family=Press+Start+2P&family=Plus+Jakarta+Sans:wght@500;700;800&display=swap" rel="stylesheet">  
  
  <style>  
    :root {  
      --primary: #0284c7;  
      --primary-dark: #0369a1;  
      --primary-light: #e0f2fe;  
      --bg-color: #f0f9ff;  
      --bg-image: none;  
      --surface: rgba(255, 255, 255, 0.92);  
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
  
    .gallery-scroll {  
      display: flex; gap: 12px; overflow-x: auto; padding: 8px 0; scroll-snap-type: x mandatory;  
    }  
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
    .lvl-esperto { background: #8b5cf6; }  
  
    .player-select { display: flex; gap: 10px; margin-bottom: 14px; }  
    .player-btn {  
      flex: 1; padding: 10px; border-radius: 10px; border: 1px solid var(--border);  
      background: #ffffff; font-weight: 700; cursor: pointer; text-align: center; color: var(--text);  
    }  
    .player-btn.active { background: var(--primary); color: white; border-color: var(--primary-dark); }  
  
    .quiz-img-box { width: 100%; height: 180px; border-radius: 12px; overflow: hidden; margin-bottom: 12px; background: #cbd5e1; }  
    .quiz-img-box img { width: 100%; height: 100%; object-fit: cover; }  
  
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
    .species-thumb { width: 75px; height: 75px; border-radius: 12px; object-fit: cover; background: #e2e8f0; flex-shrink: 0; border: 1px solid #cbd5e1; display: block; }  
    .star-rating { display: flex; gap: 4px; font-size: 1.4rem; color: #cbd5e1; cursor: pointer; user-select: none; }  
    .star-rating .star.active { color: #f59e0b; }  
  
    .stat-row { display: flex; justify-content: space-between; align-items: center; padding: 10px 0; border-bottom: 1px solid #f1f5f9; font-weight: 600; }  
    .stat-counter { display: flex; align-items: center; gap: 8px; }  
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
  
    .diving-item { background: white; padding: 12px; border-radius: 10px; border: 1px solid var(--border); margin-top: 8px; }  
    .diving-item h4 { color: var(--primary-dark); font-size: 0.95rem; }  
    .diving-item p { font-size: 0.8rem; color: var(--text-muted); margin-top: 2px; }  
    .diving-actions { display: flex; gap: 10px; margin-top: 8px; }  
    .diving-actions a { font-size: 0.78rem; font-weight: 700; text-decoration: none; color: var(--primary); }  
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
      <li class="drawer-item" onclick="showPage('didyouknow'); toggleDrawer();">🎲 Lo Sapevi?</li>  
      <li class="drawer-item" onclick="showPage('tournament'); toggleDrawer();">⚔️ Torneo Quiz 1v1</li>  
      <li class="drawer-item" onclick="showPage('logbook'); toggleDrawer();">📖 Diario di Bordo</li>  
      <li class="drawer-item" onclick="showPage('guide'); toggleDrawer();">🐟 Guida Specie & Rating ⭐</li>  
      <li class="drawer-item" onclick="showPage('stats'); toggleDrawer();">🏆 Statistiche & Sfide</li>  
      <li class="drawer-item" onclick="showPage('safety'); toggleDrawer();">🚨 Sicurezza & SOS</li>  
      <li class="drawer-item" onclick="showPage('map'); toggleDrawer();">🗺️ Mappa & Diving Vicini</li>  
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
      <h3 style="margin-bottom: 8px;">🖼️ Le Nostre Foto in Evidenza</h3>  
      <p style="font-size:0.82rem; color:var(--text-muted); margin-bottom:12px;">Aggiungi le migliori foto delle vostre immersioni!</p>  
        
      <div class="gallery-scroll" id="home-gallery">  
        <div class="gallery-add-btn" onclick="document.getElementById('gallery-input').click()">  
          <span style="font-size: 1.8rem;">📷</span>  
          <span>Aggiungi Foto</span>  
        </div>  
      </div>  
      <input type="file" id="gallery-input" accept="image/*" style="display:none;" onchange="handleGalleryUpload(event)">  
    </div>  
  
    <div class="card">  
      <h3>🎨 Personalizza Grafica e Temi</h3>  
      <p style="font-size:0.82rem; color:var(--text-muted); margin-bottom:10px;">Scegli stile dei testi, sfondi e tavolozza colori:</p>  
  
      <label>1. Font dell'App</label>  
      <select onchange="changeAppFont(this.value)">  
        <option value="'Plus Jakarta Sans', sans-serif">Moderno / Sans-Serif</option>  
        <option value="'Playfair Display', serif">Elegante / Serif</option>  
        <option value="'Caveat', cursive">Corsivo / Scrittura a mano</option>  
        <option value="'Press Start 2P', cursive">Retro Arcade / Pixel</option>  
      </select>  
  
      <label>2. Tema Colore</label>  
      <div class="theme-picker-grid">  
        <button class="theme-btn" style="background:#e0f2fe; color:#0369a1;" onclick="setTheme('#0284c7', '#0369a1', '#e0f2fe', '#f0f9ff')">🌊 Oceano</button>  
        <button class="theme-btn" style="background:#ffedd5; color:#c2410c;" onclick="setTheme('#f97316', '#c2410c', '#ffedd5', '#fff7ed')">🌅 Tramonto</button>  
        <button class="theme-btn" style="background:#fce7f3; color:#be185d;" onclick="setTheme('#ec4899', '#be185d', '#fce7f3', '#fdf2f8')">🪸 Corallo</button>  
        <button class="theme-btn" style="background:#dcfce7; color:#15803d;" onclick="setTheme('#10b981', '#047857', '#dcfce7', '#f0fdf4')">🌿 Smeraldo</button>  
      </div>  
  
      <label>3. Sfondo Personalizzato (URL Immagine)</label>  
      <input type="text" id="bg-url-input" placeholder="Incolla link immagine di sfondo..." onchange="setCustomBg(this.value)">  
    </div>  
  </main>  
  
  <!-- LO SAPEVI -->  
  <main id="didyouknow" class="page">  
    <h2 class="page-title">🎲 Lo Sapevi Che...?</h2>  
    <div class="card dice-container">  
      <p style="font-size:0.9rem; color:var(--text-muted); margin-bottom:14px;">Tocca il dado per estrarre una curiosità!</p>  
      <button class="dice-btn" id="dice-btn" onclick="rollDice()">🎲</button>  
  
      <div class="fact-card" id="fact-card" style="display:none;">  
        <span class="fact-tag" id="fact-animal">Animale</span>  
        <p id="fact-text" style="font-weight:600; font-size:1rem; color:var(--text); line-height:1.4;"></p>  
      </div>  
    </div>  
  </main>  
  
  <!-- TORNEO QUIZ -->  
  <main id="tournament" class="page">  
    <h2 class="page-title">⚔ Torneo Quiz Yari vs Chiara</h2>  
  
    <div class="card">  
      <p style="font-size:0.85rem; color:var(--text-muted); margin-bottom:10px;">Seleziona chi sta giocando ora:</p>  
      <div class="player-select">  
        <button class="player-btn active" id="btn-player1" onclick="selectPlayer('Yari')">👤 Yari</button>  
        <button class="player-btn" id="btn-player2" onclick="selectPlayer('Chiara')">👩‍🦰 Chiara</button>  
      </div>  
  
      <div id="quiz-box">  
        <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:10px;">  
          <span id="quiz-progress" style="font-weight:800; font-size:0.9rem; color:var(--primary-dark);">Domanda 1 / 30</span>  
          <span id="quiz-level-badge" class="badge-level lvl-facile">FACILE</span>  
        </div>  
  
        <div class="quiz-img-box" id="quiz-img-container" style="display:none;">  
          <img id="quiz-img" src="" alt="Quiz Foto">  
        </div>  
  
        <p id="quiz-q-text" style="font-weight:700; font-size:1rem; margin-bottom:14px;"></p>  
        <div id="quiz-options-list" style="display:flex; flex-direction:column; gap:8px;"></div>  
        <div id="quiz-feedback-box" style="margin-top:12px; font-weight:700; font-size:0.88rem; display:none; padding:10px; border-radius:8px;"></div>  
        <button id="quiz-next-q" class="submit-btn" style="display:none; margin-top:10px;" onclick="nextTournamentQ()">Prossima Domanda ➔</button>  
      </div>  
    </div>  
  
    <div class="card">  
      <h3>🏆 Punteggi Torneo</h3>  
      <div style="margin-top:10px;">  
        <div class="stat-row"><span>👤 Yari:</span><span id="score-player1">0 / 30</span></div>  
        <div class="stat-row"><span>👩‍🦰 Chiara:</span><span id="score-player2">0 / 30</span></div>  
      </div>  
      <button class="submit-btn" style="background:#64748b; margin-top:14px;" onclick="resetTournament()">🔄 Rigenera Domande</button>  
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
          <option value="Entrambi">🤿 Yari & Chiara insieme</option>  
          <option value="Yari">👤 Solo Yari</option>  
          <option value="Chiara">👩‍🦰 Solo Chiara</option>  
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
    <h2 class="page-title">🐟 Specie Marine & Rating</h2>  
    <input type="text" id="search-input" style="margin-bottom:14px;" placeholder="🔍 Cerca specie..." onkeyup="filterSpecies()">  
    <div id="species-container"></div>  
  </main>  
  
  <!-- STATISTICHE EDISIBILI & ADATTIVE -->  
  <main id="stats" class="page">  
    <h2 class="page-title">🏆 Statistiche Yari vs Chiara</h2>  
  
    <!-- STATISTICHE AUTOMATICHE DAL SITO -->  
    <div class="card">  
      <h3 style="color:var(--primary-dark); margin-bottom:12px;">📊 Report Automatico Dati</h3>  
      <div class="stat-row"><span>🤿 Immersioni Registrate:</span> <span id="auto-dives-count">Yari: 0 | Chiara: 0</span></div>  
      <div class="stat-row"><span>🐟 Specie Viste Totalizzabili:</span> <span id="auto-species-count">Yari: 0 | Chiara: 0</span></div>  
    </div>  
  
    <!-- MACRO CATEGORIE EDISIBILI -->  
    <div class="card">  
      <h3 style="margin-bottom:12px;">🐾 Avvistamenti per Macro Categoria</h3>  
      <p style="font-size:0.8rem; color:var(--text-muted); margin-bottom:10px;">Aggiorna direttamente qui i vostri contatori:</p>  
        
      <div id="category-counters-box"></div>  
    </div>  
  
    <!-- TITOLI EDISIBILI -->  
    <div class="card">  
      <h3 style="margin-bottom:10px;">👑 Assegnazione Titoli Ufficiali</h3>  
      <p style="font-size:0.8rem; color:var(--text-muted); margin-bottom:10px;">Scegliete a chi appartiene ciascun titolo:</p>  
  
      <label>🏆 Titolo Nudibranchi</label>  
      <select onchange="saveTitle('nudibranchs', this.value)" id="title-nudibranchs">  
        <option value="Non assegnato">-- Seleziona Vincitore --</option>  
        <option value="Yari">Yari</option>  
        <option value="Chiara">Chiara</option>  
        <option value="Pareggio">Pareggio</option>  
      </select>  
  
      <label>📸 Miglior Fotografo/a</label>  
      <select onchange="saveTitle('photo', this.value)" id="title-photo">  
        <option value="Non assegnato">-- Seleziona Vincitore --</option>  
        <option value="Yari">Yari</option>  
        <option value="Chiara">Chiara</option>  
        <option value="Pareggio">Pareggio</option>  
      </select>  
  
      <label>🐙 Re/Regina dei Polpi</label>  
      <select onchange="saveTitle('octopus', this.value)" id="title-octopus">  
        <option value="Non assegnato">-- Seleziona Vincitore --</option>  
        <option value="Yari">Yari</option>  
        <option value="Chiara">Chiara</option>  
        <option value="Pareggio">Pareggio</option>  
      </select>  
  
      <div id="custom-trophies-list" style="margin-top:14px;"></div>  
    </div>  
  
    <div class="card">  
      <h3>➕ Aggiungi Nuova Categoria di Sfida</h3>  
      <form id="custom-challenge-form">  
        <label for="ch-title">Nome Sfida</label>  
        <input type="text" id="ch-title" placeholder="Es. Murena più grande vista" required>  
        <label for="ch-winner">Vincitore</label>  
        <select id="ch-winner">  
          <option value="Yari">Yari</option>  
          <option value="Chiara">Chiara</option>  
          <option value="Pareggio">Pareggio</option>  
        </select>  
        <button type="submit" class="submit-btn">Salva Titolo Sfida</button>  
      </form>  
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
  
  <!-- MAPPA CON GEOLOCALIZZAZIONE & DIVING CENTER VICINI -->  
  <main id="map" class="page">  
    <h2 class="page-title">🗺️ Mappa & Diving Nelle Vicinanze</h2>  
    <div class="card">  
      <button class="submit-btn" style="margin-bottom:12px;" onclick="locateUserAndFindDivings()">📍 Trova Diving Vicini alla Mia Posizione</button>  
      <div id="location-status" style="font-size:0.85rem; color:var(--text-muted); margin-bottom:10px; text-align:center;"></div>  
        
      <iframe id="map-iframe" style="width:100%; height:280px; border:none; border-radius:12px;" src="https://maps.google.com/maps?q=Golfo%20dei%20Poeti%20diving&t=&z=12&ie=UTF8&iwloc=&output=embed"></iframe>  
    </div>  
  
    <div class="card">  
      <h3>⚓ Diving Center Rilevati / Suggeriti</h3>  
      <div id="diving-results-list">  
        <p style="font-size:0.85rem; color:var(--text-muted); margin-top:8px;">Clicca sul pulsante sopra per localizzare i centri immersione vicini a te!</p>  
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
    const globalFacts = [  
      { animal: "Polpo", text: "I polpi hanno tre cuori e il loro sangue è di colore blu perché basato sul rame anziché sul ferro!" },  
      { animal: "Balenottera Azzurra", text: "La lingua di una balenottera azzurra pesa quanto un intero elefante adulto." },  
      { animal: "Gambero Mantide", text: "Può sferrare un pugno alla velocità di un proiettile calibro 22, capace di rompere i vetri degli acquari!" },  
      { animal: "Squalo Balena", text: "È il pesce più grande del mondo e la sua pelle può raggiungere fino a 10 cm di spessore." },  
      { animal: "Nudibranchio", text: "Alcuni nudibranchi mangiano meduse velenose e assimilano le loro cellule velenose per usarle come difesa personale!" }  
    ];  
  
    const masterQuizDb = [  
      { q: "Qual è il mammifero più grande del pianeta?", opts: ["Elefante Africano", "Balenottera Azzurra", "Capodoglio", "Squalo Balena"], c: 1, lvl: "facile" },  
      { q: "Quanti cuori possiede un polpo?", opts: ["1", "2", "3", "4"], c: 2, lvl: "facile" },  
      { q: "Di che colore è il sangue dei polpi?", opts: ["Rosso", "Blu", "Verde", "Trasparente"], c: 1, lvl: "medio" },  
      { q: "Quale pesce è noto per nascondersi negli anemonie?", opts: ["Pesce Pagliaccio", "Murena", "Spigola", "Sarago"], c: 0, lvl: "facile" },  
      { q: "I cavallucci marini maschi sono gli unici a partorire i piccoli?", opts: ["Vero", "Falso"], c: 0, lvl: "facile" }  
    ];  
  
    const speciesListWithThumb = [  
      { name: "Aguglia", img: "https://images.unsplash.com/photo-1544551763-46a013bb70d5?w=150" },  
      { name: "Aragosta", img: "https://images.unsplash.com/photo-1559827291-72ee739d0d9a?w=150" },  
      { name: "Barracuda", img: "https://images.unsplash.com/photo-1544551763-46a013bb70d5?w=150" },  
      { name: "Cernia bruna", img: "https://images.unsplash.com/photo-1582967788606-a171c1080cb0?w=150" },  
      { name: "Murena", img: "https://images.unsplash.com/photo-1582967788606-a171c1080cb0?w=150" },  
      { name: "Nudibranchio", img: "https://images.unsplash.com/photo-1545671913-b89ac1b4ac10?w=150" },  
      { name: "Polpo", img: "https://images.unsplash.com/photo-1545671913-b89ac1b4ac10?w=150" },  
      { name: "Seppia", img: "https://images.unsplash.com/photo-1545671913-b89ac1b4ac10?w=150" },  
      { name: "Cavalluccio marino", img: "https://images.unsplash.com/photo-1582967788606-a171c1080cb0?w=150" }  
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
      renderCustomTrophies();  
      loadSavedTheme();  
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
        const randomFact = globalFacts[Math.floor(Math.random() * globalFacts.length)];  
        document.getElementById('fact-animal').innerText = randomFact.animal;  
        document.getElementById('fact-text').innerText = randomFact.text;  
        document.getElementById('fact-card').style.display = 'block';  
      }, 300);  
    }  
  
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
        document.getElementById('quiz-box').innerHTML = `<h3>🎉 Torneo completato per ${currentPlayer}!</h3><p>Punteggio: ${tournamentScores[currentPlayer]} / ${currentTournamentList.length}</p>`;  
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
  
    function resetTournament() {  
      localStorage.removeItem('tournament_questions');  
      tournamentScores = { "Yari": 0, "Chiara": 0 };  
      localStorage.setItem('tournament_scores_yc', JSON.stringify(tournamentScores));  
      initTournament();  
    }  
  
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
              <img src="${item.img}" class="species-thumb" alt="${name}">  
              <div style="flex:1;">  
                <h3 style="font-size:1.05rem; color:var(--text);">${name}</h3>  
                  
                <!-- STELLE CON RIMOZIONE (SE CLICCHI 1 STELLA GIA' ATTIVA DIVENTA 0) -->  
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
  
      // Se clicca 1 stella quando è già impostata a 1, la resetta a 0 stelle  
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
  
    function renderAdaptiveStats() {  
      // 1. Dati Immersioni Automatici dal Diario  
      const entries = JSON.parse(localStorage.getItem('diary_entries_v4') || '[]');  
      let yariDives = 0, chiaraDives = 0;  
  
      entries.forEach(e => {  
        if (e.sub === 'Yari') yariDives++;  
        else if (e.sub === 'Chiara') chiaraDives++;  
        else { yariDives++; chiaraDives++; }  
      });  
  
      document.getElementById('auto-dives-count').innerText = `Yari: ${yariDives} | Chiara: ${chiaraDives}`;  
  
      // 2. Dati Specie Viste Automatici  
      const seenYari = JSON.parse(localStorage.getItem('seen_yari') || '{}');  
      const seenChiara = JSON.parse(localStorage.getItem('seen_chiara') || '{}');  
        
      const countY = Object.values(seenYari).filter(Boolean).length;  
      const countC = Object.values(seenChiara).filter(Boolean).length;  
  
      document.getElementById('auto-species-count').innerText = `Yari: ${countY} | Chiara: ${countC}`;  
  
      // 3. Macro Categorie Modificabili  
      const catData = JSON.parse(localStorage.getItem('macro_categories_counts') || '{}');  
      const catBox = document.getElementById('category-counters-box');  
  
      catBox.innerHTML = macroCategories.map(cat => {  
        const valY = catData[`${cat}_Yari`] || 0;  
        const valC = catData[`${cat}_Chiara`] || 0;  
  
        return `  
          <div class="stat-row">  
            <span style="font-size:0.85rem;">${cat}</span>  
            <div class="stat-counter">  
              <span style="font-size:0.78rem; color:var(--text-muted);">Yari:</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Yari', -1)">-</button>  
              <span>${valY}</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Yari', 1)">+</button>  
                
              <span style="font-size:0.78rem; color:var(--text-muted); margin-left:6px;">Chiara:</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Chiara', -1)">-</button>  
              <span>${valC}</span>  
              <button class="count-btn" onclick="updateCatCount('${cat}', 'Chiara', 1)">+</button>  
            </div>  
          </div>  
        `;  
      }).join('');  
  
      // Carica i titoli salvati  
      const savedTitles = JSON.parse(localStorage.getItem('assigned_titles_yc') || '{}');  
      if (savedTitles.nudibranchs) document.getElementById('title-nudibranchs').value = savedTitles.nudibranchs;  
      if (savedTitles.photo) document.getElementById('title-photo').value = savedTitles.photo;  
      if (savedTitles.octopus) document.getElementById('title-octopus').value = savedTitles.octopus;  
    }  
  
    function updateCatCount(cat, user, delta) {  
      let catData = JSON.parse(localStorage.getItem('macro_categories_counts') || '{}');  
      let key = `${cat}_${user}`;  
      catData[key] = Math.max(0, (catData[key] || 0) + delta);  
      localStorage.setItem('macro_categories_counts', JSON.stringify(catData));  
      renderAdaptiveStats();  
    }  
  
    function saveTitle(key, value) {  
      let savedTitles = JSON.parse(localStorage.getItem('assigned_titles_yc') || '{}');  
      savedTitles[key] = value;  
      localStorage.setItem('assigned_titles_yc', JSON.stringify(savedTitles));  
    }  
  
    document.getElementById('custom-challenge-form').addEventListener('submit', function(e) {  
      e.preventDefault();  
      const title = document.getElementById('ch-title').value;  
      const winner = document.getElementById('ch-winner').value;  
  
      let customList = JSON.parse(localStorage.getItem('custom_trophies_yc') || '[]');  
      customList.push({ title, winner });  
      localStorage.setItem('custom_trophies_yc', JSON.stringify(customList));  
  
      this.reset();  
      renderCustomTrophies();  
    });  
  
    function renderCustomTrophies() {  
      const container = document.getElementById('custom-trophies-list');  
      const customList = JSON.parse(localStorage.getItem('custom_trophies_yc') || '[]');  
      container.innerHTML = customList.map(item => `  
        <div class="trophy-card">🏅 ${item.title}: <strong>${item.winner}</strong></div>  
      `).join('');  
    }  
  
    /* MAPPA CON GEOLOCALIZZAZIONE & DIVING CENTRES */  
    function locateUserAndFindDivings() {  
      const status = document.getElementById('location-status');  
      const iframe = document.getElementById('map-iframe');  
      const resultsList = document.getElementById('diving-results-list');  
  
      if (!navigator.geolocation) {  
        status.innerText = "La geolocalizzazione non è supportata dal tuo browser.";  
        return;  
      }  
  
      status.innerText = "⏳ Ricerca della tua posizione in corso...";  
  
      navigator.geolocation.getCurrentPosition(  
        (position) => {  
          const lat = position.coords.latitude;  
          const lon = position.coords.longitude;  
  
          status.innerText = `📍 Posizione trovata! Caricamento Diving nelle vicinanze...`;  
          iframe.src = `https://maps.google.com/maps?q=${lat},${lon}&t=&z=13&ie=UTF8&iwloc=&output=embed`;  
  
          // Genera lista dinamica di ricerca Diving Center attorno alle tue coordinate  
          const searchUrlMaps = `https://www.google.com/maps/search/Diving+Center/@${lat},${lon},12z`;  
          const searchUrlWeb = `https://www.google.com/search?q=Diving+Center+nei+vicini+a+me`;  
  
          resultsList.innerHTML = `  
            <div class="diving-item">  
              <h4>🔍 Diving Center attorno alla tua posizione</h4>  
              <p>Mappa interattiva aggiornata sulle tue coordinate GPS.</p>  
              <div class="diving-actions">  
                <a href="${searchUrlMaps}" target="_blank">🗺️ Apri su Google Maps ↗</a>  
                <a href="${searchUrlWeb}" target="_blank">🌐 Cerca Siti Web Diving ↗</a>  
              </div>  
            </div>  
          `;  
        },  
        () => {  
          status.innerText = "❌ Impossibile accedere alla tua posizione GPS. Mostro i Diving del Golfo.";  
          iframe.src = "https://maps.google.com/maps?q=Golfo%20dei%20Poeti%20diving&t=&z=12&ie=UTF8&iwloc=&output=embed";  
        }  
      );  
    }  
  </script>  
</body>  
</html>  

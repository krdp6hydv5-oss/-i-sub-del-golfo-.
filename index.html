<!DOCTYPE html>  
<html lang="it">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Y&C - I Sub del Golfo</title>  
  <style>  
    :root {  
      --primary: #0284c7;  
      --primary-dark: #0369a1;  
      --primary-light: #e0f2fe;  
      --danger: #ef4444;  
      --danger-dark: #dc2626;  
      --success: #22c55e;  
      --bg: #f0f9ff;  
      --surface: #ffffff;  
      --text: #0f172a;  
      --text-muted: #64748b;  
      --border: #bae6fd;  
      --radius: 16px;  
      --shadow: 0 10px 15px -3px rgba(0,0,0,0.08);  
    }  
  
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }  
      
    body {   
      background-color: var(--bg);   
      color: var(--text);   
      padding-bottom: 90px;  
      position: relative;  
      min-height: 100vh;  
      overflow-x: hidden;  
    }  
  
    /* BOLLE ANIMATE */  
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
  
    /* Header */  
    .header {  
      background: linear-gradient(135deg, #0284c7 0%, #0369a1 100%);  
      color: white; padding: 16px 20px; position: sticky; top: 0; z-index: 100;  
      box-shadow: 0 4px 12px rgba(2, 132, 199, 0.25);  
      display: flex; align-items: center; justify-content: space-between;  
    }  
    .brand { display: flex; align-items: center; gap: 10px; font-weight: 800; font-size: 1.1rem; }  
    .menu-toggle { background: none; border: none; color: white; font-size: 1.6rem; cursor: pointer; padding: 4px; }  
  
    /* Drawer Side Menu */  
    .drawer-overlay {  
      position: fixed; top: 0; left: 0; right: 0; bottom: 0;  
      background: rgba(15, 23, 42, 0.5); backdrop-filter: blur(4px);  
      z-index: 1000; opacity: 0; visibility: hidden; transition: all 0.3s ease;  
    }  
    .drawer-overlay.active { opacity: 1; visibility: visible; }  
    .drawer {  
      position: fixed; top: 0; left: -280px; width: 280px; height: 100%;  
      background: var(--surface); z-index: 1001; transition: left 0.3s ease;  
      display: flex; flex-direction: column; box-shadow: 5px 0 25px rgba(0,0,0,0.15);  
    }  
    .drawer.active { left: 0; }  
    .drawer-header { background: linear-gradient(135deg, #0284c7 0%, #0369a1 100%); color: white; padding: 24px 20px; font-weight: 800; font-size: 1.2rem; }  
    .drawer-menu { list-style: none; padding: 12px 0; overflow-y: auto; flex: 1; }  
    .drawer-item { padding: 14px 20px; display: flex; align-items: center; gap: 12px; color: var(--text); font-weight: 600; cursor: pointer; border-bottom: 1px solid #f1f5f9; }  
    .drawer-item:hover { background: var(--primary-light); color: var(--primary-dark); }  
  
    /* Pages */  
    .page { display: none; padding: 16px; max-width: 650px; margin: 0 auto; position: relative; z-index: 1; }  
    .page.active { display: block; }  
    .page-title { font-size: 1.4rem; font-weight: 800; color: #0f172a; margin-bottom: 14px; }  
  
    /* Cards */  
    .card {   
      background: rgba(255, 255, 255, 0.95); backdrop-filter: blur(8px);  
      border-radius: var(--radius); padding: 18px; margin-bottom: 16px;   
      box-shadow: var(--shadow); border: 1px solid var(--border);   
    }  
  
    /* WIDGET FOTO HOME (GALLERIA SCORREVOLE) */  
    .gallery-widget { margin-bottom: 16px; }  
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
      background: rgba(224, 242, 254, 0.4); cursor: pointer; color: var(--primary-dark); font-weight: 700; font-size: 0.85rem; text-align: center; padding: 10px;  
    }  
  
    /* LO SAPEVI - DADO */  
    .dice-container { text-align: center; padding: 20px 10px; }  
    .dice-btn {  
      font-size: 4rem; background: none; border: none; cursor: pointer; transition: transform 0.3s;  
      user-select: none; display: inline-block;  
    }  
    .dice-btn:active { transform: scale(0.85) rotate(180deg); }  
    .fact-card {  
      background: linear-gradient(135deg, #ffffff 0%, #e0f2fe 100%);  
      border: 2px solid var(--primary); border-radius: 18px; padding: 20px;  
      margin-top: 16px; text-align: center; box-shadow: var(--shadow);  
    }  
    .fact-tag { background: var(--primary); color: white; font-weight: 800; font-size: 0.75rem; padding: 4px 12px; border-radius: 20px; text-transform: uppercase; display: inline-block; margin-bottom: 10px; }  
  
    /* TORNEO QUIZ */  
    .badge-level { font-size: 0.75rem; font-weight: 800; padding: 4px 10px; border-radius: 12px; color: white; display: inline-block; }  
    .lvl-facile { background: #22c55e; }  
    .lvl-medio { background: #f59e0b; }  
    .lvl-difficile { background: #ef4444; }  
    .lvl-esperto { background: #8b5cf6; }  
  
    .player-select { display: flex; gap: 10px; margin-bottom: 14px; }  
    .player-btn {  
      flex: 1; padding: 10px; border-radius: 10px; border: 1px solid var(--border);  
      background: #f8fafc; font-weight: 700; cursor: pointer; text-align: center;  
    }  
    .player-btn.active { background: var(--primary); color: white; border-color: var(--primary-dark); }  
  
    .quiz-img-box { width: 100%; height: 180px; border-radius: 12px; overflow: hidden; margin-bottom: 12px; background: #cbd5e1; }  
    .quiz-img-box img { width: 100%; height: 100%; object-fit: cover; }  
  
    /* DIARIO STILE QUADERNO */  
    .log-entry {  
      background: #fff; border-left: 5px solid var(--primary); border-radius: 12px;  
      padding: 16px; margin-bottom: 16px; box-shadow: var(--shadow); border: 1px solid var(--border); border-left-width: 5px;  
    }  
    .log-media-grid { display: flex; gap: 8px; overflow-x: auto; margin-top: 10px; }  
    .log-media-item { width: 100px; height: 100px; border-radius: 8px; overflow: hidden; flex-shrink: 0; background: #000; }  
    .log-media-item img, .log-media-item video { width: 100%; height: 100%; object-fit: cover; }  
  
    /* SPECIE & STELLE */  
    .species-card {  
      background: white; border-radius: 16px; padding: 16px; margin-bottom: 16px;  
      box-shadow: var(--shadow); border: 1px solid var(--border); display: flex; flex-direction: column; gap: 12px;  
    }  
    .species-header-row { display: flex; gap: 14px; align-items: center; }  
    .species-thumb { width: 75px; height: 75px; border-radius: 12px; object-fit: cover; background: #e2e8f0; flex-shrink: 0; border: 1px solid #cbd5e1; }  
    .star-rating { display: flex; gap: 4px; font-size: 1.4rem; color: #cbd5e1; cursor: pointer; }  
    .star-rating .star.active { color: #f59e0b; }  
  
    /* STATISTICHE SCHERZOSE */  
    .stat-row { display: flex; justify-content: space-between; padding: 10px 0; border-bottom: 1px solid #f1f5f9; font-weight: 600; }  
    .trophy-card { background: linear-gradient(135deg, #fef9c3 0%, #fef08a 100%); border: 1px solid #fde047; padding: 12px; border-radius: 12px; margin-bottom: 8px; font-weight: 700; color: #854d0e; }  
  
    /* Forms */  
    label { display: block; font-size: 0.85rem; font-weight: 700; color: #334155; margin-top: 10px; margin-bottom: 4px; }  
    input, textarea, select { width: 100%; padding: 12px; border: 1px solid var(--border); border-radius: 10px; font-size: 0.95rem; background: #f8fafc; outline: none; }  
    button.submit-btn { background: linear-gradient(135deg, #0284c7 0%, #0369a1 100%); color: white; border: none; padding: 12px; border-radius: 10px; width: 100%; font-size: 1rem; font-weight: 700; cursor: pointer; margin-top: 14px; }  
  
    /* Bottom Nav */  
    .bottom-nav {  
      position: fixed; bottom: 0; left: 0; right: 0; background: rgba(255, 255, 255, 0.98);  
      backdrop-filter: blur(10px); display: flex; justify-content: space-around; padding: 8px 0 12px 0;  
      border-top: 1px solid var(--border); z-index: 1000;  
    }  
    .nav-btn { background: none; border: none; display: flex; flex-direction: column; align-items: center; color: #94a3b8; font-size: 0.72rem; font-weight: 600; flex: 1; cursor: pointer; }  
    .nav-btn.active { color: var(--primary); font-weight: 800; }  
    .nav-icon { font-size: 1.35rem; margin-bottom: 2px; }  
  </style>  
</head>  
<body>  
  
  <!-- BOLLE -->  
  <div class="bubbles-container">  
    <div class="bubble"></div><div class="bubble"></div><div class="bubble"></div><div class="bubble"></div><div class="bubble"></div>  
  </div>  
  
  <!-- MENU LATERALE -->  
  <div class="drawer-overlay" id="drawer-overlay" onclick="toggleDrawer()"></div>  
  <aside class="drawer" id="drawer">  
    <div class="drawer-header">📌 Menu Navigazione</div>  
    <ul class="drawer-menu">  
      <li class="drawer-item" onclick="showPage('home'); toggleDrawer();">🏠 Home</li>  
      <li class="drawer-item" onclick="showPage('tournament'); toggleDrawer();">⚔️ Torneo Quiz 1v1</li>  
      <li class="drawer-item" onclick="showPage('didyouknow'); toggleDrawer();">🎲 Lo Sapevi? (Curiosità)</li>  
      <li class="drawer-item" onclick="showPage('logbook'); toggleDrawer();">📖 Diario di Bordo</li>  
      <li class="drawer-item" onclick="showPage('guide'); toggleDrawer();">🐟 Guida Specie & Rating ⭐</li>  
      <li class="drawer-item" onclick="showPage('stats'); toggleDrawer();">🏆 Le Nostre Statistiche</li>  
      <li class="drawer-item" onclick="showPage('safety'); toggleDrawer();">🚨 Sicurezza & Schede SOS</li>  
      <li class="drawer-item" onclick="showPage('map'); toggleDrawer();">🗺️ Mappa & Centri Diving</li>  
      <li class="drawer-item" onclick="showPage('qrcode'); toggleDrawer();">🔲 QR Code Web App</li>  
      <li class="drawer-item" onclick="window.open('https://www.3bmeteo.com', '_blank'); toggleDrawer();">🌤️ Meteo & Mare ↗</li>  
    </ul>  
  </aside>  
  
  <!-- TOP BAR -->  
  <header class="header">  
    <button class="menu-toggle" onclick="toggleDrawer()">☰</button>  
    <div class="brand"><span>🤿 Y&C - I Sub del Golfo</span></div>  
    <div style="width: 24px;"></div>  
  </header>  
  
  <!-- HOME PAGE -->  
  <main id="home" class="page active">  
    <div class="card">  
      <h3 style="margin-bottom: 8px;">🖼️ Le Nostre Foto in Evidenza</h3>  
      <p style="font-size:0.82rem; color:var(--text-muted); margin-bottom:12px;">Carica le foto più belle delle vostre immersioni per personalizzare lo sfondo della Home!</p>  
        
      <div class="gallery-scroll" id="home-gallery">  
        <!-- Foto caricate dinamiche -->  
        <div class="gallery-add-btn" onclick="document.getElementById('gallery-input').click()">  
          <span style="font-size: 1.8rem;">📷</span>  
          <span>Aggiungi Foto</span>  
        </div>  
      </div>  
      <input type="file" id="gallery-input" accept="image/*" style="display:none;" onchange="handleGalleryUpload(event)">  
    </div>  
  
    <div class="card" onclick="showPage('tournament')" style="cursor:pointer; background: linear-gradient(135deg, #e0f2fe 0%, #ffffff 100%); border-color: var(--primary);">  
      <h3>⚔️ Torneo Quiz 1v1</h3>  
      <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 4px;">30 domande casuali per sfidare la tua amica. Classifica in tempo reale!</p>  
    </div>  
  
    <div class="card" onclick="showPage('didyouknow')" style="cursor:pointer;">  
      <h3>🎲 Lo Sapevi Che...?</h3>  
      <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 4px;">Lancia il dado e scopri fatti incredibili sulle creature marine e terrestri!</p>  
    </div>  
  </main>  
  
  <!-- LO SAPEVI (CURIOSTA') -->  
  <main id="didyouknow" class="page">  
    <h2 class="page-title">🎲 Lo Sapevi Che...?</h2>  
    <div class="card dice-container">  
      <p style="font-size:0.9rem; color:var(--text-muted); margin-bottom:14px;">Tocca il dado per estrarre una curiosità dal mondo animale!</p>  
      <button class="dice-btn" id="dice-btn" onclick="rollDice()">🎲</button>  
  
      <div class="fact-card" id="fact-card" style="display:none;">  
        <span class="fact-tag" id="fact-animal">Animale</span>  
        <p id="fact-text" style="font-weight:600; font-size:1rem; color:#0f172a; line-height:1.4;"></p>  
      </div>  
    </div>  
  </main>  
  
  <!-- TORNEO QUIZ -->  
  <main id="tournament" class="page">  
    <h2 class="page-title">⚔️ Torneo Quiz (30 Domande)</h2>  
  
    <div class="card">  
      <p style="font-size:0.85rem; color:var(--text-muted); margin-bottom:10px;">Chi sta giocando ora?</p>  
      <div class="player-select">  
        <button class="player-btn active" id="btn-player1" onclick="selectPlayer('Tu')">👤 Tu</button>  
        <button class="player-btn" id="btn-player2" onclick="selectPlayer('La tua Amica')">👩‍🦰 La tua Amica</button>  
      </div>  
  
      <div id="quiz-box">  
        <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:10px;">  
          <span id="quiz-progress" style="font-weight:800; font-size:0.9rem; color:var(--primary-dark);">Domanda 1 / 30</span>  
          <span id="quiz-level-badge" class="badge-level lvl-facile">FACILE</span>  
        </div>  
  
        <div class="quiz-img-box" id="quiz-img-container" style="display:none;">  
          <img id="quiz-img" src="" alt="Animale Quiz">  
        </div>  
  
        <p id="quiz-q-text" style="font-weight:700; font-size:1rem; margin-bottom:14px;"></p>  
        <div id="quiz-options-list" style="display:flex; flex-direction:column; gap:8px;"></div>  
        <div id="quiz-feedback-box" style="margin-top:12px; font-weight:700; font-size:0.88rem; display:none; padding:10px; border-radius:8px;"></div>  
        <button id="quiz-next-q" class="submit-btn" style="display:none; margin-top:10px;" onclick="nextTournamentQ()">Prossima Domanda ➔</button>  
      </div>  
    </div>  
  
    <!-- CLASSIFICA TORNEO -->  
    <div class="card">  
      <h3>🏆 Classifica Torneo Attuale</h3>  
      <div style="margin-top:10px;">  
        <div class="stat-row"><span>👤 Tu:</span><span id="score-player1">0 / 30</span></div>  
        <div class="stat-row"><span>👩‍🦰 La tua Amica:</span><span id="score-player2">0 / 30</span></div>  
      </div>  
      <button class="submit-btn" style="background:#64748b; margin-top:14px;" onclick="resetTournament()">🔄 Rigenera Nuove 30 Domande</button>  
    </div>  
  </main>  
  
  <!-- DIARIO DI BORDO -->  
  <main id="logbook" class="page">  
    <h2 class="page-title">📖 Diario di Bordo</h2>  
  
    <div class="card">  
      <h3>✍️ Nuova Pagina del Diario</h3>  
      <form id="diary-form">  
        <label for="d-title">Titolo Immersione / Ricordo</label>  
        <input type="text" id="d-title" placeholder="Es. Incontro magico alla Secca del Faro" required>  
  
        <label for="d-date">Data</label>  
        <input type="date" id="d-date" required>  
  
        <label for="d-location">Luogo / Punto d'immersione</label>  
        <input type="text" id="d-location" placeholder="Es. Isola Palmaria">  
  
        <label for="d-notes">Osservazioni e Note</label>  
        <textarea id="d-notes" rows="3" placeholder="Profondità, visibilità, condizioni del mare, avvistamenti speciali..." required></textarea>  
  
        <label for="d-media">Aggiungi Foto o Video</label>  
        <input type="file" id="d-media" accept="image/*,video/*" multiple onchange="previewDiaryFiles(event)">  
        <div class="log-media-grid" id="diary-preview-grid"></div>  
  
        <button type="submit" class="submit-btn">Salva nel Diario</button>  
      </form>  
    </div>  
  
    <h3 style="margin:20px 0 10px 0;">Le Tasselle del Tuo Diario</h3>  
    <div id="diary-entries-list"></div>  
  </main>  
  
  <!-- GUIA SPECIE CON STELLE -->  
  <main id="guide" class="page">  
    <h2 class="page-title">🐟 Specie Marine & Rating</h2>  
    <input type="text" id="search-input" style="margin-bottom:14px;" placeholder="🔍 Cerca specie..." onkeyup="filterSpecies()">  
    <div id="species-container"></div>  
  </main>  
  
  <!-- LE NOSTRE STATISTICHE -->  
  <main id="stats" class="page">  
    <h2 class="page-title">🏆 Le Nostre Statistiche</h2>  
  
    <div class="card">  
      <h3 style="color:var(--primary-dark); margin-bottom:12px;">📊 Tu vs La tua Amica</h3>  
      <div class="stat-row"><span>🤿 Immersioni:</span> <span>Tu: 18 | Lei: 17</span></div>  
      <div class="stat-row"><span>🐟 Specie Viste:</span> <span>Tu: 52 | Lei: 49</span></div>  
      <div class="stat-row"><span>📸 Foto Scattate:</span> <span>Tu: 87 | Lei: 103</span></div>  
      <div class="stat-row"><span>🐌 Nudibranchi:</span> <span>Tu: 12 | Lei: 8</span></div>  
    </div>  
  
    <div class="card">  
      <h3 style="margin-bottom:10px;">👑 Titoli Ufficiali</h3>  
      <div class="trophy-card">🏆 Regina dei Nudibranchi: Tu</div>  
      <div class="trophy-card">📸 Miglior Fotografa: La tua Amica</div>  
      <div class="trophy-card">🐙 Prima a trovare un polpo: Tu</div>  
      <div id="custom-trophies-list"></div>  
    </div>  
  
    <div class="card">  
      <h3>➕ Crea Nuova Categoria di Sfida</h3>  
      <form id="custom-challenge-form">  
        <label for="ch-title">Nome Categoria / Sfida</label>  
        <input type="text" id="ch-title" placeholder="Es. Murena più grande avvistata" required>  
        <label for="ch-winner">Chi ha vinto?</label>  
        <select id="ch-winner">  
          <option value="Tu">Tu</option>  
          <option value="La tua Amica">La tua Amica</option>  
          <option value="Pareggio">Pareggio</option>  
        </select>  
        <button type="submit" class="submit-btn">Aggiungi Sfida</button>  
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
  
  <!-- MAPPA -->  
  <main id="map" class="page">  
    <h2 class="page-title">🗺️ Mappa & Centri Diving</h2>  
    <div class="card">  
      <iframe style="width:100%; height:280px; border:none; border-radius:12px;" src="https://maps.google.com/maps?q=Golfo%20dei%20Poeti%20diving&t=&z=12&ie=UTF8&iwloc=&output=embed"></iframe>  
    </div>  
  </main>  
  
  <!-- QR CODE -->  
  <main id="qrcode" class="page">  
    <h2 class="page-title">🔲 QR Code Web App</h2>  
    <div class="card" style="text-align:center;">  
      <img src="https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=https://krdp6hydv5-oss.github.io/i-sub-del-golfo/" style="border-radius:12px; border:2px solid var(--primary);" alt="QR">  
    </div>  
  </main>  
  
  <!-- BOTTOM NAV -->  
  <nav class="bottom-nav">  
    <button class="nav-btn" id="btn-tournament" onclick="showPage('tournament')">  
      <span class="nav-icon">⚔️</span>  
      <span>Torneo</span>  
    </button>  
    <button class="nav-btn" id="btn-didyouknow" onclick="showPage('didyouknow')">  
      <span class="nav-icon">🎲</span>  
      <span>Lo Sapevi</span>  
    </button>  
    <button class="nav-btn active" id="btn-home" onclick="showPage('home')">  
      <span class="nav-icon">🏠</span>  
      <span>Home</span>  
    </button>  
    <button class="nav-btn" id="btn-logbook" onclick="showPage('logbook')">  
      <span class="nav-icon">📖</span>  
      <span>Diario</span>  
    </button>  
  </nav>  
  
  <script>  
    /* DATABASE CURIOSITA' GLOBAL */  
    const globalFacts = [  
      { animal: "Polpo", text: "I polpi hanno tre cuori e il loro sangue è di colore blu perché basato sul rame anziché sul ferro!" },  
      { animal: "Balenottera Azzurra", text: "La lingua di una balenottera azzurra pesa quanto un intero elefante adulto." },  
      { animal: "Gambero Mantide", text: "Può sferrare un pugno alla velocità di un proiettile calibro 22, capace di rompere i vetri degli acquari!" },  
      { animal: "Squalo Balena", text: "È il pesce più grande del mondo e la sua pelle può raggiungere fino a 10 cm di spessore." },  
      { animal: "Nudibranchio", text: "Alcuni nudibranchi mangiano meduse velenose e assimilano le loro cellule velenose per usarle come difesa personale!" },  
      { animal: "Lontra Marina", text: "Le lontre marine si tengono per mano mentre dormono per evitare di andare alla deriva con le correnti." },  
      { animal: "Pinguino", text: "Molte specie di pinguini regalano un sasso perfetto alla propria compagna come proposta per tutta la vita." },  
      { animal: "Squalo Groenlandia", text: "È il vertebrato più longevo della Terra: può vivere fino a oltre 400 anni!" }  
    ];  
  
    /* DATABASE DOMANDE TORNEO (30 DOMANDE DIVERSE) */  
    const masterQuizDb = [  
      { q: "Qual è il mammifero più grande del pianeta?", opts: ["Elefante Africano", "Balenottera Azzurra", "Capodoglio", "Squalo Balena"], c: 1, lvl: "facile" },  
      { q: "Quanti cuori possiede un polpo?", opts: ["1", "2", "3", "4"], c: 2, lvl: "facile" },  
      { q: "Quale animale terrestre è il più veloce in assoluto?", opts: ["Ghepardo", "Gazzella", "Leone", "Levriero"], c: 0, lvl: "facile" },  
      { q: "Che tipo di animale è questo nella foto?", img: "https://images.unsplash.com/photo-1544551763-46a013bb70d5?w=500", opts: ["Delfino", "Tartaruga Caretta", "Squalo", "Manta"], c: 1, lvl: "facile" },  
      { q: "Di che colore è il sangue dei polpi?", opts: ["Rosso", "Blu", "Verde", "Trasparente"], c: 1, lvl: "medio" },  
      { q: "Qual è l'unico uccello capace di volare all'indietro?", opts: ["Colibrì", "Rondine", "Aquila", "Martin Pescatore"], c: 0, lvl: "medio" },  
      { q: "Come si chiama questo animale marino?", img: "https://images.unsplash.com/photo-1545671913-b89ac1b4ac10?w=500", opts: ["Polpo", "Nudibranchio", "Stella Marina", "Medusa"], c: 1, lvl: "medio" },  
      { q: "Quale pesce è noto per nascondersi negli anemonie?", opts: ["Pesce Pagliaccio", "Murena", "Spigola", "Sarago"], c: 0, lvl: "facile" },  
      { q: "Che tipo di creatura è questa?", img: "https://images.unsplash.com/photo-1582967788606-a171c1080cb0?w=500", opts: ["Squalo Martello", "Corallo", "Cavalluccio Marino", "Riccio di Mare"], c: 2, lvl: "facile" },  
      { q: "Quale serpente è considerato il più velenoso al mondo?", opts: ["Cobra Reale", "Taipan dell'Interno", "Vipera", "Mamba Nero"], c: 1, lvl: "difficile" },  
      { q: "I cavallucci marini maschi sono gli unici a partorire i piccoli?", opts: ["Vero", "Falso"], c: 0, lvl: "facile" },  
      { q: "Qual è il rettile più grande vivente?", opts: ["Iguana", "Dragone di Komodo", "Coccodrillo Marino", "Anatonda"], c: 2, lvl: "difficile" },  
      { q: "Che animale è ritratto qui?", img: "https://images.unsplash.com/photo-1559827291-72ee739d0d9a?w=500", opts: ["Orsetto Lavatore", "Lontra Marina", "Foca", "Pinguino"], c: 1, lvl: "medio" },  
      { q: "Qual è l'animale più velenoso dell'oceano?", opts: ["Medusa Vespa di Mare", "Pesce Pietra", "Polpo dai dardi blu", "Serpente di mare"], c: 0, lvl: "esperto" },  
      { q: "Di che animale si tratta?", img: "https://images.unsplash.com/photo-1560275619-4662e36fa65c?w=500", opts: ["Squalo Bianco", "Squalo Balena", "Delfino", "Orca"], c: 1, lvl: "medio" },  
      { q: "Come orientano la caccia i pipistrelli?", opts: ["Con la vista", "Con l'Ecolocalizzazione", "Con l'olfatto", "Con il calore"], c: 1, lvl: "facile" },  
      { q: "Quante gambe ha un ragno?", opts: ["6", "8", "10", "12"], c: 1, lvl: "facile" },  
      { q: "Quale animale usa le pietre per rompere i guscio dei crostacei?", opts: ["Lontra Marina", "Gabbiano", "Polpo", "Tutti questi"], c: 3, lvl: "esperto" },  
      { q: "Riconosci questo grande predatore?", img: "https://images.unsplash.com/photo-1564349683136-77e08dba1ef9?w=500", opts: ["Panda", "Orso Polare", "Lupo", "Tigre"], c: 0, lvl: "facile" },  
      { q: "Come viene chiamata la copertura calcarea delle barriere coralline?", opts: ["Madrepora", "Atollo", "Scogliera", "Corallite"], c: 0, lvl: "esperto" },  
      { q: "Qual è l'uccello che non sa volare ma è un bravissimo nuotatore?", opts: ["Struzzo", "Pinguino", "Kiwi", "Gallina"], c: 1, lvl: "facile" },  
      { q: "Che animale mostra la foto?", img: "https://images.unsplash.com/photo-1534188753412-3e26d0d618d6?w=500", opts: ["Leone", "Tigre", "Ghepardo", "Giaguaro"], c: 0, lvl: "facile" },  
      { q: "Quale di questi NON è un crostaceo?", opts: ["Aragosta", "Granchio", "Gambero", "Seppia"], c: 3, lvl: "medio" },  
      { q: "Che animale è?", img: "https://images.unsplash.com/photo-1517849845537-4d257902454a?w=500", opts: ["Cane", "Lupo", "Volpe", "Iena"], c: 0, lvl: "facile" },  
      { q: "Quale pesce produce scariche elettriche per difendersi?", opts: ["Torpedine", "Murena", "Pesce Palla", "Cernia"], c: 0, lvl: "medio" },  
      { q: "Qual è il primate più grande del mondo?", opts: ["Scimpanzé", "Orango", "Gorilla", "Babbuino"], c: 2, lvl: "facile" },  
      { q: "I coralli sono piante o animali?", opts: ["Piante", "Animali", "Rocce", "Funghi"], c: 1, lvl: "medio" },  
      { q: "Che tipo di felino è questo?", img: "https://images.unsplash.com/photo-1561731216-c3a4d99437d5?w=500", opts: ["Tigre", "Leone", "Pantera", "Leopardo"], c: 0, lvl: "facile" },  
      { q: "Quanto può restare in apnea un capodoglio?", opts: ["10 minuti", "30 minuti", "Oltre 90 minuti", "5 ore"], c: 2, lvl: "esperto" },  
      { q: "Come si difende il pesce palla dai predatori?", opts: ["Si gonfia d'acqua", "Rilascia inchiostro", "Scossa elettrica", "Cambia colore"], c: 0, lvl: "facile" }  
    ];  
  
    const rawSpeciesList = [  
      "Aguglia", "Aragosta", "Barracuda", "Bavosa", "Castagnola", "Cavalluccio marino",  
      "Cernia bruna", "Corvina", "Donzella", "Flabellina affinis", "Gorgonia rossa",  
      "Grongo", "Murena", "Nudibranchio", "Occhiata", "Polpo", "Ricciola", "Sarago maggiore",  
      "Scorfano rosso", "Seppia", "Spigola", "Triglia di scoglio"  
    ];  
  
    let currentTournamentList = [];  
    let currentQIdx = 0;  
    let currentPlayer = "Tu";  
    let tournamentScores = { "Tu": 0, "La tua Amica": 0 };  
    let tempDiaryFiles = [];  
  
    document.addEventListener('DOMContentLoaded', () => {  
      loadGallery();  
      initTournament();  
      renderDiary();  
      renderSpecies();  
      renderCustomTrophies();  
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
  
    /* WIDGET FOTO HOME */  
    function loadGallery() {  
      const saved = JSON.parse(localStorage.getItem('home_gallery_photos') || '[]');  
      const container = document.getElementById('home-gallery');  
      const addBtnHTML = container.querySelector('.gallery-add-btn').outerHTML;  
  
      container.innerHTML = saved.map(imgData => `  
        <div class="gallery-item">  
          <img src="${imgData}" alt="Foto Home">  
        </div>  
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
  
    /* LO SAPEVI DADO */  
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
  
    /* TORNEO QUIZ */  
    function initTournament() {  
      let savedQ = localStorage.getItem('tournament_questions');  
      if (!savedQ) {  
        currentTournamentList = [...masterQuizDb].sort(() => 0.5 - Math.random()).slice(0, 30);  
        localStorage.setItem('tournament_questions', JSON.stringify(currentTournamentList));  
      } else {  
        currentTournamentList = JSON.parse(savedQ);  
      }  
  
      let savedScores = localStorage.getItem('tournament_scores');  
      if (savedScores) tournamentScores = JSON.parse(savedScores);  
  
      updateScoresUI();  
      currentQIdx = 0;  
      displayTournamentQ();  
    }  
  
    function selectPlayer(player) {  
      currentPlayer = player;  
      document.getElementById('btn-player1').classList.toggle('active', player === 'Tu');  
      document.getElementById('btn-player2').classList.toggle('active', player === 'La tua Amica');  
      currentQIdx = 0;  
      displayTournamentQ();  
    }  
  
    function displayTournamentQ() {  
      if (currentQIdx >= currentTournamentList.length) {  
        document.getElementById('quiz-box').innerHTML = `<h3>🎉 Torneo completato per ${currentPlayer}!</h3><p>Punteggio finale: ${tournamentScores[currentPlayer]} / 30</p>`;  
        return;  
      }  
  
      const qData = currentTournamentList[currentQIdx];  
      document.getElementById('quiz-progress').innerText = `Domanda ${currentQIdx + 1} / 30`;  
  
      const badge = document.getElementById('quiz-level-badge');  
      badge.innerText = qData.lvl.toUpperCase();  
      badge.className = `badge-level lvl-${qData.lvl}`;  
  
      const imgBox = document.getElementById('quiz-img-container');  
      if (qData.img) {  
        document.getElementById('quiz-img').src = qData.img;  
        imgBox.style.display = 'block';  
      } else {  
        imgBox.style.display = 'none';  
      }  
  
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
        feedback.innerText = "✅ Risposta Corretta!";  
      } else {  
        feedback.style.background = '#fee2e2'; feedback.style.color = '#991b1b';  
        feedback.innerText = `❌ Errata! Risposta corretta: ${qData.opts[qData.c]}`;  
      }  
  
      localStorage.setItem('tournament_scores', JSON.stringify(tournamentScores));  
      updateScoresUI();  
      feedback.style.display = 'block';  
      document.getElementById('quiz-next-q').style.display = 'block';  
    }  
  
    function nextTournamentQ() {  
      currentQIdx++;  
      displayTournamentQ();  
    }  
  
    function updateScoresUI() {  
      document.getElementById('score-player1').innerText = `${tournamentScores['Tu']} / 30`;  
      document.getElementById('score-player2').innerText = `${tournamentScores['La tua Amica']} / 30`;  
    }  
  
    function resetTournament() {  
      localStorage.removeItem('tournament_questions');  
      tournamentScores = { "Tu": 0, "La tua Amica": 0 };  
      localStorage.setItem('tournament_scores', JSON.stringify(tournamentScores));  
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
          if (file.type.startsWith('video')) {  
            grid.innerHTML += `<div class="log-media-item"><video src="${evt.target.result}"></video></div>`;  
          } else {  
            grid.innerHTML += `<div class="log-media-item"><img src="${evt.target.result}"></div>`;  
          }  
        };  
        reader.readAsDataURL(file);  
      });  
    }  
  
    document.getElementById('diary-form').addEventListener('submit', function(e) {  
      e.preventDefault();  
      const entry = {  
        title: document.getElementById('d-title').value,  
        date: document.getElementById('d-date').value,  
        location: document.getElementById('d-location').value,  
        notes: document.getElementById('d-notes').value,  
        media: tempDiaryFiles  
      };  
  
      let entries = JSON.parse(localStorage.getItem('diary_entries_v3') || '[]');  
      entries.unshift(entry);  
      localStorage.setItem('diary_entries_v3', JSON.stringify(entries));  
      this.reset();  
      document.getElementById('diary-preview-grid').innerHTML = '';  
      tempDiaryFiles = [];  
      renderDiary();  
    });  
  
    function renderDiary() {  
      const container = document.getElementById('diary-entries-list');  
      const entries = JSON.parse(localStorage.getItem('diary_entries_v3') || '[]');  
  
      if (entries.length === 0) {  
        container.innerHTML = `<p style="color:var(--text-muted); font-size:0.85rem;">Ancora nessuna immersione o ricordo registrato.</p>`;  
        return;  
      }  
  
      container.innerHTML = entries.map(item => `  
        <div class="log-entry">  
          <h3 style="color:var(--primary-dark);">${item.title}</h3>  
          <p style="font-size:0.8rem; color:var(--text-muted); margin: 4px 0 8px 0;">📅 ${item.date} ${item.location ? `| 📍 ${item.location}` : ''}</p>  
          <p style="font-size:0.9rem; line-height:1.4;">${item.notes}</p>  
          ${item.media && item.media.length > 0 ? `  
            <div class="log-media-grid">  
              ${item.media.map(m => m.type === 'video' ? `<div class="log-media-item"><video src="${m.url}" controls></video></div>` : `<div class="log-media-item"><img src="${m.url}"></div>`).join('')}  
            </div>  
          ` : ''}  
        </div>  
      `).join('');  
    }  
  
    /* SPECIE MARINE & RATING STELLE */  
    function renderSpecies() {  
      const container = document.getElementById('species-container');  
      let ratings = JSON.parse(localStorage.getItem('species_ratings') || '{}');  
      let seen = JSON.parse(localStorage.getItem('seen_species_v2') || '{}');  
  
      container.innerHTML = rawSpeciesList.map((name, idx) => {  
        const currentStars = ratings[name] || 0;  
        const isSeen = !!seen[name];  
        const wikiUrl = `https://it.wikipedia.org/wiki/Special:Search?search=${encodeURIComponent(name)}`;  
  
        return `  
          <div class="species-card" data-name="${name.toLowerCase()}">  
            <div class="species-header-row">  
              <img src="https://upload.wikimedia.org/wikipedia/commons/e/e0/Fish_icon.svg" class="species-thumb" alt="${name}">  
              <div style="flex:1;">  
                <h3 style="font-size:1.05rem; color:#0f172a;">${name}</h3>  
                <a href="${wikiUrl}" target="_blank" style="font-size:0.8rem; color:var(--primary); font-weight:600; text-decoration:none;">📖 Wikipedia ↗</a>  
                  
                <!-- Rating Stelle -->  
                <div class="star-rating" style="margin-top:6px;">  
                  ${[1, 2, 3, 4, 5].map(s => `  
                    <span class="star ${s <= currentStars ? 'active' : ''}" onclick="rateSpecies('${name}',${s})">★</span>  
                  `).join('')}  
                </div>  
              </div>  
            </div>  
  
            <button class="player-btn ${isSeen ? 'active' : ''}" onclick="toggleSeen('${name}')">  
              ${isSeen ? '✓ Visto nella lista' : '+ Aggiungi ai visti'}  
            </button>  
          </div>  
        `;  
      }).join('');  
    }  
  
    function rateSpecies(name, stars) {  
      let ratings = JSON.parse(localStorage.getItem('species_ratings') || '{}');  
      ratings[name] = stars;  
      localStorage.setItem('species_ratings', JSON.stringify(ratings));  
      renderSpecies();  
    }  
  
    function toggleSeen(name) {  
      let seen = JSON.parse(localStorage.getItem('seen_species_v2') || '{}');  
      seen[name] = !seen[name];  
      localStorage.setItem('seen_species_v2', JSON.stringify(seen));  
      renderSpecies();  
    }  
  
    function filterSpecies() {  
      const q = document.getElementById('search-input').value.toLowerCase();  
      document.querySelectorAll('.species-card').forEach(item => {  
        item.style.display = item.getAttribute('data-name').includes(q) ? 'flex' : 'none';  
      });  
    }  
  
    /* SFIDE PERSONALIZZATE STATISTICHE */  
    document.getElementById('custom-challenge-form').addEventListener('submit', function(e) {  
      e.preventDefault();  
      const title = document.getElementById('ch-title').value;  
      const winner = document.getElementById('ch-winner').value;  
  
      let customList = JSON.parse(localStorage.getItem('custom_trophies') || '[]');  
      customList.push({ title, winner });  
      localStorage.setItem('custom_trophies', JSON.stringify(customList));  
  
      this.reset();  
      renderCustomTrophies();  
    });  
  
    function renderCustomTrophies() {  
      const container = document.getElementById('custom-trophies-list');  
      const customList = JSON.parse(localStorage.getItem('custom_trophies') || '[]');  
      container.innerHTML = customList.map(item => `  
        <div class="trophy-card">🏅 ${item.title}: <strong>${item.winner}</strong></div>  
      `).join('');  
    }  
  </script>  
</body>  
</html>  

<!DOCTYPE html>  
<html lang="it">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">  
  <title>Y&C - I Sub del Golfo</title>  
  <style>  
    :root {  
      --primary: #0284c7;  
      --primary-dark: #0369a1;  
      --primary-light: #e0f2fe;  
      --danger: #ef4444;  
      --danger-dark: #dc2626;  
      --bg: #f8fafc;  
      --surface: #ffffff;  
      --text: #0f172a;  
      --text-muted: #64748b;  
      --border: #e2e8f0;  
      --radius: 16px;  
      --shadow: 0 10px 15px -3px rgba(0,0,0,0.05);  
    }  
  
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; -webkit-tap-highlight-color: transparent; }  
    body { background-color: var(--bg); color: var(--text); padding-bottom: 90px; }  
  
    /* Header & Side Menu */  
    .header {  
      background: linear-gradient(135deg, #0284c7 0%, #0369a1 100%);  
      color: white;  
      padding: 16px 20px;  
      position: sticky;  
      top: 0;  
      z-index: 100;  
      box-shadow: 0 4px 12px rgba(2, 132, 199, 0.25);  
      display: flex;  
      align-items: center;  
      justify-content: space-between;  
    }  
    .brand { display: flex; align-items: center; gap: 10px; font-weight: 800; font-size: 1.2rem; }  
    .menu-toggle { background: none; border: none; color: white; font-size: 1.6rem; cursor: pointer; padding: 4px; }  
  
    /* Drawer / Side Menu */  
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
    .drawer-header {  
      background: linear-gradient(135deg, #0284c7 0%, #0369a1 100%);  
      color: white; padding: 24px 20px; font-weight: 800; font-size: 1.2rem;  
    }  
    .drawer-menu { list-style: none; padding: 12px 0; overflow-y: auto; flex: 1; }  
    .drawer-item {  
      padding: 14px 20px; display: flex; align-items: center; gap: 12px;  
      color: var(--text); font-weight: 600; text-decoration: none; cursor: pointer; border-bottom: 1px solid #f1f5f9;  
    }  
    .drawer-item:hover, .drawer-item.active { background: var(--primary-light); color: var(--primary-dark); }  
  
    /* Pages */  
    .page { display: none; padding: 16px; max-width: 650px; margin: 0 auto; animation: fadeIn 0.2s ease-in-out; }  
    .page.active { display: block; }  
    @keyframes fadeIn { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: translateY(0); } }  
    .page-title { font-size: 1.4rem; font-weight: 800; color: #0f172a; margin-bottom: 14px; }  
  
    /* Cards */  
    .card { background: var(--surface); border-radius: var(--radius); padding: 18px; margin-bottom: 16px; box-shadow: var(--shadow); border: 1px solid var(--border); }  
      
    .hero-image-container {  
      position: relative; width: 100%; height: 220px; border-radius: var(--radius);  
      overflow: hidden; margin-bottom: 16px; background: linear-gradient(135deg, #0284c7 0%, #0369a1 100%);  
      display: flex; align-items: center; justify-content: center; cursor: pointer; box-shadow: var(--shadow);  
    }  
    .hero-image-container img { width: 100%; height: 100%; object-fit: cover; }  
    .hero-upload-btn {  
      position: absolute; bottom: 12px; right: 12px; background: rgba(0,0,0,0.65); color: white;  
      padding: 8px 14px; border-radius: 20px; font-size: 0.85rem; font-weight: 600; backdrop-filter: blur(4px);  
    }  
  
    /* Primary Action Cards */  
    .action-card-danger {  
      background: linear-gradient(135deg, #fef2f2 0%, #fee2e2 100%);  
      border: 1px solid #fca5a5; border-radius: var(--radius); padding: 18px; margin-bottom: 16px; cursor: pointer;  
    }  
    .action-card-danger h3 { color: var(--danger-dark); }  
  
    .sos-btn {  
      background: var(--danger); color: white; border: none; padding: 12px; border-radius: 12px;  
      font-weight: 800; font-size: 1rem; width: 100%; display: flex; align-items: center; justify-content: center;  
      gap: 8px; text-decoration: none; margin-bottom: 10px; box-shadow: 0 4px 10px rgba(239, 68, 68, 0.3);  
    }  
  
    /* Forms */  
    label { display: block; font-size: 0.85rem; font-weight: 700; color: #334155; margin-top: 10px; margin-bottom: 4px; }  
    input, textarea, select {  
      width: 100%; padding: 12px; border: 1px solid var(--border); border-radius: 10px; font-size: 0.95rem; background: #f8fafc; outline: none;  
    }  
    button.submit-btn {  
      background: linear-gradient(135deg, #0284c7 0%, #0369a1 100%); color: white; border: none; padding: 12px;  
      border-radius: 10px; width: 100%; font-size: 1rem; font-weight: 700; cursor: pointer; margin-top: 14px;  
    }  
  
    /* Species Grid */  
    .search-box { width: 100%; padding: 12px; border-radius: 12px; border: 1px solid var(--border); margin-bottom: 14px; font-size: 0.95rem; }  
    .species-grid { display: flex; flex-direction: column; gap: 10px; }  
    .species-item { display: flex; align-items: center; justify-content: space-between; background: var(--surface); padding: 12px 16px; border-radius: 12px; border: 1px solid var(--border); }  
    .seen-btn { background: #f1f5f9; border: 1px solid #cbd5e1; padding: 6px 14px; border-radius: 20px; font-weight: 700; font-size: 0.8rem; color: #475569; cursor: pointer; }  
    .seen-btn.seen { background: #dcfce7; border-color: #86efac; color: #15803d; }  
  
    /* Media & Map */  
    .media-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(130px, 1fr)); gap: 10px; margin-top: 14px; }  
    .media-item { width: 100%; height: 130px; object-fit: cover; border-radius: 10px; border: 1px solid var(--border); }  
      
    .map-frame { width: 100%; height: 260px; border: none; border-radius: 12px; margin-bottom: 14px; }  
  
    /* Bottom Nav */  
    .bottom-nav {  
      position: fixed; bottom: 0; left: 0; right: 0; background: rgba(255, 255, 255, 0.95);  
      backdrop-filter: blur(10px); display: flex; justify-content: space-around; padding: 8px 0 12px 0;  
      border-top: 1px solid var(--border); z-index: 1000;  
    }  
    .nav-btn { background: none; border: none; display: flex; flex-direction: column; align-items: center; color: #94a3b8; font-size: 0.7rem; font-weight: 600; flex: 1; cursor: pointer; }  
    .nav-btn.active { color: var(--primary); font-weight: 800; }  
    .nav-icon { font-size: 1.3rem; margin-bottom: 2px; }  
  </style>  
</head>  
<body>  
  
  <!-- Drawer Menu Lateral Overlay -->  
  <div class="drawer-overlay" id="drawer-overlay" onclick="toggleDrawer()"></div>  
  <aside class="drawer" id="drawer">  
    <div class="drawer-header">  
      📌 Menu Navigazione  
    </div>  
    <ul class="drawer-menu">  
      <li class="drawer-item" onclick="showPage('home'); toggleDrawer();">🏠 Home</li>  
      <li class="drawer-item" onclick="showPage('safety'); toggleDrawer();">🚨 Sicurezza & Scheda SOS</li>  
      <li class="drawer-item" onclick="showPage('guide'); toggleDrawer();">🐟 Guida Specie Marine</li>  
      <li class="drawer-item" onclick="showPage('map'); toggleDrawer();">🗺️ Mappa & Centri Diving</li>  
      <li class="drawer-item" onclick="window.open('https://www.3bmeteo.com', '_blank'); toggleDrawer();">🌤️ Meteo & Mare (3BMeteo) ↗</li>  
      <li class="drawer-item" onclick="showPage('media'); toggleDrawer();">📷 Galleria Foto / Video</li>  
      <li class="drawer-item" onclick="showPage('logbook'); toggleDrawer();">📖 Diario di Bordo</li>  
    </ul>  
  </aside>  
  
  <!-- Top Bar -->  
  <header class="header">  
    <button class="menu-toggle" onclick="toggleDrawer()">☰</button>  
    <div class="brand">  
      <span>🤿 Y&C - I Sub del Golfo</span>  
    </div>  
    <div style="width: 24px;"></div>  
  </header>  
  
  <!-- PAGINA HOME -->  
  <main id="home" class="page active">  
    <!-- Copertina Personalizzabile -->  
    <div class="hero-image-container" onclick="document.getElementById('hero-file-input').click()">  
      <img id="hero-banner-img" src="" alt="Copertina" style="display: none;">  
      <div id="hero-placeholder" style="color:white; text-align:center;">  
        <span style="font-size: 2rem;">📸</span><br>Premi per scegliere la copertina  
      </div>  
      <div class="hero-upload-btn">📷 Cambia Foto</div>  
    </div>  
    <input type="file" id="hero-file-input" accept="image/*" style="display: none" onchange="handleHeroImageUpload(event)">  
  
    <!-- Pulsante Primario Sicurezza al Posto delle Specie -->  
    <div class="action-card-danger" onclick="showPage('safety')">  
      <h3 style="font-size:1.1rem; margin-bottom:4px;">🚨 Sicurezza & Schedes Dati SOS</h3>  
      <p style="color:#991b1b; font-size:0.88rem;">  
        Pulsanti d'emergenza rapida (Guardia Costiera 1530 / DAN) e schede sanitarie/soccorso di te e dei tuoi compagni.  
      </p>  
    </div>  
  
    <div class="card">  
      <h3>Benvenuti a Bordo</h3>  
      <p style="color:var(--text-muted); font-size:0.9rem; margin-top:4px;">  
        Usa il menu in alto a sinistra (☰) per accedere al meteo, alla mappa dei diving spot e alla guida completa delle specie marine!  
      </p>  
    </div>  
  </main>  
  
  <!-- PAGINA SICUREZZA & CARTA IDENTITÀ / SOS -->  
  <main id="safety" class="page">  
    <h2 class="page-title">🚨 Sicurezza & Contatti SOS</h2>  
  
    <!-- Chiamate d'emergenza rapide -->  
    <div class="card" style="border-color:#fca5a5; background:#fff5f5;">  
      <h3 style="color:#991b1b; margin-bottom:12px;">Numeri di Emergenza</h3>  
      <a href="tel:1530" class="sos-btn">📞 Chiamata Guardia Costiera (1530)</a>  
      <a href="tel:+390642118685" class="sos-btn" style="background:#0284c7;">🚑 Emergenza DAN Sub (+39 06 42118685)</a>  
    </div>  
  
    <!-- Scheda d'Identità Sanitaria / Subacquea (Multi-Profilo) -->  
    <div class="card">  
      <h3>➕ Aggiungi / Modifica Scheda Dati</h3>  
      <form id="profile-form">  
        <label for="prof-name">Nome e Cognome *</label>  
        <input type="text" id="prof-name" placeholder="Es. Mario Rossi" required>  
  
        <label for="prof-city">Città / Residenza</label>  
        <input type="text" id="prof-city" placeholder="Es. La Spezia">  
  
        <label for="prof-blood">Gruppo Sanguigno & Allergie</label>  
        <input type="text" id="prof-blood" placeholder="Es. 0+ / Allergico a Penicillina">  
  
        <label for="prof-cert">Brevetto Subacqueo & Livello</label>  
        <input type="text" id="prof-cert" placeholder="Es. Open Water Diver PADI">  
  
        <label for="prof-emergency">Contatto Primario di Soccorso (Nome & Tel)</label>  
        <input type="text" id="prof-emergency" placeholder="Es. Moglie - 333 1234567">  
  
        <label for="prof-notes">Altre Informazioni Mediche Utili</label>  
        <textarea id="prof-notes" rows="3" placeholder="Ipertensione, chirurgia passata, note per i soccorritori..."></textarea>  
  
        <button type="submit" class="submit-btn" style="background:var(--primary);">Salva Scheda Dati</button>  
      </form>  
    </div>  
  
    <h3 style="margin: 20px 0 10px 0;">Schede Profilo Salvate</h3>  
    <div id="profiles-list"></div>  
  </main>  
  
  <!-- PAGINA MAPPA & CENTRI DIVING -->  
  <main id="map" class="page">  
    <h2 class="page-title">🗺️ Mappa & Centri Diving</h2>  
  
    <div class="card">  
      <h3>Mappa Interattiva</h3>  
      <iframe class="map-frame" src="https://maps.google.com/maps?q=Golfo%20dei%20Poeti%20diving&t=&z=12&ie=UTF8&iwloc=&output=embed"></iframe>  
      <p style="font-size:0.85rem; color:var(--text-muted);">Mappa con la localizzazione dei principali diving spot e punti di appoggio nel golfo.</p>  
    </div>  
  
    <div class="card">  
      <h3>Centri Diving Autorizzati</h3>  
      <ul style="list-style:none; display:flex; flex-direction:column; gap:12px; margin-top:10px;">  
        <li style="border-bottom:1px solid var(--border); padding-bottom:8px;">  
          <strong>🤿 Diving Center Golfo dei Poeti</strong><br>  
          <a href="https://www.google.com/search?q=Diving+Center+Golfo+dei+Poeti" target="_blank" style="color:var(--primary); font-size:0.85rem;">Visita Sito Web / Contatti ↗</a>  
        </li>  
        <li style="border-bottom:1px solid var(--border); padding-bottom:8px;">  
          <strong>🌊 Tribordo Sub & Diving</strong><br>  
          <a href="https://www.google.com/search?q=Tribordo+Sub+Diving" target="_blank" style="color:var(--primary); font-size:0.85rem;">Visita Sito Web / Contatti ↗</a>  
        </li>  
      </ul>  
    </div>  
  </main>  
  
  <!-- PAG  

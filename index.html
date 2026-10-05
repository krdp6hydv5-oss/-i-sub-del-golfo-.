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
    .brand { display: flex; align-items: center; gap: 10px; font-weight: 800; font-size: 1.1rem; }  
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
  
  <!-- Menu Laterale Overlay -->  
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
  
  <!-- Top Bar con Nome Y&C -->  
  <header class="header">  
    <button class="menu-toggle" onclick="toggleDrawer()">☰</button>  
    <div class="brand">  
      <span>🤿 Y&C - I Sub del Golfo</span>  
    </div>  
    <div style="width: 24px;"></div>  
  </header>  
  
  <!-- HOME PAGE -->  
  <main id="home" class="page active">  
    <div class="hero-image-container" onclick="document.getElementById('hero-file-input').click()">  
      <img id="hero-banner-img" src="" alt="Copertina" style="display: none;">  
      <div id="hero-placeholder" style="color:white; text-align:center;">  
        <span style="font-size: 2rem;">📸</span><br>Premi per scegliere la copertina  
      </div>  
      <div class="hero-upload-btn">📷 Cambia Foto</div>  
    </div>  
    <input type="file" id="hero-file-input" accept="image/*" style="display: none" onchange="handleHeroImageUpload(event)">  
  
    <div class="action-card-danger" onclick="showPage('safety')">  
      <h3 style="font-size:1.1rem; margin-bottom:4px;">🚨 Sicurezza & Schede Dati SOS</h3>  
      <p style="color:#991b1b; font-size:0.88rem;">  
        Pulsanti d'emergenza rapida (Guardia Costiera 1530 / DAN) e schede sanitarie/soccorso personali e dei compagni.  
      </p>  
    </div>  
  
    <div class="card">  
      <h3>Benvenuti a Bordo</h3>  
      <p style="color:var(--text-muted); font-size:0.9rem; margin-top:4px;">  
        Usa il menu in alto a sinistra (☰) per accedere al meteo, alla mappa dei diving spot e alla guida delle specie marine!  
      </p>  
    </div>  
  </main>  
  
  <!-- SICUREZZA & SOS -->  
  <main id="safety" class="page">  
    <h2 class="page-title">🚨 Sicurezza & Contatti SOS</h2>  
  
    <div class="card" style="border-color:#fca5a5; background:#fff5f5;">  
      <h3 style="color:#991b1b; margin-bottom:12px;">Numeri di Emergenza</h3>  
      <a href="tel:1530" class="sos-btn">📞 Chiamata Guardia Costiera (1530)</a>  
      <a href="tel:+390642118685" class="sos-btn" style="background:#0284c7;">🚑 Emergenza DAN Sub (+39 06 42118685)</a>  
    </div>  
  
    <div class="card">  
      <h3>➕ Aggiungi Scheda Dati / Carta d'Identità</h3>  
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
        <textarea id="prof-notes" rows="3" placeholder="Ipertensione, note per i soccorritori..."></textarea>  
  
        <button type="submit" class="submit-btn">Salva Scheda Dati</button>  
      </form>  
    </div>  
  
    <h3 style="margin: 20px 0 10px 0;">Schede Profilo Salvate</h3>  
    <div id="profiles-list"></div>  
  </main>  
  
  <!-- MAPPA & DIVING -->  
  <main id="map" class="page">  
    <h2 class="page-title">🗺️ Mappa & Centri Diving</h2>  
  
    <div class="card">  
      <h3>Mappa Interattiva</h3>  
      <iframe class="map-frame" src="https://maps.google.com/maps?q=Golfo%20dei%20Poeti%20diving&t=&z=12&ie=UTF8&iwloc=&output=embed"></iframe>  
      <p style="font-size:0.85rem; color:var(--text-muted);">Mappa dei principali diving spot nel golfo.</p>  
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
  
  <!-- SPECIE MARINE -->  
  <main id="guide" class="page">  
    <h2 class="page-title">🐟 Specie Marine & Wikipedia</h2>  
    <input type="text" id="search-input" class="search-box" placeholder="Cerca specie..." onkeyup="filterSpecies()">  
    <div id="species-container" class="species-grid"></div>  
  </main>  
  
  <!-- MEDIA -->  
  <main id="media" class="page">  
    <h2 class="page-title">📷 Galleria Foto & Video</h2>  
    <div class="card">  
      <h3>Carica Contenuto</h3>  
      <input type="file" id="media-input" accept="image/*,video/*" style="margin-top:8px;">  
      <button class="submit-btn" onclick="uploadMedia()">Aggiungi alla Galleria</button>  
    </div>  
    <div id="media-gallery" class="media-grid"></div>  
  </main>  
  
  <!-- DIARIO DI BORDO -->  
  <main id="logbook" class="page">  
    <h2 class="page-title">📖 Diario di Bordo</h2>  
    <div class="card">  
      <h3>Nuova Nota d'Immersione</h3>  
      <form id="dive-form">  
        <label for="dive-title">Punto Immersione</label>  
        <input type="text" id="dive-title" placeholder="Es. Secca del Faro" required>  
  
        <label for="dive-date">Data</label>  
        <input type="date" id="dive-date" required>  
  
        <label for="dive-notes">Note & Dettagli</label>  
        <textarea id="dive-notes" rows="3" placeholder="Profondità, visibilità, attrezzatura..." required></textarea>  
  
        <button type="submit" class="submit-btn">Salva Nota</button>  
      </form>  
    </div>  
    <h3 style="margin: 20px 0 10px 0;">Note Salvate</h3>  
    <div id="log-list"></div>  
  </main>  
  
  <!-- Navigation Bar Inferiore -->  
  <nav class="bottom-nav">  
    <button class="nav-btn active" id="btn-home" onclick="showPage('home')">  
      <span class="nav-icon">🏠</span>  
      <span>Home</span>  
    </button>  
    <button class="nav-btn" id="btn-safety" onclick="showPage('safety')">  
      <span class="nav-icon">🚨</span>  
      <span>Sicurezza</span>  
    </button>  
    <button class="nav-btn" id="btn-media" onclick="showPage('media')">  
      <span class="nav-icon">📷</span>  
      <span>Foto/Video</span>  
    </button>  
    <button class="nav-btn" id="btn-logbook" onclick="showPage('logbook')">  
      <span class="nav-icon">📖</span>  
      <span>Diario</span>  
    </button>  
  </nav>  
  
  <script>  
    const rawSpeciesList = [  
      "Aguglia", "Aragosta", "Bavosa", "Bavosa bianca", "Bavosa cornuta", "Bavosa gialla",  
      "Barracuda", "Boga", "Berta minore", "Cappone gallinella", "Caretta caretta", "Castagnola",  
      "Castagnola rossa", "Cavalluccio marino", "Cefalo", "Cernia bruna", "Cernia rossa", "Cepola",  
      "Civetta di mare", "Coccinella di mare", "Cormorano", "Corvina", "Delfino", "Donzella",  
      "Donzella pavonina", "Edredone", "Flabellina affinis", "Gabbiano reale", "Gallinella", "Ghiozzo",  
      "Ghiozzo di Bucchich", "Ghiozzo rigato", "Gorgonia rossa", "Granchio eremita", "Granchio reale blu",  
      "Grongo", "Hypselodoris valenciennesi", "Lampuga", "Leccia", "Lepre di mare", "Latterino",  
      "Mako", "Margherita di mare", "Medusa luminosa", "Mormora", "Mostella", "Murena", "Nasello",  
      "Occhiata", "Pagello bastardo", "Pagello fragolino", "Pagro", "Palamita", "Pesce balestra",  
      "Pesce civetta", "Pesce peperoncino", "Pesce serra", "Perchia", "Polpo", "Pomodoro di mare",  
      "Polmone di mare", "Rana pescatrice", "Razza", "Re di triglie", "Ricciola", "Rombo",  
      "Rombo di rena", "Salpa", "Sarago fasciato", "Sarago maggiore", "Sarago pizzuto", "Scorfano nero",  
      "Scorfano rosso", "Scorfanotto", "Seppia", "Sogliola", "Spigola", "Tanuta", "Torpedine",  
      "Tordo fischietto", "Tordo grigio", "Tordo mediterraneo", "Tordo musolungo", "Tordo nero",  
      "Tordo ocellato", "Tordo pavone", "Tordo verde", "Triglia di fango", "Triglia di scoglio",  
      "Vacchetta di mare", "Verdesca", "Verme dal ciuffo bianco", "Zerro"  
    ];  
  
    document.addEventListener('DOMContentLoaded', () => {  
      loadHeroImage();  
      renderSpecies();  
      renderMedia();  
      renderLogs();  
      renderProfiles();  
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
  
    function loadHeroImage() {  
      const savedImg = localStorage.getItem('sub_golfo_hero_image');  
      const imgElem = document.getElementById('hero-banner-img');  
      const placeholderElem = document.getElementById('hero-placeholder');  
  
      if (savedImg && imgElem) {  
        imgElem.src = savedImg;   
        imgElem.style.display = 'block';  
        if (placeholderElem) placeholderElem.style.display = 'none';  
      }  
    }  
  
    function handleHeroImageUpload(event) {  
      const file = event.target.files[0];  
      if (!file) return;  
      const reader = new FileReader();  
      reader.onload = function(e) {  
        const img = new Image();  
        img.onload = function() {  
          const canvas = document.createElement('canvas');  
          const maxW = 1000;  
          let w = img.width, h = img.height;  
          if (w > maxW) { h = Math.round((h * maxW) / w); w = maxW; }  
          canvas.width = w; canvas.height = h;  
          canvas.getContext('2d').drawImage(img, 0, 0, w, h);  
          localStorage.setItem('sub_golfo_hero_image', canvas.toDataURL('image/jpeg', 0.8));  
          loadHeroImage();  
        };  
        img.src = e.target.result;  
      };  
      reader.readAsDataURL(file);  
    }  
  
    document.getElementById('profile-form').addEventListener('submit', function(e) {  
      e.preventDefault();  
      const newProfile = {  
        name: document.getElementById('prof-name').value,  
        city: document.getElementById('prof-city').value,  
        blood: document.getElementById('prof-blood').value,  
        cert: document.getElementById('prof-cert').value,  
        emergency: document.getElementById('prof-emergency').value,  
        notes: document.getElementById('prof-notes').value  
      };  
  
      let profiles = JSON.parse(localStorage.getItem('app_sos_profiles') || '[]');  
      profiles.unshift(newProfile);  
      localStorage.setItem('app_sos_profiles', JSON.stringify(profiles));  
      this.reset();  
      renderProfiles();  
    });  
  
    function renderProfiles() {  
      const listEl = document.getElementById('profiles-list');  
      if (!listEl) return;  
      const profiles = JSON.parse(localStorage.getItem('app_sos_profiles') || '[]');  
  
      if (profiles.length === 0) {  
        listEl.innerHTML = '<p style="color:var(--text-muted); font-size:0.9rem;">Nessuna scheda inserita.</p>';  
        return;  
      }  
  
      listEl.innerHTML = profiles.map((p, idx) => `  
        <div class="card" style="border-left: 4px solid var(--danger);">  
          <div style="display:flex; justify-content:space-between; align-items:center;">  
            <h3>👤 ${p.name}</h3>  
            <button onclick="deleteProfile(${idx})" style="background:none; border:none; color:var(--danger); cursor:pointer;">🗑️ Elimina</button>  
          </div>  
          <p style="font-size:0.85rem; margin-top:6px;">📍 <strong>Città:</strong> ${p.city || '-'}</p>  
          <p style="font-size:0.85rem;">🩸 <strong>Gruppo/Allergie:</strong> ${p.blood || '-'}</p>  
          <p style="font-size:0.85rem;">🤿 <strong>Brevetto:</strong> ${p.cert || '-'}</p>  
          <p style="font-size:0.85rem;">📞 <strong>Soccorso:</strong> ${p.emergency || '-'}</p>  
          ${p.notes ? `<p style="font-size:0.85rem; margin-top:4px; color:#64748b;">📝 ${p.notes}</p>` : ''}  
        </div>  
      `).join('');  
    }  
  
    function deleteProfile(index) {  
      let profiles = JSON.parse(localStorage.getItem('app_sos_profiles') || '[]');  
      profiles.splice(index, 1);  
      localStorage.setItem('app_sos_profiles', JSON.stringify(profiles));  
      renderProfiles();  
    }  
  
    function renderSpecies() {  
      const container = document.getElementById('species-container');  
      if (!container) return;  
      let seenData = JSON.parse(localStorage.getItem('seen_species_v2') || '{}');  
  
      container.innerHTML = rawSpeciesList.map(name => {  
        const isSeen = !!seenData[name];  
        const wikiUrl = `https://it.wikipedia.org/wiki/Special:Search?search=${encodeURIComponent(name)}`;  
        return `  
          <div class="species-item" data-name="${name.toLowerCase()}">  
            <div>  
              <span style="font-weight:700;">${name}</span><br>  
              <a href="${wikiUrl}" target="_blank" style="font-size:0.8rem; color:var(--primary); text-decoration:none;">📖 Wikipedia ↗</a>  
            </div>  
            <button class="seen-btn ${isSeen ? 'seen' : ''}" onclick="toggleSeen('${name}')">  
              ${isSeen ? '✓ Visto' : '+ Visto'}  
            </button>  
          </div>  
        `;  
      }).join('');  
    }  
  
    function toggleSeen(name) {  
      let seenData = JSON.parse(localStorage.getItem('seen_species_v2') || '{}');  
      seenData[name] = !seenData[name];  
      localStorage.setItem('seen_species_v2', JSON.stringify(seenData));  
      renderSpecies();  
    }  
  
    function filterSpecies() {  
      const q = document.getElementById('search-input').value.toLowerCase();  
      document.querySelectorAll('.species-item').forEach(item => {  
        item.style.display = item.getAttribute('data-name').includes(q) ? 'flex' : 'none';  
      });  
    }  
  
    function uploadMedia() {  
      const input = document.getElementById('media-input');  
      if (!input.files || !input.files[0]) return;  
      const file = input.files[0];  
      const reader = new FileReader();  
      reader.onload = function(e) {  
        const mediaList = JSON.parse(localStorage.getItem('app_media') || '[]');  
        mediaList.unshift({ type: file.type.startsWith('video') ? 'video' : 'image', src: e.target.result });  
        try { localStorage.setItem('app_media', JSON.stringify(mediaList)); renderMedia(); input.value = ''; }  
        catch(err) { alert('Memoria piena.'); }  
      };  
      reader.readAsDataURL(file);  
    }  
  
    function renderMedia() {  
      const gallery = document.getElementById('media-gallery');  
      if (!gallery) return;  
      const mediaList = JSON.parse(localStorage.getItem('app_media') || '[]');  
      gallery.innerHTML = mediaList.map(m => m.type === 'video' ? `<video class="media-item" src="${m.src}" controls></video>` : `<img class="media-item" src="${m.src}">`).join('');  
    }  
  
    document.getElementById('dive-form').addEventListener('submit', function(e) {  
      e.preventDefault();  
      let logs = JSON.parse(localStorage.getItem('app_logs') || '[]');  
      logs.unshift({ title: document.getElementById('dive-title').value, date: document.getElementById('dive-date').value, notes: document.getElementById('dive-notes').value });  
      localStorage.setItem('app_logs', JSON.stringify(logs));  
      this.reset();  
      renderLogs();  
    });  
  
    function renderLogs() {  
      const logEl = document.getElementById('log-list');  
      if (!logEl) return;  
      let logs = JSON.parse(localStorage.getItem('app_logs') || '[]');  
      logEl.innerHTML = logs.map(l => `<div class="card"><h3>${l.title}</h3><p style="font-size:0.8rem; color:var(--primary);">📅 ${l.date}</p><p>${l.notes}</p></div>`).join('');  
    }  
  </script>  
</body>  
</html>  

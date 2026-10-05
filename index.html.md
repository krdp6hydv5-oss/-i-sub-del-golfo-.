<!DOCTYPE html>  
<html lang="it">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>I sub del golfo</title>  
  <style>  
    /* Reset base */  
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }  
    body { background-color: #f8fafc; color: #1e293b; padding-bottom: 70px; }  
      
    /* Header Navbar */  
    .navbar { background-color: #0284c7; color: white; padding: 14px 16px; position: sticky; top: 0; z-index: 100; box-shadow: 0 2px 4px rgba(0,0,0,0.1); display: flex; align-items: center; justify-content: space-between; }  
    .logo-container { display: flex; align-items: center; gap: 8px; font-weight: bold; font-size: 1.1rem; }  
      
    /* Pagine / Sezioni */  
    .page { display: none; padding: 16px; max-width: 800px; margin: 0 auto; }  
    .page.active { display: block; }  
  
    /* Cards e Stili */  
    .card { background: white; border-radius: 12px; padding: 16px; margin-bottom: 16px; box-shadow: 0 1px 3px rgba(0,0,0,0.1); border: 1px solid #e2e8f0; }  
    .card h3 { color: #0369a1; margin-bottom: 8px; }  
    .tag { display: inline-block; background: #e0f2fe; color: #0369a1; padding: 4px 8px; border-radius: 6px; font-size: 0.8rem; font-weight: 600; margin-bottom: 8px; }  
      
    /* Lista Specie Checklist */  
    .species-item { display: flex; align-items: center; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid #f1f5f9; }  
    .species-item:last-child { border-bottom: none; }  
    .species-info { flex: 1; }  
    .species-name { font-weight: 600; font-size: 1rem; }  
    .species-scientific { font-style: italic; color: #64748b; font-size: 0.85rem; }  
    .seen-btn { background: #e2e8f0; border: none; padding: 8px 12px; border-radius: 20px; font-weight: 600; cursor: pointer; color: #475569; }  
    .seen-btn.seen { background: #10b981; color: white; }  
  
    /* Form Log Immersioni */  
    input, textarea, select { width: 100%; padding: 10px; margin-top: 6px; margin-bottom: 12px; border: 1px solid #cbd5e1; border-radius: 8px; font-size: 0.95rem; }  
    button.submit-btn { background: #0284c7; color: white; border: none; padding: 12px; border-radius: 8px; width: 100%; font-size: 1rem; font-weight: bold; cursor: pointer; }  
  
    /* Barra di Navigazione Inferiore Mobile */  
    .bottom-nav { position: fixed; bottom: 0; left: 0; right: 0; background: white; display: flex; justify-content: space-around; padding: 8px 0; border-top: 1px solid #e2e8f0; z-index: 1000; }  
    .nav-btn { background: none; border: none; display: flex; flex-direction: column; align-items: center; color: #64748b; font-size: 0.75rem; flex: 1; cursor: pointer; }  
    .nav-btn.active { color: #0284c7; font-weight: bold; }  
    .nav-icon { font-size: 1.3rem; margin-bottom: 2px; }  
  </style>  
</head>  
<body>  
  
  <!-- Header -->  
  <div class="navbar">  
    <div class="logo-container">  
      <span>🤿</span> I sub del golfo  
    </div>  
  </div>  
  
  <!-- Pagina Home -->  
  <div id="home" class="page active">  
    <div class="card">  
      <h3>Benvenuto nella Guida Digitale</h3>  
      <p>Esplora le specie del golfo, compila la tua checklist di avvistamento e registra le tue immersioni.</p>  
    </div>  
    <div class="card">  
      <span class="tag">Novità</span>  
      <h4>Aggiornamenti recenti</h4>  
      <p style="font-size:0.9rem; color:#64748b; margin-top:4px;">Aggiunte le nuove schede specie per la fauna marina locale e la funzione logbook salvata in locale sul dispositivo.</p>  
    </div>  
  </div>  
  
  <!-- Pagina Guida Specie -->  
  <div id="guide" class="page">  
    <h2>Guida Specie</h2>  
    <p style="color:#64748b; margin-bottom:16px;">Lista delle specie osservabili nel golfo:</p>  
    <div id="species-list"></div>  
  </div>  
  
  <!-- Pagina Logbook Immersioni -->  
  <div id="logbook" class="page">  
    <h2>Logbook Immersioni</h2>  
    <div class="card">  
      <h3>Nuova Immersione</h3>  
      <form id="dive-form">  
        <label>Punto di Immersione</label>  
        <input type="text" id="dive-site" placeholder="Es. Secca del Faro" required>  
          
        <label>Data</label>  
        <input type="date" id="dive-date" required>  
          
        <label>Profondità Max (metri)</label>  
        <input type="number" id="dive-depth" placeholder="Es. 18" required>  
  
        <label>Note e Avvistamenti</label>  
        <textarea id="dive-notes" rows="3" placeholder="Note sulla visibilità, corrente o specie avvistate..."></textarea>  
          
        <button type="submit" class="submit-btn">Salva Immersione</button>  
      </form>  
    </div>  
      
    <h3>Storico Immersioni</h3>  
    <div id="log-list" style="margin-top:12px;"></div>  
  </div>  
  
  <!-- Navigazione Inferiore -->  
  <div class="bottom-nav">  
    <button class="nav-btn active" onclick="showPage('home', this)">  
      <span class="nav-icon">🏠</span> Home  
    </button>  
    <button class="nav-btn" onclick="showPage('guide', this)">  
      <span class="nav-icon">🐟</span> Specie  
    </button>  
    <button class="nav-btn" onclick="showPage('logbook', this)">  
      <span class="nav-icon">📖</span> Logbook  
    </button>  
  </div>  
  
  <script>  
    // Dati Specie  
    const speciesData = [  
      { id: 'cernia', name: 'Cernia Bruno', scientific: 'Epinephelus marginatus', desc: 'Frequenta i fondali rocciosi e le secche.' },  
      { id: 'polpo', name: 'Polpo Comune', scientific: 'Octopus vulgaris', desc: 'Mimetico tra anfratti e fessure rocciose.' },  
      { id: 'sarago', name: 'Sarago Maggiore', scientific: 'Diplodus sargus', desc: 'Presente in banchi vicino alla costa.' },  
      { id: 'murena', name: 'Murena', scientific: 'Muraena helena', desc: 'Tana nelle spaccature rocciose.' }  
    ];  
  
    // Cambio Pagina  
    function showPage(pageId, btn) {  
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));  
      document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));  
        
      document.getElementById(pageId).classList.add('active');  
      btn.classList.add('active');  
      window.scrollTo(0, 0);  
    }  
  
    // Gestione Checklist Specie  
    function renderSpecies() {  
      const listEl = document.getElementById('species-list');  
      const seenData = JSON.parse(localStorage.getItem('seen_species') || '{}');  
  
      listEl.innerHTML = speciesData.map(s => {  
        const isSeen = seenData[s.id] || false;  
        return `  
          <div class="card">  
            <div class="species-item">  
              <div class="species-info">  
                <div class="species-name">${s.name}</div>  
                <div class="species-scientific">${s.scientific}</div>  
              </div>  
              <button class="seen-btn ${isSeen ? 'seen' : ''}" onclick="toggleSeen('${s.id}')">  
                ${isSeen ? '✓ Visto' : '+ Visto'}  
              </button>  
            </div>  
            <p style="font-size:0.85rem; color:#475569; margin-top:8px;">${s.desc}</p>  
          </div>  
        `;  
      }).join('');  
    }  
  
    function toggleSeen(id) {  
      const seenData = JSON.parse(localStorage.getItem('seen_species') || '{}');  
      seenData[id] = !seenData[id];  
      localStorage.setItem('seen_species', JSON.stringify(seenData));  
      renderSpecies();  
    }  
  
    // Gestione Logbook  
    document.getElementById('dive-form').addEventListener('submit', function(e) {  
      e.preventDefault();  
      const site = document.getElementById('dive-site').value;  
      const date = document.getElementById('dive-date').value;  
      const depth = document.getElementById('dive-depth').value;  
      const notes = document.getElementById('dive-notes').value;  
  
      const dives = JSON.parse(localStorage.getItem('dive_logs') || '[]');  
      dives.unshift({ site, date, depth, notes });  
      localStorage.setItem('dive_logs', JSON.stringify(dives));  
  
      this.reset();  
      renderLogs();  
    });  
  
    function renderLogs() {  
      const logEl = document.getElementById('log-list');  
      const dives = JSON.parse(localStorage.getItem('dive_logs') || '[]');  
  
      if (dives.length === 0) {  
        logEl.innerHTML = '<p style="color:#64748b; font-size:0.9rem;">Nessuna immersione registrata.</p>';  
        return;  
      }  
  
      logEl.innerHTML = dives.map(d => `  
        <div class="card">  
          <h4>${d.site}</h4>  
          <p style="font-size:0.85rem; color:#0284c7; margin:4px 0;">Data: ${d.date} | Profondità: ${d.depth}m</p>  
          <p style="font-size:0.85rem; color:#475569;">${d.notes || 'Nessuna nota.'}</p>  
        </div>  
      `).join('');  
    }  
  
    // Inizializzazione  
    renderSpecies();  
    renderLogs();  
  </script>  
</body>  
</html>  

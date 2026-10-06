<!DOCTYPE html>  
<html lang="it">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Gestione Avvistamenti e Galleria</title>  
  <style>  
    :root {  
      --primary: #0284c7;  
      --primary-hover: #0369a1;  
      --danger: #ef4444;  
      --danger-hover: #dc2626;  
      --success: #22c55e;  
      --bg-card: #ffffff;  
      --border: #e2e8f0;  
    }  
  
    body {  
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;  
      background-color: #f8fafc;  
      color: #0f172a;  
      margin: 0;  
      padding: 24px;  
    }  
  
    .container {  
      max-width: 1000px;  
      margin: 0 auto;  
    }  
  
    h1, h2, h3 {  
      color: #1e293b;  
    }  
  
    .section-card {  
      background: var(--bg-card);  
      border: 1px solid var(--border);  
      border-radius: 12px;  
      padding: 24px;  
      margin-bottom: 24px;  
      box-shadow: 0 1px 3px rgba(0,0,0,0.05);  
    }  
  
    /* Macro Categorie */  
    .categories-flex {  
      display: flex;  
      flex-wrap: wrap;  
      gap: 10px;  
    }  
  
    .category-badge {  
      background: #f1f5f9;  
      color: #334155;  
      padding: 8px 16px;  
      border-radius: 20px;  
      font-size: 14px;  
      font-weight: 500;  
      border: 1px solid var(--border);  
    }  
  
    /* Select Specie */  
    .select-specie {  
      width: 100%;  
      max-width: 400px;  
      padding: 10px 14px;  
      border-radius: 8px;  
      border: 1px solid var(--border);  
      font-size: 15px;  
      outline: none;  
    }  
  
    /* Upload Box */  
    .upload-zone {  
      border: 2px dashed #cbd5e1;  
      border-radius: 12px;  
      padding: 32px;  
      text-align: center;  
      background: #fafafa;  
      cursor: pointer;  
      transition: background 0.2s;  
    }  
  
    .upload-zone:hover {  
      background: #f1f5f9;  
    }  
  
    .btn {  
      display: inline-block;  
      padding: 10px 20px;  
      border-radius: 8px;  
      font-weight: 600;  
      cursor: pointer;  
      border: none;  
      font-size: 14px;  
      transition: background 0.2s;  
    }  
  
    .btn-primary {  
      background: var(--primary);  
      color: white;  
    }  
  
    .btn-primary:hover {  
      background: var(--primary-hover);  
    }  
  
    /* Grid Foto */  
    .gallery-grid {  
      display: grid;  
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));  
      gap: 20px;  
      margin-top: 20px;  
    }  
  
    .photo-card {  
      background: white;  
      border: 1px solid var(--border);  
      border-radius: 10px;  
      overflow: hidden;  
      box-shadow: 0 2px 4px rgba(0,0,0,0.05);  
    }  
  
    .photo-card img {  
      width: 100%;  
      height: 180px;  
      object-fit: cover;  
      display: block;  
    }  
  
    .photo-actions {  
      padding: 12px;  
      display: flex;  
      justify-content: space-between;  
      align-items: center;  
      background: #fff;  
    }  
  
    .btn-edit {  
      color: var(--primary);  
      cursor: pointer;  
      font-weight: 600;  
      font-size: 14px;  
    }  
  
    .btn-delete {  
      color: var(--danger);  
      background: none;  
      border: none;  
      cursor: pointer;  
      font-weight: 600;  
      font-size: 14px;  
    }  
  
    .empty-msg {  
      color: #64748b;  
      font-style: italic;  
    }  
  </style>  
</head>  
<body>  
  
  <div class="container">  
    <h1>Gestione Avvistamenti e Galleria Home</h1>  
  
    <!-- 1. MACRO CATEGORIE (SENZA EMOJI) -->  
    <div class="section-card">  
      <h2>Macro Categorie</h2>  
      <div class="categories-flex" id="categories-container"></div>  
    </div>  
  
    <!-- 2. SPECIE ANIMALI (LISTA COMPLETA 93 SPECIE) -->  
    <div class="section-card">  
      <h2>Specie Animali (Database Completo)</h2>  
      <select id="species-select" class="select-specie">  
        <option value="">-- Seleziona una specie --</option>  
      </select>  
    </div>  
  
    <!-- 3. CARICAMENTO E ADATTAMENTO FOTO -->  
    <div class="section-card">  
      <h2>Foto in Evidenza e Galleria</h2>  
      <p style="color: #64748b; font-size: 14px;">La foto precedente è stata rimossa. Ogni foto caricata verrà automaticamente adattata e ridimensionata nel formato corretto del sito.</p>  
        
      <div class="upload-zone" onclick="document.getElementById('file-input').click()">  
        <p style="margin: 0 0 12px 0; font-weight: 500;">Clicca per selezionare e caricare una foto</p>  
        <button class="btn btn-primary" type="button">Scegli Immagine</button>  
        <input type="file" id="file-input" accept="image/*" style="display: none;" onchange="handleFileUpload(event)">  
      </div>  
  
      <!-- GRID GALLERIA -->  
      <div class="gallery-grid" id="gallery-grid">  
        <!-- Galleria inizialmente vuota -->  
      </div>  
    </div>  
  </div>  
  
  <script>  
    // ==========================================  
    // DATA: MACRO CATEGORIE (SENZA EMOJI)  
    // ==========================================  
    const macroCategories = [  
      "Pesci",  
      "Molluschi",  
      "Crostacei",  
      "Mammiferi marini",  
      "Rettili marini",  
      "Uccelli marini",  
      "Altri Invertebrati"  
    ];  
  
    // ==========================================  
    // DATA: SPECIE ANIMALI (93 SPECIE)  
    // ==========================================  
    const animalSpecies = [  
      "Aguglia", "Aragosta", "Bavosa", "Bavosa bianca", "Bavosa cornuta", "Bavosa gialla",   
      "Barracuda", "Boga", "Berta minore", "Cappone gallinella", "Caretta caretta", "Castagnola",   
      "Castagnola rossa", "Cavalluccio marino", "Cefalo", "Cernia bruna", "Cernia rossa", "Cepola",   
      "Civetta di mare", "Coccinella di mare", "Cormorano", "Corvina", "Delfino", "Donzella",   
      "Donzella pavonina", "Edredone", "Flabellina affinis", "Gabbiano reale", "Gallinella",   
      "Ghiozzo", "Ghiozzo di Bucchich", "Ghiozzo rigato", "Gorgonia rossa", "Granchio eremita",   
      "Granchio reale blu", "Grongo", "Hypselodoris valenciennesi", "Lampuga", "Leccia",   
      "Lepre di mare", "Latterino", "Mako", "Margherita di mare", "Medusa luminosa", "Mormora",   
      "Mostella", "Murena", "Nasello", "Occhiata", "Pagello bastardo", "Pagello fragolino",   
      "Pagro", "Palamita", "Pesce balestra", "Pesce civetta", "Pesce peperoncino", "Pesce serra",   
      "Perchia", "Polpo", "Pomodoro di mare", "Polmone di mare", "Rana pescatrice", "Razza",   
      "Re di triglie", "Ricciola", "Rombo", "Rombo di rena", "Salpa", "Sarago fasciato",   
      "Sarago maggiore", "Sarago pizzuto", "Scorfano nero", "Scorfano rosso", "Scorfanotto",   
      "Seppia", "Sogliola", "Spigola", "Tanuta", "Torpedine", "Tordo fischietto", "Tordo grigio",   
      "Tordo mediterraneo", "Tordo musolungo", "Tordo nero", "Tordo ocellato", "Tordo pavone",   
      "Tordo verde", "Triglia di fango", "Triglia di scoglio", "Vacchetta di mare", "Verdesca",   
      "Verme dal ciuffo bianco", "Zerro"  
    ];  
  
    let galleryPhotos = [];  
  
    // ==========================================  
    // INIZIALIZZAZIONE INTERFACCIA  
    // ==========================================  
    window.onload = () => {  
      // Carica Macro Categorie  
      const catContainer = document.getElementById("categories-container");  
      macroCategories.forEach(cat => {  
        const badge = document.createElement("span");  
        badge.className = "category-badge";  
        badge.textContent = cat;  
        catContainer.appendChild(badge);  
      });  
  
      // Carica Specie Animali  
      const speciesSelect = document.getElementById("species-select");  
      animalSpecies.forEach(specie => {  
        const option = document.createElement("option");  
        option.value = specie;  
        option.textContent = specie;  
        speciesSelect.appendChild(option);  
      });  
  
      renderGallery();  
    };  
  
    // ==========================================  
    // CROP & RESIZE AUTOMATICO VIA CANVAS (16:9)  
    // ==========================================  
    function processAndResizeImage(file, targetWidth = 1200, targetHeight = 675) {  
      return new Promise((resolve, reject) => {  
        const reader = new FileReader();  
        reader.readAsDataURL(file);  
        reader.onload = (event) => {  
          const img = new Image();  
          img.src = event.target.result;  
          img.onload = () => {  
            const canvas = document.createElement("canvas");  
            canvas.width = targetWidth;  
            canvas.height = targetHeight;  
            const ctx = canvas.getContext("2d");  
  
            // Calcolo proporzioni cover/crop centrato  
            const sourceRatio = img.width / img.height;  
            const targetRatio = targetWidth / targetHeight;  
            let sw, sh, sx, sy;  
  
            if (sourceRatio > targetRatio) {  
              sh = img.height;  
              sw = img.height * targetRatio;  
              sx = (img.width - sw) / 2;  
              sy = 0;  
            } else {  
              sw = img.width;  
              sh = img.width / targetRatio;  
              sx = 0;  
              sy = (img.height - sh) / 2;  
            }  
  
            ctx.drawImage(img, sx, sy, sw, sh, 0, 0, targetWidth, targetHeight);  
              
            // Restituisce URL in formato ottimizzato  
            resolve(canvas.toDataURL("image/jpeg", 0.85));  
          };  
          img.onerror = err => reject(err);  
        };  
        reader.onerror = err => reject(err);  
      });  
    }  
  
    // ==========================================  
    // GESTIONE GALLERIA (UPLOAD, EDIT, DELETE)  
    // ==========================================  
    async function handleFileUpload(event) {  
      const file = event.target.files[0];  
      if (!file) return;  
  
      try {  
        const processedUrl = await processAndResizeImage(file);  
        const newPhoto = {  
          id: Date.now(),  
          url: processedUrl  
        };  
        galleryPhotos.push(newPhoto);  
        renderGallery();  
      } catch (err) {  
        alert("Errore nell'elaborazione dell'immagine.");  
      }  
      event.target.value = "";  
    }  
  
    async function handleEditPhoto(id, event) {  
      const file = event.target.files[0];  
      if (!file) return;  
  
      try {  
        const processedUrl = await processAndResizeImage(file);  
        galleryPhotos = galleryPhotos.map(p => p.id === id ? { ...p, url: processedUrl } : p);  
        renderGallery();  
      } catch (err) {  
        alert("Errore durante la modifica della foto.");  
      }  
    }  
  
    function handleDeletePhoto(id) {  
      galleryPhotos = galleryPhotos.filter(p => p.id !== id);  
      renderGallery();  
    }  
  
    function renderGallery() {  
      const grid = document.getElementById("gallery-grid");  
      grid.innerHTML = "";  
  
      if (galleryPhotos.length === 0) {  
        grid.innerHTML = '<p class="empty-msg">Nessuna foto presente in evidenza.</p>';  
        return;  
      }  
  
      galleryPhotos.forEach(photo => {  
        const card = document.createElement("div");  
        card.className = "photo-card";  
        card.innerHTML = `  
          <img src="${photo.url}" alt="Foto avvistamento">  
          <div class="photo-actions">  
            <label class="btn-edit">  
              Modifica  
              <input type="file" accept="image/*" style="display:none" onchange="handleEditPhoto(${photo.id}, event)">  
            </label>  
            <button class="btn-delete" onclick="handleDeletePhoto(${photo.id})">Elimina</button>  
          </div>  
        `;  
        grid.appendChild(card);  
      });  
    }  
  </script>  
</body>  
</html>  

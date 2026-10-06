<!DOCTYPE html>  
<html lang="it">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Avvistamenti Marini</title>  
  <style>  
    :root {  
      --primary: #0284c7;  
      --danger: #ef4444;  
      --bg-card: #ffffff;  
      --border: #e2e8f0;  
    }  
  
    body {  
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;  
      background-color: #f8fafc;  
      color: #0f172a;  
      margin: 0;  
      padding: 16px;  
    }  
  
    .container {  
      max-width: 800px;  
      margin: 0 auto;  
    }  
  
    .section-card {  
      background: var(--bg-card);  
      border: 1px solid var(--border);  
      border-radius: 12px;  
      padding: 20px;  
      margin-bottom: 20px;  
      box-shadow: 0 1px 3px rgba(0,0,0,0.05);  
    }  
  
    h1 { font-size: 22px; margin-bottom: 16px; color: #0f172a; }  
    h2 { font-size: 18px; margin-top: 0; margin-bottom: 12px; color: #334155; }  
  
    /* Macro Categorie senza emoji */  
    .categories-flex {  
      display: flex;  
      flex-wrap: wrap;  
      gap: 8px;  
    }  
  
    .category-badge {  
      background: #f1f5f9;  
      color: #334155;  
      padding: 6px 14px;  
      border-radius: 16px;  
      font-size: 14px;  
      font-weight: 500;  
      border: 1px solid var(--border);  
    }  
  
    /* Select Specie */  
    select {  
      width: 100%;  
      padding: 10px;  
      border-radius: 8px;  
      border: 1px solid var(--border);  
      font-size: 15px;  
      background: white;  
    }  
  
    /* Upload Box */  
    .upload-zone {  
      border: 2px dashed #cbd5e1;  
      border-radius: 10px;  
      padding: 20px;  
      text-align: center;  
      background: #fafafa;  
      cursor: pointer;  
    }  
  
    .btn {  
      display: inline-block;  
      padding: 10px 18px;  
      border-radius: 6px;  
      font-weight: 600;  
      cursor: pointer;  
      border: none;  
      background: var(--primary);  
      color: white;  
      font-size: 14px;  
    }  
  
    /* Grid Foto */  
    .gallery-grid {  
      display: grid;  
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));  
      gap: 16px;  
      margin-top: 16px;  
    }  
  
    .photo-card {  
      background: white;  
      border: 1px solid var(--border);  
      border-radius: 8px;  
      overflow: hidden;  
    }  
  
    .photo-card img {  
      width: 100%;  
      height: 160px;  
      object-fit: cover;  
      display: block;  
    }  
  
    .photo-actions {  
      padding: 10px;  
      display: flex;  
      justify-content: space-between;  
      align-items: center;  
    }  
  
    .btn-edit { color: var(--primary); font-weight: 600; font-size: 13px; cursor: pointer; }  
    .btn-delete { color: var(--danger); background: none; border: none; font-weight: 600; font-size: 13px; cursor: pointer; }  
  </style>  
</head>  
<body>  
  
  <div class="container">  
    <h1>Gestione Avvistamenti</h1>  
  
    <!-- 1. MACRO CATEGORIE (SENZA EMOJI) -->  
    <div class="section-card">  
      <h2>Macro Categorie</h2>  
      <div class="categories-flex" id="categories-container"></div>  
    </div>  
  
    <!-- 2. SPECIE ANIMALI (LISTA COMPLETA 93 SPECIE) -->  
    <div class="section-card">  
      <h2>Specie Animali</h2>  
      <select id="species-select">  
        <option value="">-- Seleziona una specie --</option>  
      </select>  
    </div>  
  
    <!-- 3. GALLERIA E CARICAMENTO FOTO -->  
    <div class="section-card">  
      <h2>Galleria e Foto in Evidenza</h2>  
      <div class="upload-zone" onclick="document.getElementById('file-input').click()">  
        <p style="margin: 0 0 10px 0; font-size: 14px;">Seleziona una foto dal dispositivo</p>  
        <button class="btn" type="button">Carica Foto</button>  
        <input type="file" id="file-input" accept="image/*" style="display: none;" onchange="handleFileUpload(event)">  
      </div>  
  
      <div class="gallery-grid" id="gallery-grid">  
        <p style="color: #64748b; font-style: italic; font-size: 14px;">Nessuna foto presente in evidenza.</p>  
      </div>  
    </div>  
  </div>  
  
  <script>  
    // MACRO CATEGORIE SENZA EMOJI  
    var macroCategories = [  
      "Pesci", "Molluschi", "Crostacei", "Mammiferi marini",   
      "Rettili marini", "Uccelli marini", "Altri Invertebrati"  
    ];  
  
    // LISTA COMPLETA 93 SPECIE ANIMALI  
    var animalSpecies = [  
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
  
    var galleryPhotos = [];  
  
    document.addEventListener("DOMContentLoaded", function() {  
      // Carica Categorie  
      var catContainer = document.getElementById("categories-container");  
      macroCategories.forEach(function(cat) {  
        var badge = document.createElement("span");  
        badge.className = "category-badge";  
        badge.textContent = cat;  
        catContainer.appendChild(badge);  
      });  
  
      // Carica Specie  
      var speciesSelect = document.getElementById("species-select");  
      animalSpecies.forEach(function(specie) {  
        var option = document.createElement("option");  
        option.value = specie;  
        option.textContent = specie;  
        speciesSelect.appendChild(option);  
      });  
    });  
  
    // ADATTAMENTO / CROP AUTOMATICO FOTO VIA CANVAS (16:9)  
    function resizeImage(file, callback) {  
      var reader = new FileReader();  
      reader.readAsDataURL(file);  
      reader.onload = function(e) {  
        var img = new Image();  
        img.src = e.target.result;  
        img.onload = function() {  
          var canvas = document.createElement("canvas");  
          var w = 1200;  
          var h = 675;  
          canvas.width = w;  
          canvas.height = h;  
          var ctx = canvas.getContext("2d");  
  
          var sourceRatio = img.width / img.height;  
          var targetRatio = w / h;  
          var sw = img.width, sh = img.height, sx = 0, sy = 0;  
  
          if (sourceRatio > targetRatio) {  
            sw = img.height * targetRatio;  
            sx = (img.width - sw) / 2;  
          } else {  
            sh = img.width / targetRatio;  
            sy = (img.height - sh) / 2;  
          }  
  
          ctx.drawImage(img, sx, sy, sw, sh, 0, 0, w, h);  
          callback(canvas.toDataURL("image/jpeg", 0.85));  
        };  
      };  
    }  
  
    function handleFileUpload(event) {  
      var file = event.target.files[0];  
      if (!file) return;  
  
      resizeImage(file, function(processedUrl) {  
        galleryPhotos.push({ id: Date.now(), url: processedUrl });  
        renderGallery();  
      });  
      event.target.value = "";  
    }  
  
    function handleEditPhoto(id, event) {  
      var file = event.target.files[0];  
      if (!file) return;  
  
      resizeImage(file, function(processedUrl) {  
        for (var i = 0; i < galleryPhotos.length; i++) {  
          if (galleryPhotos[i].id === id) {  
            galleryPhotos[i].url = processedUrl;  
            break;  
          }  
        }  
        renderGallery();  
      });  
    }  
  
    function handleDeletePhoto(id) {  
      galleryPhotos = galleryPhotos.filter(function(p) { return p.id !== id; });  
      renderGallery();  
    }  
  
    function renderGallery() {  
      var grid = document.getElementById("gallery-grid");  
      grid.innerHTML = "";  
  
      if (galleryPhotos.length === 0) {  
        grid.innerHTML = '<p style="color: #64748b; font-style: italic; font-size: 14px;">Nessuna foto presente in evidenza.</p>';  
        return;  
      }  
  
      galleryPhotos.forEach(function(photo) {  
        var card = document.createElement("div");  
        card.className = "photo-card";  
        card.innerHTML =   
          '<img src="' + photo.url + '" alt="Foto">' +  
          '<div class="photo-actions">' +  
            '<label class="btn-edit">Modifica<input type="file" accept="image/*" style="display:none" onchange="handleEditPhoto(' + photo.id + ', event)"></label>' +  
            '<button class="btn-delete" onclick="handleDeletePhoto(' + photo.id + ')">Elimina</button>' +  
          '</div>';  
        grid.appendChild(card);  
      });  
    }  
  </script>  
</body>  
</html>  

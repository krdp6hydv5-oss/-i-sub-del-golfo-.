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
      --bg-card: #ffffff;  
      --border: #e2e8f0;  
    }  
  
    body {  
      font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;  
      background-color: #f8fafc;  
      color: #0f172a;  
      margin: 0;  
      padding: 24px;  
    }  
  
    .container {  
      max-width: 1000px;  
      margin: 0 auto;  
    }  
  
    .section-card {  
      background: var(--bg-card);  
      border: 1px solid var(--border);  
      border-radius: 12px;  
      padding: 24px;  
      margin-bottom: 24px;  
      box-shadow: 0 1px 3px rgba(0,0,0,0.05);  
    }  
  
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
  
    .select-specie {  
      width: 100%;  
      max-width: 400px;  
      padding: 10px 14px;  
      border-radius: 8px;  
      border: 1px solid var(--border);  
      font-size: 15px;  
    }  
  
    .upload-zone {  
      border: 2px dashed #cbd5e1;  
      border-radius: 12px;  
      padding: 32px;  
      text-align: center;  
      background: #fafafa;  
      cursor: pointer;  
    }  
  
    .btn {  
      display: inline-block;  
      padding: 10px 20px;  
      border-radius: 8px;  
      font-weight: 600;  
      cursor: pointer;  
      border: none;  
      font-size: 14px;  
      background: var(--primary);  
      color: white;  
    }  
  
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
  </style>  
</head>  
<body>  
  
  <div class="container">  
    <h1>Gestione Avvistamenti e Galleria</h1>  
  
    <!-- 1. MACRO CATEGORIE (SENZA EMOJI) -->  
    <div class="section-card">  
      <h2>Macro Categorie</h2>  
      <div class="categories-flex" id="categories-container"></div>  
    </div>  
  
    <!-- 2. SPECIE ANIMALI (LISTA COMPLETA 93 SPECIE) -->  
    <div class="section-card">  
      <h2>Specie Animali</h2>  
      <select id="species-select" class="select-specie">  
        <option value="">-- Seleziona una specie --</option>  
      </select>  
    </div>  
  
    <!-- 3. GALLERIA E CARICAMENTO FOTO -->  
    <div class="section-card">  
      <h2>Foto in Evidenza e Galleria</h2>  
      <p style="color: #64748b; font-size: 14px;">Carica le nuove foto: verranno ridimensionate automaticamente nel formato adatto al sito.</p>  
        
      <div class="upload-zone" onclick="document.getElementById('file-input').click()">  
        <p style="margin: 0 0 12px 0; font-weight: 500;">Clicca per selezionare una foto</p>  
        <button class="btn" type="button">Scegli Immagine</button>  
        <input type="file" id="file-input" accept="image/*" style="display: none;" onchange="handleFileUpload(event)">  
      </div>  
  
      <div class="gallery-grid" id="gallery-grid">  
        <p style="color: #64748b; font-style: italic;">Nessuna foto presente in evidenza.</p>  
      </div>  
    </div>  
  </div>  
  
  <script>  
    // MACRO CATEGORIE (SENZA EMOJI)  
    var macroCategories = [  
      "Pesci",  
      "Molluschi",  
      "Crostacei",  
      "Mammiferi marini",  
      "Rettili marini",  
      "Uccelli marini",  
      "Altri Invertebrati"  
    ];  
  
    // SPECIE ANIMALI (93 SPECIE COMPLETE)  
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

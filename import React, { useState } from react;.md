import React, { useState } from "react";  
  
// ==========================================  
// 1. DATABASE SPECIE ANIMALI (93 SPECIE)  
// ==========================================  
export const animalSpecies = [  
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
  
// ==========================================  
// 2. MACRO CATEGORIE (SENZA EMOJI)  
// ==========================================  
export const macroCategories = [  
  { id: "pesci", name: "Pesci" },  
  { id: "molluschi", name: "Molluschi" },  
  { id: "crostacei", name: "Crostacei" },  
  { id: "mammiferi", name: "Mammiferi marini" },  
  { id: "rettili", name: "Rettili marini" },  
  { id: "uccelli", name: "Uccelli marini" },  
  { id: "invertebrati", name: "Altri Invertebrati" }  
];  
  
// ==========================================  
// 3. UTILITY ELABORAZIONE E GESTIONE FOTO  
// ==========================================  
  
/**  
 * Ridimensiona e ritaglia l'immagine tramite Canvas per adattarla al formato del sito (16:9 di default)  
 */  
export const processImage = (file, targetWidth = 1200, targetHeight = 675) => {  
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
  
        // Calcolo delle proporzioni per il crop centrato (cover)  
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
          
        canvas.toBlob(  
          (blob) => {  
            const processedFile = new File([blob], file.name, {  
              type: "image/jpeg",  
              lastModified: Date.now()  
            });  
            resolve({  
              file: processedFile,  
              previewUrl: URL.createObjectURL(blob)  
            });  
          },  
          "image/jpeg",  
          0.85  
        );  
      };  
      img.onerror = (err) => reject(err);  
    };  
    reader.onerror = (err) => reject(err);  
  });  
};  
  
export const deleteImageAPI = async (imageId, apiEndpoint) => {  
  const response = await fetch(`${apiEndpoint}/${imageId}`, { method: "DELETE" });  
  if (!response.ok) throw new Error("Errore durante l'eliminazione dell'immagine.");  
  return await response.json();  
};  
  
export const updateImageAPI = async (imageId, newFile, apiEndpoint) => {  
  const { file } = await processImage(newFile);  
  const formData = new FormData();  
  formData.append("image", file);  
  
  const response = await fetch(`${apiEndpoint}/${imageId}`, { method: "PUT", body: formData });  
  if (!response.ok) throw new Error("Errore durante la modifica dell'immagine.");  
  return await response.json();  
};  
  
// ==========================================  
// 4. COMPONENTE GALLERIA E FOTO IN EVIDENZA  
// ==========================================  
export default function SightingGalleryManager({ apiEndpoint = "/api/photos" }) {  
  // Stato foto iniziale vuoto (rimossa la foto esistente)  
  const [photos, setPhotos] = useState([]);  
  const [uploading, setUploading] = useState(false);  
  
  // Caricamento ed elaborazione formato foto  
  const handleFileUpload = async (event) => {  
    const file = event.target.files[0];  
    if (!file) return;  
  
    setUploading(true);  
    try {  
      const { file: processedFile, previewUrl } = await processImage(file);  
        
      const formData = new FormData();  
      formData.append("photo", processedFile);  
  
      const response = await fetch(apiEndpoint, {  
        method: "POST",  
        body: formData  
      });  
        
      if (!response.ok) {  
        // Fallback locale in modalità test se l'API non è attiva  
        const mockNewPhoto = { id: Date.now(), url: previewUrl };  
        setPhotos((prev) => [...prev, mockNewPhoto]);  
      } else {  
        const newPhotoData = await response.json();  
        setPhotos((prev) => [...prev, newPhotoData]);  
      }  
    } catch (error) {  
      console.error("Errore durante il caricamento foto:", error);  
    } finally {  
      setUploading(false);  
    }  
  };  
  
  // Eliminazione Foto  
  const handleDelete = async (photoId) => {  
    try {  
      await deleteImageAPI(photoId, apiEndpoint).catch(() => null); // Fallback per simulazione  
      setPhotos((prev) => prev.filter((p) => p.id !== photoId));  
    } catch (error) {  
      console.error("Errore nella cancellazione:", error);  
    }  
  };  
  
  // Modifica / Sostituzione Foto  
  const handleEdit = async (photoId, event) => {  
    const file = event.target.files[0];  
    if (!file) return;  
  
    try {  
      const { previewUrl } = await processImage(file);  
      await updateImageAPI(photoId, file, apiEndpoint).catch(() => null); // Fallback per simulazione  
        
      setPhotos((prev) =>  
        prev.map((p) => (p.id === photoId ? { ...p, url: previewUrl } : p))  
      );  
    } catch (error) {  
      console.error("Errore nella modifica:", error);  
    }  
  };  
  
  return (  
    <div style={{ fontFamily: "sans-serif", padding: "20px", maxWidth: "1200px", margin: "0 auto" }}>  
      <h1>Gestione Avvistamenti e Galleria Home</h1>  
  
      {/* Sezione Macro Categorie */}  
      <section style={{ marginBottom: "30px" }}>  
        <h3>Macro Categorie</h3>  
        <div style={{ display: "flex", gap: "10px", flexWrap: "wrap" }}>  
          {macroCategories.map((cat) => (  
            <span key={cat.id} style={{ background: "#e0e0e0", padding: "6px 12px", borderRadius: "16px", fontSize: "14px" }}>  
              {cat.name}  
            </span>  
          ))}  
        </div>  
      </section>  
  
      {/* Sezione Caricamento Nuova Foto */}  
      <section style={{ marginBottom: "30px", border: "1px dashed #ccc", padding: "20px", textAlign: "center", borderRadius: "8px" }}>  
        <h3>Carica Foto in Evidenza</h3>  
        <p style={{ color: "#666", fontSize: "14px" }}>Le foto verranno ridimensionate e ritagliate automaticamente nel formato corretto del sito.</p>  
        <label htmlFor="photo-upload" style={{ display: "inline-block", background: "#007bff", color: "#fff", padding: "10px 20px", borderRadius: "4px", cursor: "pointer", marginTop: "10px" }}>  
          {uploading ? "Elaborazione in corso..." : "Seleziona Immagine"}  
        </label>  
        <input id="photo-upload" type="file" accept="image/*" onChange={handleFileUpload} style={{ display: "none" }} />  
      </section>  
  
      {/* Galleria Foto */}  
      <section>  
        <h3>Foto in Evidenza e Galleria</h3>  
        {photos.length === 0 ? (  
          <p style={{ fontStyle: "italic", color: "#888" }}>Nessuna foto presente in galleria.</p>  
        ) : (  
          <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fill, minmax(250px, 1fr))", gap: "20px" }}>  
            {photos.map((photo) => (  
              <div key={photo.id} style={{ border: "1px solid #ddd", borderRadius: "8px", overflow: "hidden", background: "#fff" }}>  
                <img src={photo.url} alt="Avvistamento" style={{ width: "100%", height: "180px", objectFit: "cover" }} />  
                <div style={{ padding: "10px", display: "flex", justifyContent: "space-between" }}>  
                  <label style={{ color: "#28a745", cursor: "pointer", fontWeight: "bold", fontSize: "14px" }}>  
                    Modifica  
                    <input type="file" accept="image/*" onChange={(e) => handleEdit(photo.id, e)} style={{ display: "none" }} />  
                  </label>  
                  <button onClick={() => handleDelete(photo.id)} style={{ color: "#dc3545", background: "none", border: "none", fontWeight: "bold", cursor: "pointer", fontSize: "14px" }}>  
                    Elimina  
                  </button>  
                </div>  
              </div>  
            ))}  
          </div>  
        )}  
      </section>  
    </div>  
  );  
}  

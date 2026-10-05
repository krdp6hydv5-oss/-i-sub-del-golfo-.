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
    body { background-color: var(--bg); color: var(--text); padding-bottom: 90px; overflow-x: hidden; }  
  
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
    .page { display: none; padding: 16px; max-width: 650px; margin: 0 auto; animation: fadeIn 0.2s ease-in-out; position: relative; z-index: 2; }  
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
  
    /* Animazioni Sfondo Home: Bolle e Creature */  
    #ocean-animation-container {  
      position: fixed;  
      top: 0; left: 0; width: 100vw; height: 100vh;  
      pointer-events: none;  
      z-index: 1;  
      overflow: hidden;  
      display: none;  
    }  
  
    .bubble {  
      position: absolute;  
      bottom: -30px;  
      background: rgba(2, 132, 199, 0.15);  
      border: 1px solid rgba(255, 255, 255, 0.6);  
      border-radius: 50%;  
      animation: floatUp linear forwards;  
    }  
  
    @keyframes floatUp {  
      0% { transform: translateY(0) scale(0.8); opacity: 0.8; }  
      100% { transform: translateY(-105vh) scale(1.2); opacity: 0; }  
    }  
  
    .swimming-creature {  
      position: absolute;  
      top: 40%;  
      left: -150px;  
      font-size: 4rem;  
      opacity: 0.35;  
      filter: drop-shadow(2px 4px 6px rgba(0,0,0,0.2));  
      white-space: nowrap;  
      pointer-events: none;  
    }  
  
    @keyframes swimRight {  
      0% { left: -180px; transform: translateY(0) scaleX(-1); }  
      50% { transform: translateY(-20px) scaleX(-1); }  
      100% { left: 110vw; transform: translateY(0) scaleX(-1); }  
    }  
  
    /* Cornice QR Code con Ombre Marine */  
    .qr-frame-container {  
      display: flex;  
      flex-direction: column;  
      align-items: center;  
      justify-content: center;  
      padding: 24px;  
      background: linear-gradient(180deg, #e0f2fe 0%, #ffffff 100%);  
      border-radius: 24px;  
      border: 4px dashed #0284c7;  
      box-shadow: var(--shadow);  
      margin: 20px 0;  
    }  
  
    .marine-silhouettes {  
      display: flex;  
      justify-content: space-between;  
      width: 100%;  
      max-width: 320px;  
      font-size: 1.5rem;  
      color: #0369a1;  
      opacity: 0.7;  
      margin: 8px 0;  
    }  
  
    .qr-box {  
      background: white;  
      padding: 16px;  
      border-radius: 16px;  
      box-shadow: 0 8px 20px rgba(0,0,0,0.1);  
      border: 2px solid #38bdf8;  
    }  
  
    .qr-box img {  
      width: 220px;  
      height: 220px;  
      display: block;  
      border-radius: 8px;  
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
  
    /* Card Specie */  
    .search-box { width: 100%; padding: 12px; border-radius: 12  

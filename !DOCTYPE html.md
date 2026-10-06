<!DOCTYPE html>  
<html lang="it">  
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Yari & Chiara - I Sub del Golfo</title>  
    
  <link rel="preconnect" href="https://fonts.googleapis.com">  
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>  
  <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Cinzel:wght@700&family=Fira+Code:wght@600&family=Lekton:ital,wght@0,700;1,400&family=Lobster&family=Montserrat:wght@700;900&family=Pacifico&family=Playfair+Display:ital,wght@0,600;0,800;1,600&family=Plus+Jakarta+Sans:wght@500;700;800&family=Press+Start+2P&family=Roboto+Slab:wght@700&display=swap" rel="stylesheet">  
  
  <style>  
    :root {  
      --primary: #0284c7;  
      --primary-dark: #0369a1;  
      --primary-light: #e0f2fe;  
      --bg-color: #f0f9ff;  
      --bg-image: none;  
      --surface: rgba(255, 255, 255, 0.94);  
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
      transition: background 0.3s ease;  
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
  
    .gallery-scroll { display: flex; gap: 12px; overflow-x: auto; padding: 8px 0; scroll-snap-type: x mandatory; }  
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
  
    .player-select { display: flex; gap: 10px; margin-bottom: 14px; }  
    .player-btn {  
      flex: 1; padding: 10px; border-radius: 10px; border: 1px solid var(--border);  
      background: #ffffff; font-weight: 700; cursor: pointer; text-align: center; color: var(--text);  
    }  
    .player-btn.active { background: var(--primary); color: white; border-color: var(--primary-dark); }  
  
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
    .species-thumb { width: 85px; height: 85px; border-radius: 12px; object-fit: cover; background: #e2e8f0; flex-shrink: 0; border: 1px solid #cbd5e1; display: block; }  
    .star-rating { display: flex; gap: 4px; font-size: 1.4rem; color: #cbd5e1; cursor: pointer; user-select: none; }  
    .star-rating .star.active { color: #f59e0b; }  
  
    .stat-row { display: flex; justify-content: space-between; align-items: center; padding: 10px 0; border-bottom: 1px solid #f1f5f9; font-weight: 600; }  
    .stat-counter { display: flex; align-items: center; gap: 6px; }  
    .count-btn { background: var(--primary-light); color: var(--primary-dark); border: 1px solid var(--border); width: 28px; height: 28px; border-radius: 6px; font-weight: 800; cursor: pointer; }  
  
    .trophy-card { background: linear-gradient(135deg, #fef9c3 0%, #fef08a 100%); border: 1px solid #fde047; padding: 12px  

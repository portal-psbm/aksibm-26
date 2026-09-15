---
layout: default
title: Persiapan AL
permalink: /persiapan-al/
---

<style>
  /* ===== EXECUTIVE CABINET THEME ===== */
  
  /* Premium Dark Navy Cabinet Background */
  .cabinet-container {
    background: 
      linear-gradient(135deg, #0a1929 0%, #1a2942 50%, #0f2038 100%);
    padding: 28px 28px 0 28px;
    border-radius: 16px 16px 0 0;
    box-shadow: 
      inset 0 2px 20px rgba(0,0,0,0.4),
      inset 0 -2px 10px rgba(212, 175, 55, 0.05),
      0 12px 40px rgba(10, 25, 41, 0.3);
    position: relative;
    border: 1px solid rgba(212, 175, 55, 0.15);
    border-bottom: none;
  }

  /* Gold accent line di atas kabinet */
  .cabinet-container::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: linear-gradient(90deg, 
      transparent 0%, 
      #d4af37 20%, 
      #f4d77a 50%, 
      #d4af37 80%, 
      transparent 100%);
    opacity: 0.6;
  }

  /* ===== Folder Shelf ===== */
  .folder-shelf {
    display: flex;
    flex-wrap: nowrap;
    gap: 8px;
    padding: 0 8px;
    position: relative;
    z-index: 10;
    overflow-x: auto;
    overflow-y: visible;
    scrollbar-width: thin;
    scrollbar-color: #d4af37 transparent;
    padding-bottom: 4px;
  }

  .folder-shelf::-webkit-scrollbar { height: 4px; }
  .folder-shelf::-webkit-scrollbar-track { background: rgba(255,255,255,0.03); border-radius: 2px; }
  .folder-shelf::-webkit-scrollbar-thumb { background: #d4af37; border-radius: 2px; }

  /* ===== Elegant Folder Tab ===== */
  .folder-tab {
    position: relative;
    flex: 0 0 auto;
    min-width: 115px;
    padding: 16px 14px 20px 14px;
    background: linear-gradient(180deg, #f5f0e6 0%, #e8dcc4 100%);
    border-radius: 8px 8px 0 0;
    border: 1px solid rgba(139, 115, 75, 0.3);
    border-bottom: none;
    cursor: pointer;
    text-align: center;
    font-weight: 600;
    font-size: 0.82rem;
    color: #3d2f1f;
    letter-spacing: 0.3px;
    transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    transform: translateY(4px);
    box-shadow: 
      0 -2px 6px rgba(0,0,0,0.15),
      inset 0 1px 0 rgba(255,255,255,0.6);
    text-shadow: 0 1px 0 rgba(255,255,255,0.4);
    white-space: nowrap;
  }

  /* Tab kecil di atas folder - bentuk trapesium elegan */
  .folder-tab::before {
    content: '';
    position: absolute;
    top: -7px;
    left: 18%;
    width: 64%;
    height: 7px;
    background: linear-gradient(180deg, #e8dcc4 0%, #d4c5a0 100%);
    border-radius: 4px 4px 0 0;
    border: 1px solid rgba(139, 115, 75, 0.3);
    border-bottom: none;
    transition: all 0.4s ease;
    box-shadow: inset 0 1px 0 rgba(255,255,255,0.5);
  }

  /* Lipatan kecil di pojok kanan bawah - efek realistis */
  .folder-tab::after {
    content: '';
    position: absolute;
    bottom: 0;
    right: 0;
    width: 12px;
    height: 12px;
    background: linear-gradient(135deg, 
      transparent 50%, 
      rgba(139, 115, 75, 0.15) 50%);
    border-radius: 0 0 0 8px;
    transition: all 0.3s ease;
  }

  .folder-tab:hover {
    background: linear-gradient(180deg, #faf5ea 0%, #f0e4c8 100%);
    transform: translateY(0px);
    color: #1e3a5f;
    box-shadow: 
      0 -4px 12px rgba(212, 175, 55, 0.2),
      inset 0 1px 0 rgba(255,255,255,0.8);
  }
  .folder-tab:hover::before {
    background: linear-gradient(180deg, #f0e4c8 0%, #e0d0a8 100%);
  }

  /* ===== Active Folder - Premium Navy + Gold ===== */
  .folder-tab.active {
    background: linear-gradient(180deg, #1e3a5f 0%, #0f2038 100%);
    color: #f4d77a;
    transform: translateY(-8px);
    z-index: 20;
    border: 1px solid #d4af37;
    border-bottom: none;
    box-shadow: 
      0 -6px 20px rgba(212, 175, 55, 0.35),
      0 0 0 1px rgba(212, 175, 55, 0.2),
      inset 0 1px 0 rgba(255,255,255,0.1);
    font-weight: 700;
    letter-spacing: 0.5px;
    text-shadow: 0 1px 2px rgba(0,0,0,0.4);
  }
  .folder-tab.active::before {
    background: linear-gradient(180deg, #1e3a5f 0%, #0f2038 100%);
    border-color: #d4af37;
    height: 9px;
    top: -9px;
    box-shadow: 0 -2px 6px rgba(212, 175, 55, 0.3);
  }
  .folder-tab.active::after {
    background: linear-gradient(135deg, 
      transparent 50%, 
      rgba(212, 175, 55, 0.2) 50%);
  }

  /* ===== Content Area (Drawer) ===== */
  .al-content {
    background: #ffffff;
    border: 1px solid rgba(212, 175, 55, 0.2);
    border-top: 3px solid #d4af37;
    border-radius: 0 0 16px 16px;
    padding: 32px;
    min-height: 500px;
    box-shadow: 
      0 12px 32px rgba(10, 25, 41, 0.08),
      inset 0 1px 0 rgba(212, 175, 55, 0.1);
    position: relative;
    z-index: 5;
    margin-top: -1px;
  }

  .al-panel { display: none; animation: fadeIn 0.4s cubic-bezier(0.4, 0, 0.2, 1); }
  .al-panel.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: translateY(0); } }

  /* ===== Internal Components - Refined ===== */
  .card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 16px; margin: 16px 0; }
  .stat-card { 
    background: #ffffff; 
    border-radius: 12px; 
    padding: 20px; 
    box-shadow: 0 2px 12px rgba(10, 25, 41, 0.06); 
    border-left: 4px solid #1e3a5f; 
    transition: all 0.3s ease;
    border: 1px solid #f0f0f0;
    border-left: 4px solid #1e3a5f;
  }
  .stat-card:hover { 
    transform: translateY(-3px); 
    box-shadow: 0 8px 20px rgba(10, 25, 41, 0.1);
    border-left-color: #d4af37;
  }
  .stat-card .label { font-size: 0.82rem; color: #64748b; margin-bottom: 8px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.5px; }
  .stat-card .value { font-size: 1.9rem; font-weight: 700; color: #0a1929; letter-spacing: -0.5px; }
  
  .progress-row { display: flex; align-items: center; gap: 12px; padding: 12px 0; border-bottom: 1px solid #f1f5f9; }
  .progress-row .label { width: 60px; font-weight: 700; color: #1e3a5f; font-size: 0.9rem; }
  .progress-row .bar { flex: 1; height: 10px; background: #f0f0f0; border-radius: 5px; overflow: hidden; }
  .progress-row .bar-fill { height: 100%; background: linear-gradient(90deg, #1e3a5f 0%, #2c5282 100%); border-radius: 5px; transition: width 0.8s cubic-bezier(0.4, 0, 0.2, 1); }
  .progress-row .bar-fill.review { background: linear-gradient(90deg, #d4af37 0%, #f4d77a 100%); }
  .progress-row .percent { width: 45px; font-weight: 700; text-align: right; color: #0a1929; }
  .progress-row .status { width: 80px; text-align: center; font-size: 0.7rem; font-weight: 700; padding: 4px 10px; border-radius: 12px; text-transform: uppercase; letter-spacing: 0.8px; }
  .status-ready { background: #e8f5e9; color: #1b5e20; border: 1px solid #a5d6a7; }
  .status-review { background: #fff8e1; color: #b8860b; border: 1px solid #ffe082; }
  
  .alert-box { 
    background: linear-gradient(135deg, #fffbeb 0%, #fef3c7 100%); 
    border-left: 4px solid #d4af37; 
    padding: 18px 20px; 
    border-radius: 8px; 
    margin: 20px 0;
    box-shadow: 0 2px 8px rgba(212, 175, 55, 0.1);
  }
  .alert-box h4 { color: #92400e; font-size: 0.95rem; margin: 0 0 10px 0; font-weight: 700; }
  .alert-box .item { padding: 4px 0; font-size: 0.9rem; color: #78350f; }
  
  .sub-nav { display: flex; gap: 4px; margin-bottom: 20px; border-bottom: 2px solid #e5e7eb; flex-wrap: wrap; }
  .sub-nav button { 
    padding: 10px 18px; 
    background: transparent; 
    border: none; 
    cursor: pointer; 
    font-weight: 600; 
    color: #64748b; 
    border-bottom: 3px solid transparent; 
    margin-bottom: -2px; 
    transition: all 0.2s; 
    font-size: 0.9rem;
    letter-spacing: 0.2px;
  }
  .sub-nav button:hover { color: #1e3a5f; background: #f8fafc; border-radius: 6px 6px 0 0; }
  .sub-nav button.active { color: #1e3a5f; border-bottom-color: #d4af37; }
  
  .indicator-card { 
    background: white; 
    border-radius: 10px; 
    padding: 18px; 
    margin-bottom: 12px; 
    box-shadow: 0 2px 10px rgba(10, 25, 41, 0.05); 
    border-left: 4px solid #1e3a5f; 
    transition: all 0.2s;
    border: 1px solid #f0f0f0;
    border-left: 4px solid #1e3a5f;
  }
  .indicator-card:hover { box-shadow: 0 6px 16px rgba(10, 25, 41, 0.1); transform: translateX(2px); }
  .indicator-card.review { border-left-color: #d4af37; }
  .indicator-card .head { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
  .indicator-card .title { font-weight: 700; color: #0a1929; font-size: 1rem; }
  .indicator-card .meta { font-size: 0.85rem; color: #64748b; margin: 4px 0; }
  
  .btn { padding: 8px 16px; border-radius: 6px; border: none; cursor: pointer; font-size: 0.85rem; font-weight: 600; transition: all 0.2s; letter-spacing: 0.2px; }
  .btn-primary { background: linear-gradient(135deg, #1e3a5f 0%, #0f2038 100%); color: white; box-shadow: 0 2px 6px rgba(30, 58, 95, 0.3); }
  .btn-primary:hover { background: linear-gradient(135deg, #2c5282 0%, #1e3a5f 100%); box-shadow: 0 4px 12px rgba(30, 58, 95, 0.4); transform: translateY(-1px); }
  .btn-outline { background: white; color: #1e3a5f; border: 1px solid #cbd5e1; }
  .btn-outline:hover { background: #f8fafc; border-color: #1e3a5f; color: #0f2038; }
  
  .search-box { 
    width: 100%; 
    padding: 12px 18px; 
    border: 2px solid #e5e7eb; 
    border-radius: 8px; 
    font-size: 0.95rem; 
    margin-bottom: 16px; 
    transition: all 0.2s;
    background: #fafafa;
  }
  .search-box:focus { outline: none; border-color: #d4af37; background: white; box-shadow: 0 0 0 3px rgba(212, 175, 55, 0.1); }
  
  .evidence-item { 
    background: white; 
    padding: 16px; 
    border-radius: 8px; 
    margin-bottom: 10px; 
    border-left: 4px solid #1e3a5f; 
    box-shadow: 0 1px 4px rgba(10, 25, 41, 0.05);
    border: 1px solid #f0f0f0;
    border-left: 4px solid #1e3a5f;
    transition: all 0.2s;
  }
  .evidence-item:hover { box-shadow: 0 4px 12px rgba(10, 25, 41, 0.08); }
  .evidence-item.review { border-left-color: #d4af37; }
  .evidence-item .code { font-family: 'Courier New', monospace; color: #1e3a5f; font-weight: 700; font-size: 0.85rem; background: #f0f4f8; padding: 3px 8px; border-radius: 4px; }
  .evidence-item .path { font-size: 0.8rem; color: #64748b; margin-top: 4px; }
  
  .question-card { 
    background: white; 
    padding: 18px; 
    border-radius: 10px; 
    margin-bottom: 12px; 
    box-shadow: 0 2px 10px rgba(10, 25, 41, 0.05); 
    border-left: 4px solid #1e3a5f;
    border: 1px solid #f0f0f0;
    border-left: 4px solid #1e3a5f;
  }
  .question-card.critical { border-left-color: #c62828; }
  .question-card .q-code { font-family: 'Courier New', monospace; color: #c62828; font-weight: 700; font-size: 0.8rem; }
  .question-card .q-text { font-size: 1rem; font-weight: 600; margin: 8px 0; color: #0a1929; }
  
  .ppepp-step { 
    background: white; 
    padding: 18px 22px; 
    border-left: 4px solid #1e3a5f; 
    position: relative; 
    box-shadow: 0 2px 8px rgba(10, 25, 41, 0.05); 
    margin-bottom: 10px; 
    border-radius: 0 8px 8px 0;
    border: 1px solid #f0f0f0;
    border-left: 4px solid #1e3a5f;
  }
  .ppepp-step::after { content: '▼'; position: absolute; bottom: -14px; left: 50%; transform: translateX(-50%); color: #d4af37; font-size: 0.9rem; }
  .ppepp-step:last-child::after { display: none; }
  .ppepp-step .step-title { font-weight: 700; color: #1e3a5f; margin-bottom: 6px; font-size: 0.9rem; letter-spacing: 0.5px; text-transform: uppercase; }
  .ppepp-step .step-content { color: #475569; font-size: 0.92rem; }
  
  .risk-table { width: 100%; border-collapse: separate; border-spacing: 0; margin-top: 12px; border-radius: 8px; overflow: hidden; box-shadow: 0 2px 8px rgba(10, 25, 41, 0.05); }
  .risk-table th, .risk-table td { padding: 14px; text-align: left; border-bottom: 1px solid #f1f5f9; font-size: 0.9rem; }
  .risk-table th { background: linear-gradient(180deg, #f8fafc 0%, #f0f4f8 100%); color: #1e3a5f; font-weight: 700; text-transform: uppercase; font-size: 0.78rem; letter-spacing: 0.5px; }
  .risk-table tr:hover td { background: #fafbfc; }
  .risk-badge { display: inline-block; padding: 4px 12px; border-radius: 12px; font-size: 0.72rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.5px; }
  .risk-critical { background: #fee2e2; color: #991b1b; border: 1px solid #fecaca; }
  .risk-high { background: #ffedd5; color: #9a3412; border: 1px solid #fed7aa; }
  .risk-medium { background: #fef3c7; color: #92400e; border: 1px solid #fde68a; }
  
  .team-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 16px; }
  .team-card { 
    background: white; 
    padding: 20px; 
    border-radius: 12px; 
    box-shadow: 0 2px 10px rgba(10, 25, 41, 0.06); 
    border-top: 4px solid #1e3a5f; 
    transition: all 0.3s;
    border: 1px solid #f0f0f0;
    border-top: 4px solid #1e3a5f;
  }
  .team-card:hover { transform: translateY(-3px); box-shadow: 0 8px 20px rgba(10, 25, 41, 0.1); border-top-color: #d4af37; }
  .team-card .role { font-size: 0.75rem; color: #64748b; text-transform: uppercase; letter-spacing: 0.8px; font-weight: 700; }
  .team-card .name { font-size: 1.15rem; font-weight: 700; color: #0a1929; margin: 8px 0; }
  
  .checklist-group { background: white; padding: 22px; border-radius: 12px; margin-bottom: 16px; box-shadow: 0 2px 10px rgba(10, 25, 41, 0.05); border: 1px solid #f0f0f0; }
  .checklist-group h4 { color: #1e3a5f; margin: 0 0 16px 0; font-size: 1.1rem; font-weight: 700; }
  .checklist-item { display: flex; align-items: center; gap: 12px; padding: 10px 0; border-bottom: 1px solid #f1f5f9; }
  .checklist-item input[type="checkbox"] { width: 18px; height: 18px; cursor: pointer; accent-color: #1e3a5f; }
  .checklist-item.done label { text-decoration: line-through; color: #94a3b8; }
  
  .mode-al-view { 
    background: linear-gradient(135deg, #0a1929 0%, #1e3a5f 100%); 
    color: white; 
    padding: 44px 32px; 
    border-radius: 16px; 
    text-align: center;
    box-shadow: 0 8px 24px rgba(10, 25, 41, 0.2);
    position: relative;
    overflow: hidden;
  }
  .mode-al-view::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, transparent, #d4af37, transparent);
  }
  .mode-al-view .search-big { 
    width: 100%; 
    max-width: 600px; 
    padding: 16px 24px; 
    border-radius: 30px; 
    border: 1px solid rgba(212, 175, 55, 0.3); 
    background: rgba(255,255,255,0.05); 
    color: white; 
    font-size: 1rem; 
    margin: 20px 0; 
    backdrop-filter: blur(4px);
  }
  .mode-al-view .search-big::placeholder { color: rgba(255,255,255,0.5); }
  .mode-al-view .search-big:focus { outline: none; border-color: #d4af37; background: rgba(255,255,255,0.1); box-shadow: 0 0 0 3px rgba(212, 175, 55, 0.15); }
  .quick-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 12px; margin-top: 24px; max-width: 800px; margin-left: auto; margin-right: auto; }
  .quick-btn { 
    background: rgba(255,255,255,0.06); 
    color: #f4d77a; 
    padding: 16px; 
    border-radius: 8px; 
    border: 1px solid rgba(212, 175, 55, 0.2); 
    cursor: pointer; 
    font-weight: 600; 
    transition: all 0.2s; 
    font-size: 0.9rem;
    letter-spacing: 0.3px;
  }
  .quick-btn:hover { background: rgba(212, 175, 55, 0.15); border-color: #d4af37; transform: translateY(-2px); }

  /* ===== RESPONSIVE ===== */
  @media (min-width: 1200px) {
    .folder-shelf { flex-wrap: nowrap; overflow-x: visible; padding-bottom: 0; }
    .folder-tab { flex: 1 1 0; min-width: 0; padding: 16px 8px 20px 8px; font-size: 0.8rem; white-space: normal; }
    .folder-tab::before { left: 22%; width: 56%; }
  }

  @media (min-width: 768px) and (max-width: 1199px) {
    .folder-shelf { flex-wrap: wrap; overflow-x: visible; padding-bottom: 0; }
    .folder-tab { flex: 0 1 calc(20% - 8px); min-width: 0; font-size: 0.8rem; white-space: normal; }
  }

  @media (max-width: 767px) {
    .folder-shelf { overflow-x: auto; flex-wrap: nowrap; padding-bottom: 8px; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
    .folder-shelf::-webkit-scrollbar { display: none; }
    .folder-tab { min-width: 115px; flex: 0 0 auto; font-size: 0.78rem; padding: 14px 12px 18px 12px; }
    .progress-row { flex-wrap: wrap; }
    .progress-row .label { width: 100%; margin-bottom: 4px; }
    .al-content { padding: 20px; }
    .cabinet-container { padding: 20px 16px 0 16px; }
  }
</style>

<!-- ===== KABINET FOLDER NAV ===== -->
<div class="cabinet-container">
  <div class="folder-shelf">
    <div class="folder-tab active" onclick="showPanel('dashboard', this)">📊<br>Dashboard</div>
    <div class="folder-tab" onclick="showPanel('kriteria', this)">📑<br>Kriteria</div>
    <div class="folder-tab" onclick="showPanel('bukti', this)">📎<br>Bukti</div>
    <div class="folder-tab" onclick="showPanel('pertanyaan', this)">❓<br>Pertanyaan</div>
    <div class="folder-tab" onclick="showPanel('mock', this)">🎭<br>Mock AL</div>
    <div class="folder-tab" onclick="showPanel('ppepp', this)">🔄<br>PPEPP</div>
    <div class="folder-tab" onclick="showPanel('risiko', this)">⚠️<br>Risiko</div>
    <div class="folder-tab" onclick="showPanel('tim', this)">👥<br>Tim/PIC</div>
    <div class="folder-tab" onclick="showPanel('checklist', this)">✅<br>Checklist</div>
    <div class="folder-tab" onclick="showPanel('modeal', this)">🚀<br>Mode AL</div>
  </div>

  <!-- ===== AREA KONTEN (LACI) ===== -->
  <div class="al-content">
    
    <!-- DASHBOARD -->
    <div class="al-panel active" id="panel-dashboard">
      <h2 style="color:#0a1929; margin-top:0; font-size:1.3rem; font-weight:700;">Overall Readiness</h2>
      <div class="progress-row"><div class="bar" style="height:14px;"><div class="bar-fill" style="width:89%;"></div></div><div class="percent" style="font-size:1.1rem;">89%</div></div>
      <div class="card-grid">
        <div class="stat-card"><div class="label">Evidence</div><div class="value">142/150</div><div class="sub" style="color:#64748b; font-size:0.85rem; margin-top:4px;">95% verified</div></div>
        <div class="stat-card"><div class="label">Questions</div><div class="value">126/140</div><div class="sub" style="color:#64748b; font-size:0.85rem; margin-top:4px;">90% ready</div></div>
        <div class="stat-card" style="border-left-color:#c62828;"><div class="label">Open Risk</div><div class="value" style="color:#c62828;">6</div><div class="sub" style="color:#64748b; font-size:0.85rem; margin-top:4px;">2 critical</div></div>
        <div class="stat-card" style="border-left-color:#1b5e20;"><div class="label">Mock Score</div><div class="value" style="color:#1b5e20;">3.4</div><div class="sub" style="color:#64748b; font-size:0.85rem; margin-top:4px;">/4.0 average</div></div>
      </div>
      <h3 style="color:#0a1929; margin-top:28px; font-size:1.1rem; font-weight:700;">Kesiapan Per Kriteria</h3>
      <div class="progress-row"><div class="label">C.1</div><div class="bar"><div class="bar-fill" style="width:96%;"></div></div><div class="percent">96%</div><div class="status status-ready">READY</div></div>
      <div class="progress-row"><div class="label">C.2</div><div class="bar"><div class="bar-fill" style="width:92%;"></div></div><div class="percent">92%</div><div class="status status-ready">READY</div></div>
      <div class="progress-row"><div class="label">C.3</div><div class="bar"><div class="bar-fill review" style="width:87%;"></div></div><div class="percent">87%</div><div class="status status-review">REVIEW</div></div>
      <div class="progress-row"><div class="label">C.4</div><div class="bar"><div class="bar-fill" style="width:97%;"></div></div><div class="percent">97%</div><div class="status status-ready">READY</div></div>
      <div class="progress-row"><div class="label">C.5</div><div class="bar"><div class="bar-fill" style="width:93%;"></div></div><div class="percent">93%</div><div class="status status-ready">READY</div></div>
      <div class="progress-row"><div class="label">C.6</div><div class="bar"><div class="bar-fill review" style="width:86%;"></div></div><div class="percent">86%</div><div class="status status-review">REVIEW</div></div>
      <div class="progress-row"><div class="label">C.7</div><div class="bar"><div class="bar-fill review" style="width:83%;"></div></div><div class="percent">83%</div><div class="status status-review">REVIEW</div></div>
      <div class="alert-box">
        <h4>⚠️ Perlu Perhatian</h4>
        <div class="item">🔴 <strong>2 Critical Risk</strong> — bukti CPL & link evidence</div>
        <div class="item">🟠 <strong>4 Evidence</strong> belum verified</div>
        <div class="item">🟡 <strong>3 PIC</strong> Mock AL score &lt; 3</div>
      </div>
    </div>

    <!-- KRITERIA -->
    <div class="al-panel" id="panel-kriteria">
      <h2 style="color:#0a1929; margin-top:0; font-size:1.3rem; font-weight:700;">Kriteria Akreditasi</h2>
      <div class="sub-nav" id="kriteriaSubNav">
        <button class="active" onclick="showKriteria('c1', this)">C.1 VMTS</button>
        <button onclick="showKriteria('c2', this)">C.2 Tata Pamong</button>
        <button onclick="showKriteria('c3', this)">C.3 Relevansi</button>
        <button onclick="showKriteria('c4', this)">C.4 SDM</button>
        <button onclick="showKriteria('c5', this)">C.5 Sarpras & K3L</button>
        <button onclick="showKriteria('c6', this)">C.6 Mahasiswa</button>
        <button onclick="showKriteria('c7', this)">C.7 SPMI</button>
      </div>
      <div id="kriteriaContent"></div>
    </div>

    <!-- BUKTI -->
    <div class="al-panel" id="panel-bukti">
      <h2 style="color:#0a1929; margin-top:0; font-size:1.3rem; font-weight:700;">🔍 Bukti Asesmen Lapangan</h2>
      <input type="text" class="search-box" id="buktiSearch" placeholder="Cari bukti: CPL, RPS, tracer, penelitian..." oninput="filterBukti()">
      <div class="card-grid">
        <div class="stat-card" style="border-left-color:#1b5e20;"><div class="label">Total Evidence</div><div class="value" style="color:#1b5e20;">157</div></div>
        <div class="stat-card" style="border-left-color:#1565c0;"><div class="label">Verified</div><div class="value" style="color:#1565c0;">148</div></div>
        <div class="stat-card" style="border-left-color:#d4af37;"><div class="label">Review</div><div class="value" style="color:#d4af37;">6</div></div>
        <div class="stat-card" style="border-left-color:#c62828;"><div class="label">Missing</div><div class="value" style="color:#c62828;">3</div></div>
      </div>
      <div id="buktiList"></div>
    </div>

    <!-- PERTANYAAN -->
    <div class="al-panel" id="panel-pertanyaan">
      <h2 style="color:#0a1929; margin-top:0; font-size:1.3rem; font-weight:700;">🔥 Bank Pertanyaan Asesor</h2>
      <div class="sub-nav">
        <button class="active" onclick="filterPertanyaan('all', this)">Semua</button>
        <button onclick="filterPertanyaan('critical', this)">🔥 Critical</button>
        <button onclick="filterPertanyaan('ppepp', this)">🔄 PPEPP</button>
        <button onclick="filterPertanyaan('data', this)">📊 Data</button>
      </div>
      <div id="pertanyaanList"></div>
    </div>

    <!-- MOCK AL -->
    <div class="al-panel" id="panel-mock">
      <h2 style="color:#0a1929; margin-top:0; font-size:1.3rem; font-weight:700;">🎭 Simulasi Asesmen Lapangan</h2>
      <div id="mockSetup">
        <div class="card-grid">
          <div class="stat-card"><div class="label">Pilih Kriteria</div><select style="width:100%; padding:10px; margin-top:8px; border-radius:6px; border:1px solid #cbd5e1; background:white;"><option>Semua Kriteria</option><option selected>C.3 Relevansi</option></select></div>
          <div class="stat-card"><div class="label">Mode Asesor</div><select style="width:100%; padding:10px; margin-top:8px; border-radius:6px; border:1px solid #cbd5e1; background:white;"><option>Normal</option><option selected>🔥 Kritis</option></select></div>
          <div class="stat-card"><div class="label">Jumlah Pertanyaan</div><div style="margin-top:8px; display:flex; gap:6px;"><button class="btn btn-outline">10</button><button class="btn btn-primary">20</button><button class="btn btn-outline">30</button></div></div>
        </div>
        <div style="text-align:center; margin-top:28px;"><button class="btn btn-primary" style="padding:14px 40px; font-size:1rem;" onclick="startMock()">🚀 MULAI MOCK AL</button></div>
      </div>
      <div id="mockSession" style="display:none;"></div>
    </div>

    <!-- PPEPP -->
    <div class="al-panel" id="panel-ppepp">
      <h2 style="color:#0a1929; margin-top:0; font-size:1.3rem; font-weight:700;">🔄 PPEPP Closed-Loop Improvement</h2>
      <div class="sub-nav">
        <button class="active" onclick="showPPEPP('kurikulum', this)">Kurikulum</button>
        <button onclick="showPPEPP('cpl', this)">CPL</button>
        <button onclick="showPPEPP('tracer', this)">Tracer</button>
        <button onclick="showPPEPP('ami', this)">AMI</button>
      </div>
      <div id="ppeppContent"></div>
    </div>

    <!-- RISIKO -->
    <div class="al-panel" id="panel-risiko">
      <h2 style="color:#0a1929; margin-top:0; font-size:1.3rem; font-weight:700;">⚠️ Risk & Clarification Register</h2>
      <div class="card-grid">
        <div class="stat-card" style="border-left-color:#c62828;"><div class="label">🔴 Critical</div><div class="value" style="color:#c62828;">2</div></div>
        <div class="stat-card" style="border-left-color:#d4af37;"><div class="label">🟠 High</div><div class="value" style="color:#d4af37;">4</div></div>
        <div class="stat-card" style="border-left-color:#b8860b;"><div class="label">🟡 Medium</div><div class="value" style="color:#b8860b;">7</div></div>
        <div class="stat-card" style="border-left-color:#1b5e20;"><div class="label">🟢 Resolved</div><div class="value" style="color:#1b5e20;">28</div></div>
      </div>
      <table class="risk-table">
        <thead><tr><th>Risiko</th><th>Kriteria</th><th>PIC</th><th>H-</th><th>Status</th></tr></thead>
        <tbody>
          <tr><td>Bukti CPL belum lengkap</td><td>C.3</td><td>Kurikulum</td><td>18</td><td><span class="risk-badge risk-critical">CRITICAL</span></td></tr>
          <tr><td>Link evidence mati</td><td>C.3</td><td>Admin</td><td>14</td><td><span class="risk-badge risk-high">HIGH</span></td></tr>
          <tr><td>Mock score &lt; 3</td><td>C.7</td><td>UPM</td><td>10</td><td><span class="risk-badge risk-medium">MEDIUM</span></td></tr>
        </tbody>
      </table>
    </div>

    <!-- TIM/PIC -->
    <div class="al-panel" id="panel-tim">
      <h2 style="color:#0a1929; margin-top:0; font-size:1.3rem; font-weight:700;">👥 Tim Asesmen Lapangan</h2>
      <div class="team-grid">
        <div class="team-card"><div class="role">KETUA TIM</div><div class="name">AW</div><div class="stat" style="color:#475569; font-size:0.9rem;">Overall AL Readiness: <strong style="color:#0a1929;">94%</strong></div></div>
        <div class="team-card"><div class="role">PIC C.1 VMTS</div><div class="name">AW + SH</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0a1929;">12/12</strong></div></div>
        <div class="team-card" style="border-top-color:#d4af37;"><div class="role">PIC C.3 Relevansi</div><div class="name">VF + BU</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0a1929;">18/20</strong><br>Mock Score: <strong style="color:#b8860b;">3.2</strong> ⚠️</div></div>
        <div class="team-card"><div class="role">PIC C.4 SDM</div><div class="name">DW + VF</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0a1929;">20/20</strong></div></div>
        <div class="team-card"><div class="role">PIC C.5 Sarpras & K3L</div><div class="name">Z + MF</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0a1929;">14/16</strong></div></div>
        <div class="team-card" style="border-top-color:#d4af37;"><div class="role">PIC C.6 Mahasiswa</div><div class="name">MF + DW</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0a1929;">21/24</strong><br>Mock Score: <strong style="color:#b8860b;">2.9</strong> ⚠️</div></div>
        <div class="team-card" style="border-top-color:#d4af37;"><div class="role">PIC C.7 SPMI</div><div class="name">BU + SH</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0a1929;">16/18</strong><br>Mock Score: <strong style="color:#b8860b;">2.8</strong> ⚠️</div></div>
      </div>
    </div>

    <!-- CHECKLIST -->
    <div class="al-panel" id="panel-checklist">
      <h2 style="color:#0a1929; margin-top:0; font-size:1.3rem; font-weight:700;">✅ Checklist Menuju AL</h2>
      <div class="sub-nav">
        <button class="active" onclick="showChecklist('h30', this)">H-30</button>
        <button onclick="showChecklist('h21', this)">H-21</button>
        <button onclick="showChecklist('h14', this)">H-14</button>
        <button onclick="showChecklist('h7', this)">H-7</button>
        <button onclick="showChecklist('h1', this)">H-1</button>
      </div>
      <div id="checklistContent"></div>
    </div>

    <!-- MODE AL -->
    <div class="al-panel" id="panel-modeal">
      <div class="mode-al-view">
        <h2 style="margin-top:0;">🚀 PSBM — ASESMEN LAPANGAN</h2>
        <p style="opacity:0.8; font-size:0.95rem;">Mode Presentasi • Semua data internal disembunyikan</p>
        <input type="text" class="search-big" placeholder="🔍 Cari bukti: CPL / RPS / tracer / penelitian...">
        <div style="margin:20px 0; display:flex; gap:8px; justify-content:center; flex-wrap:wrap;">
          <button class="quick-btn">C.1</button><button class="quick-btn">C.2</button><button class="quick-btn">C.3</button><button class="quick-btn">C.4</button>
          <button class="quick-btn">C.5</button><button class="quick-btn">C.6</button><button class="quick-btn">C.7</button>
        </div>
        <h3 style="margin-top:32px; text-align:left; font-size:1.1rem; color:#f4d77a;">⚡ QUICK EVIDENCE</h3>
        <div class="quick-grid">
          <button class="quick-btn">📄 LED</button><button class="quick-btn">📊 LKPS</button><button class="quick-btn">🎯 VMTS</button><button class="quick-btn">📘 Kurikulum</button>
          <button class="quick-btn">🎓 CPL</button><button class="quick-btn">📝 RPS</button><button class="quick-btn">🔬 Penelitian</button><button class="quick-btn">🤝 PkM</button>
          <button class="quick-btn">📈 Tracer</button><button class="quick-btn">👨‍🏫 DTPS</button><button class="quick-btn">🔍 AMI</button><button class="quick-btn">🔄 PPEPP</button>
        </div>
        <div style="margin-top:32px; padding:16px; background:rgba(212, 175, 55, 0.08); border-radius:10px; border:1px solid rgba(212, 175, 55, 0.2);">
          <strong style="color:#f4d77a;">💡 Catatan:</strong> <span style="color:#cbd5e1; font-size:0.9rem;">Risk register, skor kesiapan, missing evidence, dan catatan internal <strong style="color:#ffffff;">TIDAK</strong> tampil di mode ini.</span>
        </div>
      </div>
    </div>

  </div>
</div>

<script>
const dataKriteria = {
  c1: { title: 'C.1 VMTS', readiness: 96, status: 'READY', indicators: [{ name: 'Kekhasan VMTS', status: 'ready', evidence: '5/5', questions: 6, pic: 'AW + SH' }, { name: 'Mekanisme Penyusunan', status: 'ready', evidence: '4/4', questions: 5, pic: 'AW + SH' }, { name: 'Tingkat Pemahaman', status: 'ready', evidence: '6/6', questions: 7, pic: 'AW + SH' }] },
  c2: { title: 'C.2 Tata Pamong, Tata Kelola, Kerja Sama, Keuangan', readiness: 92, status: 'READY', indicators: [{ name: 'Sistem Tata Pamong', status: 'ready', evidence: '5/5', questions: 8, pic: 'SH + BU' }, { name: 'Kerja Sama', status: 'ready', evidence: '8/8', questions: 9, pic: 'MF' }] },
  c3: { title: 'C.3 Relevansi Pendidikan, Penelitian, dan PkM', readiness: 87, status: 'REVIEW', indicators: [{ name: 'Profil Lulusan', status: 'ready', evidence: '5/5', questions: 6, pic: 'Tim Kurikulum' }, { name: 'Kesesuaian CPL', status: 'ready', evidence: '8/8', questions: 9, pic: 'Tim Kurikulum' }, { name: 'Tinjauan CPL', status: 'review', evidence: '6/7', questions: 8, pic: 'Tim Kurikulum' }, { name: 'Capstone Project', status: 'review', evidence: '4/5', questions: 7, pic: 'VF' }] },
  c4: { title: 'C.4 Sumber Daya Manusia', readiness: 97, status: 'READY', indicators: [{ name: 'Profil DTPS', status: 'ready', evidence: '10/10', questions: 8, pic: 'DW' }, { name: 'Kinerja DTPS', status: 'ready', evidence: '15/15', questions: 12, pic: 'VF' }] },
  c5: { title: 'C.5 Sarana, Prasarana, dan K3L', readiness: 93, status: 'READY', indicators: [{ name: 'Sarana & Prasarana', status: 'ready', evidence: '8/8', questions: 7, pic: 'Z' }, { name: 'Dokumen K3L', status: 'review', evidence: '3/4', questions: 5, pic: 'Z' }] },
  c6: { title: 'C.6 Mahasiswa dan Luaran Mahasiswa', readiness: 86, status: 'REVIEW', indicators: [{ name: 'Tracer Study', status: 'review', evidence: '5/7', questions: 10, pic: 'MF + DW' }, { name: 'Prestasi Mahasiswa', status: 'ready', evidence: '8/8', questions: 6, pic: 'MF' }] },
  c7: { title: 'C.7 Sistem Penjaminan Mutu', readiness: 83, status: 'REVIEW', indicators: [{ name: 'Siklus PPEPP', status: 'review', evidence: '5/7', questions: 9, pic: 'BU + SH' }, { name: 'Kepuasan Stakeholder', status: 'review', evidence: '3/5', questions: 7, pic: 'BU' }] }
};

const dataBukti = [
  { code: 'C1-VMTS-001', name: 'SK VMTS PT & UPPS', path: 'C.1 → VMTS → Kekhasan', status: 'verified' },
  { code: 'C3-CPL-001', name: 'NADK PSBM 2020', path: 'C.3 → Pendidikan → CPL', status: 'verified' },
  { code: 'C3-CPL-002', name: 'Workshop OBE 2024', path: 'C.3 → Pendidikan → Tinjauan CPL', status: 'verified' },
  { code: 'C3-CPL-003', name: 'Tindak Lanjut Evaluasi CPL', path: 'C.3 → Pendidikan → Tinjauan CPL', status: 'review' },
  { code: 'C4-SDM-001', name: 'Ijazah & Sertifikat DTPS', path: 'C.4 → SDM → Profil', status: 'verified' },
  { code: 'C5-K3L-001', name: 'SOP K3L Laboratorium', path: 'C.5 → K3L → Dokumen', status: 'review' },
  { code: 'C6-TRACER-001', name: 'Laporan Tracer Study 2024', path: 'C.6 → Luaran → Tracer', status: 'verified' },
  { code: 'C7-AMI-001', name: 'Laporan AMI 2025', path: 'C.7 → SPMI → Audit', status: 'verified' }
];

const dataPertanyaan = [
  { code: 'Q01', text: 'Bagaimana PSBM mengukur ketercapaian CPL?', kriteria: 'C.3', type: 'critical', pic: 'Kurikulum' },
  { code: 'Q02', text: 'Bagaimana hasil tracer study digunakan untuk memperbaiki kurikulum?', kriteria: 'C.3/C.6', type: 'ppepp', pic: 'Kurikulum' },
  { code: 'Q03', text: 'Bagaimana PSBM memastikan CPL tetap relevan terhadap kebutuhan industri?', kriteria: 'C.3', type: 'critical', pic: 'Kurikulum' },
  { code: 'Q04', text: 'Sebutkan 3 penelitian DTPS yang melibatkan mahasiswa dan luarannya.', kriteria: 'C.3/C.4', type: 'data', pic: 'VF + DW' },
  { code: 'Q05', text: 'Bagaimana mekanisme tinjauan rutin RPS?', kriteria: 'C.3', type: 'ppepp', pic: 'VF' },
  { code: 'Q06', text: 'Apa tindak lanjut dari temuan AMI 2025?', kriteria: 'C.7', type: 'ppepp', pic: 'BU' },
  { code: 'Q07', text: 'Berapa response rate tracer study 2024?', kriteria: 'C.6', type: 'data', pic: 'MF' },
  { code: 'Q08', text: 'Bagaimana implementasi K3L di laboratorium?', kriteria: 'C.5', type: 'critical', pic: 'Z' }
];

const dataPPEPP = {
  kurikulum: { steps: [{ t: 'PENETAPAN', c: 'Kurikulum KKNI Level 6 + OBE 2020' }, { t: 'PELAKSANAAN', c: 'Pembelajaran semester berjalan' }, { t: 'EVALUASI', c: 'Tracer study + User survey + Workshop kurikulum' }, { t: 'PENGENDALIAN', c: 'Analisis kesenjangan CPL vs kebutuhan industri' }, { t: 'PENINGKATAN', c: 'Revisi Kurikulum OBE 2025' }] },
  cpl: { steps: [{ t: 'PENETAPAN', c: 'NADK PSBM 2020 — 12 CPL' }, { t: 'PELAKSANAAN', c: 'Pembelajaran berbasis CPL di setiap RPS' }, { t: 'EVALUASI', c: 'Tracer + User Survey + Workshop OBE 2024' }, { t: 'PENGENDALIAN', c: 'Analisis kesenjangan kompetensi' }, { t: 'PENINGKATAN', c: 'Pengembangan Kurikulum OBE 2025' }] },
  tracer: { steps: [{ t: 'PENETAPAN', c: 'SK Pelaksanaan Tracer Study tahunan' }, { t: 'PELAKSANAAN', c: 'Kuesioner DIKTI + follow-up lulusan' }, { t: 'EVALUASI', c: 'Response rate 2024: 68%' }, { t: 'PENGENDALIAN', c: 'Identifikasi lulusan belum terisi' }, { t: 'PENINGKATAN', c: 'Kolaborasi career center + insentif alumni' }] },
  ami: { steps: [{ t: 'PENETAPAN', c: 'SK Audit Mutu Internal 2025' }, { t: 'PELAKSANAAN', c: 'Audit 7 kriteria + wawancara' }, { t: 'EVALUASI', c: 'Laporan temuan AMI Oktober 2025' }, { t: 'PENGENDALIAN', c: 'Rapat Tinjauan Manajemen (RTM)' }, { t: 'PENINGKATAN', c: 'Rencana tindak lanjut 15 temuan' }] }
};

const dataChecklist = {
  h30: { title: 'H-30', items: [{ text: 'Freeze baseline SAKTI', done: true }, { text: 'Data Master diverifikasi', done: true }, { text: 'Identifikasi PIC per kriteria', done: true }, { text: 'Struktur Evidence folder final', done: true }, { text: 'Link Google Drive semua publik', done: false }] },
  h21: { title: 'H-21', items: [{ text: 'Evidence verification selesai', done: true }, { text: 'Mock AL I dilaksanakan', done: false }, { text: 'Critical questions dijawab', done: false }] },
  h14: { title: 'H-14', items: [{ text: 'Mock AL II dilaksanakan', done: false }, { text: 'Stakeholder simulation', done: false }, { text: 'Link audit semua bukti', done: false }] },
  h7: { title: 'H-7', items: [{ text: 'Full simulation AL', done: false }, { text: 'Backup evidence lokal & cloud', done: false }, { text: 'Freeze konten LED & LKPS', done: false }] },
  h1: { title: 'H-1', items: [{ text: 'Cek final semua link', done: false }, { text: 'Siapkan ruang AL', done: false }, { text: 'Briefing tim terakhir', done: false }] }
};

function showPanel(id, btn) {
  document.querySelectorAll('.al-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.folder-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  if (id === 'kriteria') showKriteria('c1', document.querySelector('#kriteriaSubNav button'));
  if (id === 'bukti') renderBukti();
  if (id === 'pertanyaan') renderPertanyaan();
  if (id === 'ppepp') showPPEPP('kurikulum', document.querySelector('#panel-ppepp .sub-nav button'));
  if (id === 'checklist') showChecklist('h30', document.querySelector('#panel-checklist .sub-nav button'));
}

function showKriteria(key, btn) {
  document.querySelectorAll('#kriteriaSubNav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  const k = dataKriteria[key] || { title: key.toUpperCase(), readiness: 90, status: 'READY', indicators: [] };
  let html = `<h3 style="color:#0a1929; margin-top:0; font-weight:700;">${k.title}</h3>`;
  html += `<div class="progress-row"><div class="bar" style="height:14px;"><div class="bar-fill ${k.status==='REVIEW'?'review':''}" style="width:${k.readiness}%;"></div></div><div class="percent">${k.readiness}%</div><div class="status status-${k.status.toLowerCase()}">${k.status}</div></div>`;
  k.indicators.forEach(ind => {
    html += `<div class="indicator-card ${ind.status}"><div class="head"><div class="title">${ind.name}</div><div class="status status-${ind.status==='ready'?'ready':'review'}">${ind.status==='ready'?'✓ SIAP':'⚠ REVIEW'}</div></div><div class="meta">PIC: ${ind.pic} • Evidence: ${ind.evidence} • Questions: ${ind.questions}</div><div class="actions"><button class="btn btn-primary">Detail</button><button class="btn btn-outline">Bukti</button></div></div>`;
  });
  document.getElementById('kriteriaContent').innerHTML = html;
}

function renderBukti() {
  const search = (document.getElementById('buktiSearch')?.value || '').toLowerCase();
  const filtered = dataBukti.filter(b => !search || b.name.toLowerCase().includes(search) || b.code.toLowerCase().includes(search));
  let html = '';
  filtered.forEach(b => {
    html += `<div class="evidence-item ${b.status}"><div class="code">${b.code}</div><div style="font-weight:600; margin:6px 0; color:#0a1929;">${b.name}</div><div class="path">${b.path}</div><div style="margin-top:10px;"><span class="risk-badge risk-${b.status==='verified'?'resolved':'medium'}">${b.status.toUpperCase()}</span></div></div>`;
  });
  document.getElementById('buktiList').innerHTML = html || '<p style="text-align:center; color:#64748b; padding:20px;">Tidak ada bukti ditemukan</p>';
}
function filterBukti() { renderBukti(); }

function renderPertanyaan(filter = 'all') {
  const filtered = dataPertanyaan.filter(p => filter === 'all' || p.type === filter);
  let html = '';
  filtered.forEach(p => {
    html += `<div class="question-card ${p.type==='critical'?'critical':''}"><div class="q-code">${p.code} • ${p.kriteria}</div><div class="q-text">${p.text}</div><div class="q-meta" style="color:#64748b;">PIC: ${p.pic}</div><div style="margin-top:12px;"><button class="btn btn-primary">LIHAT JAWABAN</button></div></div>`;
  });
  document.getElementById('pertanyaanList').innerHTML = html;
}
function filterPertanyaan(type, btn) {
  document.querySelectorAll('#panel-pertanyaan .sub-nav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  renderPertanyaan(type);
}

function startMock() {
  document.getElementById('mockSetup').style.display = 'none';
  const session = document.getElementById('mockSession');
  session.style.display = 'block';
  session.innerHTML = `<div style="text-align:center; padding:40px; background:linear-gradient(135deg, #f0fdf4 0%, #dcfce7 100%); border-radius:12px; border:1px solid #86efac;"><h2 style="color:#166534; margin-top:0;">✅ Mock AL Selesai!</h2><div style="font-size:2.5rem; font-weight:700; color:#0a1929; margin:16px 0;">3.4 <span style="font-size:1.2rem; color:#64748b;">/ 4.0</span></div><button class="btn btn-primary" style="padding:10px 24px;" onclick="document.getElementById('mockSetup').style.display='block'; document.getElementById('mockSession').style.display='none';">Kembali</button></div>`;
}

function showPPEPP(key, btn) {
  document.querySelectorAll('#panel-ppepp .sub-nav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  const data = dataPPEPP[key];
  let html = `<h3 style="color:#0a1929; margin-top:0; font-weight:700;">${key.toUpperCase()} — Closed Loop</h3>`;
  data.steps.forEach(s => { html += `<div class="ppepp-step"><div class="step-title">${s.t}</div><div class="step-content">${s.c}</div></div>`; });
  document.getElementById('ppeppContent').innerHTML = html;
}

function showChecklist(key, btn) {
  document.querySelectorAll('#panel-checklist .sub-nav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  const data = dataChecklist[key];
  let html = `<div class="checklist-group"><h4>${data.title}</h4>`;
  data.items.forEach((item, i) => {
    html += `<div class="checklist-item ${item.done?'done':''}"><input type="checkbox" id="cl-${key}-${i}" ${item.done?'checked':''} onchange="this.parentElement.classList.toggle('done', this.checked)"><label for="cl-${key}-${i}" style="color:#334155; cursor:pointer;">${item.text}</label></div>`;
  });
  html += '</div>';
  document.getElementById('checklistContent').innerHTML = html;
}

document.addEventListener('DOMContentLoaded', () => {
  showKriteria('c1', document.querySelector('#kriteriaSubNav button'));
  renderBukti();
  renderPertanyaan();
  showPPEPP('kurikulum', document.querySelector('#panel-ppepp .sub-nav button'));
  showChecklist('h30', document.querySelector('#panel-checklist .sub-nav button'));
});
</script>

---
layout: default
title: Persiapan AL
permalink: /persiapan-al/
---

<style>
  /* ===== Elegant Cabinet & Folder Styles ===== */
  .al-header { 
    background: linear-gradient(135deg, #0d47a1 0%, #1976d2 100%); 
    color: white; 
    padding: 24px; 
    border-radius: 16px 16px 0 0; 
    box-shadow: 0 4px 20px rgba(13, 71, 161, 0.2); 
  }
  .al-header h1 { margin: 0; font-size: 1.6rem; letter-spacing: -0.5px; }
  .al-header .subtitle { opacity: 0.9; font-size: 0.95rem; margin-top: 4px; font-weight: 400; }
  .al-header .h-countdown { 
    display: inline-block; 
    background: rgba(255, 255, 255, 0.2); 
    backdrop-filter: blur(4px);
    padding: 6px 14px; 
    border-radius: 20px; 
    font-weight: 600; 
    margin-top: 8px; 
    font-size: 0.85rem; 
    border: 1px solid rgba(255,255,255,0.3);
  }

  /* Premium Dark Slate Cabinet Background */
  .cabinet-container {
    background: linear-gradient(180deg, #1e293b 0%, #0f172a 100%);
    padding: 24px 24px 0 24px;
    border-radius: 16px 16px 16px 16px; /* Sudut atas membulat karena header dihapus */
    box-shadow: inset 0 10px 20px rgba(0,0,0,0.2), 0 12px 32px rgba(0,0,0,0.15);
    position: relative;
  }

  /* ===== Folder Shelf - Sebaris di Desktop ===== */
  .folder-shelf {
    display: flex;
    flex-wrap: nowrap;
    gap: 6px;
    padding: 0 12px;
    position: relative;
    z-index: 10;
    overflow-x: auto;
    overflow-y: hidden;
    scrollbar-width: thin;
    scrollbar-color: #94a3b8 transparent;
    padding-bottom: 8px;
  }

  .folder-shelf::-webkit-scrollbar { height: 6px; }
  .folder-shelf::-webkit-scrollbar-track { background: rgba(255,255,255,0.05); border-radius: 3px; }
  .folder-shelf::-webkit-scrollbar-thumb { background: #94a3b8; border-radius: 3px; }
  .folder-shelf::-webkit-scrollbar-thumb:hover { background: #cbd5e1; }

  /* ===== Folder Tab - Default (Mobile) ===== */
  .folder-tab {
    position: relative;
    flex: 0 0 auto;
    min-width: 110px;
    padding: 14px 16px 18px 16px;
    background: #e2e8f0;
    border-radius: 10px 10px 0 0;
    border: 1px solid transparent;
    border-bottom: none;
    cursor: pointer;
    text-align: center;
    font-weight: 500;
    font-size: 0.85rem;
    color: #475569;
    transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
    transform: translateY(6px);
    box-shadow: 0 -2px 8px rgba(0,0,0,0.05);
    white-space: nowrap;
  }

  .folder-tab::before {
    content: '';
    position: absolute;
    top: -6px;
    left: 20%;
    width: 60%;
    height: 6px;
    background: #cbd5e1;
    border-radius: 6px 6px 0 0;
    transition: all 0.35s ease;
  }

  .folder-tab:hover {
    background: #f1f5f9;
    transform: translateY(2px);
    color: #0d47a1;
  }
  .folder-tab:hover::before {
    background: #f1f5f9;
  }

  /* Active Folder - Premium Rich Blue */
  .folder-tab.active {
    background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
    color: #ffffff;
    transform: translateY(-6px);
    z-index: 20;
    box-shadow: 0 -4px 16px rgba(13, 71, 161, 0.4);
    font-weight: 600;
    border: 1px solid rgba(255,255,255,0.1);
  }
  .folder-tab.active::before {
    background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
    height: 8px;
    top: -8px;
  }

  /* ===== ✨ DESKTOP: Semua Folder Berbagi Ruang Sama Rata ===== */
  @media (min-width: 1200px) {
    .folder-shelf {
      flex-wrap: nowrap;
      overflow-x: visible;
      padding-bottom: 0;
    }
    
    .folder-tab {
      flex: 1 1 0;
      min-width: 0;
      padding: 14px 8px 18px 8px;
      font-size: 0.82rem;
      white-space: normal;
    }
    
    .folder-tab::before {
      left: 25%;
      width: 50%;
    }
  }

  /* ===== TABLET: 5 Folder per Baris ===== */
  @media (min-width: 768px) and (max-width: 1199px) {
    .folder-shelf {
      flex-wrap: wrap;
      overflow-x: visible;
      padding-bottom: 0;
    }
    
    .folder-tab {
      flex: 0 1 calc(20% - 6px);
      min-width: 0;
      font-size: 0.82rem;
      white-space: normal;
    }
  }

  /* Content Area (Drawer) */
  .al-content {
    background: #ffffff;
    border: 1px solid #e2e8f0;
    border-top: 3px solid #0d47a1;
    border-radius: 0 0 16px 16px;
    padding: 28px;
    min-height: 500px;
    box-shadow: 0 8px 24px rgba(0,0,0,0.06);
    position: relative;
    z-index: 5;
    margin-top: -1px;
  }

  .al-panel { display: none; animation: fadeIn 0.4s cubic-bezier(0.4, 0, 0.2, 1); }
  .al-panel.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: translateY(0); } }

  /* ===== Internal Components ===== */
  .card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 16px; margin: 16px 0; }
  .stat-card { background: #f8fafc; border-radius: 12px; padding: 18px; box-shadow: 0 2px 8px rgba(0,0,0,0.04); border-left: 4px solid #0d47a1; transition: transform 0.2s; }
  .stat-card:hover { transform: translateY(-2px); }
  .stat-card .label { font-size: 0.85rem; color: #64748b; margin-bottom: 6px; font-weight: 500; }
  .stat-card .value { font-size: 1.8rem; font-weight: 700; color: #0f172a; }
  
  .progress-row { display: flex; align-items: center; gap: 12px; padding: 10px 0; border-bottom: 1px solid #f1f5f9; }
  .progress-row .label { width: 60px; font-weight: 600; color: #334155; font-size: 0.9rem; }
  .progress-row .bar { flex: 1; height: 12px; background: #e2e8f0; border-radius: 6px; overflow: hidden; }
  .progress-row .bar-fill { height: 100%; background: linear-gradient(90deg, #10b981 0%, #34d399 100%); border-radius: 6px; transition: width 0.8s cubic-bezier(0.4, 0, 0.2, 1); }
  .progress-row .bar-fill.review { background: linear-gradient(90deg, #f59e0b 0%, #fbbf24 100%); }
  .progress-row .percent { width: 40px; font-weight: 700; text-align: right; color: #0f172a; }
  .progress-row .status { width: 80px; text-align: center; font-size: 0.7rem; font-weight: 700; padding: 4px 8px; border-radius: 12px; text-transform: uppercase; letter-spacing: 0.5px; }
  .status-ready { background: #dcfce7; color: #15803d; }
  .status-review { background: #fef3c7; color: #b45309; }
  
  .alert-box { background: #fffbeb; border-left: 4px solid #f59e0b; padding: 16px 18px; border-radius: 8px; margin: 20px 0; }
  .alert-box .item { padding: 4px 0; font-size: 0.9rem; color: #78350f; }
  
  .sub-nav { display: flex; gap: 4px; margin-bottom: 20px; border-bottom: 2px solid #e2e8f0; flex-wrap: wrap; }
  .sub-nav button { padding: 10px 16px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #64748b; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.9rem; }
  .sub-nav button:hover { color: #0d47a1; background: #f8fafc; border-radius: 6px 6px 0 0; }
  .sub-nav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }
  
  .indicator-card { background: white; border-radius: 10px; padding: 16px; margin-bottom: 12px; box-shadow: 0 2px 8px rgba(0,0,0,0.04); border-left: 4px solid #10b981; transition: box-shadow 0.2s; }
  .indicator-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
  .indicator-card.review { border-left-color: #f59e0b; }
  .indicator-card .head { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
  .indicator-card .title { font-weight: 700; color: #0f172a; }
  .indicator-card .meta { font-size: 0.85rem; color: #64748b; margin: 4px 0; }
  
  .btn { padding: 8px 14px; border-radius: 8px; border: none; cursor: pointer; font-size: 0.85rem; font-weight: 600; transition: all 0.2s; }
  .btn-primary { background: #0d47a1; color: white; }
  .btn-primary:hover { background: #1565c0; box-shadow: 0 4px 12px rgba(13, 71, 161, 0.3); }
  .btn-outline { background: white; color: #0d47a1; border: 1px solid #cbd5e1; }
  .btn-outline:hover { background: #f1f5f9; border-color: #0d47a1; }
  
  .search-box { width: 100%; padding: 12px 16px; border: 2px solid #e2e8f0; border-radius: 10px; font-size: 0.95rem; margin-bottom: 16px; transition: border-color 0.2s; }
  .search-box:focus { outline: none; border-color: #0d47a1; background: #f8fafc; }
  
  .evidence-item { background: white; padding: 14px; border-radius: 10px; margin-bottom: 8px; border-left: 4px solid #10b981; box-shadow: 0 1px 4px rgba(0,0,0,0.04); }
  .evidence-item.review { border-left-color: #f59e0b; }
  .evidence-item .code { font-family: 'Courier New', monospace; color: #0d47a1; font-weight: 700; font-size: 0.85rem; background: #f1f5f9; padding: 2px 6px; border-radius: 4px; }
  .evidence-item .path { font-size: 0.8rem; color: #64748b; margin-top: 4px; }
  
  .question-card { background: white; padding: 16px; border-radius: 10px; margin-bottom: 12px; box-shadow: 0 2px 8px rgba(0,0,0,0.04); border-left: 4px solid #0d47a1; }
  .question-card.critical { border-left-color: #ef4444; }
  .question-card .q-code { font-family: 'Courier New', monospace; color: #ef4444; font-weight: 700; font-size: 0.8rem; }
  .question-card .q-text { font-size: 1rem; font-weight: 600; margin: 6px 0; color: #0f172a; }
  
  .ppepp-step { background: white; padding: 16px 20px; border-left: 4px solid #0d47a1; position: relative; box-shadow: 0 2px 8px rgba(0,0,0,0.04); margin-bottom: 8px; border-radius: 0 8px 8px 0; }
  .ppepp-step::after { content: '▼'; position: absolute; bottom: -14px; left: 50%; transform: translateX(-50%); color: #cbd5e1; font-size: 1rem; }
  .ppepp-step:last-child::after { display: none; }
  .ppepp-step .step-title { font-weight: 700; color: #0d47a1; margin-bottom: 4px; font-size: 0.9rem; }
  .ppepp-step .step-content { color: #475569; font-size: 0.9rem; }
  
  .risk-table { width: 100%; border-collapse: separate; border-spacing: 0; margin-top: 12px; }
  .risk-table th, .risk-table td { padding: 12px; text-align: left; border-bottom: 1px solid #f1f5f9; font-size: 0.9rem; }
  .risk-table th { background: #f8fafc; color: #334155; font-weight: 600; }
  .risk-table tr:hover td { background: #f8fafc; }
  .risk-badge { display: inline-block; padding: 4px 10px; border-radius: 12px; font-size: 0.75rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.5px; }
  .risk-critical { background: #fee2e2; color: #b91c1c; }
  .risk-high { background: #ffedd5; color: #c2410c; }
  .risk-medium { background: #fef3c7; color: #b45309; }
  
  .team-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 16px; }
  .team-card { background: white; padding: 18px; border-radius: 12px; box-shadow: 0 2px 8px rgba(0,0,0,0.04); border-top: 4px solid #0d47a1; transition: transform 0.2s; }
  .team-card:hover { transform: translateY(-2px); box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
  .team-card .role { font-size: 0.8rem; color: #64748b; text-transform: uppercase; letter-spacing: 0.5px; font-weight: 600; }
  .team-card .name { font-size: 1.1rem; font-weight: 700; color: #0f172a; margin: 6px 0; }
  
  .checklist-group { background: white; padding: 20px; border-radius: 12px; margin-bottom: 16px; box-shadow: 0 2px 8px rgba(0,0,0,0.04); }
  .checklist-group h4 { color: #0f172a; margin: 0 0 16px 0; font-size: 1.1rem; }
  .checklist-item { display: flex; align-items: center; gap: 12px; padding: 10px 0; border-bottom: 1px solid #f1f5f9; }
  .checklist-item input[type="checkbox"] { width: 18px; height: 18px; cursor: pointer; accent-color: #0d47a1; }
  .checklist-item.done label { text-decoration: line-through; color: #94a3b8; }
  
  .mode-al-view { background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%); color: white; padding: 40px 30px; border-radius: 16px; text-align: center; }
  .mode-al-view .search-big { width: 100%; max-width: 600px; padding: 16px 24px; border-radius: 30px; border: 1px solid rgba(255,255,255,0.1); background: rgba(255,255,255,0.05); color: white; font-size: 1rem; margin: 20px 0; backdrop-filter: blur(4px); }
  .mode-al-view .search-big::placeholder { color: rgba(255,255,255,0.5); }
  .mode-al-view .search-big:focus { outline: none; border-color: #3b82f6; background: rgba(255,255,255,0.1); }
  .quick-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 12px; margin-top: 24px; max-width: 800px; margin-left: auto; margin-right: auto; }
  .quick-btn { background: rgba(255,255,255,0.08); color: white; padding: 16px; border-radius: 10px; border: 1px solid rgba(255,255,255,0.1); cursor: pointer; font-weight: 500; transition: all 0.2s; font-size: 0.9rem; }
  .quick-btn:hover { background: rgba(255,255,255,0.15); border-color: rgba(255,255,255,0.3); transform: translateY(-2px); }

  @media (max-width: 767px) {
    .folder-shelf { overflow-x: auto; flex-wrap: nowrap; padding-bottom: 8px; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
    .folder-shelf::-webkit-scrollbar { display: none; }
    .folder-tab { min-width: 110px; flex: 0 0 auto; font-size: 0.8rem; padding: 12px 10px 16px 10px; }
    .progress-row { flex-wrap: wrap; }
    .progress-row .label { width: 100%; margin-bottom: 4px; }
    .al-content { padding: 20px; }
  }
</style>

<!-- ===== KABINET FOLDER NAV (LANGSUNG TANPA HEADER) ===== -->
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
      <h2 style="color:#0f172a; margin-top:0; font-size:1.3rem;">Overall Readiness</h2>
      <div class="progress-row"><div class="bar" style="height:16px;"><div class="bar-fill" style="width:89%;"></div></div><div class="percent" style="font-size:1.1rem;">89%</div></div>
      <div class="card-grid">
        <div class="stat-card"><div class="label">Evidence</div><div class="value">142/150</div><div class="sub" style="color:#64748b; font-size:0.85rem;">95% verified</div></div>
        <div class="stat-card"><div class="label">Questions</div><div class="value">126/140</div><div class="sub" style="color:#64748b; font-size:0.85rem;">90% ready</div></div>
        <div class="stat-card" style="border-left-color:#ef4444;"><div class="label">Open Risk</div><div class="value" style="color:#ef4444;">6</div><div class="sub" style="color:#64748b; font-size:0.85rem;">2 critical</div></div>
        <div class="stat-card" style="border-left-color:#10b981;"><div class="label">Mock Score</div><div class="value" style="color:#10b981;">3.4</div><div class="sub" style="color:#64748b; font-size:0.85rem;">/4.0 average</div></div>
      </div>
      <h3 style="color:#0f172a; margin-top:28px; font-size:1.1rem;">Kesiapan Per Kriteria</h3>
      <div class="progress-row"><div class="label">C.1</div><div class="bar"><div class="bar-fill" style="width:96%;"></div></div><div class="percent">96%</div><div class="status status-ready">READY</div></div>
      <div class="progress-row"><div class="label">C.2</div><div class="bar"><div class="bar-fill" style="width:92%;"></div></div><div class="percent">92%</div><div class="status status-ready">READY</div></div>
      <div class="progress-row"><div class="label">C.3</div><div class="bar"><div class="bar-fill review" style="width:87%;"></div></div><div class="percent">87%</div><div class="status status-review">REVIEW</div></div>
      <div class="progress-row"><div class="label">C.4</div><div class="bar"><div class="bar-fill" style="width:97%;"></div></div><div class="percent">97%</div><div class="status status-ready">READY</div></div>
      <div class="progress-row"><div class="label">C.5</div><div class="bar"><div class="bar-fill" style="width:93%;"></div></div><div class="percent">93%</div><div class="status status-ready">READY</div></div>
      <div class="progress-row"><div class="label">C.6</div><div class="bar"><div class="bar-fill review" style="width:86%;"></div></div><div class="percent">86%</div><div class="status status-review">REVIEW</div></div>
      <div class="progress-row"><div class="label">C.7</div><div class="bar"><div class="bar-fill review" style="width:83%;"></div></div><div class="percent">83%</div><div class="status status-review">REVIEW</div></div>
      <div class="alert-box">
        <h4 style="margin:0 0 8px 0; color:#b45309; font-size:0.95rem;">⚠️ Perlu Perhatian</h4>
        <div class="item">🔴 <strong>2 Critical Risk</strong> — bukti CPL & link evidence</div>
        <div class="item">🟠 <strong>4 Evidence</strong> belum verified</div>
        <div class="item">🟡 <strong>3 PIC</strong> Mock AL score &lt; 3</div>
      </div>
    </div>

    <!-- KRITERIA -->
    <div class="al-panel" id="panel-kriteria">
      <h2 style="color:#0f172a; margin-top:0; font-size:1.3rem;">Kriteria Akreditasi</h2>
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
      <h2 style="color:#0f172a; margin-top:0; font-size:1.3rem;">🔍 Bukti Asesmen Lapangan</h2>
      <input type="text" class="search-box" id="buktiSearch" placeholder="Cari bukti: CPL, RPS, tracer, penelitian..." oninput="filterBukti()">
      <div class="card-grid">
        <div class="stat-card" style="border-left-color:#10b981;"><div class="label">Total Evidence</div><div class="value" style="color:#10b981;">157</div></div>
        <div class="stat-card" style="border-left-color:#3b82f6;"><div class="label">Verified</div><div class="value" style="color:#3b82f6;">148</div></div>
        <div class="stat-card" style="border-left-color:#f59e0b;"><div class="label">Review</div><div class="value" style="color:#f59e0b;">6</div></div>
        <div class="stat-card" style="border-left-color:#ef4444;"><div class="label">Missing</div><div class="value" style="color:#ef4444;">3</div></div>
      </div>
      <div id="buktiList"></div>
    </div>

    <!-- PERTANYAAN -->
    <div class="al-panel" id="panel-pertanyaan">
      <h2 style="color:#0f172a; margin-top:0; font-size:1.3rem;">🔥 Bank Pertanyaan Asesor</h2>
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
      <h2 style="color:#0f172a; margin-top:0; font-size:1.3rem;">🎭 Simulasi Asesmen Lapangan</h2>
      <div id="mockSetup">
        <div class="card-grid">
          <div class="stat-card"><div class="label">Pilih Kriteria</div><select style="width:100%; padding:10px; margin-top:8px; border-radius:8px; border:1px solid #cbd5e1; background:white;"><option>Semua Kriteria</option><option selected>C.3 Relevansi</option></select></div>
          <div class="stat-card"><div class="label">Mode Asesor</div><select style="width:100%; padding:10px; margin-top:8px; border-radius:8px; border:1px solid #cbd5e1; background:white;"><option>Normal</option><option selected>🔥 Kritis</option></select></div>
          <div class="stat-card"><div class="label">Jumlah Pertanyaan</div><div style="margin-top:8px; display:flex; gap:6px;"><button class="btn btn-outline">10</button><button class="btn btn-primary">20</button><button class="btn btn-outline">30</button></div></div>
        </div>
        <div style="text-align:center; margin-top:28px;"><button class="btn btn-primary" style="padding:14px 40px; font-size:1rem; border-radius:10px;" onclick="startMock()">🚀 MULAI MOCK AL</button></div>
      </div>
      <div id="mockSession" style="display:none;"></div>
    </div>

    <!-- PPEPP -->
    <div class="al-panel" id="panel-ppepp">
      <h2 style="color:#0f172a; margin-top:0; font-size:1.3rem;">🔄 PPEPP Closed-Loop Improvement</h2>
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
      <h2 style="color:#0f172a; margin-top:0; font-size:1.3rem;">⚠️ Risk & Clarification Register</h2>
      <div class="card-grid">
        <div class="stat-card" style="border-left-color:#ef4444;"><div class="label">🔴 Critical</div><div class="value" style="color:#ef4444;">2</div></div>
        <div class="stat-card" style="border-left-color:#f59e0b;"><div class="label">🟠 High</div><div class="value" style="color:#f59e0b;">4</div></div>
        <div class="stat-card" style="border-left-color:#eab308;"><div class="label">🟡 Medium</div><div class="value" style="color:#b45309;">7</div></div>
        <div class="stat-card" style="border-left-color:#10b981;"><div class="label">🟢 Resolved</div><div class="value" style="color:#10b981;">28</div></div>
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
      <h2 style="color:#0f172a; margin-top:0; font-size:1.3rem;">👥 Tim Asesmen Lapangan</h2>
      <div class="team-grid">
        <div class="team-card"><div class="role">KETUA TIM</div><div class="name">AW</div><div class="stat" style="color:#475569; font-size:0.9rem;">Overall AL Readiness: <strong style="color:#0f172a;">94%</strong></div></div>
        <div class="team-card"><div class="role">PIC C.1 VMTS</div><div class="name">AW + SH</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0f172a;">12/12</strong></div></div>
        <div class="team-card" style="border-top-color:#f59e0b;"><div class="role">PIC C.3 Relevansi</div><div class="name">VF + BU</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0f172a;">18/20</strong><br>Mock Score: <strong style="color:#b45309;">3.2</strong> ⚠️</div></div>
        <div class="team-card"><div class="role">PIC C.4 SDM</div><div class="name">DW + VF</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0f172a;">20/20</strong></div></div>
        <div class="team-card"><div class="role">PIC C.5 Sarpras & K3L</div><div class="name">Z + MF</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0f172a;">14/16</strong></div></div>
        <div class="team-card" style="border-top-color:#f59e0b;"><div class="role">PIC C.6 Mahasiswa</div><div class="name">MF + DW</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0f172a;">21/24</strong><br>Mock Score: <strong style="color:#b45309;">2.9</strong> ⚠️</div></div>
        <div class="team-card" style="border-top-color:#f59e0b;"><div class="role">PIC C.7 SPMI</div><div class="name">BU + SH</div><div class="stat" style="color:#475569; font-size:0.9rem;">Questions: <strong style="color:#0f172a;">16/18</strong><br>Mock Score: <strong style="color:#b45309;">2.8</strong> ⚠️</div></div>
      </div>
    </div>

    <!-- CHECKLIST -->
    <div class="al-panel" id="panel-checklist">
      <h2 style="color:#0f172a; margin-top:0; font-size:1.3rem;">✅ Checklist Menuju AL</h2>
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
        <p style="opacity:0.7; font-size:0.95rem;">Mode Presentasi • Semua data internal disembunyikan</p>
        <input type="text" class="search-big" placeholder="🔍 Cari bukti: CPL / RPS / tracer / penelitian...">
        <div style="margin:20px 0; display:flex; gap:8px; justify-content:center; flex-wrap:wrap;">
          <button class="quick-btn">C.1</button><button class="quick-btn">C.2</button><button class="quick-btn">C.3</button><button class="quick-btn">C.4</button>
          <button class="quick-btn">C.5</button><button class="quick-btn">C.6</button><button class="quick-btn">C.7</button>
        </div>
        <h3 style="margin-top:32px; text-align:left; font-size:1.1rem;">⚡ QUICK EVIDENCE</h3>
        <div class="quick-grid">
          <button class="quick-btn">📄 LED</button><button class="quick-btn">📊 LKPS</button><button class="quick-btn">🎯 VMTS</button><button class="quick-btn">📘 Kurikulum</button>
          <button class="quick-btn">🎓 CPL</button><button class="quick-btn">📝 RPS</button><button class="quick-btn">🔬 Penelitian</button><button class="quick-btn">🤝 PkM</button>
          <button class="quick-btn">📈 Tracer</button><button class="quick-btn">👨‍🏫 DTPS</button><button class="quick-btn">🔍 AMI</button><button class="quick-btn">🔄 PPEPP</button>
        </div>
        <div style="margin-top:32px; padding:16px; background:rgba(255,255,255,0.05); border-radius:10px; border:1px solid rgba(255,255,255,0.1);">
          <strong style="color:#93c5fd;">💡 Catatan:</strong> <span style="color:#cbd5e1; font-size:0.9rem;">Risk register, skor kesiapan, missing evidence, dan catatan internal <strong style="color:#ffffff;">TIDAK</strong> tampil di mode ini.</span>
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
  let html = `<h3 style="color:#0f172a; margin-top:0;">${k.title}</h3>`;
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
    html += `<div class="evidence-item ${b.status}"><div class="code">${b.code}</div><div style="font-weight:600; margin:6px 0; color:#0f172a;">${b.name}</div><div class="path">${b.path}</div><div style="margin-top:10px;"><span class="risk-badge risk-${b.status==='verified'?'resolved':'medium'}">${b.status.toUpperCase()}</span></div></div>`;
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
  session.innerHTML = `<div style="text-align:center; padding:40px; background:#f0fdf4; border-radius:12px; border:1px solid #bbf7d0;"><h2 style="color:#15803d; margin-top:0;">✅ Mock AL Selesai!</h2><div style="font-size:2.5rem; font-weight:700; color:#0f172a; margin:16px 0;">3.4 <span style="font-size:1.2rem; color:#64748b;">/ 4.0</span></div><button class="btn btn-primary" style="padding:10px 24px;" onclick="document.getElementById('mockSetup').style.display='block'; document.getElementById('mockSession').style.display='none';">Kembali</button></div>`;
}

function showPPEPP(key, btn) {
  document.querySelectorAll('#panel-ppepp .sub-nav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  const data = dataPPEPP[key];
  let html = `<h3 style="color:#0f172a; margin-top:0;">${key.toUpperCase()} — Closed Loop</h3>`;
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

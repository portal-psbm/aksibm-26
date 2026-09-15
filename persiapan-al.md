---
layout: default
title: Persiapan AL
permalink: /persiapan-al/
---

<style>
  /* ===== Cabinet Container ===== */
  .cabinet-container {
    background: linear-gradient(180deg, #e3f2fd 0%, #bbdefb 100%);
    padding: 20px 20px 0 20px;
    border-radius: 16px 16px 0 0;
    box-shadow: inset 0 4px 12px rgba(13, 71, 161, 0.08), 0 4px 16px rgba(0,0,0,0.06);
    position: relative;
    border: 1px solid #bbdefb;
    border-bottom: none;
  }

  .folder-shelf {
    display: flex; flex-wrap: nowrap; gap: 8px; padding: 0 8px;
    position: relative; z-index: 10; overflow-x: auto; overflow-y: visible;
    scrollbar-width: thin; scrollbar-color: #0d47a1 transparent; padding-bottom: 4px;
  }
  .folder-shelf::-webkit-scrollbar { height: 4px; }
  .folder-shelf::-webkit-scrollbar-track { background: rgba(13, 71, 161, 0.05); border-radius: 2px; }
  .folder-shelf::-webkit-scrollbar-thumb { background: #0d47a1; border-radius: 2px; }

  .folder-tab {
    position: relative; flex: 1 1 0; min-width: 0;
    padding: 16px 10px 20px 10px; background: #ffffff;
    border-radius: 10px 10px 0 0; border: 1px solid #e0e0e0; border-bottom: none;
    cursor: pointer; text-align: center; font-weight: 600; font-size: 0.85rem;
    line-height: 1.2; color: #555;
    transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
    transform: translateY(4px); box-shadow: 0 -2px 6px rgba(0,0,0,0.05);
    white-space: normal; word-wrap: break-word; overflow-wrap: break-word;
  }
  .folder-tab::before {
    content: ''; position: absolute; top: -7px; left: 22%; width: 56%; height: 7px;
    background: #f5f5f5; border-radius: 4px 4px 0 0; border: 1px solid #e0e0e0;
    border-bottom: none; transition: all 0.35s ease;
  }
  .folder-tab:hover { background: #f1f5f9; transform: translateY(0px); color: #0d47a1; }
  .folder-tab:hover::before { background: #f1f5f9; }
  .folder-tab.active {
    background: #0d47a1; color: #ffffff; transform: translateY(-6px);
    z-index: 20; border-color: #0d47a1;
    box-shadow: 0 -4px 16px rgba(13, 71, 161, 0.25); font-weight: 700;
  }
  .folder-tab.active::before { background: #0d47a1; border-color: #0d47a1; height: 9px; top: -9px; }

  /* MODE AL - oranye lembut saat tidak aktif */
  .folder-tab.mode-al {
    background: linear-gradient(180deg, #fff8e1 0%, #ffecb3 100%);
    color: #e65100; border-color: #ffcc80;
    box-shadow: 0 -2px 8px rgba(230, 81, 0, 0.12);
  }
  .folder-tab.mode-al::before { background: linear-gradient(180deg, #ffcc80 0%, #ffb74d 100%); border-color: #ffcc80; }
  .folder-tab.mode-al:hover { background: linear-gradient(180deg, #fff3e0 0%, #ffe0b2 100%); color: #bf360c; transform: translateY(0px); }
  .folder-tab.mode-al:hover::before { background: linear-gradient(180deg, #ffb74d 0%, #ffa726 100%); border-color: #ffb74d; }
  .folder-tab.mode-al.active {
    background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
    color: #ffffff; border-color: #0d47a1;
    box-shadow: 0 -6px 20px rgba(13, 71, 161, 0.5);
    animation: pulseMode 2.5s ease-in-out infinite;
  }
  .folder-tab.mode-al.active::before { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); border-color: #0d47a1; height: 9px; top: -9px; }
  @keyframes pulseMode {
    0%, 100% { box-shadow: 0 -6px 20px rgba(13, 71, 161, 0.5); }
    50% { box-shadow: 0 -6px 28px rgba(13, 71, 161, 0.7); }
  }

  .al-content {
    background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1;
    border-radius: 0 0 16px 16px; padding: 28px; min-height: 500px;
    box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px;
  }
  .al-panel { display: none; animation: fadeIn 0.3s ease; }
  .al-panel.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

  /* ===== MODE AL - Landing Page ===== */
  .mode-al-hero {
    background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
    color: white; padding: 28px; border-radius: 12px; margin-bottom: 20px;
    text-align: center;
  }
  .mode-al-hero h2 { margin: 0 0 6px 0; font-size: 1.4rem; }
  .mode-al-hero .subtitle { opacity: 0.9; font-size: 0.9rem; margin-bottom: 16px; }
  .mode-al-search {
    width: 100%; max-width: 700px; padding: 16px 24px; border-radius: 30px;
    border: 2px solid rgba(255,255,255,0.3); background: rgba(255,255,255,0.15);
    color: white; font-size: 1rem; margin: 0 auto; display: block;
    backdrop-filter: blur(4px);
  }
  .mode-al-search::placeholder { color: rgba(255,255,255,0.7); }
  .mode-al-search:focus { outline: none; border-color: #fff; background: rgba(255,255,255,0.25); }

  .quick-chips { display: flex; gap: 6px; justify-content: center; flex-wrap: wrap; margin-top: 16px; }
  .quick-chip {
    padding: 6px 12px; background: rgba(255,255,255,0.15);
    border: 1px solid rgba(255,255,255,0.3); border-radius: 16px;
    color: white; cursor: pointer; font-weight: 600; font-size: 0.78rem;
    transition: all 0.2s;
  }
  .quick-chip:hover { background: rgba(255,255,255,0.3); }

  .search-result-card {
    background: white; border: 1px solid #e0e0e0; border-radius: 10px;
    margin-bottom: 14px; overflow: hidden;
    box-shadow: 0 2px 8px rgba(0,0,0,0.05);
  }
  .src-header {
    display: flex; align-items: center; gap: 10px; padding: 12px 16px;
    background: #f8fafc; border-bottom: 1px solid #e0e0e0; flex-wrap: wrap;
  }
  .src-kriteria {
    background: #0d47a1; color: white; padding: 4px 10px; border-radius: 12px;
    font-size: 0.75rem; font-weight: 700;
  }
  .src-indikator { font-weight: 600; color: #333; font-size: 0.9rem; flex: 1; min-width: 200px; }
  .src-risk { padding: 4px 10px; border-radius: 12px; font-size: 0.72rem; font-weight: 700; text-transform: uppercase; }
  .src-risk.kritis { background: #ffebee; color: #b71c1c; }
  .src-risk.tinggi { background: #fff3e0; color: #e65100; }
  .src-risk.sedang { background: #fff8e1; color: #f57c00; }
  .src-risk.rendah { background: #e8f5e9; color: #2e7d32; }

  .src-body { padding: 16px; }
  .src-section { margin-bottom: 14px; }
  .src-section:last-child { margin-bottom: 0; }
  .src-section-title {
    font-size: 0.72rem; text-transform: uppercase; letter-spacing: 1px;
    font-weight: 700; color: #0d47a1; margin-bottom: 6px;
    display: flex; align-items: center; gap: 6px;
  }
  .src-section-content { font-size: 0.9rem; color: #333; line-height: 1.5; }
  .src-section-content em { color: #c62828; font-style: normal; font-weight: 600; }

  .src-meta-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
  .src-meta-item {
    background: #f8fafc; padding: 10px 12px; border-radius: 6px;
    border-left: 3px solid #0d47a1;
  }
  .src-meta-item .meta-label { font-size: 0.68rem; text-transform: uppercase; letter-spacing: 0.5px; color: #888; font-weight: 600; }
  .src-meta-item .meta-value { font-size: 0.85rem; color: #333; font-weight: 600; margin-top: 2px; }

  .src-followup {
    background: #fff8e1; border-left: 4px solid #ff9800;
    padding: 10px 14px; border-radius: 6px;
  }
  .src-followup .flabel { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 1px; font-weight: 700; color: #e65100; margin-bottom: 4px; }
  .src-followup ul { margin: 0; padding-left: 18px; }
  .src-followup ul li { font-size: 0.88rem; color: #555; padding: 2px 0; }

  .src-actions { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 12px; padding-top: 12px; border-top: 1px solid #f0f0f0; }
  .src-btn {
    padding: 6px 12px; border-radius: 6px; border: 1px solid #0d47a1;
    background: white; color: #0d47a1; font-size: 0.8rem; font-weight: 600;
    cursor: pointer; transition: all 0.2s;
  }
  .src-btn:hover { background: #0d47a1; color: white; }
  .src-btn.primary { background: #0d47a1; color: white; }
  .src-btn.primary:hover { background: #1565c0; }

  .no-result {
    text-align: center; padding: 40px 20px; color: #888;
    background: #f8fafc; border-radius: 10px;
  }

  /* ===== Bank Pertanyaan ===== */
  .sub-nav { display: flex; gap: 4px; margin-bottom: 20px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
  .sub-nav button {
    padding: 10px 16px; background: transparent; border: none; cursor: pointer;
    font-weight: 600; color: #666; border-bottom: 3px solid transparent;
    margin-bottom: -2px; transition: all 0.2s; font-size: 0.88rem;
  }
  .sub-nav button:hover { color: #0d47a1; background: #f8fafc; }
  .sub-nav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }

  .filter-bar {
    display: flex; gap: 8px; margin-bottom: 16px; flex-wrap: wrap;
    padding: 12px; background: #f8fafc; border-radius: 8px;
  }
  .filter-bar select, .filter-bar input {
    padding: 8px 12px; border: 1px solid #e0e0e0; border-radius: 6px;
    font-size: 0.85rem; background: white;
  }
  .filter-bar input { flex: 1; min-width: 200px; }

  .q-card {
    background: white; border: 1px solid #e0e0e0; border-radius: 10px;
    margin-bottom: 12px; overflow: hidden; transition: all 0.2s;
    box-shadow: 0 2px 8px rgba(0,0,0,0.05);
  }
  .q-card:hover { box-shadow: 0 4px 16px rgba(0,0,0,0.1); }
  .q-card-header {
    display: flex; align-items: center; gap: 10px;
    padding: 14px 16px; cursor: pointer; background: #f8fafc;
    border-bottom: 1px solid #e0e0e0; transition: background 0.2s;
    flex-wrap: wrap;
  }
  .q-card-header:hover { background: #e3f2fd; }
  .q-num { font-weight: 800; color: #0d47a1; font-size: 0.95rem; min-width: 30px; }
  .q-main { flex: 1; font-weight: 600; color: #333; font-size: 0.9rem; line-height: 1.4; min-width: 200px; }
  .q-card-header .q-risk { padding: 4px 10px; border-radius: 12px; font-size: 0.72rem; font-weight: 700; text-transform: uppercase; }
  .q-card-header .q-toggle { font-size: 1.2rem; color: #999; transition: transform 0.3s; }
  .q-card.open .q-card-header .q-toggle { transform: rotate(180deg); }
  .q-card-body { display: none; padding: 16px; }
  .q-card.open .q-card-body { display: block; animation: fadeIn 0.3s ease; }

  /* ===== Data Kunci LKPS ===== */
  .data-category-tabs {
    display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 16px;
  }
  .data-cat-btn {
    padding: 8px 14px; background: white; border: 2px solid #e0e0e0;
    border-radius: 20px; cursor: pointer; font-weight: 600; font-size: 0.82rem;
    color: #555; transition: all 0.2s;
  }
  .data-cat-btn:hover { border-color: #0d47a1; color: #0d47a1; }
  .data-cat-btn.active { background: #0d47a1; color: white; border-color: #0d47a1; }

  .data-card {
    background: white; border: 1px solid #e0e0e0; border-radius: 10px;
    padding: 16px; margin-bottom: 10px; border-left: 4px solid #0d47a1;
    transition: all 0.2s;
  }
  .data-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); transform: translateX(2px); }
  .data-card.wajib { border-left-color: #c62828; background: #fff8f8; }
  .data-card-header {
    display: flex; justify-content: space-between; align-items: flex-start;
    gap: 10px; margin-bottom: 8px; flex-wrap: wrap;
  }
  .data-card-title { font-weight: 700; color: #333; font-size: 0.95rem; }
  .data-card-value {
    font-size: 1.4rem; font-weight: 800; color: #0d47a1;
    background: #e3f2fd; padding: 6px 12px; border-radius: 8px;
  }
  .data-card.wajib .data-card-value { background: #ffebee; color: #c62828; }
  .wajib-badge {
    display: inline-block; background: #c62828; color: white;
    padding: 3px 8px; border-radius: 10px; font-size: 0.68rem;
    font-weight: 700; text-transform: uppercase; letter-spacing: 0.5px;
    margin-left: 6px;
  }
  .data-card-meta { font-size: 0.82rem; color: #666; line-height: 1.5; }
  .data-card-meta strong { color: #333; }

  /* ===== Evidence ===== */
  .evidence-card {
    background: white; border: 1px solid #e0e0e0; border-radius: 10px;
    padding: 14px 16px; margin-bottom: 10px; transition: all 0.2s;
    display: flex; justify-content: space-between; align-items: center;
    gap: 12px; flex-wrap: wrap;
  }
  .evidence-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
  .evidence-card.utama { border-left: 4px solid #0d47a1; }
  .evidence-card.pendukung { border-left: 4px solid #90a4ae; }
  .evidence-info { flex: 1; min-width: 200px; }
  .evidence-name { font-weight: 700; color: #333; font-size: 0.92rem; margin-bottom: 4px; }
  .evidence-desc { font-size: 0.82rem; color: #666; line-height: 1.4; }
  .evidence-meta { display: flex; gap: 6px; margin-top: 6px; flex-wrap: wrap; }
  .evidence-badge {
    padding: 3px 8px; border-radius: 10px; font-size: 0.7rem;
    font-weight: 700; text-transform: uppercase; letter-spacing: 0.3px;
  }
  .eb-ready { background: #e8f5e9; color: #2e7d32; }
  .eb-check { background: #fff8e1; color: #f57c00; }
  .eb-missing { background: #ffebee; color: #c62828; }
  .eb-utama { background: #e3f2fd; color: #0d47a1; }
  .eb-pendukung { background: #eceff1; color: #546e7a; }

  /* ===== BAB III ===== */
  .bab3-flow {
    display: flex; flex-direction: column; gap: 0; margin: 20px 0;
  }
  .bab3-step {
    background: white; padding: 16px 20px; border-left: 4px solid #0d47a1;
    position: relative; box-shadow: 0 2px 8px rgba(0,0,0,0.05);
    margin-bottom: 10px; border-radius: 0 8px 8px 0;
    border: 1px solid #e0e0e0; border-left: 4px solid #0d47a1;
  }
  .bab3-step::after {
    content: '▼'; position: absolute; bottom: -14px; left: 50%;
    transform: translateX(-50%); color: #0d47a1; font-size: 1rem; z-index: 1;
  }
  .bab3-step:last-child::after { display: none; }
  .bab3-step .step-title {
    font-weight: 700; color: #0d47a1; margin-bottom: 6px;
    font-size: 0.85rem; letter-spacing: 0.5px; text-transform: uppercase;
  }
  .bab3-step .step-content { font-size: 0.9rem; color: #333; line-height: 1.5; }

  .swot-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin: 16px 0;
  }
  .swot-card {
    padding: 16px; border-radius: 10px; border: 2px solid;
  }
  .swot-card.strength { background: #e8f5e9; border-color: #4caf50; }
  .swot-card.weakness { background: #fff8e1; border-color: #ff9800; }
  .swot-card.opportunity { background: #e3f2fd; border-color: #2196f3; }
  .swot-card.threat { background: #ffebee; border-color: #f44336; }
  .swot-card h4 { margin: 0 0 8px 0; font-size: 0.9rem; }
  .swot-card ul { margin: 0; padding-left: 18px; font-size: 0.85rem; }
  .swot-card ul li { padding: 2px 0; }

  .program-card {
    background: white; border: 1px solid #e0e0e0; border-radius: 10px;
    padding: 16px; margin-bottom: 10px; border-left: 4px solid #0d47a1;
  }
  .program-card h4 { margin: 0 0 8px 0; color: #0d47a1; font-size: 1rem; }
  .program-meta {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 8px; margin-top: 10px;
  }
  .program-meta-item {
    background: #f8fafc; padding: 8px 10px; border-radius: 6px;
    border-left: 3px solid #0d47a1;
  }
  .program-meta-item .mlabel { font-size: 0.68rem; text-transform: uppercase; color: #888; font-weight: 600; }
  .program-meta-item .mvalue { font-size: 0.85rem; color: #333; font-weight: 600; margin-top: 2px; }

  @media (max-width: 767px) {
    .folder-shelf { gap: 6px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
    .folder-shelf::-webkit-scrollbar { display: none; }
    .folder-tab { min-width: 110px; flex: 0 0 auto; font-size: 0.8rem; }
    .al-content { padding: 20px; }
    .src-meta-grid { grid-template-columns: 1fr; }
    .swot-grid { grid-template-columns: 1fr; }
  }
</style>

<!-- ===== KABINET FOLDER NAV - 5 FOLDER ===== -->
<div class="cabinet-container">
  <div class="folder-shelf">
    <div class="folder-tab mode-al active" onclick="showPanel('modeal', this)">🎯<br>MODE AL</div>
    <div class="folder-tab" onclick="showPanel('bank', this)">❓<br>BANK PERTANYAAN</div>
    <div class="folder-tab" onclick="showPanel('data', this)">📊<br>DATA KUNCI LKPS</div>
    <div class="folder-tab" onclick="showPanel('evidence', this)">📁<br>EVIDENCE</div>
    <div class="folder-tab" onclick="showPanel('bab3', this)">📘<br>BAB III</div>
  </div>

  <div class="al-content" id="alContent">

    <!-- ========== MODE AL (LANDING) ========== -->
    <div class="al-panel active" id="panel-modeal">
      <div class="mode-al-hero">
        <h2>🎯 MODE ASESMEN LAPANGAN</h2>
        <div class="subtitle">Cari pertanyaan, data LKPS, evidence, atau program pengembangan dengan cepat</div>
        <input type="text" class="mode-al-search" id="modeAlSearch" placeholder="🔎 Ketik kata kunci: VMTS, tracer, penelitian, CPL, SWOT..." oninput="searchModeAL()">
        <div class="quick-chips">
          <div class="quick-chip" onclick="quickSearch('kekhasan VMTS')">Kekhasan VMTS</div>
          <div class="quick-chip" onclick="quickSearch('tracer study')">Tracer Study</div>
          <div class="quick-chip" onclick="quickSearch('penelitian mahasiswa')">Penelitian Mhs</div>
          <div class="quick-chip" onclick="quickSearch('CPL')">CPL</div>
          <div class="quick-chip" onclick="quickSearch('kerja sama')">Kerja Sama</div>
          <div class="quick-chip" onclick="quickSearch('SWOT')">SWOT</div>
          <div class="quick-chip" onclick="quickSearch('program pengembangan')">Program Pengembangan</div>
        </div>
      </div>
      <div id="searchResultContainer"></div>
      <div id="defaultModeAL">
        <h3 style="color:#0d47a1; margin:20px 0 12px 0;">🔥 Pertanyaan Risiko Tinggi</h3>
        <div id="highRiskList"></div>
      </div>
    </div>

    <!-- ========== BANK PERTANYAAN ========== -->
    <div class="al-panel" id="panel-bank">
      <h2 style="color:#0d47a1; margin-top:0;">❓ Bank Pertanyaan C.1–C.7 + BAB III</h2>
      <p style="color:#666; font-size:0.9rem; margin-top:-4px;">Klik pertanyaan untuk melihat jawaban ideal, data LKPS, evidence, dan follow-up asesor.</p>

      <div class="sub-nav" id="bankSubNav">
        <button class="active" onclick="filterBank('all', this)">Semua</button>
        <button onclick="filterBank('C.1', this)">C.1</button>
        <button onclick="filterBank('C.2', this)">C.2</button>
        <button onclick="filterBank('C.3', this)">C.3</button>
        <button onclick="filterBank('C.4', this)">C.4</button>
        <button onclick="filterBank('C.5', this)">C.5</button>
        <button onclick="filterBank('C.6', this)">C.6</button>
        <button onclick="filterBank('C.7', this)">C.7</button>
        <button onclick="filterBank('BAB III', this)">BAB III</button>
      </div>

      <div class="filter-bar">
        <input type="text" id="bankSearch" placeholder="🔎 Cari pertanyaan..." oninput="renderBank()">
        <select id="filterRisk" onchange="renderBank()">
          <option value="">Semua Risiko</option>
          <option value="Kritis">🔴 Kritis</option>
          <option value="Tinggi">🟠 Tinggi</option>
          <option value="Sedang">🟡 Sedang</option>
          <option value="Rendah">🟢 Rendah</option>
        </select>
        <select id="filterPIC" onchange="renderBank()">
          <option value="">Semua PIC</option>
          <option value="Kaprodi">Kaprodi</option>
          <option value="Kajur">Kajur</option>
          <option value="Kurikulum">Kurikulum</option>
          <option value="GPM">GPM</option>
        </select>
      </div>

      <div id="bankContent"></div>
    </div>

    <!-- ========== DATA KUNCI LKPS ========== -->
    <div class="al-panel" id="panel-data">
      <h2 style="color:#0d47a1; margin-top:0;">📊 Data Kunci LKPS</h2>
      <p style="color:#666; font-size:0.9rem; margin-top:-4px;">Single source of truth angka akreditasi. Data berlabel <span class="wajib-badge">ANGKA WAJIB KONSISTEN</span> harus disampaikan sama oleh seluruh PIC.</p>

      <div class="data-category-tabs" id="dataCatTabs">
        <div class="data-cat-btn active" onclick="filterData('all', this)">Semua</div>
        <div class="data-cat-btn" onclick="filterData('Pendidikan', this)">Pendidikan</div>
        <div class="data-cat-btn" onclick="filterData('SDM', this)">SDM</div>
        <div class="data-cat-btn" onclick="filterData('Penelitian', this)">Penelitian</div>
        <div class="data-cat-btn" onclick="filterData('PkM', this)">PkM</div>
        <div class="data-cat-btn" onclick="filterData('Kerja Sama', this)">Kerja Sama</div>
        <div class="data-cat-btn" onclick="filterData('Mahasiswa', this)">Mahasiswa</div>
        <div class="data-cat-btn" onclick="filterData('Luaran', this)">Luaran</div>
        <div class="data-cat-btn" onclick="filterData('Keuangan', this)">Keuangan</div>
      </div>

      <div id="dataContent"></div>
    </div>

    <!-- ========== EVIDENCE ========== -->
    <div class="al-panel" id="panel-evidence">
      <h2 style="color:#0d47a1; margin-top:0;">📁 Evidence per Indikator</h2>
      <p style="color:#666; font-size:0.9rem; margin-top:-4px;">Bukti pendukung LED/LKPS terstruktur per kriteria dan indikator. Target: buka maksimal 1–2 klik.</p>

      <div class="sub-nav" id="evidenceSubNav">
        <button class="active" onclick="filterEvidence('all', this)">Semua</button>
        <button onclick="filterEvidence('C.1', this)">C.1</button>
        <button onclick="filterEvidence('C.2', this)">C.2</button>
        <button onclick="filterEvidence('C.3', this)">C.3</button>
        <button onclick="filterEvidence('C.4', this)">C.4</button>
        <button onclick="filterEvidence('C.5', this)">C.5</button>
        <button onclick="filterEvidence('C.6', this)">C.6</button>
        <button onclick="filterEvidence('C.7', this)">C.7</button>
      </div>

      <div class="filter-bar">
        <input type="text" id="evidenceSearch" placeholder="🔎 Cari evidence..." oninput="renderEvidence()">
        <select id="filterStatus" onchange="renderEvidence()">
          <option value="">Semua Status</option>
          <option value="READY">✅ READY</option>
          <option value="CHECK">🟡 CHECK</option>
          <option value="MISSING">🔴 MISSING</option>
        </select>
        <select id="filterPrioritas" onchange="renderEvidence()">
          <option value="">Semua Prioritas</option>
          <option value="UTAMA">UTAMA</option>
          <option value="PENDUKUNG">PENDUKUNG</option>
        </select>
      </div>

      <div id="evidenceContent"></div>
    </div>

    <!-- ========== BAB III ========== -->
    <div class="al-panel" id="panel-bab3">
      <h2 style="color:#0d47a1; margin-top:0;">📘 BAB III — Analisis & Program Pengembangan</h2>
      <p style="color:#666; font-size:0.9rem; margin-top:-4px;">Keterkaitan temuan C.1–C.7 dengan SWOT, akar masalah, strategi, dan program pengembangan berkelanjutan.</p>

      <div class="sub-nav" id="bab3SubNav">
        <button class="active" onclick="showBab3('temuan', this)">Temuan Utama</button>
        <button onclick="showBab3('swot', this)">SWOT</button>
        <button onclick="showBab3('tujuan', this)">Tujuan Strategis</button>
        <button onclick="showBab3('program', this)">Program Pengembangan</button>
        <button onclick="showBab3('monitoring', this)">Target–PIC–Monitoring</button>
      </div>

      <div id="bab3Content"></div>
    </div>

  </div>
</div>

<script>
// ===== DATA PERTANYAAN TERINTEGRASI =====
const dataPertanyaan = [
  // C.1 VMTS
  { no: 'C1-01', kriteria: 'C.1', indikator: 'Kekhasan VMTS', pertanyaan: 'Apa kekhasan VMTS JTE dan visi keilmuan PSBM dibanding program sejenis?', followup: ['Apa yang benar-benar membedakan PSBM, bukan sekadar istilah Broadband Multimedia?', 'Tunjukkan benchmarking dengan PT lain'], jawaban: 'PSBM memiliki kekhasan integrasi broadband, multimedia, dan IoT yang terdokumentasi dalam visi keilmuan dan diturunkan ke kurikulum melalui MK khas.', dataLKPS: ['Tabel 1 LKPS', 'Matriks benchmarking 3 PT'], evidence: ['VMTS PNJ/JTE/PSBM', 'Matriks sinkronisasi VMTS'], pic: 'Kaprodi/Kajur', risiko: 'Tinggi' },
  { no: 'C1-02', kriteria: 'C.1', indikator: 'Kekhasan VMTS', pertanyaan: 'Bagaimana linearitas visi PNJ → VMTS JTE → visi keilmuan PSBM?', followup: ['Tunjukkan keterkaitannya secara eksplisit'], jawaban: 'Linearitas terdokumentasi dalam matriks sinkronisasi VMTS yang menunjukkan benang merah dari visi institusi hingga keilmuan PSBM.', dataLKPS: ['Tabel 1 LKPS'], evidence: ['Matriks sinkronisasi VMTS'], pic: 'Kaprodi', risiko: 'Tinggi' },
  { no: 'C1-03', kriteria: 'C.1', indikator: 'Kekhasan VMTS', pertanyaan: 'Bagaimana visi keilmuan PSBM diterjemahkan ke kurikulum?', followup: ['MK apa yang paling merepresentasikan kekhasan?'], jawaban: 'Visi keilmuan diterjemahkan melalui MK khas: Broadband Multimedia, IoT, dan Multimedia Interaktif yang terpetakan ke CPL.', dataLKPS: ['Tabel 3.a.1', 'Matriks CPL-MK'], evidence: ['NADK', 'Struktur kurikulum', 'Matriks CPL-MK'], pic: 'Kaprodi/Kurikulum', risiko: 'Tinggi' },
  { no: 'C1-04', kriteria: 'C.1', indikator: 'Mekanisme VMTS', pertanyaan: 'Bagaimana VMTS dan visi keilmuan disusun?', followup: ['Siapa pemangku kepentingan yang terlibat?'], jawaban: 'VMTS disusun melalui mekanisme terstruktur dengan melibatkan dosen, alumni, pengguna lulusan, dan pakar industri melalui FGD dan workshop.', dataLKPS: ['—'], evidence: ['SK tim', 'Undangan', 'Daftar hadir', 'BA'], pic: 'Kajur', risiko: 'Sedang' },
  { no: 'C1-05', kriteria: 'C.1', indikator: 'Mekanisme VMTS', pertanyaan: 'Bagaimana kebutuhan masyarakat dan tantangan global dipertimbangkan?', followup: ['Masukan apa yang masuk ke visi/strategi?'], jawaban: 'Masukan dari tracer study, forum industri, dan FGD stakeholder dituangkan dalam revisi VMTS dan visi keilmuan.', dataLKPS: ['—'], evidence: ['Notulen workshop', 'FGD report'], pic: 'Kajur/Kaprodi', risiko: 'Sedang' },
  { no: 'C1-06', kriteria: 'C.1', indikator: 'Mekanisme VMTS', pertanyaan: 'Apa bukti alumni, pengguna lulusan, dan pakar benar-benar terlibat?', followup: ['Apakah hanya hadir atau memberi masukan?'], jawaban: 'Daftar hadir disertai notulensi masukan yang ditindaklanjuti dalam revisi dokumen VMTS.', dataLKPS: ['—'], evidence: ['Daftar hadir + masukan + tindak lanjut'], pic: 'Kaprodi', risiko: 'Tinggi' },
  { no: 'C1-07', kriteria: 'C.1', indikator: 'Pemahaman & Pencapaian', pertanyaan: 'Bagaimana VMTS disosialisasikan dan diukur tingkat pemahamannya?', followup: ['Berapa hasil pengukuran pemahaman stakeholder?'], jawaban: 'VMTS disosialisasikan melalui website, buku saku, dan rapat rutin. Survei pemahaman menunjukkan 85% stakeholder paham.', dataLKPS: ['Tabel 1'], evidence: ['Survei VMTS', 'Buku saku'], pic: 'Kajur/GPM', risiko: 'Tinggi' },
  { no: 'C1-08', kriteria: 'C.1', indikator: 'Pemahaman & Pencapaian', pertanyaan: 'Apa capaian konkret jangka pendek/menengah dari VMTS?', followup: ['Tunjukkan target vs realisasi'], jawaban: 'Capaian: 100% MK punya RPS berbasis OBE, 85% lulusan bekerja < 6 bulan, 3 publikasi internasional.', dataLKPS: ['LKPS terkait'], evidence: ['Renstra', 'Renop', 'Laporan capaian'], pic: 'Kajur', risiko: 'Tinggi' },
  { no: 'C1-09', kriteria: 'C.1', indikator: 'Pemahaman & Pencapaian', pertanyaan: 'Apa bukti VMTS berdampak dan berkelanjutan?', followup: ['Perubahan apa yang dikaitkan dengan VMTS?'], jawaban: 'Dampak terlihat dari peningkatan akreditasi, kerja sama industri, dan prestasi mahasiswa yang selaras dengan visi.', dataLKPS: ['C.3/C.4/C.6'], evidence: ['Laporan kinerja'], pic: 'Kajur/Kaprodi', risiko: 'Tinggi' },

  // C.3 Relevansi
  { no: 'C3-01', kriteria: 'C.3', indikator: 'CPL', pertanyaan: 'Bagaimana PSBM memastikan CPL sesuai dengan kebutuhan industri?', followup: ['Apa masukan industri?', 'Apa yang berubah?', 'Mana bukti tindak lanjut?'], jawaban: 'CPL ditinjau setiap 2 tahun melalui tracer study, survei pengguna, forum industri, dan workshop OBE.', dataLKPS: ['Tabel 3.a.1', 'Tabel 6.a'], evidence: ['NADK 2020', 'Laporan Workshop OBE 2024', 'Matriks Profil-CPL'], pic: 'Tim Kurikulum', risiko: 'Kritis' },
  { no: 'C3-02', kriteria: 'C.3', indikator: 'Penelitian', pertanyaan: 'Bagaimana keterlibatan mahasiswa dalam penelitian DTPS?', followup: ['Kenapa masih rendah?', 'Apa target berikutnya?'], jawaban: '26,67% penelitian DTPS melibatkan mahasiswa melalui TA dan proyek MK. Target 40% pada 2026.', dataLKPS: ['Tabel 3.b', 'Tabel 6.h.1'], evidence: ['Daftar penelitian', 'Bukti keterlibatan mhs', 'Roadmap'], pic: 'Kaprodi/Dosen', risiko: 'Tinggi' },

  // C.6 Luaran
  { no: 'C6-01', kriteria: 'C.6', indikator: 'Tracer Study', pertanyaan: 'Berapa response rate tracer study 2024?', followup: ['Strategi peningkatan?', 'Kualitas pekerjaan lulusan?'], jawaban: 'Response rate 68% (2024), di atas syarat minimal 30%. Waktu tunggu < 6 bulan: 72%.', dataLKPS: ['Tabel 6.a'], evidence: ['Laporan Tracer 2024', 'Kuesioner DIKTI'], pic: 'GPM/Kaprodi', risiko: 'Tinggi' },

  // BAB III
  { no: 'B3-01', kriteria: 'BAB III', indikator: 'Program Pengembangan', pertanyaan: 'Mengapa peningkatan pendanaan eksternal penelitian menjadi program pengembangan?', followup: ['Apa dasar analisisnya?', 'Apa targetnya?', 'Siapa PIC?'], jawaban: 'Berdasarkan analisis SWOT: pendanaan eksternal masih rendah (weakness), peluang hibah nasional meningkat (opportunity). Strategi WO: optimalisasi hibah.', dataLKPS: ['Tabel 3.b'], evidence: ['Dokumen SWOT', 'Renstra', 'Roadmap penelitian'], pic: 'LPPM/Kaprodi', risiko: 'Tinggi' },
  { no: 'B3-02', kriteria: 'BAB III', indikator: 'Tujuan Strategis', pertanyaan: 'Apa tujuan strategis PSBM 5 tahun ke depan?', followup: ['Bagaimana keterkaitan dengan VMTS?'], jawaban: '3 tujuan strategis: (1) Unggul di bidang broadband multimedia, (2) Lulusan kompeten global, (3) Pusat riset IoT terapan.', dataLKPS: ['Renstra'], evidence: ['Dokumen Renstra', 'Matriks tujuan-VMTS'], pic: 'Kajur', risiko: 'Sedang' }
];

// ===== DATA KUNCI LKPS =====
const dataLKPS = [
  { nama: 'Rasio Mahasiswa:DTPS', value: '18:1', kategori: 'Mahasiswa', periode: 'TS', sumber: 'LKPS Tabel 4.a', penjelasan: 'Rasio ideal sesuai standar LAM Teknik (<20:1)', wajib: true },
  { nama: 'IPK Lulusan Rata-rata', value: '3.52', kategori: 'Luaran', periode: '3 tahun', sumber: 'LKPS Tabel 6.a', penjelasan: 'IPK rata-rata lulusan TS-2 s.d. TS', wajib: true },
  { nama: 'Response Rate Tracer Study', value: '68%', kategori: 'Luaran', periode: '2024', sumber: 'LKPS Tabel 6.a', penjelasan: 'Di atas syarat minimal LAM 30%', wajib: true },
  { nama: 'Waktu Tunggu Lulusan', value: '< 6 bulan (72%)', kategori: 'Luaran', periode: '2024', sumber: 'LKPS Tabel 6.a', penjelasan: 'Persentase lulusan bekerja < 6 bulan', wajib: true },
  { nama: 'Jumlah DTPS', value: '11 dosen', kategori: 'SDM', periode: 'TS', sumber: 'LKPS Tabel 2.a', penjelasan: 'Dosen tetap program studi', wajib: true },
  { nama: 'Publikasi Internasional Bereputasi', value: '8 artikel', kategori: 'Penelitian', periode: '3 tahun', sumber: 'LKPS Tabel 3.b', penjelasan: 'Publikasi di jurnal terindeks Scopus/WoS', wajib: true },
  { nama: 'Keterlibatan Mahasiswa dalam Penelitian', value: '26,67%', kategori: 'Penelitian', periode: '3 tahun', sumber: 'LKPS Tabel 6.h.1', penjelasan: '12 dari 45 penelitian melibatkan mahasiswa', wajib: true },
  { nama: 'Judul PkM', value: '28 judul', kategori: 'PkM', periode: '3 tahun', sumber: 'LKPS Tabel 3.c', penjelasan: 'PkM DTPS yang relevan dengan bidang studi', wajib: false },
  { nama: 'MoU Aktif', value: '25 MoU', kategori: 'Kerja Sama', periode: 'TS', sumber: 'LKPS Tabel 5', penjelasan: 'MoU aktif dengan mitra nasional & internasional', wajib: false },
  { name: 'Implementasi Kerja Sama', value: '15 kegiatan', kategori: 'Kerja Sama', periode: '3 tahun', sumber: 'LKPS Tabel 5', penjelasan: 'Implementasi nyata dari MoU', wajib: false },
  { nama: 'Pendanaan Eksternal Penelitian', value: 'Rp 450 juta', kategori: 'Penelitian', periode: '3 tahun', sumber: 'LKPS Tabel 3.b', penjelasan: 'Dana hibah eksternal (nasional + internasional)', wajib: true },
  { nama: 'MK Berbasis OBE', value: '100%', kategori: 'Pendidikan', periode: 'TS', sumber: 'LKPS Tabel 3.a.1', penjelasan: 'Seluruh MK sudah menerapkan RPS berbasis OBE', wajib: true },
  { nama: 'CPL Terdefinisi', value: '12 CPL', kategori: 'Pendidikan', periode: 'TS', sumber: 'NADK 2020', penjelasan: 'CPL diturunkan dari profil lulusan', wajib: true },
  { nama: 'Survei Pemahaman VMTS', value: '85%', kategori: 'Pendidikan', periode: '2024', sumber: 'Laporan Survei', penjelasan: 'Stakeholder paham VMTS PSBM', wajib: false },
  { nama: 'Pendanaan Mandiri PT', value: 'Rp 1,2 M', kategori: 'Keuangan', periode: 'TS', sumber: 'LKPS Keuangan', penjelasan: 'Anggaran PT untuk PSBM per tahun', wajib: false }
];

// ===== DATA EVIDENCE =====
const dataEvidence = [
  // C.1
  { nama: 'SK VMTS PT & UPPS', kriteria: 'C.1', indikator: 'Kekhasan VMTS', deskripsi: 'SK resmi VMTS dari tingkat PT dan UPPS', pic: 'Kajur', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Matriks Sinkronisasi VMTS', kriteria: 'C.1', indikator: 'Kekhasan VMTS', deskripsi: 'Matriks linearitas visi PNJ → JTE → PSBM', pic: 'Kaprodi', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'NADK PSBM 2020', kriteria: 'C.1', indikator: 'Visi Keilmuan', deskripsi: 'Naskah Akademik Pengembangan Kurikulum', pic: 'Kurikulum', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Laporan Survei VMTS', kriteria: 'C.1', indikator: 'Pemahaman', deskripsi: 'Hasil survei pemahaman stakeholder terhadap VMTS', pic: 'GPM', status: 'READY', prioritas: 'UTAMA' },

  // C.3
  { nama: 'Matriks CPL-MK', kriteria: 'C.3', indikator: 'CPL', deskripsi: 'Pemetaan CPL ke setiap mata kuliah', pic: 'Kurikulum', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Laporan Workshop OBE 2024', kriteria: 'C.3', indikator: 'Tinjauan CPL', deskripsi: 'Dokumentasi workshop tinjauan CPL', pic: 'Kurikulum', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Kumpulan RPS', kriteria: 'C.3', indikator: 'RPS', deskripsi: 'RPS seluruh MK', pic: 'Kurikulum', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Daftar Penelitian DTPS', kriteria: 'C.3', indikator: 'Penelitian', deskripsi: 'Daftar lengkap penelitian 3 tahun terakhir', pic: 'LPPM', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Bukti Keterlibatan Mahasiswa', kriteria: 'C.3', indikator: 'Penelitian', deskripsi: 'Dokumentasi keterlibatan mhs dalam penelitian', pic: 'Kaprodi', status: 'CHECK', prioritas: 'UTAMA' },
  { nama: 'Laporan PkM', kriteria: 'C.3', indikator: 'PkM', deskripsi: 'Laporan kegiatan PkM DTPS', pic: 'LPPM', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Roadmap Penelitian', kriteria: 'C.3', indikator: 'Penelitian', deskripsi: 'Peta jalan penelitian 2020-2025', pic: 'LPPM', status: 'READY', prioritas: 'PENDUKUNG' },

  // C.4
  { nama: 'Ijazah & Sertifikat DTPS', kriteria: 'C.4', indikator: 'Profil DTPS', deskripsi: 'Scan ijazah dan sertifikat dosen', pic: 'Kajur', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Beban Kerja Dosen', kriteria: 'C.4', indikator: 'BKD', deskripsi: 'Laporan BKD per semester', pic: 'Kaprodi', status: 'READY', prioritas: 'UTAMA' },

  // C.5
  { nama: 'SOP K3L Laboratorium', kriteria: 'C.5', indikator: 'K3L', deskripsi: 'SOP resmi K3L lab', pic: 'Kajur', status: 'CHECK', prioritas: 'UTAMA' },
  { nama: 'Inventaris Lab', kriteria: 'C.5', indikator: 'Sarpras', deskripsi: 'Daftar inventaris peralatan lab', pic: 'Lab', status: 'READY', prioritas: 'UTAMA' },

  // C.6
  { nama: 'Laporan Tracer Study 2024', kriteria: 'C.6', indikator: 'Tracer', deskripsi: 'Laporan lengkap tracer study', pic: 'GPM', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Sertifikat Prestasi Mahasiswa', kriteria: 'C.6', indikator: 'Prestasi', deskripsi: 'Bukti prestasi akademik & non-akademik', pic: 'Kaprodi', status: 'READY', prioritas: 'UTAMA' },

  // C.7
  { nama: 'Laporan AMI 2025', kriteria: 'C.7', indikator: 'AMI', deskripsi: 'Laporan Audit Mutu Internal', pic: 'UPM', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Notulensi RTM', kriteria: 'C.7', indikator: 'RTM', deskripsi: 'Notulensi Rapat Tinjauan Manajemen', pic: 'UPM', status: 'READY', prioritas: 'UTAMA' },
  { nama: 'Dokumen Siklus PPEPP', kriteria: 'C.7', indikator: 'PPEPP', deskripsi: 'Dokumen lengkap siklus PPEPP', pic: 'UPM', status: 'CHECK', prioritas: 'UTAMA' }
];

// ===== DATA BAB III =====
const dataBab3 = {
  temuan: [
    { kriteria: 'C.1', temuan: 'VMTS sudah dipahami stakeholder (85%), namun sosialisasi ke mitra industri masih perlu ditingkatkan.' },
    { kriteria: 'C.3', temuan: 'CPL sudah sesuai kebutuhan industri, namun tinjauan rutin perlu diperkuat dengan data tracer study.' },
    { kriteria: 'C.3', temuan: 'Keterlibatan mahasiswa dalam penelitian masih rendah (26,67%).' },
    { kriteria: 'C.6', temuan: 'Response rate tracer study 68%, di atas syarat minimal, namun target 80% belum tercapai.' },
    { kriteria: 'C.7', temuan: 'Siklus PPEPP sudah berjalan, namun tindak lanjut temuan AMI perlu didokumentasikan lebih baik.' }
  ],
  swot: {
    strength: ['VMTS jelas dan dipahami stakeholder (85%)', '12 CPL terpetakan ke MK berbasis OBE', '11 DTPS dengan kualifikasi S2/S3', 'Akreditasi Baik dari LAM Teknik'],
    weakness: ['Keterlibatan mhs dalam penelitian rendah (26,67%)', 'Pendanaan eksternal penelitian masih terbatas', 'Response rate tracer study belum optimal (68%)', 'Dokumentasi tindak lanjut AMI belum lengkap'],
    opportunity: ['Hibah penelitian nasional (BIMA, DRTPM) meningkat', 'Industri digital butuh lulusan broadband multimedia', 'Kerja sama dengan mitra IoT & multimedia', 'Program Merdeka Belajar'],
    threat: ['Persaingan dengan PT sejenis', 'Perkembangan IPTEKS cepat', 'Tuntutan industri yang dinamis', 'Regulasi DIKTI yang berubah']
  },
  tujuan: [
    { no: 1, tujuan: 'Menjadi program studi unggul di bidang broadband multimedia tingkat nasional', indikator: 'Akreditasi Unggul 2028', target: '2028' },
    { no: 2, tujuan: 'Menghasilkan lulusan kompeten di tingkat global', indikator: '80% lulusan bekerja < 6 bulan', target: '2027' },
    { no: 3, tujuan: 'Menjadi pusat riset IoT terapan', indikator: '20 publikasi internasional bereputasi', target: '2027' }
  ],
  program: [
    { nama: 'Peningkatan Keterlibatan Mahasiswa dalam Penelitian', strategi: 'WO', akar: 'Mekanisme integrasi TA dengan penelitian dosen belum optimal', target: '40% penelitian libatkan mhs (2026)', pic: 'Kaprodi + LPPM', anggaran: 'Rp 50 juta', monitoring: 'Triwulanan' },
    { nama: 'Optimalisasi Pendanaan Eksternal Penelitian', strategi: 'WO', akar: 'Dosen belum aktif mengajukan hibah nasional', target: 'Rp 800 juta (2026)', pic: 'LPPM', anggaran: 'Rp 30 juta', monitoring: 'Semesteran' },
    { nama: 'Peningkatan Response Rate Tracer Study', strategi: 'WT', akar: 'Database alumni belum terupdate', target: '80% response rate (2026)', pic: 'GPM + Karir', anggaran: 'Rp 20 juta', monitoring: 'Tahunan' },
    { nama: 'Penguatan Tinjauan CPL Berbasis Tracer', strategi: 'SO', akar: 'Tinjauan CPL belum rutin menggunakan data tracer', target: 'Tinjauan CPL tahunan berbasis data', pic: 'Tim Kurikulum', anggaran: 'Rp 15 juta', monitoring: 'Tahunan' }
  ]
};

// ===== NAVIGATION =====
function showPanel(id, btn) {
  document.querySelectorAll('.al-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.folder-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  if (id === 'bank') { renderBank(); }
  if (id === 'data') { renderData('all'); }
  if (id === 'evidence') { renderEvidence(); }
  if (id === 'bab3') { showBab3('temuan', document.querySelector('#bab3SubNav button')); }
  if (id === 'modeal') { renderHighRisk(); }
}

// ===== MODE AL SEARCH =====
function quickSearch(keyword) {
  document.getElementById('modeAlSearch').value = keyword;
  searchModeAL();
}

function searchModeAL() {
  const query = document.getElementById('modeAlSearch').value.toLowerCase().trim();
  const container = document.getElementById('searchResultContainer');
  const defaultView = document.getElementById('defaultModeAL');

  if (!query) {
    container.innerHTML = '';
    defaultView.style.display = 'block';
    return;
  }
  defaultView.style.display = 'none';

  const results = [];

  // Cari di pertanyaan
  dataPertanyaan.forEach(q => {
    const match = q.pertanyaan.toLowerCase().includes(query) ||
                  q.indikator.toLowerCase().includes(query) ||
                  q.jawaban.toLowerCase().includes(query) ||
                  q.kriteria.toLowerCase().includes(query);
    if (match) results.push({ type: 'pertanyaan', data: q });
  });

  // Cari di data LKPS
  dataLKPS.forEach(d => {
    if (d.nama.toLowerCase().includes(query) || d.penjelasan.toLowerCase().includes(query)) {
      results.push({ type: 'data', data: d });
    }
  });

  // Cari di evidence
  dataEvidence.forEach(e => {
    if (e.nama.toLowerCase().includes(query) || e.deskripsi.toLowerCase().includes(query)) {
      results.push({ type: 'evidence', data: e });
    }
  });

  // Cari di BAB III
  if (query.includes('swot') || query.includes('program pengembangan') || query.includes('strategi')) {
    results.push({ type: 'bab3', data: { title: 'Program Pengembangan PSBM', link: 'bab3' } });
  }

  if (results.length === 0) {
    container.innerHTML = '<div class="no-result">🔍 Tidak ditemukan hasil untuk "<strong>' + query + '</strong>"<br><small>Coba kata kunci lain atau hubungi koordinator</small></div>';
    return;
  }

  let html = '<div style="margin-bottom:12px; font-size:0.85rem; color:#666;">Ditemukan <strong>' + results.length + '</strong> hasil</div>';
  results.forEach(r => { html += renderSearchResult(r); });
  container.innerHTML = html;
}

function renderSearchResult(r) {
  if (r.type === 'pertanyaan') {
    const q = r.data;
    const riskClass = q.risiko.toLowerCase();
    let html = '<div class="search-result-card">';
    html += '<div class="src-header">';
    html += '<div class="src-kriteria">' + q.kriteria + '</div>';
    html += '<div class="src-indikator">' + q.indikator + '</div>';
    html += '<div class="src-risk ' + riskClass + '">' + q.risiko + '</div>';
    html += '</div>';
    html += '<div class="src-body">';
    html += '<div class="src-section"><div class="src-section-title">❓ PERTANYAAN ASESOR</div><div class="src-section-content">' + q.pertanyaan + '</div></div>';
    html += '<div class="src-section"><div class="src-section-title">💡 JAWABAN IDEAL (20–40 detik)</div><div class="src-section-content">' + q.jawaban + '</div></div>';
    html += '<div class="src-section"><div class="src-section-title">📊 DATA LKPS YANG HARUS DISEBUT</div><ul>';
    q.dataLKPS.forEach(d => { html += '<li><strong>' + d + '</strong></li>'; });
    html += '</ul></div>';
    html += '<div class="src-section"><div class="src-section-title">📎 EVIDENCE YANG HARUS DIBUKA</div><ul>';
    q.evidence.forEach(e => { html += '<li>✓ ' + e + '</li>'; });
    html += '</ul></div>';
    if (q.followup && q.followup.length > 0) {
      html += '<div class="src-followup"><div class="flabel">🔥 FOLLOW-UP ASESOR</div><ul>';
      q.followup.forEach(f => { html += '<li>→ ' + f + '</li>'; });
      html += '</ul></div>';
    }
    html += '<div class="src-meta-grid">';
    html += '<div class="src-meta-item"><div class="meta-label">👤 PIC Utama</div><div class="meta-value">' + q.pic + '</div></div>';
    html += '<div class="src-meta-item"><div class="meta-label">⚠️ Tingkat Risiko</div><div class="meta-value">' + q.risiko + '</div></div>';
    html += '</div>';
    html += '<div class="src-actions">';
    html += '<button class="src-btn primary" onclick="jumpTo(\'bank\')">📋 Lihat di Bank Pertanyaan</button>';
    html += '<button class="src-btn" onclick="jumpTo(\'evidence\')">📁 Buka Evidence</button>';
    html += '<button class="src-btn" onclick="jumpTo(\'data\')">📊 Data LKPS</button>';
    html += '</div>';
    html += '</div></div>';
    return html;
  } else if (r.type === 'data') {
    const d = r.data;
    let html = '<div class="search-result-card">';
    html += '<div class="src-header"><div class="src-kriteria">LKPS</div><div class="src-indikator">📊 ' + d.nama + '</div>';
    if (d.wajib) html += '<div class="src-risk kritis">WAJIB KONSISTEN</div>';
    html += '</div>';
    html += '<div class="src-body">';
    html += '<div style="font-size:2rem; font-weight:800; color:#0d47a1; text-align:center; padding:10px 0;">' + d.value + '</div>';
    html += '<div class="src-meta-grid">';
    html += '<div class="src-meta-item"><div class="meta-label">📅 Periode</div><div class="meta-value">' + d.periode + '</div></div>';
    html += '<div class="src-meta-item"><div class="meta-label">📑 Sumber</div><div class="meta-value">' + d.sumber + '</div></div>';
    html += '</div>';
    html += '<div class="src-section" style="margin-top:10px;"><div class="src-section-title">📝 PENJELASAN</div><div class="src-section-content">' + d.penjelasan + '</div></div>';
    html += '<div class="src-actions"><button class="src-btn primary" onclick="jumpTo(\'data\')">📊 Lihat di Data Kunci</button></div>';
    html += '</div></div>';
    return html;
  } else if (r.type === 'evidence') {
    const e = r.data;
    let html = '<div class="search-result-card">';
    html += '<div class="src-header"><div class="src-kriteria">' + e.kriteria + '</div><div class="src-indikator">📁 ' + e.nama + '</div></div>';
    html += '<div class="src-body">';
    html += '<div class="src-section"><div class="src-section-title">📝 DESKRIPSI</div><div class="src-section-content">' + e.deskripsi + '</div></div>';
    html += '<div class="src-meta-grid">';
    html += '<div class="src-meta-item"><div class="meta-label">👤 PIC</div><div class="meta-value">' + e.pic + '</div></div>';
    html += '<div class="src-meta-item"><div class="meta-label">📌 Prioritas</div><div class="meta-value">' + e.prioritas + '</div></div>';
    html += '</div>';
    html += '<div class="src-actions"><button class="src-btn primary" onclick="jumpTo(\'evidence\')">📁 Lihat di Evidence</button></div>';
    html += '</div></div>';
    return html;
  } else if (r.type === 'bab3') {
    let html = '<div class="search-result-card">';
    html += '<div class="src-header"><div class="src-kriteria">BAB III</div><div class="src-indikator">📘 ' + r.data.title + '</div></div>';
    html += '<div class="src-body">';
    html += '<div class="src-section"><div class="src-section-content">Program pengembangan PSBM berbasis analisis SWOT dan temuan C.1–C.7.</div></div>';
    html += '<div class="src-actions"><button class="src-btn primary" onclick="jumpTo(\'bab3\')">📘 Lihat di BAB III</button></div>';
    html += '</div></div>';
    return html;
  }
  return '';
}

function jumpTo(panel) {
  const btns = document.querySelectorAll('.folder-tab');
  const panelMap = { bank: 1, data: 2, evidence: 3, bab3: 4, modeal: 0 };
  showPanel(panel, btns[panelMap[panel]]);
}

function renderHighRisk() {
  const high = dataPertanyaan.filter(q => q.risiko === 'Tinggi' || q.risiko === 'Kritis').slice(0, 5);
  let html = '';
  high.forEach(q => { html += renderSearchResult({ type: 'pertanyaan', data: q }); });
  document.getElementById('highRiskList').innerHTML = html;
}

// ===== BANK PERTANYAAN =====
let currentBankFilter = 'all';
function filterBank(filter, btn) {
  document.querySelectorAll('#bankSubNav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  currentBankFilter = filter;
  renderBank();
}

function renderBank() {
  const search = (document.getElementById('bankSearch')?.value || '').toLowerCase();
  const risk = document.getElementById('filterRisk')?.value || '';
  const pic = document.getElementById('filterPIC')?.value || '';

  let filtered = dataPertanyaan;
  if (currentBankFilter !== 'all') filtered = filtered.filter(q => q.kriteria === currentBankFilter);
  if (search) filtered = filtered.filter(q => q.pertanyaan.toLowerCase().includes(search) || q.indikator.toLowerCase().includes(search));
  if (risk) filtered = filtered.filter(q => q.risiko === risk);
  if (pic) filtered = filtered.filter(q => q.pic.toLowerCase().includes(pic.toLowerCase()));

  let html = '<div style="margin-bottom:12px; font-size:0.85rem; color:#666;">Menampilkan <strong>' + filtered.length + '</strong> pertanyaan</div>';
  filtered.forEach(q => {
    const riskClass = q.risiko.toLowerCase();
    html += '<div class="q-card" id="qcard-' + q.no + '">';
    html += '<div class="q-card-header" onclick="toggleQ(\'' + q.no + '\')">';
    html += '<div class="q-num">' + q.no + '</div>';
    html += '<div class="q-main">' + q.pertanyaan + '</div>';
    html += '<div class="q-risk ' + riskClass + '">' + q.risiko + '</div>';
    html += '<div class="q-toggle">▼</div>';
    html += '</div>';
    html += '<div class="q-card-body">';
    html += '<div class="src-section"><div class="src-section-title">💡 JAWABAN IDEAL</div><div class="src-section-content">' + q.jawaban + '</div></div>';
    html += '<div class="src-section"><div class="src-section-title">📊 DATA LKPS</div><ul>';
    q.dataLKPS.forEach(d => { html += '<li><strong>' + d + '</strong></li>'; });
    html += '</ul></div>';
    html += '<div class="src-section"><div class="src-section-title">📎 EVIDENCE</div><ul>';
    q.evidence.forEach(e => { html += '<li>✓ ' + e + '</li>'; });
    html += '</ul></div>';
    if (q.followup && q.followup.length > 0) {
      html += '<div class="src-followup"><div class="flabel">🔥 FOLLOW-UP KRITIS</div><ul>';
      q.followup.forEach(f => { html += '<li>→ ' + f + '</li>'; });
      html += '</ul></div>';
    }
    html += '<div class="src-meta-grid" style="margin-top:12px;">';
    html += '<div class="src-meta-item"><div class="meta-label">👤 PIC</div><div class="meta-value">' + q.pic + '</div></div>';
    html += '<div class="src-meta-item"><div class="meta-label">⚠️ Risiko</div><div class="meta-value">' + q.risiko + '</div></div>';
    html += '</div>';
    html += '</div></div>';
  });
  document.getElementById('bankContent').innerHTML = html;
}

function toggleQ(no) {
  document.getElementById('qcard-' + no).classList.toggle('open');
}

// ===== DATA KUNCI LKPS =====
let currentDataFilter = 'all';
function filterData(filter, btn) {
  document.querySelectorAll('.data-cat-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  currentDataFilter = filter;
  renderData(filter);
}

function renderData(filter) {
  let filtered = dataLKPS;
  if (filter && filter !== 'all') filtered = filtered.filter(d => d.kategori === filter);
  // Sort: wajib first
  filtered.sort((a, b) => (b.wajib ? 1 : 0) - (a.wajib ? 1 : 0));

  let html = '';
  filtered.forEach(d => {
    html += '<div class="data-card ' + (d.wajib ? 'wajib' : '') + '">';
    html += '<div class="data-card-header">';
    html += '<div class="data-card-title">' + d.nama + (d.wajib ? '<span class="wajib-badge">ANGKA WAJIB KONSISTEN</span>' : '') + '</div>';
    html += '<div class="data-card-value">' + d.value + '</div>';
    html += '</div>';
    html += '<div class="data-card-meta">';
    html += '<strong>📅 Periode:</strong> ' + d.periode + ' &nbsp; | &nbsp; ';
    html += '<strong>📑 Sumber:</strong> ' + d.sumber + '<br>';
    html += '<strong>📝 Penjelasan:</strong> ' + d.penjelasan;
    html += '</div>';
    html += '</div>';
  });
  document.getElementById('dataContent').innerHTML = html;
}

// ===== EVIDENCE =====
let currentEvidenceFilter = 'all';
function filterEvidence(filter, btn) {
  document.querySelectorAll('#evidenceSubNav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  currentEvidenceFilter = filter;
  renderEvidence();
}

function renderEvidence() {
  const search = (document.getElementById('evidenceSearch')?.value || '').toLowerCase();
  const status = document.getElementById('filterStatus')?.value || '';
  const prioritas = document.getElementById('filterPrioritas')?.value || '';

  let filtered = dataEvidence;
  if (currentEvidenceFilter !== 'all') filtered = filtered.filter(e => e.kriteria === currentEvidenceFilter);
  if (search) filtered = filtered.filter(e => e.nama.toLowerCase().includes(search) || e.deskripsi.toLowerCase().includes(search));
  if (status) filtered = filtered.filter(e => e.status === status);
  if (prioritas) filtered = filtered.filter(e => e.prioritas === prioritas);

  let html = '<div style="margin-bottom:12px; font-size:0.85rem; color:#666;">Menampilkan <strong>' + filtered.length + '</strong> evidence</div>';
  filtered.forEach(e => {
    const statusClass = e.status === 'READY' ? 'eb-ready' : (e.status === 'CHECK' ? 'eb-check' : 'eb-missing');
    const prioClass = e.prioritas === 'UTAMA' ? 'utama' : 'pendukung';
    const prioBadge = e.prioritas === 'UTAMA' ? 'eb-utama' : 'eb-pendukung';
    html += '<div class="evidence-card ' + prioClass + '">';
    html += '<div class="evidence-info">';
    html += '<div class="evidence-name">' + e.nama + '</div>';
    html += '<div class="evidence-desc">' + e.deskripsi + '</div>';
    html += '<div class="evidence-meta">';
    html += '<span class="evidence-badge ' + statusClass + '">' + e.status + '</span>';
    html += '<span class="evidence-badge ' + prioBadge + '">' + e.prioritas + '</span>';
    html += '<span class="evidence-badge" style="background:#f1f5f9; color:#0d47a1;">' + e.kriteria + ' · ' + e.indikator + '</span>';
    html += '<span class="evidence-badge" style="background:#f1f5f9; color:#555;">👤 ' + e.pic + '</span>';
    html += '</div></div>';
    html += '<button class="src-btn primary">📂 BUKA</button>';
    html += '</div>';
  });
  document.getElementById('evidenceContent').innerHTML = html;
}

// ===== BAB III =====
function showBab3(key, btn) {
  document.querySelectorAll('#bab3SubNav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');

  let html = '';
  if (key === 'temuan') {
    html += '<h3 style="color:#0d47a1;">Temuan Utama C.1–C.7</h3>';
    dataBab3.temuan.forEach(t => {
      html += '<div class="data-card"><div class="data-card-header"><div class="data-card-title">' + t.kriteria + '</div></div>';
      html += '<div class="data-card-meta">' + t.temuan + '</div></div>';
    });
  } else if (key === 'swot') {
    html += '<h3 style="color:#0d47a1;">Analisis SWOT</h3>';
    html += '<div class="swot-grid">';
    html += '<div class="swot-card strength"><h4>💪 STRENGTH (S)</h4><ul>';
    dataBab3.swot.strength.forEach(s => { html += '<li>' + s + '</li>'; });
    html += '</ul></div>';
    html += '<div class="swot-card weakness"><h4>⚠️ WEAKNESS (W)</h4><ul>';
    dataBab3.swot.weakness.forEach(s => { html += '<li>' + s + '</li>'; });
    html += '</ul></div>';
    html += '<div class="swot-card opportunity"><h4>🚀 OPPORTUNITY (O)</h4><ul>';
    dataBab3.swot.opportunity.forEach(s => { html += '<li>' + s + '</li>'; });
    html += '</ul></div>';
    html += '<div class="swot-card threat"><h4>⚡ THREAT (T)</h4><ul>';
    dataBab3.swot.threat.forEach(s => { html += '<li>' + s + '</li>'; });
    html += '</ul></div></div>';
  } else if (key === 'tujuan') {
    html += '<h3 style="color:#0d47a1;">Tujuan Strategis PSBM</h3>';
    dataBab3.tujuan.forEach(t => {
      html += '<div class="program-card"><h4>' + t.no + '. ' + t.tujuan + '</h4>';
      html += '<div class="program-meta">';
      html += '<div class="program-meta-item"><div class="mlabel">Indikator</div><div class="mvalue">' + t.indikator + '</div></div>';
      html += '<div class="program-meta-item"><div class="mlabel">Target</div><div class="mvalue">' + t.target + '</div></div>';
      html += '</div></div>';
    });
  } else if (key === 'program') {
    html += '<h3 style="color:#0d47a1;">Program Pengembangan</h3>';
    dataBab3.program.forEach(p => {
      html += '<div class="program-card"><h4>' + p.nama + '</h4>';
      html += '<div class="data-card-meta"><strong>Akar Masalah:</strong> ' + p.akar + '<br><strong>Strategi:</strong> ' + p.strategi + '</div>';
      html += '<div class="program-meta">';
      html += '<div class="program-meta-item"><div class="mlabel">Target</div><div class="mvalue">' + p.target + '</div></div>';
      html += '<div class="program-meta-item"><div class="mlabel">PIC</div><div class="mvalue">' + p.pic + '</div></div>';
      html += '<div class="program-meta-item"><div class="mlabel">Anggaran</div><div class="mvalue">' + p.anggaran + '</div></div>';
      html += '<div class="program-meta-item"><div class="mlabel">Monitoring</div><div class="mvalue">' + p.monitoring + '</div></div>';
      html += '</div></div>';
    });
  } else if (key === 'monitoring') {
    html += '<h3 style="color:#0d47a1;">Target – PIC – Monitoring</h3>';
    html += '<table class="risk-table"><thead><tr><th>Program</th><th>Target</th><th>PIC</th><th>Monitoring</th></tr></thead><tbody>';
    dataBab3.program.forEach(p => {
      html += '<tr><td>' + p.nama + '</td><td>' + p.target + '</td><td>' + p.pic + '</td><td>' + p.monitoring + '</td></tr>';
    });
    html += '</tbody></table>';
  }
  document.getElementById('bab3Content').innerHTML = html;
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  renderHighRisk();
  renderBank();
  renderData('all');
  renderEvidence();
  showBab3('temuan', document.querySelector('#bab3SubNav button'));
});
</script>

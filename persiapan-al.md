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

  /* ===== Folder Shelf - 4 Folder ===== */
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
    scrollbar-color: #0d47a1 transparent;
    padding-bottom: 4px;
  }
  .folder-shelf::-webkit-scrollbar { height: 4px; }
  .folder-shelf::-webkit-scrollbar-track { background: rgba(13, 71, 161, 0.05); border-radius: 2px; }
  .folder-shelf::-webkit-scrollbar-thumb { background: #0d47a1; border-radius: 2px; }

  /* ===== Folder Tab Default ===== */
  .folder-tab {
    position: relative;
    flex: 1 1 0;
    min-width: 0;
    padding: 16px 10px 20px 10px;
    background: #ffffff;
    border-radius: 10px 10px 0 0;
    border: 1px solid #e0e0e0;
    border-bottom: none;
    cursor: pointer;
    text-align: center;
    font-weight: 600;
    font-size: 0.85rem;
    line-height: 1.2;
    color: #555;
    transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
    transform: translateY(4px);
    box-shadow: 0 -2px 6px rgba(0,0,0,0.05);
    white-space: normal;
    word-wrap: break-word;
    overflow-wrap: break-word;
  }
  .folder-tab::before {
    content: '';
    position: absolute;
    top: -7px;
    left: 22%;
    width: 56%;
    height: 7px;
    background: #f5f5f5;
    border-radius: 4px 4px 0 0;
    border: 1px solid #e0e0e0;
    border-bottom: none;
    transition: all 0.35s ease;
  }
  .folder-tab:hover {
    background: #f1f5f9;
    transform: translateY(0px);
    color: #0d47a1;
  }
  .folder-tab:hover::before { background: #f1f5f9; }

  /* Folder Aktif - Biru Tema */
  .folder-tab.active {
    background: #0d47a1;
    color: #ffffff;
    transform: translateY(-6px);
    z-index: 20;
    border-color: #0d47a1;
    box-shadow: 0 -4px 16px rgba(13, 71, 161, 0.25);
    font-weight: 700;
  }
  .folder-tab.active::before {
    background: #0d47a1;
    border-color: #0d47a1;
    height: 9px;
    top: -9px;
  }

  /* ===== MODE AL - ORANYE LEMBOT saat tidak aktif ===== */
  .folder-tab.mode-al {
    background: linear-gradient(180deg, #fff8e1 0%, #ffecb3 100%);
    color: #e65100;
    border-color: #ffcc80;
    box-shadow: 0 -2px 8px rgba(230, 81, 0, 0.12);
  }
  .folder-tab.mode-al::before {
    background: linear-gradient(180deg, #ffcc80 0%, #ffb74d 100%);
    border-color: #ffcc80;
  }
  .folder-tab.mode-al:hover {
    background: linear-gradient(180deg, #fff3e0 0%, #ffe0b2 100%);
    color: #bf360c;
    transform: translateY(0px);
    box-shadow: 0 -4px 12px rgba(230, 81, 0, 0.2);
  }
  .folder-tab.mode-al:hover::before {
    background: linear-gradient(180deg, #ffb74d 0%, #ffa726 100%);
    border-color: #ffb74d;
  }

  /* MODE AL - Saat AKTIF = biru tema + pulse */
  .folder-tab.mode-al.active {
    background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
    color: #ffffff;
    border-color: #0d47a1;
    box-shadow: 0 -6px 20px rgba(13, 71, 161, 0.5);
    animation: pulseMode 2.5s ease-in-out infinite;
  }
  .folder-tab.mode-al.active::before {
    background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
    border-color: #0d47a1;
    height: 9px;
    top: -9px;
  }
  @keyframes pulseMode {
    0%, 100% { box-shadow: 0 -6px 20px rgba(13, 71, 161, 0.5); }
    50% { box-shadow: 0 -6px 28px rgba(13, 71, 161, 0.7); }
  }

  /* ===== Content Area ===== */
  .al-content {
    background: #ffffff;
    border: 1px solid #e0e0e0;
    border-top: 3px solid #0d47a1;
    border-radius: 0 0 16px 16px;
    padding: 28px;
    min-height: 500px;
    box-shadow: 0 8px 24px rgba(0,0,0,0.06);
    position: relative;
    z-index: 5;
    margin-top: -1px;
  }

  .al-panel { display: none; animation: fadeIn 0.3s ease; }
  .al-panel.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

  /* ===== Dashboard ===== */
  .dash-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 20px;
    background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
    color: white;
    border-radius: 10px;
    margin-bottom: 20px;
  }
  .dash-header h2 { margin: 0; font-size: 1.2rem; }
  .dash-header .h-badge {
    background: #ff6f00;
    padding: 8px 16px;
    border-radius: 20px;
    font-weight: 700;
    font-size: 1rem;
  }
  .overall-box {
    background: #f8fafc;
    border: 2px solid #e0e0e0;
    border-radius: 10px;
    padding: 20px;
    margin-bottom: 20px;
    text-align: center;
  }
  .overall-box .label { font-size: 0.85rem; color: #666; text-transform: uppercase; letter-spacing: 1px; font-weight: 600; }
  .overall-box .big-percent { font-size: 3rem; font-weight: 800; color: #0d47a1; margin: 8px 0; }
  .overall-box .bar { height: 14px; background: #e0e0e0; border-radius: 7px; overflow: hidden; margin-top: 8px; }
  .overall-box .bar-fill { height: 100%; background: linear-gradient(to right, #4caf50, #81c784); border-radius: 7px; }

  .kriteria-row {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px 0;
    border-bottom: 1px solid #f0f0f0;
  }
  .kriteria-row .k-label { width: 40px; font-weight: 700; color: #0d47a1; font-size: 0.9rem; }
  .kriteria-row .k-bar { flex: 1; height: 12px; background: #e0e0e0; border-radius: 6px; overflow: hidden; }
  .kriteria-row .k-bar-fill { height: 100%; border-radius: 6px; transition: width 0.6s; }
  .kriteria-row .k-bar-fill.siap { background: linear-gradient(to right, #4caf50, #81c784); }
  .kriteria-row .k-bar-fill.perlu { background: linear-gradient(to right, #ff9800, #ffb74d); }
  .kriteria-row .k-percent { width: 45px; font-weight: 700; text-align: right; color: #333; }
  .kriteria-row .k-status { width: 140px; text-align: center; font-size: 0.72rem; font-weight: 700; padding: 4px 10px; border-radius: 12px; text-transform: uppercase; letter-spacing: 0.5px; }
  .k-status.siap { background: #e8f5e9; color: #2e7d32; }
  .k-status.perlu { background: #fff3e0; color: #e65100; }

  .priority-box {
    background: #fff8e1;
    border-left: 4px solid #ff9800;
    padding: 16px 20px;
    border-radius: 8px;
    margin-top: 20px;
  }
  .priority-box h4 { margin: 0 0 10px 0; color: #e65100; font-size: 0.95rem; }
  .priority-box .item { padding: 4px 0; font-size: 0.9rem; color: #555; }

  .info-cards {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 20px;
  }
  .info-card {
    background: #f8fafc;
    border: 1px solid #e0e0e0;
    border-radius: 10px;
    padding: 16px;
    border-left: 4px solid #0d47a1;
  }
  .info-card .label { font-size: 0.78rem; color: #666; text-transform: uppercase; letter-spacing: 0.5px; font-weight: 600; }
  .info-card .value { font-size: 1.5rem; font-weight: 700; color: #0d47a1; margin-top: 4px; }
  .info-card .sub { font-size: 0.85rem; color: #666; margin-top: 4px; }

  /* ===== Kesiapan Kriteria ===== */
  .sub-nav { display: flex; gap: 4px; margin-bottom: 20px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
  .sub-nav button { padding: 10px 18px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.9rem; }
  .sub-nav button:hover { color: #0d47a1; background: #f8fafc; }
  .sub-nav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }

  .indicator-list { display: flex; flex-direction: column; gap: 6px; margin-bottom: 20px; }
  .indicator-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 12px 16px;
    background: white;
    border: 1px solid #e0e0e0;
    border-radius: 8px;
    cursor: pointer;
    transition: all 0.2s;
    border-left: 4px solid #4caf50;
  }
  .indicator-row:hover { background: #f8fafc; transform: translateX(2px); box-shadow: 0 2px 8px rgba(0,0,0,0.06); }
  .indicator-row.warn { border-left-color: #ff9800; }
  .indicator-row.active { background: #e3f2fd; border-color: #0d47a1; }
  .indicator-row .name { font-weight: 600; color: #333; }
  .indicator-row .status-icon { font-size: 1.2rem; font-weight: 700; }
  .indicator-row .status-icon.ready { color: #2e7d32; }
  .indicator-row .status-icon.warn { color: #e65100; }

  /* Detail Indikator - 5 Komponen */
  .detail-panel {
    background: #f8fafc;
    border: 1px solid #e0e0e0;
    border-radius: 10px;
    padding: 20px;
    margin-top: 16px;
  }
  .detail-section {
    background: white;
    border-radius: 8px;
    padding: 14px 16px;
    margin-bottom: 10px;
    border-left: 4px solid #0d47a1;
  }
  .detail-section.klaim { border-left-color: #0d47a1; }
  .detail-section.jawaban { border-left-color: #4caf50; }
  .detail-section.data { border-left-color: #2196f3; }
  .detail-section.bukti { border-left-color: #9c27b0; }
  .detail-section.tindak { border-left-color: #ff9800; }
  .detail-section .section-title {
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: 700;
    margin-bottom: 6px;
    color: #666;
  }
  .detail-section .section-content { font-size: 0.92rem; color: #333; line-height: 1.5; }
  .detail-section ul { margin: 4px 0 0 0; padding-left: 20px; }
  .detail-section ul li { padding: 2px 0; font-size: 0.9rem; }
  .pic-tag {
    display: inline-block;
    background: #0d47a1;
    color: white;
    padding: 4px 12px;
    border-radius: 12px;
    font-size: 0.8rem;
    font-weight: 600;
    margin-top: 12px;
  }

  /* ===== Simulasi AL ===== */
  .sim-mode-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 10px;
    margin-bottom: 20px;
  }
  .sim-mode-btn {
    padding: 14px;
    background: white;
    border: 2px solid #e0e0e0;
    border-radius: 8px;
    cursor: pointer;
    text-align: center;
    font-weight: 600;
    font-size: 0.85rem;
    color: #555;
    transition: all 0.2s;
  }
  .sim-mode-btn:hover { border-color: #0d47a1; color: #0d47a1; transform: translateY(-2px); }
  .sim-mode-btn.active { background: #0d47a1; color: white; border-color: #0d47a1; }
  .sim-mode-btn.critical { border-color: #f44336; color: #c62828; }
  .sim-mode-btn.critical.active { background: #c62828; color: white; }
  .sim-mode-btn.pic { border-color: #ff9800; color: #e65100; }
  .sim-mode-btn.pic.active { background: #e65100; color: white; }

  .sim-question-box {
    background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
    color: white;
    padding: 24px;
    border-radius: 12px;
    margin-bottom: 16px;
  }
  .sim-question-box .q-label { font-size: 0.78rem; text-transform: uppercase; letter-spacing: 1px; opacity: 0.8; margin-bottom: 8px; }
  .sim-question-box .q-text { font-size: 1.1rem; font-weight: 600; line-height: 1.5; }
  .sim-timer {
    display: inline-block;
    background: #ff6f00;
    padding: 6px 14px;
    border-radius: 20px;
    font-weight: 700;
    font-size: 0.9rem;
    margin-top: 12px;
  }

  .sim-answer-box {
    background: white;
    border: 2px solid #e0e0e0;
    border-radius: 10px;
    padding: 18px;
    margin-bottom: 12px;
  }
  .sim-answer-box h4 { margin: 0 0 10px 0; color: #0d47a1; font-size: 0.95rem; }
  .sim-answer-box ul { margin: 0; padding-left: 20px; }
  .sim-answer-box ul li { padding: 3px 0; font-size: 0.9rem; }

  .followup-box {
    background: #fff8e1;
    border-left: 4px solid #ff9800;
    padding: 14px 18px;
    border-radius: 8px;
    margin: 12px 0;
  }
  .followup-box h4 { margin: 0 0 8px 0; color: #e65100; font-size: 0.9rem; }
  .followup-box .item { padding: 3px 0; font-size: 0.88rem; color: #555; }

  .score-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 6px;
    margin-top: 16px;
  }
  .score-btn {
    padding: 12px 6px;
    background: white;
    border: 2px solid #e0e0e0;
    border-radius: 8px;
    cursor: pointer;
    text-align: center;
    font-weight: 700;
    font-size: 0.85rem;
    color: #555;
    transition: all 0.2s;
  }
  .score-btn:hover { border-color: #0d47a1; color: #0d47a1; }
  .score-btn .score-label { font-size: 0.7rem; font-weight: 500; color: #888; display: block; margin-top: 2px; }

  /* ===== Mode AL - TEMA BIRU ===== */
  .mode-al-container {
    background: linear-gradient(135deg, #0a3a8a 0%, #0d47a1 50%, #1565c0 100%);
    color: white;
    padding: 32px;
    border-radius: 12px;
    margin: -28px;
    min-height: 600px;
  }
  .mode-al-container h2 { margin: 0 0 8px 0; font-size: 1.4rem; text-align: center; }
  .mode-al-container .subtitle { text-align: center; opacity: 0.85; font-size: 0.9rem; margin-bottom: 20px; }
  .mode-al-search {
    width: 100%;
    max-width: 700px;
    padding: 16px 24px;
    border-radius: 30px;
    border: 2px solid rgba(255,255,255,0.3);
    background: rgba(255,255,255,0.1);
    color: white;
    font-size: 1rem;
    margin: 0 auto 20px auto;
    display: block;
    backdrop-filter: blur(4px);
  }
  .mode-al-search::placeholder { color: rgba(255,255,255,0.6); }
  .mode-al-search:focus { outline: none; border-color: #fff; background: rgba(255,255,255,0.15); }

  .kriteria-chips {
    display: flex;
    gap: 6px;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 24px;
  }
  .kriteria-chip {
    padding: 8px 14px;
    background: rgba(255,255,255,0.15);
    border: 1px solid rgba(255,255,255,0.3);
    border-radius: 20px;
    color: white;
    cursor: pointer;
    font-weight: 600;
    font-size: 0.82rem;
    transition: all 0.2s;
  }
  .kriteria-chip:hover { background: rgba(255,255,255,0.25); }
  .kriteria-chip.active { background: white; color: #0d47a1; border-color: white; }

  .evidence-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 10px;
    max-width: 900px;
    margin: 0 auto;
  }
  .evidence-btn {
    background: rgba(255,255,255,0.12);
    color: white;
    padding: 14px 10px;
    border-radius: 8px;
    border: 1px solid rgba(255,255,255,0.2);
    cursor: pointer;
    font-weight: 600;
    font-size: 0.85rem;
    text-align: center;
    transition: all 0.2s;
  }
  .evidence-btn:hover { background: rgba(255,255,255,0.25); transform: translateY(-2px); }

  .search-result {
    background: white;
    color: #333;
    border-radius: 12px;
    padding: 20px;
    margin-top: 20px;
    max-width: 900px;
    margin-left: auto;
    margin-right: auto;
    display: none;
  }
  .search-result.active { display: block; animation: fadeIn 0.3s ease; }
  .search-result h3 { color: #0d47a1; margin: 0 0 12px 0; font-size: 1rem; }
  .search-result .result-section {
    background: #f8fafc;
    border-radius: 8px;
    padding: 12px 14px;
    margin-bottom: 8px;
    border-left: 4px solid #0d47a1;
  }
  .search-result .result-section .section-title {
    font-size: 0.72rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: 700;
    color: #0d47a1;
    margin-bottom: 4px;
  }
  .search-result .result-section .section-content { font-size: 0.88rem; color: #333; }
  .search-result .result-section ul { margin: 4px 0 0 0; padding-left: 18px; }
  .search-result .result-section ul li { font-size: 0.85rem; padding: 2px 0; }
  .search-result .result-section.followup { border-left-color: #ff9800; }
  .search-result .result-section.followup .section-title { color: #e65100; }

  /* ===== Responsive ===== */
  @media (max-width: 767px) {
    .folder-shelf { gap: 6px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
    .folder-shelf::-webkit-scrollbar { display: none; }
    .folder-tab { min-width: 110px; flex: 0 0 auto; font-size: 0.8rem; }
    .al-content { padding: 20px; }
    .info-cards { grid-template-columns: 1fr; }
    .kriteria-row { flex-wrap: wrap; }
    .kriteria-row .k-status { width: auto; margin-top: 4px; }
    .score-grid { grid-template-columns: repeat(5, 1fr); }
    .score-btn .score-label { display: none; }
    .mode-al-container { padding: 20px; margin: -20px; }
    .dash-header { flex-direction: column; gap: 10px; text-align: center; }
  }
</style>

<!-- ===== KABINET FOLDER NAV ===== -->
<div class="cabinet-container">
  <div class="folder-shelf">
    <div class="folder-tab active" onclick="showPanel('dashboard', this)">📊<br>DASHBOARD</div>
    <div class="folder-tab" onclick="showPanel('kesiapan', this)">📑<br>KESIAPAN KRITERIA</div>
    <div class="folder-tab" onclick="showPanel('simulasi', this)">🎯<br>SIMULASI AL</div>
    <div class="folder-tab mode-al" onclick="showPanel('modeal', this)">🚀<br>MODE AL</div>
  </div>

  <!-- ===== AREA KONTEN ===== -->
  <div class="al-content" id="alContent">

    <!-- ========== DASHBOARD ========== -->
    <div class="al-panel active" id="panel-dashboard">
      <div class="dash-header">
        <h2>PERSIAPAN AL PSBM</h2>
        <div class="h-badge">H-30</div>
      </div>

      <div class="overall-box">
        <div class="label">Kesiapan Keseluruhan</div>
        <div class="big-percent">86%</div>
        <div class="bar"><div class="bar-fill" style="width: 86%;"></div></div>
      </div>

      <div class="kriteria-row"><div class="k-label">C.1</div><div class="k-bar"><div class="k-bar-fill siap" style="width:95%;"></div></div><div class="k-percent">95%</div><div class="k-status siap">SIAP</div></div>
      <div class="kriteria-row"><div class="k-label">C.2</div><div class="k-bar"><div class="k-bar-fill siap" style="width:91%;"></div></div><div class="k-percent">91%</div><div class="k-status siap">SIAP</div></div>
      <div class="kriteria-row"><div class="k-label">C.3</div><div class="k-bar"><div class="k-bar-fill perlu" style="width:84%;"></div></div><div class="k-percent">84%</div><div class="k-status perlu">PERLU PERBAIKAN</div></div>
      <div class="kriteria-row"><div class="k-label">C.4</div><div class="k-bar"><div class="k-bar-fill siap" style="width:96%;"></div></div><div class="k-percent">96%</div><div class="k-status siap">SIAP</div></div>
      <div class="kriteria-row"><div class="k-label">C.5</div><div class="k-bar"><div class="k-bar-fill siap" style="width:92%;"></div></div><div class="k-percent">92%</div><div class="k-status siap">SIAP</div></div>
      <div class="kriteria-row"><div class="k-label">C.6</div><div class="k-bar"><div class="k-bar-fill perlu" style="width:85%;"></div></div><div class="k-percent">85%</div><div class="k-status perlu">PERLU PERBAIKAN</div></div>
      <div class="kriteria-row"><div class="k-label">C.7</div><div class="k-bar"><div class="k-bar-fill perlu" style="width:83%;"></div></div><div class="k-percent">83%</div><div class="k-status perlu">PERLU PERBAIKAN</div></div>

      <div class="priority-box">
        <h4>⚠️ PRIORITAS</h4>
        <div class="item">🔴 <strong>2 bukti kritis</strong> belum siap</div>
        <div class="item">🟠 <strong>3 jawaban</strong> belum tervalidasi</div>
        <div class="item">🟡 <strong>4 PIC</strong> perlu latihan</div>
      </div>

      <div class="info-cards">
        <div class="info-card">
          <div class="label">Mock AL Terakhir</div>
          <div class="value">3.2 / 4</div>
          <div class="sub">Skor rata-rata tim</div>
        </div>
        <div class="info-card">
          <div class="label">Target Terdekat</div>
          <div class="value">H-14</div>
          <div class="sub">Mock AL II</div>
        </div>
      </div>
    </div>

    <!-- ========== KESIAPAN KRITERIA ========== -->
    <div class="al-panel" id="panel-kesiapan">
      <h2 style="color:#0d47a1; margin-top:0;">Kesiapan Kriteria</h2>
      <div class="sub-nav" id="kesiapanSubNav">
        <button class="active" onclick="showKesiapan('c1', this)">C.1</button>
        <button onclick="showKesiapan('c2', this)">C.2</button>
        <button onclick="showKesiapan('c3', this)">C.3</button>
        <button onclick="showKesiapan('c4', this)">C.4</button>
        <button onclick="showKesiapan('c5', this)">C.5</button>
        <button onclick="showKesiapan('c6', this)">C.6</button>
        <button onclick="showKesiapan('c7', this)">C.7</button>
      </div>
      <div id="kesiapanContent"></div>
    </div>

    <!-- ========== SIMULASI AL ========== -->
    <div class="al-panel" id="panel-simulasi">
      <h2 style="color:#0d47a1; margin-top:0;">Simulasi Asesmen Lapangan</h2>
      <p style="color:#666; font-size:0.9rem; margin-top:-4px;">Latih tim menghadapi pertanyaan asesor dengan mode yang realistis.</p>

      <h4 style="color:#0d47a1; margin:20px 0 10px 0;">PILIH MODE</h4>
      <div class="sim-mode-grid">
        <div class="sim-mode-btn active" onclick="setSimMode('semua', this)">📚 Semua Kriteria</div>
        <div class="sim-mode-btn" onclick="setSimMode('c1', this)">C.1</div>
        <div class="sim-mode-btn" onclick="setSimMode('c2', this)">C.2</div>
        <div class="sim-mode-btn" onclick="setSimMode('c3', this)">C.3</div>
        <div class="sim-mode-btn" onclick="setSimMode('c4', this)">C.4</div>
        <div class="sim-mode-btn" onclick="setSimMode('c5', this)">C.5</div>
        <div class="sim-mode-btn" onclick="setSimMode('c6', this)">C.6</div>
        <div class="sim-mode-btn" onclick="setSimMode('c7', this)">C.7</div>
        <div class="sim-mode-btn critical" onclick="setSimMode('critical', this)">🔥 Pertanyaan Kritis</div>
        <div class="sim-mode-btn pic" onclick="setSimMode('pic', this)">🎯 Khusus PIC</div>
      </div>

      <div id="simulasiContent">
        <div class="sim-question-box">
          <div class="q-label">Asesor bertanya:</div>
          <div class="q-text">Bagaimana PSBM memastikan bahwa CPL sesuai dengan kebutuhan industri?</div>
          <div class="sim-timer">⏱ 00:48</div>
        </div>

        <div class="sim-answer-box">
          <h4>✅ JAWABAN IDEAL</h4>
          <p style="font-size:0.9rem; color:#333; line-height:1.5; margin:0 0 10px 0;">PSBM melakukan tinjauan CPL setiap 2 tahun melalui mekanisme terstruktur yang melibatkan tracer study, survei pengguna lulusan, dan forum industri.</p>
          <p style="font-size:0.85rem; font-weight:600; color:#0d47a1; margin:8px 0 4px 0;">Data yang seharusnya disebut:</p>
          <ul>
            <li>✓ Tracer study response rate 68%</li>
            <li>✓ Survei pengguna lulusan 45 responden</li>
            <li>✓ Forum industri tahunan (3 mitra utama)</li>
            <li>✓ Workshop OBE 2024 dengan 3 narasumber eksternal</li>
          </ul>
          <p style="font-size:0.85rem; font-weight:600; color:#0d47a1; margin:8px 0 4px 0;">Bukti:</p>
          <ul>
            <li>✓ NADK PSBM 2020</li>
            <li>✓ Laporan Tracer Study 2024</li>
            <li>✓ Notulensi Forum Industri 2024</li>
            <li>✓ Matriks Profil–CPL hasil revisi</li>
          </ul>
        </div>

        <div class="followup-box">
          <h4>🔍 FOLLOW-UP ASESOR</h4>
          <div class="item">→ Apa masukan konkret dari industri?</div>
          <div class="item">→ Apa yang berubah dari tinjauan terakhir?</div>
          <div class="item">→ Mana bukti tindak lanjutnya?</div>
          <div class="item">→ Bagaimana dampaknya terhadap kurikulum?</div>
        </div>

        <h4 style="color:#0d47a1; margin:20px 0 8px 0;">BERI SKOR</h4>
        <div class="score-grid">
          <div class="score-btn" onclick="giveScore(0)">0<span class="score-label">Tidak menjawab</span></div>
          <div class="score-btn" onclick="giveScore(1)">1<span class="score-label">Jawaban umum</span></div>
          <div class="score-btn" onclick="giveScore(2)">2<span class="score-label">+ Data</span></div>
          <div class="score-btn" onclick="giveScore(3)">3<span class="score-label">+ Data + Bukti</span></div>
          <div class="score-btn" onclick="giveScore(4)">4<span class="score-label">+ Tindak Lanjut</span></div>
        </div>
      </div>
    </div>

    <!-- ========== MODE AL ========== -->
    <div class="al-panel" id="panel-modeal">
      <div class="mode-al-container">
        <h2>🚀 PSBM — MODE ASESMEN LAPANGAN</h2>
        <div class="subtitle">Cari pertanyaan, data, atau bukti dengan cepat</div>

        <input type="text" class="mode-al-search" id="modeAlSearch" placeholder="🔎 Contoh: penelitian mahasiswa, tinjauan CPL, tracer study..." oninput="searchModeAL()">

        <div class="kriteria-chips">
          <div class="kriteria-chip active" onclick="setKriteriaChip(this)">C.1</div>
          <div class="kriteria-chip" onclick="setKriteriaChip(this)">C.2</div>
          <div class="kriteria-chip" onclick="setKriteriaChip(this)">C.3</div>
          <div class="kriteria-chip" onclick="setKriteriaChip(this)">C.4</div>
          <div class="kriteria-chip" onclick="setKriteriaChip(this)">C.5</div>
          <div class="kriteria-chip" onclick="setKriteriaChip(this)">C.6</div>
          <div class="kriteria-chip" onclick="setKriteriaChip(this)">C.7</div>
        </div>

        <h3 style="text-align:center; margin:20px 0 12px 0; font-size:0.9rem; letter-spacing:1px; opacity:0.9;">BUKTI UTAMA</h3>
        <div class="evidence-grid">
          <div class="evidence-btn" onclick="quickSearch('led')">📄 LED</div>
          <div class="evidence-btn" onclick="quickSearch('lkps')">📊 LKPS</div>
          <div class="evidence-btn" onclick="quickSearch('vmts')">🎯 VMTS</div>
          <div class="evidence-btn" onclick="quickSearch('kurikulum')">📘 Kurikulum</div>
          <div class="evidence-btn" onclick="quickSearch('cpl')">🎓 CPL</div>
          <div class="evidence-btn" onclick="quickSearch('rps')">📝 RPS</div>
          <div class="evidence-btn" onclick="quickSearch('roadmap')">🗺️ Roadmap</div>
          <div class="evidence-btn" onclick="quickSearch('penelitian')">🔬 Penelitian</div>
          <div class="evidence-btn" onclick="quickSearch('pkm')">🤝 PkM</div>
          <div class="evidence-btn" onclick="quickSearch('tracer')">📈 Tracer</div>
          <div class="evidence-btn" onclick="quickSearch('kerja sama')">🤝 Kerja Sama</div>
          <div class="evidence-btn" onclick="quickSearch('ami')">🔍 AMI/RTM</div>
        </div>

        <div class="search-result" id="searchResult"></div>
      </div>
    </div>

  </div>
</div>

<script>
// ===== DATA KRITERIA & INDIKATOR =====
const dataKesiapan = {
  c1: {
    title: 'C.1 VMTS',
    indicators: [
      { name: 'Kekhasan VMTS', status: 'ready' },
      { name: 'Mekanisme Penyusunan', status: 'ready' },
      { name: 'Tingkat Pemahaman Stakeholder', status: 'ready' },
      { name: 'Sosialisasi VMTS', status: 'ready' },
      { name: 'Pencapaian Sasaran', status: 'ready' }
    ]
  },
  c2: {
    title: 'C.2 Tata Pamong, Tata Kelola, Kerja Sama, Keuangan',
    indicators: [
      { name: 'Sistem Tata Pamong', status: 'ready' },
      { name: 'Kerja Sama Tridharma', status: 'ready' },
      { name: 'Implementasi Kerja Sama', status: 'warn' },
      { name: 'Pengelolaan Keuangan', status: 'ready' },
      { name: 'Transparansi & Akuntabilitas', status: 'ready' }
    ]
  },
  c3: {
    title: 'C.3 Relevansi Pendidikan, Penelitian & PkM',
    indicators: [
      { name: 'Profil Lulusan', status: 'ready', detail: 'klaimCPL' },
      { name: 'Kesesuaian CPL', status: 'ready' },
      { name: 'Tinjauan CPL', status: 'warn', detail: 'tinjauanCPL' },
      { name: 'RPS', status: 'ready' },
      { name: 'Tinjauan RPS', status: 'warn' },
      { name: 'Proses Pembelajaran', status: 'ready' },
      { name: 'Penelitian DTPS', status: 'warn' },
      { name: 'PkM DTPS', status: 'ready' },
      { name: 'Evaluasi Capaian', status: 'warn' },
      { name: 'SWOT Pengembangan', status: 'ready' }
    ]
  },
  c4: {
    title: 'C.4 Sumber Daya Manusia',
    indicators: [
      { name: 'Profil DTPS', status: 'ready' },
      { name: 'Tenaga Kependidikan', status: 'ready' },
      { name: 'Beban Kerja Dosen', status: 'ready' },
      { name: 'Publikasi Ilmiah', status: 'ready' },
      { name: 'Rekognisi DTPS', status: 'ready' }
    ]
  },
  c5: {
    title: 'C.5 Sarana, Prasarana & K3L',
    indicators: [
      { name: 'Prasarana Pembelajaran', status: 'ready' },
      { name: 'Peralatan Laboratorium', status: 'ready' },
      { name: 'Dokumen K3L', status: 'warn' },
      { name: 'Fasilitas K3L', status: 'ready' }
    ]
  },
  c6: {
    title: 'C.6 Mahasiswa dan Luaran',
    indicators: [
      { name: 'Rasio Mahasiswa:DTPS', status: 'ready' },
      { name: 'Tracer Study', status: 'warn' },
      { name: 'Prestasi Mahasiswa', status: 'ready' },
      { name: 'Kinerja Lulusan', status: 'warn' },
      { name: 'Kesesuaian Bidang Kerja', status: 'warn' }
    ]
  },
  c7: {
    title: 'C.7 Sistem Penjaminan Mutu',
    indicators: [
      { name: 'Unit Penjaminan Mutu', status: 'ready' },
      { name: 'Perangkat SPMI', status: 'ready' },
      { name: 'Siklus PPEPP', status: 'warn' },
      { name: 'Audit Mutu Internal', status: 'warn' },
      { name: 'Kepuasan Stakeholder', status: 'warn' }
    ]
  }
};

// ===== DETAIL 5 KOMPONEN =====
const dataDetail = {
  tinjauanCPL: {
    klaim: 'PSBM melakukan tinjauan CPL secara berkala sebagai bagian dari evaluasi dan pengembangan kurikulum untuk menjaga relevansi dengan kebutuhan industri dan perkembangan IPTEKS.',
    jawaban: 'PSBM melakukan tinjauan CPL setiap 2 tahun melalui mekanisme terstruktur yang melibatkan tracer study, survei pengguna lulusan, forum industri, dan workshop OBE. Hasil tinjauan dituangkan dalam revisi NADK dan matriks profil–CPL.',
    data: ['Kurikulum 2020 (NADK)', 'Workshop OBE 2024', '11 dosen terlibat', '3 alumni sebagai narasumber', '3 narasumber eksternal dari industri'],
    bukti: ['NADK PSBM 2020', 'Laporan Workshop OBE 2024', 'Matriks Profil–CPL', 'Masukan Industri (notulensi forum)', 'Dokumen Tindak Lanjut'],
    tindak: 'Penguatan keterkaitan PL–CPL–bidang kajian dan pengembangan kurikulum berbasis OBE yang lebih adaptif terhadap kebutuhan industri digital.',
    pic: 'Tim Kurikulum (VF + BU)'
  },
  klaimCPL: {
    klaim: 'PSBM merumuskan profil lulusan dan CPL yang selaras dengan KKNI Level 6, kebutuhan industri broadband multimedia, dan visi keilmuan program studi.',
    jawaban: 'Profil lulusan PSBM disusun berdasarkan analisis kebutuhan industri melalui tracer study, forum industri, dan benchmarking dengan program studi sejenis. CPL diturunkan dari profil lulusan dan dipetakan ke setiap mata kuliah.',
    data: ['12 CPL terdefinisi', 'KKNI Level 6', '6 profil lulusan', 'Benchmarking 3 PT'],
    bukti: ['NADK PSBM 2020', 'Matriks Profil–CPL', 'Laporan Analisis Kebutuhan', 'Notulensi Forum Industri'],
    tindak: 'Pemutakhiran CPL berbasis hasil tracer study 2024 dan masukan industri pada forum tahunan.',
    pic: 'Tim Kurikulum'
  }
};

// ===== DATA MODE AL (Search) =====
const dataModeAL = {
  'penelitian mahasiswa': {
    title: 'C.3 > PENELITIAN',
    jawaban: 'PSBM melibatkan mahasiswa dalam penelitian DTPS melalui mekanisme Tugas Akhir, proyek mata kuliah, dan asisten riset. Keterlibatan ini terdokumentasi dalam peta jalan penelitian dan laporan tahunan.',
    data: ['45 penelitian DTPS (3 tahun)', '12 penelitian melibatkan mahasiswa', '26,67% keterlibatan', '8 TA berbasis penelitian dosen'],
    bukti: ['LKPS Tabel 6.h.1', 'Daftar Penelitian DTPS', 'Bukti Keterlibatan Mahasiswa', 'Roadmap Penelitian 2020-2025'],
    tindak: 'Integrasi penelitian dosen dengan TA dan proyek mahasiswa ditingkatkan menjadi minimal 40% pada 2026.',
    followup: ['Kenapa masih rendah (26,67%)?', 'Apa tindak lanjut konkret?', 'Apa target berikutnya?']
  },
  'tinjauan cpl': {
    title: 'C.3 > TINJAUAN CPL',
    jawaban: 'PSBM melakukan tinjauan CPL setiap 2 tahun melalui mekanisme terstruktur yang melibatkan tracer study, survei pengguna, dan forum industri.',
    data: ['Kurikulum 2020', 'Workshop OBE 2024', '11 dosen terlibat', '3 alumni + 3 narasumber eksternal'],
    bukti: ['NADK PSBM 2020', 'Laporan Workshop OBE 2024', 'Matriks Profil–CPL', 'Masukan Industri'],
    tindak: 'Penguatan PL–CPL–bidang kajian dan pengembangan kurikulum berbasis OBE.',
    followup: ['Apa masukan industri?', 'Apa yang berubah?', 'Mana bukti tindak lanjut?', 'Bagaimana dampaknya?']
  },
  'tracer study': {
    title: 'C.6 > TRACER STUDY',
    jawaban: 'PSBM melaksanakan tracer study tahunan menggunakan kuesioner standar DIKTI dengan response rate 68% pada 2024.',
    data: ['Response rate 68% (2024)', 'Minimal 30% (syarat LAM)', 'Waktu tunggu < 6 bulan: 72%', 'Kesesuaian bidang tinggi: 65%'],
    bukti: ['Laporan Tracer Study 2024', 'Kuesioner DIKTI', 'Rekapitulasi Responden'],
    tindak: 'Kolaborasi dengan career center + insentif alumni untuk meningkatkan response rate menjadi 80%.',
    followup: ['Kenapa response rate masih 68%?', 'Apa strategi peningkatan?', 'Bagaimana kualitas pekerjaan lulusan?']
  },
  'led': { title: 'DOKUMEN UTAMA', jawaban: 'Laporan Evaluasi Diri (LED) PSBM 2026 disusun berdasarkan 7 kriteria LAM Teknik Edisi 2025.', data: ['7 kriteria', '200+ halaman', 'Terintegrasi dengan LKPS'], bukti: ['File LED.pdf', 'File LKPS.pdf'], tindak: 'Finalisasi minggu ke-2 sebelum submit.', followup: [] },
  'lkps': { title: 'DOKUMEN UTAMA', jawaban: 'Laporan Kinerja Program Studi berisi data kuantitatif 3 tahun terakhir (TS-2 s.d. TS).', data: ['31 tabel LKPS', 'Data TS-2, TS-1, TS'], bukti: ['File LKPS.pdf', 'Google Sheet LKPS'], tindak: 'Verifikasi data dengan PD-Dikti dan SINTA.', followup: [] },
  'vmts': { title: 'C.1 > VMTS', jawaban: 'VMTS PSBM selaras dengan VMTS PNJ dan visi keilmuan broadband multimedia.', data: ['SK VMTS PT', 'SK VMTS UPPS', 'Visi Keilmuan PS'], bukti: ['SK VMTS PT', 'SK VMTS UPPS', 'Dokumen Visi Keilmuan'], tindak: 'Sosialisasi VMTS ke seluruh stakeholder.', followup: [] },
  'kurikulum': { title: 'C.3 > KURIKULUM', jawaban: 'Kurikulum PSBM berbasis KKNI Level 6 dan OBE dengan 144 SKS.', data: ['144 SKS', 'KKNI Level 6', 'OBE 2020', 'Revisi 2025'], bukti: ['Dokumen Kurikulum', 'Matriks CPL-MK', 'RPS Lengkap'], tindak: 'Revisi Kurikulum OBE 2025 berbasis tracer study.', followup: [] },
  'cpl': { title: 'C.3 > CPL', jawaban: '12 CPL PSBM diturunkan dari profil lulusan dan dipetakan ke setiap MK.', data: ['12 CPL', '6 Profil Lulusan', 'Matriks CPL-MK lengkap'], bukti: ['NADK PSBM 2020', 'Matriks CPL-MK'], tindak: 'Tinjauan CPL berbasis tracer study 2024.', followup: [] },
  'rps': { title: 'C.3 > RPS', jawaban: 'Seluruh MK dilengkapi RPS yang ditinjau setiap 2 tahun.', data: ['100% MK punya RPS', 'Tinjauan 2024'], bukti: ['Kumpulan RPS', 'Laporan Tinjauan RPS'], tindak: 'Update RPS berbasis hasil penelitian terbaru.', followup: [] },
  'roadmap': { title: 'C.3 > ROADMAP', jawaban: 'Peta jalan penelitian & PkM PSBM 2020-2025 selaras dengan visi keilmuan.', data: ['Roadmap 2020-2025', '4 bidang fokus'], bukti: ['Dokumen Roadmap', 'Laporan Tahunan'], tindak: 'Perpanjangan roadmap 2025-2030.', followup: [] },
  'penelitian': { title: 'C.3 > PENELITIAN DTPS', jawaban: 'Penelitian DTPS didanai dari PT, nasional, dan mandiri.', data: ['45 judul (3 tahun)', '15 PT', '20 nasional', '10 mandiri'], bukti: ['LKPS Tabel 3.b', 'Daftar Penelitian'], tindak: 'Peningkatan publikasi internasional bereputasi.', followup: [] },
  'pkm': { title: 'C.3 > PkM', jawaban: 'PkM DTPS relevan dengan bidang studi dan melibatkan masyarakat.', data: ['28 judul PkM (3 tahun)'], bukti: ['LKPS Tabel 3.c', 'Laporan PkM'], tindak: 'Peningkatan adopsi hasil PkM oleh masyarakat.', followup: [] },
  'kerja sama': { title: 'C.2 > KERJA SAMA', jawaban: 'Kerja sama tridharma dengan mitra nasional dan internasional.', data: ['25 MoU aktif', '15 implementasi'], bukti: ['Daftar MoU', 'Bukti Implementasi'], tindak: 'Peningkatan implementasi kerja sama.', followup: [] },
  'ami': { title: 'C.7 > AMI/RTM', jawaban: 'Audit Mutu Internal dilaksanakan tahunan dengan tindak lanjut terdokumentasi.', data: ['AMI 2025', '15 temuan', 'RTM 2025'], bukti: ['Laporan AMI 2025', 'Notulensi RTM', 'Rencana Tindak Lanjut'], tindak: 'Penyelesaian 15 temuan AMI sebelum AL.', followup: [] }
};

// ===== NAVIGATION =====
function showPanel(id, btn) {
  document.querySelectorAll('.al-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.folder-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  
  if (id === 'kesiapan') showKesiapan('c1', document.querySelector('#kesiapanSubNav button'));
}

// ===== KESIAPAN KRITERIA =====
function showKesiapan(key, btn) {
  document.querySelectorAll('#kesiapanSubNav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  
  const k = dataKesiapan[key];
  let html = '<h3 style="color:#0d47a1; margin:0 0 16px 0;">' + k.title + '</h3>';
  html += '<div class="indicator-list">';
  k.indicators.forEach((ind, i) => {
    const warnClass = ind.status === 'warn' ? 'warn' : '';
    const iconClass = ind.status === 'ready' ? 'ready' : 'warn';
    const icon = ind.status === 'ready' ? '✓' : '⚠';
    html += '<div class="indicator-row ' + warnClass + '" onclick="showDetail(this, \'' + (ind.detail || '') + '\')">';
    html += '<div class="name">' + ind.name + '</div>';
    html += '<div class="status-icon ' + iconClass + '">' + icon + '</div>';
    html += '</div>';
  });
  html += '</div>';
  html += '<div id="detailContainer"></div>';
  
  document.getElementById('kesiapanContent').innerHTML = html;
}

function showDetail(row, detailKey) {
  document.querySelectorAll('.indicator-row').forEach(r => r.classList.remove('active'));
  row.classList.add('active');
  
  const container = document.getElementById('detailContainer');
  if (!detailKey || !dataDetail[detailKey]) {
    container.innerHTML = '<div class="detail-panel"><p style="color:#666; text-align:center;">Detail 5 komponen belum tersedia untuk indikator ini. Klik indikator lain atau hubungi koordinator.</p></div>';
    return;
  }
  
  const d = dataDetail[detailKey];
  let html = '<div class="detail-panel">';
  html += '<div class="detail-section klaim"><div class="section-title">1. KLAIM LED</div><div class="section-content">' + d.klaim + '</div></div>';
  html += '<div class="detail-section jawaban"><div class="section-title">2. JAWABAN AL</div><div class="section-content">' + d.jawaban + '</div></div>';
  html += '<div class="detail-section data"><div class="section-title">3. DATA KUNCI</div><ul>';
  d.data.forEach(item => { html += '<li>' + item + '</li>'; });
  html += '</ul></div>';
  html += '<div class="detail-section bukti"><div class="section-title">4. BUKTI</div><ul>';
  d.bukti.forEach(item => { html += '<li>✓ ' + item + '</li>'; });
  html += '</ul></div>';
  html += '<div class="detail-section tindak"><div class="section-title">5. TINDAK LANJUT / DAMPAK</div><div class="section-content">' + d.tindak + '</div></div>';
  html += '<div class="pic-tag">PIC: ' + d.pic + '</div>';
  html += '</div>';
  
  container.innerHTML = html;
}

// ===== SIMULASI AL =====
function setSimMode(mode, btn) {
  document.querySelectorAll('.sim-mode-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}

function giveScore(score) {
  const labels = ['Tidak menjawab', 'Jawaban umum', '+ Data', '+ Data + Bukti', '+ Tindak Lanjut'];
  alert('Skor: ' + score + ' — ' + labels[score] + '\n\nPertanyaan ini akan masuk daftar "skor <3" untuk latihan berikutnya.');
}

// ===== MODE AL =====
function setKriteriaChip(chip) {
  document.querySelectorAll('.kriteria-chip').forEach(c => c.classList.remove('active'));
  chip.classList.add('active');
}

function quickSearch(keyword) {
  document.getElementById('modeAlSearch').value = keyword.toLowerCase();
  searchModeAL();
}

function searchModeAL() {
  const query = document.getElementById('modeAlSearch').value.toLowerCase().trim();
  const resultDiv = document.getElementById('searchResult');
  
  if (!query) {
    resultDiv.classList.remove('active');
    return;
  }
  
  let found = null;
  for (const key in dataModeAL) {
    if (key.includes(query) || dataModeAL[key].title.toLowerCase().includes(query)) {
      found = dataModeAL[key];
      break;
    }
  }
  
  if (!found) {
    resultDiv.classList.remove('active');
    return;
  }
  
  let html = '<h3>' + found.title + '</h3>';
  html += '<div class="result-section"><div class="section-title">JAWABAN INTI</div><div class="section-content">' + found.jawaban + '</div></div>';
  
  html += '<div class="result-section"><div class="section-title">DATA KUNCI</div><ul>';
  found.data.forEach(d => { html += '<li>' + d + '</li>'; });
  html += '</ul></div>';
  
  html += '<div class="result-section"><div class="section-title">BUKTI</div><ul>';
  found.bukti.forEach(b => { html += '<li>✓ ' + b + '</li>'; });
  html += '</ul></div>';
  
  if (found.tindak) {
    html += '<div class="result-section"><div class="section-title">TINDAK LANJUT</div><div class="section-content">' + found.tindak + '</div></div>';
  }
  
  if (found.followup && found.followup.length > 0) {
    html += '<div class="result-section followup"><div class="section-title">FOLLOW-UP</div><ul>';
    found.followup.forEach(f => { html += '<li>→ ' + f + '</li>'; });
    html += '</ul></div>';
  }
  
  resultDiv.innerHTML = html;
  resultDiv.classList.add('active');
}
</script>

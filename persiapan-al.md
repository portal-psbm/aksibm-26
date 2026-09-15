---
layout: default
title: Persiapan AL
permalink: /persiapan-al/
---

<style>
  /* ===== AL Command Center Styles ===== */
  .al-header {
    background: linear-gradient(135deg, #0d47a1 0%, #1976d2 100%);
    color: white;
    padding: 24px;
    border-radius: 12px;
    margin-bottom: 20px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  }
  .al-header h1 { margin: 0; font-size: 1.6rem; }
  .al-header .subtitle { opacity: 0.9; font-size: 0.95rem; margin-top: 4px; }
  .al-header .h-countdown {
    display: inline-block;
    background: #ff6f00;
    padding: 6px 14px;
    border-radius: 20px;
    font-weight: 700;
    margin-top: 8px;
    font-size: 0.9rem;
  }

  /* Top Nav */
  .al-nav {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    background: #f1f5f9;
    padding: 10px;
    border-radius: 10px;
    margin-bottom: 20px;
    border: 1px solid #e0e0e0;
  }
  .al-nav button {
    flex: 1;
    min-width: 100px;
    padding: 10px 14px;
    background: transparent;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-weight: 600;
    color: #455a64;
    transition: all 0.2s;
    font-size: 0.88rem;
  }
  .al-nav button:hover { background: #e3f2fd; color: #0d47a1; }
  .al-nav button.active {
    background: #0d47a1;
    color: white;
    box-shadow: 0 2px 6px rgba(13,71,161,0.3);
  }

  /* Content Area */
  .al-content { min-height: 500px; }
  .al-panel { display: none; animation: fadeIn 0.3s ease; }
  .al-panel.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

  /* Cards */
  .card-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 16px;
    margin: 16px 0;
  }
  .stat-card {
    background: white;
    border-radius: 10px;
    padding: 18px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
    border-left: 4px solid #0d47a1;
  }
  .stat-card .label { font-size: 0.85rem; color: #666; margin-bottom: 6px; }
  .stat-card .value { font-size: 1.8rem; font-weight: 700; color: #0d47a1; }
  .stat-card .sub { font-size: 0.8rem; color: #888; margin-top: 4px; }

  /* Progress bars */
  .progress-row {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px 0;
    border-bottom: 1px solid #f0f0f0;
  }
  .progress-row .label { width: 60px; font-weight: 600; color: #0d47a1; }
  .progress-row .bar {
    flex: 1;
    height: 14px;
    background: #e0e0e0;
    border-radius: 7px;
    overflow: hidden;
    position: relative;
  }
  .progress-row .bar-fill {
    height: 100%;
    background: linear-gradient(to right, #4caf50, #81c784);
    border-radius: 7px;
    transition: width 0.6s;
  }
  .progress-row .bar-fill.review { background: linear-gradient(to right, #ff9800, #ffb74d); }
  .progress-row .bar-fill.risk { background: linear-gradient(to right, #f44336, #e57373); }
  .progress-row .percent { width: 40px; font-weight: 600; text-align: right; }
  .progress-row .status {
    width: 80px;
    text-align: center;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 3px 8px;
    border-radius: 12px;
  }
  .status-ready { background: #e8f5e9; color: #2e7d32; }
  .status-review { background: #fff3e0; color: #e65100; }
  .status-risk { background: #ffebee; color: #c62828; }

  /* Alert box */
  .alert-box {
    background: #fff8e1;
    border-left: 4px solid #ff9800;
    padding: 14px 18px;
    border-radius: 6px;
    margin: 16px 0;
  }
  .alert-box .item { padding: 4px 0; font-size: 0.92rem; }

  /* Sub-tabs for Kriteria */
  .sub-nav {
    display: flex;
    gap: 4px;
    margin-bottom: 16px;
    border-bottom: 2px solid #e0e0e0;
    flex-wrap: wrap;
  }
  .sub-nav button {
    padding: 8px 16px;
    background: transparent;
    border: none;
    cursor: pointer;
    font-weight: 600;
    color: #666;
    border-bottom: 3px solid transparent;
    margin-bottom: -2px;
    transition: all 0.2s;
  }
  .sub-nav button.active {
    color: #0d47a1;
    border-bottom-color: #0d47a1;
  }

  /* Indicator cards */
  .indicator-card {
    background: white;
    border-radius: 10px;
    padding: 16px;
    margin-bottom: 12px;
    box-shadow: 0 2px 6px rgba(0,0,0,0.06);
    border-left: 4px solid #4caf50;
  }
  .indicator-card.review { border-left-color: #ff9800; }
  .indicator-card.risk { border-left-color: #f44336; }
  .indicator-card .head {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 8px;
  }
  .indicator-card .title { font-weight: 700; color: #0d47a1; }
  .indicator-card .meta { font-size: 0.85rem; color: #666; margin: 4px 0; }
  .indicator-card .actions {
    display: flex;
    gap: 6px;
    margin-top: 10px;
  }
  .btn {
    padding: 6px 12px;
    border-radius: 6px;
    border: none;
    cursor: pointer;
    font-size: 0.85rem;
    font-weight: 600;
    transition: all 0.2s;
  }
  .btn-primary { background: #0d47a1; color: white; }
  .btn-primary:hover { background: #1976d2; }
  .btn-outline { background: white; color: #0d47a1; border: 1px solid #0d47a1; }
  .btn-outline:hover { background: #e3f2fd; }

  /* Search */
  .search-box {
    width: 100%;
    padding: 12px 16px;
    border: 2px solid #e0e0e0;
    border-radius: 8px;
    font-size: 1rem;
    margin-bottom: 12px;
  }
  .search-box:focus { outline: none; border-color: #0d47a1; }
  .filter-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 16px;
  }
  .filter-row select {
    padding: 8px 12px;
    border: 1px solid #e0e0e0;
    border-radius: 6px;
    background: white;
    font-size: 0.9rem;
  }

  /* Evidence list */
  .evidence-item {
    background: white;
    padding: 14px;
    border-radius: 8px;
    margin-bottom: 8px;
    border-left: 4px solid #4caf50;
    box-shadow: 0 1px 4px rgba(0,0,0,0.05);
  }
  .evidence-item.review { border-left-color: #ff9800; }
  .evidence-item.missing { border-left-color: #f44336; }
  .evidence-item .code { font-family: monospace; color: #0d47a1; font-weight: 700; }
  .evidence-item .path { font-size: 0.82rem; color: #888; margin-top: 2px; }

  /* Question card */
  .question-card {
    background: white;
    padding: 16px;
    border-radius: 10px;
    margin-bottom: 12px;
    box-shadow: 0 2px 6px rgba(0,0,0,0.06);
    border-left: 4px solid #0d47a1;
  }
  .question-card.critical { border-left-color: #f44336; }
  .question-card .q-code { font-family: monospace; color: #f44336; font-weight: 700; font-size: 0.85rem; }
  .question-card .q-text { font-size: 1rem; font-weight: 600; margin: 6px 0; }
  .question-card .q-meta { font-size: 0.85rem; color: #666; }

  /* PPEPP flow */
  .ppepp-flow {
    display: flex;
    flex-direction: column;
    gap: 0;
    margin: 20px 0;
  }
  .ppepp-step {
    background: white;
    padding: 16px 20px;
    border-left: 4px solid #0d47a1;
    position: relative;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  }
  .ppepp-step::after {
    content: '▼';
    position: absolute;
    bottom: -14px;
    left: 50%;
    transform: translateX(-50%);
    color: #0d47a1;
    font-size: 1.2rem;
  }
  .ppepp-step:last-child::after { display: none; }
  .ppepp-step .step-title { font-weight: 700; color: #0d47a1; margin-bottom: 4px; }
  .ppepp-step .step-content { font-size: 0.92rem; color: #555; }

  /* Risk table */
  .risk-table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 12px;
  }
  .risk-table th, .risk-table td {
    padding: 10px;
    text-align: left;
    border-bottom: 1px solid #e0e0e0;
    font-size: 0.9rem;
  }
  .risk-table th { background: #f1f5f9; color: #0d47a1; font-weight: 600; }
  .risk-badge {
    display: inline-block;
    padding: 3px 10px;
    border-radius: 12px;
    font-size: 0.78rem;
    font-weight: 700;
  }
  .risk-critical { background: #ffebee; color: #c62828; }
  .risk-high { background: #fff3e0; color: #e65100; }
  .risk-medium { background: #fff8e1; color: #f57c00; }
  .risk-resolved { background: #e8f5e9; color: #2e7d32; }

  /* Team cards */
  .team-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 14px;
  }
  .team-card {
    background: white;
    padding: 18px;
    border-radius: 10px;
    box-shadow: 0 2px 6px rgba(0,0,0,0.08);
    border-top: 4px solid #0d47a1;
  }
  .team-card .role { font-size: 0.82rem; color: #888; }
  .team-card .name { font-size: 1.1rem; font-weight: 700; color: #0d47a1; margin: 4px 0; }
  .team-card .stat { font-size: 0.88rem; color: #555; margin-top: 8px; }

  /* Checklist */
  .checklist-group {
    background: white;
    padding: 18px;
    border-radius: 10px;
    margin-bottom: 14px;
    box-shadow: 0 2px 6px rgba(0,0,0,0.06);
  }
  .checklist-group h4 { color: #0d47a1; margin: 0 0 12px 0; }
  .checklist-item {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 8px 0;
    border-bottom: 1px solid #f5f5f5;
  }
  .checklist-item input[type="checkbox"] { width: 18px; height: 18px; cursor: pointer; }
  .checklist-item.done label { text-decoration: line-through; color: #999; }

  /* Mode AL */
  .mode-al-view {
    background: #0d47a1;
    color: white;
    padding: 30px;
    border-radius: 12px;
    text-align: center;
  }
  .mode-al-view h2 { margin: 0 0 16px 0; font-size: 1.8rem; }
  .mode-al-view .search-big {
    width: 100%;
    max-width: 600px;
    padding: 14px 20px;
    border-radius: 30px;
    border: none;
    font-size: 1rem;
    margin: 16px 0;
  }
  .quick-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 10px;
    margin-top: 20px;
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
  }
  .quick-btn {
    background: rgba(255,255,255,0.15);
    color: white;
    padding: 14px;
    border-radius: 8px;
    border: 1px solid rgba(255,255,255,0.2);
    cursor: pointer;
    font-weight: 600;
    transition: all 0.2s;
  }
  .quick-btn:hover { background: rgba(255,255,255,0.25); }

  @media (max-width: 600px) {
    .al-nav button { min-width: 80px; font-size: 0.78rem; padding: 8px 10px; }
    .progress-row { flex-wrap: wrap; }
    .progress-row .label { width: 100%; }
  }
</style>

<!-- ===== HEADER ===== -->
<div class="al-header">
  <h1>🎯 PSBM — AL COMMAND CENTER</h1>
  <div class="subtitle">Persiapan Asesmen Lapangan • LAM Teknik 2026</div>
  <div class="h-countdown" id="hCountdown">H-30</div>
</div>

<!-- ===== TOP NAV ===== -->
<div class="al-nav">
  <button class="active" onclick="showPanel('dashboard', this)">📊 Dashboard</button>
  <button onclick="showPanel('kriteria', this)">📑 Kriteria</button>
  <button onclick="showPanel('bukti', this)">📎 Bukti</button>
  <button onclick="showPanel('pertanyaan', this)">❓ Pertanyaan</button>
  <button onclick="showPanel('mock', this)">🎭 Mock AL</button>
  <button onclick="showPanel('ppepp', this)">🔄 PPEPP</button>
  <button onclick="showPanel('risiko', this)">⚠️ Risiko</button>
  <button onclick="showPanel('tim', this)">👥 Tim/PIC</button>
  <button onclick="showPanel('checklist', this)">✅ Checklist</button>
  <button onclick="showPanel('modeal', this)">🚀 Mode AL</button>
</div>

<!-- ===== CONTENT AREA ===== -->
<div class="al-content">

  <!-- ===== DASHBOARD ===== -->
  <div class="al-panel active" id="panel-dashboard">
    <h2 style="color:#0d47a1;">Overall Readiness</h2>
    <div class="progress-row">
      <div class="bar" style="height:22px;">
        <div class="bar-fill" style="width:89%;"></div>
      </div>
      <div class="percent" style="font-size:1.2rem;">89%</div>
    </div>

    <div class="card-grid">
      <div class="stat-card">
        <div class="label">Evidence</div>
        <div class="value">142/150</div>
        <div class="sub">95% verified</div>
      </div>
      <div class="stat-card">
        <div class="label">Questions</div>
        <div class="value">126/140</div>
        <div class="sub">90% ready</div>
      </div>
      <div class="stat-card" style="border-left-color:#f44336;">
        <div class="label">Open Risk</div>
        <div class="value" style="color:#f44336;">6</div>
        <div class="sub">2 critical</div>
      </div>
      <div class="stat-card" style="border-left-color:#4caf50;">
        <div class="label">Mock Score</div>
        <div class="value" style="color:#4caf50;">3.4</div>
        <div class="sub">/4.0 average</div>
      </div>
    </div>

    <h3 style="color:#0d47a1; margin-top:24px;">Kesiapan Per Kriteria</h3>
    <div class="progress-row">
      <div class="label">C.1</div>
      <div class="bar"><div class="bar-fill" style="width:96%;"></div></div>
      <div class="percent">96%</div>
      <div class="status status-ready">READY</div>
    </div>
    <div class="progress-row">
      <div class="label">C.2</div>
      <div class="bar"><div class="bar-fill" style="width:92%;"></div></div>
      <div class="percent">92%</div>
      <div class="status status-ready">READY</div>
    </div>
    <div class="progress-row">
      <div class="label">C.3</div>
      <div class="bar"><div class="bar-fill review" style="width:87%;"></div></div>
      <div class="percent">87%</div>
      <div class="status status-review">REVIEW</div>
    </div>
    <div class="progress-row">
      <div class="label">C.4</div>
      <div class="bar"><div class="bar-fill" style="width:97%;"></div></div>
      <div class="percent">97%</div>
      <div class="status status-ready">READY</div>
    </div>
    <div class="progress-row">
      <div class="label">C.5</div>
      <div class="bar"><div class="bar-fill" style="width:93%;"></div></div>
      <div class="percent">93%</div>
      <div class="status status-ready">READY</div>
    </div>
    <div class="progress-row">
      <div class="label">C.6</div>
      <div class="bar"><div class="bar-fill review" style="width:86%;"></div></div>
      <div class="percent">86%</div>
      <div class="status status-review">REVIEW</div>
    </div>
    <div class="progress-row">
      <div class="label">C.7</div>
      <div class="bar"><div class="bar-fill review" style="width:83%;"></div></div>
      <div class="percent">83%</div>
      <div class="status status-review">REVIEW</div>
    </div>

    <div class="alert-box">
      <h4 style="margin:0 0 8px 0; color:#e65100;">⚠️ Perlu Perhatian</h4>
      <div class="item">🔴 <strong>2 Critical Risk</strong> — bukti CPL & link evidence</div>
      <div class="item">🟠 <strong>4 Evidence</strong> belum verified</div>
      <div class="item">🟡 <strong>3 PIC</strong> Mock AL score &lt; 3</div>
    </div>
  </div>

  <!-- ===== KRITERIA ===== -->
  <div class="al-panel" id="panel-kriteria">
    <h2 style="color:#0d47a1;">Kriteria Akreditasi</h2>
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

  <!-- ===== BUKTI ===== -->
  <div class="al-panel" id="panel-bukti">
    <h2 style="color:#0d47a1;">🔍 Bukti Asesmen Lapangan</h2>
    <input type="text" class="search-box" id="buktiSearch" placeholder="Cari bukti: CPL, RPS, tracer, penelitian..." oninput="filterBukti()">
    <div class="filter-row">
      <select id="filterKriteria" onchange="filterBukti()">
        <option value="">Semua Kriteria</option>
        <option value="C.1">C.1</option><option value="C.2">C.2</option>
        <option value="C.3">C.3</option><option value="C.4">C.4</option>
        <option value="C.5">C.5</option><option value="C.6">C.6</option>
        <option value="C.7">C.7</option>
      </select>
      <select id="filterStatus" onchange="filterBukti()">
        <option value="">Semua Status</option>
        <option value="verified">Verified</option>
        <option value="review">Review</option>
        <option value="missing">Missing</option>
      </select>
    </div>

    <div class="card-grid">
      <div class="stat-card" style="border-left-color:#4caf50;">
        <div class="label">Total Evidence</div>
        <div class="value" style="color:#4caf50;">157</div>
      </div>
      <div class="stat-card" style="border-left-color:#2196f3;">
        <div class="label">Verified</div>
        <div class="value" style="color:#2196f3;">148</div>
      </div>
      <div class="stat-card" style="border-left-color:#ff9800;">
        <div class="label">Review</div>
        <div class="value" style="color:#ff9800;">6</div>
      </div>
      <div class="stat-card" style="border-left-color:#f44336;">
        <div class="label">Missing</div>
        <div class="value" style="color:#f44336;">3</div>
      </div>
    </div>

    <div id="buktiList"></div>
  </div>

  <!-- ===== PERTANYAAN ===== -->
  <div class="al-panel" id="panel-pertanyaan">
    <h2 style="color:#0d47a1;">🔥 Bank Pertanyaan Asesor</h2>
    <div class="sub-nav">
      <button class="active" onclick="filterPertanyaan('all', this)">Semua</button>
      <button onclick="filterPertanyaan('critical', this)">🔥 Critical</button>
      <button onclick="filterPertanyaan('ppepp', this)">🔄 PPEPP</button>
      <button onclick="filterPertanyaan('data', this)">📊 Data</button>
    </div>
    <div id="pertanyaanList"></div>
  </div>

  <!-- ===== MOCK AL ===== -->
  <div class="al-panel" id="panel-mock">
    <h2 style="color:#0d47a1;">🎭 Simulasi Asesmen Lapangan</h2>
    <div id="mockSetup">
      <div class="card-grid">
        <div class="stat-card">
          <div class="label">Pilih Kriteria</div>
          <select style="width:100%; padding:8px; margin-top:8px; border-radius:6px; border:1px solid #ddd;">
            <option>Semua Kriteria</option>
            <option>C.1 VMTS</option><option>C.2 Tata Pamong</option>
            <option selected>C.3 Relevansi</option><option>C.4 SDM</option>
            <option>C.5 Sarpras & K3L</option><option>C.6 Mahasiswa</option>
            <option>C.7 SPMI</option>
          </select>
        </div>
        <div class="stat-card">
          <div class="label">Mode Asesor</div>
          <select style="width:100%; padding:8px; margin-top:8px; border-radius:6px; border:1px solid #ddd;">
            <option>Normal</option>
            <option selected>🔥 Kritis</option>
            <option>📊 Data Auditor</option>
            <option>🔄 PPEPP</option>
          </select>
        </div>
        <div class="stat-card">
          <div class="label">Jumlah Pertanyaan</div>
          <div style="margin-top:8px; display:flex; gap:6px;">
            <button class="btn btn-outline">10</button>
            <button class="btn btn-primary">20</button>
            <button class="btn btn-outline">30</button>
          </div>
        </div>
      </div>
      <div style="text-align:center; margin-top:24px;">
        <button class="btn btn-primary" style="padding:14px 40px; font-size:1rem;" onclick="startMock()">🚀 MULAI MOCK AL</button>
      </div>
    </div>
    <div id="mockSession" style="display:none;"></div>
  </div>

  <!-- ===== PPEPP ===== -->
  <div class="al-panel" id="panel-ppepp">
    <h2 style="color:#0d47a1;">🔄 PPEPP Closed-Loop Improvement</h2>
    <div class="sub-nav">
      <button class="active" onclick="showPPEPP('kurikulum', this)">Kurikulum</button>
      <button onclick="showPPEPP('cpl', this)">CPL</button>
      <button onclick="showPPEPP('rps', this)">RPS</button>
      <button onclick="showPPEPP('pembelajaran', this)">Pembelajaran</button>
      <button onclick="showPPEPP('penelitian', this)">Penelitian</button>
      <button onclick="showPPEPP('pkm', this)">PkM</button>
      <button onclick="showPPEPP('tracer', this)">Tracer</button>
      <button onclick="showPPEPP('ami', this)">AMI</button>
    </div>
    <div id="ppeppContent"></div>
  </div>

  <!-- ===== RISIKO ===== -->
  <div class="al-panel" id="panel-risiko">
    <h2 style="color:#0d47a1;">⚠️ Risk & Clarification Register</h2>
    <div class="card-grid">
      <div class="stat-card" style="border-left-color:#f44336;">
        <div class="label">🔴 Critical</div>
        <div class="value" style="color:#f44336;">2</div>
      </div>
      <div class="stat-card" style="border-left-color:#ff9800;">
        <div class="label">🟠 High</div>
        <div class="value" style="color:#ff9800;">4</div>
      </div>
      <div class="stat-card" style="border-left-color:#ffc107;">
        <div class="label">🟡 Medium</div>
        <div class="value" style="color:#f57c00;">7</div>
      </div>
      <div class="stat-card" style="border-left-color:#4caf50;">
        <div class="label">🟢 Resolved</div>
        <div class="value" style="color:#4caf50;">28</div>
      </div>
    </div>
    <table class="risk-table">
      <thead>
        <tr><th>Risiko</th><th>Kriteria</th><th>PIC</th><th>H-</th><th>Status</th></tr>
      </thead>
      <tbody>
        <tr><td>Bukti CPL belum lengkap</td><td>C.3</td><td>Kurikulum</td><td>18</td><td><span class="risk-badge risk-critical">CRITICAL</span></td></tr>
        <tr><td>Link evidence mati</td><td>C.3</td><td>Admin</td><td>14</td><td><span class="risk-badge risk-high">HIGH</span></td></tr>
        <tr><td>Mock score &lt; 3</td><td>C.7</td><td>UPM</td><td>10</td><td><span class="risk-badge risk-medium">MEDIUM</span></td></tr>
        <tr><td>Tracer study response rate rendah</td><td>C.6</td><td>Karir</td><td>12</td><td><span class="risk-badge risk-high">HIGH</span></td></tr>
        <tr><td>SOP K3L belum disahkan</td><td>C.5</td><td>Lab</td><td>8</td><td><span class="risk-badge risk-critical">CRITICAL</span></td></tr>
      </tbody>
    </table>
  </div>

  <!-- ===== TIM/PIC ===== -->
  <div class="al-panel" id="panel-tim">
    <h2 style="color:#0d47a1;">👥 Tim Asesmen Lapangan</h2>
    <div class="team-grid">
      <div class="team-card">
        <div class="role">KETUA TIM</div>
        <div class="name">AW</div>
        <div class="stat">Overall AL Readiness: <strong>94%</strong></div>
        <div class="stat">Mock Score: <strong>3.8</strong></div>
      </div>
      <div class="team-card">
        <div class="role">PIC C.1 VMTS</div>
        <div class="name">AW + SH</div>
        <div class="stat">Questions: <strong>12/12</strong></div>
        <div class="stat">Mock Score: <strong>3.6</strong></div>
      </div>
      <div class="team-card">
        <div class="role">PIC C.2 Tata Pamong</div>
        <div class="name">SH + BU</div>
        <div class="stat">Questions: <strong>18/20</strong></div>
        <div class="stat">Mock Score: <strong>3.4</strong></div>
      </div>
      <div class="team-card" style="border-top-color:#ff9800;">
        <div class="role">PIC C.3 Relevansi</div>
        <div class="name">VF + BU</div>
        <div class="stat">Questions: <strong>18/20</strong></div>
        <div class="stat">Mock Score: <strong>3.2</strong> ⚠️</div>
      </div>
      <div class="team-card">
        <div class="role">PIC C.4 SDM</div>
        <div class="name">DW + VF</div>
        <div class="stat">Questions: <strong>20/20</strong></div>
        <div class="stat">Mock Score: <strong>3.7</strong></div>
      </div>
      <div class="team-card">
        <div class="role">PIC C.5 Sarpras & K3L</div>
        <div class="name">Z + MF</div>
        <div class="stat">Questions: <strong>14/16</strong></div>
        <div class="stat">Mock Score: <strong>3.3</strong></div>
      </div>
      <div class="team-card" style="border-top-color:#ff9800;">
        <div class="role">PIC C.6 Mahasiswa</div>
        <div class="name">MF + DW</div>
        <div class="stat">Questions: <strong>21/24</strong></div>
        <div class="stat">Mock Score: <strong>2.9</strong> ⚠️</div>
      </div>
      <div class="team-card" style="border-top-color:#ff9800;">
        <div class="role">PIC C.7 SPMI</div>
        <div class="name">BU + SH</div>
        <div class="stat">Questions: <strong>16/18</strong></div>
        <div class="stat">Mock Score: <strong>2.8</strong> ⚠️</div>
      </div>
    </div>
  </div>

  <!-- ===== CHECKLIST ===== -->
  <div class="al-panel" id="panel-checklist">
    <h2 style="color:#0d47a1;">✅ Checklist Menuju AL</h2>
    <div class="sub-nav">
      <button class="active" onclick="showChecklist('h30', this)">H-30</button>
      <button onclick="showChecklist('h21', this)">H-21</button>
      <button onclick="showChecklist('h14', this)">H-14</button>
      <button onclick="showChecklist('h7', this)">H-7</button>
      <button onclick="showChecklist('h1', this)">H-1</button>
    </div>
    <div id="checklistContent"></div>
  </div>

  <!-- ===== MODE AL ===== -->
  <div class="al-panel" id="panel-modeal">
    <div class="mode-al-view">
      <h2>🚀 PSBM — ASESMEN LAPANGAN</h2>
      <p style="opacity:0.9;">Mode Presentasi • Semua data internal disembunyikan</p>
      <input type="text" class="search-big" placeholder="🔍 Cari bukti: CPL / RPS / tracer / penelitian...">
      <div style="margin:16px 0; display:flex; gap:6px; justify-content:center; flex-wrap:wrap;">
        <button class="quick-btn">C.1</button>
        <button class="quick-btn">C.2</button>
        <button class="quick-btn">C.3</button>
        <button class="quick-btn">C.4</button>
        <button class="quick-btn">C.5</button>
        <button class="quick-btn">C.6</button>
        <button class="quick-btn">C.7</button>
      </div>
      <h3 style="margin-top:24px; text-align:left;">⚡ QUICK EVIDENCE</h3>
      <div class="quick-grid">
        <button class="quick-btn">📄 LED</button>
        <button class="quick-btn">📊 LKPS</button>
        <button class="quick-btn">🎯 VMTS</button>
        <button class="quick-btn">📘 Kurikulum</button>
        <button class="quick-btn">🎓 CPL</button>
        <button class="quick-btn">📝 RPS</button>
        <button class="quick-btn">🔬 Penelitian</button>
        <button class="quick-btn">🤝 PkM</button>
        <button class="quick-btn">🗺️ Roadmap</button>
        <button class="quick-btn">📈 Tracer</button>
        <button class="quick-btn">🤝 Kerja Sama</button>
        <button class="quick-btn">👨‍🏫 DTPS</button>
        <button class="quick-btn">🔍 AMI</button>
        <button class="quick-btn">📋 RTM</button>
        <button class="quick-btn">🔄 PPEPP</button>
      </div>
      <div style="margin-top:30px; padding:16px; background:rgba(255,255,255,0.1); border-radius:8px;">
        <strong>💡 Catatan:</strong> Risk register, skor kesiapan, missing evidence, dan catatan internal <strong>TIDAK</strong> tampil di mode ini.
      </div>
    </div>
  </div>

</div>

<script>
// ===== DATA =====
const dataKriteria = {
  c1: { title: 'C.1 VMTS', readiness: 96, status: 'READY', indicators: [
    { name: 'Kekhasan VMTS', status: 'ready', evidence: '5/5', questions: 6, pic: 'AW + SH' },
    { name: 'Mekanisme Penyusunan', status: 'ready', evidence: '4/4', questions: 5, pic: 'AW + SH' },
    { name: 'Tingkat Pemahaman', status: 'ready', evidence: '6/6', questions: 7, pic: 'AW + SH' }
  ]},
  c2: { title: 'C.2 Tata Pamong, Tata Kelola, Kerja Sama, Keuangan', readiness: 92, status: 'READY', indicators: [
    { name: 'Sistem Tata Pamong', status: 'ready', evidence: '5/5', questions: 8, pic: 'SH + BU' },
    { name: 'Komitmen Pimpinan', status: 'ready', evidence: '4/4', questions: 6, pic: 'SH + BU' },
    { name: 'Kerja Sama', status: 'ready', evidence: '8/8', questions: 9, pic: 'MF' },
    { name: 'Pengelolaan Keuangan', status: 'review', evidence: '5/6', questions: 7, pic: 'SH' }
  ]},
  c3: { title: 'C.3 Relevansi Pendidikan, Penelitian, dan PkM', readiness: 87, status: 'REVIEW', indicators: [
    { name: 'Profil Lulusan', status: 'ready', evidence: '5/5', questions: 6, pic: 'Tim Kurikulum' },
    { name: 'Kesesuaian CPL', status: 'ready', evidence: '8/8', questions: 9, pic: 'Tim Kurikulum' },
    { name: 'Tinjauan CPL', status: 'review', evidence: '6/7', questions: 8, pic: 'Tim Kurikulum' },
    { name: 'RPS', status: 'ready', evidence: '12/12', questions: 10, pic: 'VF' },
    { name: 'Capstone Project', status: 'review', evidence: '4/5', questions: 7, pic: 'VF' }
  ]},
  c4: { title: 'C.4 Sumber Daya Manusia', readiness: 97, status: 'READY', indicators: [
    { name: 'Profil DTPS', status: 'ready', evidence: '10/10', questions: 8, pic: 'DW' },
    { name: 'Tenaga Kependidikan', status: 'ready', evidence: '4/4', questions: 5, pic: 'Z' },
    { name: 'Beban Kerja Dosen', status: 'ready', evidence: '6/6', questions: 6, pic: 'DW' },
    { name: 'Kinerja DTPS', status: 'ready', evidence: '15/15', questions: 12, pic: 'VF' }
  ]},
  c5: { title: 'C.5 Sarana, Prasarana, dan K3L', readiness: 93, status: 'READY', indicators: [
    { name: 'Sarana & Prasarana', status: 'ready', evidence: '8/8', questions: 7, pic: 'Z' },
    { name: 'Dokumen K3L', status: 'review', evidence: '3/4', questions: 5, pic: 'Z' },
    { name: 'Fasilitas K3L', status: 'ready', evidence: '6/6', questions: 4, pic: 'Z + MF' }
  ]},
  c6: { title: 'C.6 Mahasiswa dan Luaran Mahasiswa', readiness: 86, status: 'REVIEW', indicators: [
    { name: 'Rasio Mahasiswa:DTPS', status: 'ready', evidence: '3/3', questions: 4, pic: 'MF' },
    { name: 'IPK Lulusan', status: 'ready', evidence: '3/3', questions: 3, pic: 'MF' },
    { name: 'Tracer Study', status: 'review', evidence: '5/7', questions: 10, pic: 'MF + DW' },
    { name: 'Prestasi Mahasiswa', status: 'ready', evidence: '8/8', questions: 6, pic: 'MF' },
    { name: 'Kinerja Lulusan', status: 'review', evidence: '4/6', questions: 8, pic: 'MF + DW' }
  ]},
  c7: { title: 'C.7 Sistem Penjaminan Mutu', readiness: 83, status: 'REVIEW', indicators: [
    { name: 'Unit Penjaminan Mutu', status: 'ready', evidence: '4/4', questions: 5, pic: 'BU' },
    { name: 'Perangkat SPMI', status: 'ready', evidence: '4/4', questions: 6, pic: 'BU' },
    { name: 'Siklus PPEPP', status: 'review', evidence: '5/7', questions: 9, pic: 'BU + SH' },
    { name: 'Kepuasan Stakeholder', status: 'review', evidence: '3/5', questions: 7, pic: 'BU' }
  ]}
};

const dataBukti = [
  { code: 'C1-VMTS-001', name: 'SK VMTS PT & UPPS', path: 'C.1 → VMTS → Kekhasan', status: 'verified' },
  { code: 'C1-VMTS-002', name: 'Renstra 2025-2029', path: 'C.1 → VMTS → Pencapaian', status: 'verified' },
  { code: 'C3-CPL-001', name: 'NADK PSBM 2020', path: 'C.3 → Pendidikan → CPL', status: 'verified' },
  { code: 'C3-CPL-002', name: 'Workshop OBE 2024', path: 'C.3 → Pendidikan → Tinjauan CPL', status: 'verified' },
  { code: 'C3-CPL-003', name: 'Tindak Lanjut Evaluasi CPL', path: 'C.3 → Pendidikan → Tinjauan CPL', status: 'review' },
  { code: 'C4-SDM-001', name: 'Ijazah & Sertifikat DTPS', path: 'C.4 → SDM → Profil', status: 'verified' },
  { code: 'C5-K3L-001', name: 'SOP K3L Laboratorium', path: 'C.5 → K3L → Dokumen', status: 'review' },
  { code: 'C6-TRACER-001', name: 'Laporan Tracer Study 2024', path: 'C.6 → Luaran → Tracer', status: 'verified' },
  { code: 'C6-TRACER-002', name: 'Kuesioner DIKTI', path: 'C.6 → Luaran → Tracer', status: 'verified' },
  { code: 'C7-AMI-001', name: 'Laporan AMI 2025', path: 'C.7 → SPMI → Audit', status: 'verified' },
  { code: 'C7-PPEPP-001', name: 'Dokumen Siklus PPEPP', path: 'C.7 → SPMI → PPEPP', status: 'missing' }
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
  kurikulum: {
    steps: [
      { t: 'PENETAPAN', c: 'Kurikulum KKNI Level 6 + OBE 2020' },
      { t: 'PELAKSANAAN', c: 'Pembelajaran semester berjalan' },
      { t: 'EVALUASI', c: 'Tracer study + User survey + Workshop kurikulum' },
      { t: 'PENGENDALIAN', c: 'Analisis kesenjangan CPL vs kebutuhan industri' },
      { t: 'PENINGKATAN', c: 'Revisi Kurikulum OBE 2025' }
    ]
  },
  cpl: {
    steps: [
      { t: 'PENETAPAN', c: 'NADK PSBM 2020 — 12 CPL' },
      { t: 'PELAKSANAAN', c: 'Pembelajaran berbasis CPL di setiap RPS' },
      { t: 'EVALUASI', c: 'Tracer + User Survey + Workshop OBE 2024' },
      { t: 'PENGENDALIAN', c: 'Analisis kesenjangan kompetensi' },
      { t: 'PENINGKATAN', c: 'Pengembangan Kurikulum OBE 2025' }
    ]
  },
  tracer: {
    steps: [
      { t: 'PENETAPAN', c: 'SK Pelaksanaan Tracer Study tahunan' },
      { t: 'PELAKSANAAN', c: 'Kuesioner DIKTI + follow-up lulusan' },
      { t: 'EVALUASI', c: 'Response rate 2024: 68%' },
      { t: 'PENGENDALIAN', c: 'Identifikasi lulusan belum terisi' },
      { t: 'PENINGKATAN', c: 'Kolaborasi dengan career center + insentif alumni' }
    ]
  },
  ami: {
    steps: [
      { t: 'PENETAPAN', c: 'SK Audit Mutu Internal 2025' },
      { t: 'PELAKSANAAN', c: 'Audit 7 kriteria + wawancara' },
      { t: 'EVALUASI', c: 'Laporan temuan AMI Oktober 2025' },
      { t: 'PENGENDALIAN', c: 'Rapat Tinjauan Manajemen (RTM)' },
      { t: 'PENINGKATAN', c: 'Rencana tindak lanjut 15 temuan' }
    ]
  }
};
// Default untuk sub-tab lain
['rps','pembelajaran','penelitian','pkm'].forEach(k => {
  dataPPEPP[k] = {
    steps: [
      { t: 'PENETAPAN', c: 'Dokumen kebijakan terkait' },
      { t: 'PELAKSANAAN', c: 'Implementasi di lapangan' },
      { t: 'EVALUASI', c: 'Monitoring & evaluasi berkala' },
      { t: 'PENGENDALIAN', c: 'Analisis temuan' },
      { t: 'PENINGKATAN', c: 'Rencana perbaikan berkelanjutan' }
    ]
  };
});

const dataChecklist = {
  h30: { title: 'H-30', items: [
    { text: 'Freeze baseline SAKTI', done: true },
    { text: 'Data Master diverifikasi', done: true },
    { text: 'Identifikasi PIC per kriteria', done: true },
    { text: 'Struktur Evidence folder final', done: true },
    { text: 'Link Google Drive semua publik', done: false }
  ]},
  h21: { title: 'H-21', items: [
    { text: 'Evidence verification selesai', done: true },
    { text: 'Mock AL I dilaksanakan', done: false },
    { text: 'Critical questions dijawab', done: false },
    { text: 'Tracer study response ≥ 30%', done: false }
  ]},
  h14: { title: 'H-14', items: [
    { text: 'Mock AL II dilaksanakan', done: false },
    { text: 'Stakeholder simulation', done: false },
    { text: 'Link audit semua bukti', done: false },
    { text: 'Dokumen K3L disahkan', done: false }
  ]},
  h7: { title: 'H-7', items: [
    { text: 'Full simulation AL', done: false },
    { text: 'Backup evidence lokal & cloud', done: false },
    { text: 'Freeze konten LED & LKPS', done: false },
    { text: 'Presentasi tim final', done: false }
  ]},
  h1: { title: 'H-1', items: [
    { text: 'Cek final semua link', done: false },
    { text: 'Siapkan ruang AL', done: false },
    { text: 'Briefing tim terakhir', done: false },
    { text: 'Aktifkan Mode AL', done: false }
  ]}
};

// ===== FUNCTIONS =====
function showPanel(id, btn) {
  document.querySelectorAll('.al-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.al-nav button').forEach(b => b.classList.remove('active'));
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
  const k = dataKriteria[key];
  let html = `<h3 style="color:#0d47a1;">${k.title}</h3>`;
  html += `<div class="progress-row"><div class="bar" style="height:18px;"><div class="bar-fill ${k.status==='REVIEW'?'review':''}" style="width:${k.readiness}%;"></div></div><div class="percent">${k.readiness}%</div><div class="status status-${k.status.toLowerCase()}">${k.status}</div></div>`;
  k.indicators.forEach(ind => {
    html += `<div class="indicator-card ${ind.status}">
      <div class="head"><div class="title">${ind.name}</div><div class="status status-${ind.status==='ready'?'ready':'review'}">${ind.status==='ready'?'✓ SIAP':'⚠ REVIEW'}</div></div>
      <div class="meta">PIC: ${ind.pic} • Evidence: ${ind.evidence} • Questions: ${ind.questions}</div>
      <div class="actions"><button class="btn btn-primary">Detail</button><button class="btn btn-outline">Bukti</button><button class="btn btn-outline">Latihan</button></div>
    </div>`;
  });
  document.getElementById('kriteriaContent').innerHTML = html;
}

function renderBukti() {
  const search = (document.getElementById('buktiSearch')?.value || '').toLowerCase();
  const fk = document.getElementById('filterKriteria')?.value || '';
  const fs = document.getElementById('filterStatus')?.value || '';
  const filtered = dataBukti.filter(b => {
    const matchSearch = !search || b.name.toLowerCase().includes(search) || b.code.toLowerCase().includes(search);
    const matchK = !fk || b.path.startsWith(fk);
    const matchS = !fs || b.status === fs;
    return matchSearch && matchK && matchS;
  });
  let html = '';
  filtered.forEach(b => {
    html += `<div class="evidence-item ${b.status}">
      <div class="code">${b.code}</div>
      <div style="font-weight:600; margin:4px 0;">${b.name}</div>
      <div class="path">${b.path}</div>
      <div style="margin-top:8px; display:flex; gap:8px; align-items:center;">
        <span class="risk-badge risk-${b.status==='verified'?'resolved':b.status}">${b.status.toUpperCase()}</span>
        <button class="btn btn-outline">BUKA</button>
      </div>
    </div>`;
  });
  if (!filtered.length) html = '<p style="text-align:center; color:#888; padding:20px;">Tidak ada bukti ditemukan</p>';
  document.getElementById('buktiList').innerHTML = html;
}
function filterBukti() { renderBukti(); }

function renderPertanyaan(filter = 'all') {
  const filtered = dataPertanyaan.filter(p => filter === 'all' || p.type === filter);
  let html = '';
  filtered.forEach(p => {
    html += `<div class="question-card ${p.type==='critical'?'critical':''}">
      <div class="q-code">${p.code} • ${p.kriteria}</div>
      <div class="q-text">${p.text}</div>
      <div class="q-meta">PIC: ${p.pic} • Type: ${p.type.toUpperCase()}</div>
      <div style="margin-top:10px;"><button class="btn btn-primary">LIHAT JAWABAN</button></div>
    </div>`;
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
  let qNum = 1;
  const total = 5;
  const questions = [
    'Bagaimana PSBM memastikan bahwa penelitian dosen sesuai dengan peta jalan penelitian?',
    'Sebutkan bukti konkret integrasi hasil PkM ke dalam bahan ajar minimal 10% MK inti.',
    'Bagaimana mekanisme tinjauan rutin CPL dan siapa yang terlibat?',
    'Apa tindak lanjut dari temuan AMI 2025 terkait K3L?',
    'Bagaimana PSBM mengukur waktu tunggu lulusan dan kesesuaian bidang kerja?'
  ];
  function renderQ() {
    session.innerHTML = `
      <div style="background:#0d47a1; color:white; padding:16px; border-radius:10px; margin-bottom:16px;">
        <div style="display:flex; justify-content:space-between; align-items:center;">
          <div><strong>MOCK AL — C.3</strong><br><small>Question ${qNum} / ${total}</small></div>
          <div style="background:#ff6f00; padding:8px 16px; border-radius:20px; font-weight:700;">⏱ 00:52</div>
        </div>
      </div>
      <div style="background:white; padding:24px; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.08); margin-bottom:16px;">
        <div style="font-size:1.1rem; font-weight:600; color:#0d47a1;">${questions[qNum-1]}</div>
      </div>
      <div style="display:flex; gap:10px; flex-wrap:wrap;">
        <button class="btn btn-outline">📎 TAMPILKAN BUKTI</button>
        <button class="btn btn-primary" onclick="nextMock()">✓ SELESAI MENJAWAB</button>
      </div>
      <div style="margin-top:20px; background:#fff8e1; padding:14px; border-radius:8px;">
        <strong>SKOR:</strong> 0=Tidak menjawab • 1=Umum • 2=+Data • 3=+Data+Bukti • 4=+Data+Bukti+Tindak Lanjut
        <div style="margin-top:10px; display:flex; gap:6px;">
          ${[0,1,2,3,4].map(n => `<button class="btn btn-outline" style="flex:1;">${n}</button>`).join('')}
        </div>
      </div>`;
  }
  window.nextMock = function() {
    if (qNum < total) { qNum++; renderQ(); }
    else {
      session.innerHTML = `<div style="text-align:center; padding:40px; background:#e8f5e9; border-radius:12px;">
        <h2 style="color:#2e7d32;">✅ Mock AL Selesai!</h2>
        <div style="font-size:2rem; font-weight:700; color:#0d47a1; margin:16px 0;">3.4 / 4.0</div>
        <p>Rata-rata skor C.3 — masih perlu latihan di bagian PPEPP</p>
        <button class="btn btn-primary" onclick="document.getElementById('mockSetup').style.display='block'; document.getElementById('mockSession').style.display='none';">Kembali</button>
      </div>`;
    }
  };
  renderQ();
}

function showPPEPP(key, btn) {
  document.querySelectorAll('#panel-ppepp .sub-nav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  const data = dataPPEPP[key];
  let html = `<h3 style="color:#0d47a1;">${key.toUpperCase()} — Closed Loop</h3><div class="ppepp-flow">`;
  data.steps.forEach(s => {
    html += `<div class="ppepp-step"><div class="step-title">${s.t}</div><div class="step-content">${s.c}</div><button class="btn btn-outline" style="margin-top:8px;">📎 BUKA BUKTI</button></div>`;
  });
  html += '</div>';
  document.getElementById('ppeppContent').innerHTML = html;
}

function showChecklist(key, btn) {
  document.querySelectorAll('#panel-checklist .sub-nav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  const data = dataChecklist[key];
  let html = `<div class="checklist-group"><h4>${data.title}</h4>`;
  data.items.forEach((item, i) => {
    html += `<div class="checklist-item ${item.done?'done':''}">
      <input type="checkbox" id="cl-${key}-${i}" ${item.done?'checked':''} onchange="this.parentElement.classList.toggle('done', this.checked)">
      <label for="cl-${key}-${i}">${item.text}</label>
    </div>`;
  });
  html += '</div>';
  document.getElementById('checklistContent').innerHTML = html;
}

// Init
document.addEventListener('DOMContentLoaded', () => {
  showKriteria('c1', document.querySelector('#kriteriaSubNav button'));
  renderBukti();
  renderPertanyaan();
  showPPEPP('kurikulum', document.querySelector('#panel-ppepp .sub-nav button'));
  showChecklist('h30', document.querySelector('#panel-checklist .sub-nav button'));
});
</script>

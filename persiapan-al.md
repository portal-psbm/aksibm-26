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
  .folder-tab:hover { background: #f1f5f9; transform: translateY(0px); color: #0d47a1; }
  .folder-tab:hover::before { background: #f1f5f9; }
  .folder-tab.active {
    background: #0d47a1; color: #ffffff; transform: translateY(-6px);
    z-index: 20; border-color: #0d47a1;
    box-shadow: 0 -4px 16px rgba(13, 71, 161, 0.25); font-weight: 700;
  }
  .folder-tab.active::before { background: #0d47a1; border-color: #0d47a1; height: 9px; top: -9px; }

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

  .sub-nav { display: flex; gap: 4px; margin-bottom: 20px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
  .sub-nav button { padding: 10px 18px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.9rem; }
  .sub-nav button:hover { color: #0d47a1; background: #f8fafc; }
  .sub-nav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }

  .indicator-list { display: flex; flex-direction: column; gap: 6px; margin-bottom: 20px; }
  .indicator-row {
    display: flex; align-items: center; justify-content: space-between;
    padding: 12px 16px; background: white; border: 1px solid #e0e0e0;
    border-radius: 8px; cursor: pointer; transition: all 0.2s; border-left: 4px solid #4caf50;
  }
  .indicator-row:hover { background: #f8fafc; transform: translateX(2px); box-shadow: 0 2px 8px rgba(0,0,0,0.06); }
  .indicator-row.warn { border-left-color: #ff9800; }
  .indicator-row.active { background: #e3f2fd; border-color: #0d47a1; }
  .indicator-row .name { font-weight: 600; color: #333; }
  .indicator-row .status-icon { font-size: 1.2rem; font-weight: 700; }
  .indicator-row .status-icon.ready { color: #2e7d32; }
  .indicator-row .status-icon.warn { color: #e65100; }

  .detail-panel { background: #f8fafc; border: 1px solid #e0e0e0; border-radius: 10px; padding: 20px; margin-top: 16px; }
  .detail-section { background: white; border-radius: 8px; padding: 14px 16px; margin-bottom: 10px; border-left: 4px solid #0d47a1; }
  .detail-section.klaim { border-left-color: #0d47a1; }
  .detail-section.jawaban { border-left-color: #4caf50; }
  .detail-section.data { border-left-color: #2196f3; }
  .detail-section.bukti { border-left-color: #9c27b0; }
  .detail-section.tindak { border-left-color: #ff9800; }
  .detail-section .section-title { font-size: 0.75rem; text-transform: uppercase; letter-spacing: 1px; font-weight: 700; margin-bottom: 6px; color: #666; }
  .detail-section .section-content { font-size: 0.92rem; color: #333; line-height: 1.5; }
  .detail-section ul { margin: 4px 0 0 0; padding-left: 20px; }
  .detail-section ul li { padding: 2px 0; font-size: 0.9rem; }
  .pic-tag { display: inline-block; background: #0d47a1; color: white; padding: 4px 12px; border-radius: 12px; font-size: 0.8rem; font-weight: 600; margin-top: 12px; }

  /* ===== Simulasi AL ===== */
  .sim-mode-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 10px; margin-bottom: 20px; }
  .sim-mode-btn {
    padding: 14px; background: white; border: 2px solid #e0e0e0; border-radius: 8px;
    cursor: pointer; text-align: center; font-weight: 600; font-size: 0.85rem; color: #555; transition: all 0.2s;
  }
  .sim-mode-btn:hover { border-color: #0d47a1; color: #0d47a1; transform: translateY(-2px); }
  .sim-mode-btn.active { background: #0d47a1; color: white; border-color: #0d47a1; }
  .sim-mode-btn.critical { border-color: #f44336; color: #c62828; }
  .sim-mode-btn.critical.active { background: #c62828; color: white; }
  .sim-mode-btn.pic { border-color: #ff9800; color: #e65100; }
  .sim-mode-btn.pic.active { background: #e65100; color: white; }

  /* Question Card Baru */
  .q-card {
    background: white; border: 1px solid #e0e0e0; border-radius: 10px;
    margin-bottom: 14px; overflow: hidden; transition: all 0.2s;
    box-shadow: 0 2px 8px rgba(0,0,0,0.05);
  }
  .q-card:hover { box-shadow: 0 4px 16px rgba(0,0,0,0.1); }
  .q-card-header {
    display: flex; align-items: center; justify-content: space-between;
    padding: 14px 18px; cursor: pointer; background: #f8fafc;
    border-bottom: 1px solid #e0e0e0; transition: background 0.2s;
  }
  .q-card-header:hover { background: #e3f2fd; }
  .q-card-header .q-num { font-weight: 800; color: #0d47a1; font-size: 1.1rem; min-width: 30px; }
  .q-card-header .q-main { flex: 1; font-weight: 600; color: #333; font-size: 0.92rem; margin: 0 12px; line-height: 1.4; }
  .q-card-header .q-risk { padding: 4px 10px; border-radius: 12px; font-size: 0.72rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.5px; white-space: nowrap; }
  .q-risk.tinggi { background: #ffebee; color: #c62828; }
  .q-risk.sedang { background: #fff8e1; color: #f57c00; }
  .q-card-header .q-toggle { font-size: 1.2rem; color: #999; transition: transform 0.3s; margin-left: 8px; }
  .q-card.open .q-card-header .q-toggle { transform: rotate(180deg); }
  .q-card-body { display: none; padding: 16px 18px; }
  .q-card.open .q-card-body { display: block; animation: fadeIn 0.3s ease; }

  .q-section { margin-bottom: 14px; }
  .q-section:last-child { margin-bottom: 0; }
  .q-section-title {
    font-size: 0.72rem; text-transform: uppercase; letter-spacing: 1px;
    font-weight: 700; color: #0d47a1; margin-bottom: 6px;
    display: flex; align-items: center; gap: 6px;
  }
  .q-section-title .icon { font-size: 0.9rem; }
  .q-section-content { font-size: 0.9rem; color: #333; line-height: 1.5; }
  .q-section-content em { color: #c62828; font-style: normal; font-weight: 600; }

  .q-meta-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 12px; }
  .q-meta-item { background: #f8fafc; padding: 10px 12px; border-radius: 6px; border-left: 3px solid #0d47a1; }
  .q-meta-item .meta-label { font-size: 0.7rem; text-transform: uppercase; letter-spacing: 0.5px; color: #888; font-weight: 600; }
  .q-meta-item .meta-value { font-size: 0.88rem; color: #333; font-weight: 600; margin-top: 2px; }

  .q-followup {
    background: #fff8e1; border-left: 4px solid #ff9800;
    padding: 12px 14px; border-radius: 6px; margin-top: 10px;
  }
  .q-followup .followup-label { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 1px; font-weight: 700; color: #e65100; margin-bottom: 4px; }
  .q-followup .followup-text { font-size: 0.9rem; color: #555; font-style: italic; }

  .q-score-row { display: flex; gap: 6px; margin-top: 14px; }
  .q-score-btn {
    flex: 1; padding: 8px 4px; background: white; border: 2px solid #e0e0e0;
    border-radius: 6px; cursor: pointer; text-align: center; font-weight: 700;
    font-size: 0.85rem; color: #555; transition: all 0.2s;
  }
  .q-score-btn:hover { border-color: #0d47a1; color: #0d47a1; }
  .q-score-btn .score-sub { font-size: 0.65rem; font-weight: 500; color: #888; display: block; }

  /* Mode AL */
  .mode-al-container {
    background: linear-gradient(135deg, #0a3a8a 0%, #0d47a1 50%, #1565c0 100%);
    color: white; padding: 32px; border-radius: 12px; margin: -28px; min-height: 600px;
  }
  .mode-al-container h2 { margin: 0 0 8px 0; font-size: 1.4rem; text-align: center; }
  .mode-al-container .subtitle { text-align: center; opacity: 0.85; font-size: 0.9rem; margin-bottom: 20px; }
  .mode-al-search {
    width: 100%; max-width: 700px; padding: 16px 24px; border-radius: 30px;
    border: 2px solid rgba(255,255,255,0.3); background: rgba(255,255,255,0.1);
    color: white; font-size: 1rem; margin: 0 auto 20px auto; display: block; backdrop-filter: blur(4px);
  }
  .mode-al-search::placeholder { color: rgba(255,255,255,0.6); }
  .mode-al-search:focus { outline: none; border-color: #fff; background: rgba(255,255,255,0.15); }
  .kriteria-chips { display: flex; gap: 6px; justify-content: center; flex-wrap: wrap; margin-bottom: 24px; }
  .kriteria-chip { padding: 8px 14px; background: rgba(255,255,255,0.15); border: 1px solid rgba(255,255,255,0.3); border-radius: 20px; color: white; cursor: pointer; font-weight: 600; font-size: 0.82rem; transition: all 0.2s; }
  .kriteria-chip:hover { background: rgba(255,255,255,0.25); }
  .kriteria-chip.active { background: white; color: #0d47a1; border-color: white; }
  .evidence-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 10px; max-width: 900px; margin: 0 auto; }
  .evidence-btn { background: rgba(255,255,255,0.12); color: white; padding: 14px 10px; border-radius: 8px; border: 1px solid rgba(255,255,255,0.2); cursor: pointer; font-weight: 600; font-size: 0.85rem; text-align: center; transition: all 0.2s; }
  .evidence-btn:hover { background: rgba(255,255,255,0.25); transform: translateY(-2px); }
  .search-result { background: white; color: #333; border-radius: 12px; padding: 20px; margin-top: 20px; max-width: 900px; margin-left: auto; margin-right: auto; display: none; }
  .search-result.active { display: block; animation: fadeIn 0.3s ease; }
  .search-result h3 { color: #0d47a1; margin: 0 0 12px 0; font-size: 1rem; }
  .search-result .result-section { background: #f8fafc; border-radius: 8px; padding: 12px 14px; margin-bottom: 8px; border-left: 4px solid #0d47a1; }
  .search-result .result-section .section-title { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 1px; font-weight: 700; color: #0d47a1; margin-bottom: 4px; }
  .search-result .result-section .section-content { font-size: 0.88rem; color: #333; }
  .search-result .result-section ul { margin: 4px 0 0 0; padding-left: 18px; }
  .search-result .result-section ul li { font-size: 0.85rem; padding: 2px 0; }
  .search-result .result-section.followup { border-left-color: #ff9800; }
  .search-result .result-section.followup .section-title { color: #e65100; }

  @media (max-width: 767px) {
    .folder-shelf { gap: 6px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
    .folder-shelf::-webkit-scrollbar { display: none; }
    .folder-tab { min-width: 110px; flex: 0 0 auto; font-size: 0.8rem; }
    .al-content { padding: 20px; }
    .q-meta-grid { grid-template-columns: 1fr; }
    .q-card-header { flex-wrap: wrap; gap: 6px; }
    .q-card-header .q-main { margin: 4px 0; min-width: 100%; order: 3; }
    .mode-al-container { padding: 20px; margin: -20px; }
  }
</style>

<div class="cabinet-container">
  <div class="folder-shelf">
    <div class="folder-tab active" onclick="showPanel('kesiapan', this)">📑<br>KESIAPAN KRITERIA</div>
    <div class="folder-tab" onclick="showPanel('simulasi', this)">🎯<br>SIMULASI AL</div>
    <div class="folder-tab mode-al" onclick="showPanel('modeal', this)">🚀<br>MODE AL</div>
  </div>

  <div class="al-content" id="alContent">

    <!-- ========== KESIAPAN KRITERIA ========== -->
    <div class="al-panel active" id="panel-kesiapan">
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
      <p style="color:#666; font-size:0.9rem; margin-top:-4px;">Klik pertanyaan untuk melihat detail jawaban, data, bukti, dan follow-up kritis.</p>

      <h4 style="color:#0d47a1; margin:20px 0 10px 0;">FILTER PERTANYAAN</h4>
      <div class="sim-mode-grid">
        <div class="sim-mode-btn active" onclick="filterSim('semua', this)">📚 Semua (9)</div>
        <div class="sim-mode-btn critical" onclick="filterSim('tinggi', this)">🔥 Risiko Tinggi (7)</div>
        <div class="sim-mode-btn" onclick="filterSim('sedang', this)">🟡 Risiko Sedang (2)</div>
        <div class="sim-mode-btn pic" onclick="filterSim('kaprodi', this)">🎯 PIC Kaprodi</div>
        <div class="sim-mode-btn pic" onclick="filterSim('kajur', this)">🎯 PIC Kajur</div>
      </div>

      <div id="simulasiContent"></div>
    </div>

    <!-- ========== MODE AL ========== -->
    <div class="al-panel" id="panel-modeal">
      <div class="mode-al-container">
        <h2>🚀 PSBM — MODE ASESMEN LAPANGAN</h2>
        <div class="subtitle">Cari pertanyaan, data, atau bukti dengan cepat</div>
        <input type="text" class="mode-al-search" id="modeAlSearch" placeholder="🔎 Contoh: VMTS, kekhasan, linearitas visi..." oninput="searchModeAL()">
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
// ===== DATA KRITERIA =====
const dataKesiapan = {
  c1: { title: 'C.1 VMTS', indicators: [
    { name: 'Kekhasan VMTS', status: 'ready' },
    { name: 'Mekanisme Penyusunan', status: 'ready' },
    { name: 'Tingkat Pemahaman Stakeholder', status: 'ready' },
    { name: 'Sosialisasi VMTS', status: 'ready' },
    { name: 'Pencapaian Sasaran', status: 'ready' }
  ]},
  c2: { title: 'C.2 Tata Pamong, Tata Kelola, Kerja Sama, Keuangan', indicators: [
    { name: 'Sistem Tata Pamong', status: 'ready' },
    { name: 'Kerja Sama Tridharma', status: 'ready' },
    { name: 'Implementasi Kerja Sama', status: 'warn' },
    { name: 'Pengelolaan Keuangan', status: 'ready' },
    { name: 'Transparansi & Akuntabilitas', status: 'ready' }
  ]},
  c3: { title: 'C.3 Relevansi Pendidikan, Penelitian & PkM', indicators: [
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
  ]},
  c4: { title: 'C.4 Sumber Daya Manusia', indicators: [
    { name: 'Profil DTPS', status: 'ready' }, { name: 'Tenaga Kependidikan', status: 'ready' },
    { name: 'Beban Kerja Dosen', status: 'ready' }, { name: 'Publikasi Ilmiah', status: 'ready' },
    { name: 'Rekognisi DTPS', status: 'ready' }
  ]},
  c5: { title: 'C.5 Sarana, Prasarana & K3L', indicators: [
    { name: 'Prasarana Pembelajaran', status: 'ready' }, { name: 'Peralatan Laboratorium', status: 'ready' },
    { name: 'Dokumen K3L', status: 'warn' }, { name: 'Fasilitas K3L', status: 'ready' }
  ]},
  c6: { title: 'C.6 Mahasiswa dan Luaran', indicators: [
    { name: 'Rasio Mahasiswa:DTPS', status: 'ready' }, { name: 'Tracer Study', status: 'warn' },
    { name: 'Prestasi Mahasiswa', status: 'ready' }, { name: 'Kinerja Lulusan', status: 'warn' },
    { name: 'Kesesuaian Bidang Kerja', status: 'warn' }
  ]},
  c7: { title: 'C.7 Sistem Penjaminan Mutu', indicators: [
    { name: 'Unit Penjaminan Mutu', status: 'ready' }, { name: 'Perangkat SPMI', status: 'ready' },
    { name: 'Siklus PPEPP', status: 'warn' }, { name: 'Audit Mutu Internal', status: 'warn' },
    { name: 'Kepuasan Stakeholder', status: 'warn' }
  ]}
};

const dataDetail = {
  tinjauanCPL: {
    klaim: 'PSBM melakukan tinjauan CPL secara berkala sebagai bagian dari evaluasi dan pengembangan kurikulum.',
    jawaban: 'PSBM melakukan tinjauan CPL setiap 2 tahun melalui mekanisme terstruktur yang melibatkan tracer study, survei pengguna lulusan, forum industri, dan workshop OBE.',
    data: ['Kurikulum 2020 (NADK)', 'Workshop OBE 2024', '11 dosen terlibat', '3 alumni + 3 narasumber eksternal'],
    bukti: ['NADK PSBM 2020', 'Laporan Workshop OBE 2024', 'Matriks Profil–CPL', 'Masukan Industri', 'Dokumen Tindak Lanjut'],
    tindak: 'Penguatan keterkaitan PL–CPL–bidang kajian dan pengembangan kurikulum berbasis OBE.',
    pic: 'Tim Kurikulum (VF + BU)'
  },
  klaimCPL: {
    klaim: 'PSBM merumuskan profil lulusan dan CPL yang selaras dengan KKNI Level 6 dan kebutuhan industri broadband multimedia.',
    jawaban: 'Profil lulusan disusun berdasarkan analisis kebutuhan industri melalui tracer study, forum industri, dan benchmarking.',
    data: ['12 CPL terdefinisi', 'KKNI Level 6', '6 profil lulusan', 'Benchmarking 3 PT'],
    bukti: ['NADK PSBM 2020', 'Matriks Profil–CPL', 'Laporan Analisis Kebutuhan', 'Notulensi Forum Industri'],
    tindak: 'Pemutakhiran CPL berbasis hasil tracer study 2024.',
    pic: 'Tim Kurikulum'
  }
};

// ===== DATA PERTANYAAN SIMULASI AL (9 Pertanyaan C.1 VMTS) =====
const dataSimulasi = [
  {
    no: 1, indikator: 'Kekhasan VMTS',
    pertanyaan: 'Apa kekhasan VMTS JTE dan visi keilmuan PSBM dibanding program sejenis?',
    followup: 'Apa yang benar-benar membedakan PSBM, bukan sekadar penggunaan istilah Broadband Multimedia?',
    dataLKPS: 'Tabel 1',
    bukti: 'VMTS PNJ/JTE/PSBM',
    pic: 'Kaprodi/Kajur',
    risiko: 'Tinggi'
  },
  {
    no: 2, indikator: 'Kekhasan VMTS',
    pertanyaan: 'Bagaimana linearitas visi PNJ → VMTS JTE → visi keilmuan PSBM?',
    followup: 'Tunjukkan keterkaitannya secara eksplisit.',
    dataLKPS: 'Tabel 1',
    bukti: 'Matriks sinkronisasi VMTS',
    pic: 'Kaprodi',
    risiko: 'Tinggi'
  },
  {
    no: 3, indikator: 'Kekhasan VMTS',
    pertanyaan: 'Bagaimana visi keilmuan PSBM diterjemahkan ke kurikulum?',
    followup: 'MK apa yang paling merepresentasikan kekhasan tersebut?',
    dataLKPS: '3.a.1',
    bukti: 'NADK, struktur kurikulum',
    pic: 'Kaprodi/Kurikulum',
    risiko: 'Tinggi'
  },
  {
    no: 4, indikator: 'Mekanisme VMTS',
    pertanyaan: 'Bagaimana VMTS dan visi keilmuan disusun?',
    followup: 'Siapa pemangku kepentingan internal dan eksternal yang terlibat?',
    dataLKPS: '—',
    bukti: 'SK tim, undangan, daftar hadir, BA',
    pic: 'Kajur',
    risiko: 'Sedang'
  },
  {
    no: 5, indikator: 'Mekanisme VMTS',
    pertanyaan: 'Bagaimana kebutuhan masyarakat dan tantangan global dipertimbangkan?',
    followup: 'Masukan apa yang akhirnya masuk ke visi/strategi?',
    dataLKPS: '—',
    bukti: 'Notulen/workshop/FGD',
    pic: 'Kajur/Kaprodi',
    risiko: 'Sedang'
  },
  {
    no: 6, indikator: 'Mekanisme VMTS',
    pertanyaan: 'Apa bukti bahwa alumni, pengguna lulusan, dan pakar benar-benar terlibat?',
    followup: 'Apakah hanya hadir atau memberikan masukan?',
    dataLKPS: '—',
    bukti: 'Daftar hadir + masukan + tindak lanjut',
    pic: 'Kaprodi',
    risiko: 'Tinggi'
  },
  {
    no: 7, indikator: 'Pemahaman & Pencapaian VMTS',
    pertanyaan: 'Bagaimana VMTS disosialisasikan dan diukur tingkat pemahamannya?',
    followup: 'Berapa hasil pengukuran pemahaman stakeholder?',
    dataLKPS: 'Tabel 1',
    bukti: 'Survei VMTS',
    pic: 'Kajur/GPM',
    risiko: 'Tinggi'
  },
  {
    no: 8, indikator: 'Pemahaman & Pencapaian VMTS',
    pertanyaan: 'Apa capaian konkret jangka pendek/menengah dari VMTS?',
    followup: 'Tunjukkan target versus realisasi.',
    dataLKPS: 'LKPS terkait',
    bukti: 'Renstra, Renop, laporan capaian',
    pic: 'Kajur',
    risiko: 'Tinggi'
  },
  {
    no: 9, indikator: 'Pemahaman & Pencapaian VMTS',
    pertanyaan: 'Apa bukti VMTS berdampak dan berkelanjutan?',
    followup: 'Perubahan apa yang dapat dikaitkan langsung dengan VMTS?',
    dataLKPS: 'C.3/C.4/C.6',
    bukti: 'Laporan kinerja',
    pic: 'Kajur/Kaprodi',
    risiko: 'Tinggi'
  }
];

// ===== DATA MODE AL =====
const dataModeAL = {
  'vmts': { title: 'C.1 > VMTS', jawaban: 'VMTS PSBM selaras dengan VMTS PNJ dan visi keilmuan broadband multimedia.', data: ['SK VMTS PT', 'SK VMTS UPPS', 'Visi Keilmuan PS'], bukti: ['SK VMTS PT', 'SK VMTS UPPS', 'Dokumen Visi Keilmuan'], tindak: 'Sosialisasi VMTS ke seluruh stakeholder.', followup: [] },
  'kekhasan': { title: 'C.1 > KEKHASAN VMTS', jawaban: 'Kekhasan PSBM terletak pada integrasi broadband, multimedia, dan IoT yang tidak dimiliki program sejenis.', data: ['Matriks sinkronisasi VMTS', 'Benchmarking 3 PT'], bukti: ['VMTS PNJ/JTE/PSBM', 'Matriks perbandingan'], tindak: 'Penguatan branding keilmuan.', followup: ['Apa yang membedakan?', 'Tunjukkan secara eksplisit'] },
  'linearitas': { title: 'C.1 > LINEARITAS VISI', jawaban: 'Visi PNJ → VMTS JTE → Visi Keilmuan PSBM memiliki benang merah yang terdokumentasi.', data: ['Tabel 1 LKPS'], bukti: ['Matriks sinkronisasi VMTS'], tindak: 'Verifikasi keterkaitan eksplisit.', followup: ['Tunjukkan keterkaitannya'] },
  'kurikulum': { title: 'C.3 > KURIKULUM', jawaban: 'Kurikulum PSBM berbasis KKNI Level 6 dan OBE dengan 144 SKS.', data: ['144 SKS', 'KKNI Level 6', 'OBE 2020'], bukti: ['Dokumen Kurikulum', 'Matriks CPL-MK', 'RPS Lengkap'], tindak: 'Revisi Kurikulum OBE 2025.', followup: [] },
  'cpl': { title: 'C.3 > CPL', jawaban: '12 CPL PSBM diturunkan dari profil lulusan dan dipetakan ke setiap MK.', data: ['12 CPL', '6 Profil Lulusan'], bukti: ['NADK PSBM 2020', 'Matriks CPL-MK'], tindak: 'Tinjauan CPL berbasis tracer study.', followup: [] },
  'led': { title: 'DOKUMEN UTAMA', jawaban: 'LED PSBM 2026 disusun berdasarkan 7 kriteria LAM Teknik Edisi 2025.', data: ['7 kriteria', '200+ halaman'], bukti: ['File LED.pdf', 'File LKPS.pdf'], tindak: 'Finalisasi minggu ke-2.', followup: [] },
  'lkps': { title: 'DOKUMEN UTAMA', jawaban: 'LKPS berisi data kuantitatif 3 tahun terakhir.', data: ['31 tabel LKPS'], bukti: ['File LKPS.pdf'], tindak: 'Verifikasi data.', followup: [] },
  'tracer': { title: 'C.6 > TRACER STUDY', jawaban: 'Response rate 68% pada 2024.', data: ['Response rate 68%', 'Minimal 30%'], bukti: ['Laporan Tracer 2024'], tindak: 'Target 80%.', followup: ['Strategi peningkatan?'] },
  'penelitian': { title: 'C.3 > PENELITIAN', jawaban: '45 penelitian DTPS (3 tahun), 12 melibatkan mahasiswa.', data: ['45 judul', '26,67% keterlibatan'], bukti: ['LKPS Tabel 3.b'], tindak: 'Target 40% keterlibatan.', followup: [] },
  'pkm': { title: 'C.3 > PkM', jawaban: '28 judul PkM (3 tahun).', data: ['28 judul'], bukti: ['LKPS Tabel 3.c'], tindak: 'Peningkatan adopsi.', followup: [] },
  'rps': { title: 'C.3 > RPS', jawaban: '100% MK punya RPS.', data: ['Tinjauan 2024'], bukti: ['Kumpulan RPS'], tindak: 'Update RPS.', followup: [] },
  'roadmap': { title: 'C.3 > ROADMAP', jawaban: 'Roadmap 2020-2025, 4 bidang fokus.', data: ['4 bidang'], bukti: ['Dokumen Roadmap'], tindak: 'Perpanjangan 2025-2030.', followup: [] },
  'kerja sama': { title: 'C.2 > KERJA SAMA', jawaban: '25 MoU aktif, 15 implementasi.', data: ['25 MoU', '15 implementasi'], bukti: ['Daftar MoU'], tindak: 'Peningkatan implementasi.', followup: [] },
  'ami': { title: 'C.7 > AMI/RTM', jawaban: 'AMI 2025, 15 temuan.', data: ['15 temuan', 'RTM 2025'], bukti: ['Laporan AMI 2025'], tindak: 'Penyelesaian temuan.', followup: [] }
};

// ===== NAVIGATION =====
function showPanel(id, btn) {
  document.querySelectorAll('.al-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.folder-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  if (id === 'kesiapan') showKesiapan('c1', document.querySelector('#kesiapanSubNav button'));
  if (id === 'simulasi') renderSimulasi('semua');
}

// ===== KESIAPAN KRITERIA =====
function showKesiapan(key, btn) {
  document.querySelectorAll('#kesiapanSubNav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  const k = dataKesiapan[key];
  let html = '<h3 style="color:#0d47a1; margin:0 0 16px 0;">' + k.title + '</h3><div class="indicator-list">';
  k.indicators.forEach(ind => {
    const w = ind.status === 'warn' ? 'warn' : '';
    const ic = ind.status === 'ready' ? 'ready' : 'warn';
    const icon = ind.status === 'ready' ? '✓' : '⚠';
    html += '<div class="indicator-row ' + w + '" onclick="showDetail(this, \'' + (ind.detail || '') + '\')"><div class="name">' + ind.name + '</div><div class="status-icon ' + ic + '">' + icon + '</div></div>';
  });
  html += '</div><div id="detailContainer"></div>';
  document.getElementById('kesiapanContent').innerHTML = html;
}

function showDetail(row, detailKey) {
  document.querySelectorAll('.indicator-row').forEach(r => r.classList.remove('active'));
  row.classList.add('active');
  const container = document.getElementById('detailContainer');
  if (!detailKey || !dataDetail[detailKey]) {
    container.innerHTML = '<div class="detail-panel"><p style="color:#666; text-align:center;">Detail belum tersedia. Hubungi koordinator.</p></div>';
    return;
  }
  const d = dataDetail[detailKey];
  let html = '<div class="detail-panel">';
  html += '<div class="detail-section klaim"><div class="section-title">1. KLAIM LED</div><div class="section-content">' + d.klaim + '</div></div>';
  html += '<div class="detail-section jawaban"><div class="section-title">2. JAWABAN AL</div><div class="section-content">' + d.jawaban + '</div></div>';
  html += '<div class="detail-section data"><div class="section-title">3. DATA KUNCI</div><ul>';
  d.data.forEach(i => { html += '<li>' + i + '</li>'; });
  html += '</ul></div><div class="detail-section bukti"><div class="section-title">4. BUKTI</div><ul>';
  d.bukti.forEach(i => { html += '<li>✓ ' + i + '</li>'; });
  html += '</ul></div><div class="detail-section tindak"><div class="section-title">5. TINDAK LANJUT / DAMPAK</div><div class="section-content">' + d.tindak + '</div></div>';
  html += '<div class="pic-tag">PIC: ' + d.pic + '</div></div>';
  container.innerHTML = html;
}

// ===== SIMULASI AL =====
function renderSimulasi(filter) {
  let filtered = dataSimulasi;
  if (filter === 'tinggi') filtered = dataSimulasi.filter(q => q.risiko === 'Tinggi');
  else if (filter === 'sedang') filtered = dataSimulasi.filter(q => q.risiko === 'Sedang');
  else if (filter === 'kaprodi') filtered = dataSimulasi.filter(q => q.pic.toLowerCase().includes('kaprodi'));
  else if (filter === 'kajur') filtered = dataSimulasi.filter(q => q.pic.toLowerCase().includes('kajur'));

  let html = '<div style="margin-bottom:12px; font-size:0.85rem; color:#666;">Menampilkan <strong>' + filtered.length + '</strong> pertanyaan</div>';

  filtered.forEach(q => {
    const riskClass = q.risiko === 'Tinggi' ? 'tinggi' : 'sedang';
    html += '<div class="q-card" id="qcard-' + q.no + '">';
    html += '<div class="q-card-header" onclick="toggleQ(' + q.no + ')">';
    html += '<div class="q-num">Q' + q.no + '</div>';
    html += '<div class="q-main">' + q.pertanyaan + '</div>';
    html += '<div class="q-risk ' + riskClass + '">' + q.risiko + '</div>';
    html += '<div class="q-toggle">▼</div>';
    html += '</div>';
    html += '<div class="q-card-body">';

    // Indikator
    html += '<div class="q-section"><div class="q-section-title"><span class="icon">📑</span> INDIKATOR MATRIKS</div><div class="q-section-content">C.1 — ' + q.indikator + '</div></div>';

    // Pertanyaan Utama
    html += '<div class="q-section"><div class="q-section-title"><span class="icon">❓</span> PERTANYAAN UTAMA</div><div class="q-section-content">' + q.pertanyaan + '</div></div>';

    // Follow-up Kritis
    html += '<div class="q-followup"><div class="followup-label">🔥 FOLLOW-UP / KRITIS</div><div class="followup-text">' + q.followup + '</div></div>';

    // Meta Grid
    html += '<div class="q-meta-grid">';
    html += '<div class="q-meta-item"><div class="meta-label">📊 Data LKPS</div><div class="meta-value">' + q.dataLKPS + '</div></div>';
    html += '<div class="q-meta-item"><div class="meta-label">👤 PIC</div><div class="meta-value">' + q.pic + '</div></div>';
    html += '<div class="q-meta-item" style="grid-column: 1 / -1;"><div class="meta-label">📎 Bukti yang Harus Ditunjukkan</div><div class="meta-value">' + q.bukti + '</div></div>';
    html += '</div>';

    // Skor
    html += '<div class="q-section" style="margin-top:14px;"><div class="q-section-title"><span class="icon">⭐</span> BERI SKOR LATIHAN</div>';
    html += '<div class="q-score-row">';
    html += '<div class="q-score-btn" onclick="event.stopPropagation(); giveScore(' + q.no + ', 0)">0<span class="score-sub">Tidak jawab</span></div>';
    html += '<div class="q-score-btn" onclick="event.stopPropagation(); giveScore(' + q.no + ', 1)">1<span class="score-sub">Umum</span></div>';
    html += '<div class="q-score-btn" onclick="event.stopPropagation(); giveScore(' + q.no + ', 2)">2<span class="score-sub">+ Data</span></div>';
    html += '<div class="q-score-btn" onclick="event.stopPropagation(); giveScore(' + q.no + ', 3)">3<span class="score-sub">+ Bukti</span></div>';
    html += '<div class="q-score-btn" onclick="event.stopPropagation(); giveScore(' + q.no + ', 4)">4<span class="score-sub">+ Dampak</span></div>';
    html += '</div></div>';

    html += '</div></div>';
  });

  document.getElementById('simulasiContent').innerHTML = html;
}

function filterSim(filter, btn) {
  document.querySelectorAll('.sim-mode-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  renderSimulasi(filter);
}

function toggleQ(no) {
  const card = document.getElementById('qcard-' + no);
  card.classList.toggle('open');
}

function giveScore(no, score) {
  const labels = ['Tidak menjawab', 'Jawaban umum', '+ Data', '+ Data + Bukti', '+ Tindak Lanjut'];
  alert('Q' + no + ' — Skor: ' + score + ' (' + labels[score] + ')\n\nMasuk daftar latihan berikutnya.');
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
  if (!query) { resultDiv.classList.remove('active'); return; }
  let found = null;
  for (const key in dataModeAL) {
    if (key.includes(query) || dataModeAL[key].title.toLowerCase().includes(query)) { found = dataModeAL[key]; break; }
  }
  if (!found) { resultDiv.classList.remove('active'); return; }
  let html = '<h3>' + found.title + '</h3>';
  html += '<div class="result-section"><div class="section-title">JAWABAN INTI</div><div class="section-content">' + found.jawaban + '</div></div>';
  html += '<div class="result-section"><div class="section-title">DATA KUNCI</div><ul>';
  found.data.forEach(d => { html += '<li>' + d + '</li>'; });
  html += '</ul></div><div class="result-section"><div class="section-title">BUKTI</div><ul>';
  found.bukti.forEach(b => { html += '<li>✓ ' + b + '</li>'; });
  html += '</ul></div>';
  if (found.tindak) html += '<div class="result-section"><div class="section-title">TINDAK LANJUT</div><div class="section-content">' + found.tindak + '</div></div>';
  if (found.followup && found.followup.length > 0) {
    html += '<div class="result-section followup"><div class="section-title">FOLLOW-UP</div><ul>';
    found.followup.forEach(f => { html += '<li>→ ' + f + '</li>'; });
    html += '</ul></div>';
  }
  resultDiv.innerHTML = html;
  resultDiv.classList.add('active');
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  showKesiapan('c1', document.querySelector('#kesiapanSubNav button'));
  renderSimulasi('semua');
});
</script>

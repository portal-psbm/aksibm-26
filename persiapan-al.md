---
layout: default
title: Persiapan AL
permalink: /persiapan-al/
---

<style>
  .cabinet-container { background: linear-gradient(180deg, #e3f2fd 0%, #bbdefb 100%); padding: 20px 20px 0 20px; border-radius: 16px 16px 0 0; box-shadow: inset 0 4px 12px rgba(13, 71, 161, 0.08), 0 4px 16px rgba(0,0,0,0.06); position: relative; border: 1px solid #bbdefb; border-bottom: none; }
  .folder-shelf { display: flex; flex-wrap: nowrap; gap: 8px; padding: 0 8px; position: relative; z-index: 10; overflow-x: auto; overflow-y: visible; scrollbar-width: thin; scrollbar-color: #0d47a1 transparent; padding-bottom: 4px; }
  .folder-shelf::-webkit-scrollbar { height: 4px; }
  .folder-shelf::-webkit-scrollbar-track { background: rgba(13, 71, 161, 0.05); border-radius: 2px; }
  .folder-shelf::-webkit-scrollbar-thumb { background: #0d47a1; border-radius: 2px; }
  .folder-tab { position: relative; flex: 1 1 0; min-width: 0; padding: 16px 10px 20px 10px; background: #ffffff; border-radius: 10px 10px 0 0; border: 1px solid #e0e0e0; border-bottom: none; cursor: pointer; text-align: center; font-weight: 600; font-size: 0.85rem; line-height: 1.2; color: #555; transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1); transform: translateY(4px); box-shadow: 0 -2px 6px rgba(0,0,0,0.05); white-space: normal; word-wrap: break-word; overflow-wrap: break-word; }
  .folder-tab::before { content: ''; position: absolute; top: -7px; left: 22%; width: 56%; height: 7px; background: #f5f5f5; border-radius: 4px 4px 0 0; border: 1px solid #e0e0e0; border-bottom: none; transition: all 0.35s ease; }
  .folder-tab:hover { background: #f1f5f9; transform: translateY(0px); color: #0d47a1; }
  .folder-tab:hover::before { background: #f1f5f9; }
  .folder-tab.active { background: #0d47a1; color: #ffffff; transform: translateY(-6px); z-index: 20; border-color: #0d47a1; box-shadow: 0 -4px 16px rgba(13, 71, 161, 0.25); font-weight: 700; }
  .folder-tab.active::before { background: #0d47a1; border-color: #0d47a1; height: 9px; top: -9px; }
  .folder-tab.mode-al { background: linear-gradient(180deg, #fff8e1 0%, #ffecb3 100%); color: #e65100; border-color: #ffcc80; box-shadow: 0 -2px 8px rgba(230, 81, 0, 0.12); }
  .folder-tab.mode-al::before { background: linear-gradient(180deg, #ffcc80 0%, #ffb74d 100%); border-color: #ffcc80; }
  .folder-tab.mode-al:hover { background: linear-gradient(180deg, #fff3e0 0%, #ffe0b2 100%); color: #bf360c; transform: translateY(0px); }
  .folder-tab.mode-al:hover::before { background: linear-gradient(180deg, #ffb74d 0%, #ffa726 100%); border-color: #ffb74d; }
  .folder-tab.mode-al.active { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); color: #ffffff; border-color: #0d47a1; box-shadow: 0 -6px 20px rgba(13, 71, 161, 0.5); animation: pulseMode 2.5s ease-in-out infinite; }
  .folder-tab.mode-al.active::before { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); border-color: #0d47a1; height: 9px; top: -9px; }
  @keyframes pulseMode { 0%, 100% { box-shadow: 0 -6px 20px rgba(13, 71, 161, 0.5); } 50% { box-shadow: 0 -6px 28px rgba(13, 71, 161, 0.7); } }
  .al-content { background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1; border-radius: 0 0 16px 16px; padding: 28px; min-height: 500px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px; }
  .al-panel { display: none; animation: fadeIn 0.3s ease; }
  .al-panel.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

  .stats-bar { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 10px; margin-bottom: 16px; }
  .stat-mini { background: white; border: 1px solid #e0e0e0; border-radius: 8px; padding: 12px; text-align: center; border-left: 4px solid #0d47a1; }
  .stat-mini .snum { font-size: 1.5rem; font-weight: 800; color: #0d47a1; }
  .stat-mini .slbl { font-size: 0.75rem; color: #666; text-transform: uppercase; letter-spacing: 0.5px; margin-top: 2px; }
  .stat-mini.kritis { border-left-color: #c62828; }
  .stat-mini.kritis .snum { color: #c62828; }
  .stat-mini.tinggi { border-left-color: #e65100; }
  .stat-mini.tinggi .snum { color: #e65100; }
  .stat-mini.sedang { border-left-color: #f57c00; }
  .stat-mini.sedang .snum { color: #f57c00; }
  .stat-mini.rendah { border-left-color: #2e7d32; }
  .stat-mini.rendah .snum { color: #2e7d32; }

  .filter-bar { display: flex; gap: 8px; margin-bottom: 16px; flex-wrap: wrap; padding: 12px; background: #f8fafc; border-radius: 8px; border: 1px solid #e0e0e0; }
  .filter-bar select, .filter-bar input { padding: 8px 12px; border: 1px solid #e0e0e0; border-radius: 6px; font-size: 0.85rem; background: white; }
  .filter-bar input { flex: 1; min-width: 200px; }
  .filter-bar input:focus, .filter-bar select:focus { outline: none; border-color: #0d47a1; }

  .sub-nav { display: flex; gap: 4px; margin-bottom: 16px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
  .sub-nav button { padding: 10px 16px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.88rem; }
  .sub-nav button:hover { color: #0d47a1; background: #f8fafc; }
  .sub-nav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }
  .sub-nav button .count { background: #e3f2fd; color: #0d47a1; padding: 2px 8px; border-radius: 10px; font-size: 0.75rem; margin-left: 4px; font-weight: 700; }
  .sub-nav button.active .count { background: #0d47a1; color: white; }
  .sub-nav button.bab3-btn { background: linear-gradient(135deg, #fff8e1 0%, #ffecb3 100%); color: #e65100; border-radius: 6px; border: 1px solid #ffcc80; }
  .sub-nav button.bab3-btn.active { background: linear-gradient(135deg, #e65100 0%, #bf360c 100%); color: white; border-color: #bf360c; }
  .sub-nav button.bab3-btn .count { background: #ffe0b2; color: #bf360c; }
  .sub-nav button.bab3-btn.active .count { background: white; color: #bf360c; }

  .q-card { background: white; border: 1px solid #e0e0e0; border-radius: 10px; margin-bottom: 10px; overflow: hidden; transition: all 0.2s; box-shadow: 0 2px 6px rgba(0,0,0,0.04); }
  .q-card:hover { box-shadow: 0 4px 14px rgba(0,0,0,0.08); }
  .q-card.bab3 { border-left: 4px solid #e65100; }
  .q-card-header { display: flex; align-items: center; gap: 10px; padding: 12px 14px; cursor: pointer; background: #f8fafc; border-bottom: 1px solid #e0e0e0; transition: background 0.2s; flex-wrap: wrap; }
  .q-card.bab3 .q-card-header { background: #fff8e1; }
  .q-card-header:hover { background: #e3f2fd; }
  .q-card.bab3 .q-card-header:hover { background: #ffecb3; }
  .q-num { font-weight: 800; color: #0d47a1; font-size: 0.85rem; min-width: 40px; font-family: 'Courier New', monospace; }
  .q-card.bab3 .q-num { color: #e65100; }
  .q-ind { font-size: 0.72rem; color: #888; background: #eceff1; padding: 2px 8px; border-radius: 10px; font-weight: 600; }
  .q-card.bab3 .q-ind { background: #ffe0b2; color: #bf360c; }
  .q-main { flex: 1; font-weight: 600; color: #333; font-size: 0.88rem; line-height: 1.4; min-width: 200px; }
  .q-risk { padding: 4px 10px; border-radius: 12px; font-size: 0.7rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.3px; white-space: nowrap; }
  .q-risk.Kritis { background: #ffebee; color: #b71c1c; border: 1px solid #ef9a9a; }
  .q-risk.Tinggi { background: #fff3e0; color: #e65100; border: 1px solid #ffcc80; }
  .q-risk.Sedang { background: #fff8e1; color: #f57c00; border: 1px solid #ffe082; }
  .q-risk.Rendah { background: #e8f5e9; color: #2e7d32; border: 1px solid #a5d6a7; }
  .q-card-header .q-toggle { font-size: 1rem; color: #999; transition: transform 0.3s; }
  .q-card.open .q-card-header .q-toggle { transform: rotate(180deg); }
  .q-card-body { display: none; padding: 16px; background: white; }
  .q-card.open .q-card-body { display: block; animation: fadeIn 0.3s ease; }

  .q-section { margin-bottom: 12px; padding-bottom: 12px; border-bottom: 1px dashed #e0e0e0; }
  .q-section:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }
  .q-section-title { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 1px; font-weight: 700; color: #0d47a1; margin-bottom: 6px; display: flex; align-items: center; gap: 6px; }
  .q-card.bab3 .q-section-title { color: #e65100; }
  .q-section-content { font-size: 0.88rem; color: #333; line-height: 1.5; }
  .q-followup { background: #fff8e1; border-left: 4px solid #ff9800; padding: 10px 14px; border-radius: 6px; margin-top: 8px; }
  .q-followup .flabel { font-size: 0.72rem; text-transform: uppercase; letter-spacing: 1px; font-weight: 700; color: #e65100; margin-bottom: 4px; }
  .q-followup .ftext { font-size: 0.88rem; color: #555; font-style: italic; line-height: 1.5; }
  .q-meta-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 8px; margin-top: 10px; }
  .q-meta-item { background: #f8fafc; padding: 8px 10px; border-radius: 6px; border-left: 3px solid #0d47a1; }
  .q-card.bab3 .q-meta-item { border-left-color: #e65100; }
  .q-meta-item .mlabel { font-size: 0.68rem; text-transform: uppercase; letter-spacing: 0.5px; color: #888; font-weight: 600; }
  .q-meta-item .mvalue { font-size: 0.82rem; color: #333; font-weight: 600; margin-top: 2px; }

  /* ===== Mode AL ===== */
  .mode-al-hero { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); color: white; padding: 28px; border-radius: 12px; margin-bottom: 20px; text-align: center; }
  .mode-al-hero h2 { margin: 0 0 6px 0; font-size: 1.4rem; }
  .mode-al-hero .subtitle { opacity: 0.9; font-size: 0.9rem; margin-bottom: 16px; }
  .mode-al-search-wrapper { display: flex; gap: 8px; max-width: 700px; margin: 0 auto 16px auto; }
  .mode-al-search { flex: 1; padding: 16px 24px; border-radius: 30px; border: 2px solid rgba(255,255,255,0.3); background: rgba(255,255,255,0.15); color: white; font-size: 1rem; backdrop-filter: blur(4px); }
  .mode-al-search::placeholder { color: rgba(255,255,255,0.7); }
  .mode-al-search:focus { outline: none; border-color: #fff; background: rgba(255,255,255,0.25); }
  .mode-al-btn { padding: 16px 24px; border-radius: 30px; border: none; font-size: 1rem; font-weight: 600; cursor: pointer; transition: all 0.2s; white-space: nowrap; }
  .mode-al-btn.search { background: #4caf50; color: white; }
  .mode-al-btn.search:hover { background: #45a049; }
  .mode-al-btn.clear { background: rgba(255,255,255,0.2); color: white; border: 2px solid rgba(255,255,255,0.5); }
  .mode-al-btn.clear:hover { background: rgba(255,255,255,0.3); }
  .quick-chips { display: flex; gap: 6px; justify-content: center; flex-wrap: wrap; margin-top: 16px; }
  .quick-chip { padding: 6px 12px; background: rgba(255,255,255,0.15); border: 1px solid rgba(255,255,255,0.3); border-radius: 16px; color: white; cursor: pointer; font-weight: 600; font-size: 0.78rem; transition: all 0.2s; }
  .quick-chip:hover { background: rgba(255,255,255,0.3); }
  .quick-chip.bab3 { background: rgba(230, 81, 0, 0.25); border-color: rgba(255, 183, 77, 0.5); }
  .quick-chip.bab3:hover { background: rgba(230, 81, 0, 0.4); }

  .no-result { text-align: center; padding: 40px 20px; color: #888; background: #f8fafc; border-radius: 10px; }

  /* ===== Data Kunci LKPS ===== */
  .lkps-hero { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); color: white; padding: 24px; border-radius: 12px; margin-bottom: 20px; text-align: center; }
  .lkps-hero h2 { margin: 0 0 6px 0; font-size: 1.3rem; }
  .lkps-hero .subtitle { opacity: 0.9; font-size: 0.88rem; }
  .lkps-warning { display: inline-block; background: #c62828; color: white; padding: 4px 12px; border-radius: 12px; font-size: 0.75rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.5px; margin-top: 10px; }

  .super-priority-box { background: linear-gradient(135deg, #fff8e1 0%, #ffecb3 100%); border: 2px solid #ff9800; border-radius: 12px; padding: 20px; margin-bottom: 20px; }
  .super-priority-box h3 { margin: 0 0 12px 0; color: #e65100; font-size: 1rem; display: flex; align-items: center; gap: 8px; }
  .super-priority-box .sp-item { background: white; padding: 10px 14px; border-radius: 8px; margin-bottom: 8px; font-size: 0.88rem; color: #333; border-left: 4px solid #ff9800; font-family: 'Courier New', monospace; font-weight: 600; line-height: 1.6; }
  .super-priority-box .sp-item:last-child { margin-bottom: 0; }

  .critical-notes-box { background: #ffebee; border: 2px solid #c62828; border-radius: 12px; padding: 20px; margin-bottom: 20px; }
  .critical-notes-box h3 { margin: 0 0 12px 0; color: #c62828; font-size: 1rem; display: flex; align-items: center; gap: 8px; }
  .critical-notes-box .cn-item { background: white; padding: 12px 14px; border-radius: 8px; margin-bottom: 8px; font-size: 0.88rem; color: #333; border-left: 4px solid #c62828; line-height: 1.5; }
  .critical-notes-box .cn-item:last-child { margin-bottom: 0; }
  .critical-notes-box .cn-item strong { color: #c62828; }

  .lkps-cat-tabs { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 16px; }
  .lkps-cat-btn { padding: 8px 14px; background: white; border: 2px solid #e0e0e0; border-radius: 20px; cursor: pointer; font-weight: 600; font-size: 0.82rem; color: #555; transition: all 0.2s; }
  .lkps-cat-btn:hover { border-color: #0d47a1; color: #0d47a1; }
  .lkps-cat-btn.active { background: #0d47a1; color: white; border-color: #0d47a1; }

  .lkps-card { background: white; border: 1px solid #e0e0e0; border-radius: 10px; padding: 14px 16px; margin-bottom: 10px; border-left: 4px solid #0d47a1; transition: all 0.2s; }
  .lkps-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); transform: translateX(2px); }
  .lkps-card.wajib { border-left-color: #c62828; background: #fff8f8; }
  .lkps-card-header { display: flex; justify-content: space-between; align-items: flex-start; gap: 10px; margin-bottom: 8px; flex-wrap: wrap; }
  .lkps-card-title { font-weight: 700; color: #333; font-size: 0.95rem; flex: 1; min-width: 200px; }
  .lkps-card-value { font-size: 1.4rem; font-weight: 800; color: #0d47a1; background: #e3f2fd; padding: 6px 12px; border-radius: 8px; white-space: nowrap; }
  .lkps-card.wajib .lkps-card-value { background: #ffebee; color: #c62828; }
  .wajib-badge { display: inline-block; background: #c62828; color: white; padding: 3px 8px; border-radius: 10px; font-size: 0.68rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.5px; margin-left: 6px; }
  .lkps-card-note { font-size: 0.82rem; color: #666; line-height: 1.5; margin-bottom: 8px; }
  .lkps-card-note strong { color: #333; }
  .lkps-card-actions { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 8px; padding-top: 8px; border-top: 1px dashed #e0e0e0; }
  .lkps-btn { padding: 4px 10px; border-radius: 6px; border: 1px solid #0d47a1; background: white; color: #0d47a1; font-size: 0.75rem; font-weight: 600; cursor: pointer; transition: all 0.2s; }
  .lkps-btn:hover { background: #0d47a1; color: white; }
  .lkps-btn.primary { background: #0d47a1; color: white; }
  .lkps-btn.primary:hover { background: #1565c0; }

  @media (max-width: 767px) {
    .folder-shelf { gap: 6px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
    .folder-shelf::-webkit-scrollbar { display: none; }
    .folder-tab { min-width: 110px; flex: 0 0 auto; font-size: 0.8rem; }
    .al-content { padding: 20px; }
    .q-meta-grid { grid-template-columns: 1fr; }
    .q-card-header { flex-wrap: wrap; gap: 6px; }
    .q-main { margin: 4px 0; min-width: 100%; order: 3; }
    .lkps-card-header { flex-direction: column; }
    .mode-al-search-wrapper { flex-direction: column; }
    .mode-al-btn { width: 100%; }
  }
</style>

<div class="cabinet-container">
  <div class="folder-shelf">
    <div class="folder-tab mode-al active" onclick="showPanel('modeal', this)">🎯<br>MODE AL</div>
    <div class="folder-tab" onclick="showPanel('data', this)">📊<br>DATA KUNCI</div>
    <div class="folder-tab" onclick="showPanel('bank', this)">❓<br>BANK PERTANYAAN</div>
  </div>

  <div class="al-content" id="alContent">

    <!-- ========== MODE AL ========== -->
    <div class="al-panel active" id="panel-modeal">
      <div class="mode-al-hero">
        <h2>🎯 MODE ASESMEN LAPANGAN</h2>
        <div class="subtitle">Cari dari 243 pertanyaan asesmen PSBM (C.1–C.7 + BAB III)</div>
        <div class="mode-al-search-wrapper">
          <input type="text" class="mode-al-search" id="modeAlSearch" placeholder="🔎 Ketik: VMTS, 66 kerja sama, 11 DTPS, tracer, CPL, SWOT..." onkeypress="if(event.key==='Enter') searchModeAL()">
          <button class="mode-al-btn search" onclick="searchModeAL()">🔍 Cari</button>
          <button class="mode-al-btn clear" onclick="clearSearch()"> Clear</button>
        </div>
        <div class="quick-chips">
          <div class="quick-chip" onclick="quickSearch('66')">66 Kerja Sama</div>
          <div class="quick-chip" onclick="quickSearch('11 DTPS')">11 DTPS</div>
          <div class="quick-chip" onclick="quickSearch('45 penelitian')">45 Penelitian</div>
          <div class="quick-chip" onclick="quickSearch('53 MK')">53 MK</div>
          <div class="quick-chip" onclick="quickSearch('tracer')">Tracer</div>
          <div class="quick-chip" onclick="quickSearch('CPL')">CPL</div>
          <div class="quick-chip" onclick="quickSearch('K3L')">K3L</div>
          <div class="quick-chip bab3" onclick="quickSearch('SWOT')">📘 SWOT</div>
          <div class="quick-chip bab3" onclick="quickSearch('program pengembangan')">📘 Program</div>
        </div>
      </div>
      <div id="searchResultContainer"></div>
      <div id="defaultModeAL">
        <h3 style="color:#0d47a1; margin:20px 0 12px 0;">🔥 Pertanyaan Risiko KRITIS</h3>
        <div id="kritisList"></div>
      </div>
    </div>

    <!-- ========== DATA KUNCI LKPS ========== -->
    <div class="al-panel" id="panel-data">
      <div class="lkps-hero">
        <h2>📊 ANGKA KUNCI LKPS — WAJIB KONSISTEN</h2>
        <div class="subtitle">Resume Data / Angka Penting LKPS PSBM — Sumber tunggal untuk Kaprodi/PIC saat AL</div>
        <div class="lkps-warning">🔴 Semua angka harus sama dengan LKPS final yang diunggah ke SAKTI</div>
      </div>

      <!-- Super Priority -->
      <div class="super-priority-box">
        <h3>⭐ ANGKA SUPER-PRIORITAS — WAJIB DIHAFAL</h3>
        <div class="sp-item">🤝 66 kerja sama → 42 Pendidikan | 17 Penelitian | 7 PkM</div>
        <div class="sp-item">📘 53 MK | 150 SKS | 80 SKS praktik = 53,33%</div>
        <div class="sp-item">👨🏫 11 DTPS | 3 Doktor | 4 Lektor Kepala | 6 Lektor</div>
        <div class="sp-item">🔬 45 penelitian → 14 | 13 | 18</div>
        <div class="sp-item">💰 36 internal | 9 eksternal nasional | 0 luar negeri</div>
        <div class="sp-item">🎓 12/45 penelitian melibatkan mahasiswa = 26,67%</div>
        <div class="sp-item"> 14 PkM → 2 | 6 | 6; 100% pendanaan internal/mandiri</div>
        <div class="sp-item">🎯 80 lulusan | 61 terlacak = 76,25%</div>
        <div class="sp-item">💼 43/61 kesesuaian kerja tinggi = 70,49%</div>
        <div class="sp-item"> 49/61 bekerja nasional/multinasional = 80,33%</div>
      </div>

      <!-- Critical Notes -->
      <div class="critical-notes-box">
        <h3>🔴 CATATAN KRITIS UNTUK AL</h3>
        <div class="cn-item"><strong>Kerja sama = 66</strong> (42 + 17 + 7). Angka ini berbeda dari 65 = 41 + 17 + 7 pada draft/narasi sebelumnya. Gunakan dan rekonsiliasikan terhadap LKPS final yang disubmit.</div>
        <div class="cn-item"><strong>Penelitian melibatkan mahasiswa = 12 dari 45 (26,67%)</strong>. Siapkan penjelasan evaluasi diri dan program peningkatan integrasi penelitian DTPS dengan mahasiswa.</div>
        <div class="cn-item"><strong>Kepuasan pengguna — Bahasa asing:</strong> tabel menunjukkan "Cukup" = 11,1%, sedangkan narasi RTL menyebut 25%. <strong>Inkonsistensi ini perlu direkonsiliasi sebelum AL.</strong></div>
      </div>

      <!-- Category Tabs -->
      <div class="lkps-cat-tabs" id="lkpsCatTabs">
        <div class="lkps-cat-btn active" onclick="filterLKPS('all', this)">Semua</div>
        <div class="lkps-cat-btn" onclick="filterLKPS('Kerja Sama', this)">🤝 Kerja Sama</div>
        <div class="lkps-cat-btn" onclick="filterLKPS('Pendidikan', this)">📘 Pendidikan</div>
        <div class="lkps-cat-btn" onclick="filterLKPS('SDM', this)">👨‍ SDM</div>
        <div class="lkps-cat-btn" onclick="filterLKPS('Penelitian', this)">🔬 Penelitian</div>
        <div class="lkps-cat-btn" onclick="filterLKPS('PkM', this)">🤝 PkM</div>
        <div class="lkps-cat-btn" onclick="filterLKPS('Luaran DTPS', this)">📤 Luaran DTPS</div>
        <div class="lkps-cat-btn" onclick="filterLKPS('Tracer', this)">🎯 Tracer</div>
        <div class="lkps-cat-btn" onclick="filterLKPS('Kepuasan Pengguna', this)">⭐ Kepuasan</div>
        <div class="lkps-cat-btn" onclick="filterLKPS('Prestasi Mhs', this)">🏆 Prestasi Mhs</div>
      </div>

      <div class="filter-bar">
        <input type="text" id="lkpsSearch" placeholder="🔎 Cari angka atau indikator..." oninput="renderLKPS()">
        <select id="filterWajib" onchange="renderLKPS()">
          <option value="">Semua</option>
          <option value="wajib">🔴 Wajib Konsisten</option>
        </select>
      </div>

      <div id="lkpsContent"></div>
    </div>

    <!-- ========== BANK PERTANYAAN ========== -->
    <div class="al-panel" id="panel-bank">
      <h2 style="color:#0d47a1; margin-top:0;">❓ Bank Pertanyaan AL PSBM — 243 Pertanyaan</h2>
      <p style="color:#666; font-size:0.9rem; margin-top:-4px;">183 pertanyaan C.1–C.7 + 60 pertanyaan BAB III. Klik pertanyaan untuk melihat detail.</p>

      <div class="stats-bar" id="statsBar"></div>
      <div class="sub-nav" id="bankSubNav"></div>

      <div class="filter-bar">
        <input type="text" id="bankSearch" placeholder="🔎 Cari pertanyaan, indikator, PIC..." oninput="renderBank()">
        <select id="filterRisk" onchange="renderBank()">
          <option value="">Semua Risiko</option>
          <option value="Kritis"> Kritis</option>
          <option value="Tinggi">🟠 Tinggi</option>
          <option value="Sedang"> Sedang</option>
          <option value="Rendah">🟢 Rendah</option>
        </select>
        <select id="filterPIC" onchange="renderBank()">
          <option value="">Semua PIC</option>
        </select>
      </div>

      <div id="bankContent"></div>
    </div>

  </div>
</div>

<script>
// ===== DATA KUNCI LKPS =====
const dataLKPS = [
  // Kerja Sama
  { nama: 'Kerja sama tridharma', value: '66', kategori: 'Kerja Sama', wajib: true, catatan: '🔴 Wajib konsisten. Berbeda dari draft lama (65). Rekonsiliasi dengan LKPS final.', pertanyaan: ['016','017','033','034'] },
  { nama: 'Kerja sama Pendidikan', value: '42', kategori: 'Kerja Sama', wajib: true, catatan: '5 internasional + 37 nasional', pertanyaan: ['016','018'] },
  { nama: 'Kerja sama Penelitian', value: '17', kategori: 'Kerja Sama', wajib: true, catatan: '1 internasional + 16 nasional', pertanyaan: ['016','020'] },
  { nama: 'Kerja sama PkM', value: '7', kategori: 'Kerja Sama', wajib: true, catatan: '1 nasional + 6 lokal/wilayah', pertanyaan: ['016'] },

  // Pendidikan
  { nama: 'Mata kuliah', value: '53 MK', kategori: 'Pendidikan', wajib: true, catatan: 'Seluruhnya memiliki RPS', pertanyaan: ['043','044'] },
  { nama: 'Total kurikulum', value: '150 SKS', kategori: 'Pendidikan', wajib: true, catatan: '—', pertanyaan: [] },
  { nama: 'Praktik/praktikum/lapangan', value: '80 SKS', kategori: 'Pendidikan', wajib: true, catatan: '53,33% dari total SKS', pertanyaan: ['052','053'] },
  { nama: 'Teori/kuliah', value: '68 SKS', kategori: 'Pendidikan', wajib: false, catatan: '—', pertanyaan: [] },
  { nama: 'Seminar', value: '2 SKS', kategori: 'Pendidikan', wajib: false, catatan: '—', pertanyaan: [] },
  { nama: 'MK kompetensi', value: '25 MK', kategori: 'Pendidikan', wajib: false, catatan: '—', pertanyaan: ['088'] },

  // SDM
  { nama: 'DTPS', value: '11 dosen', kategori: 'SDM', wajib: true, catatan: '🔴 Angka dasar SDM', pertanyaan: ['076','127','128'] },
  { nama: 'Doktor', value: '3 (27,27%)', kategori: 'SDM', wajib: true, catatan: 'Perlu pengembangan', pertanyaan: ['079','080'] },
  { nama: 'Lektor Kepala', value: '4 (36,36%)', kategori: 'SDM', wajib: true, catatan: '—', pertanyaan: ['082'] },
  { nama: 'Lektor', value: '6', kategori: 'SDM', wajib: false, catatan: '—', pertanyaan: ['082'] },
  { nama: 'BKD rata-rata', value: '14,77 SKS', kategori: 'SDM', wajib: false, catatan: '—', pertanyaan: ['094'] },

  // Penelitian
  { nama: 'Penelitian 3 tahun', value: '45', kategori: 'Penelitian', wajib: true, catatan: '14 → 13 → 18', pertanyaan: ['017','067','097'] },
  { nama: 'Penelitian internal/mandiri', value: '36 (80%)', kategori: 'Penelitian', wajib: true, catatan: ' Dominan internal', pertanyaan: ['018','029'] },
  { nama: 'Penelitian eksternal nasional', value: '9 (20%)', kategori: 'Penelitian', wajib: true, catatan: '—', pertanyaan: ['018'] },
  { nama: 'Penelitian luar negeri', value: '0', kategori: 'Penelitian', wajib: true, catatan: ' Titik pendalaman', pertanyaan: ['018','098'] },
  { nama: 'Penelitian melibatkan mahasiswa', value: '12/45 (26,67%)', kategori: 'Penelitian', wajib: true, catatan: '🔴 Perlu ditingkatkan', pertanyaan: ['020','067','068','069'] },

  // PkM
  { nama: 'PkM 3 tahun', value: '14', kategori: 'PkM', wajib: true, catatan: '2 → 6 → 6', pertanyaan: ['023','073'] },
  { nama: 'Pendanaan PkM internal/mandiri', value: '14/14 (100%)', kategori: 'PkM', wajib: true, catatan: ' Titik pendalaman', pertanyaan: ['022','032'] },
  { nama: 'PkM melibatkan mahasiswa', value: '7', kategori: 'PkM', wajib: false, catatan: '—', pertanyaan: ['074'] },

  // Luaran DTPS
  { nama: 'Produk/jasa DTPS diadopsi', value: '13', kategori: 'Luaran DTPS', wajib: true, catatan: 'Kekuatan luaran', pertanyaan: ['109','110'] },
  { nama: 'Publikasi DTPS', value: '220', kategori: 'Luaran DTPS', wajib: false, catatan: '3 tahun', pertanyaan: ['103'] },

  // Tracer
  { nama: 'Lulusan (basis tracer)', value: '80', kategori: 'Tracer', wajib: true, catatan: 'Basis tracer', pertanyaan: ['155'] },
  { nama: 'Lulusan terlacak', value: '61', kategori: 'Tracer', wajib: true, catatan: '76,25%', pertanyaan: ['155'] },
  { nama: 'Waktu tunggu <3 bulan', value: '34/61 (55,74%)', kategori: 'Tracer', wajib: false, catatan: '—', pertanyaan: ['157'] },
  { nama: 'Waktu tunggu 3–18 bulan', value: '27/61 (44,26%)', kategori: 'Tracer', wajib: false, catatan: '—', pertanyaan: ['157'] },
  { nama: 'Waktu tunggu >18 bulan', value: '0', kategori: 'Tracer', wajib: false, catatan: 'Kekuatan', pertanyaan: ['157'] },
  { nama: 'Kesesuaian kerja tinggi', value: '43/61 (70,49%)', kategori: 'Tracer', wajib: true, catatan: '—', pertanyaan: ['160'] },
  { nama: 'Kesesuaian kerja sedang', value: '11/61 (18,03%)', kategori: 'Tracer', wajib: false, catatan: '—', pertanyaan: ['160'] },
  { nama: 'Kesesuaian kerja rendah', value: '7/61 (11,48%)', kategori: 'Tracer', wajib: false, catatan: '—', pertanyaan: ['160'] },
  { nama: 'Kerja skala nasional', value: '39/61', kategori: 'Tracer', wajib: false, catatan: '—', pertanyaan: ['163'] },
  { nama: 'Multinasional/internasional', value: '10/61', kategori: 'Tracer', wajib: false, catatan: '—', pertanyaan: ['163'] },
  { nama: 'Nasional + multinasional', value: '49/61 (80,33%)', kategori: 'Tracer', wajib: true, catatan: 'Kekuatan', pertanyaan: ['163'] },

  // Kepuasan Pengguna
  { nama: 'Responden pengguna lulusan', value: '45', kategori: 'Kepuasan Pengguna', wajib: true, catatan: 'Jangan tertukar dengan 61 tracer', pertanyaan: ['166'] },
  { nama: 'Kepuasan TI – Sangat Baik', value: '82,2%', kategori: 'Kepuasan Pengguna', wajib: false, catatan: 'Tertinggi', pertanyaan: ['167'] },
  { nama: 'Etika – Sangat Baik', value: '80,0%', kategori: 'Kepuasan Pengguna', wajib: false, catatan: '—', pertanyaan: ['167'] },
  { nama: 'Komunikasi – Sangat Baik', value: '77,78%', kategori: 'Kepuasan Pengguna', wajib: false, catatan: '—', pertanyaan: ['167'] },
  { nama: 'Kerja sama tim – Sangat Baik', value: '75,6%', kategori: 'Kepuasan Pengguna', wajib: false, catatan: '—', pertanyaan: ['167'] },
  { nama: 'Keahlian bidang – Sangat Baik', value: '73,3%', kategori: 'Kepuasan Pengguna', wajib: false, catatan: '—', pertanyaan: ['167'] },
  { nama: 'Pengembangan diri – Sangat Baik', value: '73,3%', kategori: 'Kepuasan Pengguna', wajib: false, catatan: '—', pertanyaan: ['167'] },
  { nama: 'Bahasa asing – Sangat Baik', value: '71,1%', kategori: 'Kepuasan Pengguna', wajib: true, catatan: '️ Perlu penguatan. Tabel: "Cukup"=11,1% vs RTL=25% → INKONSISTEN', pertanyaan: ['167','168'] },

  // Prestasi Mahasiswa
  { nama: 'Prestasi akademik', value: '10', kategori: 'Prestasi Mhs', wajib: false, catatan: '2 internasional + 8 nasional', pertanyaan: ['136'] },
  { nama: 'Prestasi nonakademik', value: '9', kategori: 'Prestasi Mhs', wajib: false, catatan: '1 internasional + 5 nasional + 3 wilayah', pertanyaan: ['137'] },
  { nama: 'Publikasi/presentasi mahasiswa', value: '126', kategori: 'Prestasi Mhs', wajib: false, catatan: 'Termasuk 34 jurnal nasional terakreditasi', pertanyaan: ['148'] },
  { nama: 'Produk/jasa mahasiswa', value: '16', kategori: 'Prestasi Mhs', wajib: false, catatan: '—', pertanyaan: ['139'] }
];

// ===== 243 PERTANYAAN (183 C.1-C.7 + 60 BAB III) =====
const dataPertanyaan = [
  // C.1 (9)
  { no:'001', k:'C.1', ind:'1 Kekhasan VMTS', q:'Apa kekhasan VMTS JTE dan visi keilmuan PSBM dibanding program sejenis?', f:'Apa yang benar-benar membedakan PSBM, bukan sekadar penggunaan istilah Broadband Multimedia?', d:'Tabel 1', b:'VMTS PNJ/JTE/PSBM', p:'Kaprodi/Kajur', r:'Tinggi' },
  { no:'002', k:'C.1', ind:'1 Kekhasan VMTS', q:'Bagaimana linearitas visi PNJ → VMTS JTE → visi keilmuan PSBM?', f:'Tunjukkan keterkaitannya secara eksplisit.', d:'Tabel 1', b:'Matriks sinkronisasi VMTS', p:'Kaprodi', r:'Tinggi' },
  { no:'003', k:'C.1', ind:'1 Kekhasan VMTS', q:'Bagaimana visi keilmuan PSBM diterjemahkan ke kurikulum?', f:'MK apa yang paling merepresentasikan kekhasan tersebut?', d:'3.a.1', b:'NADK, struktur kurikulum', p:'Kaprodi/Kurikulum', r:'Tinggi' },
  { no:'004', k:'C.1', ind:'2 Mekanisme VMTS', q:'Bagaimana VMTS dan visi keilmuan disusun?', f:'Siapa pemangku kepentingan internal dan eksternal yang terlibat?', d:'—', b:'SK tim, undangan, daftar hadir, BA', p:'Kajur', r:'Sedang' },
  { no:'005', k:'C.1', ind:'2 Mekanisme VMTS', q:'Bagaimana kebutuhan masyarakat dan tantangan global dipertimbangkan?', f:'Masukan apa yang akhirnya masuk ke visi/strategi?', d:'—', b:'Notulen/workshop/FGD', p:'Kajur/Kaprodi', r:'Sedang' },
  { no:'006', k:'C.1', ind:'2 Mekanisme VMTS', q:'Apa bukti bahwa alumni, pengguna lulusan, dan pakar benar-benar terlibat?', f:'Apakah hanya hadir atau memberikan masukan?', d:'—', b:'Daftar hadir + masukan + tindak lanjut', p:'Kaprodi', r:'Tinggi' },
  { no:'007', k:'C.1', ind:'3 Pemahaman & Pencapaian VMTS', q:'Bagaimana VMTS disosialisasikan dan diukur tingkat pemahamannya?', f:'Berapa hasil pengukuran pemahaman stakeholder?', d:'Tabel 1', b:'Survei VMTS', p:'Kajur/GPM', r:'Tinggi' },
  { no:'008', k:'C.1', ind:'3 Pemahaman & Pencapaian VMTS', q:'Apa capaian konkret jangka pendek/menengah dari VMTS?', f:'Tunjukkan target versus realisasi.', d:'LKPS terkait', b:'Renstra, Renop, laporan capaian', p:'Kajur', r:'Tinggi' },
  { no:'009', k:'C.1', ind:'3 Pemahaman & Pencapaian VMTS', q:'Apa bukti VMTS berdampak dan berkelanjutan?', f:'Perubahan apa yang dapat dikaitkan langsung dengan VMTS?', d:'C.3/C.4/C.6', b:'Laporan kinerja', p:'Kajur/Kaprodi', r:'Tinggi' },
  // C.2 (24)
  { no:'010', k:'C.2', ind:'4 Tata Pamong', q:'Bagaimana struktur tata pamong JTE bekerja?', f:'Apakah kewenangan tiap organ benar-benar dijalankan?', d:'—', b:'Statuta, OTK, SK', p:'Kajur', r:'Sedang' },
  { no:'011', k:'C.2', ind:'4 Tata Pamong', q:'Bagaimana prinsip efektif, transparan, dan akuntabel diterapkan?', f:'Berikan satu contoh keputusan yang menunjukkan prinsip tersebut.', d:'—', b:'SOP, BA rapat, laporan', p:'Kajur', r:'Sedang' },
  { no:'012', k:'C.2', ind:'4 Tata Pamong', q:'Apa dampak tata kelola terhadap PSBM?', f:'Apa yang berubah akibat keputusan UPPS?', d:'—', b:'RTM/Rapat Jurusan', p:'Kajur/Kaprodi', r:'Tinggi' },
  { no:'013', k:'C.2', ind:'5 Komitmen Pimpinan', q:'Bagaimana pimpinan menunjukkan komitmen terhadap visi dan tujuan organisasi?', f:'Program dan anggaran apa yang membuktikannya?', d:'2.b', b:'Renstra/RKAT', p:'Kajur', r:'Sedang' },
  { no:'014', k:'C.2', ind:'5 Komitmen Pimpinan', q:'Bagaimana pengembangan sumber daya diprioritaskan?', f:'Berikan contoh pengembangan dosen, tendik, atau fasilitas PSBM.', d:'4.a/4.b/5.a', b:'RKAT, surat tugas', p:'Kajur', r:'Sedang' },
  { no:'015', k:'C.2', ind:'5 Kemampuan Manajerial', q:'Bagaimana pimpinan menangani konflik atau masalah strategis?', f:'Berikan contoh masalah → keputusan → hasil.', d:'—', b:'BA rapat/keputusan', p:'Kajur', r:'Sedang' },
  { no:'016', k:'C.2', ind:'6 Relevansi Kerja Sama', q:'Berapa kerja sama pendidikan, penelitian, dan PkM PSBM?', f:'Apakah angka tersebut sama dengan LKPS submitted?', d:'2.a', b:'Rekap kerja sama', p:'Kerja Sama/Kaprodi', r:'Kritis' },
  { no:'017', k:'C.2', ind:'6 Tingkat Kerja Sama', q:'Berapa kerja sama internasional, nasional, dan lokal?', f:'Mana yang benar-benar aktif dalam 3 tahun terakhir?', d:'2.a', b:'IA/laporan kegiatan', p:'Kerja Sama', r:'Tinggi' },
  { no:'018', k:'C.2', ind:'6 Relevansi Kerja Sama', q:'Bagaimana memastikan kerja sama relevan dengan visi PSBM?', f:'Pilih tiga kerja sama dan jelaskan relevansinya.', d:'2.a', b:'Matriks kerja sama–tridharma', p:'Kaprodi', r:'Tinggi' },
  { no:'019', k:'C.2', ind:'7 Pelaksanaan Kerja Sama', q:'Apa manfaat nyata kerja sama bagi pembelajaran?', f:'Tunjukkan contoh magang, praktisi, fasilitas, atau sertifikasi.', d:'2.a', b:'Laporan implementasi', p:'Kaprodi', r:'Tinggi' },
  { no:'020', k:'C.2', ind:'7 Pelaksanaan Kerja Sama', q:'Bagaimana kerja sama meningkatkan penelitian dan PkM?', f:'Mana luaran yang dihasilkan?', d:'2.a/3.b/3.c', b:'Laporan kerja sama', p:'P3M/Kaprodi', r:'Tinggi' },
  { no:'021', k:'C.2', ind:'7 Pelaksanaan Kerja Sama', q:'Bagaimana kepuasan mitra diukur?', f:'Apa hasil dan tindak lanjut surveinya?', d:'—', b:'Survei mitra', p:'Kerja Sama/GPM', r:'Kritis' },
  { no:'022', k:'C.2', ind:'8 Pengelolaan Keuangan', q:'Bagaimana prinsip transparansi dan kepatuhan diterapkan?', f:'Siapa yang mengaudit?', d:'—', b:'SOP keuangan, audit', p:'Kajur/Keuangan', r:'Sedang' },
  { no:'023', k:'C.2', ind:'8 Pengelolaan Keuangan', q:'Bagaimana efektivitas dan efisiensi penggunaan anggaran dievaluasi?', f:'Berikan contoh realokasi berdasarkan evaluasi.', d:'2.b', b:'RKAT/realisasi', p:'Kajur', r:'Sedang' },
  { no:'024', k:'C.2', ind:'8 Pengelolaan Keuangan', q:'Bagaimana risiko keuangan dikendalikan?', f:'Tunjukkan audit internal dan eksternal.', d:'—', b:'Laporan audit', p:'Kajur/Keuangan', r:'Sedang' },
  { no:'025', k:'C.2', ind:'9 BOP', q:'Berapa rata-rata BOP per mahasiswa per tahun?', f:'Bagaimana perhitungannya?', d:'2.b', b:'RKAT/realisasi', p:'Keuangan', r:'Tinggi' },
  { no:'026', k:'C.2', ind:'9 BOP', q:'Apakah BOP memadai untuk pembelajaran PSBM?', f:'Apa indikator kecukupannya?', d:'2.b/5.a', b:'Anggaran pembelajaran', p:'Kajur', r:'Sedang' },
  { no:'027', k:'C.2', ind:'9 BOP', q:'Bagaimana tren BOP tiga tahun terakhir?', f:'Mengapa naik/turun?', d:'2.b', b:'Rekap tiga tahun', p:'Keuangan', r:'Sedang' },
  { no:'028', k:'C.2', ind:'10 Dana Penelitian', q:'Berapa rata-rata dana penelitian DTPS/tahun?', f:'Sumber internal versus eksternalnya?', d:'2.b/3.b', b:'Kontrak penelitian', p:'P3M', r:'Tinggi' },
  { no:'029', k:'C.2', ind:'10 Dana Penelitian', q:'Mengapa pendanaan penelitian masih dominan internal?', f:'Apa strategi meningkatkan hibah eksternal?', d:'3.b', b:'Proposal/roadmap hibah', p:'P3M/Kaprodi', r:'Tinggi' },
  { no:'030', k:'C.2', ind:'10 Dana Penelitian', q:'Bagaimana dana penelitian mendukung visi PSBM?', f:'Tunjukkan penelitian prioritas.', d:'3.b', b:'Roadmap + kontrak', p:'P3M', r:'Sedang' },
  { no:'031', k:'C.2', ind:'11 Dana PkM', q:'Berapa rata-rata dana PkM DTPS/tahun?', f:'Bagaimana angka dihitung?', d:'2.b/3.c', b:'Kontrak PkM', p:'P3M', r:'Tinggi' },
  { no:'032', k:'C.2', ind:'11 Dana PkM', q:'Apa sumber pembiayaan PkM?', f:'Mengapa belum banyak eksternal?', d:'3.c', b:'Rekap sumber dana', p:'P3M', r:'Tinggi' },
  { no:'033', k:'C.2', ind:'11 Dana PkM', q:'Bagaimana kecukupan dana dinilai?', f:'Apa dampaknya terhadap skala PkM?', d:'2.b/3.c', b:'Evaluasi PkM', p:'P3M', r:'Sedang' },
  // C.3 (42)
  { no:'034', k:'C.3', ind:'12 Pemutakhiran Kurikulum', q:'Kapan Kurikulum PSBM terakhir dievaluasi?', f:'Mengapa evaluasi dilakukan pada 2020, 2021, dan 2024?', d:'3.a.1', b:'NADK, BA evaluasi', p:'Kurikulum', r:'Tinggi' },
  { no:'035', k:'C.3', ind:'12 Pemutakhiran Kurikulum', q:'Siapa stakeholder yang terlibat?', f:'Apa masukan industri dan pakar?', d:'—', b:'Daftar hadir/notulen', p:'Kurikulum', r:'Tinggi' },
  { no:'036', k:'C.3', ind:'12 Pemutakhiran Kurikulum', q:'Apa perubahan kurikulum akibat masukan stakeholder/IPTEKS?', f:'Tunjukkan sebelum–sesudahnya.', d:'3.a.1', b:'Dokumen evaluasi', p:'Kurikulum', r:'Kritis' },
  { no:'037', k:'C.3', ind:'13 Profil Lulusan', q:'Bagaimana profil lulusan ditetapkan?', f:'Bagaimana visi, kebutuhan pengguna, dan sumber daya dipertimbangkan?', d:'3.a.1', b:'NADK 2020', p:'Kurikulum', r:'Tinggi' },
  { no:'038', k:'C.3', ind:'13 Profil Lulusan', q:'Bagaimana profil lulusan mempertimbangkan kebutuhan global?', f:'Kompetensi apa yang membuktikannya?', d:'3.a.1', b:'PL–CPL', p:'Kurikulum', r:'Sedang' },
  { no:'039', k:'C.3', ind:'13 Profil Lulusan', q:'Bagaimana profil lulusan diturunkan menjadi CPL?', f:'Tunjukkan matriks Profil–CPL.', d:'3.a.1', b:'Matriks PL–CPL', p:'Kurikulum', r:'Tinggi' },
  { no:'040', k:'C.3', ind:'14 CPL', q:'Bagaimana CPL memenuhi empat standar kompetensi lulusan?', f:'Mana CPL untuk rekayasa, teknologi, komunikasi/tim, dan etika?', d:'3.a.1', b:'Rumusan CPL', p:'Kurikulum', r:'Tinggi' },
  { no:'041', k:'C.3', ind:'14 CPL', q:'Bagaimana CPL ditinjau rutin?', f:'Siapa stakeholder internal/eksternal yang terlibat?', d:'—', b:'Workshop OBE 2024', p:'Kurikulum', r:'Tinggi' },
  { no:'042', k:'C.3', ind:'14 CPL', q:'Bagaimana ketercapaian CPL diukur?', f:'Tunjukkan hasil ukur → evaluasi → tindak lanjut.', d:'3.a.1', b:'CPL–CPMK, rekap capaian', p:'Kurikulum/GPM', r:'Kritis' },
  { no:'043', k:'C.3', ind:'15 RPS', q:'Apakah seluruh mata kuliah mempunyai RPS?', f:'Tunjukkan beberapa RPS secara acak.', d:'3.a.1', b:'Repository RPS', p:'Kurikulum', r:'Kritis' },
  { no:'044', k:'C.3', ind:'15 RPS', q:'Apakah RPS memenuhi sembilan komponen matriks?', f:'Tunjukkan CPL, CPMK, bahan kajian, metode, waktu, tugas, penilaian, referensi.', d:'3.a.1', b:'Sampel RPS', p:'Kurikulum/Dosen', r:'Kritis' },
  { no:'045', k:'C.3', ind:'15 RPS', q:'Bagaimana RPS ditinjau rutin?', f:'Apa RPS yang berubah dan mengapa?', d:'—', b:'BA tinjauan RPS', p:'Kurikulum', r:'Kritis' },
  { no:'046', k:'C.3', ind:'16 Proses Pembelajaran', q:'Bagaimana pembelajaran memastikan pencapaian CPL?', f:'Berikan contoh metode pada satu MK.', d:'3.a.1', b:'RPS, LMS', p:'Dosen/Kurikulum', r:'Tinggi' },
  { no:'047', k:'C.3', ind:'16 Proses Pembelajaran', q:'Bagaimana interaksi dan kemampuan analisis kritis mahasiswa dikembangkan?', f:'Tunjukkan tugas/proyek yang relevan.', d:'3.a.1', b:'Tugas/rubrik', p:'Dosen', r:'Sedang' },
  { no:'048', k:'C.3', ind:'16 Proses Pembelajaran', q:'Bagaimana proses pembelajaran dimonitor?', f:'Tunjukkan temuan dan tindakan perbaikan.', d:'—', b:'Monitoring PBM', p:'GPM/Kurikulum', r:'Tinggi' },
  { no:'049', k:'C.3', ind:'17 Integrasi Penelitian/PkM', q:'Berapa MK inti yang mengintegrasikan penelitian/PkM?', f:'Apakah memenuhi minimal 10%?', d:'3.a.3', b:'RPS/bahan ajar', p:'Kurikulum', r:'Kritis' },
  { no:'050', k:'C.3', ind:'17 Integrasi Penelitian/PkM', q:'Penelitian apa yang masuk ke pembelajaran?', f:'Pada MK dan materi apa?', d:'3.a.3', b:'Matriks penelitian–MK', p:'Dosen', r:'Kritis' },
  { no:'051', k:'C.3', ind:'17 Integrasi Penelitian/PkM', q:'Apa bukti integrasi tersebut bukan sekadar daftar penelitian?', f:'Tunjukkan RPS/modul/tugas mahasiswa.', d:'3.a.3', b:'RPS/modul', p:'Kurikulum', r:'Kritis' },
  { no:'052', k:'C.3', ind:'18 Praktik', q:'Berapa persentase jam praktik/penugasan?', f:'Bagaimana PJP dihitung?', d:'3.a.1', b:'Kurikulum', p:'Kurikulum', r:'Sedang' },
  { no:'053', k:'C.3', ind:'18 Praktik', q:'Apakah proporsi praktik sesuai karakter vokasi PSBM?', f:'Berikan contoh MK dominan praktik.', d:'3.a.1', b:'RPS/jadwal', p:'Kurikulum', r:'Rendah' },
  { no:'054', k:'C.3', ind:'18 Praktik', q:'Bagaimana kualitas kegiatan praktik dievaluasi?', f:'Apa tindak lanjut hasil evaluasi?', d:'—', b:'Evaluasi praktikum', p:'Kalab/Kurikulum', r:'Sedang' },
  { no:'055', k:'C.3', ind:'19 Basic Sciences', q:'Berapa SKS Basic Sciences dan Matematika?', f:'MK apa saja?', d:'3.a.4', b:'Kurikulum/RPS', p:'Kurikulum', r:'Rendah' },
  { no:'056', k:'C.3', ind:'19 Basic Sciences', q:'Bagaimana Basic Sciences mendukung CPL Broadband Multimedia?', f:'Berikan contoh penerapannya.', d:'3.a.4', b:'Matriks CPL–MK', p:'Kurikulum', r:'Sedang' },
  { no:'057', k:'C.3', ind:'19 Basic Sciences', q:'Bagaimana kedalaman materi Basic Sciences ditentukan?', f:'Apakah sesuai kebutuhan rekayasa terapan?', d:'3.a.4', b:'RPS', p:'Dosen', r:'Sedang' },
  { no:'058', k:'C.3', ind:'20 Capstone', q:'Apa bentuk capstone project PSBM?', f:'Apakah mempunyai panduan formal?', d:'3.a.5', b:'Panduan TA/capstone', p:'Kaprodi', r:'Tinggi' },
  { no:'059', k:'C.3', ind:'20 Capstone', q:'Bagaimana standar keteknikan dan batasan realistis digunakan?', f:'Tunjukkan satu contoh proyek.', d:'3.a.5', b:'Proposal/laporan/rubrik', p:'Dosen TA', r:'Tinggi' },
  { no:'060', k:'C.3', ind:'20 Capstone', q:'Bagaimana CPL capstone diukur?', f:'Tunjukkan rubrik dan hasil asesmennya.', d:'3.a.5', b:'Rubrik penilaian', p:'Kurikulum', r:'Tinggi' },
  { no:'061', k:'C.3', ind:'21 Suasana Akademik', q:'Program apa yang membangun suasana akademik?', f:'Seberapa rutin dilaksanakan?', d:'—', b:'Kalender kegiatan', p:'Kaprodi', r:'Sedang' },
  { no:'062', k:'C.3', ind:'21 Suasana Akademik', q:'Bagaimana kebebasan akademik, mimbar akademik dan otonomi keilmuan diwujudkan?', f:'Berikan kegiatan 1–2 bulanan.', d:'—', b:'Laporan seminar/kuliah tamu', p:'Kaprodi', r:'Sedang' },
  { no:'063', k:'C.3', ind:'21 Suasana Akademik', q:'Bagaimana efektivitas suasana akademik dievaluasi?', f:'Apa perbaikan berdasarkan evaluasi?', d:'—', b:'Survei/evaluasi', p:'GPM', r:'Sedang' },
  { no:'064', k:'C.3', ind:'22 Penelitian', q:'Bagaimana roadmap penelitian mendukung VMTS dan visi PSBM?', f:'Tunjukkan hubungan tema dengan visi.', d:'3.b', b:'Roadmap penelitian', p:'P3M/Kaprodi', r:'Tinggi' },
  { no:'065', k:'C.3', ind:'22 Penelitian', q:'Bagaimana roadmap memayungi penelitian dosen dan mahasiswa?', f:'Petakan contoh penelitian ke roadmap.', d:'3.b/6.h.1', b:'Matriks roadmap', p:'P3M', r:'Tinggi' },
  { no:'066', k:'C.3', ind:'22 Penelitian', q:'Bagaimana roadmap dievaluasi dan menghasilkan dampak?', f:'Apa perubahan/dampak bagi masyarakat?', d:'3.b', b:'BA evaluasi, luaran', p:'P3M', r:'Tinggi' },
  { no:'067', k:'C.3', ind:'23 Penelitian–Mahasiswa', q:'Berapa penelitian DTPS tiga tahun terakhir?', f:'Berapa yang melibatkan mahasiswa?', d:'6.h.1', b:'Daftar penelitian', p:'P3M', r:'Kritis' },
  { no:'068', k:'C.3', ind:'23 Penelitian–Mahasiswa', q:'Bagaimana mahasiswa dilibatkan?', f:'Sebagai anggota, pengambil data, TA, atau penulis?', d:'6.h.1', b:'SK/tim/laporan', p:'Dosen/P3M', r:'Tinggi' },
  { no:'069', k:'C.3', ind:'23 Penelitian–Mahasiswa', q:'Apa strategi meningkatkan keterlibatan mahasiswa?', f:'Bagaimana integrasi dengan TA/proyek?', d:'6.h.1', b:'RTL penelitian', p:'Kaprodi', r:'Tinggi' },
  { no:'070', k:'C.3', ind:'24 PkM', q:'Bagaimana roadmap PkM mendukung VMTS/visi PSBM?', f:'Apa tema utama?', d:'3.c', b:'Roadmap PkM', p:'P3M', r:'Tinggi' },
  { no:'071', k:'C.3', ind:'24 PkM', q:'Bagaimana PkM dosen/mahasiswa dipetakan terhadap roadmap?', f:'Tunjukkan beberapa contoh.', d:'3.c/6.i', b:'Matriks roadmap–PkM', p:'P3M', r:'Tinggi' },
  { no:'072', k:'C.3', ind:'24 PkM', q:'Bagaimana dampak PkM kepada masyarakat dievaluasi?', f:'Apa perubahan nyata pada mitra?', d:'3.c', b:'Laporan/dampak', p:'P3M', r:'Tinggi' },
  { no:'073', k:'C.3', ind:'25 PkM–Mahasiswa', q:'Berapa PkM DTPS yang melibatkan mahasiswa?', f:'Apakah angka sama dengan LKPS?', d:'6.i', b:'Daftar PkM', p:'P3M', r:'Kritis' },
  { no:'074', k:'C.3', ind:'25 PkM–Mahasiswa', q:'Apa peran mahasiswa dalam PkM?', f:'Tunjukkan bukti keterlibatan individual.', d:'6.i', b:'SK, laporan, foto', p:'Dosen/P3M', r:'Tinggi' },
  { no:'075', k:'C.3', ind:'25 PkM–Mahasiswa', q:'Bagaimana PkM diintegrasikan dengan pembelajaran?', f:'MK/CPL apa yang didukung?', d:'3.a.3/6.i', b:'RPS/laporan', p:'Kurikulum/P3M', r:'Tinggi' },
  // C.4 (45)
  { no:'076', k:'C.4', ind:'26 Kecukupan DTPS', q:'Berapa jumlah DTPS PSBM?', f:'Mengapa dosen tersebut dikategorikan sesuai kompetensi inti?', d:'4.a', b:'CV/SK dosen', p:'Kaprodi', r:'Tinggi' },
  { no:'077', k:'C.4', ind:'26 Kecukupan DTPS', q:'Bagaimana kecukupan DTPS dibanding beban mahasiswa/MK?', f:'Apakah ada DTT?', d:'4.a/6.a', b:'Jadwal mengajar', p:'Kaprodi', r:'Sedang' },
  { no:'078', k:'C.4', ind:'26 Kecukupan DTPS', q:'Apakah dosen MK umum/MKWU dipisahkan dari DTPS inti?', f:'Tunjukkan pemetaannya.', d:'4.a', b:'Matriks dosen–MK', p:'Kaprodi', r:'Tinggi' },
  { no:'079', k:'C.4', ind:'27 Kualifikasi', q:'Berapa DTPS bergelar doktor?', f:'Apakah bidang doktornya relevan?', d:'4.a', b:'Ijazah/CV', p:'Kaprodi', r:'Sedang' },
  { no:'080', k:'C.4', ind:'27 Kualifikasi', q:'Bagaimana rencana peningkatan dosen doktor?', f:'Siapa yang sedang studi lanjut?', d:'4.a', b:'Roadmap SDM', p:'Kajur', r:'Sedang' },
  { no:'081', k:'C.4', ind:'27 Kualifikasi', q:'Bagaimana kualifikasi akademik mendukung bidang PSBM?', f:'Petakan dosen dengan bidang keahlian.', d:'4.a', b:'CV/matriks kepakaran', p:'Kaprodi', r:'Sedang' },
  { no:'082', k:'C.4', ind:'28 Jabatan Akademik', q:'Berapa DTPS Lektor/Lektor Kepala/GB?', f:'Cocokkan dengan 4.a.', d:'4.a', b:'SK Jafa', p:'Kaprodi', r:'Sedang' },
  { no:'083', k:'C.4', ind:'28 Jabatan Akademik', q:'Apa strategi peningkatan jabatan akademik?', f:'Siapa target berikutnya?', d:'4.a', b:'Roadmap Jafa', p:'Kajur', r:'Sedang' },
  { no:'084', k:'C.4', ind:'28 Jabatan Akademik', q:'Bagaimana jabatan akademik berdampak pada mutu PSBM?', f:'Berikan contoh kepemimpinan akademik.', d:'—', b:'SK/luaran', p:'Kajur', r:'Sedang' },
  { no:'085', k:'C.4', ind:'29 Sertifikasi', q:'Berapa DTPS bersertifikat kompetensi/profesi/industri?', f:'Sertifikasi apa dan masih berlaku?', d:'4.a', b:'Sertifikat', p:'Kaprodi', r:'Sedang' },
  { no:'086', k:'C.4', ind:'29 Sertifikasi', q:'Apakah sertifikasi relevan dengan MK yang diampu?', f:'Berikan pemetaan.', d:'4.a', b:'Matriks sertifikasi–MK', p:'Kaprodi', r:'Sedang' },
  { no:'087', k:'C.4', ind:'29 Sertifikasi', q:'Bagaimana rencana pembaruan sertifikasi?', f:'Apa dukungan anggaran?', d:'—', b:'Program pengembangan', p:'Kajur', r:'Rendah' },
  { no:'088', k:'C.4', ind:'30 Praktisi', q:'Berapa MK kompetensi diampu praktisi?', f:'Berapa persentasenya?', d:'4.a', b:'SK/jadwal', p:'Kaprodi', r:'Tinggi' },
  { no:'089', k:'C.4', ind:'30 Praktisi', q:'Bagaimana praktisi dipilih?', f:'Apa kompetensi industri yang dibawa?', d:'4.a', b:'CV praktisi', p:'Kaprodi', r:'Sedang' },
  { no:'090', k:'C.4', ind:'30 Praktisi', q:'Apa dampak keterlibatan praktisi terhadap pembelajaran?', f:'Bagaimana dievaluasi mahasiswa?', d:'—', b:'EDOM/survei', p:'Kurikulum', r:'Sedang' },
  { no:'091', k:'C.4', ind:'31 Tendik', q:'Berapa laboran/teknisi yang melayani PSBM?', f:'Cukupkah dibanding jumlah lab?', d:'4.b', b:'Daftar tendik', p:'Kajur/Kalab', r:'Tinggi' },
  { no:'092', k:'C.4', ind:'31 Tendik', q:'Apakah kualifikasi laboran sesuai laboratorium?', f:'Tunjukkan penugasannya.', d:'4.b', b:'Ijazah/SK', p:'Kalab', r:'Sedang' },
  { no:'093', k:'C.4', ind:'31 Tendik', q:'Berapa yang memiliki sertifikat kompetensi?', f:'Bagaimana rencana peningkatannya?', d:'4.b', b:'Sertifikat', p:'Kajur', r:'Tinggi' },
  { no:'094', k:'C.4', ind:'32 Beban Kerja', q:'Berapa RBK DTPS?', f:'Apakah berada pada rentang ideal?', d:'4.c', b:'BKD', p:'Kaprodi', r:'Sedang' },
  { no:'095', k:'C.4', ind:'32 Beban Kerja', q:'Apakah ada dosen dengan beban berlebih?', f:'Bagaimana pengendaliannya?', d:'4.c', b:'BKD/jadwal', p:'Kajur', r:'Sedang' },
  { no:'096', k:'C.4', ind:'32 Beban Kerja', q:'Bagaimana beban penelitian/PkM diseimbangkan dengan pengajaran?', f:'Berikan contoh.', d:'4.c', b:'BKD', p:'Kajur', r:'Sedang' },
  { no:'097', k:'C.4', ind:'33 Penelitian DTPS', q:'Berapa penelitian berdasarkan sumber dana?', f:'Internal, nasional, internasional?', d:'3.b', b:'Kontrak penelitian', p:'P3M', r:'Tinggi' },
  { no:'098', k:'C.4', ind:'33 Penelitian DTPS', q:'Mengapa pendanaan eksternal/internasional masih terbatas?', f:'Apa strategi konkret?', d:'3.b', b:'Proposal/roadmap', p:'P3M', r:'Tinggi' },
  { no:'099', k:'C.4', ind:'33 Penelitian DTPS', q:'Bagaimana penelitian tersebut mendukung visi PSBM?', f:'Pilih lima contoh.', d:'3.b', b:'Roadmap', p:'P3M', r:'Sedang' },
  { no:'100', k:'C.4', ind:'34 PkM DTPS', q:'Berapa PkM berdasarkan sumber pendanaan?', f:'Berapa eksternal?', d:'3.c', b:'Kontrak', p:'P3M', r:'Tinggi' },
  { no:'101', k:'C.4', ind:'34 PkM DTPS', q:'Bagaimana PkM mendukung visi PSBM?', f:'Tunjukkan tema dan mitranya.', d:'3.c', b:'Roadmap/laporan', p:'P3M', r:'Sedang' },
  { no:'102', k:'C.4', ind:'34 PkM DTPS', q:'Apa strategi meningkatkan pendanaan PkM eksternal?', f:'Target dan mitra potensial?', d:'3.c', b:'RTL', p:'P3M', r:'Tinggi' },
  { no:'103', k:'C.4', ind:'35 Publikasi DTPS', q:'Berapa publikasi/presentasi DTPS tiga tahun terakhir?', f:'Internasional/nasional/lokal?', d:'4.e', b:'Artikel/prosiding', p:'P3M', r:'Tinggi' },
  { no:'104', k:'C.4', ind:'35 Publikasi DTPS', q:'Apakah publikasi relevan dengan visi keilmuan?', f:'Pilih contoh publikasi utama.', d:'4.e', b:'Artikel', p:'Kaprodi', r:'Sedang' },
  { no:'105', k:'C.4', ind:'35 Publikasi DTPS', q:'Bagaimana kualitas publikasi ditingkatkan?', f:'Apa target jurnal bereputasi?', d:'4.e', b:'Program publikasi', p:'P3M', r:'Sedang' },
  { no:'106', k:'C.4', ind:'36 Luaran DTPS', q:'Berapa paten, HKI, TTG, produk, buku dan book chapter?', f:'Cocokkan satu per satu dengan LKPS.', d:'4.f', b:'Sertifikat/produk', p:'P3M', r:'Tinggi' },
  { no:'107', k:'C.4', ind:'36 Luaran DTPS', q:'Mana luaran yang mendukung visi PSBM?', f:'Jelaskan hubungan substansinya.', d:'4.f', b:'Luaran', p:'Kaprodi', r:'Sedang' },
  { no:'108', k:'C.4', ind:'36 Luaran DTPS', q:'Bagaimana strategi meningkatkan luaran bernilai tinggi?', f:'Dari HKI menuju paten/produk?', d:'4.f', b:'Roadmap hilirisasi', p:'P3M', r:'Tinggi' },
  { no:'109', k:'C.4', ind:'37 Produk Diadopsi', q:'Berapa produk/jasa DTPS yang diadopsi masyarakat/industri?', f:'Siapa pengguna dan bagaimana membuktikannya?', d:'4.g', b:'BA adopsi/testimoni', p:'P3M', r:'Kritis' },
  { no:'110', k:'C.4', ind:'37 Produk Diadopsi', q:'Apa arti "diadopsi" pada produk yang diklaim?', f:'Apakah benar digunakan, bukan hanya didemonstrasikan?', d:'4.g', b:'Bukti penggunaan', p:'P3M', r:'Kritis' },
  { no:'111', k:'C.4', ind:'37 Produk Diadopsi', q:'Bagaimana meningkatkan hilirisasi hasil penelitian?', f:'Apa target berikutnya?', d:'4.g', b:'RTL hilirisasi', p:'P3M', r:'Tinggi' },
  { no:'112', k:'C.4', ind:'38 Penulis Utama', q:'Berapa DTPS menjadi penulis pertama/korespondensi?', f:'Mana publikasinya?', d:'4.h', b:'Artikel', p:'P3M', r:'Tinggi' },
  { no:'113', k:'C.4', ind:'38 Penulis Utama', q:'Bagaimana validasi status penulis dilakukan?', f:'Cocokkan metadata artikel.', d:'4.h', b:'DOI/artikel', p:'P3M', r:'Sedang' },
  { no:'114', k:'C.4', ind:'38 Penulis Utama', q:'Bagaimana budaya kepemimpinan publikasi dikembangkan?', f:'Apa program pendukungnya?', d:'—', b:'Program penelitian', p:'P3M', r:'Sedang' },
  { no:'115', k:'C.4', ind:'39 Sitasi', q:'Berapa karya bereputasi DTPS yang disitasi?', f:'Apakah terdapat duplikasi pencatatan?', d:'4.i', b:'Scopus/Google Scholar', p:'P3M', r:'Tinggi' },
  { no:'116', k:'C.4', ind:'39 Sitasi', q:'Bagaimana sitasi diverifikasi?', f:'Tunjukkan sumber dan tanggal pengambilan data.', d:'4.i', b:'Profil indeksasi', p:'P3M', r:'Tinggi' },
  { no:'117', k:'C.4', ind:'39 Sitasi', q:'Bagaimana strategi meningkatkan dampak ilmiah?', f:'Apa target publikasi/sitasi?', d:'4.i', b:'Roadmap publikasi', p:'P3M', r:'Sedang' },
  { no:'118', k:'C.4', ind:'40 Rekognisi', q:'Berapa DTPS mempunyai rekognisi kepakaran?', f:'Bentuk rekognisinya apa?', d:'4.j', b:'SK/sertifikat', p:'Kaprodi', r:'Kritis' },
  { no:'119', k:'C.4', ind:'40 Rekognisi', q:'Mengapa rekognisi yang diklaim memenuhi definisi matriks?', f:'Tunjukkan bukti eksternal.', d:'4.j', b:'Undangan/SK', p:'Kaprodi', r:'Kritis' },
  { no:'120', k:'C.4', ind:'40 Rekognisi', q:'Apa strategi meningkatkan rekognisi DTPS?', f:'Siapa yang ditargetkan dan bentuk rekognisinya?', d:'4.j', b:'Roadmap SDM', p:'Kajur', r:'Tinggi' },
  // C.5 (6)
  { no:'121', k:'C.5', ind:'41 Sarpras Akademik', q:'Apakah sarpras cukup untuk mendukung CPL PSBM?', f:'Tunjukkan lab utama dan alat penciri PSBM.', d:'5.a', b:'Inventaris/lab', p:'Kajur/Kalab', r:'Tinggi' },
  { no:'122', k:'C.5', ind:'41 Sarpras', q:'Bagaimana kelayakan, pemeliharaan dan akses sarpras dijamin?', f:'Bagaimana dengan alat tidak terawat?', d:'5.a', b:'Logbook/pemeliharaan', p:'Kalab', r:'Tinggi' },
  { no:'123', k:'C.5', ind:'41 Sarpras Nonakademik', q:'Apa fasilitas kesehatan, konseling, karier dan ibadah yang tersedia?', f:'Bagaimana akses mahasiswa?', d:'5.a', b:'Dokumentasi/SOP', p:'Kajur', r:'Rendah' },
  { no:'124', k:'C.5', ind:'42 K3L', q:'Apa kebijakan dan tata kelola K3L di JTE?', f:'Siapa penanggung jawabnya?', d:'5.b', b:'Kebijakan/SOP K3L', p:'Kajur/Kalab', r:'Tinggi' },
  { no:'125', k:'C.5', ind:'42 K3L', q:'Apa fasilitas K3L yang tersedia di laboratorium?', f:'Tunjukkan APAR, jalur evakuasi, APD, dll.', d:'5.c', b:'Inventaris/foto', p:'Kalab', r:'Tinggi' },
  { no:'126', k:'C.5', ind:'42 K3L', q:'Bagaimana K3L dilaksanakan dan ditinjau berkala?', f:'Kapan simulasi/audit terakhir dan apa tindak lanjutnya?', d:'5.b/5.c', b:'Laporan K3L', p:'Kajur/Kalab', r:'Tinggi' },
  // C.6 (42)
  { no:'127', k:'C.6', ind:'43 Rasio Mhs/DTPS', q:'Berapa mahasiswa aktif dan DTPS pada TS?', f:'Berapa RMD?', d:'6.a/4.a', b:'PDDikti/LKPS', p:'Kaprodi', r:'Kritis' },
  { no:'128', k:'C.6', ind:'43 Rasio Mhs/DTPS', q:'Apakah jumlah mahasiswa konsisten antara LED, LKPS dan PDDikti?', f:'Jelaskan jika ada selisih.', d:'6.a', b:'PDDikti', p:'Kaprodi', r:'Kritis' },
  { no:'129', k:'C.6', ind:'43 Rasio Mhs/DTPS', q:'Bagaimana rasio tersebut memengaruhi mutu pembelajaran?', f:'Bagaimana kapasitas kelas/lab?', d:'6.a/5.a', b:'Jadwal/lab', p:'Kaprodi', r:'Sedang' },
  { no:'130', k:'C.6', ind:'44 Mahasiswa Asing', q:'Berapa mahasiswa asing PSBM?', f:'Negara asal/statusnya?', d:'6.a', b:'PDDikti/dokumen mahasiswa', p:'Kemahasiswaan', r:'Tinggi' },
  { no:'131', k:'C.6', ind:'44 Mahasiswa Asing', q:'Apa strategi internasionalisasi mahasiswa?', f:'Bagaimana jika PMA masih rendah/nol?', d:'6.a', b:'Program internasional', p:'Kajur', r:'Tinggi' },
  { no:'132', k:'C.6', ind:'44 Mahasiswa Asing', q:'Apakah inbound/mobility dapat dibuktikan?', f:'Jangan samakan peserta kegiatan dengan mahasiswa asing reguler.', d:'6.a', b:'Dokumen resmi', p:'Kemahasiswaan', r:'Tinggi' },
  { no:'133', k:'C.6', ind:'45 IPK', q:'Berapa rata-rata IPK tiga tahun terakhir?', f:'Bagaimana trennya?', d:'6.b', b:'Yudisium/SIAKAD', p:'Kaprodi', r:'Rendah' },
  { no:'134', k:'C.6', ind:'45 IPK', q:'Bagaimana mutu penilaian dijaga sehingga IPK bermakna?', f:'Bagaimana moderasi/evaluasi nilai?', d:'6.b', b:'Pedoman penilaian', p:'Kurikulum', r:'Sedang' },
  { no:'135', k:'C.6', ind:'45 IPK', q:'Apakah peningkatan IPK diikuti peningkatan CPL?', f:'Tunjukkan korelasinya secara institusional.', d:'6.b/rekap CPL', b:'Rekap CPL', p:'Kurikulum', r:'Sedang' },
  { no:'136', k:'C.6', ind:'46 Prestasi Akademik', q:'Berapa prestasi akademik internasional/nasional/lokal?', f:'Cocokkan dengan 6.c.1.', d:'6.c.1', b:'Sertifikat', p:'Kemahasiswaan', r:'Tinggi' },
  { no:'137', k:'C.6', ind:'46 Prestasi Nonakademik', q:'Berapa prestasi nonakademik?', f:'Tingkat kompetisinya?', d:'6.c.2', b:'Sertifikat', p:'Kemahasiswaan', r:'Tinggi' },
  { no:'138', k:'C.6', ind:'46 Prestasi', q:'Bagaimana PSBM meningkatkan prestasi mahasiswa?', f:'Apa program pembinaan dan hasilnya?', d:'6.c', b:'Program pembinaan', p:'Kaprodi', r:'Tinggi' },
  { no:'139', k:'C.6', ind:'47 Produk Mahasiswa', q:'Berapa produk/jasa mahasiswa yang diadopsi?', f:'Mana bukti adopsinya?', d:'6.e.4', b:'BA/testimoni', p:'Kaprodi', r:'Kritis' },
  { no:'140', k:'C.6', ind:'47 Produk Mahasiswa', q:'Produk apa yang paling berdampak?', f:'Siapa pengguna dan sejak kapan?', d:'6.e.4', b:'Dokumentasi penggunaan', p:'Kaprodi', r:'Tinggi' },
  { no:'141', k:'C.6', ind:'47 Produk Mahasiswa', q:'Bagaimana proyek mahasiswa diarahkan menuju adopsi?', f:'Apa mekanisme hilirisasinya?', d:'6.e.4', b:'Inkubasi/kerja sama', p:'Kaprodi', r:'Tinggi' },
  { no:'142', k:'C.6', ind:'48 Masa Studi', q:'Berapa rata-rata masa studi?', f:'Mengapa demikian?', d:'6.d', b:'Data kelulusan', p:'Kaprodi', r:'Sedang' },
  { no:'143', k:'C.6', ind:'48 Masa Studi', q:'Apa penyebab mahasiswa terlambat?', f:'Bagaimana intervensinya?', d:'6.d', b:'Monitoring akademik', p:'PA/Kaprodi', r:'Sedang' },
  { no:'144', k:'C.6', ind:'48 Masa Studi', q:'Bagaimana efektivitas intervensi dievaluasi?', f:'Apakah masa studi membaik?', d:'6.d', b:'Tren tiga tahun', p:'Kaprodi', r:'Sedang' },
  { no:'145', k:'C.6', ind:'49 Kelulusan Tepat Waktu', q:'Berapa persentase kelulusan tepat waktu?', f:'Tunjukkan perhitungan cohort.', d:'6.d', b:'Data akademik', p:'Kaprodi', r:'Tinggi' },
  { no:'146', k:'C.6', ind:'49 Kelulusan Tepat Waktu', q:'Apa faktor mahasiswa tidak tepat waktu?', f:'TA, akademik, finansial, lainnya?', d:'6.d', b:'Evaluasi', p:'Kaprodi', r:'Sedang' },
  { no:'147', k:'C.6', ind:'49 Kelulusan Tepat Waktu', q:'Apa tindakan untuk meningkatkan PTW?', f:'Apa hasil setelah tindakan?', d:'6.d', b:'RTL', p:'Kaprodi', r:'Sedang' },
  { no:'148', k:'C.6', ind:'50 Publikasi Mahasiswa', q:'Berapa publikasi/presentasi mahasiswa?', f:'Internasional/nasional/lokal?', d:'6.e.2', b:'Artikel/sertifikat', p:'Kaprodi/P3M', r:'Tinggi' },
  { no:'149', k:'C.6', ind:'50 Publikasi Mahasiswa', q:'Mana yang dihasilkan bersama DTPS?', f:'Apa kontribusi mahasiswa?', d:'6.e.2', b:'Artikel', p:'Dosen', r:'Sedang' },
  { no:'150', k:'C.6', ind:'50 Publikasi Mahasiswa', q:'Bagaimana mahasiswa dibina menghasilkan publikasi?', f:'Apakah terintegrasi dengan TA?', d:'6.e.2', b:'Pedoman/program', p:'Kaprodi', r:'Sedang' },
  { no:'151', k:'C.6', ind:'51 Luaran Mahasiswa', q:'Berapa paten, HKI, TTG, produk dan buku mahasiswa?', f:'Cocokkan dengan 6.e.3.', d:'6.e.3', b:'Sertifikat HKI', p:'Kaprodi/P3M', r:'Tinggi' },
  { no:'152', k:'C.6', ind:'51 Luaran Mahasiswa', q:'Bagaimana luaran tersebut mendukung visi PSBM?', f:'Berikan contoh terkuat.', d:'6.e.3', b:'Produk/HKI', p:'Kaprodi', r:'Sedang' },
  { no:'153', k:'C.6', ind:'51 Luaran Mahasiswa', q:'Bagaimana strategi meningkatkan paten/TTG?', f:'Apa pipeline TA → HKI → produk?', d:'6.e.3', b:'Program hilirisasi', p:'Kaprodi', r:'Tinggi' },
  { no:'154', k:'C.6', ind:'52 Tracer Study', q:'Bagaimana tracer study dilaksanakan?', f:'Apakah terkoordinasi PT dan rutin tahunan?', d:'6.f', b:'Instrumen/laporan tracer', p:'CDC/Kaprodi', r:'Tinggi' },
  { no:'155', k:'C.6', ind:'52 Tracer Study', q:'Berapa populasi dan responden tracer?', f:'Apakah memenuhi cakupan yang dipersyaratkan?', d:'6.f.1/6.f.2', b:'Raw data tracer', p:'CDC', r:'Tinggi' },
  { no:'156', k:'C.6', ind:'52 Tracer Study', q:'Bagaimana hasil tracer digunakan memperbaiki kurikulum?', f:'Tunjukkan satu perubahan konkret.', d:'6.f', b:'BA kurikulum', p:'Kurikulum', r:'Kritis' },
  { no:'157', k:'C.6', ind:'53 Waktu Tunggu', q:'Berapa rata-rata waktu tunggu lulusan?', f:'Bagaimana dihitung?', d:'6.f.1', b:'Raw tracer', p:'CDC', r:'Tinggi' },
  { no:'158', k:'C.6', ind:'53 Waktu Tunggu', q:'Apa penyebab lulusan dengan waktu tunggu panjang?', f:'Sudah dianalisis?', d:'6.f.1', b:'Analisis tracer', p:'CDC/Kaprodi', r:'Sedang' },
  { no:'159', k:'C.6', ind:'53 Waktu Tunggu', q:'Apa tindakan PSBM untuk memperpendek waktu tunggu?', f:'Bagaimana dampaknya?', d:'6.f.1', b:'Career program', p:'Kaprodi', r:'Sedang' },
  { no:'160', k:'C.6', ind:'54 Kesesuaian Bidang', q:'Berapa lulusan bekerja sesuai bidang?', f:'Tinggi/sedang/rendah berapa?', d:'6.f.2', b:'Raw tracer', p:'CDC', r:'Kritis' },
  { no:'161', k:'C.6', ind:'54 Kesesuaian Bidang', q:'Bagaimana definisi tingkat kesesuaian ditetapkan?', f:'Siapa yang mengklasifikasikan?', d:'6.f.2', b:'Instrumen/metode', p:'CDC', r:'Tinggi' },
  { no:'162', k:'C.6', ind:'54 Kesesuaian Bidang', q:'Bagaimana ketidaksesuaian bidang kerja ditindaklanjuti?', f:'Apakah otomatis dianggap masalah kurikulum?', d:'6.f.2', b:'Analisis tracer', p:'Kurikulum', r:'Tinggi' },
  { no:'163', k:'C.6', ind:'55 Tempat Kerja', q:'Berapa lulusan bekerja di tingkat internasional/nasional/lokal?', f:'Cocokkan dengan 6.g.1.', d:'6.g.1', b:'Raw tracer', p:'CDC', r:'Kritis' },
  { no:'164', k:'C.6', ind:'55 Tempat Kerja', q:'Bagaimana kategori perusahaan ditentukan?', f:'Apa bukti perusahaan multinasional/nasional?', d:'6.g.1', b:'Data perusahaan', p:'CDC', r:'Tinggi' },
  { no:'165', k:'C.6', ind:'55 Tempat Kerja', q:'Bagaimana PSBM meningkatkan lulusan pada perusahaan nasional/internasional?', f:'Program apa yang dilakukan?', d:'6.g.1', b:'Career/sertifikasi', p:'Kaprodi', r:'Tinggi' },
  { no:'166', k:'C.6', ind:'56 Kepuasan Pengguna', q:'Bagaimana survei pengguna lulusan dilakukan?', f:'Berapa response rate?', d:'6.g.2', b:'Raw survey', p:'CDC/GPM', r:'Kritis' },
  { no:'167', k:'C.6', ind:'56 Kepuasan Pengguna', q:'Bagaimana hasil tujuh aspek kepuasan pengguna?', f:'Aspek mana terendah?', d:'6.g.2', b:'Rekap survei', p:'GPM', r:'Tinggi' },
  { no:'168', k:'C.6', ind:'56 Kepuasan Pengguna', q:'Apa tindak lanjut dari aspek kepuasan yang rendah?', f:'Tunjukkan perubahan pembelajaran/kurikulum.', d:'6.g.2', b:'BA/RTL', p:'Kurikulum/GPM', r:'Kritis' },
  // C.7 (15)
  { no:'169', k:'C.7', ind:'57 Unit Penjaminan Mutu', q:'Bagaimana struktur penjaminan mutu di JTE?', f:'Apa dasar legal GPM?', d:'7.a', b:'SK GPM', p:'GPM/Kajur', r:'Tinggi' },
  { no:'170', k:'C.7', ind:'57 Unit Penjaminan Mutu', q:'Bagaimana independensi auditor AMI dijamin?', f:'Apakah auditor mengaudit unitnya sendiri?', d:'7.a', b:'SK auditor', p:'GPM', r:'Tinggi' },
  { no:'171', k:'C.7', ind:'57 Unit Penjaminan Mutu', q:'Apa perangkat SPMI yang tersedia?', f:'Tunjukkan kebijakan, PPEPP, standar dan dokumentasi.', d:'7.a', b:'Dokumen SPMI', p:'GPM', r:'Tinggi' },
  { no:'172', k:'C.7', ind:'58 IKT', q:'Apa IKT JTE/PSBM di luar IKU?', f:'Bagaimana IKT terkait tujuan strategis?', d:'—', b:'Dokumen IKT', p:'Kajur/GPM', r:'Tinggi' },
  { no:'173', k:'C.7', ind:'58 IKT', q:'Mana IKT yang menunjukkan daya saing internasional?', f:'Berapa target dan capaiannya?', d:'—', b:'Matriks IKT', p:'Kajur', r:'Tinggi' },
  { no:'174', k:'C.7', ind:'58 IKT', q:'Bagaimana hasil IKT dianalisis untuk perbaikan?', f:'Berikan contoh IKT → keputusan.', d:'—', b:'Evaluasi IKT', p:'GPM', r:'Tinggi' },
  { no:'175', k:'C.7', ind:'59 PPEPP', q:'Bagaimana siklus PPEPP dilaksanakan di PSBM?', f:'Berikan satu contoh lengkap P→P→E→P→P.', d:'7.b', b:'SPMI/AMI/RTM/RTL', p:'GPM', r:'Kritis' },
  { no:'176', k:'C.7', ind:'59 PPEPP', q:'Apa bukti efektivitas penjaminan mutu?', f:'Jangan hanya menunjukkan dokumen AMI. Apa yang berubah?', d:'7.b', b:'AMI + RTL + hasil', p:'GPM/Kaprodi', r:'Kritis' },
  { no:'177', k:'C.7', ind:'59 PPEPP', q:'Mana bukti peningkatan standar?', f:'Standar apa yang dinaikkan setelah evaluasi?', d:'7.b', b:'Standar lama/baru', p:'GPM', r:'Kritis' },
  { no:'178', k:'C.7', ind:'60 Evaluasi Kinerja', q:'Bagaimana IKU/IKT diukur?', f:'Apa metode dan sumber datanya?', d:'7.a/7.b', b:'Laporan kinerja', p:'GPM', r:'Tinggi' },
  { no:'179', k:'C.7', ind:'60 Evaluasi Kinerja', q:'Bagaimana indikator yang tidak tercapai dianalisis?', f:'Apa akar masalah dan tindak lanjutnya?', d:'7.b', b:'Analisis/RTM', p:'GPM/Kajur', r:'Tinggi' },
  { no:'180', k:'C.7', ind:'60 Evaluasi Kinerja', q:'Bagaimana hasil pengukuran disebarluaskan kepada stakeholder?', f:'Tunjukkan bukti publikasi/diseminasi.', d:'—', b:'Website/rapat/laporan', p:'GPM', r:'Tinggi' },
  { no:'181', k:'C.7', ind:'61 Kepuasan Stakeholder', q:'Siapa saja stakeholder yang disurvei?', f:'Apakah mencakup mahasiswa, dosen, tendik, lulusan, pengguna, industri, dan mitra lain?', d:'—', b:'Instrumen survei', p:'GPM', r:'Kritis' },
  { no:'182', k:'C.7', ind:'61 Kepuasan Stakeholder', q:'Bagaimana validitas, periodisitas dan analisis survei kepuasan dijamin?', f:'Apa hasil terendah?', d:'—', b:'Instrumen/raw data', p:'GPM', r:'Tinggi' },
  { no:'183', k:'C.7', ind:'61 Kepuasan Stakeholder', q:'Bagaimana hasil kepuasan ditindaklanjuti dan dipublikasikan?', f:'Tunjukkan survei → masalah → tindakan → hasil berikutnya.', d:'—', b:'RTL + publikasi', p:'GPM/Kajur', r:'Kritis' },
  // BAB III (60)
  { no:'B3-01', k:'BAB III', ind:'Dasar BAB III', q:'Apa dasar penyusunan BAB III?', f:'Apakah BAB III hanya rencana kerja?', d:'C.1–C.7', b:'LED C.1–C.7 → BAB III', p:'Kaprodi/GPM', r:'Kritis' },
  { no:'B3-02', k:'BAB III', ind:'Dasar BAB III', q:'Jadi BAB III bukan sekadar rencana kerja?', f:'Bagaimana program diturunkan dari gap evaluasi diri?', d:'Indikator terkait', b:'Matriks SWOT + program', p:'Kaprodi', r:'Kritis' },
  { no:'B3-03', k:'BAB III', ind:'Prioritas', q:'Apa tiga masalah strategis terpenting PSBM?', f:'Mengapa masalah tersebut dipilih?', d:'3.b; 6.h.1; 7', b:'BAB III / RTL', p:'Kajur/Kaprodi', r:'Kritis' },
  { no:'B3-04', k:'BAB III', ind:'Prioritas', q:'Mengapa masalah tersebut dipilih?', f:'Apakah muncul konsisten pada evaluasi?', d:'C.3; C.4; C.6; C.7', b:'Analisis faktor penghambat', p:'Kaprodi', r:'Kritis' },
  { no:'B3-05', k:'BAB III', ind:'Traceability', q:'Bagaimana menjamin masalah di BAB III sesuai fakta?', f:'Tunjukkan traceability ke LED/LKPS.', d:'Seluruh LKPS', b:'Matriks traceability', p:'Kaprodi/GPM', r:'Kritis' },
  { no:'B3-06', k:'BAB III', ind:'SWOT', q:'Apa kekuatan utama PSBM?', f:'Bukti konkretnya apa?', d:'2.a; 3.a; 4.a', b:'SWOT', p:'Kaprodi', r:'Tinggi' },
  { no:'B3-07', k:'BAB III', ind:'Kurikulum', q:'Apa bukti kekhasan Broadband Multimedia?', f:'MK apa yang merepresentasikannya?', d:'3.a.1', b:'NADK + Kurikulum', p:'Kurikulum', r:'Tinggi' },
  { no:'B3-08', k:'BAB III', ind:'Kurikulum', q:'Apa bukti kurikulum PSBM kuat secara vokasional?', f:'Berapa SKS praktik/aplikatif?', d:'3.a.1', b:'LKPS 3.a.1', p:'Kurikulum', r:'Tinggi' },
  { no:'B3-09', k:'BAB III', ind:'CPL', q:'Apa kelemahan paling mendasar dari pendidikan?', f:'Mengapa itu dianggap kelemahan strategis?', d:'3.a', b:'Rekap CPL/CPMK', p:'Kurikulum/GPM', r:'Kritis' },
  { no:'B3-10', k:'BAB III', ind:'CPL', q:'Mengapa itu dianggap kelemahan strategis?', f:'CPL sebagai ukuran utama keberhasilan?', d:'3.a', b:'CPL–CPMK–MK', p:'Kurikulum/GPM', r:'Kritis' },
  { no:'B3-11', k:'BAB III', ind:'RPS', q:'Bukankah seluruh RPS sudah tersedia?', f:'Apa tantangan berikutnya?', d:'3.a.2', b:'Repository RPS', p:'Kurikulum', r:'Tinggi' },
  { no:'B3-12', k:'BAB III', ind:'Peluang', q:'Apa peluang terbesar PSBM?', f:'Bagaimana peluang teknologi dimanfaatkan?', d:'—', b:'Analisis lingkungan eksternal', p:'Kajur/Kaprodi', r:'Tinggi' },
  { no:'B3-13', k:'BAB III', ind:'Peluang', q:'Bagaimana peluang teknologi dimanfaatkan?', f:'Program apa yang dijalankan?', d:'3.a; 3.b; 4.a', b:'Kurikulum + roadmap', p:'Kaprodi', r:'Tinggi' },
  { no:'B3-14', k:'BAB III', ind:'Ancaman', q:'Apa ancaman terbesar?', f:'Bagaimana PSBM mengantisipasinya?', d:'3.a; 4.a; 5.a', b:'SWOT', p:'Kajur/Kaprodi', r:'Tinggi' },
  { no:'B3-15', k:'BAB III', ind:'Ancaman', q:'Bagaimana PSBM mengantisipasinya?', f:'Program konkret apa yang dijalankan?', d:'3.a; 4.a; 5.a', b:'Program pengembangan', p:'Kajur/Kaprodi', r:'Tinggi' },
  { no:'B3-16', k:'BAB III', ind:'Penelitian', q:'Apa kelemahan penelitian?', f:'Berapa penelitian DTPS?', d:'3.b; 6.h.1', b:'LKPS penelitian', p:'P3M/Kaprodi', r:'Kritis' },
  { no:'B3-17', k:'BAB III', ind:'Penelitian', q:'Berapa penelitian DTPS?', f:'Bagaimana sumber dananya?', d:'3.b', b:'LKPS 3.b', p:'P3M', r:'Kritis' },
  { no:'B3-18', k:'BAB III', ind:'Penelitian', q:'Bagaimana sumber dananya?', f:'Apa makna angka itu bagi evaluasi diri?', d:'3.b', b:'Kontrak / rekap penelitian', p:'P3M', r:'Kritis' },
  { no:'B3-19', k:'BAB III', ind:'Penelitian', q:'Apa makna angka itu bagi evaluasi diri?', f:'Bagaimana dengan keterlibatan mahasiswa?', d:'3.b', b:'SWOT + LKPS 3.b', p:'P3M', r:'Tinggi' },
  { no:'B3-20', k:'BAB III', ind:'Penelitian', q:'Bagaimana dengan keterlibatan mahasiswa?', f:'Apa program perbaikannya?', d:'6.h.1', b:'LKPS 6.h.1', p:'P3M/Kaprodi', r:'Kritis' },
  { no:'B3-21', k:'BAB III', ind:'Penelitian', q:'Apa program perbaikannya?', f:'Bagaimana integrasi dengan TA?', d:'3.b; 6.h.1', b:'Roadmap + program', p:'P3M', r:'Kritis' },
  { no:'B3-22', k:'BAB III', ind:'PkM', q:'Apa kelemahan PkM?', f:'Berapa PkM PSBM?', d:'3.c', b:'LKPS 3.c', p:'P3M', r:'Kritis' },
  { no:'B3-23', k:'BAB III', ind:'PkM', q:'Berapa PkM PSBM?', f:'Apa yang positif dari PkM?', d:'3.c', b:'LKPS 3.c', p:'P3M', r:'Tinggi' },
  { no:'B3-24', k:'BAB III', ind:'PkM', q:'Apa yang positif dari PkM?', f:'Lalu apa pengembangannya?', d:'3.c; 6.i', b:'LKPS 6.i', p:'P3M', r:'Tinggi' },
  { no:'B3-25', k:'BAB III', ind:'PkM', q:'Lalu apa pengembangannya?', f:'Bagaimana pendanaan eksternal diperluas?', d:'2.a; 3.c', b:'Roadmap PkM', p:'P3M', r:'Tinggi' },
  { no:'B3-26', k:'BAB III', ind:'SDM', q:'Apa kelemahan SDM?', f:'Apa basis kekuatan SDM?', d:'4.a–4.j', b:'SWOT C.4', p:'Kajur', r:'Tinggi' },
  { no:'B3-27', k:'BAB III', ind:'SDM', q:'Apa basis kekuatan SDM?', f:'Apakah jumlah doktor sudah memadai?', d:'4.a; 4.c', b:'LKPS SDM', p:'Kajur/Kaprodi', r:'Kritis' },
  { no:'B3-28', k:'BAB III', ind:'SDM', q:'Apakah jumlah doktor sudah memadai?', f:'Apa masalah JAFA?', d:'4.a', b:'Ijazah + roadmap SDM', p:'Kajur', r:'Tinggi' },
  { no:'B3-29', k:'BAB III', ind:'SDM', q:'Apa masalah JAFA?', f:'Bagaimana strategi percepatan?', d:'4.a', b:'SK JAFA + roadmap', p:'Kajur', r:'Tinggi' },
  { no:'B3-30', k:'BAB III', ind:'Internasionalisasi', q:'Apa kelemahan internasionalisasi?', f:'Apa indikator masalah daya saing global lulusan?', d:'2.a; 4.e; 4.j; 6.g', b:'SWOT', p:'Kajur/Kaprodi', r:'Kritis' },
  { no:'B3-31', k:'BAB III', ind:'Lulusan', q:'Apa indikator masalah daya saing global lulusan?', f:'Apa program untuk mengatasinya?', d:'6.g.2', b:'Survei pengguna', p:'Kaprodi/CDC', r:'Tinggi' },
  { no:'B3-32', k:'BAB III', ind:'Lulusan', q:'Apa program untuk mengatasinya?', f:'Bagaimana mengukur keberhasilannya?', d:'6.g', b:'Program pengembangan', p:'Kaprodi', r:'Tinggi' },
  { no:'B3-33', k:'BAB III', ind:'Kerja Sama', q:'Mengapa kerja sama menjadi kekuatan?', f:'Apakah jumlah cukup untuk menyatakan unggul?', d:'2.a', b:'LKPS 2.a', p:'Kajur/Kaprodi', r:'Kritis' },
  { no:'B3-34', k:'BAB III', ind:'Kerja Sama', q:'Apakah jumlah kerja sama cukup untuk menyatakan unggul?', f:'Apa yang harus dikembangkan?', d:'2.a', b:'IA + laporan outcome', p:'Kajur/Kaprodi', r:'Kritis' },
  { no:'B3-35', k:'BAB III', ind:'Strategi', q:'Apa hubungan SWOT dengan tujuan strategis?', f:'Berikan contoh strategi SO.', d:'—', b:'SWOT → tujuan strategis', p:'Kajur/Kaprodi', r:'Kritis' },
  { no:'B3-36', k:'BAB III', ind:'Strategi SO', q:'Berikan contoh strategi SO.', f:'Berikan contoh strategi WO.', d:'2.a; 3.a; 3.b; 4.a', b:'Matriks SO', p:'Kaprodi', r:'Tinggi' },
  { no:'B3-37', k:'BAB III', ind:'Strategi WO', q:'Berikan contoh strategi WO.', f:'Berikan contoh strategi ST.', d:'2.a; 3.b; 4.e', b:'Matriks WO', p:'Kaprodi', r:'Tinggi' },
  { no:'B3-38', k:'BAB III', ind:'Strategi ST', q:'Berikan contoh strategi ST.', f:'Berikan contoh strategi WT.', d:'3.a; 4.a', b:'Matriks ST', p:'Kaprodi', r:'Tinggi' },
  { no:'B3-39', k:'BAB III', ind:'Strategi WT', q:'Berikan contoh strategi WT.', f:'Bagaimana strategi ini diimplementasikan?', d:'4.a; 5.a; 6.g', b:'Matriks WT', p:'Kajur/Kaprodi', r:'Tinggi' },
  { no:'B3-40', k:'BAB III', ind:'Tujuan Strategis', q:'Apa tujuan strategis utama pengembangan?', f:'Bagaimana memastikan tujuan strategis sesuai VMTS?', d:'C.1–C.7', b:'Tujuan Strategis BAB III', p:'Kajur/Kaprodi', r:'Kritis' },
  { no:'B3-41', k:'BAB III', ind:'Tujuan Strategis', q:'Bagaimana memastikan tujuan strategis sesuai VMTS?', f:'Siapa yang bertanggung jawab?', d:'—', b:'VMTS → SWOT → tujuan', p:'Kajur/Kaprodi', r:'Kritis' },
  { no:'B3-42', k:'BAB III', ind:'Program Pendidikan', q:'Apa prioritas pertama pendidikan?', f:'Apa indikator keberhasilannya?', d:'3.a', b:'Tabel 3.2', p:'Kurikulum', r:'Kritis' },
  { no:'B3-43', k:'BAB III', ind:'Program Pendidikan', q:'Apa indikator keberhasilannya?', f:'Bagaimana membuktikan closed loop CPL?', d:'3.a', b:'Dashboard / rekap CPL', p:'Kurikulum/GPM', r:'Kritis' },
  { no:'B3-44', k:'BAB III', ind:'CPL', q:'Bagaimana membuktikan closed loop CPL?', f:'Siapa yang bertanggung jawab?', d:'3.a', b:'CPL → BA → RTL', p:'Kurikulum/GPM', r:'Kritis' },
  { no:'B3-45', k:'BAB III', ind:'PIC', q:'Siapa yang bertanggung jawab?', f:'Bagaimana koordinasi dengan stakeholder?', d:'—', b:'SK + BA evaluasi', p:'Kaprodi', r:'Tinggi' },
  { no:'B3-46', k:'BAB III', ind:'Program Penelitian', q:'Apa prioritas penelitian?', f:'Bagaimana keberhasilannya diukur?', d:'3.b; 6.h.1', b:'Program penelitian', p:'P3M', r:'Kritis' },
  { no:'B3-47', k:'BAB III', ind:'Program Penelitian', q:'Bagaimana keberhasilannya diukur?', f:'Apa target konkret?', d:'3.b; 4.e–4.g; 6.h.1', b:'LKPS + laporan', p:'P3M', r:'Kritis' },
  { no:'B3-48', k:'BAB III', ind:'Program PkM', q:'Apa prioritas PkM?', f:'Bagaimana dampaknya dievaluasi?', d:'3.c; 6.i', b:'Program PkM', p:'P3M', r:'Tinggi' },
  { no:'B3-49', k:'BAB III', ind:'Program SDM', q:'Apa prioritas SDM?', f:'Siapa PIC-nya?', d:'4.a–4.j', b:'Roadmap SDM', p:'Kajur', r:'Tinggi' },
  { no:'B3-50', k:'BAB III', ind:'Program Sarpras', q:'Apa prioritas sarpras?', f:'Bagaimana kelayakan program?', d:'5.a', b:'Inventaris + RKAT', p:'Kajur/Kalab', r:'Tinggi' },
  { no:'B3-51', k:'BAB III', ind:'Kelayakan', q:'Bagaimana program dibuat realistis?', f:'Dari mana anggarannya?', d:'2.b; 4; 5', b:'Tabel 3.2 + RKAT', p:'Kajur', r:'Kritis' },
  { no:'B3-52', k:'BAB III', ind:'Anggaran', q:'Dari mana anggarannya?', f:'Bagaimana program dimonitor?', d:'2.b', b:'RKAT + kontrak', p:'Kajur', r:'Kritis' },
  { no:'B3-53', k:'BAB III', ind:'Monitoring', q:'Bagaimana program dimonitor?', f:'Bagaimana BAB III masuk PPEPP?', d:'7', b:'AMI + RTM + RTL', p:'GPM', r:'Kritis' },
  { no:'B3-54', k:'BAB III', ind:'PPEPP', q:'Bagaimana BAB III masuk PPEPP?', f:'Apa bukti program ini berkelanjutan setelah AL?', d:'7.a; 7.b', b:'PPEPP + AMI + RTM', p:'GPM', r:'Kritis' },
  { no:'B3-55', k:'BAB III', ind:'Keberlanjutan', q:'Apa bukti program ini berkelanjutan setelah AL?', f:'Bagaimana stakeholder eksternal berperan?', d:'—', b:'Renstra + Renop + RKAT', p:'Kajur', r:'Kritis' },
  { no:'B3-56', k:'BAB III', ind:'Stakeholder', q:'Bagaimana stakeholder eksternal berperan?', f:'Apa risiko jika program pengembangan tidak berhasil?', d:'2.a; 3.a', b:'BA + IA + laporan', p:'Kaprodi', r:'Tinggi' },
  { no:'B3-57', k:'BAB III', ind:'Prioritas', q:'Jika sumber daya terbatas, program mana didahulukan?', f:'Bagaimana menentukan prioritas?', d:'C.3; C.4; C.6; C.7', b:'Matriks prioritas', p:'Kajur/Kaprodi', r:'Kritis' },
  { no:'B3-58', k:'BAB III', ind:'Risiko', q:'Apa risiko jika program pengembangan tidak berhasil?', f:'Bagaimana mitigasinya?', d:'—', b:'Risk Register + SWOT', p:'Kajur/Kaprodi', r:'Tinggi' },
  { no:'B3-59', k:'BAB III', ind:'Outcome', q:'Bagaimana PSBM tahu program berhasil?', f:'Indikator outcome apa yang dipakai?', d:'C.3; C.4; C.6', b:'KPI + LKPS periode berikutnya', p:'GPM/Kaprodi', r:'Kritis' },
  { no:'B3-60', k:'BAB III', ind:'Arah Pengembangan', q:'Dalam satu kalimat, ke mana PSBM akan dikembangkan?', f:'Bagaimana VMTS mendukung arah ini?', d:'C.1–C.7', b:'VMTS + BAB III', p:'Kajur/Kaprodi', r:'Kritis' }
];

// ===== NAVIGATION =====
function showPanel(id, btn) {
  document.querySelectorAll('.al-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.folder-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  if (id === 'bank') initBank();
  if (id === 'data') renderData('all');
  if (id === 'modeal') renderKritis();
}

// ===== DATA KUNCI LKPS =====
let currentLKPSFilter = 'all';
function filterLKPS(filter, btn) {
  document.querySelectorAll('.lkps-cat-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  currentLKPSFilter = filter;
  renderLKPS();
}

function renderData(filter) {
  currentLKPSFilter = filter;
  document.querySelectorAll('.lkps-cat-btn').forEach(b => {
    b.classList.remove('active');
    if (b.textContent.trim() === 'Semua') b.classList.add('active');
  });
  renderLKPS();
}

function renderLKPS() {
  const search = (document.getElementById('lkpsSearch')?.value || '').toLowerCase();
  const wajibOnly = document.getElementById('filterWajib')?.value || '';

  let filtered = dataLKPS;
  if (currentLKPSFilter !== 'all') filtered = filtered.filter(d => d.kategori === currentLKPSFilter);
  if (search) filtered = filtered.filter(d => 
    d.nama.toLowerCase().includes(search) || 
    d.value.toLowerCase().includes(search) || 
    d.catatan.toLowerCase().includes(search)
  );
  if (wajibOnly === 'wajib') filtered = filtered.filter(d => d.wajib);

  // Sort: wajib first
  filtered.sort((a, b) => (b.wajib ? 1 : 0) - (a.wajib ? 1 : 0));

  let html = '<div style="margin-bottom:12px; font-size:0.85rem; color:#666;">Menampilkan <strong>' + filtered.length + '</strong> dari ' + dataLKPS.length + ' angka</div>';
  
  filtered.forEach(d => {
    html += '<div class="lkps-card ' + (d.wajib ? 'wajib' : '') + '">';
    html += '<div class="lkps-card-header">';
    html += '<div class="lkps-card-title">' + d.nama + (d.wajib ? '<span class="wajib-badge">🔴 WAJIB KONSISTEN</span>' : '') + '</div>';
    html += '<div class="lkps-card-value">' + d.value + '</div>';
    html += '</div>';
    html += '<div class="lkps-card-note"><strong>📝 Catatan:</strong> ' + d.catatan + '</div>';
    
    if (d.pertanyaan && d.pertanyaan.length > 0) {
      html += '<div class="lkps-card-actions">';
      html += '<button class="lkps-btn primary" onclick="jumpToPertanyaan(\'' + d.pertanyaan[0] + '\')"> Lihat Pertanyaan Terkait (' + d.pertanyaan.length + ')</button>';
      html += '<button class="lkps-btn" onclick="alert(\'Buka LKPS: ' + d.nama + '\')">📄 Buka LKPS</button>';
      html += '<button class="lkps-btn" onclick="alert(\'Buka Evidence: ' + d.nama + '\')">📁 Buka Evidence</button>';
      html += '</div>';
    }
    html += '</div>';
  });

  if (filtered.length === 0) {
    html = '<div class="no-result">🔍 Tidak ada angka yang cocok dengan filter.</div>';
  }

  document.getElementById('lkpsContent').innerHTML = html;
}

function jumpToPertanyaan(no) {
  const btns = document.querySelectorAll('.folder-tab');
  showPanel('bank', btns[2]);
  setTimeout(() => {
    const card = document.getElementById('qcard-' + no);
    if (card) {
      card.classList.add('open');
      card.scrollIntoView({ behavior: 'smooth', block: 'center' });
      card.style.boxShadow = '0 0 0 3px #0d47a1';
      setTimeout(() => { card.style.boxShadow = ''; }, 2500);
    }
  }, 300);
}

// ===== STATS =====
function renderStats() {
  const total = dataPertanyaan.length;
  const kritis = dataPertanyaan.filter(q => q.r === 'Kritis').length;
  const tinggi = dataPertanyaan.filter(q => q.r === 'Tinggi').length;
  const sedang = dataPertanyaan.filter(q => q.r === 'Sedang').length;
  const rendah = dataPertanyaan.filter(q => q.r === 'Rendah').length;
  document.getElementById('statsBar').innerHTML = 
    '<div class="stat-mini"><div class="snum">' + total + '</div><div class="slbl">Total Pertanyaan</div></div>' +
    '<div class="stat-mini kritis"><div class="snum">' + kritis + '</div><div class="slbl">🔴 Kritis</div></div>' +
    '<div class="stat-mini tinggi"><div class="snum">' + tinggi + '</div><div class="slbl">🟠 Tinggi</div></div>' +
    '<div class="stat-mini sedang"><div class="snum">' + sedang + '</div><div class="slbl">🟡 Sedang</div></div>' +
    '<div class="stat-mini rendah"><div class="snum">' + rendah + '</div><div class="slbl">🟢 Rendah</div></div>';
}

// ===== SUB NAV KRITERIA + BAB III =====
let currentKFilter = 'all';
function renderSubNav() {
  const counts = { all: dataPertanyaan.length };
  ['C.1','C.2','C.3','C.4','C.5','C.6','C.7','BAB III'].forEach(k => {
    counts[k] = dataPertanyaan.filter(q => q.k === k).length;
  });
  let html = '<button class="active" onclick="filterK(\'all\', this)">Semua <span class="count">' + counts.all + '</span></button>';
  ['C.1','C.2','C.3','C.4','C.5','C.6','C.7'].forEach(k => {
    html += '<button onclick="filterK(\'' + k + '\', this)">' + k + ' <span class="count">' + counts[k] + '</span></button>';
  });
  html += '<button class="bab3-btn" onclick="filterK(\'BAB III\', this)">📘 BAB III <span class="count">' + counts['BAB III'] + '</span></button>';
  document.getElementById('bankSubNav').innerHTML = html;
}
function filterK(k, btn) {
  document.querySelectorAll('#bankSubNav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  currentKFilter = k;
  renderBank();
}

// ===== PIC OPTIONS =====
function renderPICOptions() {
  const pics = [...new Set(dataPertanyaan.map(q => q.p))].sort();
  const sel = document.getElementById('filterPIC');
  sel.innerHTML = '<option value="">Semua PIC</option>';
  pics.forEach(p => {
    const opt = document.createElement('option');
    opt.value = p;
    opt.textContent = p;
    sel.appendChild(opt);
  });
}

// ===== RENDER BANK =====
function renderBank() {
  const search = (document.getElementById('bankSearch')?.value || '').toLowerCase();
  const risk = document.getElementById('filterRisk')?.value || '';
  const pic = document.getElementById('filterPIC')?.value || '';

  let filtered = dataPertanyaan;
  if (currentKFilter !== 'all') filtered = filtered.filter(q => q.k === currentKFilter);
  if (search) filtered = filtered.filter(q => 
    q.q.toLowerCase().includes(search) || 
    q.ind.toLowerCase().includes(search) || 
    q.f.toLowerCase().includes(search) ||
    q.b.toLowerCase().includes(search) ||
    q.p.toLowerCase().includes(search)
  );
  if (risk) filtered = filtered.filter(q => q.r === risk);
  if (pic) filtered = filtered.filter(q => q.p.toLowerCase().includes(pic.toLowerCase()));

  let html = '<div style="margin-bottom:12px; font-size:0.85rem; color:#666;">Menampilkan <strong>' + filtered.length + '</strong> dari ' + dataPertanyaan.length + ' pertanyaan</div>';
  
  filtered.forEach(q => {
    const isBab3 = q.k === 'BAB III';
    html += '<div class="q-card ' + (isBab3 ? 'bab3' : '') + '" id="qcard-' + q.no + '">';
    html += '<div class="q-card-header" onclick="toggleQ(\'' + q.no + '\')">';
    html += '<div class="q-num">#' + q.no + '</div>';
    html += '<div class="q-ind">' + q.k + ' • ' + q.ind + '</div>';
    html += '<div class="q-main">' + q.q + '</div>';
    html += '<div class="q-risk ' + q.r + '">' + q.r.toUpperCase() + '</div>';
    html += '<div class="q-toggle">▼</div>';
    html += '</div>';
    html += '<div class="q-card-body">';
    
    html += '<div class="q-section"><div class="q-section-title">❓ PERTANYAAN UTAMA</div><div class="q-section-content">' + q.q + '</div></div>';
    html += '<div class="q-followup"><div class="flabel">🔍 PERTANYAAN PENDALAMAN / FOLLOW-UP</div><div class="ftext">' + q.f + '</div></div>';
    html += '<div class="q-meta-grid">';
    html += '<div class="q-meta-item"><div class="mlabel">📊 Data LKPS</div><div class="mvalue">' + q.d + '</div></div>';
    html += '<div class="q-meta-item"><div class="mlabel"> PIC</div><div class="mvalue">' + q.p + '</div></div>';
    html += '<div class="q-meta-item"><div class="mlabel">⚠️ Risiko</div><div class="mvalue"><span class="q-risk ' + q.r + '" style="font-size:0.72rem;">' + q.r.toUpperCase() + '</span></div></div>';
    html += '</div>';
    html += '<div class="q-section" style="margin-top:12px;"><div class="q-section-title">📎 BUKTI YANG DIBUKA</div><div class="q-section-content">' + q.b + '</div></div>';
    
    html += '</div></div>';
  });

  if (filtered.length === 0) {
    html = '<div class="no-result">🔍 Tidak ada pertanyaan yang cocok dengan filter.<br><small>Coba ubah kata kunci atau filter.</small></div>';
  }

  document.getElementById('bankContent').innerHTML = html;
}

function toggleQ(no) {
  document.getElementById('qcard-' + no).classList.toggle('open');
}

// ===== MODE AL SEARCH =====
function quickSearch(keyword) {
  document.getElementById('modeAlSearch').value = keyword;
  searchModeAL();
}

function clearSearch() {
  document.getElementById('modeAlSearch').value = '';
  document.getElementById('searchResultContainer').innerHTML = '';
  document.getElementById('defaultModeAL').style.display = 'block';
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

  // Cari di LKPS
  dataLKPS.forEach(d => {
    if (d.nama.toLowerCase().includes(query) || 
        d.value.toLowerCase().includes(query) || 
        d.catatan.toLowerCase().includes(query)) {
      results.push({ type: 'lkps', data: d });
    }
  });

  // Cari di pertanyaan
  dataPertanyaan.forEach(q => {
    const match = q.q.toLowerCase().includes(query) ||
                  q.ind.toLowerCase().includes(query) ||
                  q.f.toLowerCase().includes(query) ||
                  q.b.toLowerCase().includes(query) ||
                  q.p.toLowerCase().includes(query) ||
                  q.k.toLowerCase().includes(query);
    if (match) results.push({ type: 'pertanyaan', data: q });
  });

  if (results.length === 0) {
    container.innerHTML = '<div class="no-result">🔍 Tidak ditemukan hasil untuk "<strong>' + query + '</strong>"<br><small>Coba kata kunci lain.</small></div>';
    return;
  }

  let html = '<div style="margin-bottom:12px; font-size:0.85rem; color:#666;">Ditemukan <strong>' + results.length + '</strong> hasil</div>';
  
  // Tampilkan LKPS dulu
  results.filter(r => r.type === 'lkps').forEach(r => {
    const d = r.data;
    html += '<div class="lkps-card ' + (d.wajib ? 'wajib' : '') + '">';
    html += '<div class="lkps-card-header">';
    html += '<div class="lkps-card-title">' + d.nama + (d.wajib ? '<span class="wajib-badge"> WAJIB KONSISTEN</span>' : '') + '</div>';
    html += '<div class="lkps-card-value">' + d.value + '</div>';
    html += '</div>';
    html += '<div class="lkps-card-note"><strong>📝 Catatan:</strong> ' + d.catatan + '</div>';
    if (d.pertanyaan && d.pertanyaan.length > 0) {
      html += '<div class="lkps-card-actions">';
      html += '<button class="lkps-btn primary" onclick="jumpToPertanyaan(\'' + d.pertanyaan[0] + '\')">❓ Pertanyaan Terkait (' + d.pertanyaan.length + ')</button>';
      html += '</div>';
    }
    html += '</div>';
  });

  // Lalu pertanyaan
  results.filter(r => r.type === 'pertanyaan').forEach(q => {
    const qd = q.data;
    const isBab3 = qd.k === 'BAB III';
    html += '<div class="q-card ' + (isBab3 ? 'bab3' : '') + '" id="mcard-' + qd.no + '">';
    html += '<div class="q-card-header" onclick="document.getElementById(\'mcard-' + qd.no + '\').classList.toggle(\'open\')">';
    html += '<div class="q-num">#' + qd.no + '</div>';
    html += '<div class="q-ind">' + qd.k + ' • ' + qd.ind + '</div>';
    html += '<div class="q-main">' + qd.q + '</div>';
    html += '<div class="q-risk ' + qd.r + '">' + qd.r.toUpperCase() + '</div>';
    html += '<div class="q-toggle">▼</div>';
    html += '</div>';
    html += '<div class="q-card-body">';
    html += '<div class="q-followup"><div class="flabel">🔍 FOLLOW-UP ASESOR</div><div class="ftext">' + qd.f + '</div></div>';
    html += '<div class="q-meta-grid">';
    html += '<div class="q-meta-item"><div class="mlabel">📊 Data LKPS</div><div class="mvalue">' + qd.d + '</div></div>';
    html += '<div class="q-meta-item"><div class="mlabel">👤 PIC</div><div class="mvalue">' + qd.p + '</div></div>';
    html += '<div class="q-meta-item"><div class="mlabel">⚠️ Risiko</div><div class="mvalue"><span class="q-risk ' + qd.r + '" style="font-size:0.72rem;">' + qd.r.toUpperCase() + '</span></div></div>';
    html += '</div>';
    html += '<div class="q-section" style="margin-top:12px;"><div class="q-section-title">📎 BUKTI</div><div class="q-section-content">' + qd.b + '</div></div>';
    html += '<div style="margin-top:12px;"><button class="lkps-btn primary" onclick="jumpToBank(\'' + qd.no + '\')">📋 Lihat di Bank Pertanyaan</button></div>';
    html += '</div></div>';
  });

  container.innerHTML = html;
}

function jumpToBank(no) {
  const btns = document.querySelectorAll('.folder-tab');
  showPanel('bank', btns[2]);
  setTimeout(() => {
    const card = document.getElementById('qcard-' + no);
    if (card) {
      card.classList.add('open');
      card.scrollIntoView({ behavior: 'smooth', block: 'center' });
      card.style.boxShadow = '0 0 0 3px #0d47a1';
      setTimeout(() => { card.style.boxShadow = ''; }, 2500);
    }
  }, 300);
}

function renderKritis() {
  const kritis = dataPertanyaan.filter(q => q.r === 'Kritis').slice(0, 10);
  let html = '';
  kritis.forEach(q => {
    const isBab3 = q.k === 'BAB III';
    html += '<div class="q-card ' + (isBab3 ? 'bab3' : '') + '" id="kcard-' + q.no + '">';
    html += '<div class="q-card-header" onclick="document.getElementById(\'kcard-' + q.no + '\').classList.toggle(\'open\')">';
    html += '<div class="q-num">#' + q.no + '</div>';
    html += '<div class="q-ind">' + q.k + ' • ' + q.ind + '</div>';
    html += '<div class="q-main">' + q.q + '</div>';
    html += '<div class="q-risk Kritis">KRITIS</div>';
    html += '<div class="q-toggle">▼</div>';
    html += '</div>';
    html += '<div class="q-card-body">';
    html += '<div class="q-followup"><div class="flabel">🔍 FOLLOW-UP</div><div class="ftext">' + q.f + '</div></div>';
    html += '<div class="q-meta-grid">';
    html += '<div class="q-meta-item"><div class="mlabel">📊 Data LKPS</div><div class="mvalue">' + q.d + '</div></div>';
    html += '<div class="q-meta-item"><div class="mlabel">👤 PIC</div><div class="mvalue">' + q.p + '</div></div>';
    html += '</div>';
    html += '<div class="q-section" style="margin-top:12px;"><div class="q-section-title">📎 BUKTI</div><div class="q-section-content">' + q.b + '</div></div>';
    html += '</div></div>';
  });
  document.getElementById('kritisList').innerHTML = html;
}

// ===== INIT =====
function initBank() {
  renderStats();
  renderSubNav();
  renderPICOptions();
  renderBank();
}

document.addEventListener('DOMContentLoaded', function() {
  renderKritis();
  initBank();
  renderLKPS();
});
</script>

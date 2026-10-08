---
layout: default
title: Evidence AL
permalink: /evidence-al/
---

<style>
.ev-cabinet { background: linear-gradient(180deg, #e3f2fd 0%, #bbdefb 100%); padding: 20px 20px 0 20px; border-radius: 16px 16px 0 0; box-shadow: inset 0 4px 12px rgba(13, 71, 161, 0.08), 0 4px 16px rgba(0,0,0,0.06); position: relative; border: 1px solid #bbdefb; border-bottom: none; }
.ev-shelf { display: flex; flex-wrap: nowrap; gap: 6px; padding: 0 8px; position: relative; z-index: 10; overflow-x: auto; overflow-y: visible; scrollbar-width: thin; scrollbar-color: #0d47a1 transparent; padding-bottom: 4px; }
.ev-shelf::-webkit-scrollbar { height: 4px; }
.ev-shelf::-webkit-scrollbar-track { background: rgba(13, 71, 161, 0.05); border-radius: 2px; }
.ev-shelf::-webkit-scrollbar-thumb { background: #0d47a1; border-radius: 2px; }
.ev-tab { position: relative; flex: 1 1 0; min-width: 0; padding: 14px 8px 18px 8px; background: #ffffff; border-radius: 10px 10px 0 0; border: 1px solid #e0e0e0; border-bottom: none; cursor: pointer; text-align: center; font-weight: 600; font-size: 0.78rem; line-height: 1.2; color: #555; transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1); transform: translateY(4px); box-shadow: 0 -2px 6px rgba(0,0,0,0.05); white-space: normal; word-wrap: break-word; overflow-wrap: break-word; }
.ev-tab::before { content: ''; position: absolute; top: -6px; left: 22%; width: 56%; height: 6px; background: #f5f5f5; border-radius: 4px 4px 0 0; border: 1px solid #e0e0e0; border-bottom: none; transition: all 0.35s ease; }
.ev-tab:hover { background: #f1f5f9; transform: translateY(0px); color: #0d47a1; }
.ev-tab:hover::before { background: #f1f5f9; }
.ev-tab.active { background: #0d47a1; color: #ffffff; transform: translateY(-6px); z-index: 20; border-color: #0d47a1; box-shadow: 0 -4px 16px rgba(13, 71, 161, 0.25); font-weight: 700; }
.ev-tab.active::before { background: #0d47a1; border-color: #0d47a1; height: 8px; top: -8px; }
.ev-tab.sesi1 { background: linear-gradient(180deg, #e3f2fd 0%, #bbdefb 100%); color: #0d47a1; border-color: #90caf9; }
.ev-tab.sesi1.active { background: linear-gradient(135deg, #1565c0 0%, #0d47a1 100%); color: white; }
.ev-tab.sesi2 { background: linear-gradient(180deg, #e8f5e9 0%, #c8e6c9 100%); color: #2e7d32; border-color: #a5d6a7; }
.ev-tab.sesi2.active { background: linear-gradient(135deg, #388e3c 0%, #2e7d32 100%); color: white; }
.ev-tab.sesi3 { background: linear-gradient(180deg, #fff3e0 0%, #ffe0b2 100%); color: #e65100; border-color: #ffcc80; }
.ev-tab.sesi3.active { background: linear-gradient(135deg, #f57c00 0%, #e65100 100%); color: white; }

.ev-content { background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1; border-radius: 0 0 16px 16px; padding: 28px; min-height: 500px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px; }
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

/* Session Header */
.session-header { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); color: white; padding: 24px; border-radius: 12px; margin-bottom: 20px; }
.session-header.sesi2 { background: linear-gradient(135deg, #2e7d32 0%, #388e3c 100%); }
.session-header.sesi3 { background: linear-gradient(135deg, #e65100 0%, #f57c00 100%); }
.session-header h2 { margin: 0 0 8px 0; font-size: 1.4rem; }
.session-header .subtitle { opacity: 0.9; font-size: 0.9rem; margin-bottom: 16px; }
.session-header .session-info { display: flex; gap: 20px; flex-wrap: wrap; margin-top: 12px; }
.session-header .info-item { background: rgba(255,255,255,0.15); padding: 8px 14px; border-radius: 8px; font-size: 0.85rem; }
.session-header .info-item strong { display: block; font-size: 1.2rem; margin-bottom: 2px; }

/* Progress Bar */
.progress-section { background: #f8fafc; border: 1px solid #e0e0e0; border-radius: 10px; padding: 16px; margin-bottom: 20px; }
.progress-section h3 { color: #0d47a1; margin: 0 0 12px 0; font-size: 1rem; }
.progress-bar { height: 20px; background: #e0e0e0; border-radius: 10px; overflow: hidden; margin-bottom: 8px; }
.progress-fill { height: 100%; background: linear-gradient(90deg, #4caf50 0%, #81c784 100%); transition: width 0.5s ease; display: flex; align-items: center; justify-content: center; color: white; font-size: 0.75rem; font-weight: 700; }
.progress-stats { display: flex; justify-content: space-between; font-size: 0.82rem; color: #666; }

/* Sub-nav Kategori */
.ev-subnav { display: flex; gap: 4px; margin-bottom: 16px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
.ev-subnav button { padding: 8px 14px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.82rem; }
.ev-subnav button:hover { color: #0d47a1; background: #f8fafc; }
.ev-subnav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }
.ev-subnav button .cnt { background: #e3f2fd; color: #0d47a1; padding: 2px 8px; border-radius: 10px; font-size: 0.7rem; margin-left: 4px; font-weight: 700; }
.ev-subnav button.active .cnt { background: #0d47a1; color: white; }

/* Evidence Card */
.ev-card { background: white; border: 1px solid #e0e0e0; border-radius: 10px; padding: 14px 16px; margin-bottom: 10px; transition: all 0.2s; display: flex; gap: 14px; align-items: flex-start; }
.ev-card:hover { box-shadow: 0 4px 14px rgba(0,0,0,0.08); transform: translateX(2px); }
.ev-card.utama { border-left: 4px solid #0d47a1; }
.ev-card.pendukung { border-left: 4px solid #90a4ae; }
.ev-card-icon { font-size: 1.6rem; min-width: 36px; text-align: center; padding-top: 2px; }
.ev-card-body { flex: 1; min-width: 0; }
.ev-card-title { font-weight: 700; color: #333; font-size: 0.92rem; margin-bottom: 4px; }
.ev-card-desc { font-size: 0.82rem; color: #555; line-height: 1.5; margin-bottom: 8px; }
.ev-card-meta { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 10px; }
.ev-badge { padding: 3px 10px; border-radius: 10px; font-size: 0.68rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.3px; }
.ev-badge.utama { background: #e3f2fd; color: #0d47a1; }
.ev-badge.pendukung { background: #eceff1; color: #546e7a; }
.ev-badge.jenis { background: #f3e5f5; color: #6a1b9a; }
.ev-badge.tahun { background: #e8f5e9; color: #2e7d32; }
.ev-badge.sumber { background: #fff8e1; color: #e65100; }
.ev-card-actions { display: flex; gap: 6px; flex-wrap: wrap; }
.ev-open-btn { padding: 6px 14px; border-radius: 6px; border: none; background: #0d47a1; color: white; font-size: 0.78rem; font-weight: 600; cursor: pointer; transition: all 0.2s; display: inline-flex; align-items: center; gap: 4px; text-decoration: none; }
.ev-open-btn:hover { background: #1565c0; transform: translateY(-1px); }
.ev-open-btn.secondary { background: white; color: #0d47a1; border: 1px solid #0d47a1; }
.ev-open-btn.secondary:hover { background: #e3f2fd; }
.ev-open-btn:disabled { background: #bdbdbd; cursor: not-allowed; }

/* Checklist */
.checklist-section { background: #f8fafc; border: 1px solid #e0e0e0; border-radius: 10px; padding: 16px; margin-bottom: 20px; }
.checklist-section h3 { color: #0d47a1; margin: 0 0 12px 0; font-size: 1rem; }
.checklist-item { display: flex; align-items: center; gap: 10px; padding: 8px 0; border-bottom: 1px solid #e0e0e0; }
.checklist-item:last-child { border-bottom: none; }
.checklist-item input[type="checkbox"] { width: 18px; height: 18px; cursor: pointer; accent-color: #0d47a1; }
.checklist-item label { font-size: 0.88rem; color: #333; cursor: pointer; flex: 1; }
.checklist-item.done label { text-decoration: line-through; color: #999; }

/* Quick Access Grid */
.quick-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); gap: 10px; margin: 16px 0; }
.quick-card { background: white; border: 1px solid #e0e0e0; border-left: 4px solid #0d47a1; border-radius: 8px; padding: 12px; cursor: pointer; transition: all 0.2s; }
.quick-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); transform: translateY(-2px); border-left-color: #4caf50; }
.quick-card .qc-icon { font-size: 1.4rem; margin-bottom: 4px; }
.quick-card .qc-name { font-weight: 700; color: #333; font-size: 0.85rem; }
.quick-card .qc-desc { font-size: 0.72rem; color: #666; margin-top: 2px; }

/* Search */
.ev-search-wrap { display: flex; gap: 8px; max-width: 700px; margin: 0 auto 16px auto; }
.ev-search { flex: 1; padding: 14px 22px; border-radius: 30px; border: 2px solid rgba(255,255,255,0.3); background: rgba(255,255,255,0.15); color: white; font-size: 1rem; backdrop-filter: blur(4px); }
.ev-search::placeholder { color: rgba(255,255,255,0.7); }
.ev-search:focus { outline: none; border-color: #fff; background: rgba(255,255,255,0.25); }
.ev-btn { padding: 14px 22px; border-radius: 30px; border: none; font-size: 0.95rem; font-weight: 600; cursor: pointer; transition: all 0.2s; white-space: nowrap; }
.ev-btn.search { background: #4caf50; color: white; }
.ev-btn.search:hover { background: #45a049; }
.ev-btn.clear { background: rgba(255,255,255,0.2); color: white; border: 2px solid rgba(255,255,255,0.5); }

.no-result { text-align: center; padding: 40px 20px; color: #888; background: #f8fafc; border-radius: 10px; }

@media (max-width: 767px) {
.ev-shelf { gap: 4px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
.ev-shelf::-webkit-scrollbar { display: none; }
.ev-tab { min-width: 90px; flex: 0 0 auto; font-size: 0.72rem; padding: 12px 6px 16px 6px; }
.ev-content { padding: 20px; }
.ev-search-wrap { flex-direction: column; }
.ev-btn { width: 100%; }
.ev-card { flex-direction: column; }
.session-header .session-info { flex-direction: column; gap: 8px; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab sesi1 active" onclick="showEvPanel('sesi1', this)">📊<br>SESI 1<br>LKPS</div>
    <div class="ev-tab sesi2" onclick="showEvPanel('sesi2', this)">🔄<br>SESI 2<br>Penjaminan Mutu</div>
    <div class="ev-tab sesi3" onclick="showEvPanel('sesi3', this)">📕<br>SESI 3<br>LEDPS</div>
  </div>

  <div class="ev-content">

    <!-- ========== SESI 1: LKPS ========== -->
    <div class="ev-panel active" id="panel-sesi1">
      <div class="session-header">
        <h2>📊 SESI 1 — LAPORAN KINERJA PROGRAM STUDI (LKPS)</h2>
        <div class="subtitle">Data kuantitatif 3 tahun terakhir (TS-2, TS-1, TS)</div>
        <div class="session-info">
          <div class="info-item"><strong>87</strong> Dokumen Evidence</div>
          <div class="info-item"><strong>C.1–C.7</strong> Semua Kriteria</div>
          <div class="info-item"><strong>3 Tahun</strong> Periode Data</div>
        </div>
      </div>

      <!-- Progress -->
      <div class="progress-section">
        <h3>📈 Progress Kesiapan Sesi 1</h3>
        <div class="progress-bar">
          <div class="progress-fill" style="width: 75%;">75%</div>
        </div>
        <div class="progress-stats">
          <span>65 dari 87 dokumen siap</span>
          <span>22 dokumen perlu verifikasi</span>
        </div>
      </div>

      <!-- Checklist -->
      <div class="checklist-section">
        <h3>✅ Checklist Dokumen Sesi 1</h3>
        <div class="checklist-item done"><input type="checkbox" checked><label>Tabel 1 — VMTS dan Profil Program Studi</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Tabel 2.a — Kerja Sama Tridharma</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Tabel 2.b — Keuangan dan Pembiayaan</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Tabel 3.a.1 — Kurikulum dan CPL</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Tabel 3.b — Penelitian DTPS</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Tabel 3.c — PkM DTPS</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Tabel 4.a — DTPS dan Kualifikasi</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Tabel 4.e — Publikasi DTPS</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Tabel 5.a — Sarana dan Prasarana</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Tabel 6.a — Mahasiswa</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Tabel 6.f — Tracer Study</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Tabel 7.a — SPMI</label></div>
      </div>

      <!-- Quick Access -->
      <h3 style="color:#0d47a1; margin: 20px 0 12px 0;">⚡ Akses Cepat Dokumen LKPS</h3>
      <div class="quick-grid">
        <div class="quick-card" onclick="filterKategori('lkps-table1')">
          <div class="qc-icon">📊</div>
          <div class="qc-name">Tabel 1</div>
          <div class="qc-desc">VMTS & Profil PS</div>
        </div>
        <div class="quick-card" onclick="filterKategori('lkps-kerja-sama')">
          <div class="qc-icon">🤝</div>
          <div class="qc-name">Tabel 2.a</div>
          <div class="qc-desc">Kerja Sama (66)</div>
        </div>
        <div class="quick-card" onclick="filterKategori('lkps-keuangan')">
          <div class="qc-icon">💰</div>
          <div class="qc-name">Tabel 2.b</div>
          <div class="qc-desc">Keuangan</div>
        </div>
        <div class="quick-card" onclick="filterKategori('lkps-kurikulum')">
          <div class="qc-icon">📘</div>
          <div class="qc-name">Tabel 3.a</div>
          <div class="qc-desc">Kurikulum & CPL</div>
        </div>
        <div class="quick-card" onclick="filterKategori('lkps-penelitian')">
          <div class="qc-icon">🔬</div>
          <div class="qc-name">Tabel 3.b</div>
          <div class="qc-desc">Penelitian (45)</div>
        </div>
        <div class="quick-card" onclick="filterKategori('lkps-pkm')">
          <div class="qc-icon"></div>
          <div class="qc-name">Tabel 3.c</div>
          <div class="qc-desc">PkM (14)</div>
        </div>
        <div class="quick-card" onclick="filterKategori('lkps-sdm')">
          <div class="qc-icon">👨‍🏫</div>
          <div class="qc-name">Tabel 4</div>
          <div class="qc-desc">SDM & DTPS</div>
        </div>
        <div class="quick-card" onclick="filterKategori('lkps-sarpras')">
          <div class="qc-icon">🔧</div>
          <div class="qc-name">Tabel 5</div>
          <div class="qc-desc">Sarpras & K3L</div>
        </div>
        <div class="quick-card" onclick="filterKategori('lkps-mahasiswa')">
          <div class="qc-icon">🎓</div>
          <div class="qc-name">Tabel 6</div>
          <div class="qc-desc">Mahasiswa & Luaran</div>
        </div>
        <div class="quick-card" onclick="filterKategori('lkps-tracer')">
          <div class="qc-icon"></div>
          <div class="qc-name">Tabel 6.f</div>
          <div class="qc-desc">Tracer Study</div>
        </div>
      </div>

      <!-- Evidence List -->
      <div id="sesi1Content"></div>
    </div>

    <!-- ========== SESI 2: PENJAMINAN MUTU ========== -->
    <div class="ev-panel" id="panel-sesi2">
      <div class="session-header sesi2">
        <h2>🔄 SESI 2 — PENJAMINAN MUTU (SPMI)</h2>
        <div class="subtitle">Sistem Penjaminan Mutu Internal & Eksternal</div>
        <div class="session-info">
          <div class="info-item"><strong>23</strong> Dokumen Evidence</div>
          <div class="info-item"><strong>C.7</strong> Fokus Utama</div>
          <div class="info-item"><strong>PPEPP</strong> Siklus Mutu</div>
        </div>
      </div>

      <!-- Progress -->
      <div class="progress-section">
        <h3>📈 Progress Kesiapan Sesi 2</h3>
        <div class="progress-bar">
          <div class="progress-fill" style="width: 85%; background: linear-gradient(90deg, #388e3c 0%, #4caf50 100%);">85%</div>
        </div>
        <div class="progress-stats">
          <span>20 dari 23 dokumen siap</span>
          <span>3 dokumen perlu update</span>
        </div>
      </div>

      <!-- Checklist -->
      <div class="checklist-section">
        <h3>✅ Checklist Dokumen Sesi 2</h3>
        <div class="checklist-item done"><input type="checkbox" checked><label>SK GPM (Gugus Penjaminan Mutu)</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Dokumen Kebijakan SPMI</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Manual SPMI (PPEPP)</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Dokumen Standar SPMI</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Laporan AMI 2025</label></div>
        <div class="checklist-item"><input type="checkbox"><label>SK Auditor AMI</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Notulensi RTM</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Dokumen RTL AMI (15 temuan)</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Laporan Survei Kepuasan Stakeholder</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Laporan Survei Kepuasan Pengguna Lulusan</label></div>
      </div>

      <!-- Quick Access -->
      <h3 style="color:#2e7d32; margin: 20px 0 12px 0;">⚡ Akses Cepat Dokumen SPMI</h3>
      <div class="quick-grid">
        <div class="quick-card" onclick="filterKategori('spmi-kebijakan')" style="border-left-color: #2e7d32;">
          <div class="qc-icon"></div>
          <div class="qc-name">Kebijakan SPMI</div>
          <div class="qc-desc">Dokumen resmi</div>
        </div>
        <div class="quick-card" onclick="filterKategori('spmi-manual')" style="border-left-color: #2e7d32;">
          <div class="qc-icon">📗</div>
          <div class="qc-name">Manual PPEPP</div>
          <div class="qc-desc">Siklus mutu</div>
        </div>
        <div class="quick-card" onclick="filterKategori('spmi-ami')" style="border-left-color: #2e7d32;">
          <div class="qc-icon"></div>
          <div class="qc-name">AMI 2025</div>
          <div class="qc-desc">Audit Mutu Internal</div>
        </div>
        <div class="quick-card" onclick="filterKategori('spmi-rtm')" style="border-left-color: #2e7d32;">
          <div class="qc-icon">📝</div>
          <div class="qc-name">RTM</div>
          <div class="qc-desc">Rapat Tinjauan Manajemen</div>
        </div>
        <div class="quick-card" onclick="filterKategori('spmi-rtl')" style="border-left-color: #2e7d32;">
          <div class="qc-icon">📋</div>
          <div class="qc-name">RTL</div>
          <div class="qc-desc">Rencana Tindak Lanjut</div>
        </div>
        <div class="quick-card" onclick="filterKategori('spmi-survei')" style="border-left-color: #2e7d32;">
          <div class="qc-icon">⭐</div>
          <div class="qc-name">Survei Kepuasan</div>
          <div class="qc-desc">Stakeholder & Pengguna</div>
        </div>
      </div>

      <!-- Evidence List -->
      <div id="sesi2Content"></div>
    </div>

    <!-- ========== SESI 3: LEDPS ========== -->
    <div class="ev-panel" id="panel-sesi3">
      <div class="session-header sesi3">
        <h2>📕 SESI 3 — LAPORAN EVALUASI DIRI (LEDPS)</h2>
        <div class="subtitle">Analisis, SWOT, dan Program Pengembangan Berkelanjutan</div>
        <div class="session-info">
          <div class="info-item"><strong>35</strong> Dokumen Evidence</div>
          <div class="info-item"><strong>C.1 + BAB III</strong> Fokus Utama</div>
          <div class="info-item"><strong>SWOT</strong> Analisis Strategis</div>
        </div>
      </div>

      <!-- Progress -->
      <div class="progress-section">
        <h3>📈 Progress Kesiapan Sesi 3</h3>
        <div class="progress-bar">
          <div class="progress-fill" style="width: 90%; background: linear-gradient(90deg, #e65100 0%, #f57c00 100%);">90%</div>
        </div>
        <div class="progress-stats">
          <span>32 dari 35 dokumen siap</span>
          <span>3 dokumen dalam finalisasi</span>
        </div>
      </div>

      <!-- Checklist -->
      <div class="checklist-section">
        <h3>✅ Checklist Dokumen Sesi 3</h3>
        <div class="checklist-item done"><input type="checkbox" checked><label>LEDPS Final (Bab 1-7)</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>VMTS PT, JTE, PSBM</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Matriks Sinkronisasi VMTS</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Dokumen SWOT</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Tujuan Strategis</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Program Pengembangan (Tabel 3.2)</label></div>
        <div class="checklist-item"><input type="checkbox"><label>Matriks Traceability</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Renstra & Renop JTE</label></div>
        <div class="checklist-item done"><input type="checkbox" checked><label>Laporan Capaian VMTS</label></div>
      </div>

      <!-- Quick Access -->
      <h3 style="color:#e65100; margin: 20px 0 12px 0;"> Akses Cepat Dokumen LEDPS</h3>
      <div class="quick-grid">
        <div class="quick-card" onclick="filterKategori('led-vmts')" style="border-left-color: #e65100;">
          <div class="qc-icon">🎯</div>
          <div class="qc-name">VMTS</div>
          <div class="qc-desc">Visi Misi Tujuan Sasaran</div>
        </div>
        <div class="quick-card" onclick="filterKategori('led-swot')" style="border-left-color: #e65100;">
          <div class="qc-icon">📊</div>
          <div class="qc-name">SWOT</div>
          <div class="qc-desc">Analisis Strategis</div>
        </div>
        <div class="quick-card" onclick="filterKategori('led-tujuan')" style="border-left-color: #e65100;">
          <div class="qc-icon">🎯</div>
          <div class="qc-name">Tujuan Strategis</div>
          <div class="qc-desc">6 Tujuan Utama</div>
        </div>
        <div class="quick-card" onclick="filterKategori('led-program')" style="border-left-color: #e65100;">
          <div class="qc-icon">📘</div>
          <div class="qc-name">Program Pengembangan</div>
          <div class="qc-desc">Tabel 3.2</div>
        </div>
        <div class="quick-card" onclick="filterKategori('led-renstra')" style="border-left-color: #e65100;">
          <div class="qc-icon">📗</div>
          <div class="qc-name">Renstra/Renop</div>
          <div class="qc-desc">Perencanaan</div>
        </div>
        <div class="quick-card" onclick="filterKategori('led-capstone')" style="border-left-color: #e65100;">
          <div class="qc-icon"></div>
          <div class="qc-name">Capstone Project</div>
          <div class="qc-desc">Evaluasi Pembelajaran</div>
        </div>
      </div>

      <!-- Evidence List -->
      <div id="sesi3Content"></div>
    </div>

  </div>
</div>

<script>
// ===== DATA EVIDENCE PER SESI =====
const dataEvidenceSesi1 = [
  // LKPS Tables - C.1
  { id:'LKPS-001', nama:'Tabel 1 — VMTS dan Profil PS', sesi:'sesi1', kategori:'lkps-table1', jenis:'Tabel LKPS', tahun:'2024', ket:'Data VMTS PT, JTE, PSBM dan profil program studi', sumber:'LKPS Tabel 1', prio:'UTAMA', icon:'', url:'' },
  { id:'LKPS-002', nama:'Tabel 2.a — Kerja Sama Tridharma', sesi:'sesi1', kategori:'lkps-kerja-sama', jenis:'Tabel LKPS', tahun:'2024', ket:'66 kerja sama: 42 pendidikan, 17 penelitian, 7 PkM', sumber:'LKPS Tabel 2.a', prio:'UTAMA', icon:'🤝', url:'' },
  { id:'LKPS-003', nama:'Tabel 2.b — Keuangan', sesi:'sesi1', kategori:'lkps-keuangan', jenis:'Tabel LKPS', tahun:'2024', ket:'BOP, anggaran, realisasi 3 tahun', sumber:'LKPS Tabel 2.b', prio:'UTAMA', icon:'💰', url:'' },
  
  // LKPS Tables - C.3
  { id:'LKPS-004', nama:'Tabel 3.a.1 — Kurikulum', sesi:'sesi1', kategori:'lkps-kurikulum', jenis:'Tabel LKPS', tahun:'2024', ket:'53 MK, 150 SKS, 80 SKS praktik (53,33%)', sumber:'LKPS Tabel 3.a.1', prio:'UTAMA', icon:'', url:'' },
  { id:'LKPS-005', nama:'Tabel 3.b — Penelitian', sesi:'sesi1', kategori:'lkps-penelitian', jenis:'Tabel LKPS', tahun:'2024', ket:'45 penelitian: 14, 13, 18 (3 tahun)', sumber:'LKPS Tabel 3.b', prio:'UTAMA', icon:'🔬', url:'' },
  { id:'LKPS-006', nama:'Tabel 3.c — PkM', sesi:'sesi1', kategori:'lkps-pkm', jenis:'Tabel LKPS', tahun:'2024', ket:'14 PkM: 2, 6, 6 (3 tahun)', sumber:'LKPS Tabel 3.c', prio:'UTAMA', icon:'', url:'' },
  
  // LKPS Tables - C.4
  { id:'LKPS-007', nama:'Tabel 4.a — DTPS', sesi:'sesi1', kategori:'lkps-sdm', jenis:'Tabel LKPS', tahun:'2024', ket:'11 DTPS: 3 doktor, 4 LK, 6 Lektor', sumber:'LKPS Tabel 4.a', prio:'UTAMA', icon:'👨‍🏫', url:'' },
  { id:'LKPS-008', nama:'Tabel 4.e — Publikasi', sesi:'sesi1', kategori:'lkps-sdm', jenis:'Tabel LKPS', tahun:'2024', ket:'220 publikasi 3 tahun', sumber:'LKPS Tabel 4.e', prio:'UTAMA', icon:'📚', url:'' },
  
  // LKPS Tables - C.5
  { id:'LKPS-009', nama:'Tabel 5.a — Sarpras', sesi:'sesi1', kategori:'lkps-sarpras', jenis:'Tabel LKPS', tahun:'2024', ket:'Laboratorium, peralatan, K3L', sumber:'LKPS Tabel 5.a', prio:'UTAMA', icon:'', url:'' },
  
  // LKPS Tables - C.6
  { id:'LKPS-010', nama:'Tabel 6.a — Mahasiswa', sesi:'sesi1', kategori:'lkps-mahasiswa', jenis:'Tabel LKPS', tahun:'2024', ket:'Rasio mhs:DTPS 18:1', sumber:'LKPS Tabel 6.a', prio:'UTAMA', icon:'🎓', url:'' },
  { id:'LKPS-011', nama:'Tabel 6.f — Tracer Study', sesi:'sesi1', kategori:'lkps-tracer', jenis:'Tabel LKPS', tahun:'2024', ket:'80 lulusan, 61 terlacak (76,25%)', sumber:'LKPS Tabel 6.f', prio:'UTAMA', icon:'📈', url:'' },
  { id:'LKPS-012', nama:'Tabel 6.g — Kepuasan Pengguna', sesi:'sesi1', kategori:'lkps-mahasiswa', jenis:'Tabel LKPS', tahun:'2024', ket:'45 responden, 7 aspek', sumber:'LKPS Tabel 6.g', prio:'UTAMA', icon:'⭐', url:'' }
];

const dataEvidenceSesi2 = [
  // SPMI - C.7
  { id:'SPMI-001', nama:'SK GPM JTE', sesi:'sesi2', kategori:'spmi-kebijakan', jenis:'SK', tahun:'2023', ket:'SK Gugus Penjaminan Mutu', sumber:'LED C.7', prio:'UTAMA', icon:'', url:'' },
  { id:'SPMI-002', nama:'Dokumen Kebijakan SPMI', sesi:'sesi2', kategori:'spmi-kebijakan', jenis:'Dokumen', tahun:'2023', ket:'Kebijakan SPMI resmi', sumber:'LED C.7', prio:'UTAMA', icon:'📘', url:'' },
  { id:'SPMI-003', nama:'Manual SPMI (PPEPP)', sesi:'sesi2', kategori:'spmi-manual', jenis:'Manual', tahun:'2023', ket:'Manual siklus PPEPP', sumber:'LED C.7', prio:'UTAMA', icon:'📗', url:'' },
  { id:'SPMI-004', nama:'Dokumen Standar SPMI', sesi:'sesi2', kategori:'spmi-kebijakan', jenis:'Dokumen', tahun:'2023', ket:'Standar mutu SPMI', sumber:'LED C.7', prio:'UTAMA', icon:'📘', url:'' },
  { id:'SPMI-005', nama:'Laporan AMI 2025', sesi:'sesi2', kategori:'spmi-ami', jenis:'Laporan', tahun:'2025', ket:'Laporan Audit Mutu Internal', sumber:'LED C.7', prio:'UTAMA', icon:'🔍', url:'' },
  { id:'SPMI-006', nama:'SK Auditor AMI', sesi:'sesi2', kategori:'spmi-ami', jenis:'SK', tahun:'2025', ket:'SK auditor AMI independen', sumber:'LED C.7', prio:'UTAMA', icon:'📜', url:'' },
  { id:'SPMI-007', nama:'Notulensi RTM', sesi:'sesi2', kategori:'spmi-rtm', jenis:'Notulensi', tahun:'2025', ket:'Rapat Tinjauan Manajemen', sumber:'LED C.7', prio:'UTAMA', icon:'📝', url:'' },
  { id:'SPMI-008', nama:'Dokumen RTL AMI', sesi:'sesi2', kategori:'spmi-rtl', jenis:'Dokumen', tahun:'2025', ket:'Rencana Tindak Lanjut 15 temuan', sumber:'LED C.7', prio:'UTAMA', icon:'📋', url:'' },
  { id:'SPMI-009', nama:'Laporan Survei Kepuasan Stakeholder', sesi:'sesi2', kategori:'spmi-survei', jenis:'Laporan', tahun:'2024', ket:'Survei mahasiswa, dosen, lulusan, pengguna', sumber:'LED C.7', prio:'UTAMA', icon:'⭐', url:'' },
  { id:'SPMI-010', nama:'Laporan Survei Kepuasan Pengguna Lulusan', sesi:'sesi2', kategori:'spmi-survei', jenis:'Laporan', tahun:'2024', ket:'45 responden, 7 aspek kepuasan', sumber:'LED C.6', prio:'UTAMA', icon:'⭐', url:'' }
];

const dataEvidenceSesi3 = [
  // LEDPS - C.1 & BAB III
  { id:'LED-001', nama:'LEDPS Final (Bab 1-7)', sesi:'sesi3', kategori:'led-vmts', jenis:'Laporan', tahun:'2026', ket:'Laporan Evaluasi Diri Program Studi lengkap', sumber:'LEDPS', prio:'UTAMA', icon:'📕', url:'' },
  { id:'LED-002', nama:'SK VMTS PT', sesi:'sesi3', kategori:'led-vmts', jenis:'SK', tahun:'2020', ket:'SK VMTS tingkat Politeknik Negeri Jakarta', sumber:'LED C.1', prio:'UTAMA', icon:'📜', url:'' },
  { id:'LED-003', nama:'SK VMTS UPPS (JTE)', sesi:'sesi3', kategori:'led-vmts', jenis:'SK', tahun:'2020', ket:'SK VMTS tingkat Jurusan/UPPS', sumber:'LED C.1', prio:'UTAMA', icon:'📜', url:'' },
  { id:'LED-004', nama:'Dokumen Visi Keilmuan PSBM', sesi:'sesi3', kategori:'led-vmts', jenis:'Dokumen', tahun:'2020', ket:'Visi keilmuan Broadband Multimedia', sumber:'LED C.1', prio:'UTAMA', icon:'📘', url:'' },
  { id:'LED-005', nama:'Matriks Sinkronisasi VMTS', sesi:'sesi3', kategori:'led-vmts', jenis:'Matriks', tahun:'2024', ket:'Linearitas visi PT → JTE → PSBM', sumber:'LED C.1', prio:'UTAMA', icon:'📊', url:'' },
  { id:'LED-006', nama:'Dokumen SWOT', sesi:'sesi3', kategori:'led-swot', jenis:'Dokumen', tahun:'2024', ket:'Analisis SWOT PSBM', sumber:'BAB III', prio:'UTAMA', icon:'📊', url:'' },
  { id:'LED-007', nama:'Tujuan Strategis', sesi:'sesi3', kategori:'led-tujuan', jenis:'Dokumen', tahun:'2024', ket:'6 tujuan strategis PSBM', sumber:'BAB III', prio:'UTAMA', icon:'🎯', url:'' },
  { id:'LED-008', nama:'Program Pengembangan (Tabel 3.2)', sesi:'sesi3', kategori:'led-program', jenis:'Tabel', tahun:'2024', ket:'6 program pengembangan dengan PIC dan anggaran', sumber:'BAB III', prio:'UTAMA', icon:'📘', url:'' },
  { id:'LED-009', nama:'Matriks Traceability', sesi:'sesi3', kategori:'led-program', jenis:'Matriks', tahun:'2024', ket:'Keterlacakan temuan → SWOT → program', sumber:'BAB III', prio:'UTAMA', icon:'', url:'' },
  { id:'LED-010', nama:'Renstra & Renop JTE', sesi:'sesi3', kategori:'led-renstra', jenis:'Dokumen', tahun:'2020-2025', ket:'Target dan capaian VMTS', sumber:'LED C.1', prio:'UTAMA', icon:'', url:'' },
  { id:'LED-011', nama:'Laporan Capaian VMTS', sesi:'sesi3', kategori:'led-renstra', jenis:'Laporan', tahun:'2024', ket:'Realisasi vs target VMTS', sumber:'LED C.1', prio:'UTAMA', icon:'📊', url:'' },
  { id:'LED-012', nama:'Panduan Capstone Project', sesi:'sesi3', kategori:'led-capstone', jenis:'Panduan', tahun:'2024', ket:'Panduan resmi capstone project', sumber:'LED C.3', prio:'UTAMA', icon:'📗', url:'' }
];

// ===== NAVIGATION =====
function showEvPanel(id, btn) {
  document.querySelectorAll('.ev-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.ev-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  
  if (id === 'sesi1') renderSesi1();
  if (id === 'sesi2') renderSesi2();
  if (id === 'sesi3') renderSesi3();
}

// ===== RENDER SESI 1 =====
function renderSesi1() {
  let html = '<h3 style="color:#0d47a1; margin: 20px 0 12px 0;">📊 Dokumen Evidence Sesi 1 — LKPS</h3>';
  dataEvidenceSesi1.forEach(e => { html += renderEvCard(e); });
  document.getElementById('sesi1Content').innerHTML = html;
}

// ===== RENDER SESI 2 =====
function renderSesi2() {
  let html = '<h3 style="color:#2e7d32; margin: 20px 0 12px 0;">🔄 Dokumen Evidence Sesi 2 — Penjaminan Mutu</h3>';
  dataEvidenceSesi2.forEach(e => { html += renderEvCard(e); });
  document.getElementById('sesi2Content').innerHTML = html;
}

// ===== RENDER SESI 3 =====
function renderSesi3() {
  let html = '<h3 style="color:#e65100; margin: 20px 0 12px 0;">📕 Dokumen Evidence Sesi 3 — LEDPS</h3>';
  dataEvidenceSesi3.forEach(e => { html += renderEvCard(e); });
  document.getElementById('sesi3Content').innerHTML = html;
}

// ===== RENDER CARD =====
function renderEvCard(e) {
  const prioClass = e.prio === 'UTAMA' ? 'utama' : 'pendukung';
  const hasUrl = e.url && e.url.trim() !== '';
  const btnHtml = hasUrl 
    ? '<a href="' + e.url + '" target="_blank" class="ev-open-btn">📂 BUKA DOKUMEN</a>'
    : '<button class="ev-open-btn" disabled title="Link belum tersedia">📂 BUKA DOKUMEN</button>';
  
  let html = '<div class="ev-card ' + prioClass + '">';
  html += '<div class="ev-card-icon">' + e.icon + '</div>';
  html += '<div class="ev-card-body">';
  html += '<div class="ev-card-title">' + e.nama + '</div>';
  html += '<div class="ev-card-desc">' + e.ket + '</div>';
  html += '<div class="ev-card-meta">';
  html += '<span class="ev-badge ' + prioClass + '">' + e.prio + '</span>';
  html += '<span class="ev-badge jenis">' + e.jenis + '</span>';
  html += '<span class="ev-badge tahun">' + e.tahun + '</span>';
  html += '<span class="ev-badge sumber">📖 ' + e.sumber + '</span>';
  html += '</div>';
  html += '<div class="ev-card-actions">';
  html += btnHtml;
  html += '<button class="ev-open-btn secondary" onclick="showSourceInfo(\'' + e.id + '\')"> Referensi</button>';
  html += '</div></div></div>';
  return html;
}

// ===== SHOW SOURCE INFO =====
function showSourceInfo(id) {
  const allData = [...dataEvidenceSesi1, ...dataEvidenceSesi2, ...dataEvidenceSesi3];
  const e = allData.find(x => x.id === id);
  if (!e) return;
  alert(
    `📚 REFERENSI DOKUMEN\n\n` +
    `📄 Dokumen: ${e.nama}\n` +
    `📁 Kategori: ${e.kategori}\n` +
    `📚 Sumber: ${e.sumber}\n` +
    `📅 Tahun: ${e.tahun}\n\n` +
    ` Pastikan dokumen sudah diunggah ke Google Drive.`
  );
}

// ===== FILTER KATEGORI =====
function filterKategori(kategori) {
  alert(`Filter kategori: ${kategori}\n\nFitur ini akan menampilkan dokumen dengan kategori "${kategori}".\n\nImplementasi: tambahkan filter berdasarkan properti 'kategori' di data evidence.`);
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  renderSesi1();
  renderSesi2();
  renderSesi3();
});
</script>

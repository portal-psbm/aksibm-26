---
layout: default
title: Evidence AL
permalink: /evidence-al/
---

<style>
/* ===== CABINET & TABS ===== */
.ev-cabinet { 
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%); 
  padding: 20px 20px 0 20px; 
  border-radius: 16px 16px 0 0; 
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08); 
  position: relative; 
  border: 1px solid #e2e8f0; 
  border-bottom: none; 
}
.ev-shelf { 
  display: flex; 
  flex-wrap: nowrap; 
  gap: 8px; 
  padding: 0 8px; 
  position: relative; 
  z-index: 10; 
  overflow-x: auto; 
  overflow-y: visible; 
  scrollbar-width: thin; 
  scrollbar-color: rgba(13, 71, 161, 0.3) transparent; 
  padding-bottom: 8px; 
}
.ev-shelf::-webkit-scrollbar { height: 4px; }
.ev-shelf::-webkit-scrollbar-track { background: rgba(13, 71, 161, 0.05); border-radius: 2px; }
.ev-shelf::-webkit-scrollbar-thumb { background: rgba(13, 71, 161, 0.3); border-radius: 2px; }

.ev-tab { 
  position: relative; 
  flex: 1 1 0; 
  min-width: 0; 
  padding: 14px 8px 18px 8px; 
  background: white; 
  border-radius: 10px 10px 0 0; 
  border: 1px solid #e2e8f0; 
  border-bottom: none; 
  cursor: pointer; 
  text-align: center; 
  font-weight: 600; 
  font-size: 0.78rem; 
  line-height: 1.2; 
  color: #64748b; 
  transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1); 
  transform: translateY(4px); 
  box-shadow: 0 -2px 6px rgba(0,0,0,0.05); 
  white-space: normal; 
  word-wrap: break-word; 
  overflow-wrap: break-word; 
}
.ev-tab::before { 
  content: ''; 
  position: absolute; 
  top: -6px; 
  left: 22%; 
  width: 56%; 
  height: 6px; 
  background: #f1f5f9; 
  border-radius: 4px 4px 0 0; 
  border: 1px solid #e2e8f0; 
  border-bottom: none; 
  transition: all 0.35s ease; 
}
.ev-tab:hover { 
  background: #f8fafc; 
  transform: translateY(0px); 
  color: #0d47a1; 
}
.ev-tab:hover::before { 
  background: #e2e8f0; 
}
.ev-tab.active { 
  background: #ffffff; 
  color: #0d47a1; 
  transform: translateY(-6px); 
  z-index: 20; 
  border-color: #0d47a1; 
  box-shadow: 0 -4px 16px rgba(13, 71, 161, 0.15); 
  font-weight: 700; 
}
.ev-tab.active::before { 
  background: #0d47a1; 
  border-color: #0d47a1; 
  height: 8px; 
  top: -8px; 
}

/* SESI 2 - BIRU MUDA */
.ev-tab.sesi2.active { 
  color: #0288d1; 
  border-color: #0288d1; 
  box-shadow: 0 -4px 16px rgba(2, 136, 209, 0.15); 
}
.ev-tab.sesi2.active::before { 
  background: #0288d1; 
  border-color: #0288d1; 
}
.ev-tab .tab-emoji { font-size: 1.2rem; display: block; margin-bottom: 4px; }
.ev-tab .tab-label { font-size: 0.72rem; opacity: 0.9; }

.ev-content { 
  background: #ffffff; 
  border: 1px solid #e0e0e0; 
  border-top: 3px solid #0d47a1; 
  border-radius: 0 0 16px 16px; 
  padding: 24px; 
  min-height: 500px; 
  box-shadow: 0 8px 24px rgba(0,0,0,0.06); 
  position: relative; 
  z-index: 5; 
  margin-top: -1px; 
}
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

.session-header { padding: 20px; border-radius: 12px; margin-bottom: 16px; color: white; }
.session-header.sesi1 { background: linear-gradient(135deg, #1565c0 0%, #0d47a1 100%); }
.session-header.sesi2 { background: linear-gradient(135deg, #29b6f6 0%, #0288d1 100%); }
.session-header h2 { margin: 0 0 6px 0; font-size: 1.3rem; }
.session-header .subtitle { opacity: 0.95; font-size: 0.88rem; margin-bottom: 10px; }
.session-header .tag { display: inline-block; background: rgba(255,255,255,0.25); padding: 4px 12px; border-radius: 12px; font-size: 0.72rem; font-weight: 700; margin-bottom: 8px; letter-spacing: 0.5px; }

/* ===== SUB-NAV ===== */
.criteria-nav { display: flex; gap: 6px; margin-bottom: 16px; flex-wrap: wrap; padding: 8px; background: #f8fafc; border-radius: 10px; border: 1px solid #e2e8f0; }
.criteria-nav button { 
  padding: 8px 12px; 
  background: white; 
  border: 1.5px solid #e2e8f0; 
  border-radius: 8px; 
  cursor: pointer; 
  font-weight: 600; 
  color: #64748b; 
  font-size: 0.75rem; 
  transition: all 0.2s; 
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2px;
}
.criteria-nav button small { font-size: 0.65rem; opacity: 0.7; }
.criteria-nav button:hover { border-color: #0d47a1; color: #0d47a1; transform: translateY(-1px); }
.criteria-nav button.active { background: #0d47a1; color: white; border-color: #0d47a1; box-shadow: 0 2px 6px rgba(13, 71, 161, 0.2); }
.criteria-nav button.active small { opacity: 0.9; }

.criteria-nav.ledps-nav button.active { background: #0288d1; border-color: #0288d1; box-shadow: 0 2px 6px rgba(2, 136, 209, 0.2); }
.criteria-nav.ledps-nav button.bab3-btn.active { background: #e65100; border-color: #e65100; }

.lkps-table-panel { display: none; animation: fadeIn 0.3s ease; }
.lkps-table-panel.active { display: block; }
.ledps-criteria { display: none; animation: fadeIn 0.3s ease; }
.ledps-criteria.active { display: block; }

.lkps-section { margin-bottom: 20px; }
.lkps-section h3 { color: #0d47a1; border-left: 4px solid #0d47a1; padding-left: 10px; margin: 0 0 12px 0; font-size: 1rem; }
.lkps-section.ledps h3 { color: #0288d1; border-left-color: #0288d1; }

.table-responsive { overflow-x: auto; border: 1px solid #e0e0e0; border-radius: 8px; margin-bottom: 12px; }
.lkps-table { width: 100%; border-collapse: collapse; font-size: 0.8rem; min-width: 600px; }
.lkps-table th, .lkps-table td { border: 1px solid #e0e0e0; padding: 8px 10px; text-align: left; vertical-align: top; }
.lkps-table th { background-color: #f1f5f9; font-weight: 600; color: #0d47a1; position: sticky; top: 0; z-index: 1; }
.lkps-table tr:nth-child(even) { background-color: #f8fafc; }
.lkps-table tr:hover { background-color: #e3f2fd; }
.highlight-data { background-color: #fff8e1 !important; font-weight: 600; color: #e65100; }

.summary-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 8px; margin: 12px 0; }
.summary-card { background: white; border: 1px solid #e0e0e0; border-left: 4px solid #0d47a1; border-radius: 6px; padding: 10px; transition: all 0.2s; }
.summary-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); transform: translateY(-2px); }
.summary-card .sc-label { font-size: 0.68rem; color: #666; text-transform: uppercase; letter-spacing: 0.5px; }
.summary-card .sc-value { font-size: 1.2rem; font-weight: 800; color: #0d47a1; margin: 2px 0; }
.summary-card .sc-desc { font-size: 0.72rem; color: #555; }

.info-box { background: #e3f2fd; border-left: 4px solid #0d47a1; padding: 10px 14px; border-radius: 6px; margin-bottom: 16px; font-size: 0.82rem; color: #0d47a1; }
.info-box.ledps { background: #e1f5fe; border-left-color: #0288d1; color: #01579b; }
.info-box strong { color: inherit; filter: brightness(0.7); }

.led-card { background: white; border: 1px solid #e0e0e0; border-radius: 8px; padding: 12px; margin-bottom: 10px; border-left: 4px solid #0288d1; }
.led-card h4 { color: #0288d1; margin: 0 0 6px 0; font-size: 0.88rem; }
.led-card p { color: #555; font-size: 0.82rem; line-height: 1.5; margin: 0 0 6px 0; }
.led-card ul { margin: 6px 0; padding-left: 18px; font-size: 0.8rem; color: #555; }
.led-card li { margin-bottom: 3px; line-height: 1.4; }

.swot-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin: 12px 0; }
.swot-card { padding: 12px; border-radius: 8px; border: 2px solid; }
.swot-card.strength { background: #e8f5e9; border-color: #4caf50; }
.swot-card.weakness { background: #fff3e0; border-color: #ff9800; }
.swot-card.opportunity { background: #e3f2fd; border-color: #2196f3; }
.swot-card.threat { background: #ffebee; border-color: #f44336; }
.swot-card h4 { margin: 0 0 6px 0; font-size: 0.88rem; }
.swot-card ul { margin: 0; padding-left: 16px; font-size: 0.78rem; }
.swot-card ul li { padding: 1px 0; }

/* ===== TABLE LINK BUTTON (FLEXBOX ALIGNMENT) ===== */
.table-link-container {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-top: 12px;
}
.table-link-btn { 
  display: inline-flex; 
  align-items: center; 
  gap: 6px; 
  padding: 8px 12px; 
  background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); 
  color: white; 
  border-radius: 6px; 
  text-decoration: none; 
  font-weight: 600; 
  font-size: 0.75rem; 
  transition: all 0.2s; 
  box-shadow: 0 2px 6px rgba(13, 71, 161, 0.2); 
}
.table-link-btn:hover { 
  background: linear-gradient(135deg, #1565c0 0%, #1976d2 100%); 
  transform: translateY(-1px); 
  box-shadow: 0 4px 10px rgba(13, 71, 161, 0.3); 
}
.table-link-btn.secondary { background: linear-gradient(135deg, #455a64 0%, #546e7a 100%); box-shadow: 0 2px 6px rgba(69, 90, 100, 0.2); }
.table-link-btn.secondary:hover { background: linear-gradient(135deg, #546e7a 0%, #607d8b 100%); }
.table-link-btn.success { background: linear-gradient(135deg, #0288d1 0%, #29b6f6 100%); box-shadow: 0 2px 6px rgba(2, 136, 209, 0.2); }
.table-link-btn.success:hover { background: linear-gradient(135deg, #29b6f6 0%, #4fc3f7 100%); }
.table-link-btn .btn-icon { font-size: 0.9rem; }

@media (max-width: 767px) {
  .ev-shelf { gap: 4px; padding-bottom: 6px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
  .ev-shelf::-webkit-scrollbar { display: none; }
  .ev-tab { min-width: 90px; flex: 0 0 auto; font-size: 0.72rem; padding: 10px 6px 14px 6px; }
  .ev-content { padding: 16px; }
  .summary-grid { grid-template-columns: 1fr 1fr; }
  .swot-grid { grid-template-columns: 1fr; }
  .criteria-nav { gap: 4px; padding: 6px; }
  .criteria-nav button { padding: 6px 8px; font-size: 0.7rem; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('sesi1', this)">
      <span class="tab-emoji">📊</span>
      <span class="tab-label">SESI 1: LKPS</span>
    </div>
    <div class="ev-tab sesi2" onclick="showEvPanel('sesi2', this)">
      <span class="tab-emoji">📘</span>
      <span class="tab-label">SESI 2: LEDPS</span>
    </div>
  </div>

  <div class="ev-content">

    <!-- ========== SESI 1: LKPS ========== -->
    <div class="ev-panel active" id="panel-sesi1">
      <div class="session-header sesi1">
        <span class="tag">DATA KUANTITATIF — 50+ TABEL LKPS</span>
        <h2>📊 SESI 1 — LAPORAN KINERJA PROGRAM STUDI (LKPS)</h2>
        <div class="subtitle">Semua tabel LKPS PSBM dengan link bukti Google Drive</div>
      </div>

      <div class="info-box">
        <strong>ℹ️ Informasi:</strong> Halaman ini menampilkan <strong>50+ tabel LKPS</strong> dengan link bukti Google Drive. Klik tombol "📂 Buka Bukti" untuk mengakses dokumen asli.
      </div>

      <!-- Sub-nav Kriteria -->
      <div class="criteria-nav" id="lkpsNav">
        <button class="active" onclick="showLkpsTable('t1', this)"><span>📑</span><span>T1</span><small>VMTS</small></button>
        <button onclick="showLkpsTable('t2', this)"><span>🤝</span><span>T2</span><small>Kerja Sama</small></button>
        <button onclick="showLkpsTable('t3', this)"><span>📘</span><span>T3</span><small>Kurikulum</small></button>
        <button onclick="showLkpsTable('t4', this)"><span>👨‍🏫</span><span>T4</span><small>SDM</small></button>
        <button onclick="showLkpsTable('t5', this)"><span>💰</span><span>T5</span><small>Sarpras</small></button>
        <button onclick="showLkpsTable('t6', this)"><span>🎓</span><span>T6</span><small>Luaran</small></button>
        <button onclick="showLkpsTable('t7', this)"><span>🔄</span><span>T7</span><small>SPMI</small></button>
      </div>

      <!-- TABEL 1: VMTS -->
      <div class="lkps-table-panel active" id="lkps-t1">
        <div class="lkps-section">
          <h3>📑 Tabel 1: VMTS PT, UPPS, dan Visi Keilmuan Program Studi</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>No</th><th>Jenis VMTS</th><th>Pernyataan</th><th>No. SK</th></tr></thead>
              <tbody>
                <tr><td>1</td><td><strong>VMTS PT</strong></td><td>Visi: Menjadi politeknik unggul bertaraf internasional</td><td>643/PL3/OT/2021</td></tr>
                <tr><td>2</td><td><strong>VMTS UPPS (JTE)</strong></td><td>Visi: Menjadi Jurusan Teknik Elektro unggul bertaraf internasional</td><td>2585/PL3/OT/2020</td></tr>
                <tr><td>3</td><td><strong>Visi Keilmuan PS</strong></td><td>Unggul bertaraf internasional di bidang broadband multimedia</td><td>2589/PL3/KR.00/2020</td></tr>
              </tbody>
            </table>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📄</span> Buka Bukti: VMTS PT</a>
            <a href="https://drive.google.com/drive/folders/1JiRWv_v_-pbrFTMl74JwQzJ1ZNnCpcOt" target="_blank" class="table-link-btn"><span class="btn-icon">📄</span> Buka Bukti: VMTS UPPS</a>
            <a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf" target="_blank" class="table-link-btn"><span class="btn-icon">📘</span> Buka Bukti: Visi Keilmuan PS</a>
          </div>
        </div>
      </div>

      <!-- TABEL 2: KERJA SAMA & DANA -->
      <div class="lkps-table-panel" id="lkps-t2">
        <div class="lkps-section">
          <h3>🤝 Tabel 2a1: Kerja Sama Tridharma - Pendidikan</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">5</div></div>
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">37</div></div>
            <div class="summary-card"><div class="sc-label">Total</div><div class="sc-value">42</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🤝</span> Buka Bukti: Kerja Sama Pendidikan</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🔬 Tabel 2a2: Kerja Sama Tridharma - Penelitian</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">16</div></div>
            <div class="summary-card"><div class="sc-label">Total</div><div class="sc-value">17</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🔬</span> Buka Bukti: Kerja Sama Penelitian</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🤝 Tabel 2a3: Kerja Sama Tridharma - PkM</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Lokal/Wilayah</div><div class="sc-value">6</div></div>
            <div class="summary-card"><div class="sc-label">Total</div><div class="sc-value">7</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🤝</span> Buka Bukti: Kerja Sama PkM</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>💰 Tabel 2b: Penggunaan Dana</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>Jenis</th><th>UPPS Rata-rata</th><th>PS Rata-rata</th></tr></thead>
              <tbody>
                <tr><td>Operasional + Kemahasiswaan</td><td>25,83 M</td><td>3,84 M</td></tr>
                <tr><td>Penelitian</td><td>1,06 M</td><td>0,14 M</td></tr>
                <tr><td>PkM</td><td>0,35 M</td><td>0,08 M</td></tr>
                <tr class="highlight-data"><td><strong>TOTAL</strong></td><td><strong>27,24 M</strong></td><td><strong>4,08 M</strong></td></tr>
              </tbody>
            </table>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">💰</span> Buka Bukti: Penggunaan Dana</a>
          </div>
        </div>
      </div>

      <!-- TABEL 3: KURIKULUM & TRIDHARMA -->
      <div class="lkps-table-panel" id="lkps-t3">
        <div class="lkps-section">
          <h3>📘 Tabel 3a1: Kurikulum dan Rencana Pembelajaran</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total MK</div><div class="sc-value">53</div></div>
            <div class="summary-card"><div class="sc-label">Total SKS</div><div class="sc-value">150</div></div>
            <div class="summary-card"><div class="sc-label">SKS Praktik</div><div class="sc-value">80 (53,33%)</div></div>
            <div class="summary-card"><div class="sc-label">SKS Kuliah</div><div class="sc-value">68</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📘</span> Buka Bukti: Kurikulum</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>📘 Tabel 3a2: Mata Kuliah dan Dokumen Pembelajaran</h3>
          <div class="info-box"><strong>📌 Ringkasan:</strong> 100% MK memiliki RPS dengan 9 komponen lengkap.</div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📝</span> Buka Bukti: RPS</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🔬 Tabel 3b: Penelitian DTPS</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">14</div></div>
            <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">13</div></div>
            <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">18</div></div>
            <div class="summary-card"><div class="sc-label">Total</div><div class="sc-value">45</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🔬</span> Buka Bukti: Penelitian DTPS</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🤝 Tabel 3c: PkM DTPS</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">6</div></div>
            <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">6</div></div>
            <div class="summary-card"><div class="sc-label">Total</div><div class="sc-value">14</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🤝</span> Buka Bukti: PkM DTPS</a>
          </div>
        </div>
      </div>

      <!-- TABEL 4: SDM & LUARAN -->
      <div class="lkps-table-panel" id="lkps-t4">
        <div class="lkps-section">
          <h3>👨‍🏫 Tabel 4a: Profil Dosen (DTPS)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total DTPS</div><div class="sc-value">11</div></div>
            <div class="summary-card"><div class="sc-label">Doktor</div><div class="sc-value">3 (27,27%)</div></div>
            <div class="summary-card"><div class="sc-label">Lektor Kepala</div><div class="sc-value">4 (36,36%)</div></div>
            <div class="summary-card"><div class="sc-label">Lektor</div><div class="sc-value">6</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">👨‍🏫</span> Buka Bukti: Profil DTPS</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>📚 Tabel 4e: Publikasi Ilmiah DTPS</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Jurnal Nasional</div><div class="sc-value">73</div></div>
            <div class="summary-card"><div class="sc-label">Jurnal Internasional</div><div class="sc-value">12</div></div>
            <div class="summary-card"><div class="sc-label">Prosiding</div><div class="sc-value">125</div></div>
            <div class="summary-card"><div class="sc-label">Total</div><div class="sc-value">220</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📚</span> Buka Bukti: Publikasi DTPS</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>📦 Tabel 4g: Produk/Jasa DTPS Diadopsi</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total Produk</div><div class="sc-value">13</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z" target="_blank" class="table-link-btn"><span class="btn-icon">📦</span> Buka Bukti: Produk Diadopsi</a>
          </div>
        </div>
      </div>

      <!-- TABEL 5: SARPRAS & K3L -->
      <div class="lkps-table-panel" id="lkps-t5">
        <div class="lkps-section">
          <h3>💰 Tabel 5a: Prasarana dan Peralatan Utama</h3>
          <div class="info-box"><strong>📌 Ringkasan:</strong> 16 prasarana utama (13 lab/ruang + 3 layanan nonakademik). Seluruhnya terawat, dimiliki sendiri.</div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">💰</span> Buka Bukti: Sarpras</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>⚠️ Tabel 5b: Dokumen K3L</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total Dokumen</div><div class="sc-value">17</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">⚠️</span> Buka Bukti: Dokumen K3L</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🧯 Tabel 5c: Fasilitas K3L</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">APAR</div><div class="sc-value">6</div></div>
            <div class="summary-card"><div class="sc-label">Hidran</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">Ambulance</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">P3K</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">Rambu K3</div><div class="sc-value">7</div></div>
            <div class="summary-card"><div class="sc-label">Jalur Evakuasi</div><div class="sc-value">22</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🧯</span> Buka Bukti: Fasilitas K3L</a>
          </div>
        </div>
      </div>

      <!-- TABEL 6: MAHASISWA & LUARAN -->
      <div class="lkps-table-panel" id="lkps-t6">
        <div class="lkps-section">
          <h3>🎓 Tabel 6a: Jumlah Mahasiswa</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">192</div></div>
            <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">182</div></div>
            <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">189</div></div>
            <div class="summary-card"><div class="sc-label">Mhs Asing PT</div><div class="sc-value">12</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🎓</span> Buka Bukti: Mahasiswa</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🎓 Tabel 6b: IPK Lulusan</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>Tahun Lulus</th><th>Jumlah</th><th>Min</th><th>Rata-rata</th><th>Maks</th></tr></thead>
              <tbody>
                <tr><td>TS-2</td><td>44</td><td>2.66</td><td class="highlight-data">3.49</td><td>3.76</td></tr>
                <tr><td>TS-1</td><td>36</td><td>3.18</td><td class="highlight-data">3.45</td><td>3.73</td></tr>
                <tr><td>TS</td><td>44</td><td>2.78</td><td class="highlight-data">3.43</td><td>3.82</td></tr>
              </tbody>
            </table>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🎓</span> Buka Bukti: IPK Lulusan</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🏆 Tabel 6c: Prestasi Mahasiswa</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Akademik</div><div class="sc-value">10</div></div>
            <div class="summary-card"><div class="sc-label">Non-Akademik</div><div class="sc-value">9</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🏆</span> Buka Bukti: Prestasi</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>📚 Tabel 6e: Luaran Mahasiswa</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Publikasi</div><div class="sc-value">126</div></div>
            <div class="summary-card"><div class="sc-label">HKI</div><div class="sc-value">16</div></div>
            <div class="summary-card"><div class="sc-label">TTG</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Buku</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">Produk Diadopsi</div><div class="sc-value">16</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📚</span> Buka Bukti: Publikasi Mhs</a>
            <a href="https://drive.google.com/drive/folders/1gj3fyC_mO2c6pDTNRzhnlPcIE4_pKBYS" target="_blank" class="table-link-btn success"><span class="btn-icon">📦</span> Buka Bukti: Produk Mhs</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>📈 Tabel 6f & 6g: Tracer Study & Kepuasan</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Terlacak</div><div class="sc-value">76,25%</div></div>
            <div class="summary-card"><div class="sc-label">WT < 3 bln</div><div class="sc-value">55,74%</div></div>
            <div class="summary-card"><div class="sc-label">Sesuai Bidang</div><div class="sc-value">70,49%</div></div>
            <div class="summary-card"><div class="sc-label">Nasional+</div><div class="sc-value">80,33%</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📈</span> Buka Bukti: Tracer Study</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn secondary"><span class="btn-icon">⭐</span> Buka Bukti: Kepuasan Pengguna</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🔬 Tabel 6h & 6i: Keterlibatan Mahasiswa</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Penelitian</div><div class="sc-value">12</div></div>
            <div class="summary-card"><div class="sc-label">PkM</div><div class="sc-value">7</div></div>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🔬</span> Buka Bukti: Penelitian Mhs</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn secondary"><span class="btn-icon">🤝</span> Buka Bukti: PkM Mhs</a>
          </div>
        </div>
      </div>

      <!-- TABEL 7: SPMI -->
      <div class="lkps-table-panel" id="lkps-t7">
        <div class="lkps-section">
          <h3>🔄 Tabel 7a: Dokumen SPMI</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>No</th><th>Jenis Dokumen</th><th>No Dokumen</th><th>Tanggal</th></tr></thead>
              <tbody>
                <tr><td>1</td><td>Kebijakan SPMI</td><td>SM/PNJ/SPMI/342</td><td>18/1/2022</td></tr>
                <tr><td>2</td><td>Pedoman PPEPP</td><td>KM/PNJ/SPMI/212</td><td>18/1/2022</td></tr>
                <tr><td>3</td><td>Standar Mutu</td><td>SM/PNJ/SPMI/311</td><td>20/1/2022</td></tr>
                <tr><td>4</td><td>Tata Cara Pendokumentasian</td><td>KM/PNJ/SPMI/215</td><td>20/1/2022</td></tr>
              </tbody>
            </table>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="table-link-btn"><span class="btn-icon">📋</span> Buka Bukti: Dokumen SPMI</a>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🔄 Tabel 7b: Pelaksanaan SPMI (PPEPP)</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>Tahap</th><th>Dokumen</th><th>Audit</th><th>RTM</th><th>Peningkatan</th></tr></thead>
              <tbody>
                <tr><td><strong>Penetapan</strong></td><td>✅</td><td>—</td><td>—</td><td>—</td></tr>
                <tr><td><strong>Pelaksanaan</strong></td><td>✅</td><td>—</td><td>—</td><td>—</td></tr>
                <tr><td><strong>Evaluasi</strong></td><td>✅</td><td>✅</td><td>—</td><td>—</td></tr>
                <tr><td><strong>Pengendalian</strong></td><td>✅</td><td>—</td><td>✅</td><td>—</td></tr>
                <tr><td><strong>Peningkatan</strong></td><td>✅</td><td>—</td><td>—</td><td>✅</td></tr>
              </tbody>
            </table>
          </div>
          <div class="table-link-container">
            <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="table-link-btn"><span class="btn-icon">📋</span> Penetapan & Pelaksanaan</a>
            <a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank" class="table-link-btn secondary"><span class="btn-icon">🔍</span> Laporan AMI</a>
            <a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank" class="table-link-btn secondary"><span class="btn-icon">📝</span> Notulensi RTM</a>
            <a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank" class="table-link-btn success"><span class="btn-icon">📈</span> Peningkatan & RTL</a>
          </div>
        </div>
      </div>

    </div>

    <!-- ========== SESI 2: LEDPS ========== -->
    <div class="ev-panel" id="panel-sesi2">
      <div class="session-header sesi2">
        <span class="tag">ANALISIS KUALITATIF + BAB III</span>
        <h2>📘 SESI 2 — LAPORAN EVALUASI DIRI (LEDPS)</h2>
        <div class="subtitle">C.1 s.d. C.7 (Analisis Naratif) + BAB III (SWOT & Program Pengembangan)</div>
      </div>

      <div class="info-box ledps">
        <strong>ℹ️ Informasi:</strong> Halaman ini berisi analisis kualitatif per kriteria (LEDPS) dan BAB III. Setiap sub-bagian memiliki tombol link ke bukti Google Drive.
      </div>

      <!-- Sub-nav Kriteria + BAB III -->
      <div class="criteria-nav ledps-nav" id="ledpsNav">
        <button class="active" onclick="showLedpsCriteria('c1', this)"><span>📑</span><span>C.1</span><small>Diferensiasi Misi</small></button>
        <button onclick="showLedpsCriteria('c2', this)"><span>🏛️</span><span>C.2</span><small>Akuntabilitas</small></button>
        <button onclick="showLedpsCriteria('c3', this)"><span>📘</span><span>C.3</span><small>Relevansi</small></button>
        <button onclick="showLedpsCriteria('c4', this)"><span>👨‍🏫</span><span>C.4</span><small>SDM</small></button>
        <button onclick="showLedpsCriteria('c5', this)"><span>💰</span><span>C.5</span><small>Sarpras & K3L</small></button>
        <button onclick="showLedpsCriteria('c6', this)"><span>🎓</span><span>C.6</span><small>Mahasiswa</small></button>
        <button onclick="showLedpsCriteria('c7', this)"><span>🔄</span><span>C.7</span><small>SPMI</small></button>
        <button class="bab3-btn" onclick="showLedpsCriteria('bab3', this)"><span>📕</span><span>BAB III</span><small>SWOT & Program</small></button>
      </div>

      <!-- C.1 DIFERENSIASI MISI -->
      <div class="ledps-criteria active" id="ledps-c1">
        <div class="lkps-section ledps">
          <h3>📑 C.1 — Diferensiasi Misi</h3>
          <div class="led-card">
            <h4>🎯 Visi Keilmuan PSBM</h4>
            <p><strong>"Menjadi Program Studi Unggul Bertaraf Internasional di Bidang Broadband Multimedia untuk Mendukung Daya Saing Bangsa"</strong></p>
            <p><strong>Kekhasan:</strong> Integrasi teknologi telekomunikasi broadband, jaringan komputer, komputasi, dan multimedia dengan karakter pendidikan vokasi berbasis praktik, proyek, magang industri, dan sertifikasi kompetensi.</p>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf" target="_blank" class="table-link-btn success"><span class="btn-icon">📘</span> Buka Bukti: Visi Keilmuan PS</a>
            </div>
          </div>
          <div class="led-card">
            <h4>🔧 Mekanisme Penyusunan VMTS</h4>
            <ul>
              <li><strong>Internal:</strong> Dosen, mahasiswa, tendik (Forum Dialog Jurusan)</li>
              <li><strong>Eksternal:</strong> Alumni, pengguna lulusan, pakar industri (FGD)</li>
              <li><strong>SK Penetapan:</strong> SK Direktur PNJ No. 954/PL3.9/HK.03/2020</li>
            </ul>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn success"><span class="btn-icon">📋</span> Buka Bukti: Mekanisme VMTS</a>
            </div>
          </div>
        </div>
      </div>

      <!-- C.2 AKUNTABILITAS -->
      <div class="ledps-criteria" id="ledps-c2">
        <div class="lkps-section ledps">
          <h3>🏛️ C.2 — Akuntabilitas</h3>
          <div class="led-card">
            <h4>🏢 Tata Pamong & Kerja Sama</h4>
            <p>Struktur tata pamong mengacu pada Statuta PNJ No. 35 Tahun 2018. Total 66 kerja sama (42 pendidikan, 17 penelitian, 7 PkM) dengan mitra strategis seperti St. John's University, Ericsson, Huawei, Telkomsel, dan BRIN.</p>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn success"><span class="btn-icon">🤝</span> Buka Bukti: Kerja Sama</a>
            </div>
          </div>
          <div class="led-card">
            <h4>💰 Keuangan</h4>
            <p>Total Anggaran Rata-rata: Rp 27,24 M/tahun (UPPS), Rp 4,08 M/tahun (PS). BOP per Mahasiswa: Rp 20,36 juta/tahun.</p>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn success"><span class="btn-icon">💰</span> Buka Bukti: Penggunaan Dana</a>
            </div>
          </div>
        </div>
      </div>

      <!-- C.3 RELEVANSI DIKLITPMAS -->
      <div class="ledps-criteria" id="ledps-c3">
        <div class="lkps-section ledps">
          <h3>📘 C.3 — Relevansi Diklitpmas</h3>
          <div class="led-card">
            <h4>📚 Kurikulum & Tridharma</h4>
            <p>53 MK, 150 SKS (53,33% praktik). Dievaluasi 2020, 2021, 2024. 45 penelitian dan 14 PkM dalam 3 tahun terakhir, seluruh PkM melibatkan mahasiswa.</p>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn success"><span class="btn-icon">📘</span> Buka Bukti: Kurikulum & Tridharma</a>
            </div>
          </div>
        </div>
      </div>

      <!-- C.4 SUMBER DAYA MANUSIA -->
      <div class="ledps-criteria" id="ledps-c4">
        <div class="lkps-section ledps">
          <h3>👨‍🏫 C.4 — Sumber Daya Manusia</h3>
          <div class="led-card">
            <h4>📊 Profil & Kinerja DTPS</h4>
            <p>11 DTPS (90,91% Lektor ke atas). 100% memiliki sertifikasi kompetensi. Rerata beban kerja 14,77 SKS. Menghasilkan 220 publikasi dan 43 rekognisi.</p>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn success"><span class="btn-icon">👨‍🏫</span> Buka Bukti: Profil & Kinerja DTPS</a>
            </div>
          </div>
        </div>
      </div>

      <!-- C.5 SARANA, PRASARANA, DAN K3L -->
      <div class="ledps-criteria" id="ledps-c5">
        <div class="lkps-section ledps">
          <h3>💰 C.5 — Sarana, Prasarana, dan K3L</h3>
          <div class="led-card">
            <h4>🔧 Sarana & K3L</h4>
            <p>7 lab + 1 bengkel, 12 ruang kelas. 17 dokumen K3L dan 12 item fasilitas K3L (APAR, hidran, ambulance, P3K, jalur evakuasi) yang seluruhnya terawat.</p>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn success"><span class="btn-icon">🔧</span> Buka Bukti: Sarpras & K3L</a>
            </div>
          </div>
        </div>
      </div>

      <!-- C.6 MAHASISWA DAN LUARAN -->
      <div class="ledps-criteria" id="ledps-c6">
        <div class="lkps-section ledps">
          <h3>🎓 C.6 — Mahasiswa dan Luaran</h3>
          <div class="led-card">
            <h4>👨‍🎓 Kinerja Mahasiswa & Lulusan</h4>
            <p>189 mahasiswa aktif. IPK rata-rata 3,46, masa studi 4,06 tahun. Tracer study: 76,25% terlacak, 55,74% bekerja <3 bulan, 70,49% sesuai bidang.</p>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn success"><span class="btn-icon">🎓</span> Buka Bukti: Mahasiswa & Luaran</a>
            </div>
          </div>
        </div>
      </div>

      <!-- C.7 SISTEM PENJAMINAN MUTU -->
      <div class="ledps-criteria" id="ledps-c7">
        <div class="lkps-section ledps">
          <h3>🔄 C.7 — Sistem Penjaminan Mutu</h3>
          <div class="led-card">
            <h4>📋 SPMI & PPEPP</h4>
            <p>UPM di tingkat institusi dan GPM di tingkat jurusan (SK 147/PL3/JM/2025). Siklus PPEPP berjalan dengan AMI, RTM, dan RTL yang terdokumentasi.</p>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="table-link-btn success"><span class="btn-icon">📋</span> Buka Bukti: SPMI & PPEPP</a>
            </div>
          </div>
        </div>
      </div>

      <!-- BAB III -->
      <div class="ledps-criteria" id="ledps-bab3">
        <div class="lkps-section ledps">
          <h3>📕 BAB III — Program Pengembangan Berkelanjutan</h3>
          
          <div class="led-card">
            <h4>📊 Analisis SWOT</h4>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths</h4>
                <ul>
                  <li>VMTS linear PNJ→JTE→PSBM</li>
                  <li>Kurikulum vokasi kuat (53,33% praktik)</li>
                  <li>SDM kuat (90,91% Lektor+, 100% sertifikasi)</li>
                  <li>SPMI berjalan (PPEPP, AMI, RTM)</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses</h4>
                <ul>
                  <li>Internasionalisasi belum sekuat nasional</li>
                  <li>Pendanaan penelitian 80% internal</li>
                  <li>Keterlibatan mhs dalam penelitian 26,67%</li>
                  <li>Bahasa asing perlu penguatan</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities</h4>
                <ul>
                  <li>Transformasi digital & 5G/6G, IoT, AI</li>
                  <li>Hibah nasional (BIMA, DRTPM)</li>
                  <li>Kebutuhan DUDI broadband</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats</h4>
                <ul>
                  <li>Perubahan teknologi cepat</li>
                  <li>Persaingan PT sejenis</li>
                  <li>Regulasi DIKTI berubah</li>
                </td>
              </div>
            </div>
          </div>

          <div class="led-card">
            <h4>🎯 6 Tujuan Strategis PSBM</h4>
            <div class="summary-grid">
              <div class="summary-card" style="border-left-color: #e65100;"><div class="sc-label">Tujuan 1</div><div class="sc-value" style="font-size:0.8rem;">Mutu Pendidikan</div></div>
              <div class="summary-card" style="border-left-color: #e65100;"><div class="sc-label">Tujuan 2</div><div class="sc-value" style="font-size:0.8rem;">Penelitian & Hilirisasi</div></div>
              <div class="summary-card" style="border-left-color: #e65100;"><div class="sc-label">Tujuan 3</div><div class="sc-value" style="font-size:0.8rem;">Kualitas SDM</div></div>
              <div class="summary-card" style="border-left-color: #e65100;"><div class="sc-label">Tujuan 4</div><div class="sc-value" style="font-size:0.8rem;">Internasionalisasi</div></div>
              <div class="summary-card" style="border-left-color: #e65100;"><div class="sc-label">Tujuan 5</div><div class="sc-value" style="font-size:0.8rem;">Daya Saing Lulusan</div></div>
              <div class="summary-card" style="border-left-color: #e65100;"><div class="sc-label">Tujuan 6</div><div class="sc-value" style="font-size:0.8rem;">Budaya Mutu</div></div>
            </div>
          </div>

          <div class="led-card">
            <h4>📘 6 Program Pengembangan</h4>
            <div class="table-responsive">
              <table class="lkps-table">
                <thead><tr><th>No</th><th>Program</th><th>Target</th></tr></thead>
                <tbody>
                  <tr><td>1</td><td>Closed-Loop CPL</td><td>100% CPL terukur</td></tr>
                  <tr><td>2</td><td>Pendanaan Eksternal</td><td>≥40% (2026)</td></tr>
                  <tr><td>3</td><td>Integrasi Penelitian-Mhs</td><td>≥40% libatkan mhs</td></tr>
                  <tr><td>4</td><td>JAFA & Studi Lanjut</td><td>5 doktor, 50% LK</td></tr>
                  <tr><td>5</td><td>Response Rate Tracer</td><td>≥80%</td></tr>
                  <tr><td>6</td><td>Internasionalisasi</td><td>≥5 MoU intl</td></tr>
                </tbody>
                </table>
            </div>
            <div class="table-link-container">
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn success"><span class="btn-icon">📕</span> Buka Bukti: BAB III</a>
            </div>
          </div>

        </div>
      </div>

    </div>

  </div>
</div>

<script>
function showEvPanel(id, btn) {
  document.querySelectorAll('.ev-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.ev-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  if (id === 'sesi1') showLkpsTable('t1', document.querySelector('#lkpsNav button'));
  else if (id === 'sesi2') showLedpsCriteria('c1', document.querySelector('#ledpsNav button'));
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

function showLkpsTable(id, btn) {
  document.querySelectorAll('.lkps-table-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('lkps-' + id).classList.add('active');
  const nav = btn.parentElement;
  nav.querySelectorAll('button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}

function showLedpsCriteria(id, btn) {
  document.querySelectorAll('.ledps-criteria').forEach(p => p.classList.remove('active'));
  document.getElementById('ledps-' + id).classList.add('active');
  const nav = btn.parentElement;
  nav.querySelectorAll('button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}

document.addEventListener('DOMContentLoaded', function() {
  document.getElementById('panel-sesi1').classList.add('active');
  document.getElementById('lkps-t1').classList.add('active');
  document.getElementById('ledps-c1').classList.add('active');
});
</script>

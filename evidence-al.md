---
layout: default
title: Evidence AL
permalink: /evidence-al/
---

<style>
/* ===== MODERN CABINET & TABS ===== */
.ev-cabinet { 
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%); 
  padding: 20px 20px 0 20px; 
  border-radius: 16px 16px 0 0; 
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08); 
  position: relative; 
  border: 1px solid #e2e8f0; 
  border-bottom: none; 
}

.ev-shelf { 
  display: flex; 
  gap: 8px; 
  padding: 0 4px; 
  position: relative; 
  z-index: 10; 
  overflow-x: auto; 
  scrollbar-width: none; 
}
.ev-shelf::-webkit-scrollbar { display: none; }

.ev-tab { 
  position: relative;
  flex: 1;
  min-width: 0;
  padding: 14px 16px 18px 16px; 
  background: white;
  border-radius: 12px 12px 0 0;
  border: 1px solid #e2e8f0;
  border-bottom: none;
  cursor: pointer; 
  text-align: center; 
  font-weight: 600; 
  font-size: 0.85rem; 
  line-height: 1.3; 
  color: #64748b; 
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); 
  transform: translateY(2px);
  box-shadow: 0 -2px 6px rgba(0,0,0,0.02);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
}

.ev-tab::before { 
  content: ''; 
  position: absolute; 
  top: 0; left: 0; right: 0; 
  height: 3px; 
  background: transparent; 
  border-radius: 12px 12px 0 0; 
  transition: all 0.3s ease; 
}

.ev-tab:hover { 
  background: #f8fafc; 
  transform: translateY(0); 
  color: #0d47a1; 
  box-shadow: 0 -4px 12px rgba(0,0,0,0.06);
}
.ev-tab:hover::before { background: #cbd5e1; }

.ev-tab.active { 
  background: white; 
  color: #0d47a1; 
  transform: translateY(-4px); 
  z-index: 20; 
  border-color: #0d47a1; 
  box-shadow: 0 -6px 20px rgba(13, 71, 161, 0.15); 
  font-weight: 700; 
}
.ev-tab.active::before { 
  background: linear-gradient(90deg, #0d47a1, #1565c0); 
  height: 4px; 
}

.ev-tab .tab-icon { font-size: 1.3rem; }
.ev-tab .tab-label { font-size: 0.75rem; opacity: 0.8; }
.ev-tab.active .tab-label { opacity: 1; }

/* SESI 2 - BIRU MUDA */
.ev-tab.sesi2.active { 
  color: #0288d1; 
  border-color: #0288d1; 
  box-shadow: 0 -6px 20px rgba(2, 136, 209, 0.15); 
}
.ev-tab.sesi2.active::before { 
  background: linear-gradient(90deg, #0288d1, #29b6f6); 
}

/* ===== CONTENT ===== */
.ev-content { 
  background: white; 
  border: 1px solid #e2e8f0; 
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

/* ===== SESSION HEADER ===== */
.session-header { 
  padding: 24px; 
  border-radius: 12px; 
  margin-bottom: 20px; 
  color: white; 
  position: relative;
  overflow: hidden;
}
.session-header::before {
  content: '';
  position: absolute;
  top: -50%;
  right: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
  pointer-events: none;
}
.session-header.sesi1 { 
  background: linear-gradient(135deg, #1565c0 0%, #0d47a1 100%); 
  box-shadow: 0 8px 24px rgba(13, 71, 161, 0.25);
}
.session-header.sesi2 { 
  background: linear-gradient(135deg, #0288d1 0%, #01579b 100%); 
  box-shadow: 0 8px 24px rgba(2, 136, 209, 0.25);
}
.session-header h2 { 
  margin: 0 0 8px 0; 
  font-size: 1.4rem; 
  font-weight: 700;
  position: relative;
  z-index: 1;
}
.session-header .subtitle { 
  opacity: 0.95; 
  font-size: 0.92rem; 
  margin-bottom: 12px;
  position: relative;
  z-index: 1;
}
.session-header .tag { 
  display: inline-block; 
  background: rgba(255,255,255,0.25); 
  padding: 4px 12px; 
  border-radius: 12px; 
  font-size: 0.72rem; 
  font-weight: 700; 
  margin-bottom: 8px;
  letter-spacing: 0.5px;
  position: relative;
  z-index: 1;
}

/* ===== SUB-NAV ===== */
.criteria-nav { 
  display: flex; 
  gap: 6px; 
  margin-bottom: 20px; 
  flex-wrap: wrap; 
  padding: 8px;
  background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
  border-radius: 12px;
  border: 1px solid #e2e8f0;
  box-shadow: inset 0 2px 4px rgba(0,0,0,0.02);
}
.criteria-nav button { 
  position: relative;
  padding: 8px 12px; 
  background: white;
  border: 1.5px solid #e2e8f0;
  border-radius: 8px;
  cursor: pointer; 
  font-weight: 600; 
  color: #64748b; 
  font-size: 0.75rem;
  transition: all 0.25s ease;
  box-shadow: 0 1px 2px rgba(0,0,0,0.02);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2px;
  min-width: 65px;
}
.criteria-nav button small {
  font-size: 0.62rem;
  font-weight: 500;
  opacity: 0.7;
}
.criteria-nav button:hover { 
  transform: translateY(-1px);
  border-color: #0d47a1;
  color: #0d47a1;
  box-shadow: 0 3px 8px rgba(13, 71, 161, 0.1);
}
.criteria-nav button.active { 
  background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
  color: white;
  border-color: #0d47a1;
  box-shadow: 0 3px 10px rgba(13, 71, 161, 0.25);
  transform: translateY(-1px);
}
.criteria-nav button.active small { opacity: 0.9; }

.criteria-nav.ledps-nav button:hover {
  border-color: #0288d1;
  color: #0288d1;
  box-shadow: 0 3px 8px rgba(2, 136, 209, 0.1);
}
.criteria-nav.ledps-nav button.active { 
  background: linear-gradient(135deg, #0288d1 0%, #29b6f6 100%);
  border-color: #0288d1;
  box-shadow: 0 3px 10px rgba(2, 136, 209, 0.25);
}
.criteria-nav button.bab3-btn {
  background: linear-gradient(135deg, #fff3e0 0%, #ffe0b2 100%);
  border-color: #ffcc80;
  color: #e65100;
}
.criteria-nav button.bab3-btn:hover {
  border-color: #e65100;
  color: #e65100;
}
.criteria-nav button.bab3-btn.active {
  background: linear-gradient(135deg, #e65100 0%, #f57c00 100%);
  color: white;
  border-color: #e65100;
  box-shadow: 0 3px 10px rgba(230, 81, 0, 0.25);
}

/* ===== PANELS ===== */
.lkps-table-panel { display: none; animation: fadeIn 0.3s ease; }
.lkps-table-panel.active { display: block; }
.ledps-criteria { display: none; animation: fadeIn 0.3s ease; }
.ledps-criteria.active { display: block; }

.lkps-section { margin-bottom: 24px; }
.lkps-section h3 { 
  color: #0d47a1; 
  border-left: 4px solid #0d47a1; 
  padding-left: 12px; 
  margin: 0 0 12px 0; 
  font-size: 1.05rem;
  font-weight: 700;
}
.lkps-section.ledps h3 { 
  color: #0288d1; 
  border-left-color: #0288d1; 
}

.table-responsive { 
  overflow-x: auto; 
  border: 1px solid #e2e8f0; 
  border-radius: 8px; 
  margin-bottom: 16px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
}
.lkps-table { 
  width: 100%; 
  border-collapse: collapse; 
  font-size: 0.82rem; 
  min-width: 600px; 
}
.lkps-table th, .lkps-table td { 
  border: 1px solid #e2e8f0; 
  padding: 8px 10px; 
  text-align: left; 
  vertical-align: top; 
}
.lkps-table th { 
  background: linear-gradient(135deg, #f1f5f9 0%, #e2e8f0 100%);
  font-weight: 700; 
  color: #0d47a1; 
  position: sticky; 
  top: 0; 
  z-index: 1;
  font-size: 0.78rem;
  text-transform: uppercase;
  letter-spacing: 0.3px;
}
.lkps-table tr:nth-child(even) { background-color: #f8fafc; }
.lkps-table tr:hover { background-color: #e3f2fd; transition: background-color 0.2s ease; }
.highlight-data { background-color: #fff8e1 !important; font-weight: 600; color: #e65100; }
.link-cell a { color: #0d47a1; text-decoration: none; font-weight: 600; }
.link-cell a:hover { text-decoration: underline; }

.summary-grid { 
  display: grid; 
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); 
  gap: 10px; 
  margin: 16px 0; 
}
.summary-card { 
  background: white; 
  border: 1px solid #e2e8f0; 
  border-left: 4px solid #0d47a1; 
  border-radius: 8px; 
  padding: 12px; 
  transition: all 0.25s ease;
  box-shadow: 0 2px 6px rgba(0,0,0,0.04);
}
.summary-card:hover { 
  box-shadow: 0 6px 16px rgba(0,0,0,0.08); 
  transform: translateY(-3px); 
  border-left-color: #1565c0;
}
.summary-card .sc-label { 
  font-size: 0.7rem; 
  color: #64748b; 
  text-transform: uppercase; 
  letter-spacing: 0.5px;
  font-weight: 600;
}
.summary-card .sc-value { 
  font-size: 1.3rem; 
  font-weight: 800; 
  color: #0d47a1; 
  margin: 4px 0; 
}
.summary-card .sc-desc { 
  font-size: 0.75rem; 
  color: #64748b; 
}

.info-box { 
  background: linear-gradient(135deg, #e3f2fd 0%, #bbdefb 100%); 
  border-left: 4px solid #0d47a1; 
  padding: 12px 16px; 
  border-radius: 10px; 
  margin-bottom: 20px; 
  font-size: 0.88rem; 
  color: #0d47a1;
  box-shadow: 0 2px 8px rgba(13, 71, 161, 0.08);
}
.info-box.ledps { 
  background: linear-gradient(135deg, #e1f5fe 0%, #b3e5fc 100%); 
  border-left-color: #0288d1; 
  color: #01579b;
  box-shadow: 0 2px 8px rgba(2, 136, 209, 0.08);
}
.info-box strong { color: inherit; font-weight: 700; }

.led-card { 
  background: white; 
  border: 1px solid #e2e8f0; 
  border-radius: 10px; 
  padding: 16px; 
  margin-bottom: 12px; 
  border-left: 4px solid #0288d1;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  transition: all 0.25s ease;
}
.led-card:hover {
  box-shadow: 0 6px 16px rgba(0,0,0,0.08);
  transform: translateX(2px);
}
.led-card h4 { 
  color: #0288d1; 
  margin: 0 0 10px 0; 
  font-size: 0.95rem;
  font-weight: 700;
}
.led-card p { 
  color: #475569; 
  font-size: 0.85rem; 
  line-height: 1.6; 
  margin: 0 0 10px 0; 
}
.led-card ul { 
  margin: 10px 0; 
  padding-left: 22px; 
  font-size: 0.82rem; 
  color: #475569; 
}
.led-card li { 
  margin-bottom: 5px; 
  line-height: 1.5; 
}

.evidence-link { 
  display: inline-flex; 
  align-items: center; 
  gap: 6px; 
  background: linear-gradient(135deg, #e1f5fe 0%, #b3e5fc 100%);
  color: #0288d1; 
  padding: 6px 12px; 
  border-radius: 8px; 
  font-size: 0.75rem; 
  font-weight: 600; 
  text-decoration: none; 
  margin: 4px 4px 0 0;
  transition: all 0.2s ease;
  border: 1px solid #81d4fa;
}
.evidence-link:hover { 
  background: linear-gradient(135deg, #b3e5fc 0%, #81d4fa 100%);
  transform: translateY(-1px);
  box-shadow: 0 4px 8px rgba(2, 136, 209, 0.2);
}

.table-link-btn { 
  display: inline-flex; 
  align-items: center; 
  gap: 6px; 
  padding: 8px 14px; 
  background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); 
  color: white; 
  border-radius: 8px; 
  text-decoration: none; 
  font-weight: 600; 
  font-size: 0.78rem; 
  transition: all 0.25s ease; 
  margin: 4px 4px 4px 0; 
  box-shadow: 0 2px 6px rgba(13, 71, 161, 0.2);
  border: none;
}
.table-link-btn:hover { 
  background: linear-gradient(135deg, #1565c0 0%, #1976d2 100%); 
  transform: translateY(-2px); 
  box-shadow: 0 4px 12px rgba(13, 71, 161, 0.3);
}
.table-link-btn.secondary { 
  background: linear-gradient(135deg, #455a64 0%, #546e7a 100%); 
  box-shadow: 0 2px 6px rgba(69, 90, 100, 0.2); 
}
.table-link-btn.secondary:hover { 
  background: linear-gradient(135deg, #546e7a 0%, #607d8b 100%); 
}
.table-link-btn.success { 
  background: linear-gradient(135deg, #2e7d32 0%, #388e3c 100%); 
  box-shadow: 0 2px 6px rgba(46, 125, 50, 0.2); 
}
.table-link-btn.success:hover { 
  background: linear-gradient(135deg, #388e3c 0%, #43a047 100%); 
}
.table-link-btn .btn-icon { font-size: 1rem; }

.swot-grid { 
  display: grid; 
  grid-template-columns: 1fr 1fr; 
  gap: 12px; 
  margin: 16px 0; 
}
.swot-card { 
  padding: 14px; 
  border-radius: 10px; 
  border: 2px solid;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  transition: all 0.25s ease;
}
.swot-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(0,0,0,0.08);
}
.swot-card.strength { background: #e8f5e9; border-color: #4caf50; }
.swot-card.weakness { background: #fff3e0; border-color: #ff9800; }
.swot-card.opportunity { background: #e3f2fd; border-color: #2196f3; }
.swot-card.threat { background: #ffebee; border-color: #f44336; }
.swot-card h4 { 
  margin: 0 0 10px 0; 
  font-size: 0.9rem;
  font-weight: 700;
}
.swot-card ul { 
  margin: 0; 
  padding-left: 18px; 
  font-size: 0.82rem; 
}
.swot-card ul li { padding: 3px 0; line-height: 1.5; }

@media (max-width: 767px) {
  .ev-shelf { gap: 4px; padding-bottom: 6px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
  .ev-shelf::-webkit-scrollbar { display: none; }
  .ev-tab { min-width: 100px; flex: 0 0 auto; font-size: 0.75rem; padding: 12px 10px; }
  .ev-content { padding: 16px; }
  .summary-grid { grid-template-columns: 1fr 1fr; }
  .swot-grid { grid-template-columns: 1fr; }
  .criteria-nav { gap: 4px; padding: 6px; }
  .criteria-nav button { padding: 6px 8px; font-size: 0.7rem; min-width: 60px; }
  .session-header { padding: 20px; }
  .session-header h2 { font-size: 1.2rem; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('sesi1', this)">
      <span class="tab-icon"></span>
      <span class="tab-label">SESI 1: LKPS</span>
    </div>
    <div class="ev-tab sesi2" onclick="showEvPanel('sesi2', this)">
      <span class="tab-icon">📘</span>
      <span class="tab-label">SESI 2: LEDPS</span>
    </div>
  </div>

  <div class="ev-content">

    <!-- ========== SESI 1: LKPS ========== -->
    <div class="ev-panel active" id="panel-sesi1">
      <div class="session-header sesi1">
        <span class="tag">DATA KUANTITATIF — 50+ TABEL LKPS</span>
        <h2>📊 SESI 1 — LAPORAN KINERJA PROGRAM STUDI (LKPS)</h2>
        <div class="subtitle">Tabel 1 s.d. 7 — Data angka 3 tahun terakhir dengan link bukti Google Drive</div>
      </div>

      <div class="info-box">
        <strong>️ Informasi:</strong> Halaman ini menampilkan <strong>50+ tabel LKPS</strong> dengan link bukti Google Drive. Klik tombol "📂 Buka Bukti" untuk mengakses dokumen asli.
      </div>

      <!-- Sub-nav Tabel 1-7 -->
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
          <h3>📑 Tabel 1: VMTS PT, UPPS, dan Visi Keilmuan PS</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>No</th><th>Jenis VMTS</th><th>Pernyataan</th><th>No. SK</th><th>Link Dokumen</th></tr></thead>
              <tbody>
                <tr><td>1</td><td><strong>VMTS PT</strong></td><td>Visi: Menjadi politeknik unggul bertaraf internasional</td><td>643/PL3/OT/2021</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank">📂 Buka</a></td></tr>
                <tr><td>2</td><td><strong>VMTS UPPS (JTE)</strong></td><td>Visi: Menjadi Jurusan Teknik Elektro unggul bertaraf internasional</td><td>2585/PL3/OT/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1JiRWv_v_-pbrFTMl74JwQzJ1ZNnCpcOt" target="_blank">📂 Buka</a></td></tr>
                <tr><td>3</td><td><strong>Visi Keilmuan PS</strong></td><td>Unggul bertaraf internasional di bidang broadband multimedia</td><td>2589/PL3/KR.00/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf" target="_blank">📂 Buka</a></td></tr>
              </tbody>
            </table>
          </div>
          <div style="margin-top:12px;">
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📄</span> Buka Bukti: Tabel 1 - VMTS PT</a>
            <a href="https://drive.google.com/drive/folders/1JiRWv_v_-pbrFTMl74JwQzJ1ZNnCpcOt" target="_blank" class="table-link-btn"><span class="btn-icon"></span> Buka Bukti: Tabel 1 - VMTS UPPS</a>
            <a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf" target="_blank" class="table-link-btn"><span class="btn-icon">📘</span> Buka Bukti: Tabel 1 - Visi Keilmuan PS</a>
          </div>
        </div>
      </div>

      <!-- TABEL 2: KERJA SAMA & DANA -->
      <div class="lkps-table-panel" id="lkps-t2">
        <div class="lkps-section">
          <h3>🤝 Tabel 2a1: Kerja Sama Pendidikan (42)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">5</div></div>
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">37</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">42</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon"></span> Buka Bukti: Tabel 2a1 - Kerja Sama Pendidikan</a>
        </div>
        <div class="lkps-section">
          <h3>🔬 Tabel 2a2: Kerja Sama Penelitian (17)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">16</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">17</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🔬</span> Buka Bukti: Tabel 2a2 - Kerja Sama Penelitian</a>
        </div>
        <div class="lkps-section">
          <h3>🤝 Tabel 2a3: Kerja Sama PkM (7)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Lokal/Wilayah</div><div class="sc-value">6</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">7</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🤝</span> Buka Bukti: Tabel 2a3 - Kerja Sama PkM</a>
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
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">💰</span> Buka Bukti: Tabel 2b - Penggunaan Dana</a>
        </div>
      </div>

      <!-- TABEL 3: KURIKULUM & TRIDHARMA -->
      <div class="lkps-table-panel" id="lkps-t3">
        <div class="lkps-section">
          <h3>📘 Tabel 3a1: Kurikulum (53 MK, 150 SKS)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total MK</div><div class="sc-value">53</div></div>
            <div class="summary-card"><div class="sc-label">Total SKS</div><div class="sc-value">150</div></div>
            <div class="summary-card"><div class="sc-label">SKS Praktik</div><div class="sc-value">80 (53,33%)</div></div>
            <div class="summary-card"><div class="sc-label">SKS Kuliah</div><div class="sc-value">68</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📘</span> Buka Bukti: Tabel 3a1 - Kurikulum</a>
        </div>
        <div class="lkps-section">
          <h3>🔬 Tabel 3b: Penelitian DTPS (45 judul)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">14</div></div>
            <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">13</div></div>
            <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">18</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">45</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🔬</span> Buka Bukti: Tabel 3b - Penelitian DTPS</a>
        </div>
        <div class="lkps-section">
          <h3>🤝 Tabel 3c: PkM DTPS (14 judul)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">6</div></div>
            <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">6</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">14</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🤝</span> Buka Bukti: Tabel 3c - PkM DTPS</a>
        </div>
      </div>

      <!-- TABEL 4: SDM & LUARAN -->
      <div class="lkps-table-panel" id="lkps-t4">
        <div class="lkps-section">
          <h3>👨‍ Tabel 4a: Profil DTPS (11 Dosen)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total DTPS</div><div class="sc-value">11</div></div>
            <div class="summary-card"><div class="sc-label">Doktor</div><div class="sc-value">3 (27,27%)</div></div>
            <div class="summary-card"><div class="sc-label">Lektor Kepala</div><div class="sc-value">4 (36,36%)</div></div>
            <div class="summary-card"><div class="sc-label">Lektor</div><div class="sc-value">6</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">‍🏫</span> Buka Bukti: Tabel 4a - Profil DTPS</a>
        </div>
        <div class="lkps-section">
          <h3>📚 Tabel 4e: Publikasi DTPS (220 total)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Jurnal Nasional Terakreditasi</div><div class="sc-value">73</div></div>
            <div class="summary-card"><div class="sc-label">Jurnal Internasional Bereputasi</div><div class="sc-value">12</div></div>
            <div class="summary-card"><div class="sc-label">Prosiding Nasional</div><div class="sc-value">92</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">TOTAL</div><div class="sc-value">220</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📚</span> Buka Bukti: Tabel 4e - Publikasi DTPS</a>
        </div>
        <div class="lkps-section">
          <h3>📦 Tabel 4g: Produk/Jasa DTPS Diadopsi (13)</h3>
          <a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z" target="_blank" class="table-link-btn"><span class="btn-icon">📦</span> Buka Bukti: Tabel 4g - Produk DTPS Diadopsi</a>
        </div>
      </div>

      <!-- TABEL 5: SARPRAS & K3L -->
      <div class="lkps-table-panel" id="lkps-t5">
        <div class="lkps-section">
          <h3>💰 Tabel 5a: Prasarana & Peralatan Utama</h3>
          <div class="info-box"><strong>📌 Ringkasan:</strong> 16 prasarana utama (13 lab/ruang + 3 layanan nonakademik). Seluruhnya terawat, dimiliki sendiri.</div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon"></span> Buka Bukti: Tabel 5a - Sarpras</a>
        </div>
        <div class="lkps-section">
          <h3>⚠️ Tabel 5b: Dokumen K3L (17 dokumen)</h3>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">️</span> Buka Bukti: Tabel 5b - Dokumen K3L</a>
        </div>
        <div class="lkps-section">
          <h3>🧯 Tabel 5c: Fasilitas K3L (12 item)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">APAR</div><div class="sc-value">6</div></div>
            <div class="summary-card"><div class="sc-label">Hidran</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">Ambulance</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">P3K</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">Rambu K3</div><div class="sc-value">7</div></div>
            <div class="summary-card"><div class="sc-label">Jalur Evakuasi</div><div class="sc-value">22</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🧯</span> Buka Bukti: Tabel 5c - Fasilitas K3L</a>
        </div>
      </div>

      <!-- TABEL 6: MAHASISWA & LUARAN -->
      <div class="lkps-table-panel" id="lkps-t6">
        <div class="lkps-section">
          <h3> Tabel 6a: Jumlah Mahasiswa (189 aktif TS)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">192</div></div>
            <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">182</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">TS</div><div class="sc-value">189</div></div>
            <div class="summary-card"><div class="sc-label">Mhs Asing PT TS</div><div class="sc-value">12</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🎓</span> Buka Bukti: Tabel 6a - Mahasiswa</a>
        </div>
        <div class="lkps-section">
          <h3>🎓 Tabel 6b: IPK Lulusan</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>Tahun Lulus</th><th>Jumlah Lulusan</th><th>Min</th><th>Rata-rata</th><th>Maks</th></tr></thead>
              <tbody>
                <tr><td>TS-2</td><td>44</td><td>2.66</td><td class="highlight-data">3.49</td><td>3.76</td></tr>
                <tr><td>TS-1</td><td>36</td><td>3.18</td><td class="highlight-data">3.45</td><td>3.73</td></tr>
                <tr><td>TS</td><td>44</td><td>2.78</td><td class="highlight-data">3.43</td><td>3.82</td></tr>
              </tbody>
            </table>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">🎓</span> Buka Bukti: Tabel 6b - IPK Lulusan</a>
        </div>
        <div class="lkps-section">
          <h3>📈 Tabel 6f1: Waktu Tunggu Lulusan</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total Lulusan</div><div class="sc-value">80</div></div>
            <div class="summary-card"><div class="sc-label">Terlacak</div><div class="sc-value">61 (76,25%)</div></div>
            <div class="summary-card"><div class="sc-label">WT &lt; 3 bulan</div><div class="sc-value">34 (55,74%)</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">WT &gt; 18 bulan</div><div class="sc-value">0</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📈</span> Buka Bukti: Tabel 6f1 - Waktu Tunggu</a>
        </div>
        <div class="lkps-section">
          <h3>⭐ Tabel 6g2: Kepuasan Pengguna (45 responden)</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>Kemampuan</th><th>Sangat Baik</th><th>Baik</th><th>Cukup</th><th>Kurang</th></tr></thead>
              <tbody>
                <tr><td>Etika</td><td class="highlight-data">80,00%</td><td>20,00%</td><td>0,00%</td><td>0,00%</td></tr>
                <tr><td>Keahlian bidang ilmu</td><td class="highlight-data">73,30%</td><td>26,70%</td><td>0,00%</td><td>0,00%</td></tr>
                <tr><td>Bahasa asing</td><td class="highlight-data">71,10%</td><td>17,80%</td><td class="highlight-data">11,10%</td><td>0,00%</td></tr>
                <tr><td>Teknologi informasi</td><td class="highlight-data">82,20%</td><td>17,80%</td><td>0,00%</td><td>0,00%</td></tr>
              </tbody>
            </table>
          </div>
          <div class="info-box"><strong>️ Catatan Kritis:</strong> Bahasa asing 11,1% "Cukup" — perlu direkonsiliasi dengan narasi RTL yang menyebut 25%.</div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">⭐</span> Buka Bukti: Tabel 6g2 - Kepuasan Pengguna</a>
        </div>
      </div>

      <!-- TABEL 7: SPMI -->
      <div class="lkps-table-panel" id="lkps-t7">
        <div class="lkps-section">
          <h3>🔄 Tabel 7a: Dokumen SPMI (4 dokumen)</h3>
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
          <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="table-link-btn"><span class="btn-icon">📋</span> Buka Bukti: Tabel 7a - Dokumen SPMI</a>
        </div>
        <div class="lkps-section">
          <h3>🔄 Tabel 7b: Pelaksanaan SPMI (Siklus PPEPP)</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>Tahap PPEPP</th><th>Link Dokumen</th><th>Link Audit</th><th>Link RTM</th><th>Link Peningkatan</th></tr></thead>
              <tbody>
                <tr><td><strong>Penetapan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank">📂 Buka</a></td><td>—</td><td>—</td><td>—</td></tr>
                <tr><td><strong>Pelaksanaan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank">📂 Buka</a></td><td>—</td><td>—</td><td>—</td></tr>
                <tr><td><strong>Evaluasi</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1ywPn4RexBzQjD6DXRT8DCXTEtemvcQLz" target="_blank">📂 Buka</a></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank">📂 Buka</a></td><td>—</td><td>—</td></tr>
                <tr><td><strong>Pengendalian</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1WFgIamM3JnSGZ-WAv-UOC1W22E0ondmV" target="_blank">📂 Buka</a></td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank">📂 Buka</a></td><td>—</td></tr>
                <tr><td><strong>Peningkatan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank">📂 Buka</a></td><td>—</td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank">📂 Buka</a></td></tr>
              </tbody>
            </table>
          </div>
          <div style="margin-top:12px;">
            <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="table-link-btn"><span class="btn-icon">📋</span> Buka Bukti: Tabel 7b - Penetapan & Pelaksanaan</a>
            <a href="https://drive.google.com/drive/folders/1ywPn4RexBzQjD6DXRT8DCXTEtemvcQLz" target="_blank" class="table-link-btn secondary"><span class="btn-icon">📊</span> Buka Bukti: Tabel 7b - Evaluasi</a>
            <a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank" class="table-link-btn secondary"><span class="btn-icon">🔍</span> Buka Bukti: Tabel 7b - Laporan AMI</a>
            <a href="https://drive.google.com/drive/folders/1WFgIamM3JnSGZ-WAv-UOC1W22E0ondmV" target="_blank" class="table-link-btn secondary"><span class="btn-icon">📝</span> Buka Bukti: Tabel 7b - Pengendalian</a>
            <a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank" class="table-link-btn secondary"><span class="btn-icon"></span> Buka Bukti: Tabel 7b - Notulensi RTM</a>
            <a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank" class="table-link-btn success"><span class="btn-icon"></span> Buka Bukti: Tabel 7b - Peningkatan & RTL</a>
          </div>
          <div class="info-box"><strong>✅ Siklus PPEPP Lengkap:</strong> Semua 5 tahap terdokumentasi dengan link Google Drive aktif.</div>
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
        <strong>️ Informasi:</strong> Halaman ini berisi analisis kualitatif per kriteria (LEDPS) dan BAB III (SWOT, Tujuan Strategis, Program Pengembangan). Setiap sub-bagian memiliki tombol link ke bukti Google Drive.
      </div>

      <!-- Sub-nav Kriteria + BAB III -->
      <div class="criteria-nav ledps-nav" id="ledpsNav">
        <button class="active" onclick="showLedpsCriteria('c1', this)"><span></span><span>C.1</span><small>Diferensiasi Misi</small></button>
        <button onclick="showLedpsCriteria('c2', this)"><span>🏛️</span><span>C.2</span><small>Akuntabilitas</small></button>
        <button onclick="showLedpsCriteria('c3', this)"><span>📘</span><span>C.3</span><small>Relevansi</small></button>
        <button onclick="showLedpsCriteria('c4', this)"><span>👨‍🏫</span><span>C.4</span><small>SDM</small></button>
        <button onclick="showLedpsCriteria('c5', this)"><span></span><span>C.5</span><small>Sarpras & K3L</small></button>
        <button onclick="showLedpsCriteria('c6', this)"><span>🎓</span><span>C.6</span><small>Luaran</small></button>
        <button onclick="showLedpsCriteria('c7', this)"><span>🔄</span><span>C.7</span><small>SPMI</small></button>
        <button class="bab3-btn" onclick="showLedpsCriteria('bab3', this)"><span>📕</span><span>BAB III</span><small>SWOT & Program</small></button>
      </div>

      <!-- C.1 DIFERENSIASI MISI -->
      <div class="ledps-criteria active" id="ledps-c1">
        <div class="lkps-section ledps">
          <h3>📑 C.1 — Diferensiasi Misi (Visi, Misi, Tujuan, dan Strategi)</h3>
          <div class="led-card">
            <h4>🎯 Visi Keilmuan PSBM</h4>
            <p><strong>"Menjadi Program Studi Unggul Bertaraf Internasional di Bidang Broadband Multimedia untuk Mendukung Daya Saing Bangsa"</strong></p>
            <p><strong>Kekhasan:</strong> Integrasi teknologi telekomunikasi broadband, jaringan komputer, komputasi, dan multimedia dengan karakter pendidikan vokasi berbasis praktik, proyek, magang industri, dan sertifikasi kompetensi.</p>
            <a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf" target="_blank" class="evidence-link">📂 Bukti: Tabel 1 - Visi Keilmuan PS</a>
          </div>
          <div class="led-card">
            <h4>🔧 Mekanisme Penyusunan VMTS</h4>
            <ul>
              <li><strong>Internal:</strong> Dosen, mahasiswa, tendik (Forum Dialog Jurusan)</li>
              <li><strong>Eksternal:</strong> Alumni, pengguna lulusan, pakar industri (FGD)</li>
              <li><strong>Pakar:</strong> Marfani (Telkomsel), Hendra Gunawan (MyRepublic), Irvan Nugraha (Universal Satellite Indonesia)</li>
              <li><strong>SK Penetapan:</strong> SK Direktur PNJ No. 954/PL3.9/HK.03/2020</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 1 - Mekanisme VMTS</a>
          </div>
          <div class="led-card">
            <h4>🎯 Capaian VMTS (Traceability ke LKPS)</h4>
            <ul>
              <li><strong>Pendidikan:</strong> 53,33% praktik, 5 MK diampu praktisi (20%) → <em>LKPS 3.a</em></li>
              <li><strong>Penelitian:</strong> 45 penelitian (14→13→18), tren meningkat → <em>LKPS 3.b</em></li>
              <li><strong>PkM:</strong> 14 kegiatan (2→6→6), seluruhnya libatkan mahasiswa → <em>LKPS 3.c</em></li>
              <li><strong>Luaran Mahasiswa:</strong> 126 publikasi, 19 prestasi → <em>LKPS 6.c, 6.e</em></li>
              <li><strong>Daya Saing Lulusan:</strong> 81,96% kesesuaian bidang kerja, 80,32% bekerja nasional-multinasional → <em>LKPS 6.f, 6.g</em></li>
            </ul>
          </div>
        </div>
      </div>

      <!-- C.2 AKUNTABILITAS -->
      <div class="ledps-criteria" id="ledps-c2">
        <div class="lkps-section ledps">
          <h3>🏛️ C.2 — Akuntabilitas (Tata Pamong, Tata Kelola, Kerja Sama, Keuangan)</h3>
          <div class="led-card">
            <h4>🏢 Tata Pamong</h4>
            <p>Struktur tata pamong mengacu pada <strong>Statuta PNJ No. 35 Tahun 2018</strong> dan <strong>OTK PNJ No. 60 Tahun 2022</strong>. Lima pilar Good University Governance: Kredibel, Transparan, Akuntabel, Bertanggung Jawab, Adil.</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 2 - Tata Pamong</a>
          </div>
          <div class="led-card">
            <h4>🤝 Kerja Sama Tridharma — Analisis</h4>
            <ul>
              <li><strong>Total:</strong> 66 kerja sama (42 pendidikan, 17 penelitian, 7 PkM) → <em>LKPS 2.a</em></li>
              <li><strong>Tingkat:</strong> 5 internasional, 45 nasional, 16 lokal/wilayah</li>
              <li><strong>Mitra Strategis:</strong> St. John's University Taiwan, PT Ericsson, PT Huawei, PT Telkomsel, PT NEC, PT MyRepublic, BRIN, Bank BRI</li>
              <li><strong>Analisis:</strong> Kerja sama pendidikan dominan nasional (37/42), perlu penguatan internasionalisasi</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 2a1 - Kerja Sama Pendidikan</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 2a2 - Kerja Sama Penelitian</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 2a3 - Kerja Sama PkM</a>
          </div>
          <div class="led-card">
            <h4>💰 Keuangan — Analisis</h4>
            <ul>
              <li><strong>Total Anggaran Rata-rata:</strong> Rp 27,24 M/tahun (UPPS), Rp 4,08 M/tahun (PS) → <em>LKPS 2.b</em></li>
              <li><strong>BOP per Mahasiswa:</strong> Rp 20,36 juta/tahun</li>
              <li><strong>Dana Penelitian:</strong> Rp 144,44 juta/tahun (80% internal, 20% eksternal nasional)</li>
              <li><strong>Dana PkM:</strong> Rp 88,16 juta/tahun (100% internal)</li>
              <li><strong>Analisis:</strong> Ketersediaan dana memadai, namun diversifikasi pendanaan eksternal perlu ditingkatkan</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 2b - Penggunaan Dana</a>
          </div>
        </div>
      </div>

      <!-- C.3 RELEVANSI PENDIDIKAN, PENELITIAN, DAN PKM -->
      <div class="ledps-criteria" id="ledps-c3">
        <div class="lkps-section ledps">
          <h3>📘 C.3 — Relevansi Pendidikan, Penelitian, dan PkM</h3>
          <div class="led-card">
            <h4>📚 Kurikulum — Evaluasi</h4>
            <ul>
              <li><strong>Total:</strong> 53 MK, 150 SKS (80 SKS praktik = 53,33%) → <em>LKPS 3.a.1</em></li>
              <li><strong>Evaluasi:</strong> 2020, 2021, 2024 (melibatkan dosen, alumni, industri, pakar)</li>
              <li><strong>Profil Lulusan:</strong> 12 profil (IT Engineer, Network Engineer, RF Planner, dll.)</li>
              <li><strong>CPL:</strong> 12 CPL sesuai 4 standar kompetensi lulusan</li>
              <li><strong>RPS:</strong> 100% MK memiliki RPS dengan 9 komponen lengkap</li>
              <li><strong>Analisis:</strong> Kurikulum vokasi kuat, perlu penguatan closed-loop CPL</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 3a1 - Kurikulum</a>
          </div>
          <div class="led-card">
            <h4>🔬 Penelitian — Evaluasi</h4>
            <ul>
              <li><strong>Total:</strong> 45 penelitian (14→13→18) → <em>LKPS 3.b</em></li>
              <li><strong>Sumber Dana:</strong> 36 internal (80%), 9 eksternal nasional (20%), 0 luar negeri</li>
              <li><strong>Keterlibatan Mahasiswa:</strong> 12/45 (26,67%) → <em>LKPS 6.h.1</em></li>
              <li><strong>Tema:</strong> AI/ML, IoT, LoRa, 4G/5G, komunikasi nirkabel, antena, cloud computing</li>
              <li><strong>Analisis:</strong> Produktivitas baik, namun pendanaan eksternal dan keterlibatan mahasiswa perlu ditingkatkan</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 3b - Penelitian DTPS</a>
          </div>
          <div class="led-card">
            <h4>🤝 PkM — Evaluasi</h4>
            <ul>
              <li><strong>Total:</strong> 14 kegiatan (2→6→6) → <em>LKPS 3.c</em></li>
              <li><strong>Pendanaan:</strong> 100% internal/mandiri</li>
              <li><strong>Keterlibatan Mahasiswa:</strong> 7 PkM melibatkan mahasiswa → <em>LKPS 6.i</em></li>
              <li><strong>Contoh:</strong> Smart Aquaculture LoRa, Aplikasi Bank Sampah, Sistem Keamanan IoT, Website Desa Wisata</li>
              <li><strong>Analisis:</strong> Dampak masyarakat baik, perlu hilirisasi dan pendanaan eksternal</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link"> Bukti: Tabel 3c - PkM DTPS</a>
            <a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z" target="_blank" class="evidence-link">📂 Bukti: Tabel 4g - Produk Diadopsi</a>
          </div>
        </div>
      </div>

      <!-- C.4 SUMBER DAYA MANUSIA -->
      <div class="ledps-criteria" id="ledps-c4">
        <div class="lkps-section ledps">
          <h3>👨🏫 C.4 — Sumber Daya Manusia</h3>
          <div class="led-card">
            <h4>📊 Profil DTPS — Analisis</h4>
            <ul>
              <li><strong>Total DTPS:</strong> 11 dosen → <em>LKPS 4.a</em></li>
              <li><strong>Doktor:</strong> 3 (27,27%) — perlu peningkatan melalui studi lanjut</li>
              <li><strong>Lektor Kepala:</strong> 4 (36,36%) — mayoritas Lektor</li>
              <li><strong>Sertifikasi:</strong> 100% DTPS memiliki sertifikat kompetensi/profesi/industri</li>
              <li><strong>Rasio Mhs:DTPS:</strong> 1:17,18 — ideal</li>
              <li><strong>Analisis:</strong> SDM kompeten, perlu percepatan Guru Besar dan doktor</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 4a - Profil DTPS</a>
          </div>
          <div class="led-card">
            <h4>⚖️ Beban Kerja — Evaluasi</h4>
            <p><strong>Rata-rata BKD:</strong> 14,77 SKS/semester (rentang ideal 12-16 SKS)</p>
            <p>Komposisi: 9,98 SKS pendidikan, 2,22 SKS penelitian, 1,70 SKS PkM, 0,88 SKS tugas tambahan</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 4c - Beban Kerja DTPS</a>
          </div>
          <div class="led-card">
            <h4>📈 Kinerja Tridharma — Analisis</h4>
            <ul>
              <li><strong>Publikasi:</strong> 220 (73 JNT, 12 JIB, 92 Prosiding Nas, 33 Prosiding Intl) → <em>LKPS 4.e</em></li>
              <li><strong>Luaran:</strong> 3 Paten, 36 HKI, 4 TTG, 14 Buku/Book Chapter → <em>LKPS 4.f</em></li>
              <li><strong>Produk Diadopsi:</strong> 13 produk/jasa → <em>LKPS 4.g</em></li>
              <li><strong>Rekognisi:</strong> 43 rekognisi (10 dari 11 DTPS = 90,91%) → <em>LKPS 4.j</em></li>
              <li><strong>Analisis:</strong> Produktivitas tinggi, perlu penguatan rekognisi internasional</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 4e - Publikasi DTPS</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 4f - Luaran DTPS</a>
            <a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z" target="_blank" class="evidence-link">📂 Bukti: Tabel 4g - Produk Diadopsi (13)</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 4j - Rekognisi DTPS</a>
          </div>
        </div>
      </div>

      <!-- C.5 SARANA, PRASARANA, DAN K3L -->
      <div class="ledps-criteria" id="ledps-c5">
        <div class="lkps-section ledps">
          <h3>💰 C.5 — Sarana, Prasarana, dan Keselamatan Kesehatan Kerja dan Lingkungan (K3L)</h3>
          <div class="led-card">
            <h4>🔧 Sarana Pembelajaran — Evaluasi</h4>
            <ul>
              <li><strong>Laboratorium:</strong> 7 lab + 1 bengkel (Elektronika, Transmisi, Telekomunikasi, Mikrokontroler, Komunikasi Data, Jaringan Broadband, Smartlab) → <em>LKPS 5.a</em></li>
              <li><strong>Ruang Kelas:</strong> 12 ruang</li>
              <li><strong>Perangkat Lunak:</strong> Software pembelajaran lengkap</li>
              <li><strong>Akses Digital:</strong> LMS, SIAKAD, perpustakaan digital, jurnal internasional</li>
              <li><strong>Analisis:</strong> Sarpras memadai, perlu pemutakhiran berkelanjutan sesuai perkembangan teknologi</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link"> Bukti: Tabel 5a - Sarpras & Lab</a>
          </div>
          <div class="led-card">
            <h4>⚠️ K3L — Evaluasi</h4>
            <ul>
              <li><strong>Dokumen:</strong> 17 dokumen K3L (Pedoman, SOP, Laporan) → <em>LKPS 5.b</em></li>
              <li><strong>Fasilitas:</strong> 12 item (APAR, Hidran, Ambulance, APD, P3K, Jalur Evakuasi) → <em>LKPS 5.c</em></li>
              <li><strong>Status:</strong> Seluruhnya terawat dan berfungsi</li>
              <li><strong>Analisis:</strong> Implementasi K3L baik, perlu audit berkala dan sosialisasi berkelanjutan</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 5b - Dokumen K3L</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link"> Bukti: Tabel 5c - Fasilitas K3L</a>
          </div>
        </div>
      </div>

      <!-- C.6 MAHASISWA DAN LUARAN MAHASISWA -->
      <div class="ledps-criteria" id="ledps-c6">
        <div class="lkps-section ledps">
          <h3>🎓 C.6 — Mahasiswa dan Luaran Mahasiswa</h3>
          <div class="led-card">
            <h4>👨‍🎓 Mahasiswa — Analisis</h4>
            <ul>
              <li><strong>Mahasiswa Aktif:</strong> 189 (TS) → <em>LKPS 6.a</em></li>
              <li><strong>Mahasiswa Asing:</strong> 13 (1 FT, 12 PT dari Turki dan Malaysia)</li>
              <li><strong>IPK Rata-rata:</strong> 3,46 (TS-2: 3,49, TS-1: 3,45, TS: 3,43)</li>
              <li><strong>Masa Studi:</strong> 4,06 tahun</li>
              <li><strong>Kelulusan Tepat Waktu:</strong> 95,025%</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 6a - Mahasiswa</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 6b - IPK Lulusan</a>
          </div>
          <div class="led-card">
            <h4>🏆 Prestasi & Luaran — Analisis</h4>
            <ul>
              <li><strong>Prestasi Akademik:</strong> 10 (2 internasional, 8 nasional) → <em>LKPS 6.c.1</em></li>
              <li><strong>Prestasi Nonakademik:</strong> 9 (1 internasional, 5 nasional, 3 wilayah) → <em>LKPS 6.c.2</em></li>
              <li><strong>Publikasi Mahasiswa:</strong> 126 (34 JNT, 1 JIB, 91 Prosiding) → <em>LKPS 6.e.2</em></li>
              <li><strong>Luaran HKI:</strong> 16 HKI, 1 TTG, 2 Buku → <em>LKPS 6.e.3</em></li>
              <li><strong>Produk Diadopsi:</strong> 16 produk/jasa mahasiswa → <em>LKPS 6.e.4</em></li>
              <li><strong>Analisis:</strong> Luaran mahasiswa sangat produktif, perlu peningkatan eksposur internasional</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 6c1 - Prestasi Akademik</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 6c2 - Prestasi Nonakademik</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 6e2 - Publikasi Mahasiswa</a>
            <a href="https://drive.google.com/drive/folders/1gj3fyC_mO2c6pDTNRzhnlPcIE4_pKBYS" target="_blank" class="evidence-link">📂 Bukti: Tabel 6e4 - Produk Mahasiswa (16)</a>
          </div>
          <div class="led-card">
            <h4>📈 Tracer Study — Evaluasi</h4>
            <ul>
              <li><strong>Populasi:</strong> 80 lulusan | <strong>Terlacak:</strong> 61 (76,25%) → <em>LKPS 6.f.1</em></li>
              <li><strong>Waktu Tunggu:</strong> 55,74% &lt;3 bulan, 44,26% 3-18 bulan, 0% &gt;18 bulan</li>
              <li><strong>Kesesuaian Bidang:</strong> 70,49% tinggi, 18,03% sedang, 11,48% rendah → <em>LKPS 6.f.2</em></li>
              <li><strong>Tempat Kerja:</strong> 63,93% nasional, 16,39% multinasional, 19,67% lokal → <em>LKPS 6.g.1</em></li>
              <li><strong>Analisis:</strong> Daya saing lulusan baik, perlu peningkatan response rate tracer</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link"> Bukti: Tabel 6f1 - Waktu Tunggu</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 6f2 - Kesesuaian Bidang</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 6g1 - Tempat Kerja</a>
          </div>
          <div class="led-card">
            <h4>⭐ Kepuasan Pengguna — Evaluasi</h4>
            <p><strong>45 responden</strong> menilai 7 aspek kompetensi lulusan → <em>LKPS 6.g.2</em></p>
            <ul>
              <li>Teknologi Informasi: 82,2% Sangat Baik</li>
              <li>Etika: 80,0% Sangat Baik</li>
              <li>Komunikasi: 77,78% Sangat Baik</li>
              <li>Kerja Sama Tim: 75,6% Sangat Baik</li>
              <li>Keahlian Bidang: 73,3% Sangat Baik</li>
              <li>Pengembangan Diri: 73,3% Sangat Baik</li>
              <li>Bahasa Asing: 71,1% Sangat Baik ⚠️ (11,1% Cukup)</li>
            </ul>
            <p><strong>RTL:</strong> Kelas intensif bahasa asing, sertifikasi TOEFL/TOEIC, program imersi.</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 6g2 - Kepuasan Pengguna</a>
          </div>
        </div>
      </div>

      <!-- C.7 SISTEM PENJAMINAN MUTU -->
      <div class="ledps-criteria" id="ledps-c7">
        <div class="lkps-section ledps">
          <h3>🔄 C.7 — Sistem Penjaminan Mutu</h3>
          <div class="led-card">
            <h4>📋 Struktur SPMI</h4>
            <ul>
              <li><strong>Tingkat Institusi:</strong> Unit Penjaminan Mutu (UPM) di bawah PPMPP</li>
              <li><strong>Tingkat Jurusan:</strong> Gugus Penjamin Mutu (GPM) sejak 2023</li>
              <li><strong>SK GPM:</strong> SK Direktur No. 147/PL3/JM/2025</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="evidence-link">📂 Bukti: Tabel 7a - Dokumen SPMI</a>
          </div>
          <div class="led-card">
            <h4>🔄 Siklus PPEPP — Evaluasi</h4>
            <ul>
              <li><strong>Penetapan:</strong> Standar mutu melalui SK Rektor/Dekan → <em>LKPS 7.a</em></li>
              <li><strong>Pelaksanaan:</strong> Program kerja mengacu standar (LMS, SIAKAD, SIMLitmas)</li>
              <li><strong>Evaluasi:</strong> AMI tahunan, EDOM semesteran, Monev PBM → <em>LKPS 7.b</em></li>
              <li><strong>Pengendalian:</strong> RTM tingkat jurusan untuk tindak lanjut</li>
              <li><strong>Peningkatan:</strong> Revisi standar dan strategi berdasarkan hasil evaluasi</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank" class="evidence-link">📂 Bukti: Tabel 7b - Laporan AMI</a>
            <a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank" class="evidence-link">📂 Bukti: Tabel 7b - Notulensi RTM</a>
            <a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank" class="evidence-link">📂 Bukti: Tabel 7b - Dokumen RTL</a>
          </div>
          <div class="led-card">
            <h4>⭐ Kepuasan Stakeholder — Evaluasi</h4>
            <p>Survei kepuasan dilakukan terhadap mahasiswa, dosen, tendik, dan pengguna lulusan. Hasil menunjukkan persepsi positif dengan area peningkatan pada layanan SDM, kemahasiswaan, dan sarana-prasarana.</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Tabel 7 - Survei Stakeholder</a>
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
                <h4>💪 Strengths (Kekuatan)</h4>
                <ul>
                  <li>VMTS linear PNJ→JTE→PSBM</li>
                  <li>Kekhasan Broadband Multimedia</li>
                  <li>Kurikulum vokasi kuat (53,33% praktik)</li>
                  <li>66 kerja sama tridharma</li>
                  <li>SDM kuat (90,91% Lektor+, 100% sertifikasi)</li>
                  <li>Tridharma produktif (45 penelitian, 14 PkM)</li>
                  <li>Kinerja lulusan baik (IPK 3,46, 80,32% nasional+)</li>
                  <li>SPMI berjalan (PPEPP, AMI, RTM)</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses (Kelemahan)</h4>
                <ul>
                  <li>Internasionalisasi belum sekuat nasional</li>
                  <li>Dokumentasi CPL/CPMK perlu diperkuat</li>
                  <li>Pendanaan penelitian 80% internal</li>
                  <li>Keterlibatan mhs dalam penelitian 26,67%</li>
                  <li>Belum ada Guru Besar</li>
                  <li>Publikasi bereputasi belum merata</li>
                  <li>Bahasa asing perlu penguatan</li>
                  <li>Pemutakhiran fasilitas berkelanjutan</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities (Peluang)</h4>
                <ul>
                  <li>Transformasi digital & 5G/6G</li>
                  <li>IoT, AI, cloud computing, Big Data</li>
                  <li>Hibah nasional (BIMA, DRTPM)</li>
                  <li>Kebutuhan DUDI broadband</li>
                  <li>Program Merdeka Belajar</li>
                  <li>Jejaring alumni & pengguna</li>
                  <li>Sertifikasi kompetensi internasional</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats (Ancaman)</h4>
                <ul>
                  <li>Perubahan teknologi cepat</li>
                  <li>Persaingan PT sejenis</li>
                  <li>Tuntutan kompetensi DUDI dinamis</li>
                  <li>Regulasi DIKTI berubah</li>
                  <li>Persaingan hibah eksternal</li>
                  <li>Standar internasional meningkat</li>
                </ul>
              </div>
            </div>
          </div>

          <div class="led-card">
            <h4>🎯 6 Tujuan Strategis PSBM</h4>
            <div class="summary-grid">
              <div class="summary-card" style="border-left-color: #e65100;">
                <div class="sc-label">Tujuan 1</div>
                <div class="sc-value" style="font-size:0.85rem;">Memperkuat relevansi & mutu pendidikan</div>
                <div class="sc-desc">Indikator: 100% CPL terukur</div>
              </div>
              <div class="summary-card" style="border-left-color: #e65100;">
                <div class="sc-label">Tujuan 2</div>
                <div class="sc-value" style="font-size:0.85rem;">Meningkatkan penelitian & hilirisasi</div>
                <div class="sc-desc">Target: ≥40% pendanaan eksternal</div>
              </div>
              <div class="summary-card" style="border-left-color: #e65100;">
                <div class="sc-label">Tujuan 3</div>
                <div class="sc-value" style="font-size:0.85rem;">Meningkatkan kualitas SDM</div>
                <div class="sc-desc">Target: 5 doktor, 50% LK</div>
              </div>
              <div class="summary-card" style="border-left-color: #e65100;">
                <div class="sc-label">Tujuan 4</div>
                <div class="sc-value" style="font-size:0.85rem;">Memperluas internasionalisasi</div>
                <div class="sc-desc">Target: ≥5 kerja sama intl</div>
              </div>
              <div class="summary-card" style="border-left-color: #e65100;">
                <div class="sc-label">Tujuan 5</div>
                <div class="sc-value" style="font-size:0.85rem;">Meningkatkan daya saing lulusan</div>
                <div class="sc-desc">Target: ≥80% sesuai bidang</div>
              </div>
              <div class="summary-card" style="border-left-color: #e65100;">
                <div class="sc-label">Tujuan 6</div>
                <div class="sc-value" style="font-size:0.85rem;">Memperkuat budaya mutu</div>
                <div class="sc-desc">Target: Siklus PPEPP berjalan</div>
              </div>
            </div>
          </div>

          <div class="led-card">
            <h4>📘 6 Program Pengembangan Berkelanjutan</h4>
            <div class="table-responsive">
              <table class="lkps-table">
                <thead><tr><th>No</th><th>Program</th><th>Strategi</th><th>Target</th><th>PIC</th><th>Anggaran</th></tr></thead>
                <tbody>
                  <tr><td>1</td><td><strong>Penguatan Closed-Loop CPL</strong></td><td>WO</td><td>100% CPL terukur & ditindaklanjuti</td><td>Kurikulum/GPM</td><td>Rp 30 juta</td></tr>
                  <tr><td>2</td><td><strong>Peningkatan Pendanaan Eksternal Penelitian</strong></td><td>WO</td><td>≥40% pendanaan eksternal (2026)</td><td>P3M</td><td>Rp 50 juta</td></tr>
                  <tr><td>3</td><td><strong>Integrasi Penelitian DTPS dengan Mahasiswa</strong></td><td>WO</td><td>≥40% penelitian libatkan mhs</td><td>P3M/Kaprodi</td><td>Rp 40 juta</td></tr>
                  <tr><td>4</td><td><strong>Percepatan JAFA & Studi Lanjut</strong></td><td>ST</td><td>5 doktor, 50% LK, 1 GB</td><td>Kajur</td><td>Rp 200 juta</td></tr>
                  <tr><td>5</td><td><strong>Peningkatan Response Rate Tracer</strong></td><td>WT</td><td>≥80% response rate</td><td>CDC/GPM</td><td>Rp 20 juta</td></tr>
                  <tr><td>6</td><td><strong>Internasionalisasi Kerja Sama & Publikasi</strong></td><td>SO</td><td>≥5 MoU intl, ≥10 publikasi Scopus</td><td>Kajur/P3M</td><td>Rp 80 juta</td></tr>
                </tbody>
              </table>
            </div>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"><span class="btn-icon">📕</span> Buka Bukti: BAB III - Program Pengembangan</a>
          </div>

          <div class="led-card">
            <h4>🔄 Monitoring & PPEPP</h4>
            <div class="summary-grid">
              <div class="summary-card" style="border-left-color: #e65100;">
                <div class="sc-label">🔍 AMI</div>
                <div class="sc-value" style="font-size:0.95rem;">Audit Mutu Internal</div>
                <div class="sc-desc">Audit internal tahunan terhadap 7 kriteria</div>
              </div>
              <div class="summary-card" style="border-left-color: #e65100;">
                <div class="sc-label">📝 RTM</div>
                <div class="sc-value" style="font-size:0.95rem;">Rapat Tinjauan Manajemen</div>
                <div class="sc-desc">Tinjauan hasil AMI oleh pimpinan</div>
              </div>
              <div class="summary-card" style="border-left-color: #e65100;">
                <div class="sc-label">📋 RTL</div>
                <div class="sc-value" style="font-size:0.95rem;">Rencana Tindak Lanjut</div>
                <div class="sc-desc">15 temuan AMI dengan RTL terdokumentasi</div>
              </div>
            </div>
            <a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank" class="table-link-btn"><span class="btn-icon">🔍</span> Buka Bukti: Tabel 7b - AMI</a>
            <a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank" class="table-link-btn secondary"><span class="btn-icon">📝</span> Buka Bukti: Tabel 7b - RTM</a>
            <a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank" class="table-link-btn success"><span class="btn-icon">📋</span> Buka Bukti: Tabel 7b - RTL</a>
          </div>
        </div>
      </div>

    </div>

  </div>
</div>

<script>
// ===== NAVIGATION UTAMA =====
function showEvPanel(id, btn) {
  document.querySelectorAll('.ev-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.ev-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  
  if (id === 'sesi1') {
    showLkpsTable('t1', document.querySelector('#lkpsNav button'));
  } else if (id === 'sesi2') {
    showLedpsCriteria('c1', document.querySelector('#ledpsNav button'));
  }
  
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

// ===== SUB-NAV LKPS (Tabel 1-7) =====
function showLkpsTable(id, btn) {
  document.querySelectorAll('.lkps-table-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('lkps-' + id).classList.add('active');
  const nav = btn.parentElement;
  nav.querySelectorAll('button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}

// ===== SUB-NAV LEDPS (C.1-C.7 + BAB III) =====
function showLedpsCriteria(id, btn) {
  document.querySelectorAll('.ledps-criteria').forEach(p => p.classList.remove('active'));
  document.getElementById('ledps-' + id).classList.add('active');
  const nav = btn.parentElement;
  nav.querySelectorAll('button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  const sesi1Panel = document.getElementById('panel-sesi1');
  if (sesi1Panel) sesi1Panel.classList.add('active');
  
  const firstLkpsTable = document.getElementById('lkps-t1');
  if (firstLkpsTable) firstLkpsTable.classList.add('active');
  
  const firstLedpsCriteria = document.getElementById('ledps-c1');
  if (firstLedpsCriteria) firstLedpsCriteria.classList.add('active');
});
</script>

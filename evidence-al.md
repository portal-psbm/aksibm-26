---
layout: default
title: Evidence AL
permalink: /evidence-al/
---

<style>
/* ===== COMPACT CABINET ===== */
.ev-cabinet { 
  background: linear-gradient(180deg, #e3f2fd 0%, #bbdefb 100%); 
  padding: 12px 12px 0 12px; 
  border-radius: 12px 12px 0 0; 
  box-shadow: 0 4px 16px rgba(0,0,0,0.08); 
  position: relative; 
  border: 1px solid #bbdefb; 
  border-bottom: none; 
}

.ev-shelf { 
  display: flex; 
  gap: 4px; 
  padding: 0 4px; 
  overflow-x: auto; 
  scrollbar-width: none;
}
.ev-shelf::-webkit-scrollbar { display: none; }

.ev-tab { 
  flex: 1;
  padding: 10px 8px 14px 8px; 
  background: white;
  border-radius: 8px 8px 0 0;
  border: 1px solid #e0e0e0;
  border-bottom: none;
  cursor: pointer;
  text-align: center;
  font-weight: 600;
  font-size: 0.75rem;
  color: #555;
  transition: all 0.3s ease;
  transform: translateY(2px);
}
.ev-tab:hover { 
  background: #f1f5f9; 
  transform: translateY(0);
  color: #0d47a1;
}
.ev-tab.active { 
  background: #0d47a1; 
  color: white; 
  transform: translateY(-4px); 
  z-index: 10; 
  box-shadow: 0 -4px 12px rgba(13, 71, 161, 0.2);
}
.ev-tab.sesi2.active { 
  background: #2e7d32; 
}

.ev-content { 
  background: white; 
  border: 1px solid #e0e0e0; 
  border-top: 3px solid #0d47a1; 
  border-radius: 0 0 12px 12px; 
  padding: 16px; 
  min-height: 400px; 
  box-shadow: 0 4px 12px rgba(0,0,0,0.04); 
}

.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

/* ===== COMPACT SESSION HEADER ===== */
.session-header { 
  padding: 12px 16px; 
  border-radius: 8px; 
  margin-bottom: 12px; 
  color: white; 
}
.session-header.sesi1 { background: linear-gradient(135deg, #1565c0, #0d47a1); }
.session-header.sesi2 { background: linear-gradient(135deg, #388e3c, #2e7d32); }
.session-header h2 { 
  margin: 0 0 4px 0; 
  font-size: 1.1rem; 
  font-weight: 700;
}
.session-header .subtitle { 
  font-size: 0.78rem; 
  opacity: 0.9; 
  margin: 0;
}
.session-header .tag { 
  display: inline-block; 
  background: rgba(255,255,255,0.2); 
  padding: 2px 8px; 
  border-radius: 10px; 
  font-size: 0.65rem; 
  font-weight: 700; 
  margin-bottom: 6px;
}

/* ===== COMPACT INFO BOX ===== */
.info-box { 
  background: #e3f2fd; 
  border-left: 3px solid #0d47a1; 
  padding: 8px 12px; 
  border-radius: 4px; 
  margin-bottom: 12px; 
  font-size: 0.78rem; 
  color: #0d47a1; 
}
.info-box.ledps { 
  background: #e8f5e9; 
  border-left-color: #2e7d32; 
  color: #2e7d32; 
}

/* ===== COMPACT SUB-NAV ===== */
.criteria-nav { 
  display: flex; 
  gap: 3px; 
  margin-bottom: 12px; 
  flex-wrap: wrap; 
  padding: 6px;
  background: #f8fafc;
  border-radius: 6px;
  border: 1px solid #e0e0e0;
}
.criteria-nav button { 
  padding: 5px 10px; 
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 5px;
  cursor: pointer; 
  font-weight: 600; 
  color: #555; 
  font-size: 0.72rem;
  transition: all 0.2s;
}
.criteria-nav button:hover { 
  border-color: #0d47a1;
  color: #0d47a1;
}
.criteria-nav button.active { 
  background: #0d47a1;
  color: white;
  border-color: #0d47a1;
}
.criteria-nav.ledps-nav button.active { 
  background: #2e7d32;
  border-color: #2e7d32;
}

/* ===== COMPACT SECTIONS ===== */
.lkps-section { margin-bottom: 14px; }
.lkps-section h3 { 
  color: #0d47a1; 
  border-left: 3px solid #0d47a1; 
  padding-left: 8px; 
  margin: 0 0 8px 0; 
  font-size: 0.92rem; 
  font-weight: 700;
}
.lkps-section.ledps h3 { 
  color: #2e7d32; 
  border-left-color: #2e7d32; 
}

/* ===== COMPACT TABLES ===== */
.table-responsive { 
  overflow-x: auto; 
  border: 1px solid #e0e0e0; 
  border-radius: 6px; 
  margin-bottom: 10px; 
}
.lkps-table { 
  width: 100%; 
  border-collapse: collapse; 
  font-size: 0.75rem; 
  min-width: 500px; 
}
.lkps-table th, .lkps-table td { 
  border: 1px solid #e0e0e0; 
  padding: 5px 8px; 
  text-align: left; 
}
.lkps-table th { 
  background: #f1f5f9; 
  font-weight: 600; 
  color: #0d47a1; 
  font-size: 0.72rem;
}
.lkps-table tr:nth-child(even) { background: #f8fafc; }
.highlight-data { background: #fff8e1 !important; font-weight: 600; color: #e65100; }
.link-cell a { color: #0d47a1; text-decoration: none; font-weight: 600; font-size: 0.72rem; }

/* ===== COMPACT SUMMARY CARDS ===== */
.summary-grid { 
  display: grid; 
  grid-template-columns: repeat(auto-fit, minmax(120px, 1fr)); 
  gap: 6px; 
  margin: 10px 0; 
}
.summary-card { 
  background: white; 
  border: 1px solid #e0e0e0; 
  border-left: 3px solid #0d47a1; 
  border-radius: 6px; 
  padding: 8px; 
}
.summary-card .sc-label { 
  font-size: 0.65rem; 
  color: #666; 
  text-transform: uppercase; 
}
.summary-card .sc-value { 
  font-size: 1.1rem; 
  font-weight: 800; 
  color: #0d47a1; 
  margin: 2px 0; 
}
.summary-card .sc-desc { 
  font-size: 0.68rem; 
  color: #555; 
}

/* ===== COMPACT LINK BUTTONS ===== */
.table-link-btn { 
  display: inline-flex; 
  align-items: center; 
  gap: 4px; 
  padding: 5px 10px; 
  background: #0d47a1; 
  color: white; 
  border-radius: 5px; 
  text-decoration: none; 
  font-weight: 600; 
  font-size: 0.72rem; 
  margin: 3px 3px 3px 0; 
  transition: all 0.2s;
}
.table-link-btn:hover { 
  background: #1565c0; 
  transform: translateY(-1px);
}
.table-link-btn.secondary { background: #546e7a; }
.table-link-btn.secondary:hover { background: #607d8b; }
.table-link-btn.success { background: #2e7d32; }
.table-link-btn.success:hover { background: #388e3c; }

/* ===== COMPACT LED CARDS ===== */
.led-card { 
  background: white; 
  border: 1px solid #e0e0e0; 
  border-radius: 6px; 
  padding: 10px 12px; 
  margin-bottom: 8px; 
  border-left: 3px solid #2e7d32; 
}
.led-card h4 { 
  color: #2e7d32; 
  margin: 0 0 6px 0; 
  font-size: 0.85rem; 
  font-weight: 700;
}
.led-card p, .led-card ul { 
  color: #555; 
  font-size: 0.78rem; 
  line-height: 1.4; 
  margin: 0 0 6px 0; 
}
.led-card ul { padding-left: 16px; }
.led-card li { margin-bottom: 2px; }

.evidence-link { 
  display: inline-flex; 
  align-items: center; 
  gap: 4px; 
  background: #e8f5e9; 
  color: #2e7d32; 
  padding: 3px 8px; 
  border-radius: 4px; 
  font-size: 0.7rem; 
  font-weight: 600; 
  text-decoration: none; 
  margin: 4px 4px 0 0;
}
.evidence-link:hover { background: #c8e6c9; }

/* ===== COMPACT SWOT ===== */
.swot-grid { 
  display: grid; 
  grid-template-columns: 1fr 1fr; 
  gap: 8px; 
  margin: 10px 0; 
}
.swot-card { 
  padding: 10px; 
  border-radius: 6px; 
  border: 2px solid; 
}
.swot-card.strength { background: #e8f5e9; border-color: #4caf50; }
.swot-card.weakness { background: #fff3e0; border-color: #ff9800; }
.swot-card.opportunity { background: #e3f2fd; border-color: #2196f3; }
.swot-card.threat { background: #ffebee; border-color: #f44336; }
.swot-card h4 { 
  margin: 0 0 6px 0; 
  font-size: 0.82rem; 
  font-weight: 700;
}
.swot-card ul { 
  margin: 0; 
  padding-left: 14px; 
  font-size: 0.75rem; 
}
.swot-card ul li { padding: 1px 0; }

@media (max-width: 767px) {
  .ev-tab { font-size: 0.68rem; padding: 8px 6px 12px 6px; }
  .ev-content { padding: 12px; }
  .summary-grid { grid-template-columns: 1fr 1fr; }
  .swot-grid { grid-template-columns: 1fr; }
  .session-header h2 { font-size: 1rem; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('sesi1', this)">📊 SESI 1: LKPS</div>
    <div class="ev-tab sesi2" onclick="showEvPanel('sesi2', this)">📕 SESI 2: LEDPS</div>
  </div>

  <div class="ev-content">

    <!-- ========== SESI 1: LKPS ========== -->
    <div class="ev-panel active" id="panel-sesi1">
      <div class="session-header sesi1">
        <span class="tag">DATA KUANTITATIF</span>
        <h2>📊 SESI 1 — LKPS</h2>
        <div class="subtitle">Tabel 1-7 | Data 3 Tahun Terakhir</div>
      </div>

      <div class="info-box">
        <strong>ℹ️</strong> Klik sub-tab di bawah untuk melihat tabel LKPS dengan link bukti Google Drive.
      </div>

      <!-- Sub-nav -->
      <div class="criteria-nav" id="lkpsNav">
        <button class="active" onclick="showLkpsTable('t1', this)">T1: VMTS</button>
        <button onclick="showLkpsTable('t2', this)">T2: Kerja Sama</button>
        <button onclick="showLkpsTable('t3', this)">T3: Kurikulum</button>
        <button onclick="showLkpsTable('t4', this)">T4: SDM</button>
        <button onclick="showLkpsTable('t5', this)">T5: Sarpras</button>
        <button onclick="showLkpsTable('t6', this)">T6: Luaran</button>
        <button onclick="showLkpsTable('t7', this)">T7: SPMI</button>
      </div>

      <!-- TABEL 1 -->
      <div class="lkps-table-panel active" id="lkps-t1">
        <div class="lkps-section">
          <h3>📑 Tabel 1: VMTS</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>No</th><th>Jenis</th><th>SK</th><th>Link</th></tr></thead>
              <tbody>
                <tr><td>1</td><td><strong>VMTS PT</strong></td><td>643/PL3/OT/2021</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank">📂 Buka</a></td></tr>
                <tr><td>2</td><td><strong>VMTS UPPS</strong></td><td>2585/PL3/OT/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1JiRWv_v_-pbrFTMl74JwQzJ1ZNnCpcOt" target="_blank">📂 Buka</a></td></tr>
                <tr><td>3</td><td><strong>Visi Keilmuan PS</strong></td><td>2589/PL3/KR.00/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf" target="_blank">📂 Buka</a></td></tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>

      <!-- TABEL 2 -->
      <div class="lkps-table-panel" id="lkps-t2">
        <div class="lkps-section">
          <h3>🤝 Tabel 2: Kerja Sama & Dana</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Pendidikan</div><div class="sc-value">42</div></div>
            <div class="summary-card"><div class="sc-label">Penelitian</div><div class="sc-value">17</div></div>
            <div class="summary-card"><div class="sc-label">PkM</div><div class="sc-value">7</div></div>
            <div class="summary-card"><div class="sc-label">Dana Rata-rata</div><div class="sc-value">27,24 M</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn">📂 Buka Bukti: Kerja Sama</a>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn">💰 Buka Bukti: Dana</a>
        </div>
      </div>

      <!-- TABEL 3 -->
      <div class="lkps-table-panel" id="lkps-t3">
        <div class="lkps-section">
          <h3>📘 Tabel 3: Kurikulum & Tridharma</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">MK</div><div class="sc-value">53</div></div>
            <div class="summary-card"><div class="sc-label">SKS</div><div class="sc-value">150</div></div>
            <div class="summary-card"><div class="sc-label">Penelitian</div><div class="sc-value">45</div></div>
            <div class="summary-card"><div class="sc-label">PkM</div><div class="sc-value">14</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn">📘 Buka Bukti: Kurikulum</a>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn secondary">🔬 Buka Bukti: Penelitian</a>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn secondary"> Buka Bukti: PkM</a>
        </div>
      </div>

      <!-- TABEL 4 -->
      <div class="lkps-table-panel" id="lkps-t4">
        <div class="lkps-section">
          <h3>👨‍ Tabel 4: SDM & Luaran</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">DTPS</div><div class="sc-value">11</div></div>
            <div class="summary-card"><div class="sc-label">Publikasi</div><div class="sc-value">220</div></div>
            <div class="summary-card"><div class="sc-label">Produk Diadopsi</div><div class="sc-value">13</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn">👨‍🏫 Buka Bukti: DTPS</a>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn secondary">📚 Buka Bukti: Publikasi</a>
          <a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z" target="_blank" class="table-link-btn success"> Buka Bukti: Produk Diadopsi</a>
        </div>
      </div>

      <!-- TABEL 5 -->
      <div class="lkps-table-panel" id="lkps-t5">
        <div class="lkps-section">
          <h3>💰 Tabel 5: Sarpras & K3L</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Prasarana</div><div class="sc-value">16</div></div>
            <div class="summary-card"><div class="sc-label">Dokumen K3L</div><div class="sc-value">17</div></div>
            <div class="summary-card"><div class="sc-label">Fasilitas K3L</div><div class="sc-value">12</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn">💰 Buka Bukti: Sarpras</a>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn secondary">️ Buka Bukti: K3L</a>
        </div>
      </div>

      <!-- TABEL 6 -->
      <div class="lkps-table-panel" id="lkps-t6">
        <div class="lkps-section">
          <h3>🎓 Tabel 6: Mahasiswa & Luaran</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Mahasiswa</div><div class="sc-value">189</div></div>
            <div class="summary-card"><div class="sc-label">IPK</div><div class="sc-value">3,46</div></div>
            <div class="summary-card"><div class="sc-label">Tracer</div><div class="sc-value">76,25%</div></div>
            <div class="summary-card"><div class="sc-label">Kesesuaian Kerja</div><div class="sc-value">70,49%</div></div>
          </div>
          <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="table-link-btn"> Buka Bukti: Mahasiswa</a>
          <a href="https://drive.google.com/drive/folders/1gj3fyC_mO2c6pDTNRzhnlPcIE4_pKBYS" target="_blank" class="table-link-btn success">📦 Buka Bukti: Produk Mhs (16)</a>
        </div>
      </div>

      <!-- TABEL 7 -->
      <div class="lkps-table-panel" id="lkps-t7">
        <div class="lkps-section">
          <h3>🔄 Tabel 7: SPMI</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>Tahap PPEPP</th><th>Link</th></tr></thead>
              <tbody>
                <tr><td><strong>Penetapan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank">📂 Buka</a></td></tr>
                <tr><td><strong>Pelaksanaan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank">📂 Buka</a></td></tr>
                <tr><td><strong>Evaluasi</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1ywPn4RexBzQjD6DXRT8DCXTEtemvcQLz" target="_blank">📂 Buka</a></td></tr>
                <tr><td><strong>Pengendalian</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1WFgIamM3JnSGZ-WAv-UOC1W22E0ondmV" target="_blank">📂 Buka</a></td></tr>
                <tr><td><strong>Peningkatan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank"> Buka</a></td></tr>
              </tbody>
            </table>
          </div>
          <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="table-link-btn">📋 Buka Bukti: SPMI</a>
          <a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank" class="table-link-btn secondary">🔍 Buka Bukti: AMI</a>
          <a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank" class="table-link-btn secondary">📝 Buka Bukti: RTM</a>
          <a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank" class="table-link-btn success">📈 Buka Bukti: RTL</a>
        </div>
      </div>

    </div>

    <!-- ========== SESI 2: LEDPS ========== -->
    <div class="ev-panel" id="panel-sesi2">
      <div class="session-header sesi2">
        <span class="tag">ANALISIS KUALITATIF</span>
        <h2>📕 SESI 2 — LEDPS</h2>
        <div class="subtitle">C.1-C.7 + BAB III | Analisis Naratif</div>
      </div>

      <div class="info-box ledps">
        <strong>️</strong> Klik sub-tab untuk melihat analisis per kriteria dengan link bukti.
      </div>

      <!-- Sub-nav -->
      <div class="criteria-nav ledps-nav" id="ledpsNav">
        <button class="active" onclick="showLedpsCriteria('c1', this)">C.1 VMTS</button>
        <button onclick="showLedpsCriteria('c2', this)">C.2 Akuntabilitas</button>
        <button onclick="showLedpsCriteria('c3', this)">C.3 Diklitpmas</button>
        <button onclick="showLedpsCriteria('c4', this)">C.4 SDM</button>
        <button onclick="showLedpsCriteria('c5', this)">C.5 Sarpras</button>
        <button onclick="showLedpsCriteria('c6', this)">C.6 Luaran</button>
        <button onclick="showLedpsCriteria('c7', this)">C.7 SPMI</button>
        <button onclick="showLedpsCriteria('bab3', this)" style="background:#fff3e0; color:#e65100; border:1px solid #ffcc80;">📕 BAB III</button>
      </div>

      <!-- C.1 -->
      <div class="ledps-criteria active" id="ledps-c1">
        <div class="lkps-section ledps">
          <h3>📑 C.1 — Diferensiasi Misi</h3>
          <div class="led-card">
            <h4>🎯 Visi Keilmuan</h4>
            <p><strong>"Menjadi Program Studi Unggul Bertaraf Internasional di Bidang Broadband Multimedia"</strong></p>
            <a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf" target="_blank" class="evidence-link">📂 Bukti: Visi Keilmuan</a>
          </div>
          <div class="led-card">
            <h4>🔧 Mekanisme</h4>
            <ul>
              <li>Internal: Dosen, mahasiswa, tendik</li>
              <li>Eksternal: Alumni, pengguna, pakar (FGD)</li>
              <li>SK: 954/PL3.9/HK.03/2020</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Mekanisme VMTS</a>
          </div>
        </div>
      </div>

      <!-- C.2 -->
      <div class="ledps-criteria" id="ledps-c2">
        <div class="lkps-section ledps">
          <h3>🏛️ C.2 — Akuntabilitas</h3>
          <div class="led-card">
            <h4> Kerja Sama</h4>
            <p>66 kerja sama (42 pendidikan, 17 penelitian, 7 PkM). Mitra: Ericsson, Huawei, Telkomsel, NEC, MyRepublic.</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: MoU & IA</a>
          </div>
          <div class="led-card">
            <h4>💰 Keuangan</h4>
            <p>Rp 27,24 M/tahun (UPPS), Rp 4,08 M/tahun (PS). BOP: Rp 20,36 juta/mhs/tahun.</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Keuangan</a>
          </div>
        </div>
      </div>

      <!-- C.3 -->
      <div class="ledps-criteria" id="ledps-c3">
        <div class="lkps-section ledps">
          <h3>📘 C.3 — Diklitpmas</h3>
          <div class="led-card">
            <h4>📚 Kurikulum</h4>
            <p>53 MK, 150 SKS (53,33% praktik). Dievaluasi 2020, 2021, 2024.</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Kurikulum</a>
          </div>
          <div class="led-card">
            <h4>🔬 Penelitian & PkM</h4>
            <p>45 penelitian (80% internal), 14 PkM (100% internal). 12/45 penelitian libatkan mhs (26,67%).</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Penelitian</a>
          </div>
        </div>
      </div>

      <!-- C.4 -->
      <div class="ledps-criteria" id="ledps-c4">
        <div class="lkps-section ledps">
          <h3>👨🏫 C.4 — SDM</h3>
          <div class="led-card">
            <h4>📊 Profil DTPS</h4>
            <ul>
              <li>11 dosen (3 doktor, 4 LK, 6 Lektor)</li>
              <li>100% bersertifikat</li>
              <li>BKD: 14,77 SKS</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: DTPS</a>
          </div>
          <div class="led-card">
            <h4>📈 Kinerja</h4>
            <p>220 publikasi, 13 produk diadopsi, 43 rekognisi (90,91% DTPS).</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Publikasi</a>
            <a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z" target="_blank" class="evidence-link">📦 Bukti: Produk</a>
          </div>
        </div>
      </div>

      <!-- C.5 -->
      <div class="ledps-criteria" id="ledps-c5">
        <div class="lkps-section ledps">
          <h3>💰 C.5 — Sarpras & K3L</h3>
          <div class="led-card">
            <h4>🔧 Sarana</h4>
            <p>7 lab + 1 bengkel, 12 ruang kelas. Software lengkap, akses LMS & SIAKAD.</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Sarpras</a>
          </div>
          <div class="led-card">
            <h4>⚠️ K3L</h4>
            <p>17 dokumen K3L, 12 fasilitas (APAR, hidran, ambulance, P3K).</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: K3L</a>
          </div>
        </div>
      </div>

      <!-- C.6 -->
      <div class="ledps-criteria" id="ledps-c6">
        <div class="lkps-section ledps">
          <h3>🎓 C.6 — Luaran</h3>
          <div class="led-card">
            <h4>👨‍🎓 Mahasiswa</h4>
            <ul>
              <li>189 aktif, 13 asing</li>
              <li>IPK: 3,46 | Masa studi: 4,06 tahun</li>
              <li>Kelulusan tepat waktu: 95,025%</li>
            </ul>
          </div>
          <div class="led-card">
            <h4>🏆 Prestasi & Luaran</h4>
            <ul>
              <li>19 prestasi (10 akademik, 9 nonakademik)</li>
              <li>126 publikasi mhs</li>
              <li>16 produk mhs diadopsi</li>
            </ul>
            <a href="https://drive.google.com/drive/folders/1gj3fyC_mO2c6pDTNRzhnlPcIE4_pKBYS" target="_blank" class="evidence-link"> Bukti: Produk Mhs</a>
          </div>
          <div class="led-card">
            <h4> Tracer Study</h4>
            <ul>
              <li>80 lulusan, 61 terlacak (76,25%)</li>
              <li>WT <3 bulan: 55,74%</li>
              <li>Kesesuaian tinggi: 70,49%</li>
              <li>Nasional+multinasional: 80,33%</li>
            </ul>
          </div>
          <div class="led-card">
            <h4>⭐ Kepuasan Pengguna</h4>
            <p>45 responden. TI: 82,2% | Etika: 80% | Bahasa asing: 71,1% (⚠️ 11,1% Cukup).</p>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Survei</a>
          </div>
        </div>
      </div>

      <!-- C.7 -->
      <div class="ledps-criteria" id="ledps-c7">
        <div class="lkps-section ledps">
          <h3>🔄 C.7 — SPMI</h3>
          <div class="led-card">
            <h4>📋 Struktur</h4>
            <p>UPM (institusi) + GPM (jurusan) sejak 2023. SK: 147/PL3/JM/2025.</p>
            <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="evidence-link">📂 Bukti: SPMI</a>
          </div>
          <div class="led-card">
            <h4>🔄 PPEPP</h4>
            <p>Penetapan → Pelaksanaan → Evaluasi → Pengendalian → Peningkatan. AMI + RTM + RTL berjalan.</p>
            <a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank" class="evidence-link">📂 Bukti: AMI</a>
            <a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank" class="evidence-link"> Bukti: RTM</a>
          </div>
        </div>
      </div>

      <!-- BAB III -->
      <div class="ledps-criteria" id="ledps-bab3">
        <div class="lkps-section ledps">
          <h3>📕 BAB III — Program Pengembangan</h3>
          
          <div class="led-card">
            <h4>📊 SWOT</h4>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths</h4>
                <ul>
                  <li>VMTS linear PNJ→JTE→PSBM</li>
                  <li>Kekhasan Broadband Multimedia</li>
                  <li>66 kerja sama tridharma</li>
                  <li>SDM kuat (90,91% Lektor+)</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses</h4>
                <ul>
                  <li>Internasionalisasi terbatas</li>
                  <li>Penelitian 80% internal</li>
                  <li>Keterlibatan mhs 26,67%</li>
                  <li>Bahasa asing perlu penguatan</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities</h4>
                <ul>
                  <li>5G/6G, IoT, AI</li>
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
                </ul>
              </div>
            </div>
          </div>

          <div class="led-card">
            <h4>🎯 6 Tujuan Strategis</h4>
            <div class="summary-grid">
              <div class="summary-card" style="border-left-color:#e65100;"><div class="sc-label">Tujuan 1</div><div class="sc-value" style="font-size:0.78rem;">Mutu Pendidikan</div></div>
              <div class="summary-card" style="border-left-color:#e65100;"><div class="sc-label">Tujuan 2</div><div class="sc-value" style="font-size:0.78rem;">Penelitian & Hilirisasi</div></div>
              <div class="summary-card" style="border-left-color:#e65100;"><div class="sc-label">Tujuan 3</div><div class="sc-value" style="font-size:0.78rem;">Kualitas SDM</div></div>
              <div class="summary-card" style="border-left-color:#e65100;"><div class="sc-label">Tujuan 4</div><div class="sc-value" style="font-size:0.78rem;">Internasionalisasi</div></div>
              <div class="summary-card" style="border-left-color:#e65100;"><div class="sc-label">Tujuan 5</div><div class="sc-value" style="font-size:0.78rem;">Daya Saing Lulusan</div></div>
              <div class="summary-card" style="border-left-color:#e65100;"><div class="sc-label">Tujuan 6</div><div class="sc-value" style="font-size:0.78rem;">Budaya Mutu</div></div>
            </div>
          </div>

          <div class="led-card">
            <h4> 6 Program Pengembangan</h4>
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
  document.getElementById('lkps-t1').classList.add('active');
  document.getElementById('ledps-c1').classList.add('active');
});
</script>

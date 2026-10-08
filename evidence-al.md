---
layout: default
title: Evidence AL
permalink: /evidence-al/
---

<style>
/* ===== CABINET ===== */
.ev-cabinet { 
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); 
  padding: 16px 16px 0 16px; 
  border-radius: 14px 14px 0 0; 
  box-shadow: 0 8px 32px rgba(102, 126, 234, 0.25);
  position: relative; 
  border: none; 
}

/* ===== MAIN TABS (SESI) ===== */
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
  flex: 1;
  padding: 10px 16px; 
  background: rgba(255,255,255,0.15); 
  backdrop-filter: blur(10px);
  border: 2px solid rgba(255,255,255,0.2);
  border-bottom: none;
  border-radius: 10px 10px 0 0;
  cursor: pointer; 
  text-align: center; 
  font-weight: 700; 
  font-size: 0.85rem; 
  color: rgba(255,255,255,0.9);
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}
.ev-tab:hover { 
  background: rgba(255,255,255,0.25); 
  transform: translateY(-2px);
  color: white;
}
.ev-tab.active { 
  background: white; 
  color: #0d47a1; 
  border-color: white;
  box-shadow: 0 -4px 12px rgba(0,0,0,0.1);
  transform: translateY(-4px);
}
.ev-tab .tab-icon { font-size: 1.2rem; }

/* ===== CONTENT ===== */
.ev-content { 
  background: #ffffff; 
  border: 1px solid #e0e0e0; 
  border-top: 3px solid #0d47a1; 
  border-radius: 0 0 14px 14px; 
  padding: 16px; 
  min-height: 400px; 
  box-shadow: 0 4px 16px rgba(0,0,0,0.06); 
}
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

/* ===== FILE OPEN BUTTON ===== */
.file-open-bar { 
  display: flex; 
  gap: 8px; 
  margin-bottom: 12px; 
  flex-wrap: wrap; 
}
.file-open-btn { 
  display: inline-flex; 
  align-items: center; 
  gap: 6px; 
  padding: 8px 14px; 
  background: linear-gradient(135deg, #4caf50 0%, #45a049 100%);
  color: white;
  border-radius: 6px; 
  text-decoration: none; 
  font-weight: 600; 
  font-size: 0.78rem; 
  transition: all 0.2s; 
  box-shadow: 0 2px 6px rgba(76, 175, 80, 0.3);
  border: none;
  cursor: pointer;
}
.file-open-btn:hover { 
  transform: translateY(-1px); 
  box-shadow: 0 4px 10px rgba(76, 175, 80, 0.4);
}
.file-open-btn.pdf { 
  background: linear-gradient(135deg, #c62828 0%, #b71c1c 100%);
  box-shadow: 0 2px 6px rgba(198, 40, 40, 0.3);
}
.file-open-btn.pdf:hover {
  box-shadow: 0 4px 10px rgba(198, 40, 40, 0.4);
}
.file-open-btn .btn-icon { font-size: 1rem; }

/* ===== SUB-NAV BUTTONS ===== */
.sub-nav { 
  display: flex; 
  gap: 6px; 
  margin-bottom: 12px; 
  flex-wrap: wrap; 
  padding: 8px; 
  background: #f8fafc;
  border-radius: 8px;
  border: 1px solid #e0e0e0;
}
.sub-nav button { 
  padding: 6px 12px; 
  background: white;
  border: 2px solid #e0e0e0; 
  border-radius: 6px;
  cursor: pointer; 
  font-weight: 600; 
  color: #555; 
  font-size: 0.75rem; 
  transition: all 0.2s;
}
.sub-nav button:hover { 
  border-color: #0d47a1;
  color: #0d47a1;
  transform: translateY(-1px);
}
.sub-nav button.active { 
  background: #0d47a1;
  color: white;
  border-color: #0d47a1;
  box-shadow: 0 2px 6px rgba(13, 71, 161, 0.3);
}

/* ===== COMPACT CARDS ===== */
.lkps-section { margin-bottom: 12px; }
.lkps-section h3 { 
  color: #0d47a1; 
  border-left: 3px solid #0d47a1; 
  padding-left: 8px; 
  margin: 0 0 8px 0; 
  font-size: 0.95rem; 
}

.compact-card { 
  background: white; 
  border: 1px solid #e0e0e0; 
  border-radius: 6px; 
  padding: 10px 12px; 
  margin-bottom: 8px;
  border-left: 3px solid #0d47a1;
  transition: all 0.2s;
}
.compact-card:hover {
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  transform: translateX(2px);
}
.compact-card h4 { 
  color: #0d47a1; 
  margin: 0 0 4px 0; 
  font-size: 0.85rem; 
}
.compact-card p, .compact-card ul { 
  color: #555; 
  font-size: 0.78rem; 
  line-height: 1.4; 
  margin: 0 0 4px 0; 
}
.compact-card ul { padding-left: 16px; }
.compact-card li { margin-bottom: 2px; }

/* ===== TABLES ===== */
.table-responsive { overflow-x: auto; border: 1px solid #e0e0e0; border-radius: 6px; margin-bottom: 8px; }
.lkps-table { width: 100%; border-collapse: collapse; font-size: 0.75rem; min-width: 500px; }
.lkps-table th, .lkps-table td { border: 1px solid #e0e0e0; padding: 6px 8px; text-align: left; }
.lkps-table th { background-color: #f1f5f9; font-weight: 600; color: #0d47a1; }
.lkps-table tr:nth-child(even) { background-color: #f8fafc; }
.highlight-data { background-color: #fff8e1 !important; font-weight: 600; color: #e65100; }
.link-cell a { color: #0d47a1; text-decoration: none; font-weight: 600; }

.summary-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(120px, 1fr)); gap: 6px; margin: 8px 0; }
.summary-card { 
  background: white; 
  border: 1px solid #e0e0e0; 
  border-left: 3px solid #0d47a1; 
  border-radius: 6px; 
  padding: 8px; 
  text-align: center;
}
.summary-card .sc-value { font-size: 1.1rem; font-weight: 800; color: #0d47a1; }
.summary-card .sc-label { font-size: 0.68rem; color: #666; }

.info-box { 
  background: #e3f2fd; 
  border-left: 3px solid #0d47a1; 
  padding: 8px 12px; 
  border-radius: 4px; 
  margin-bottom: 12px; 
  font-size: 0.78rem; 
  color: #0d47a1; 
}

@media (max-width: 767px) {
  .ev-tab { font-size: 0.75rem; padding: 8px 12px; }
  .ev-content { padding: 12px; }
  .summary-grid { grid-template-columns: 1fr 1fr; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('sesi1', this)">
      <span class="tab-icon"></span>
      <span>SESI 1: LKPS</span>
    </div>
    <div class="ev-tab" onclick="showEvPanel('sesi2', this)">
      <span class="tab-icon"></span>
      <span>SESI 2: LEDPS</span>
    </div>
  </div>

  <div class="ev-content">

    <!-- ========== SESI 1: LKPS ========== -->
    <div class="ev-panel active" id="panel-sesi1">
      
      <!-- FILE OPEN BUTTON -->
      <div class="file-open-bar">
        <a href="https://drive.google.com/file/d/GANTI_DENGAN_ID_FILE_LKPS/view?usp=sharing" target="_blank" class="file-open-btn">
          <span class="btn-icon">📗</span>
          <span>Open LKPS (Excel)</span>
        </a>
      </div>

      <div class="info-box">
        <strong>ℹ️ Sesi 1:</strong> Data kuantitatif 3 tahun terakhir. Klik tombol di atas untuk membuka file LKPS.
      </div>

      <!-- Sub-nav -->
      <div class="sub-nav" id="lkpsNav">
        <button class="active" onclick="showLkpsTable('t1', this)">Tabel 1</button>
        <button onclick="showLkpsTable('t2', this)">Tabel 2</button>
        <button onclick="showLkpsTable('t3', this)">Tabel 3</button>
        <button onclick="showLkpsTable('t4', this)">Tabel 4</button>
        <button onclick="showLkpsTable('t5', this)">Tabel 5</button>
        <button onclick="showLkpsTable('t6', this)">Tabel 6</button>
        <button onclick="showLkpsTable('t7', this)">Tabel 7</button>
      </div>

      <!-- TABEL 1 -->
      <div class="lkps-table-panel active" id="lkps-t1">
        <div class="lkps-section">
          <h3> Tabel 1: VMTS</h3>
          <div class="compact-card">
            <h4>VMTS PT, UPPS, Visi Keilmuan</h4>
            <ul>
              <li><strong>VMTS PT:</strong> SK 643/PL3/OT/2021</li>
              <li><strong>VMTS UPPS:</strong> SK 2585/PL3/OT/2020</li>
              <li><strong>Visi Keilmuan PS:</strong> SK 2589/PL3/KR.00/2020</li>
            </ul>
          </div>
        </div>
      </div>

      <!-- TABEL 2 -->
      <div class="lkps-table-panel" id="lkps-t2">
        <div class="lkps-section">
          <h3>🤝 Tabel 2: Kerja Sama & Dana</h3>
          <div class="summary-grid">
            <div class="summary-card">
              <div class="sc-value">42</div>
              <div class="sc-label">Pendidikan</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">17</div>
              <div class="sc-label">Penelitian</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">7</div>
              <div class="sc-label">PkM</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">27,24 M</div>
              <div class="sc-label">Dana Rata-rata</div>
            </div>
          </div>
        </div>
      </div>

      <!-- TABEL 3 -->
      <div class="lkps-table-panel" id="lkps-t3">
        <div class="lkps-section">
          <h3>📘 Tabel 3: Kurikulum & Tridharma</h3>
          <div class="summary-grid">
            <div class="summary-card">
              <div class="sc-value">53</div>
              <div class="sc-label">MK</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">150</div>
              <div class="sc-label">SKS</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">45</div>
              <div class="sc-label">Penelitian</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">14</div>
              <div class="sc-label">PkM</div>
            </div>
          </div>
        </div>
      </div>

      <!-- TABEL 4 -->
      <div class="lkps-table-panel" id="lkps-t4">
        <div class="lkps-section">
          <h3>👨‍🏫 Tabel 4: SDM</h3>
          <div class="summary-grid">
            <div class="summary-card">
              <div class="sc-value">11</div>
              <div class="sc-label">DTPS</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">3</div>
              <div class="sc-label">Doktor</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">220</div>
              <div class="sc-label">Publikasi</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">13</div>
              <div class="sc-label">Produk Diadopsi</div>
            </div>
          </div>
        </div>
      </div>

      <!-- TABEL 5 -->
      <div class="lkps-table-panel" id="lkps-t5">
        <div class="lkps-section">
          <h3>💰 Tabel 5: Sarpras & K3L</h3>
          <div class="compact-card">
            <p><strong>Sarpras:</strong> 16 prasarana utama (13 lab + 3 layanan)</p>
            <p><strong>K3L:</strong> 17 dokumen, 12 fasilitas</p>
          </div>
        </div>
      </div>

      <!-- TABEL 6 -->
      <div class="lkps-table-panel" id="lkps-t6">
        <div class="lkps-section">
          <h3>🎓 Tabel 6: Mahasiswa & Luaran</h3>
          <div class="summary-grid">
            <div class="summary-card">
              <div class="sc-value">189</div>
              <div class="sc-label">Mahasiswa</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">3,46</div>
              <div class="sc-label">IPK Rata-rata</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">76,25%</div>
              <div class="sc-label">Tracer</div>
            </div>
            <div class="summary-card">
              <div class="sc-value">70,49%</div>
              <div class="sc-label">Kesesuaian Kerja</div>
            </div>
          </div>
        </div>
      </div>

      <!-- TABEL 7 -->
      <div class="lkps-table-panel" id="lkps-t7">
        <div class="lkps-section">
          <h3>🔄 Tabel 7: SPMI</h3>
          <div class="compact-card">
            <h4>Dokumen SPMI</h4>
            <ul>
              <li>Kebijakan SPMI: SM/PNJ/SPMI/342</li>
              <li>Pedoman PPEPP: KM/PNJ/SPMI/212</li>
              <li>Standar Mutu: SM/PNJ/SPMI/311</li>
            </ul>
          </div>
        </div>
      </div>

    </div>

    <!-- ========== SESI 2: LEDPS ========== -->
    <div class="ev-panel" id="panel-sesi2">
      
      <!-- FILE OPEN BUTTON -->
      <div class="file-open-bar">
        <a href="https://drive.google.com/file/d/GANTI_DENGAN_ID_FILE_LED/view?usp=sharing" target="_blank" class="file-open-btn pdf">
          <span class="btn-icon"></span>
          <span>Open LEDPS (PDF)</span>
        </a>
      </div>

      <div class="info-box">
        <strong>ℹ️ Sesi 2:</strong> Analisis kualitatif per kriteria + BAB III. Klik tombol di atas untuk membuka file LEDPS.
      </div>

      <!-- Sub-nav -->
      <div class="sub-nav" id="ledpsNav">
        <button class="active" onclick="showLedpsCriteria('c1', this)">C.1</button>
        <button onclick="showLedpsCriteria('c2', this)">C.2</button>
        <button onclick="showLedpsCriteria('c3', this)">C.3</button>
        <button onclick="showLedpsCriteria('c4', this)">C.4</button>
        <button onclick="showLedpsCriteria('c5', this)">C.5</button>
        <button onclick="showLedpsCriteria('c6', this)">C.6</button>
        <button onclick="showLedpsCriteria('c7', this)">C.7</button>
        <button onclick="showLedpsCriteria('bab3', this)">BAB III</button>
      </div>

      <!-- C.1 -->
      <div class="ledps-criteria active" id="ledps-c1">
        <div class="lkps-section">
          <h3>📑 C.1 — VMTS</h3>
          <div class="compact-card">
            <h4>Visi Keilmuan PSBM</h4>
            <p>"Menjadi Program Studi Unggul Bertaraf Internasional di Bidang Broadband Multimedia"</p>
            <h4 style="margin-top:8px;">Mekanisme</h4>
            <ul>
              <li>Internal: Dosen, mahasiswa, tendik</li>
              <li>Eksternal: Alumni, pengguna, pakar industri</li>
              <li>SK: 954/PL3.9/HK.03/2020</li>
            </ul>
          </div>
        </div>
      </div>

      <!-- C.2 -->
      <div class="ledps-criteria" id="ledps-c2">
        <div class="lkps-section">
          <h3>🏛️ C.2 — Tata Kelola</h3>
          <div class="compact-card">
            <h4>Tata Pamong</h4>
            <p>Statuta PNJ No. 35/2018, OTK No. 60/2022</p>
            <h4 style="margin-top:8px;">Kerja Sama</h4>
            <p>66 kerja sama (42 pendidikan, 17 penelitian, 7 PkM)</p>
            <h4 style="margin-top:8px;">Keuangan</h4>
            <p>Rp 27,24 M/tahun (UPPS), Rp 4,08 M/tahun (PS)</p>
          </div>
        </div>
      </div>

      <!-- C.3 -->
      <div class="ledps-criteria" id="ledps-c3">
        <div class="lkps-section">
          <h3>📘 C.3 — Diklitpmas</h3>
          <div class="compact-card">
            <h4>Kurikulum</h4>
            <p>53 MK, 150 SKS (53,33% praktik)</p>
            <h4 style="margin-top:8px;">Penelitian</h4>
            <p>45 penelitian (80% internal, 20% eksternal)</p>
            <h4 style="margin-top:8px;">PkM</h4>
            <p>14 kegiatan (100% internal)</p>
          </div>
        </div>
      </div>

      <!-- C.4 -->
      <div class="ledps-criteria" id="ledps-c4">
        <div class="lkps-section">
          <h3>👨‍ C.4 — SDM</h3>
          <div class="compact-card">
            <h4>Profil DTPS</h4>
            <ul>
              <li>11 dosen (3 doktor, 4 LK, 6 Lektor)</li>
              <li>100% bersertifikat</li>
              <li>BKD: 14,77 SKS/semester</li>
            </ul>
            <h4 style="margin-top:8px;">Kinerja</h4>
            <p>220 publikasi, 13 produk diadopsi, 43 rekognisi</p>
          </div>
        </div>
      </div>

      <!-- C.5 -->
      <div class="ledps-criteria" id="ledps-c5">
        <div class="lkps-section">
          <h3>💰 C.5 — Sarpras</h3>
          <div class="compact-card">
            <h4>Sarana</h4>
            <p>7 lab + 1 bengkel, 12 ruang kelas</p>
            <h4 style="margin-top:8px;">K3L</h4>
            <p>17 dokumen, 12 fasilitas (APAR, hidran, ambulance)</p>
          </div>
        </div>
      </div>

      <!-- C.6 -->
      <div class="ledps-criteria" id="ledps-c6">
        <div class="lkps-section">
          <h3>🎓 C.6 — Luaran</h3>
          <div class="compact-card">
            <h4>Mahasiswa</h4>
            <ul>
              <li>189 aktif, 13 asing</li>
              <li>IPK: 3,46 | Masa studi: 4,06 tahun</li>
            </ul>
            <h4 style="margin-top:8px;">Luaran</h4>
            <ul>
              <li>19 prestasi (10 akademik, 9 nonakademik)</li>
              <li>126 publikasi, 16 produk diadopsi</li>
            </ul>
          </div>
        </div>
      </div>

      <!-- C.7 -->
      <div class="ledps-criteria" id="ledps-c7">
        <div class="lkps-section">
          <h3>🔄 C.7 — SPMI</h3>
          <div class="compact-card">
            <h4>Struktur</h4>
            <p>UPM (institusi) + GPM (jurusan) sejak 2023</p>
            <h4 style="margin-top:8px;">Siklus PPEPP</h4>
            <p>Penetapan → Pelaksanaan → Evaluasi → Pengendalian → Peningkatan</p>
          </div>
        </div>
      </div>

      <!-- BAB III -->
      <div class="ledps-criteria" id="ledps-bab3">
        <div class="lkps-section">
          <h3> BAB III — Program Pengembangan</h3>
          <div class="compact-card">
            <h4>SWOT</h4>
            <ul>
              <li><strong>S:</strong> Kekhasan BM, 66 kerja sama, SDM kuat</li>
              <li><strong>W:</strong> Internasionalisasi, CPL, pendanaan eksternal</li>
              <li><strong>O:</strong> 5G/6G, IoT, AI, hibah nasional</li>
              <li><strong>T:</strong> Perubahan teknologi cepat, persaingan</li>
            </ul>
            <h4 style="margin-top:8px;">6 Tujuan Strategis</h4>
            <ol style="font-size:0.75rem; padding-left:16px; margin:4px 0;">
              <li>Memperkuat mutu pendidikan</li>
              <li>Meningkatkan penelitian & hilirisasi</li>
              <li>Meningkatkan kualitas SDM</li>
              <li>Memperluas internasionalisasi</li>
              <li>Meningkatkan daya saing lulusan</li>
              <li>Memperkuat budaya mutu</li>
            </ol>
          </div>
        </div>
      </div>

    </div>

  </div>
</div>

<script>
// ===== NAVIGATION =====
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
}

// ===== SUB-NAV LKPS =====
function showLkpsTable(id, btn) {
  document.querySelectorAll('.lkps-table-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('lkps-' + id).classList.add('active');
  const nav = btn.parentElement;
  nav.querySelectorAll('button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}

// ===== SUB-NAV LEDPS =====
function showLedpsCriteria(id, btn) {
  document.querySelectorAll('.ledps-criteria').forEach(p => p.classList.remove('active'));
  document.getElementById('ledps-' + id).classList.add('active');
  const nav = btn.parentElement;
  nav.querySelectorAll('button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  document.getElementById('lkps-t1').classList.add('active');
  document.getElementById('ledps-c1').classList.add('active');
});
</script>

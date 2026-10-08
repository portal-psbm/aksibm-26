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
.ev-tab.active { background: #0d47a1; color: #ffffff; transform: translateY(-6px); z-index: 20; border-color: #0d47a1; box-shadow: 0 -4px 16px rgba(13, 71, 161, 0.25); font-weight: 700; }
.ev-tab.active::before { background: #0d47a1; border-color: #0d47a1; height: 8px; top: -8px; }
.ev-tab.sesi2.active { background: linear-gradient(135deg, #388e3c 0%, #2e7d32 100%); border-color: #2e7d32; }
.ev-tab.sesi2.active::before { background: linear-gradient(135deg, #388e3c 0%, #2e7d32 100%); }

.ev-content { background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1; border-radius: 0 0 16px 16px; padding: 28px; min-height: 500px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px; }
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

.session-header { padding: 24px; border-radius: 12px; margin-bottom: 20px; color: white; }
.session-header.sesi1 { background: linear-gradient(135deg, #1565c0 0%, #0d47a1 100%); }
.session-header.sesi2 { background: linear-gradient(135deg, #388e3c 0%, #2e7d32 100%); }
.session-header h2 { margin: 0 0 8px 0; font-size: 1.4rem; }
.session-header .subtitle { opacity: 0.95; font-size: 0.92rem; margin-bottom: 12px; }
.session-header .tag { display: inline-block; background: rgba(255,255,255,0.25); padding: 4px 12px; border-radius: 12px; font-size: 0.75rem; font-weight: 700; margin-bottom: 8px; letter-spacing: 0.5px; }
.session-info { display: flex; gap: 12px; flex-wrap: wrap; margin-top: 12px; }
.session-info .info-item { background: rgba(255,255,255,0.2); padding: 8px 14px; border-radius: 8px; font-size: 0.85rem; backdrop-filter: blur(4px); }
.session-info .info-item strong { display: block; font-size: 1.3rem; margin-bottom: 2px; }

/* Sub-nav utama */
.criteria-nav { display: flex; gap: 4px; margin-bottom: 16px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
.criteria-nav button { padding: 8px 14px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.82rem; }
.criteria-nav button:hover { color: #0d47a1; background: #f8fafc; }
.criteria-nav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }
.criteria-nav.ledps-nav button.active { color: #2e7d32; border-bottom-color: #2e7d32; }

/* Sub-nav sub-kriteria (level 2) */
.sub-criteria-nav { display: flex; gap: 4px; margin-bottom: 16px; flex-wrap: wrap; padding: 10px; background: #f8fafc; border-radius: 8px; border: 1px solid #e0e0e0; }
.sub-criteria-nav button { padding: 6px 12px; background: white; border: 1px solid #e0e0e0; border-radius: 16px; cursor: pointer; font-weight: 500; color: #555; font-size: 0.78rem; transition: all 0.2s; }
.sub-criteria-nav button:hover { background: #e3f2fd; border-color: #0d47a1; color: #0d47a1; }
.sub-criteria-nav button.active { background: #0d47a1; color: white; border-color: #0d47a1; }
.sub-criteria-nav.ledps-sub button.active { background: #2e7d32; border-color: #2e7d32; }

.sub-criteria-panel { display: none; animation: fadeIn 0.3s ease; }
.sub-criteria-panel.active { display: block; }

.lkps-section { margin-bottom: 24px; }
.lkps-section h3 { color: #0d47a1; border-left: 4px solid #0d47a1; padding-left: 12px; margin-bottom: 12px; font-size: 1.1rem; }
.lkps-section.ledps h3 { color: #2e7d32; border-left-color: #2e7d32; }
.lkps-section h4 { color: #1565c0; margin: 16px 0 10px 0; font-size: 1rem; padding-bottom: 6px; border-bottom: 1px dashed #e0e0e0; }
.lkps-section.ledps h4 { color: #388e3c; }

.table-responsive { overflow-x: auto; border: 1px solid #e0e0e0; border-radius: 8px; margin-bottom: 16px; }
.lkps-table { width: 100%; border-collapse: collapse; font-size: 0.82rem; min-width: 600px; }
.lkps-table th, .lkps-table td { border: 1px solid #e0e0e0; padding: 8px 10px; text-align: left; vertical-align: top; }
.lkps-table th { background-color: #f1f5f9; font-weight: 600; color: #0d47a1; position: sticky; top: 0; z-index: 1; }
.lkps-table tr:nth-child(even) { background-color: #f8fafc; }
.lkps-table tr:hover { background-color: #e3f2fd; }
.highlight-data { background-color: #fff8e1 !important; font-weight: 600; color: #e65100; }
.link-cell a { color: #0d47a1; text-decoration: none; word-break: break-all; font-weight: 600; }
.link-cell a:hover { text-decoration: underline; }

.summary-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 10px; margin: 16px 0; }
.summary-card { background: white; border: 1px solid #e0e0e0; border-left: 4px solid #0d47a1; border-radius: 8px; padding: 12px; transition: all 0.2s; }
.summary-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); transform: translateY(-2px); }
.summary-card .sc-label { font-size: 0.72rem; color: #666; text-transform: uppercase; letter-spacing: 0.5px; }
.summary-card .sc-value { font-size: 1.4rem; font-weight: 800; color: #0d47a1; margin: 4px 0; }
.summary-card .sc-desc { font-size: 0.78rem; color: #555; }

.info-box { background: #e3f2fd; border-left: 4px solid #0d47a1; padding: 12px 16px; border-radius: 6px; margin-bottom: 20px; font-size: 0.88rem; color: #0d47a1; }
.info-box.ledps { background: #e8f5e9; border-left-color: #2e7d32; color: #2e7d32; }
.info-box strong { color: inherit; filter: brightness(0.7); }

.led-card { background: white; border: 1px solid #e0e0e0; border-radius: 10px; padding: 16px; margin-bottom: 12px; border-left: 4px solid #2e7d32; }
.led-card h4 { color: #2e7d32; margin: 0 0 8px 0; font-size: 0.95rem; }
.led-card p { color: #555; font-size: 0.88rem; line-height: 1.6; margin: 0 0 8px 0; }
.led-card ul { margin: 8px 0; padding-left: 20px; font-size: 0.85rem; color: #555; }
.led-card li { margin-bottom: 4px; line-height: 1.5; }
.led-card .evidence-link { display: inline-flex; align-items: center; gap: 4px; background: #e8f5e9; color: #2e7d32; padding: 4px 10px; border-radius: 12px; font-size: 0.75rem; font-weight: 600; text-decoration: none; margin-top: 8px; margin-right: 6px; }
.led-card .evidence-link:hover { background: #c8e6c9; }

.ev-open-btn { padding: 6px 14px; border-radius: 6px; border: none; background: #0d47a1; color: white; font-size: 0.78rem; font-weight: 600; cursor: pointer; transition: all 0.2s; display: inline-flex; align-items: center; gap: 4px; text-decoration: none; margin-right: 6px; margin-bottom: 6px; }
.ev-open-btn:hover { background: #1565c0; transform: translateY(-1px); }
.ev-open-btn.secondary { background: white; color: #0d47a1; border: 1px solid #0d47a1; }
.ev-open-btn.secondary:hover { background: #e3f2fd; }

.swot-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin: 16px 0; }
.swot-card { padding: 16px; border-radius: 10px; border: 2px solid; }
.swot-card.strength { background: #e8f5e9; border-color: #4caf50; }
.swot-card.weakness { background: #fff3e0; border-color: #ff9800; }
.swot-card.opportunity { background: #e3f2fd; border-color: #2196f3; }
.swot-card.threat { background: #ffebee; border-color: #f44336; }
.swot-card h4 { margin: 0 0 8px 0; font-size: 0.95rem; }
.swot-card ul { margin: 0; padding-left: 18px; font-size: 0.85rem; }
.swot-card ul li { padding: 2px 0; }

@media (max-width: 767px) {
.ev-shelf { gap: 4px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
.ev-shelf::-webkit-scrollbar { display: none; }
.ev-tab { min-width: 110px; flex: 0 0 auto; font-size: 0.8rem; }
.ev-content { padding: 20px; }
.summary-grid { grid-template-columns: 1fr 1fr; }
.session-info { flex-direction: column; }
.swot-grid { grid-template-columns: 1fr; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('sesi1', this)"><br>SESI 1<br>LKPS</div>
    <div class="ev-tab sesi2" onclick="showEvPanel('sesi2', this)">📕<br>SESI 2<br>LEDPS</div>
  </div>

  <div class="ev-content">

    <!-- ========== SESI 1: LKPS ========== -->
    <div class="ev-panel active" id="panel-sesi1">
      <div class="session-header sesi1">
        <span class="tag">DATA KUANTITATIF</span>
        <h2>📊 SESI 1 — LAPORAN KINERJA PROGRAM STUDI (LKPS)</h2>
        <div class="subtitle">Tabel 1 s.d. 7 — Data angka 3 tahun terakhir (TS-2, TS-1, TS)</div>
        <div class="session-info">
          <div class="info-item"><strong>7</strong> Kategori Tabel</div>
          <div class="info-item"><strong>50+</strong> Tabel Evidence</div>
          <div class="info-item"><strong>3 Tahun</strong> Periode Data</div>
        </div>
      </div>

      <div class="info-box">
        <strong>ℹ️ LKPS = Data Angka:</strong> Semua tabel di bawah ini berisi <strong>data kuantitatif</strong> yang telah disubmit ke SAKTI LAM Teknik. Fokus asesor: <em>validasi angka, konsistensi, dan kecukupan</em>.
      </div>

      <div class="criteria-nav">
        <button class="active" onclick="showLkpsTable('t1', this)">Tabel 1<br><small>VMTS</small></button>
        <button onclick="showLkpsTable('t2', this)">Tabel 2<br><small>Kerja Sama & Dana</small></button>
        <button onclick="showLkpsTable('t3', this)">Tabel 3<br><small>Kurikulum & Tridharma</small></button>
        <button onclick="showLkpsTable('t4', this)">Tabel 4<br><small>SDM & Luaran</small></button>
        <button onclick="showLkpsTable('t5', this)">Tabel 5<br><small>Sarpras & K3L</small></button>
        <button onclick="showLkpsTable('t6', this)">Tabel 6<br><small>Mahasiswa & Luaran</small></button>
        <button onclick="showLkpsTable('t7', this)">Tabel 7<br><small>SPMI</small></button>
      </div>

      <!-- TABEL 1-7 (ringkas, sama seperti sebelumnya) -->
      <div class="lkps-table-panel active" id="lkps-t1">
        <div class="lkps-section">
          <h3>📑 Tabel 1: VMTS PT, UPPS, dan Visi Keilmuan PS</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>No</th><th>Jenis VMTS</th><th>Pernyataan (Ringkasan)</th><th>No. SK</th><th>Link Dokumen</th></tr></thead>
              <tbody>
                <tr><td>1</td><td><strong>VMTS PT</strong></td><td>Visi: Menjadi politeknik unggul bertaraf internasional untuk mendukung daya saing bangsa</td><td>643/PL3/OT/2021</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU?usp=drive_link" target="_blank">📂 Buka Folder</a></td></tr>
                <tr><td>2</td><td><strong>VMTS UPPS (JTE)</strong></td><td>Visi: Menjadi Jurusan Teknik Elektro unggul bertaraf internasional untuk mendukung daya saing bangsa</td><td>2585/PL3/OT/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1JiRWv_v_-pbrFTMl74JwQzJ1ZNnCpcOt?usp=drive_link" target="_blank">📂 Buka Folder</a></td></tr>
                <tr><td>3</td><td><strong>Visi Keilmuan PS</strong></td><td>Menjadi program studi unggul bertaraf internasional di bidang broadband multimedia untuk mendukung daya saing bangsa</td><td>2589/PL3/KR.00/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf?usp=sharing" target="_blank">📂 Buka Folder</a></td></tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>

      <div class="lkps-table-panel" id="lkps-t2">
        <div class="lkps-section">
          <h3>🤝 Tabel 2a1: Kerja Sama Pendidikan (42)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">5</div></div>
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">37</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">42</div></div>
          </div>
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn"> Buka Folder Kerja Sama</a></div>
        </div>
        <div class="lkps-section">
          <h3>🔬 Tabel 2a2: Kerja Sama Penelitian (17)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">16</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">17</div></div>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🤝 Tabel 2a3: Kerja Sama PkM (7)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Lokal/Wilayah</div><div class="sc-value">6</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">7</div></div>
          </div>
        </div>
        <div class="lkps-section">
          <h3>💰 Tabel 2b: Penggunaan Dana (Rupiah)</h3>
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
        </div>
      </div>

      <div class="lkps-table-panel" id="lkps-t3">
        <div class="lkps-section">
          <h3>📘 Tabel 3a1: Kurikulum (53 MK, 150 SKS)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total MK</div><div class="sc-value">53</div></div>
            <div class="summary-card"><div class="sc-label">Total SKS</div><div class="sc-value">150</div></div>
            <div class="summary-card"><div class="sc-label">SKS Praktik</div><div class="sc-value">80 (53,33%)</div></div>
            <div class="summary-card"><div class="sc-label">SKS Kuliah</div><div class="sc-value">68</div></div>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🔬 Tabel 3b: Penelitian DTPS (45 judul, 3 tahun)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">14</div></div>
            <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">13</div></div>
            <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">18</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">45</div></div>
            <div class="summary-card"><div class="sc-label">PT/Mandiri</div><div class="sc-value">36 (80%)</div></div>
            <div class="summary-card"><div class="sc-label">Eksternal</div><div class="sc-value">9 (20%)</div></div>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🤝 Tabel 3c: PkM DTPS (14 judul, 3 tahun)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">6</div></div>
            <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">6</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">14</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Internal/Mandiri</div><div class="sc-value">14 (100%)</div></div>
          </div>
        </div>
      </div>

      <div class="lkps-table-panel" id="lkps-t4">
        <div class="lkps-section">
          <h3>👨‍🏫 Tabel 4a: Profil DTPS (11 Dosen)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total DTPS</div><div class="sc-value">11</div></div>
            <div class="summary-card"><div class="sc-label">Doktor</div><div class="sc-value">3 (27,27%)</div></div>
            <div class="summary-card"><div class="sc-label">Lektor Kepala</div><div class="sc-value">4 (36,36%)</div></div>
            <div class="summary-card"><div class="sc-label">Lektor</div><div class="sc-value">6</div></div>
          </div>
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder DTPS</a></div>
        </div>
        <div class="lkps-section">
          <h3>📚 Tabel 4e: Publikasi DTPS (220 total)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Jurnal Nasional Terakreditasi</div><div class="sc-value">73</div></div>
            <div class="summary-card"><div class="sc-label">Jurnal Internasional Bereputasi</div><div class="sc-value">12</div></div>
            <div class="summary-card"><div class="sc-label">Prosiding Nasional</div><div class="sc-value">92</div></div>
            <div class="summary-card"><div class="sc-label">Prosiding Scopus/WoS</div><div class="sc-value">33</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">TOTAL</div><div class="sc-value">220</div></div>
          </div>
        </div>
        <div class="lkps-section">
          <h3>📦 Tabel 4g: Produk/Jasa DTPS Diadopsi (13)</h3>
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z" target="_blank" class="ev-open-btn">📂 Buka Folder Produk Diadopsi</a></div>
        </div>
      </div>

      <div class="lkps-table-panel" id="lkps-t5">
        <div class="lkps-section">
          <h3>💰 Tabel 5a: Prasarana & Peralatan Utama</h3>
          <div class="info-box"><strong> Ringkasan:</strong> 16 prasarana utama (13 lab/ruang + 3 layanan nonakademik). Seluruhnya terawat, dimiliki sendiri.</div>
        </div>
        <div class="lkps-section">
          <h3>⚠️ Tabel 5b: Dokumen K3L (17 dokumen)</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>No</th><th>Jenis Dokumen</th><th>Jumlah</th><th>Tanggal Pengesahan</th></tr></thead>
              <tbody>
                <tr><td>1</td><td>Pedoman Sistem Manajemen K3 Lingkungan PNJ</td><td>1</td><td>1 Januari 2025</td></tr>
                <tr><td>2</td><td>Pedoman K3L Jurusan Teknik Elektro</td><td>1</td><td>25 Oktober 2025</td></tr>
                <tr><td>3-15</td><td>13 SOP K3L</td><td>13</td><td>1 Januari 2025</td></tr>
                <tr><td>16</td><td>SOP Penggunaan Lab dan Bengkel</td><td>1</td><td>1 Januari 2025</td></tr>
                <tr><td>17</td><td>Hasil Tinjauan Berkala K3</td><td>1</td><td>5 November 2025</td></tr>
              </tbody>
            </table>
          </div>
        </div>
        <div class="lkps-section">
          <h3>🧯 Tabel 5c: Fasilitas K3L (12 item, semua terawat)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">APAR</div><div class="sc-value">6</div></div>
            <div class="summary-card"><div class="sc-label">Hidran</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">Ambulance</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">P3K</div><div class="sc-value">2</div></div>
            <div class="summary-card"><div class="sc-label">Rambu K3</div><div class="sc-value">7</div></div>
            <div class="summary-card"><div class="sc-label">Jalur Evakuasi</div><div class="sc-value">22</div></div>
          </div>
        </div>
      </div>

      <div class="lkps-table-panel" id="lkps-t6">
        <div class="lkps-section">
          <h3> Tabel 6a: Jumlah Mahasiswa (189 aktif TS)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">192</div></div>
            <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">182</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">TS</div><div class="sc-value">189</div></div>
            <div class="summary-card"><div class="sc-label">Mhs Asing PT TS</div><div class="sc-value">12</div></div>
          </div>
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
        </div>
        <div class="lkps-section">
          <h3>🏆 Tabel 6c: Prestasi Mahasiswa (19)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Akademik</div><div class="sc-value">10</div><div class="sc-desc">2 intl + 8 nasional</div></div>
            <div class="summary-card"><div class="sc-label">Nonakademik</div><div class="sc-value">9</div><div class="sc-desc">1 intl + 5 nas + 3 wil</div></div>
          </div>
        </div>
        <div class="lkps-section">
          <h3>📚 Tabel 6e2: Publikasi Mahasiswa (126)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Jurnal Nasional Terakreditasi</div><div class="sc-value">34</div></div>
            <div class="summary-card"><div class="sc-label">Jurnal Internasional</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Prosiding Nasional</div><div class="sc-value">91</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">126</div></div>
          </div>
        </div>
        <div class="lkps-section">
          <h3>📦 Tabel 6e4: Produk Mahasiswa Diadopsi (16)</h3>
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1gj3fyC_mO2c6pDTNRzhnlPcIE4_pKBYS" target="_blank" class="ev-open-btn"> Buka Folder Produk Mahasiswa</a></div>
        </div>
        <div class="lkps-section">
          <h3>📈 Tabel 6f1: Waktu Tunggu Lulusan</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total Lulusan</div><div class="sc-value">80</div></div>
            <div class="summary-card"><div class="sc-label">Terlacak</div><div class="sc-value">61 (76,25%)</div></div>
            <div class="summary-card"><div class="sc-label">WT &lt; 3 bulan</div><div class="sc-value">34 (55,74%)</div></div>
            <div class="summary-card"><div class="sc-label">WT 3-18 bulan</div><div class="sc-value">27 (44,26%)</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">WT &gt; 18 bulan</div><div class="sc-value">0</div></div>
          </div>
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
                <tr><td>Berkomunikasi</td><td class="highlight-data">77,78%</td><td>22,20%</td><td>0,00%</td><td>0,00%</td></tr>
                <tr><td>Kerjasama tim</td><td class="highlight-data">75,60%</td><td>24,40%</td><td>0,00%</td><td>0,00%</td></tr>
                <tr><td>Pengembangan diri</td><td class="highlight-data">73,30%</td><td>26,70%</td><td>0,00%</td><td>0,00%</td></tr>
              </tbody>
            </table>
          </div>
          <div class="info-box"><strong>⚠️ Catatan Kritis:</strong> Bahasa asing 11,1% "Cukup" — perlu direkonsiliasi dengan narasi RTL.</div>
        </div>
      </div>

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
        </div>
        <div class="lkps-section">
          <h3>🔄 Tabel 7b: Pelaksanaan SPMI (Siklus PPEPP)</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>Tahap PPEPP</th><th>Link Dokumen</th><th>Link Audit</th><th>Link RTM</th><th>Link Peningkatan</th></tr></thead>
              <tbody>
                <tr><td><strong>Penetapan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank"> Buka</a></td><td>—</td><td>—</td><td>—</td></tr>
                <tr><td><strong>Pelaksanaan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank"> Buka</a></td><td>—</td><td>—</td><td>—</td></tr>
                <tr><td><strong>Evaluasi</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1ywPn4RexBzQjD6DXRT8DCXTEtemvcQLz" target="_blank">📂 Buka</a></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank">📂 Buka</a></td><td>—</td><td>—</td></tr>
                <tr><td><strong>Pengendalian</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1WFgIamM3JnSGZ-WAv-UOC1W22E0ondmV" target="_blank">📂 Buka</a></td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank">📂 Buka</a></td><td>—</td></tr>
                <tr><td><strong>Peningkatan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank"> Buka</a></td><td>—</td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank">📂 Buka</a></td></tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>

    </div>

    <!-- ========== SESI 2: LEDPS (DENGAN SUB-KRITERIA LENGKAP) ========== -->
    <div class="ev-panel" id="panel-sesi2">
      <div class="session-header sesi2">
        <span class="tag">ANALISIS KUALITATIF + BAB III</span>
        <h2>📕 SESI 2 — LAPORAN EVALUASI DIRI (LEDPS)</h2>
        <div class="subtitle">C.1 s.d. C.7 + BAB III — Analisis Naratif dengan Sub-Kriteria Detail</div>
        <div class="session-info">
          <div class="info-item"><strong>7</strong> Kriteria</div>
          <div class="info-item"><strong>30+</strong> Sub-Kriteria</div>
          <div class="info-item"><strong>SWOT</strong> + Program</div>
        </div>
      </div>

      <div class="info-box ledps">
        <strong>ℹ️ LEDPS = Analisis Naratif:</strong> Berbeda dengan LKPS (angka), LEDPS berisi <strong>analisis kualitatif</strong> per kriteria — evaluasi diri, capaian, masalah, dan tindak lanjut. Setiap kriteria memiliki <strong>sub-kriteria detail</strong> untuk memudahkan asesmen.
      </div>

      <!-- Sub-nav Kriteria Utama -->
      <div class="criteria-nav ledps-nav">
        <button class="active" onclick="showLedpsCriteria('c1', this)">C.1 VMTS</button>
        <button onclick="showLedpsCriteria('c2', this)">C.2 Akuntabilitas</button>
        <button onclick="showLedpsCriteria('c3', this)">C.3 Diklitpmas</button>
        <button onclick="showLedpsCriteria('c4', this)">C.4 SDM</button>
        <button onclick="showLedpsCriteria('c5', this)">C.5 Sarpras</button>
        <button onclick="showLedpsCriteria('c6', this)">C.6 Luaran</button>
        <button onclick="showLedpsCriteria('c7', this)">C.7 SPMI</button>
        <button onclick="showLedpsCriteria('bab3', this)" style="background: linear-gradient(135deg, #fff3e0 0%, #ffe0b2 100%); color: #e65100; border-radius: 6px; border: 1px solid #ffcc80;">📕 BAB III</button>
      </div>

      <!-- ================================================================ -->
      <!-- C.1 VMTS - SUB KRITERIA -->
      <!-- ================================================================ -->
      <div class="ledps-criteria active" id="ledps-c1">
        
        <div class="sub-criteria-nav ledps-sub">
          <button class="active" onclick="showSubCriteria('c1', 'vmts', this)"> Kekhasan VMTS</button>
          <button onclick="showSubCriteria('c1', 'mekanisme', this)">🔧 Mekanisme</button>
          <button onclick="showSubCriteria('c1', 'pemahaman', this)">📊 Pemahaman</button>
          <button onclick="showSubCriteria('c1', 'pencapaian', this)">🎯 Pencapaian</button>
          <button onclick="showSubCriteria('c1', 'swot', this)">📊 SWOT C.1</button>
        </div>

        <!-- Sub: Kekhasan VMTS -->
        <div class="sub-criteria-panel active" id="c1-vmts">
          <div class="lkps-section ledps">
            <h3>🎯 Kekhasan VMTS & Visi Keilmuan</h3>
            <div class="led-card">
              <h4>📑 Visi Keilmuan PSBM</h4>
              <p><strong>"Menjadi Program Studi Unggul Bertaraf Internasional di Bidang Broadband Multimedia untuk Mendukung Daya Saing Bangsa"</strong></p>
              <p><strong>Kekhasan:</strong> Integrasi teknologi telekomunikasi broadband, jaringan komputer, komputasi, dan multimedia dengan karakter pendidikan vokasi berbasis praktik, proyek, magang industri, dan sertifikasi kompetensi.</p>
              <a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf" target="_blank" class="evidence-link">📂 Bukti: SK Visi Keilmuan PS</a>
            </div>
            <div class="led-card">
              <h4>🔗 Linearitas VMTS</h4>
              <ul>
                <li><strong>PNJ:</strong> "Menjadi politeknik unggul bertaraf internasional untuk mendukung daya saing bangsa"</li>
                <li><strong>JTE:</strong> "Menjadi Jurusan Teknik Elektro unggul bertaraf internasional untuk mendukung daya saing bangsa"</li>
                <li><strong>PSBM:</strong> "Menjadi Program Studi Unggul Bertaraf Internasional di Bidang Broadband Multimedia untuk Mendukung Daya Saing Bangsa"</li>
              </ul>
              <p><strong>Konsistensi:</strong> Semua tingkatan mempertahankan arah "unggul bertaraf internasional" dan "daya saing bangsa", dengan penajaman kekhasan di tingkat PSBM.</p>
            </div>
            <div class="led-card">
              <h4>📚 Implementasi dalam Kurikulum</h4>
              <p>25 mata kuliah inti PSBM membentuk kompetensi berjenjang dari sistem telekomunikasi dan transmisi, jaringan broadband, komunikasi nirkabel dan serat optik, hingga integrasi dan penerapan teknologi melalui proyek, Magang Industri, dan Skripsi.</p>
              <p><strong>Karakter vokasi:</strong> 53,33% praktik (80 SKS dari 150 SKS total).</p>
            </div>
          </div>
        </div>

        <!-- Sub: Mekanisme -->
        <div class="sub-criteria-panel" id="c1-mekanisme">
          <div class="lkps-section ledps">
            <h3>🔧 Mekanisme Penyusunan VMTS</h3>
            <div class="led-card">
              <h4>👥 Pemangku Kepentingan Internal</h4>
              <ul>
                <li><strong>Dosen:</strong> Melalui tim penyusun VMTS yang mewakili PSBM</li>
                <li><strong>Mahasiswa:</strong> Masukan melalui Forum Dialog Jurusan</li>
                <li><strong>Tendik:</strong> Penjaringan aspirasi dan keterlibatan unsur staf</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🌐 Pemangku Kepentingan Eksternal</h4>
              <ul>
                <li><strong>Alumni:</strong> Masukan berdasarkan pengalaman kerja</li>
                <li><strong>Pengguna Lulusan:</strong> Kebutuhan kompetensi lulusan dan perkembangan industri</li>
                <li><strong>Pakar Industri:</strong>
                  <ul>
                    <li>Marfani (Telkomsel) — komunikasi seluler</li>
                    <li>Hendra Gunawan (MyRepublic) — komunikasi serat optik</li>
                    <li>Irvan Nugraha (Universal Satellite Indonesia) — komunikasi satelit</li>
                  </ul>
                </li>
              </ul>
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: Notulensi FGD & SK</a>
            </div>
            <div class="led-card">
              <h4>📜 SK Penetapan</h4>
              <p><strong>SK Direktur PNJ No. 954/PL3.9/HK.03/2020</strong> tentang VMTS JTE</p>
              <p>Strategi pencapaian disusun mengacu Renstra PNJ dan menjadi arah pengembangan JTE serta PSBM.</p>
            </div>
          </div>
        </div>

        <!-- Sub: Pemahaman -->
        <div class="sub-criteria-panel" id="c1-pemahaman">
          <div class="lkps-section ledps">
            <h3>📊 Sosialisasi & Pemahaman VMTS</h3>
            <div class="led-card">
              <h4>📢 Media Sosialisasi</h4>
              <ul>
                <li>Laman institusi dan jurusan</li>
                <li>Media informasi di lingkungan JTE</li>
                <li>Kegiatan PKKP (Pengenalan Kehidupan Kampus Politeknik)</li>
                <li>Kuliah umum</li>
                <li>Kegiatan yang melibatkan alumni dan mitra industri</li>
                <li>Video profil PSBM</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📈 Hasil Survei Pemahaman</h4>
              <p>Hasil evaluasi menunjukkan bahwa pada seluruh aspek yang dievaluasi, <strong>lebih dari 60% responden</strong> berada pada kategori "Memahami" terhadap VMTS JTE.</p>
              <a href="#" class="evidence-link"> Bukti: Laporan Survei VMTS</a>
            </div>
          </div>
        </div>

        <!-- Sub: Pencapaian -->
        <div class="sub-criteria-panel" id="c1-pencapaian">
          <div class="lkps-section ledps">
            <h3>🎯 Capaian VMTS (Traceability ke LKPS)</h3>
            <div class="led-card">
              <h4>📚 Pendidikan</h4>
              <ul>
                <li>53,33% praktik → <em>LKPS 3.a.1</em></li>
                <li>5 MK diampu praktisi (20%) → <em>LKPS 4.a</em></li>
                <li>Sertifikasi kompetensi mahasiswa (RF Planner, Teknisi Madya Jaringan Komputer)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🔬 Penelitian & PkM</h4>
              <ul>
                <li>45 penelitian (14→13→18), tren meningkat → <em>LKPS 3.b</em></li>
                <li>14 PkM (2→6→6), seluruhnya libatkan mahasiswa → <em>LKPS 3.c</em></li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🏆 Luaran Mahasiswa</h4>
              <ul>
                <li>126 publikasi, 19 prestasi → <em>LKPS 6.c, 6.e</em></li>
                <li>16 produk mahasiswa diadopsi → <em>LKPS 6.e.4</em></li>
              </ul>
            </div>
            <div class="led-card">
              <h4>💼 Daya Saing Lulusan</h4>
              <ul>
                <li>81,96% kesesuaian bidang kerja sedang-tinggi → <em>LKPS 6.f.2</em></li>
                <li>80,32% bekerja nasional-multinasional → <em>LKPS 6.g.1</em></li>
                <li>0% waktu tunggu &gt;18 bulan → <em>LKPS 6.f.1</em></li>
              </ul>
            </div>
            <div class="led-card">
              <h4> Analisis Faktor Keberhasilan & Penghambat</h4>
              <table class="lkps-table">
                <thead><tr><th>Indikator</th><th>Capaian</th><th>Akar Masalah</th><th>Tindak Lanjut</th></tr></thead>
                <tbody>
                  <tr><td>Keselaran VMTS</td><td>Tercapai</td><td>Perlu dijaga konsistensi</td><td>Evaluasi berkala</td></tr>
                  <tr><td>Relevansi pendidikan</td><td>Tercapai</td><td>Teknologi berubah cepat</td><td>Pemutakhiran kurikulum berkelanjutan</td></tr>
                  <tr><td>Dukungan SDM & Tridharma</td><td>Tercapai</td><td>Kapasitas perlu dikembangkan</td><td>Pengembangan kompetensi SDM</td></tr>
                  <tr><td>Internasionalisasi</td><td>Perlu ditingkatkan</td><td>Kerja sama internasional terbatas</td><td>Memperkuat kerja sama internasional berdampak</td></tr>
                  <tr><td>Daya saing global lulusan</td><td>Perlu ditingkatkan</td><td>Bahasa asing belum merata</td><td>Penguatan bahasa asing & sertifikasi</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Sub: SWOT C.1 -->
        <div class="sub-criteria-panel" id="c1-swot">
          <div class="lkps-section ledps">
            <h3>📊 SWOT C.1 — Diferensiasi Misi</h3>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths</h4>
                <ul>
                  <li>S1. Linearitas VMTS PNJ–JTE–PSBM</li>
                  <li>S2. Kekhasan Broadband Multimedia terimplementasi dalam kurikulum</li>
                  <li>S3. SDM memiliki kompetensi relevan</li>
                  <li>S4. Keterlibatan industri dan alumni</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses</h4>
                <ul>
                  <li>W1. Internasionalisasi belum sekuat capaian nasional</li>
                  <li>W2. Kemampuan bahasa asing mahasiswa perlu diperkuat</li>
                  <li>W3. Luaran dan rekognisi internasional masih perlu ditingkatkan</li>
                  <li>W4. Kerja sama internasional berdampak masih terbatas</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities</h4>
                <ul>
                  <li>O1. Perkembangan teknologi broadband, IoT, AI/ML, cloud</li>
                  <li>O2. Kebutuhan industri terhadap SDM telekomunikasi kompeten</li>
                  <li>O3. Peluang sertifikasi kompetensi dan penguatan keterlibatan industri</li>
                  <li>O4. Peluang kerja sama pendidikan/penelitian/PkM nasional/internasional</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats</h4>
                <ul>
                  <li>T1. Perubahan teknologi telekomunikasi dan digital yang cepat</li>
                  <li>T2. Perubahan kebutuhan kompetensi industri</li>
                  <li>T3. Meningkatnya tuntutan sertifikasi dan standar profesional</li>
                  <li>T4. Persaingan lulusan dan program pendidikan</li>
                </ul>
              </div>
            </div>
            <div class="led-card">
              <h4>🎯 Arah Strategi</h4>
              <ul>
                <li><strong>SO:</strong> Memanfaatkan kekhasan Broadband Multimedia, kompetensi SDM, dan jejaring industri untuk mengembangkan pembelajaran, sertifikasi, penelitian terapan, serta kerja sama pada teknologi broadband yang berkembang.</li>
                <li><strong>WO:</strong> Memanfaatkan kerja sama dan perkembangan teknologi untuk memperkuat internasionalisasi, kemampuan bahasa asing, serta luaran dan rekognisi internasional dosen dan mahasiswa.</li>
                <li><strong>ST:</strong> Memanfaatkan relevansi kurikulum, kompetensi SDM, serta keterlibatan industri untuk menjaga kesesuaian kompetensi dengan perubahan teknologi, kebutuhan industri, dan standar profesional.</li>
                <li><strong>WT:</strong> Memperkuat internasionalisasi, kemampuan komunikasi profesional, sertifikasi, dan kerja sama internasional yang berdampak untuk meningkatkan daya saing PSBM dan lulusan pada tingkat global.</li>
              </ul>
            </div>
          </div>
        </div>

      </div>

      <!-- ================================================================ -->
      <!-- C.2 AKUNTABILITAS - SUB KRITERIA -->
      <!-- ================================================================ -->
      <div class="ledps-criteria" id="ledps-c2">
        
        <div class="sub-criteria-nav ledps-sub">
          <button class="active" onclick="showSubCriteria('c2', 'tata-pamong', this)"> Tata Pamong</button>
          <button onclick="showSubCriteria('c2', 'kerja-sama', this)">🤝 Kerja Sama</button>
          <button onclick="showSubCriteria('c2', 'keuangan', this)">💰 Keuangan</button>
          <button onclick="showSubCriteria('c2', 'swot', this)">📊 SWOT C.2</button>
        </div>

        <!-- Sub: Tata Pamong -->
        <div class="sub-criteria-panel active" id="c2-tata-pamong">
          <div class="lkps-section ledps">
            <h3>🏢 Tata Pamong & Tata Kelola</h3>
            <div class="led-card">
              <h4>📜 Dasar Hukum</h4>
              <ul>
                <li><strong>Statuta PNJ No. 35 Tahun 2018</strong></li>
                <li><strong>OTK PNJ No. 60 Tahun 2022</strong> (Permendikbudristek)</li>
                <li><strong>Renstra PNJ 2025-2029</strong> & <strong>Renstra JTE 2025-2029</strong></li>
                <li><strong>SK Direktur No. 1909/PL3/OT/2018</strong> tentang SOP PNJ</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🏛️ Struktur Organisasi</h4>
              <ul>
                <li><strong>Senat:</strong> Penyusun kebijakan serta pertimbangan dan pengawasan akademik</li>
                <li><strong>Direktur:</strong> Dipantu 4 Wakil Direktur (Akademik, Umum & Keuangan, Kemahasiswaan, Kerja Sama)</li>
                <li><strong>SPI:</strong> Satuan Pengawas Internal (pengawasan non-akademik)</li>
                <li><strong>Tingkat UPPS:</strong> Ketua Jurusan, Sekretaris Jurusan, Koordinator PS, KBK, Laboran, GKM</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>⭐ 5 Pilar Good University Governance</h4>
              <ul>
                <li><strong>Kredibel:</strong> Pejabat struktural diangkat melalui mekanisme sesuai Statuta/OTK dengan mempertimbangkan kompetensi dan rekam jejak</li>
                <li><strong>Transparan:</strong> Kebijakan, keputusan, dan capaian kinerja disebarluaskan melalui kanal resmi dan rapat yang melibatkan dosen</li>
                <li><strong>Akuntabel:</strong> Program kerja dipertanggungjawabkan berkala melalui pelaporan berjenjang, AMI, dan audit SPI</li>
                <li><strong>Bertanggung Jawab:</strong> Setiap organ menjalankan tugas sesuai tupoksi dengan tindak lanjut yang jelas atas hasil audit/evaluasi</li>
                <li><strong>Adil:</strong> Kesempatan setara bagi dosen dan tendik dalam pengembangan karier, penugasan Tridharma, dan akses sumber daya</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>👔 Komitmen Pimpinan</h4>
              <ul>
                <li><strong>Visi & Tujuan Strategis:</strong> Penjabaran VMTS institusi ke VMTS Jurusan dan PS secara partisipatif</li>
                <li><strong>Integritas & Transparansi:</strong> Kepatuhan terhadap Kode Etik Dosen, Tendik, dan Mahasiswa PNJ</li>
                <li><strong>Pengembangan SDM:</strong> Fasilitasi studi lanjut S2/S3, dukungan sertifikasi kompetensi (LSP TDI, mitra industri)</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Kerja Sama -->
        <div class="sub-criteria-panel" id="c2-kerja-sama">
          <div class="lkps-section ledps">
            <h3>🤝 Kerja Sama Tridharma — Analisis</h3>
            <div class="led-card">
              <h4>📊 Ringkasan Kerja Sama</h4>
              <ul>
                <li><strong>Total:</strong> 66 kerja sama (42 pendidikan, 17 penelitian, 7 PkM) → <em>LKPS 2.a</em></li>
                <li><strong>Tingkat:</strong> 5 internasional, 45 nasional, 16 lokal/wilayah</li>
                <li><strong>Mitra Strategis:</strong> St. John's University Taiwan, PT Ericsson, PT Huawei, PT Telkomsel, PT NEC, PT MyRepublic, BRIN, Bank BRI</li>
              </ul>
              <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="evidence-link">📂 Bukti: MoU & IA</a>
            </div>
            <div class="led-card">
              <h4>🎯 Relevansi Kerja Sama</h4>
              <ul>
                <li><strong>Pendidikan:</strong> Penyelarasan kurikulum dengan NEC, Huawei, Telkomsel, Ericsson; PKL/magang; dosen tamu/praktisi; sertifikasi LSP TDI</li>
                <li><strong>Penelitian:</strong> Riset terapan dengan Huawei, Ericsson, PT Packet Systems Indonesia, AI Brain Inc; riset infrastruktur dengan PT PLN, PT Pasifik Satelit Nusantara</li>
                <li><strong>PkM:</strong> Pemberdayaan masyarakat dengan PT Bank Rakyat Indonesia (literasi digital), PT Nindya Karya, PT Nexwave Indonesia, PT Eka Mas Republik, PT Jalur Satu Aman</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📈 Manfaat & Kepuasan Mitra</h4>
              <ul>
                <li><strong>Manfaat Pembelajaran:</strong> PKL/magang, dosen tamu, penyelarasan kurikulum, sertifikasi kompetensi</li>
                <li><strong>Peningkatan Kinerja:</strong> Peningkatan jumlah lulusan tersertifikasi, publikasi dosen, kegiatan PkM tahunan, kontribusi hibah peralatan laboratorium</li>
                <li><strong>Kepuasan Mitra:</strong> Dievaluasi melalui survei mencakup komunikasi, responsivitas, kualitas mahasiswa/lulusan, dan keberlanjutan kerja sama</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📊 Analisis Faktor Keberhasilan & Penghambat</h4>
              <table class="lkps-table">
                <thead><tr><th>Faktor</th><th>Deskripsi</th></tr></thead>
                <tbody>
                  <tr><td><strong>Keberhasilan:</strong></td><td>Kelengkapan regulasi (Statuta, OTK), kepemimpinan kolegial-partisipatif, jejaring 65 kerja sama, relevansi kerja sama tinggi, stabilitas anggaran BLU</td></tr>
                  <tr><td><strong>Penghambat:</strong></td><td>Distribusi kerja sama belum merata, tren penurunan dana penelitian/PkM pada TS, instrumen evaluasi kepuasan mitra belum terstandar, ketergantungan pendanaan institusional</td></tr>
                  <tr><td><strong>RTL:</strong></td><td>Perluasan kerja sama pendidikan/penelitian ke tingkat lokal, PkM ke tingkat internasional, penguatan pendampingan proposal hibah, pengembangan instrumen survei kepuasan mitra</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Sub: Keuangan -->
        <div class="sub-criteria-panel" id="c2-keuangan">
          <div class="lkps-section ledps">
            <h3>💰 Keuangan — Analisis</h3>
            <div class="led-card">
              <h4>📊 Ringkasan Keuangan</h4>
              <ul>
                <li><strong>Total Anggaran Rata-rata:</strong> Rp 27,24 M/tahun (UPPS), Rp 4,08 M/tahun (PS) → <em>LKPS 2.b</em></li>
                <li><strong>BOP per Mahasiswa:</strong> Rp 20,36 juta/tahun</li>
                <li><strong>Dana Penelitian:</strong> Rp 144,44 juta/tahun (80% internal, 20% eksternal nasional)</li>
                <li><strong>Dana PkM:</strong> Rp 88,16 juta/tahun (100% internal)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🔍 Prinsip Pengelolaan</h4>
              <ul>
                <li><strong>Akuntabel:</strong> Laporan keuangan sesuai standar akuntansi pemerintahan, diaudit berkala oleh SPI & auditor eksternal</li>
                <li><strong>Transparan:</strong> RKA dan realisasi anggaran disampaikan dalam rapat kerja Jurusan</li>
                <li><strong>Efektif:</strong> Alokasi anggaran diprioritaskan sesuai target Renop, dievaluasi melalui LRA tiap akhir tahun</li>
                <li><strong>Efisien:</strong> Perencanaan berbasis skala prioritas, pemanfaatan sumber daya bersama (laboratorium lintas PS), optimalisasi kontribusi mitra</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📈 Tren & Analisis</h4>
              <ul>
                <li>Tren biaya operasional menunjukkan kecenderungan stabil dengan sedikit penurunan dari TS-2 ke TS (~2,9%)</li>
                <li>Dana penelitian fluktuatif: peningkatan TS-2→TS-1 (+6,7%), penurunan TS-1→TS (-25,3%)</li>
                <li>Dana PkM fluktuatif: peningkatan TS-2→TS-1 (+14,8%), penurunan TS-1→TS (-37,6%)</li>
                <li><strong>Analisis:</strong> Ketersediaan dana memadai, namun diversifikasi pendanaan eksternal perlu ditingkatkan</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: SWOT C.2 -->
        <div class="sub-criteria-panel" id="c2-swot">
          <div class="lkps-section ledps">
            <h3>📊 SWOT C.2 — Akuntabilitas</h3>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths</h4>
                <ul>
                  <li>S1. Regulasi tata kelola lengkap (Statuta, OTK)</li>
                  <li>S2. Kepemimpinan kolegial-partisipatif dan responsif</li>
                  <li>S3. Jejaring 65 kerja sama dengan mitra industri terkemuka</li>
                  <li>S4. Relevansi kerja sama tinggi terhadap Tridharma</li>
                  <li>S5. Anggaran operasional stabil, pengelolaan keuangan akuntabel</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses</h4>
                <ul>
                  <li>W1. Distribusi kerja sama belum merata antartingkat</li>
                  <li>W2. Tren penurunan dana penelitian dan PkM DTPS pada TS</li>
                  <li>W3. Instrumen evaluasi kepuasan mitra belum terstandar</li>
                  <li>W4. Ketergantungan pendanaan pada sumber institusional</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities</h4>
                <ul>
                  <li>O1. Perkembangan teknologi broadband, jaringan, dan AI membuka peluang kerjasama riset dengan vendor global</li>
                  <li>O2. Kebijakan vokasi berbasis link and match mendorong perluasan kerja sama pendidikan/sertifikasi</li>
                  <li>O3. Beragam skema hibah kompetitif nasional yang dapat dioptimalkan</li>
                  <li>O4. Kebutuhan transformasi digital lintas sektor membuka peluang PkM/penelitian baru</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats</h4>
                <ul>
                  <li>T1. Persaingan antar-PT vokasi memperebutkan mitra dan hibah kompetitif</li>
                  <li>T2. Perubahan kebijakan/prioritas pendanaan hibah pemerintah atau mitra</li>
                  <li>T3. Dinamika teknologi yang cepat menuntut pembaruan kompetensi dan kurikulum berkelanjutan</li>
                  <li>T4. Potensi ketidakstabilan komitmen mitra akibat faktor eksternal</li>
                </ul>
              </div>
            </div>
          </div>
        </div>

      </div>

      <!-- ================================================================ -->
      <!-- C.3 DIKLITPMAS - SUB KRITERIA -->
      <!-- ================================================================ -->
      <div class="ledps-criteria" id="ledps-c3">
        
        <div class="sub-criteria-nav ledps-sub">
          <button class="active" onclick="showSubCriteria('c3', 'kurikulum', this)">📘 Kurikulum & CPL</button>
          <button onclick="showSubCriteria('c3', 'rps', this)">📝 RPS & Pembelajaran</button>
          <button onclick="showSubCriteria('c3', 'capstone', this)">🎓 Capstone & Suasana</button>
          <button onclick="showSubCriteria('c3', 'penelitian', this)">🔬 Penelitian</button>
          <button onclick="showSubCriteria('c3', 'pkm', this)">🤝 PkM</button>
          <button onclick="showSubCriteria('c3', 'swot', this)">📊 SWOT C.3</button>
        </div>

        <!-- Sub: Kurikulum & CPL -->
        <div class="sub-criteria-panel active" id="c3-kurikulum">
          <div class="lkps-section ledps">
            <h3>📘 Kurikulum & CPL — Evaluasi</h3>
            <div class="led-card">
              <h4>📚 Struktur Kurikulum</h4>
              <ul>
                <li><strong>Total:</strong> 53 MK, 150 SKS (80 SKS praktik = 53,33%) → <em>LKPS 3.a.1</em></li>
                <li><strong>MK Kompetensi:</strong> 25 MK</li>
                <li><strong>Evaluasi:</strong> 2020, 2021, 2024 (melibatkan dosen, alumni, industri, pakar)</li>
                <li><strong>Profil Lulusan:</strong> 12 profil (IT Engineer, Network Engineer, RF Planner, dll.)</li>
                <li><strong>CPL:</strong> 12 CPL sesuai 4 standar kompetensi lulusan</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🔄 Pemutakhiran Kurikulum</h4>
              <ul>
                <li><strong>2020:</strong> Workshop dengan 16 dosen + 5 narasumber industri (Telkomsel, PT Immobi Solusi Prima, MNC Play, PT Aplikanusa Lintasarta, PT Citra Langgeng Sentosa)</li>
                <li><strong>2021:</strong> FGD Sinkronisasi MB-KM dengan 16 dosen, 4 pengguna lulusan, 6 alumni</li>
                <li><strong>2024:</strong> Workshop OBE dengan 11 dosen, 3 alumni, narasumber dari MyRepublic, PT Kinarya Utama Teknik, IPB</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🎯 Kesesuaian CPL dengan Standar Kompetensi</h4>
              <table class="lkps-table">
                <thead><tr><th>Unsur</th><th>Substansi CPL PSBM</th></tr></thead>
                <tbody>
                  <tr><td>Konsep rekayasa spesifik</td><td>Menerapkan matematika, sains, dan prinsip rekayasa; menguasai matematika rekayasa, engineering principles, sains rekayasa, dan perancangan rekayasa</td></tr>
                  <tr><td>Kemampuan teknis & adaptasi</td><td>Menelusuri dan menerapkan standar ITU, ISO, IEEE; merancang, menginstal, menguji, memodifikasi dan mengintegrasikan sistem</td></tr>
                  <tr><td>Komunikasi & kerja tim</td><td>Berkomunikasi secara individu maupun tim, mengkomunikasikan hasil pekerjaan/rancangan, bertanggung jawab terhadap hasil kerja kelompok</td></tr>
                  <tr><td>Etika profesi</td><td>Menginternalisasi nilai, norma dan etika akademik; bertanggung jawab terhadap pekerjaan; memahami dan menerapkan etika profesi Broadband Multimedia</td></tr>
                </tbody>
              </table>
            </div>
            <div class="led-card">
              <h4>📊 Analisis & Tindak Lanjut</h4>
              <p><strong>Kekuatan:</strong> Kurikulum vokasi kuat, responsif terhadap industri, melibatkan pemangku kepentingan.</p>
              <p><strong>Area Perbaikan:</strong> Dokumentasi pengukuran CPL/CPMK, monitoring pembelajaran, dan tindak lanjut perlu diperkuat melalui mekanisme closed-loop improvement.</p>
            </div>
          </div>
        </div>

        <!-- Sub: RPS & Pembelajaran -->
        <div class="sub-criteria-panel" id="c3-rps">
          <div class="lkps-section ledps">
            <h3>📝 RPS & Proses Pembelajaran</h3>
            <div class="led-card">
              <h4>📋 Ketersediaan RPS</h4>
              <p><strong>100% MK (53 dari 53)</strong> memiliki RPS dengan 9 komponen lengkap:</p>
              <ol>
                <li>Nama PS, nama & kode MK, semester, SKS, nama dosen</li>
                <li>CPL yang dibebankan pada MK</li>
                <li>CPMK/kemampuan akhir</li>
                <li>Bahan kajian</li>
                <li>Metode pembelajaran</li>
                <li>Waktu pembelajaran</li>
                <li>Pengalaman belajar mahasiswa (tugas)</li>
                <li>Kriteria, indikator, dan bobot penilaian</li>
                <li>Daftar referensi</li>
              </ol>
              <p>RPS dapat diakses mahasiswa melalui <strong>LMS PNJ</strong>.</p>
            </div>
            <div class="led-card">
              <h4>🔄 Tinjauan Rutin RPS</h4>
              <p>RPS ditinjau <strong>setiap tahun</strong> oleh dosen pengampu berdasarkan pedoman evaluasi RPS dan hasil pelaksanaan pembelajaran periode sebelumnya.</p>
              <p>Hasil tinjauan diverifikasi oleh <strong>Kaprodi dan Ketua Jurusan</strong>.</p>
            </div>
            <div class="led-card">
              <h4>🎓 Proses Pembelajaran</h4>
              <ul>
                <li><strong>Metode:</strong> Kombinasi teori, praktikum, diskusi, studi kasus, penugasan, PBL</li>
                <li><strong>Media:</strong> LMS PNJ, bahan ajar digital, laboratorium, perangkat lunak/keras, simulator</li>
                <li><strong>Interaksi:</strong> Tatap muka, praktikum, pembimbingan tugas/proyek, WhatsApp, LMS</li>
                <li><strong>Analisis Kritis:</strong> Studi kasus, praktikum, tugas pemecahan masalah, PBL</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🔬 Integrasi Penelitian/PkM dalam Pembelajaran</h4>
              <p><strong>8 bentuk integrasi</strong> hasil penelitian dan PkM DTPS ke dalam pembelajaran:</p>
              <ul>
                <li>Sistem Mikrokontroler, Sistem Komunikasi Seluler 1 & 2, Jaringan Komunikasi Broadband</li>
                <li>Aplikasi Bergerak, Komputasi Pervasive, Keamanan & Kehandalan Jaringan</li>
                <li>Komunikasi Data, Komunikasi Radio & Satelit</li>
              </ul>
              <p><strong>Contoh:</strong> Penelitian 4G/5G, Non-Public Network, Open RAN, NTN-GEO Satellite, antena MIMO 5G, LoRa/LoRaWAN, ZigBee, Ultra Wideband, keamanan jaringan, IoT, cloud computing, computer vision, deep learning, aplikasi bergerak.</p>
            </div>
            <div class="led-card">
              <h4>🔢 Basic Sciences & Matematika (8 SKS)</h4>
              <table class="lkps-table">
                <thead><tr><th>Mata Kuliah</th><th>Semester</th><th>SKS</th></tr></thead>
                <tbody>
                  <tr><td>Matematika Dasar</td><td>1</td><td>2</td></tr>
                  <tr><td>Medan Elektromagnetik</td><td>2</td><td>2</td></tr>
                  <tr><td>Matematika 2</td><td>2</td><td>2</td></tr>
                  <tr><td>Matematika Teknik</td><td>3</td><td>2</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Sub: Capstone & Suasana -->
        <div class="sub-criteria-panel" id="c3-capstone">
          <div class="lkps-section ledps">
            <h3>🎓 Capstone Design & Suasana Akademik</h3>
            <div class="led-card">
              <h4>🏗️ Capstone Design (Skripsi, 10 SKS, Semester 8)</h4>
              <p>Mengacu Rekomendasi FORTEI, seluruh TA/Skripsi PSBM disusun dalam bentuk <strong>engineering design</strong>, bukan penelitian murni, dengan luaran berupa produk, proses, atau sistem rekayasa.</p>
              <ul>
                <li><strong>Panduan:</strong> Buku Panduan Penyusunan TA/Skripsi JTE</li>
                <li><strong>CPMK:</strong> 4 CPMK (identifikasi masalah, proposal rancangan, analisis & pengujian, luaran engineering blueprint)</li>
                <li><strong>Standar Keteknikan:</strong> 3GPP, ITU-R, IEEE Std 145, ITU-T G.652/G.655, IETF RFC, IEEE 802, ISO/IEC 27001, NIST CSF, LoRa Alliance</li>
                <li><strong>Dikerjakan tim/berkelompok</strong> (berbeda dengan pola individual umum)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🎭 Suasana Akademik</h4>
              <ul>
                <li><strong>Dasar:</strong> Permenristekdikti No. 35 Tahun 2018 (Statuta PNJ) — Kebebasan Akademik, Mimbar Akademik, Otonomi Keilmuan</li>
                <li><strong>Program:</strong> Kuliah Umum, Penerbitan Jurnal (Electrices & Spektral), Evaluasi Kurikulum, Kerja Sama Link & Match, Pelatihan & Sertifikasi Dosen, Sertifikat Kompetensi Mahasiswa, Seminar Nasional JTE, Kompetisi Mahasiswa</li>
                <li><strong>Ritme:</strong> 1-2 bulanan (seminar kemajuan TA bulanan, sidang terbuka magang, kuliah umum semesteran, seminar nasional tahunan)</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Penelitian -->
        <div class="sub-criteria-panel" id="c3-penelitian">
          <div class="lkps-section ledps">
            <h3>🔬 Penelitian — Evaluasi</h3>
            <div class="led-card">
              <h4>📊 Data Penelitian</h4>
              <ul>
                <li><strong>Total:</strong> 45 penelitian (14→13→18) → <em>LKPS 3.b</em></li>
                <li><strong>Sumber Dana:</strong> 36 internal (80%), 9 eksternal nasional (20%), 0 luar negeri</li>
                <li><strong>Keterlibatan Mahasiswa:</strong> 12/45 (26,67%) → <em>LKPS 6.h.1</em></li>
                <li><strong>Tema:</strong> AI/ML, IoT, LoRa, 4G/5G, komunikasi nirkabel, antena, cloud computing</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🗺️ Roadmap Penelitian</h4>
              <p>Mengacu Peta Jalan Penelitian JTE dengan tema <strong>"Sistem Cerdas Terintegrasi untuk Industri dan Masyarakat"</strong>, dijabarkan dalam Peta Jalan Penelitian PSBM dengan fokus:</p>
              <ul>
                <li>Big Data, Cloud Computing, AI</li>
                <li>Internet of Things (IoT)</li>
                <li>Mobile Technologies</li>
                <li>Optical Communications</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📈 Analisis & Tindak Lanjut</h4>
              <p><strong>Kekuatan:</strong> Produktivitas baik, tema relevan dengan peta jalan, tren meningkat.</p>
              <p><strong>Area Perbaikan:</strong></p>
              <ul>
                <li>Diversifikasi pendanaan eksternal dan kolaborasi internasional</li>
                <li>Integrasi penelitian dosen dengan TA dan pembelajaran</li>
                <li>Peningkatan keterlibatan mahasiswa (target ≥40%)</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: PkM -->
        <div class="sub-criteria-panel" id="c3-pkm">
          <div class="lkps-section ledps">
            <h3>🤝 PkM — Evaluasi</h3>
            <div class="led-card">
              <h4>📊 Data PkM</h4>
              <ul>
                <li><strong>Total:</strong> 14 kegiatan (2→6→6) → <em>LKPS 3.c</em></li>
                <li><strong>Pendanaan:</strong> 100% internal/mandiri</li>
                <li><strong>Keterlibatan Mahasiswa:</strong> 7 PkM → <em>LKPS 6.i</em></li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🗺️ Roadmap PkM</h4>
              <p>Mengacu Peta Jalan PkM JTE dan dijabarkan dalam Peta Jalan PkM PSBM yang memayungi tema PkM dosen dan mahasiswa serta mengarahkan penerapan hasil penelitian untuk meningkatkan kapasitas mitra.</p>
            </div>
            <div class="led-card">
              <h4>🌟 Contoh PkM Berdampak</h4>
              <ul>
                <li>Smart Aquaculture LoRa di BBI Ciganjur</li>
                <li>Aplikasi Bank Sampah "Bersih Plus" di Kampung Proklim Beji Timur</li>
                <li>Sistem Keamanan IoT Beji Timur</li>
                <li>Website Desa Wisata Kampung Setaman</li>
                <li>Sistem Informasi OJT Kemensos RI</li>
                <li>Pelatihan Kompetensi Digital Beji Timur</li>
              </ul>
              <a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z" target="_blank" class="evidence-link">📂 Bukti: Produk Diadopsi</a>
            </div>
            <div class="led-card">
              <h4>📈 Analisis & Tindak Lanjut</h4>
              <p><strong>Kekuatan:</strong> Dampak masyarakat baik, 100% libatkan mahasiswa, tren meningkat.</p>
              <p><strong>Area Perbaikan:</strong></p>
              <ul>
                <li>Diversifikasi pendanaan eksternal</li>
                <li>Pemanfaatan jejaring kerja sama untuk perluasan pendanaan</li>
                <li>Peningkatan hilirisasi dan pengukuran dampak</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: SWOT C.3 -->
        <div class="sub-criteria-panel" id="c3-swot">
          <div class="lkps-section ledps">
            <h3>📊 SWOT C.3 — Diklitpmas</h3>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths</h4>
                <ul>
                  <li>S1. Kurikulum dievaluasi & dimutakhirkan dengan melibatkan pemangku kepentingan</li>
                  <li>S2. 65 kerja sama tridharma (41 pendidikan, 17 penelitian, 7 PkM)</li>
                  <li>S3. Peta jalan penelitian & PkM relevan dengan Broadband Multimedia</li>
                  <li>S4. Hasil penelitian/PkM terintegrasi dalam pembelajaran</li>
                  <li>S5. Proporsi pembelajaran praktik 53,33% memperkuat karakter vokasi</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses</h4>
                <ul>
                  <li>W1. Dokumentasi CPL/CPMK & closed-loop improvement belum lengkap</li>
                  <li>W2. Pendanaan penelitian 80% internal, belum ada luar negeri</li>
                  <li>W3. Keterlibatan mahasiswa dalam penelitian 26,67%</li>
                  <li>W4. PkM 100% pendanaan internal/mandiri</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities</h4>
                <ul>
                  <li>O1. Perkembangan broadband, IoT, AI/ML, cloud, big data</li>
                  <li>O2. Jejaring kerja sama pendidikan/penelitian/PkM</li>
                  <li>O3. Peluang hibah nasional/internasional (BIMA, DRTPM)</li>
                  <li>O4. Kebutuhan DUDI terhadap solusi transformasi digital</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats</h4>
                <ul>
                  <li>T1. Perkembangan teknologi telekomunikasi & digital cepat</li>
                  <li>T2. Kebutuhan kompetensi & sertifikasi industri meningkat</li>
                  <li>T3. Persaingan hibah & pendanaan eksternal tinggi</li>
                  <li>T4. Tuntutan kolaborasi, publikasi, rekognisi internasional meningkat</li>
                </ul>
              </div>
            </div>
          </div>
        </div>

      </div>

      <!-- ================================================================ -->
      <!-- C.4 SDM - SUB KRITERIA -->
      <!-- ================================================================ -->
      <div class="ledps-criteria" id="ledps-c4">
        
        <div class="sub-criteria-nav ledps-sub">
          <button class="active" onclick="showSubCriteria('c4', 'profil', this)">👨‍ Profil DTPS</button>
          <button onclick="showSubCriteria('c4', 'kualifikasi', this)">🎓 Kualifikasi & JAFA</button>
          <button onclick="showSubCriteria('c4', 'sertifikasi', this)">🏅 Sertifikasi & Praktisi</button>
          <button onclick="showSubCriteria('c4', 'tendik', this)">👷 Tendik</button>
          <button onclick="showSubCriteria('c4', 'beban', this)">️ Beban Kerja</button>
          <button onclick="showSubCriteria('c4', 'kinerja', this)">📈 Kinerja Tridharma</button>
          <button onclick="showSubCriteria('c4', 'luaran', this)">💡 Luaran DTPS</button>
          <button onclick="showSubCriteria('c4', 'rekognisi', this)"> Rekognisi</button>
          <button onclick="showSubCriteria('c4', 'swot', this)">📊 SWOT C.4</button>
        </div>

        <!-- Sub: Profil DTPS -->
        <div class="sub-criteria-panel active" id="c4-profil">
          <div class="lkps-section ledps">
            <h3>👨‍🏫 Profil DTPS — Analisis</h3>
            <div class="led-card">
              <h4>📊 Ringkasan DTPS</h4>
              <ul>
                <li><strong>Total DTPS:</strong> 11 dosen → <em>LKPS 4.a</em></li>
                <li><strong>Rasio Mhs:DTPS:</strong> 1:17,18 — ideal</li>
                <li><strong>Dosen Industri:</strong> 3 DI (Dr. Sinta Novanana, Ir. Lingga Wardhana, Syafnedi)</li>
                <li><strong>Bidang Keahlian:</strong> Telekomunikasi, jaringan & sistem komunikasi, elektronika, machine learning, AI, teknologi digital</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>👥 Daftar DTPS</h4>
              <table class="lkps-table">
                <thead><tr><th>No</th><th>Nama</th><th>Jabatan</th><th>Pendidikan</th><th>Bidang</th></tr></thead>
                <tbody>
                  <tr><td>1</td><td>Dr. Isdawimah, S.T., M.T.</td><td>Lektor Kepala</td><td>Doktor</td><td>Aplikasi Sistem Kelistrikan Energi Terbarukan</td></tr>
                  <tr><td>2</td><td>Nana Sutarna, S.T., M.T., Ph.D.</td><td>Lektor Kepala</td><td>Ph.D.</td><td>Teknologi Rekayasa Elektronika</td></tr>
                  <tr><td>3</td><td>Mera Kartika Delimayanti, Ph.D.</td><td>Lektor Kepala</td><td>Ph.D.</td><td>Sains Data Terapan</td></tr>
                  <tr><td>4</td><td>Zulhelman, S.T., M.T.</td><td>Lektor Kepala</td><td>Magister</td><td>Teknologi Rekayasa Internet</td></tr>
                  <tr><td>5</td><td>Agus Wagyana, S.T., M.T.</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Internet</td></tr>
                  <tr><td>6</td><td>Asri Wulandari, S.T., M.T.</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Telekomunikasi</td></tr>
                  <tr><td>7</td><td>Dandun Widhiantoro, S.T., M.T.</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Telekomunikasi</td></tr>
                  <tr><td>8</td><td>Mohamad Fathurahman, S.T., M.T.</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Internet</td></tr>
                  <tr><td>9</td><td>Viving Frendiana, S.ST., M.T.</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Internet</td></tr>
                  <tr><td>10</td><td>Toto Supriyanto, S.T., M.T.</td><td>Lektor</td><td>Magister</td><td>Teknologi Telekomunikasi</td></tr>
                  <tr><td>11</td><td>Shita Herfiah, S.Pd., M.T.</td><td>Asisten Ahli</td><td>Magister</td><td>Teknologi Rekayasa Telekomunikasi</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Sub: Kualifikasi & JAFA -->
        <div class="sub-criteria-panel" id="c4-kualifikasi">
          <div class="lkps-section ledps">
            <h3>🎓 Kualifikasi & Jabatan Akademik</h3>
            <div class="led-card">
              <h4>📊 Distribusi Kualifikasi</h4>
              <div class="summary-grid">
                <div class="summary-card"><div class="sc-label">Doktor/Ph.D.</div><div class="sc-value">3</div><div class="sc-desc">27,27% (melampaui target Renstra JTE 13%)</div></div>
                <div class="summary-card"><div class="sc-label">Lektor Kepala</div><div class="sc-value">4</div><div class="sc-desc">36,36% (target 50%)</div></div>
                <div class="summary-card"><div class="sc-label">Lektor</div><div class="sc-value">6</div><div class="sc-desc">54,54%</div></div>
                <div class="summary-card"><div class="sc-label">Asisten Ahli</div><div class="sc-value">1</div><div class="sc-desc">9,09%</div></div>
                <div class="summary-card highlight-data"><div class="sc-label">Lektor+</div><div class="sc-value">90,91%</div><div class="sc-desc">10 dari 11 DTPS</div></div>
                <div class="summary-card"><div class="sc-label">Guru Besar</div><div class="sc-value">0</div><div class="sc-desc">Belum ada</div></div>
              </div>
            </div>
            <div class="led-card">
              <h4>📈 Analisis & Rencana Pengembangan</h4>
              <ul>
                <li><strong>Kekuatan:</strong> 90,91% DTPS Lektor atau lebih tinggi, 3 doktor (27,27%)</li>
                <li><strong>Area Pengembangan:</strong> Percepatan Guru Besar, peningkatan Lektor Kepala ke 50%, studi lanjut S3</li>
                <li><strong>Strategi:</strong> Pendampingan kenaikan JAFA, roadmap karier akademik, pemantauan berkala</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Sertifikasi & Praktisi -->
        <div class="sub-criteria-panel" id="c4-sertifikasi">
          <div class="lkps-section ledps">
            <h3>🏅 Sertifikasi & Praktisi</h3>
            <div class="led-card">
              <h4>📊 Sertifikasi DTPS</h4>
              <p><strong>100% DTPS (11/11)</strong> memiliki sertifikat kompetensi/profesi/industri yang masih berlaku.</p>
              <p><strong>Bidang Sertifikasi:</strong> Telekomunikasi, RF, drive test, fiber optic, IoT, cloud computing, data science, AI, manajemen proyek, energi, asesmen kompetensi.</p>
              <p><strong>Lembaga:</strong> BNSP, Kementerian, Huawei, Google, Cisco, CQI & IRCA, EC-Council, PeopleCert, PASAS Institute.</p>
            </div>
            <div class="led-card">
              <h4>👨‍💼 Dosen Industri/Praktisi</h4>
              <p><strong>5 dari 25 MK kompetensi (20%)</strong> diampu dosen industri/praktisi:</p>
              <ul>
                <li>Optimasi Jaringan — Dr. Sinta Novanana (Train4best)</li>
                <li>Kecerdasan Buatan — DI (AIBrain Korea)</li>
                <li>Komputasi Awan & Big Data — DI</li>
                <li>Perancangan Jaringan Serat Optik — Syafnedi (Kopindosat)</li>
                <li>Sistem Komunikasi Serat Optik — DI</li>
                <li>Manajemen Proyek — Ir. Lingga Wardhana (Floatway System, LSP TDI)</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Tendik -->
        <div class="sub-criteria-panel" id="c4-tendik">
          <div class="lkps-section ledps">
            <h3>👷 Tenaga Kependidikan (Laboran)</h3>
            <div class="led-card">
              <h4>📊 Data Tendik</h4>
              <ul>
                <li><strong>Total Laboran JTE:</strong> 8 orang → <em>LKPS 4.b</em></li>
                <li><strong>Bersertifikat:</strong> 6/8 (75%)</li>
                <li><strong>Aktif untuk PSBM:</strong> 4 laboran</li>
                <li><strong>Ruang Lab/Bengkel:</strong> 7 lab + 1 bengkel</li>
                <li><strong>Penggunaan:</strong> Rata-rata 4 ruang/hari, maksimum 5 ruang bersamaan</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>👥 Daftar Laboran</h4>
              <table class="lkps-table">
                <thead><tr><th>No</th><th>Nama</th><th>Pendidikan</th><th>Sertifikat</th><th>Unit</th></tr></thead>
                <tbody>
                  <tr><td>1</td><td>Vida Farida Damayanti</td><td>D3</td><td>IoT Networking</td><td>PS</td></tr>
                  <tr><td>2</td><td>Achmad</td><td>D3</td><td>Teknisi Instrumentasi</td><td>UPPS</td></tr>
                  <tr><td>3</td><td>Agus Setiawan</td><td>S1</td><td>Junior Network Admin</td><td>PS</td></tr>
                  <tr><td>4</td><td>Riri Octaviani</td><td>S1</td><td>Pelaksana Utama Tegangan Rendah</td><td>UPPS</td></tr>
                  <tr><td>5</td><td>Illa Nurabika</td><td>D3</td><td>Network Admin, K3 Muda, P3K</td><td>UPPS</td></tr>
                  <tr><td>6</td><td>Hari Surahman</td><td>S1</td><td>Network Engineer</td><td>PS</td></tr>
                  <tr><td>7</td><td>Iing Ibrahim</td><td>SMA/SMK</td><td>—</td><td>PS</td></tr>
                  <tr><td>8</td><td>Ilham Yanuar</td><td>D3</td><td>Pelaksana Utama Tegangan Rendah</td><td>UPPS</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Sub: Beban Kerja -->
        <div class="sub-criteria-panel" id="c4-beban">
          <div class="lkps-section ledps">
            <h3>⚖️ Beban Kerja DTPS</h3>
            <div class="led-card">
              <h4>📊 Rata-rata Beban Kerja</h4>
              <p><strong>RBK: 14,77 SKS/semester</strong> (rentang ideal 12-16 SKS)</p>
              <div class="summary-grid">
                <div class="summary-card"><div class="sc-label">Pendidikan</div><div class="sc-value">9,98</div><div class="sc-desc">SKS</div></div>
                <div class="summary-card"><div class="sc-label">Penelitian</div><div class="sc-value">2,22</div><div class="sc-desc">SKS</div></div>
                <div class="summary-card"><div class="sc-label">PkM</div><div class="sc-value">1,70</div><div class="sc-desc">SKS</div></div>
                <div class="summary-card"><div class="sc-label">Tugas Tambahan</div><div class="sc-value">0,88</div><div class="sc-desc">SKS</div></div>
              </div>
            </div>
            <div class="led-card">
              <h4>📈 Distribusi Beban</h4>
              <ul>
                <li>3 DTPS pada rentang 13-14 SKS</li>
                <li>3 DTPS pada rentang 14-15 SKS</li>
                <li>5 DTPS pada rentang 15-16 SKS</li>
                <li><strong>Seluruh DTPS ≤16 SKS</strong> — proporsional</li>
              </ul>
              <p><strong>Pemantauan:</strong> Dilakukan setiap semester untuk menjaga distribusi tetap proporsional.</p>
            </div>
          </div>
        </div>

        <!-- Sub: Kinerja Tridharma -->
        <div class="sub-criteria-panel" id="c4-kinerja">
          <div class="lkps-section ledps">
            <h3>📈 Kinerja Tridharma DTPS</h3>
            <div class="led-card">
              <h4>🔬 Penelitian</h4>
              <ul>
                <li><strong>45 penelitian</strong> dalam 3 tahun (14→13→18)</li>
                <li>Tren meningkat pada TS (18 penelitian)</li>
                <li>80% internal, 20% eksternal nasional, 0% luar negeri</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🤝 PkM</h4>
              <ul>
                <li><strong>14 kegiatan</strong> dalam 3 tahun (2→6→6)</li>
                <li>100% internal/mandiri</li>
                <li>Seluruhnya melibatkan mahasiswa</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📚 Publikasi (220 total)</h4>
              <ul>
                <li><strong>73</strong> Jurnal Nasional Terakreditasi</li>
                <li><strong>12</strong> Jurnal Internasional Bereputasi</li>
                <li><strong>92</strong> Prosiding Nasional</li>
                <li><strong>33</strong> Prosiding Scopus/WoS</li>
                <li>Tren meningkat: 48 (TS-2) → 74 (TS-1) → 98 (TS)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>✍️ Penulis Utama (20 publikasi, 6 DTPS)</h4>
              <p>6 dari 11 DTPS (54,55%) memiliki karya sebagai penulis utama pada jurnal/prosiding internasional bereputasi.</p>
              <p>Distribusi: 7 (TS-2), 6 (TS-1), 7 (TS).</p>
            </div>
            <div class="led-card">
              <h4>📖 Sitasi (94 karya, 500 sitasi)</h4>
              <p>Rata-rata <strong>5,32 sitasi per artikel</strong>. Karya ilmiah DTPS digunakan sebagai rujukan komunitas ilmiah.</p>
            </div>
          </div>
        </div>

        <!-- Sub: Luaran DTPS -->
        <div class="sub-criteria-panel" id="c4-luaran">
          <div class="lkps-section ledps">
            <h3>💡 Luaran Penelitian & PkM DTPS</h3>
            <div class="led-card">
              <h4>📊 Ringkasan Luaran</h4>
              <div class="summary-grid">
                <div class="summary-card"><div class="sc-label">Paten/Paten Sederhana</div><div class="sc-value">3</div></div>
                <div class="summary-card"><div class="sc-label">HKI (Hak Cipta)</div><div class="sc-value">36</div></div>
                <div class="summary-card"><div class="sc-label">Teknologi Tepat Guna</div><div class="sc-value">4</div></div>
                <div class="summary-card"><div class="sc-label">Buku/Book Chapter</div><div class="sc-value">14</div></div>
                <div class="summary-card highlight-data"><div class="sc-label">Produk Diadopsi</div><div class="sc-value">13</div></div>
              </div>
            </div>
            <div class="led-card">
              <h4>📦 Contoh Produk Diadopsi</h4>
              <ul>
                <li>PJU Hybrid PV & Angin Terintegrasi IoT (Dr. Isdawimah)</li>
                <li>Metode Deteksi Gangguan Tidur Berbasis Web (Nana Sutarna)</li>
                <li>Stasiun Pengisian Daya E-Bike Plug & Play (Nana Sutarna)</li>
                <li>Sistem Keamanan Lingkungan IoT (Viving Frendiana)</li>
                <li>Smart Aquaculture LoRa (Mohamad Fathurahman)</li>
                <li>Aplikasi Bank Sampah (Asri Wulandari)</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Rekognisi -->
        <div class="sub-criteria-panel" id="c4-rekognisi">
          <div class="lkps-section ledps">
            <h3>🏆 Rekognisi DTPS</h3>
            <div class="led-card">
              <h4>📊 Ringkasan Rekognisi</h4>
              <ul>
                <li><strong>10 dari 11 DTPS (90,91%)</strong> memperoleh rekognisi → <em>LKPS 4.j</em></li>
                <li><strong>Total:</strong> 43 kegiatan/pengakuan</li>
                <li><strong>33</strong> sebagai editor/mitra bestari</li>
                <li><strong>7</strong> sebagai staf ahli/narasumber</li>
                <li><strong>3</strong> penghargaan atas prestasi & kinerja</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🌟 Contoh Rekognisi Internasional</h4>
              <ul>
                <li>Mera Kartika Delimayanti: Reviewer Scientific Reports, Discover Applied Sciences, BMC Medical Informatics, BMC Public Health</li>
                <li>Nana Sutarna: Reviewer Recognition (AI-Based Solar Irradiance Prediction Models)</li>
                <li>Nana Sutarna: Jury Electric, Electronics & Telecommunication — International Borneo Innovation Exhibition 2025</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: SWOT C.4 -->
        <div class="sub-criteria-panel" id="c4-swot">
          <div class="lkps-section ledps">
            <h3>📊 SWOT C.4 — SDM</h3>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths</h4>
                <ul>
                  <li>S1. Rasio DTPS-mahasiswa ±1:17 dengan kompetensi sesuai</li>
                  <li>S2. DTPS S3 mencapai 27,27% (melampaui target 13%)</li>
                  <li>S3. 90,91% DTPS Lektor atau lebih tinggi</li>
                  <li>S4. 100% DTPS bersertifikat kompetensi/profesi/industri</li>
                  <li>S5. Beban kerja proporsional (14,77 SKS/semester)</li>
                  <li>S6. Produktivitas penelitian, publikasi, luaran, adopsi produk, rekognisi baik</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses</h4>
                <ul>
                  <li>W1. Lektor Kepala 36,36% (target 50%), belum ada Guru Besar</li>
                  <li>W2. Pendanaan penelitian/PkM didominasi internal</li>
                  <li>W3. Keterlibatan mahasiswa dalam penelitian belum menyeluruh</li>
                  <li>W4. Publikasi bereputasi & rekognisi internasional belum merata</li>
                  <li>W5. Sertifikasi kompetensi belum mencakup seluruh laboran</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities</h4>
                <ul>
                  <li>O1. Peluang hibah penelitian/PkM & dukungan publikasi</li>
                  <li>O2. Kolaborasi DUDI & perguruan tinggi nasional/internasional</li>
                  <li>O3. Perkembangan 5G/6G, IoT, AI, cloud, big data</li>
                  <li>O4. Sertifikasi profesional & jejaring akademik internasional</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats</h4>
                <ul>
                  <li>T1. Perkembangan teknologi cepat menuntut pembaruan kompetensi</li>
                  <li>T2. Kompetisi hibah, publikasi bereputasi, rekognisi internasional tinggi</li>
                  <li>T3. Standar kompetensi industri & persyaratan JAFA terus meningkat</li>
                </ul>
              </div>
            </div>
          </div>
        </div>

      </div>

      <!-- ================================================================ -->
      <!-- C.5 SARPRAS - SUB KRITERIA -->
      <!-- ================================================================ -->
      <div class="ledps-criteria" id="ledps-c5">
        
        <div class="sub-criteria-nav ledps-sub">
          <button class="active" onclick="showSubCriteria('c5', 'sarana', this)">🔧 Sarana Pembelajaran</button>
          <button onclick="showSubCriteria('c5', 'nonakademik', this)">🏢 Sarana Non-Akademik</button>
          <button onclick="showSubCriteria('c5', 'tik', this)">💻 TIK</button>
          <button onclick="showSubCriteria('c5', 'k3l', this)">️ K3L</button>
          <button onclick="showSubCriteria('c5', 'swot', this)">📊 SWOT C.5</button>
        </div>

        <!-- Sub: Sarana Pembelajaran -->
        <div class="sub-criteria-panel active" id="c5-sarana">
          <div class="lkps-section ledps">
            <h3>🔧 Sarana Pembelajaran</h3>
            <div class="led-card">
              <h4>🏫 Laboratorium & Bengkel</h4>
              <ul>
                <li><strong>7 Laboratorium:</strong> Elektronika Analog & Digital, Sistem Transmisi, Sistem Telekomunikasi, Mikrokontroler & Antarmuka, Komunikasi Data & Serat Optik, Jaringan Broadband, Smartlab</li>
                <li><strong>1 Bengkel:</strong> Elektronika & Fabrikasi Antena</li>
                <li><strong>Ruang Kelas:</strong> 12 ruang</li>
                <li><strong>Ruang Penyimpanan Alat:</strong> G106, G116</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📊 Pemanfaatan</h4>
              <ul>
                <li>Rata-rata penggunaan: <strong>16 jam/minggu</strong></li>
                <li>Seluruh peralatan <strong>terawat dan berfungsi</strong></li>
                <li>Digunakan untuk pembelajaran, penelitian, PkM, proyek, TA</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🤝 Pengembangan dengan Industri</h4>
              <ul>
                <li><strong>Smart Laboratory:</strong> Competitive Fund 2021 & Matching Fund 2023 (Telkomsel, MyRepublic, Pasifik Satelit Nusantara, NEC, Floatway System, Jalur Satu Aman)</li>
                <li><strong>Pelatihan Dosen:</strong> ND-PKD Vokasi 2024, KLSD 2025</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Non-Akademik -->
        <div class="sub-criteria-panel" id="c5-nonakademik">
          <div class="lkps-section ledps">
            <h3>🏢 Sarana Non-Akademik</h3>
            <div class="led-card">
              <h4> Layanan Kesehatan & Konseling</h4>
              <ul>
                <li>Layanan Kesehatan PNJ</li>
                <li>Klinik MAKARA UI (Klinik Satelit)</li>
                <li>Layanan Konseling</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🕌 Fasilitas Ibadah & Kemahasiswaan</h4>
              <ul>
                <li>Masjid Darul Ilmi</li>
                <li>Gedung Pusat Kegiatan Mahasiswa (PUSGIWA)</li>
                <li>Lapangan Spirit PNJ, Kantin, Gedung Parkir</li>
                <li>Aula, Mini Convention, Ruang Pertemuan</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🚌 Transportasi</h4>
              <ul>
                <li>Bis Kuning (Kerjasama dengan UI)</li>
                <li>Bipol PNJ</li>
                <li>Halte PNJ</li>
                <li>Rusunawa (dekat kampus)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📚 Perpustakaan</h4>
              <ul>
                <li>Koleksi: 10.625 judul buku, 30.513 eksemplar</li>
                <li>Akses online: <a href="https://opac.pnj.ac.id" target="_blank">opac.pnj.ac.id</a></li>
                <li>E-resources: Perpusnas, IOS, Cambridge, ProQuest, Taylor & Francis</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: TIK -->
        <div class="sub-criteria-panel" id="c5-tik">
          <div class="lkps-section ledps">
            <h3>💻 Sarana TIK</h3>
            <div class="led-card">
              <h4>🌐 Layanan TIK PNJ</h4>
              <table class="lkps-table">
                <thead><tr><th>No</th><th>Layanan</th><th>Akses</th></tr></thead>
                <tbody>
                  <tr><td>1</td><td>LMS E-learning</td><td>elearning.pnj.ac.id</td></tr>
                  <tr><td>2</td><td>SIAKAD (Spirit Academia)</td><td>academia.pnj.ac.id</td></tr>
                  <tr><td>3</td><td>PMB</td><td>penerimaan.pnj.ac.id</td></tr>
                  <tr><td>4</td><td>Pusat Layanan</td><td>layanan.pnj.ac.id</td></tr>
                  <tr><td>5</td><td>SIM Litmas</td><td>simlitmas.pnj.ac.id</td></tr>
                  <tr><td>6</td><td>LAPOR!</td><td>lapor.go.id</td></tr>
                  <tr><td>7</td><td>Perpustakaan Digital</td><td>perpustakaan.pnj.ac.id</td></tr>
                  <tr><td>8</td><td>Jurnal JTE (Spectral & Electrices)</td><td>jurnal.pnj.ac.id</td></tr>
                  <tr><td>9</td><td>Prosiding SNTE</td><td>prosiding.pnj.ac.id</td></tr>
                  <tr><td>10</td><td>SIMPEG</td><td>simpeg.pnj.ac.id</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Sub: K3L -->
        <div class="sub-criteria-panel" id="c5-k3l">
          <div class="lkps-section ledps">
            <h3>⚠️ K3L — Evaluasi</h3>
            <div class="led-card">
              <h4>📋 Dokumen K3L (17 dokumen)</h4>
              <ul>
                <li>Pedoman SMK3L PNJ</li>
                <li>Pedoman K3L JTE</li>
                <li>13 SOP K3L (Identifikasi Bahaya, Pelatihan, Tanggap Darurat, Audit Internal, dll.)</li>
                <li>SOP Penggunaan Lab & Bengkel</li>
                <li>Hasil Tinjauan Berkala K3 (5 November 2025)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🧯 Fasilitas K3L (12 item, semua terawat)</h4>
              <ul>
                <li>Hidran Pilar (2), APAR (6), APAB (1), Truk Damkar (1)</li>
                <li>Ambulance (1), Kotak P3K (2)</li>
                <li>Rambu Keselamatan (7), Sign System APD (5)</li>
                <li>Lemari Bahan Kimia (2), Tanda Jalur Evakuasi (22)</li>
                <li>Video Safety Induction (1)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📊 Analisis & Tindak Lanjut</h4>
              <ul>
                <li><strong>Kekuatan:</strong> Kebijakan lengkap, implementasi konsisten, fasilitas terawat</li>
                <li><strong>Area Perbaikan:</strong> Audit formal K3L tingkat jurusan belum dilaksanakan, konsistensi budaya K3L perlu ditingkatkan</li>
                <li><strong>RTL:</strong> Audit formal, monitoring berkala, sosialisasi berkelanjutan</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: SWOT C.5 -->
        <div class="sub-criteria-panel" id="c5-swot">
          <div class="lkps-section ledps">
            <h3>📊 SWOT C.5 — Sarpras & K3L</h3>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths</h4>
                <ul>
                  <li>S1. Laboratorium, bengkel, ruang kelas, perpustakaan, TIK memadai</li>
                  <li>S2. Lab mendukung kompetensi elektronika, transmisi, serat optik, broadband, mikrokontroler, antena</li>
                  <li>S3. Fasilitas dimanfaatkan untuk pembelajaran, penelitian, PkM, proyek, TA</li>
                  <li>S4. Kerja sama DUDI (Smart Lab via Competitive Fund & Matching Fund)</li>
                  <li>S5. Fasilitas fisik & digital dapat diakses mahasiswa & dosen</li>
                  <li>S6. Pedoman SMK3, SOP SMK3L, IBPR, APD, rambu keselamatan, jalur evakuasi, safety induction, inspeksi internal tersedia</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses</h4>
                <ul>
                  <li>W1. Intensitas penggunaan tinggi → pemeliharaan berkelanjutan</li>
                  <li>W2. Kemutakhiran peralatan perlu dievaluasi (perkembangan teknologi cepat)</li>
                  <li>W3. Data inventaris perlu dilengkapi & dimutakhirkan</li>
                  <li>W4. Informasi akses, jadwal, SOP, peminjaman belum terintegrasi</li>
                  <li>W5. Audit formal K3L tingkat jurusan belum dilaksanakan</li>
                  <li>W6. Konsistensi budaya & kepatuhan K3L perlu ditingkatkan</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities</h4>
                <ul>
                  <li>O1. Jejaring DUDI → pengembangan lab, hibah/peremajaan alat, transfer teknologi</li>
                  <li>O2. Program pendanaan eksternal untuk pengembangan sarpras</li>
                  <li>O3. Perkembangan broadband, jaringan, telekomunikasi, multimedia</li>
                  <li>O4. Teknologi digital → integrasi inventaris, penjadwalan, pemantauan</li>
                  <li>O5. DUDI sebagai sumber masukan kebutuhan kompetensi & fasilitas</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats</h4>
                <ul>
                  <li>T1. Perkembangan teknologi → peralatan kurang relevan</li>
                  <li>T2. Intensitas penggunaan → percepatan penurunan kondisi</li>
                  <li>T3. Perubahan peralatan & aktivitas → risiko K3L baru</li>
                  <li>T4. Kebutuhan pembaruan → peningkatan sumber daya</li>
                  <li>T5. Perubahan kebutuhan kompetensi → penyesuaian fasilitas</li>
                </ul>
              </div>
            </div>
          </div>
        </div>

      </div>

      <!-- ================================================================ -->
      <!-- C.6 LUARAN - SUB KRITERIA -->
      <!-- ================================================================ -->
      <div class="ledps-criteria" id="ledps-c6">
        
        <div class="sub-criteria-nav ledps-sub">
          <button class="active" onclick="showSubCriteria('c6', 'mahasiswa', this)">‍🎓 Mahasiswa</button>
          <button onclick="showSubCriteria('c6', 'prestasi', this)"> Prestasi & Luaran</button>
          <button onclick="showSubCriteria('c6', 'masa-studi', this)">📅 Masa Studi & Kelulusan</button>
          <button onclick="showSubCriteria('c6', 'tracer', this)">📈 Tracer Study</button>
          <button onclick="showSubCriteria('c6', 'kepuasan', this)">⭐ Kepuasan Pengguna</button>
          <button onclick="showSubCriteria('c6', 'swot', this)">📊 SWOT C.6</button>
        </div>

        <!-- Sub: Mahasiswa -->
        <div class="sub-criteria-panel active" id="c6-mahasiswa">
          <div class="lkps-section ledps">
            <h3>👨🎓 Mahasiswa — Analisis</h3>
            <div class="led-card">
              <h4>📊 Data Mahasiswa</h4>
              <ul>
                <li><strong>Mahasiswa Aktif:</strong> 189 (TS) → <em>LKPS 6.a</em></li>
                <li><strong>Rasio Mhs:DTPS:</strong> 1:17,18 — proporsional</li>
                <li><strong>Mahasiswa Asing:</strong> 13 (1 FT, 12 PT dari Turki & Malaysia)</li>
                <li><strong>IPK Rata-rata:</strong> 3,46 (TS-2: 3,49, TS-1: 3,45, TS: 3,43)</li>
                <li><strong>Masa Studi:</strong> 4,06 tahun</li>
                <li><strong>Kelulusan Tepat Waktu:</strong> 95,025%</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📈 Tren IPK</h4>
              <p>Ada kecenderungan penurunan IPK dari 3,49 (TS-2) → 3,45 (TS-1) → 3,43 (TS). Meskipun rata-rata 3 tahun (3,46) masih di atas target internal (3,40), tren ini perlu ditelusuri lebih lanjut.</p>
              <p><strong>Faktor:</strong> Dampak learning loss pasca pandemi, transisi ke evaluasi tatap muka penuh.</p>
            </div>
            <div class="led-card">
              <h4> Internasionalisasi Mahasiswa</h4>
              <ul>
                <li>13 mahasiswa asing (Program Darmasiswa & Student Mobility)</li>
                <li>Asal: Malaysia (student mobility), Turki (Darmasiswa)</li>
                <li><strong>Analisis:</strong> Capaian positif, namun variasi negara & bentuk program masih terbatas</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Prestasi & Luaran -->
        <div class="sub-criteria-panel" id="c6-prestasi">
          <div class="lkps-section ledps">
            <h3>🏆 Prestasi & Luaran — Analisis</h3>
            <div class="led-card">
              <h4> Prestasi Akademik (10)</h4>
              <ul>
                <li><strong>Internasional (2):</strong> Cisco APJC NetAcad Riders 2024 (Juara 2 Silver, Juara 3 Bronze)</li>
                <li><strong>Nasional (8):</strong> Tech Enthusiast Day 2021, NETCOMP 2022, E-TIME 2022 & 2023, IONIC 2023, Networking Competition TED 2021, NETCOMP 2024</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🎭 Prestasi Nonakademik (9)</h4>
              <ul>
                <li><strong>Internasional (1):</strong> Global Youth Model United Nations 2020</li>
                <li><strong>Nasional (5):</strong> Lomba Video Edukatif NBC 2024, Pencak Silat Dispora DKI 2024, Lomba Poster Digital Berlian 2025, Lomba Content Creator Dies Natalis PNJ 2024, Prabu Taekwondo Challenge 6 & 7</li>
                <li><strong>Wilayah (3):</strong> Lomba Poster Ilmiah IE Competition 2023, Solo Vocal Competition Olimpiade Politeknik 2024, dll.</li>
              </ul>
            </div>
            <div class="led-card">
              <h4> Publikasi Mahasiswa (126)</h4>
              <ul>
                <li><strong>34</strong> Jurnal Nasional Terakreditasi</li>
                <li><strong>1</strong> Jurnal Internasional Bereputasi</li>
                <li><strong>91</strong> Prosiding Seminar Nasional/Wilayah</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>💡 Luaran Penelitian/PkM Mahasiswa (19)</h4>
              <ul>
                <li><strong>16</strong> HKI (Pencatatan Ciptaan)</li>
                <li><strong>1</strong> Teknologi Tepat Guna (TKT 3)</li>
                <li><strong>2</strong> Buku ber-ISBN/Book Chapter</li>
              </ul>
            </div>
            <div class="led-card">
              <h4> Produk Mahasiswa Diadopsi (16)</h4>
              <p>16 produk/karya mahasiswa telah dimanfaatkan masyarakat melalui penelitian & PkM.</p>
              <ul>
                <li>Web Sekolah & Sistem Pemantauan KBM</li>
                <li>Website Desa Wisata Kampung Setaman</li>
                <li>Aplikasi Bank Sampah "Bersih Plus"</li>
                <li>Smart Aquaculture LoRa BBI Ciganjur</li>
                <li>Sistem Keamanan IoT Beji Timur</li>
                <li>Sistem Informasi OJT Kemensos RI</li>
                <li>Peduli PMI — Sistem Informasi PMI Malaysia</li>
                <li>Website Admin Chatbot & Voicebot Kejaksaan Agung</li>
                <li>Monitoring Jaringan & Automasi Router Ansible</li>
                <li>Antena Mikrostrip Array Dual Band 2.4/5.8 GHz</li>
                <li>Website Administrasi Bank Sampah</li>
                <li>Antena Quasi Yagi Peredam Wi-Fi</li>
                <li>Monitoring Hidroponik IoT Tenaga Surya</li>
                <li>Pemantau Suhu Mesin Roasting + Telegram</li>
                <li>Automasi Backup VM & Konfigurasi Jaringan ISP</li>
              </ul>
              <a href="https://drive.google.com/drive/folders/1gj3fyC_mO2c6pDTNRzhnlPcIE4_pKBYS" target="_blank" class="evidence-link">📂 Bukti: Produk Mahasiswa</a>
            </div>
          </div>
        </div>

        <!-- Sub: Masa Studi & Kelulusan -->
        <div class="sub-criteria-panel" id="c6-masa-studi">
          <div class="lkps-section ledps">
            <h3>📅 Masa Studi & Kelulusan Tepat Waktu</h3>
            <div class="led-card">
              <h4>⏱️ Masa Studi</h4>
              <ul>
                <li><strong>Rata-rata:</strong> 4,05 tahun</li>
                <li><strong>TS-7:</strong> 39/41 (95,12%) lulus 3,5-4,5 tahun; 2/41 (4,88%) 4,5-5,5 tahun</li>
                <li><strong>TS-6:</strong> 39/42 (92,86%) lulus 3,5-4,5 tahun; 3/42 (7,14%) 4,5-5,5 tahun</li>
                <li><strong>Tidak ada lulusan</strong> dengan masa studi &gt;5,5 tahun</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🎓 Kelulusan Tepat Waktu</h4>
              <ul>
                <li><strong>Rata-rata PTW:</strong> 95,025%</li>
                <li><strong>TS-7:</strong> 95,1% tepat waktu</li>
                <li><strong>TS-6:</strong> 92,9% tepat waktu</li>
                <li><strong>TS-5:</strong> 97,7% tepat waktu</li>
                <li><strong>TS-4:</strong> 94,7% tepat waktu</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Tracer Study -->
        <div class="sub-criteria-panel" id="c6-tracer">
          <div class="lkps-section ledps">
            <h3>📈 Tracer Study — Evaluasi</h3>
            <div class="led-card">
              <h4>📊 Data Tracer</h4>
              <ul>
                <li><strong>Populasi:</strong> 80 lulusan (TS-2: 44, TS-1: 36)</li>
                <li><strong>Terlacak:</strong> 61 (76,25%) → <em>LKPS 6.f.1</em></li>
                <li><strong>Waktu Tunggu:</strong> 55,74% &lt;3 bulan, 44,26% 3-18 bulan, 0% &gt;18 bulan</li>
                <li><strong>Kesesuaian Bidang:</strong> 70,49% tinggi, 18,03% sedang, 11,48% rendah → <em>LKPS 6.f.2</em></li>
                <li><strong>Tempat Kerja:</strong> 63,93% nasional, 16,39% multinasional, 19,67% lokal → <em>LKPS 6.g.1</em></li>
              </ul>
            </div>
            <div class="led-card">
              <h4> Analisis & Tindak Lanjut</h4>
              <ul>
                <li><strong>Kekuatan:</strong> 0% WT &gt;18 bulan, 80,32% bekerja nasional+multinasional</li>
                <li><strong>Area Perbaikan:</strong> Peningkatan response rate tracer (target ≥80%), penelusuran lulusan dengan kesesuaian rendah</li>
                <li><strong>RTL:</strong> Pemutakhiran basis data alumni, optimalisasi komunikasi, peningkatan respons</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Kepuasan Pengguna -->
        <div class="sub-criteria-panel" id="c6-kepuasan">
          <div class="lkps-section ledps">
            <h3>⭐ Kepuasan Pengguna Lulusan — Evaluasi</h3>
            <div class="led-card">
              <h4>📊 Hasil Survei (45 responden, 7 aspek)</h4>
              <table class="lkps-table">
                <thead><tr><th>Aspek</th><th>Sangat Baik</th><th>Baik</th><th>Cukup</th><th>Kurang</th></tr></thead>
                <tbody>
                  <tr><td>Teknologi Informasi</td><td class="highlight-data">82,20%</td><td>17,80%</td><td>0,00%</td><td>0,00%</td></tr>
                  <tr><td>Etika</td><td class="highlight-data">80,00%</td><td>20,00%</td><td>0,00%</td><td>0,00%</td></tr>
                  <tr><td>Berkomunikasi</td><td class="highlight-data">77,78%</td><td>22,20%</td><td>0,00%</td><td>0,00%</td></tr>
                  <tr><td>Kerjasama Tim</td><td class="highlight-data">75,60%</td><td>24,40%</td><td>0,00%</td><td>0,00%</td></tr>
                  <tr><td>Keahlian Bidang</td><td class="highlight-data">73,30%</td><td>26,70%</td><td>0,00%</td><td>0,00%</td></tr>
                  <tr><td>Pengembangan Diri</td><td class="highlight-data">73,30%</td><td>26,70%</td><td>0,00%</td><td>0,00%</td></tr>
                  <tr><td>Bahasa Asing</td><td class="highlight-data">71,10%</td><td>17,80%</td><td class="highlight-data">11,10%</td><td>0,00%</td></tr>
                </tbody>
              </table>
            </div>
            <div class="led-card">
              <h4>⚠️ Catatan Kritis: Bahasa Asing</h4>
              <p><strong>11,1% pengguna</strong> memberikan penilaian "Cukup" untuk kemampuan bahasa asing. Ini menjadi area peningkatan paling jelas berdasarkan survei.</p>
              <p><strong>RTL:</strong> Kelas intensif bahasa asing, sertifikasi TOEFL/TOEIC, program imersi, pemanfaatan referensi internasional, presentasi akademik dalam bahasa Inggris.</p>
            </div>
          </div>
        </div>

        <!-- Sub: SWOT C.6 -->
        <div class="sub-criteria-panel" id="c6-swot">
          <div class="lkps-section ledps">
            <h3>📊 SWOT C.6 — Mahasiswa & Luaran</h3>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths</h4>
                <ul>
                  <li>S1. Rasio mhs:DTPS 1:17,18 mendukung pembelajaran</li>
                  <li>S2. IPK 3,46, masa studi 4,06 tahun, PTW 95,025%</li>
                  <li>S3. Prestasi akademik & nonakademik hingga internasional</li>
                  <li>S4. 126 publikasi mahasiswa</li>
                  <li>S5. 19 luaran penelitian/PkM, 16 produk dimanfaatkan masyarakat</li>
                  <li>S6. Tracer study: daya serap lulusan baik</li>
                  <li>S7. 81,96% kesesuaian bidang kerja sedang-tinggi</li>
                  <li>S8. 80,32% bekerja nasional-multinasional</li>
                  <li>S9. Kepuasan pengguna sangat positif (tidak ada "Kurang")</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses</h4>
                <ul>
                  <li>W1. Tren penurunan IPK (3,49→3,45→3,43)</li>
                  <li>W2. Prestasi & rekognisi internasional masih terbatas</li>
                  <li>W3. Internasionalisasi mahasiswa terbatas</li>
                  <li>W4. Publikasi mahasiswa didominasi nasional</li>
                  <li>W5. Luaran didominasi Pencatatan Ciptaan, hilirisasi terbatas</li>
                  <li>W6. Keterlacakan lulusan 76,25% (belum optimal)</li>
                  <li>W7. 11,48% lulusan kesesuaian bidang kerja rendah</li>
                  <li>W8. Bahasa asing perlu penguatan (11,1% Cukup)</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities</h4>
                <ul>
                  <li>O1. Industri telekomunikasi, broadband, multimedia berkembang</li>
                  <li>O2. Jejaring DUDI untuk magang, sertifikasi, rekrutmen</li>
                  <li>O3. Kerja sama PT luar negeri untuk mobilitas mahasiswa</li>
                  <li>O4. Kompetisi, konferensi, jurnal, hibah, program kreativitas</li>
                  <li>O5. Ekosistem inovasi → hilirisasi TA, penelitian, PkM</li>
                  <li>O6. Kebutuhan tenaga profesional bersertifikasi & berkemampuan global</li>
                  <li>O7. Teknologi digital & jejaring alumni → optimalisasi tracer</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats</h4>
                <ul>
                  <li>T1. Perkembangan teknologi cepat → relevansi kompetensi</li>
                  <li>T2. Persaingan lulusan telekomunikasi, informatika, jaringan tinggi</li>
                  <li>T3. Perubahan kebutuhan kompetensi → skill mismatch</li>
                  <li>T4. Persaingan hibah, publikasi, mobilitas, rekognisi internasional</li>
                  <li>T5. Perubahan pasar kerja → waktu tunggu, kesesuaian bidang</li>
                  <li>T6. Tuntutan bahasa asing, sertifikasi, soft skills, teknologi baru</li>
                  <li>T7. Mobilitas alumni → penurunan keterlacakan</li>
                </ul>
              </div>
            </div>
          </div>
        </div>

      </div>

      <!-- ================================================================ -->
      <!-- C.7 SPMI - SUB KRITERIA -->
      <!-- ================================================================ -->
      <div class="ledps-criteria" id="ledps-c7">
        
        <div class="sub-criteria-nav ledps-sub">
          <button class="active" onclick="showSubCriteria('c7', 'unit', this)"> Unit Penjaminan Mutu</button>
          <button onclick="showSubCriteria('c7', 'perangkat', this)">📋 Perangkat SPMI</button>
          <button onclick="showSubCriteria('c7', 'ikt', this)">📊 IKT</button>
          <button onclick="showSubCriteria('c7', 'ppepp', this)">🔄 Siklus PPEPP</button>
          <button onclick="showSubCriteria('c7', 'evaluasi', this)">📈 Evaluasi Kinerja</button>
          <button onclick="showSubCriteria('c7', 'kepuasan', this)">⭐ Kepuasan Stakeholder</button>
          <button onclick="showSubCriteria('c7', 'swot', this)">📊 SWOT C.7</button>
        </div>

        <!-- Sub: Unit Penjaminan Mutu -->
        <div class="sub-criteria-panel active" id="c7-unit">
          <div class="lkps-section ledps">
            <h3>🏢 Unit Penjaminan Mutu</h3>
            <div class="led-card">
              <h4>📜 Struktur & Dasar Legal</h4>
              <ul>
                <li><strong>Tingkat Institusi:</strong> Unit Penjaminan Mutu (UPM) di bawah PPMPP</li>
                <li><strong>Tingkat Jurusan:</strong> Gugus Penjamin Mutu (GPM) sejak 2023</li>
                <li><strong>SK GPM:</strong> SK Direktur No. 147/PL3/JM/2025</li>
                <li><strong>Struktur PPMPP:</strong> SK Direktur No. 602/PL3/OT.00.01/2023</li>
              </ul>
              <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="evidence-link">📂 Bukti: Dokumen SPMI</a>
            </div>
            <div class="led-card">
              <h4>🔍 Independensi Auditor AMI</h4>
              <p>Auditor Mutu Internal ditugaskan secara independen melalui dokumen penugasan yang sah. Auditor tidak mengaudit unitnya sendiri.</p>
            </div>
          </div>
        </div>

        <!-- Sub: Perangkat SPMI -->
        <div class="sub-criteria-panel" id="c7-perangkat">
          <div class="lkps-section ledps">
            <h3>📋 Perangkat SPMI</h3>
            <div class="led-card">
              <h4>📚 Dokumen SPMI (4 dokumen)</h4>
              <table class="lkps-table">
                <thead><tr><th>No</th><th>Jenis Dokumen</th><th>No Dokumen</th><th>Tanggal</th></tr></thead>
                <tbody>
                  <tr><td>1</td><td>Kebijakan SPMI</td><td>KM/PNJ/SPMI/111</td><td>—</td></tr>
                  <tr><td>2</td><td>Pedoman PPEPP</td><td>KM/PNJ/SPMI/212</td><td>18/1/2022</td></tr>
                  <tr><td>3</td><td>Standar Mutu</td><td>SM/PNJ/SPMI/311</td><td>20/1/2022</td></tr>
                  <tr><td>4</td><td>Tata Cara Pendokumentasian</td><td>KM/PNJ/SPMI/215</td><td>20/1/2022</td></tr>
                </tbody>
              </table>
            </div>
            <div class="led-card">
              <h4>📖 Manual Mutu (5 bagian)</h4>
              <ul>
                <li>Manual Penetapan Standar (MM/PNJ/SPMI/211)</li>
                <li>Manual Pelaksanaan/Pemenuhan Standar</li>
                <li>Manual Evaluasi Pelaksanaan Standar</li>
                <li>Manual Pengendalian Standar</li>
                <li>Manual Peningkatan Standar</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📋 Prosedur & Formulir</h4>
              <ul>
                <li><strong>51 SOP</strong> (SOP-01-SM/PNJ/SPMI/311 s.d. SOP-01-SM/PNJ/SPMI/362)</li>
                <li><strong>64 Formulir</strong> (standar isi, proses PBM, kompetensi lulusan, pendidik & tendik, sarpras, pengelolaan, penelitian, PkM, kerja sama)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>🏆 Pengakuan Mutu Eksternal</h4>
              <table class="lkps-table">
                <thead><tr><th>Peringkat</th><th>Jumlah PS</th></tr></thead>
                <tbody>
                  <tr><td>Unggul (LAM TEK)</td><td>1</td></tr>
                  <tr><td>A (BAN-PT)</td><td>1</td></tr>
                  <tr><td>Baik Sekali (LAM TEK)</td><td>2</td></tr>
                  <tr><td>Baik (LAM TEK)</td><td>2</td></tr>
                  <tr><td>B (BAN-PT)</td><td>1</td></tr>
                </tbody>
              </table>
              <p><strong>Audit Eksternal:</strong> Itjen Kemenristekdikti, BPK RI, KAP — Hasil audit 2023: <strong>"Wajar Tanpa Pengecualian"</strong></p>
            </div>
          </div>
        </div>

        <!-- Sub: IKT -->
        <div class="sub-criteria-panel" id="c7-ikt">
          <div class="lkps-section ledps">
            <h3>📊 Indikator Kinerja Tambahan (IKT)</h3>
            <div class="led-card">
              <h4>🎯 4 Unsur IKT</h4>
              <ol>
                <li><strong>Tujuan Strategis Organisasi:</strong> IKT selaras dengan VMTS & Renstra</li>
                <li><strong>Dampak Positif & Terukur:</strong> Parameter keberhasilan kuantitatif & kualitatif</li>
                <li><strong>Daya Saing Internasional:</strong> Output tridharma bersaing di tingkat internasional</li>
                <li><strong>Pengukuran & Analisis:</strong> Melalui siklus PPEPP, dianalisis di RTM</li>
              </ol>
            </div>
            <div class="led-card">
              <h4>📈 Standar Melampaui SN-DIKTI</h4>
              <ul>
                <li>Standar Penerimaan Mahasiswa Baru</li>
                <li>Standar Kemahasiswaan</li>
                <li>Standar Pelaksanaan Wisuda</li>
                <li>Standar Kerja Sama</li>
                <li>Standar Mutu Pengadaan Pegawai</li>
                <li>Standar Mutu Manajemen Karir Pegawai</li>
                <li>Standar Mutu Pemberhentian Pegawai</li>
                <li>Standar Penyusunan Anggaran</li>
                <li>Standar Sistem Informasi</li>
                <li>Standar Visi Misi</li>
                <li>Standar Pelaksanaan MBKM</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: PPEPP -->
        <div class="sub-criteria-panel" id="c7-ppepp">
          <div class="lkps-section ledps">
            <h3>🔄 Siklus PPEPP — Evaluasi</h3>
            <div class="led-card">
              <h4>📋 5 Tahap PPEPP</h4>
              <ul>
                <li><strong>Penetapan:</strong> Standar mutu melalui SK Rektor/Dekan → <em>LKPS 7.a</em></li>
                <li><strong>Pelaksanaan:</strong> Program kerja mengacu standar (LMS, SIAKAD, SIMLitmas)</li>
                <li><strong>Evaluasi:</strong> AMI tahunan, EDOM semesteran, Monev PBM → <em>LKPS 7.b</em></li>
                <li><strong>Pengendalian:</strong> RTM tingkat jurusan untuk tindak lanjut</li>
                <li><strong>Peningkatan:</strong> Revisi standar & strategi berdasarkan hasil evaluasi</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📊 Jenis Evaluasi</h4>
              <table class="lkps-table">
                <thead><tr><th>Jenis</th><th>Bentuk</th><th>Siklus</th></tr></thead>
                <tbody>
                  <tr><td>Formatif</td><td>Monev PBM</td><td>1x/semester</td></tr>
                  <tr><td>Formatif</td><td>Survei kepuasan pengguna layanan</td><td>1x/tahun</td></tr>
                  <tr><td>Sumatif</td><td>Audit Mutu Internal (AMI)</td><td>1x/tahun</td></tr>
                  <tr><td>Sumatif</td><td>Rapat evaluasi jurusan</td><td>1x/semester</td></tr>
                </tbody>
              </table>
            </div>
            <div class="led-card">
              <h4>✅ Bukti Efektivitas</h4>
              <ul>
                <li>Laporan AMI dengan temuan terverifikasi</li>
                <li>Dokumen RTL dari RTM</li>
                <li>Peningkatan capaian IKU/IKT (tren positif)</li>
              </ul>
              <a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank" class="evidence-link">📂 Bukti: Laporan AMI</a>
              <a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank" class="evidence-link">📂 Bukti: Notulensi RTM</a>
              <a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank" class="evidence-link"> Bukti: Dokumen RTL</a>
            </div>
          </div>
        </div>

        <!-- Sub: Evaluasi Kinerja -->
        <div class="sub-criteria-panel" id="c7-evaluasi">
          <div class="lkps-section ledps">
            <h3>📈 Evaluasi Capaian Kinerja</h3>
            <div class="led-card">
              <h4>🔍 Metode Pengukuran</h4>
              <ul>
                <li>AMI oleh auditor SPMI</li>
                <li>Monitoring pembelajaran via sistem akademik & e-learning</li>
                <li>EDOM setiap semester</li>
                <li>Evaluasi hasil pembelajaran</li>
                <li>Rapat evaluasi PS & jurusan</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📊 4 Dimensi Evaluasi</h4>
              <ul>
                <li><strong>Budaya:</strong> Implementasi SPMI, AMI, evaluasi semester, tindak lanjut</li>
                <li><strong>Relevansi:</strong> Evaluasi RPS, pembelajaran, hasil belajar</li>
                <li><strong>Akuntabilitas:</strong> Standar, monitoring, AMI, dokumentasi, tindak lanjut</li>
                <li><strong>Diferensiasi:</strong> Karakter PSBM (vokasi, praktik rekayasa, Broadband Multimedia)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>📢 Penyebarluasan Hasil</h4>
              <ul>
                <li>Monitoring pembelajaran → Forum PS & Jurusan</li>
                <li>EDOM → Umpan balik dosen & pengelola PS</li>
                <li>AMI → Unit yang diaudit & pimpinan</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Kepuasan Stakeholder -->
        <div class="sub-criteria-panel" id="c7-kepuasan">
          <div class="lkps-section ledps">
            <h3>⭐ Kepuasan Stakeholder</h3>
            <div class="led-card">
              <h4>👨‍🏫 Kepuasan Dosen</h4>
              <ul>
                <li><strong>Sistem Informasi:</strong> 85,6% tinggi</li>
                <li><strong>Tata Pamong:</strong> 80,5% tinggi</li>
                <li><strong>Penelitian & PkM:</strong> 78,8% tinggi</li>
                <li><strong>SDM & Sarpras:</strong> 43,2% tinggi (perlu peningkatan)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>👷 Kepuasan Tendik</h4>
              <ul>
                <li><strong>Sistem Informasi:</strong> 62,73% tinggi</li>
                <li><strong>Tata Pamong & Keuangan:</strong> 55,45% tinggi</li>
                <li><strong>Sarpras:</strong> 52,73% tinggi</li>
                <li><strong>SDM:</strong> 39,09% tinggi, 49,09% sedang (perlu peningkatan)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>👨‍ Kepuasan Mahasiswa</h4>
              <ul>
                <li><strong>Pendidikan:</strong> 76,5% tinggi</li>
                <li><strong>Tata Pamong:</strong> 73,2% tinggi</li>
                <li><strong>Keuangan:</strong> 68,8% tinggi</li>
                <li><strong>Kemahasiswaan:</strong> 40,4% sedang (perlu peningkatan)</li>
                <li><strong>Sarpras:</strong> 38,6% sedang (perlu peningkatan)</li>
              </ul>
            </div>
            <div class="led-card">
              <h4>⭐ Kepuasan Pengguna Lulusan</h4>
              <p>Telah dibahas di C.6 — 7 aspek, 45 responden, tidak ada penilaian "Kurang".</p>
            </div>
          </div>
        </div>

        <!-- Sub: SWOT C.7 -->
        <div class="sub-criteria-panel" id="c7-swot">
          <div class="lkps-section ledps">
            <h3>📊 SWOT C.7 — SPMI</h3>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths</h4>
                <ul>
                  <li>S1. Struktur & dasar legal pelaksana penjaminan mutu</li>
                  <li>S2. Perangkat SPMI lengkap (Kebijakan, Manual, Standar, Prosedur, Formulir)</li>
                  <li>S3. Siklus PPEPP dilaksanakan (AMI, RTM, tindak lanjut)</li>
                  <li>S4. Dokumentasi kegiatan akademik didukung sistem informasi</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses</h4>
                <ul>
                  <li>W1. Kapasitas personel GPM belum merata, jumlah terbatas</li>
                  <li>W2. Integrasi basis data & dokumen mutu belum optimal</li>
                  <li>W3. Penyelesaian tindak lanjut AMI kadang melewati batas waktu</li>
                  <li>W4. Penyesuaian standar terhadap regulasi belum selalu cepat</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities</h4>
                <ul>
                  <li>O1. Pengembangan sistem informasi → integrasi basis data SPMI</li>
                  <li>O2. Pelatihan & sertifikasi penjaminan mutu</li>
                  <li>O3. Sertifikasi & akreditasi internasional</li>
                  <li>O4. Data AMI, RTM, evaluasi → dasar peningkatan mutu</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats</h4>
                <ul>
                  <li>T1. Perubahan regulasi pendidikan tinggi cepat</li>
                  <li>T2. Peningkatan tuntutan standar mutu & akreditasi</li>
                  <li>T3. Ketergantungan sistem informasi & koneksi internet</li>
                  <li>T4. Beban kerja personel beragam → hambatan ketepatan waktu</li>
                </ul>
              </div>
            </div>
          </div>
        </div>

      </div>

      <!-- ================================================================ -->
      <!-- BAB III - SUB KRITERIA -->
      <!-- ================================================================ -->
      <div class="ledps-criteria" id="ledps-bab3">
        
        <div class="sub-criteria-nav ledps-sub">
          <button class="active" onclick="showSubCriteria('bab3', 'swot', this)">📊 SWOT</button>
          <button onclick="showSubCriteria('bab3', 'tujuan', this)"> Tujuan Strategis</button>
          <button onclick="showSubCriteria('bab3', 'program', this)">📘 Program Pengembangan</button>
          <button onclick="showSubCriteria('bab3', 'monitoring', this)">🔄 Monitoring</button>
        </div>

        <!-- Sub: SWOT -->
        <div class="sub-criteria-panel active" id="bab3-swot">
          <div class="lkps-section ledps">
            <h3>📊 Analisis SWOT Komprehensif</h3>
            <div class="swot-grid">
              <div class="swot-card strength">
                <h4>💪 Strengths (9 Kekuatan)</h4>
                <ul>
                  <li>S1. VMTS PNJ–JTE–PSBM linear & diterjemahkan dalam Renstra, kurikulum</li>
                  <li>S2. Kekhasan Broadband Multimedia terintegrasi dalam kurikulum</li>
                  <li>S3. Evaluasi kurikulum melibatkan dosen, alumni, industri, pakar</li>
                  <li>S4. 65 kerja sama tridharma (41 pendidikan, 17 penelitian, 7 PkM)</li>
                  <li>S5. 90,91% DTPS Lektor+, 100% sertifikasi, BKD 14,77 SKS</li>
                  <li>S6. 45 penelitian & 14 PkM relevan dengan telekomunikasi & digital</li>
                  <li>S7. Rasio 1:17,18, IPK 3,46, masa studi 4,06 tahun</li>
                  <li>S8. Produktivitas mahasiswa: publikasi, luaran, produk dimanfaatkan</li>
                  <li>S9. Tata pamong didukung regulasi jelas, kepemimpinan partisipatif, SPMI</li>
                </ul>
              </div>
              <div class="swot-card weakness">
                <h4>⚠️ Weaknesses (9 Kelemahan)</h4>
                <ul>
                  <li>W1. Internasionalisasi belum sekuat capaian nasional</li>
                  <li>W2. Dokumentasi CPL/CPMK & closed-loop improvement perlu diperkuat</li>
                  <li>W3. Pendanaan penelitian & PkM didominasi internal</li>
                  <li>W4. Keterlibatan mahasiswa dalam penelitian 26,67%</li>
                  <li>W5. Belum ada Guru Besar, publikasi/rekognisi internasional perlu ditingkatkan</li>
                  <li>W6. Pemutakhiran fasilitas lab & kompetensi SDM perlu berkelanjutan</li>
                  <li>W7. Prestasi & aktivitas internasional mahasiswa terbatas</li>
                  <li>W8. Beberapa layanan (SDM, kemahasiswaan, sarpras) perlu peningkatan</li>
                  <li>W9. Evaluasi manfaat & kepuasan mitra kerja sama belum terstandar</li>
                </ul>
              </div>
              <div class="swot-card opportunity">
                <h4>🚀 Opportunities (6 Peluang)</h4>
                <ul>
                  <li>O1. Transformasi digital & pembangunan infrastruktur broadband</li>
                  <li>O2. Perkembangan 5G/6G, IoT, AI, cloud, Big Data, multimedia</li>
                  <li>O3. Jejaring DUDI, asosiasi, alumni, PT untuk pembelajaran, sertifikasi, penelitian, PkM</li>
                  <li>O4. Peluang pendanaan eksternal penelitian/PkM</li>
                  <li>O5. Sertifikasi profesi, standar industri, jejaring akademik/profesional</li>
                  <li>O6. Jejaring alumni & pengguna untuk magang, tracer, rekrutmen, kurikulum</li>
                </ul>
              </div>
              <div class="swot-card threat">
                <h4>⚡ Threats (6 Ancaman)</h4>
                <ul>
                  <li>T1. Perubahan teknologi telekomunikasi & digital sangat cepat</li>
                  <li>T2. Persaingan dengan PS telekomunikasi, elektro, informatika/TI, komputer, multimedia</li>
                  <li>T3. Perubahan kebutuhan kompetensi DUDI → risiko skill mismatch</li>
                  <li>T4. Persaingan pendanaan eksternal, publikasi bereputasi</li>
                  <li>T5. Pasar kerja meningkatkan tuntutan sertifikasi, bahasa asing, standar internasional</li>
                  <li>T6. Perkembangan teknologi butuh investasi berkelanjutan</li>
                </ul>
              </div>
            </div>
          </div>
        </div>

        <!-- Sub: Tujuan Strategis -->
        <div class="sub-criteria-panel" id="bab3-tujuan">
          <div class="lkps-section ledps">
            <h3>🎯 Tujuan Strategis Pengembangan</h3>
            
            <h4 style="color:#2e7d32; margin-top:16px;">📌 Jangka Pendek (1-3 tahun)</h4>
            <div class="summary-grid">
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">Tujuan 1</div>
                <div class="sc-value" style="font-size:0.85rem;">Mutu Kurikulum & Pembelajaran</div>
                <div class="sc-desc">Pemutakhiran pembelajaran sesuai teknologi & DUDI, penguatan pengukuran CPL</div>
              </div>
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">Tujuan 2</div>
                <div class="sc-value" style="font-size:0.85rem;">Kompetensi & Kinerja SDM</div>
                <div class="sc-desc">Pengembangan JAFA, sertifikasi, pelatihan teknologi, publikasi, rekognisi</div>
              </div>
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">Tujuan 3</div>
                <div class="sc-value" style="font-size:0.85rem;">Kualitas & Dampak Penelitian/PkM</div>
                <div class="sc-desc">Keterlibatan mahasiswa, integrasi dengan pembelajaran/TA, pendanaan eksternal</div>
              </div>
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">Tujuan 4</div>
                <div class="sc-value" style="font-size:0.85rem;">Sarpras & Layanan Pendukung</div>
                <div class="sc-desc">Pemutakhiran & pemeliharaan lab, penguatan layanan TIK</div>
              </div>
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">Tujuan 5</div>
                <div class="sc-value" style="font-size:0.85rem;">Prestasi & Daya Saing Mahasiswa/Lulusan</div>
                <div class="sc-desc">Sertifikasi, pembinaan prestasi, bahasa asing, pengalaman nasional/internasional</div>
              </div>
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">Tujuan 6</div>
                <div class="sc-value" style="font-size:0.85rem;">Efektivitas & Dampak Kerja Sama</div>
                <div class="sc-desc">Optimalisasi jejaring DUDI, PT, alumni untuk pendidikan, penelitian, PkM</div>
              </div>
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">Tujuan 7</div>
                <div class="sc-value" style="font-size:0.85rem;">Tata Kelola & Penjaminan Mutu</div>
                <div class="sc-desc">Konsistensi PPEPP, tindak lanjut evaluasi, pemanfaatan data kinerja</div>
              </div>
            </div>

            <h4 style="color:#2e7d32; margin-top:24px;">🎯 Jangka Menengah (4-5 tahun)</h4>
            <div class="led-card">
              <ul>
                <li>Memperkuat posisi PSBM sebagai PS vokasi unggul di bidang Broadband Multimedia</li>
                <li>Meningkatkan rekognisi SDM pada tingkat nasional & internasional</li>
                <li>Meningkatkan kualitas, kolaborasi, kebermanfaatan penelitian & PkM</li>
                <li>Mengembangkan sarpras pembelajaran & lab yang adaptif terhadap teknologi</li>
                <li>Meningkatkan internasionalisasi & daya saing mahasiswa/lulusan</li>
                <li>Memperluas kerja sama nasional & internasional yang berdampak</li>
                <li>Memperkuat budaya mutu berkelanjutan melalui PPEPP, tracer, survei, evaluasi kinerja</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Sub: Program Pengembangan -->
        <div class="sub-criteria-panel" id="bab3-program">
          <div class="lkps-section ledps">
            <h3>📘 7 Program Pengembangan Berkelanjutan</h3>
            <div class="table-responsive">
              <table class="lkps-table">
                <thead><tr><th>No</th><th>Program</th><th>Kegiatan Utama</th><th>Indikator Keberhasilan</th><th>Sumber Daya</th></tr></thead>
                <tbody>
                  <tr>
                    <td>1</td>
                    <td><strong>Penguatan Kurikulum & Pembelajaran</strong></td>
                    <td>Penguatan pengukuran CPL; pemutakhiran RPS & pembelajaran sesuai teknologi & DUDI; peningkatan pembelajaran berbasis praktik/proyek</td>
                    <td>Pengukuran CPL terdokumentasi & ditindaklanjuti; kurikulum relevan dengan DUDI</td>
                    <td>PS-BM, DTPS, GPM, alumni, pengguna, DUDI</td>
                  </tr>
                  <tr>
                    <td>2</td>
                    <td><strong>Pengembangan SDM</strong></td>
                    <td>Pengembangan JAFA; sertifikasi; pelatihan teknologi; peningkatan publikasi, kolaborasi, rekognisi</td>
                    <td>Peningkatan JAFA, kompetensi, publikasi, kolaborasi, rekognisi DTPS</td>
                    <td>PNJ, JTE, PS-BM, DTPS, tendik, mitra</td>
                  </tr>
                  <tr>
                    <td>3</td>
                    <td><strong>Penguatan Penelitian & PkM</strong></td>
                    <td>Pengajuan hibah eksternal; kolaborasi; peningkatan keterlibatan mahasiswa; publikasi/HKI; pemanfaatan hasil</td>
                    <td>Pendanaan eksternal & keterlibatan mahasiswa meningkat; peningkatan luaran & pemanfaatan</td>
                    <td>P3M, JTE, PS-BM, DTPS, mahasiswa, DUDI/PT mitra</td>
                  </tr>
                  <tr>
                    <td>4</td>
                    <td><strong>Pengembangan Sarana-Prasarana</strong></td>
                    <td>Pemutakhiran & pemeliharaan laboratorium serta fasilitas TIK sesuai kebutuhan pembelajaran</td>
                    <td>Kecukupan, keandalan, pemanfaatan fasilitas meningkat</td>
                    <td>PNJ, JTE, PS-BM, laboratorium, mitra</td>
                  </tr>
                  <tr>
                    <td>5</td>
                    <td><strong>Peningkatan Daya Saing Mahasiswa & Lulusan</strong></td>
                    <td>Pembinaan prestasi; sertifikasi; penguatan bahasa asing; magang & kegiatan nasional/internasional</td>
                    <td>Prestasi, sertifikasi, aktivitas internasional meningkat; daya serap & relevansi lulusan terjaga</td>
                    <td>PS-BM, mahasiswa, alumni, DUDI/PT mitra</td>
                  </tr>
                  <tr>
                    <td>6</td>
                    <td><strong>Penguatan Kerja Sama Berdampak</strong></td>
                    <td>Optimalisasi kerja sama untuk pembelajaran, magang, sertifikasi, penelitian/PkM, peningkatan kompetensi</td>
                    <td>Implementasi & manfaat kerja sama meningkat; kepuasan mitra terdokumentasi</td>
                    <td>JTE, PS-BM, DUDI, PT, asosiasi, alumni</td>
                  </tr>
                  <tr>
                    <td>7</td>
                    <td><strong>Penguatan Tata Kelola & Penjaminan Mutu</strong></td>
                    <td>Penguatan PPEPP, AMI, RTM, tindak lanjut evaluasi, pemanfaatan data kinerja</td>
                    <td>Tindak lanjut terdokumentasi; hasil evaluasi digunakan untuk perbaikan & peningkatan standar</td>
                    <td>JTE, PS-BM, GPM, PPMPP, unit terkait</td>
                  </tr>
                </tbody>
              </table>
            </div>
            <div class="led-card">
              <h4>⚠️ Manajemen Risiko</h4>
              <p><strong>Risiko yang diidentifikasi:</strong> Keterbatasan sumber daya, perubahan teknologi cepat, keberhasilan memperoleh pendanaan eksternal, konsistensi implementasi pembelajaran, keberlanjutan kerja sama.</p>
              <p><strong>Mitigasi:</strong> Penetapan prioritas, optimalisasi sumber daya & dukungan mitra, penguatan kompetensi SDM, monitoring & evaluasi berkala.</p>
            </div>
          </div>
        </div>

        <!-- Sub: Monitoring -->
        <div class="sub-criteria-panel" id="bab3-monitoring">
          <div class="lkps-section ledps">
            <h3>🔄 Monitoring & PPEPP Program</h3>
            <div class="summary-grid">
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">🔍 AMI</div>
                <div class="sc-value" style="font-size:1rem;">Audit Mutu Internal</div>
                <div class="sc-desc">Audit internal tahunan terhadap 7 kriteria</div>
              </div>
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">📝 RTM</div>
                <div class="sc-value" style="font-size:1rem;">Rapat Tinjauan Manajemen</div>
                <div class="sc-desc">Tinjauan hasil AMI oleh pimpinan</div>
              </div>
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label">📋 RTL</div>
                <div class="sc-value" style="font-size:1rem;">Rencana Tindak Lanjut</div>
                <div class="sc-desc">Tindak lanjut temuan AMI terdokumentasi</div>
              </div>
              <div class="summary-card" style="border-left-color: #2e7d32;">
                <div class="sc-label"> Evaluasi Berkala</div>
                <div class="sc-value" style="font-size:1rem;">Tracer & Survei</div>
                <div class="sc-desc">Tracer study, survei kepuasan, evaluasi kinerja</div>
              </div>
            </div>
            <div class="led-card">
              <h4>🔗 Keberlanjutan Program</h4>
              <p>Program tidak dibentuk untuk AL, tetapi diintegrasikan dengan:</p>
              <ul>
                <li><strong>Perencanaan UPPS/PS:</strong> Renstra, Renop, RKAT</li>
                <li><strong>Penjaminan Mutu:</strong> Siklus PPEPP, AMI, RTM</li>
                <li><strong>Pengembangan Jangka Menengah:</strong> Target 2026-2028</li>
              </ul>
              <a href="#" class="evidence-link">📂 Bukti: Renstra + Renop + RKAT</a>
            </div>
            <div class="led-card">
              <h4>🎯 Indikator Outcome</h4>
              <p>Keberhasilan program diukur melalui perubahan indikator hasil:</p>
              <ul>
                <li>Capaian CPL terukur & ditindaklanjuti</li>
                <li>Pendanaan eksternal meningkat</li>
                <li>Keterlibatan mahasiswa dalam penelitian meningkat</li>
                <li>Luaran, rekognisi, kerja sama berdampak meningkat</li>
                <li>Luaran lulusan (prestasi, publikasi, produk) meningkat</li>
              </ul>
            </div>
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
  
  // Reset sub-criteria ke yang pertama
  const firstSubBtn = document.querySelector('#ledps-' + id + ' .sub-criteria-nav button');
  if (firstSubBtn) {
    const firstSubId = firstSubBtn.getAttribute('onclick').match(/'([^']+)'/)[1].split(',')[1].trim().replace(/'/g, '');
    showSubCriteria(id, firstSubId, firstSubBtn);
  }
}

// ===== SUB-SUB-NAV (Sub-Kriteria dalam setiap kriteria) =====
function showSubCriteria(kriteria, subId, btn) {
  const panelId = kriteria + '-' + subId;
  const panel = document.getElementById(panelId);
  if (!panel) return;
  
  // Sembunyikan semua sub-panel dalam kriteria ini
  const parentPanel = document.getElementById('ledps-' + kriteria);
  parentPanel.querySelectorAll('.sub-criteria-panel').forEach(p => p.classList.remove('active'));
  
  // Tampilkan sub-panel yang dipilih
  panel.classList.add('active');
  
  // Update tombol aktif
  const nav = btn.parentElement;
  nav.querySelectorAll('button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  
  window.scrollTo({ top: panel.offsetTop - 100, behavior: 'smooth' });
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  document.querySelectorAll('.lkps-table-panel').forEach((p, i) => {
    p.classList.toggle('active', i === 0);
  });
  document.querySelectorAll('.ledps-criteria').forEach((p, i) => {
    p.classList.toggle('active', i === 0);
  });
  document.querySelectorAll('.sub-criteria-panel').forEach((p, i) => {
    // Aktifkan hanya sub-panel pertama di setiap kriteria
    const parent = p.parentElement;
    const firstSub = parent.querySelector('.sub-criteria-panel');
    p.classList.toggle('active', p === firstSub);
  });
});
</script>

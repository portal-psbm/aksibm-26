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

.criteria-nav { display: flex; gap: 4px; margin-bottom: 16px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
.criteria-nav button { padding: 8px 14px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.82rem; }
.criteria-nav button:hover { color: #0d47a1; background: #f8fafc; }
.criteria-nav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }

.criteria-panel { display: none; animation: fadeIn 0.3s ease; }
.criteria-panel.active { display: block; }

.lkps-section { margin-bottom: 24px; }
.lkps-section h3 { color: #0d47a1; border-left: 4px solid #0d47a1; padding-left: 12px; margin-bottom: 12px; font-size: 1.1rem; }
.lkps-section.sesi2 h3 { color: #2e7d32; border-left-color: #2e7d32; }

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
.info-box strong { color: #0a3a8a; }

.ev-open-btn { padding: 6px 14px; border-radius: 6px; border: none; background: #0d47a1; color: white; font-size: 0.78rem; font-weight: 600; cursor: pointer; transition: all 0.2s; display: inline-flex; align-items: center; gap: 4px; text-decoration: none; margin-right: 6px; margin-bottom: 6px; }
.ev-open-btn:hover { background: #1565c0; transform: translateY(-1px); }
.ev-open-btn.secondary { background: white; color: #0d47a1; border: 1px solid #0d47a1; }
.ev-open-btn.secondary:hover { background: #e3f2fd; }

@media (max-width: 767px) {
.ev-shelf { gap: 4px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
.ev-shelf::-webkit-scrollbar { display: none; }
.ev-tab { min-width: 110px; flex: 0 0 auto; font-size: 0.8rem; }
.ev-content { padding: 20px; }
.summary-grid { grid-template-columns: 1fr 1fr; }
.session-info { flex-direction: column; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('sesi1', this)">📊<br>SESI 1<br>LKPS</div>
    <div class="ev-tab sesi2" onclick="showEvPanel('sesi2', this)">🔄<br>SESI 2<br>Penjaminan Mutu</div>
  </div>

  <div class="ev-content">

    <!-- ========== SESI 1: LKPS ========== -->
    <div class="ev-panel active" id="panel-sesi1">
      <div class="session-header sesi1">
        <span class="tag">DATA KUANTITATIF + LINK BUKTI</span>
        <h2>📊 SESI 1 — LAPORAN KINERJA PROGRAM STUDI (LKPS)</h2>
        <div class="subtitle">Tabel 1 s.d. 7 — Data angka 3 tahun terakhir dengan link bukti Google Drive</div>
        <div class="session-info">
          <div class="info-item"><strong>50+</strong> Tabel Evidence</div>
          <div class="info-item"><strong>C.1–C.7</strong> Semua Kriteria</div>
          <div class="info-item"><strong>3 Tahun</strong> Periode Data</div>
        </div>
      </div>

      <div class="info-box">
        <strong>ℹ️ Informasi:</strong> Halaman ini menampilkan seluruh tabel LKPS PSBM dengan <strong>link bukti Google Drive</strong> yang sudah terintegrasi. Klik tombol "📂 Buka" untuk mengakses dokumen asli.
      </div>

      <!-- Sub-nav Tabel -->
      <div class="criteria-nav">
        <button class="active" onclick="showLkpsTable('t1', this)">Tabel 1<br><small>VMTS</small></button>
        <button onclick="showLkpsTable('t2', this)">Tabel 2<br><small>Kerja Sama & Dana</small></button>
        <button onclick="showLkpsTable('t3', this)">Tabel 3<br><small>Kurikulum & Tridharma</small></button>
        <button onclick="showLkpsTable('t4', this)">Tabel 4<br><small>SDM & Luaran</small></button>
        <button onclick="showLkpsTable('t5', this)">Tabel 5<br><small>Sarpras & K3L</small></button>
        <button onclick="showLkpsTable('t6', this)">Tabel 6<br><small>Mahasiswa & Luaran</small></button>
        <button onclick="showLkpsTable('t7', this)">Tabel 7<br><small>SPMI</small></button>
      </div>

      <!-- ===== TABEL 1: VMTS ===== -->
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

      <!-- ===== TABEL 2: KERJA SAMA & DANA ===== -->
      <div class="lkps-table-panel" id="lkps-t2">
        <div class="lkps-section">
          <h3>🤝 Tabel 2a1: Kerja Sama Pendidikan (42)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">5</div></div>
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">37</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">42</div></div>
          </div>
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder Kerja Sama Pendidikan</a></div>
        </div>
        <div class="lkps-section">
          <h3>🔬 Tabel 2a2: Kerja Sama Penelitian (17)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">16</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">17</div></div>
          </div>
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder Kerja Sama Penelitian</a></div>
        </div>
        <div class="lkps-section">
          <h3>🤝 Tabel 2a3: Kerja Sama PkM (7)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">1</div></div>
            <div class="summary-card"><div class="sc-label">Lokal/Wilayah</div><div class="sc-value">6</div></div>
            <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">7</div></div>
          </div>
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder Kerja Sama PkM</a></div>
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
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder Keuangan</a></div>
        </div>
      </div>

      <!-- ===== TABEL 3: KURIKULUM & TRIDHARMA ===== -->
      <div class="lkps-table-panel" id="lkps-t3">
        <div class="lkps-section">
          <h3>📘 Tabel 3a1: Kurikulum (53 MK, 150 SKS)</h3>
          <div class="summary-grid">
            <div class="summary-card"><div class="sc-label">Total MK</div><div class="sc-value">53</div></div>
            <div class="summary-card"><div class="sc-label">Total SKS</div><div class="sc-value">150</div></div>
            <div class="summary-card"><div class="sc-label">SKS Praktik</div><div class="sc-value">80 (53,33%)</div></div>
            <div class="summary-card"><div class="sc-label">SKS Kuliah</div><div class="sc-value">68</div></div>
          </div>
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder Kurikulum</a></div>
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
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder Penelitian</a></div>
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
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder PkM</a></div>
        </div>
      </div>

      <!-- ===== TABEL 4: SDM & LUARAN ===== -->
      <div class="lkps-table-panel" id="lkps-t4">
        <div class="lkps-section">
          <h3>👨🏫 Tabel 4a: Profil DTPS (11 Dosen)</h3>
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
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder Publikasi</a></div>
        </div>
        <div class="lkps-section">
          <h3>📦 Tabel 4g: Produk/Jasa DTPS Diadopsi (13)</h3>
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>No</th><th>Nama DTPS</th><th>Nama Produk/Jasa</th><th>Link Bukti</th></tr></thead>
              <tbody>
                <tr><td>1</td><td>Viving Frendiana</td><td>Web Sekolah & Sistem Pemantauan KBM</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>2</td><td>Viving Frendiana</td><td>Website Desa Wisata Kampung Setaman</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1z9iUaWIHcKZnNlxXHH3rYC7PbNS_q_4y?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>3</td><td>Viving Frendiana</td><td>Modul Pelatihan Kompetensi Digital Beji Timur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1UhrW8jTpDyjj1ivYWuMzq6y1YRs6NmWs?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>4</td><td>Asri Wulandari</td><td>Aplikasi Bank Sampah Beji Timur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/105r2TRtetj-Nt9ULWgWxxnsW5f_mOgPK?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>5</td><td>Zulhelman</td><td>Sistem Informasi OJT Kemensos RI</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1Q9KQyaZKFr9P35UYPn25LLK2N4YvV3wH?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>6</td><td>Mohamad Fathurahman</td><td>Smart Aquaculture LoRa BBI Ciganjur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1-BrkUP0EVaN4J3rrFYyBJtyBNRLzRwnX?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>7</td><td>Viving Frendiana</td><td>Sistem Keamanan IoT Beji Timur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/167sSDvTK5Q9depemXao-pcVs0sHJbqPn?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>8</td><td>Asri Wulandari</td><td>Sistem Informasi PMI Malaysia</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/15vgOxUMBX8FWW6uIJUxLyiDL39Q2Xp6Q?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>9</td><td>Nana Sutarna</td><td>Lampu Perangkap Serangga Tenaga Surya</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1-qDKCxeu05GU8vGrT-BqgAWHU4WxenpF?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>10</td><td>Dr. Isdawimah</td><td>Penerangan Otomatis & CCTV Kebun Polisekar</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1nMMar36UhwXaM0W9uD45jN7bRSjkomkO?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>11</td><td>Nana Sutarna</td><td>Trainer Kit PLC-SCADA SMK</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1R_t0aznaZVQY9rRDc-yu055gL5r7WOIa?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>12</td><td>Toto Supriyanto</td><td>Alat Pengolah Air Kelompok Tani Mina Lestari</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1B60q7h1b9gxz9UUxeLUfT9pRon9es17t?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>13</td><td>Toto Supriyanto</td><td>Training Kit IoT Limbah Cair SMK Citra Negara</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1YIxIzBmK8ndVgSV7mblSd5Mffl9DdUVx?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>

      <!-- ===== TABEL 5: SARPRAS & K3L ===== -->
      <div class="lkps-table-panel" id="lkps-t5">
        <div class="lkps-section">
          <h3>💰 Tabel 5a: Prasarana & Peralatan Utama</h3>
          <div class="info-box"><strong>📌 Ringkasan:</strong> 16 prasarana utama (13 lab/ruang + 3 layanan nonakademik). Seluruhnya terawat, dimiliki sendiri.</div>
          <div class="info-box"><strong> Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn"> Buka Folder Sarpras</a></div>
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
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn"> Buka Folder K3L</a></div>
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

      <!-- ===== TABEL 6: MAHASISWA & LUARAN ===== -->
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
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder Prestasi</a></div>
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
          <div class="table-responsive">
            <table class="lkps-table">
              <thead><tr><th>No</th><th>Nama Mahasiswa</th><th>Produk/Jasa</th><th>Link Bukti</th></tr></thead>
              <tbody>
                <tr><td>1</td><td>Algifri Prayudha dkk</td><td>Web Sekolah & Sistem Pemantauan KBM</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1gj3fyC_mO2c6pDTNRzhnlPcIE4_pKBYS?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>2</td><td>Muhammad Zaki Raya dkk</td><td>Website Desa Wisata Kampung Setaman</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/10Uedbfz4neHCLzH0gVGHO46a18iBY_Sn?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>3</td><td>Adrian Eka Ramadhani dkk</td><td>Pelatihan Kompetensi Digital Beji Timur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1_bRTrD7Biee4s4TWA7hixSnR6tAUoEs6?usp=sharing" target="_blank"> Buka</a></td></tr>
                <tr><td>4</td><td>Bemi Raihan R dkk</td><td>Aplikasi Bank Sampah "Bersih Plus"</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kOYXp1Zto8t7KmGOKmEyXLlYZgm0986E?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>5</td><td>Nabilla Farassaskya Zanna</td><td>Sistem Informasi OJT Kemensos RI</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1RtCF0v8ZWTKRa554t-tfHOazMMd1bJ-3?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>6</td><td>Ilham Satria Lubis dkk</td><td>Smart Aquaculture LoRa BBI Ciganjur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1sbQtwzrJmOYN8MMsVykxXJMIsNnvWPE4?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>7</td><td>Annisa Octaviani dkk</td><td>Sistem Keamanan IoT Beji Timur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1jOUQDJJjgd0QhcgX3RgIchbhu01FsJLf?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>8</td><td>Farhan Yuswa Bianto</td><td>Sistem Informasi PMI Malaysia</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1J7Mgq_AIQYyJtKua0u6g3ZuVFpMV1H22?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>9</td><td>Muhammad Djapar</td><td>Website Admin Chatbot Kejaksaan Agung</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1znsjt7VPRsWNueWmNr3LXIpes6v8OdPW?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>10</td><td>Daniel Bastian Muhammad</td><td>Monitoring Jaringan & Automasi Router</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1Tmf7vbxX6Gfj8PhHIPZMPJJRRdqwPVDl?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>11</td><td>Fransisca Liany Zahara</td><td>Antena Mikrostrip Array Dual Band</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1lol99_4PBBxleQ-4aMl6Gq_ek6zsfwrI?usp=sharing" target="_blank"> Buka</a></td></tr>
                <tr><td>12</td><td>Salsya Nur'Alfienda</td><td>Website Administrasi Bank Sampah</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1My3a8RALVQHqucIVGpKiPpD2Vx0li5X0?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>13</td><td>Dhaniya Prameswari</td><td>Antena Quasi Yagi Peredam Wi-Fi</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kGTnCs1DYVna53dUfmn_YcYFJS34OxFR?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>14</td><td>Juan Hafidz Segara</td><td>Monitoring Hidroponik IoT Tenaga Surya</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1GQBHpFVUq9rUmo_Ns-58c5D0NwPZShqG?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>15</td><td>Muhammad Hakim Ramadhan</td><td>Pemantau Suhu Mesin Roasting + Telegram</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1XLIlRTGU5Uv1_YxJoinC7tsF92ilxLd9?usp=sharing" target="_blank">📂 Buka</a></td></tr>
                <tr><td>16</td><td>Andika Yulyan Chandra</td><td>Automasi Backup VM & Konfigurasi Jaringan ISP</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/114zDOiBkoPpkiyszmO_PzwQX-bLdQtcI?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              </tbody>
            </table>
          </div>
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
          <div class="info-box"><strong> Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Buka Folder Tracer Study</a></div>
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
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn"> Buka Folder Survei Kepuasan</a></div>
        </div>
      </div>

      <!-- ===== TABEL 7: SPMI ===== -->
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
          <div class="info-box"><strong>📂 Link Bukti:</strong> <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="ev-open-btn">📂 Buka Folder Dokumen SPMI</a></div>
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
          <div class="info-box"><strong>✅ Siklus PPEPP Lengkap:</strong> Semua 5 tahap terdokumentasi dengan link Google Drive aktif.</div>
        </div>
      </div>

    </div>

    <!-- ========== SESI 2: PENJAMINAN MUTU ========== -->
    <div class="ev-panel" id="panel-sesi2">
      <div class="session-header sesi2">
        <span class="tag">ANALISIS KUALITATIF + BAB III</span>
        <h2>🔄 SESI 2 — PENJAMINAN MUTU & LEDPS</h2>
        <div class="subtitle">C.1 s.d. C.7 (Analisis Naratif) + BAB III (SWOT & Program Pengembangan)</div>
        <div class="session-info">
          <div class="info-item"><strong>7</strong> Kriteria</div>
          <div class="info-item"><strong>61</strong> Indikator</div>
          <div class="info-item"><strong>SWOT</strong> + Program</div>
        </div>
      </div>

      <div class="info-box">
        <strong>ℹ️ Informasi:</strong> Halaman ini berisi analisis kualitatif per kriteria (LEDPS) dan BAB III (SWOT, Tujuan Strategis, Program Pengembangan).
      </div>

      <!-- Sub-nav Kriteria + BAB III -->
      <div class="criteria-nav">
        <button class="active" onclick="showLedpsCriteria('c1', this)">C.1 VMTS</button>
        <button onclick="showLedpsCriteria('c2', this)">C.2 Tata Kelola</button>
        <button onclick="showLedpsCriteria('c3', this)">C.3 Diklitpmas</button>
        <button onclick="showLedpsCriteria('c4', this)">C.4 SDM</button>
        <button onclick="showLedpsCriteria('c5', this)">C.5 Sarpras</button>
        <button onclick="showLedpsCriteria('c6', this)">C.6 Luaran</button>
        <button onclick="showLedpsCriteria('c7', this)">C.7 SPMI</button>
        <button onclick="showLedpsCriteria('bab3', this)" style="background: linear-gradient(135deg, #fff3e0 0%, #ffe0b2 100%); color: #e65100; border-radius: 6px; border: 1px solid #ffcc80;"> BAB III</button>
      </div>

      <!-- ===== C.1 VMTS ===== -->
      <div class="ledps-criteria active" id="ledps-c1">
        <div class="lkps-section">
          <h3>📑 C.1 — Kekhasan VMTS & Pencapaian</h3>
          <div class="info-box">
            <strong>📂 Link Bukti:</strong>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 VMTS PT</a>
            <a href="https://drive.google.com/drive/folders/1JiRWv_v_-pbrFTMl74JwQzJ1ZNnCpcOt" target="_blank" class="ev-open-btn">📂 VMTS UPPS</a>
            <a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf" target="_blank" class="ev-open-btn">📂 Visi Keilmuan PS</a>
          </div>
          <p><strong>Visi Keilmuan PSBM:</strong> "Menjadi Program Studi Unggul Bertaraf Internasional di Bidang Broadband Multimedia untuk Mendukung Daya Saing Bangsa"</p>
          <p><strong>Kekhasan:</strong> Integrasi teknologi telekomunikasi broadband, jaringan komputer, komputasi, dan multimedia dengan karakter pendidikan vokasi berbasis praktik, proyek, magang industri, dan sertifikasi kompetensi.</p>
        </div>
      </div>

      <!-- ===== C.2 TATA KELOLA ===== -->
      <div class="ledps-criteria" id="ledps-c2">
        <div class="lkps-section">
          <h3>🏛️ C.2 — Tata Pamong, Tata Kelola, Kerja Sama, Keuangan</h3>
          <div class="info-box">
            <strong>📂 Link Bukti:</strong>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 MoU & IA Kerja Sama</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Dokumen Keuangan</a>
          </div>
          <p><strong>Tata Pamong:</strong> Mengacu pada Statuta PNJ No. 35 Tahun 2018 dan OTK PNJ No. 60 Tahun 2022.</p>
          <p><strong>Kerja Sama:</strong> 66 kerja sama tridharma (42 pendidikan, 17 penelitian, 7 PkM).</p>
          <p><strong>Keuangan:</strong> Total anggaran rata-rata Rp 27,24 M/tahun (UPPS), Rp 4,08 M/tahun (PS).</p>
        </div>
      </div>

      <!-- ===== C.3 DIKLITPMAS ===== -->
      <div class="ledps-criteria" id="ledps-c3">
        <div class="lkps-section">
          <h3>📘 C.3 — Relevansi Pendidikan, Penelitian, dan PkM</h3>
          <div class="info-box">
            <strong>📂 Link Bukti:</strong>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Kurikulum & RPS</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Penelitian</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 PkM</a>
          </div>
          <p><strong>Kurikulum:</strong> 53 MK, 150 SKS (80 SKS praktik = 53,33%). Dievaluasi 2020, 2021, 2024.</p>
          <p><strong>Penelitian:</strong> 45 penelitian (14→13→18). 36 internal (80%), 9 eksternal nasional (20%).</p>
          <p><strong>PkM:</strong> 14 kegiatan (2→6→6). 100% internal/mandiri.</p>
        </div>
      </div>

      <!-- ===== C.4 SDM ===== -->
      <div class="ledps-criteria" id="ledps-c4">
        <div class="lkps-section">
          <h3>‍🏫 C.4 — Sumber Daya Manusia</h3>
          <div class="info-box">
            <strong>📂 Link Bukti:</strong>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 DTPS & CV</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Publikasi</a>
            <a href="https://drive.google.com/drive/folders/1ReDF1ecxwnx7v2lVkMaxdwkl8Hd7NF1z" target="_blank" class="ev-open-btn">📂 Produk Diadopsi (13)</a>
          </div>
          <p><strong>DTPS:</strong> 11 dosen (3 doktor, 4 LK, 6 Lektor). BKD rata-rata 14,77 SKS.</p>
          <p><strong>Publikasi:</strong> 220 (73 JNT, 12 JIB, 92 Prosiding Nas, 33 Prosiding Intl).</p>
          <p><strong>Produk Diadopsi:</strong> 13 produk/jasa DTPS.</p>
        </div>
      </div>

      <!-- ===== C.5 SARPRAS ===== -->
      <div class="ledps-criteria" id="ledps-c5">
        <div class="lkps-section">
          <h3>💰 C.5 — Sarana, Prasarana, dan K3L</h3>
          <div class="info-box">
            <strong>📂 Link Bukti:</strong>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Sarpras & Lab</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 K3L</a>
          </div>
          <p><strong>Sarana:</strong> 7 lab + 1 bengkel, 12 ruang kelas. Seluruhnya terawat.</p>
          <p><strong>K3L:</strong> 17 dokumen, 12 fasilitas (APAR, Hidran, Ambulance, P3K, Jalur Evakuasi).</p>
        </div>
      </div>

      <!-- ===== C.6 LUARAN ===== -->
      <div class="ledps-criteria" id="ledps-c6">
        <div class="lkps-section">
          <h3> C.6 — Mahasiswa dan Luaran</h3>
          <div class="info-box">
            <strong>📂 Link Bukti:</strong>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Tracer Study</a>
            <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank" class="ev-open-btn">📂 Survei Kepuasan</a>
            <a href="https://drive.google.com/drive/folders/1gj3fyC_mO2c6pDTNRzhnlPcIE4_pKBYS" target="_blank" class="ev-open-btn">📂 Produk Mahasiswa (16)</a>
          </div>
          <p><strong>Mahasiswa:</strong> 189 aktif, 13 asing. IPK rata-rata 3,46. Masa studi 4,06 tahun.</p>
          <p><strong>Prestasi:</strong> 19 (10 akademik + 9 nonakademik).</p>
          <p><strong>Publikasi Mhs:</strong> 126 (34 JNT, 1 JIB, 91 Prosiding).</p>
          <p><strong>Tracer:</strong> 80 lulusan, 61 terlacak (76,25%). 70,49% kesesuaian kerja tinggi.</p>
        </div>
      </div>

      <!-- ===== C.7 SPMI ===== -->
      <div class="ledps-criteria" id="ledps-c7">
        <div class="lkps-section">
          <h3>🔄 C.7 — Sistem Penjaminan Mutu</h3>
          <div class="info-box">
            <strong>📂 Link Bukti:</strong>
            <a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S" target="_blank" class="ev-open-btn">📂 Dokumen SPMI</a>
            <a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2" target="_blank" class="ev-open-btn">📂 Laporan AMI</a>
            <a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0" target="_blank" class="ev-open-btn">📂 Notulensi RTM</a>
            <a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0" target="_blank" class="ev-open-btn"> Dokumen RTL</a>
          </div>
          <p><strong>Struktur:</strong> UPM (institusi) + GPM (jurusan) sejak 2023.</p>
          <p><strong>Siklus PPEPP:</strong> Penetapan → Pelaksanaan → Evaluasi → Pengendalian → Peningkatan.</p>
          <p><strong>AMI:</strong> Audit Mutu Internal tahunan. <strong>RTM:</strong> Rapat Tinjauan Manajemen.</p>
        </div>
      </div>

      <!-- ===== BAB III ===== -->
      <div class="ledps-criteria" id="ledps-bab3">
        <div class="lkps-section">
          <h3>📕 BAB III — Program Pengembangan Berkelanjutan</h3>
          
          <h4 style="color:#e65100; margin-top:20px;">📊 Analisis SWOT</h4>
          <div class="summary-grid">
            <div class="summary-card" style="border-left-color: #4caf50; background: #e8f5e9;">
              <div class="sc-label"> STRENGTH</div>
              <div class="sc-value" style="font-size:0.9rem;">Kekuatan</div>
              <div class="sc-desc">Kekhasan Broadband Multimedia, 11 DTPS relevan, kurikulum vokasi kuat (53,33% praktik), 66 kerja sama tridharma</div>
            </div>
            <div class="summary-card" style="border-left-color: #ff9800; background: #fff3e0;">
              <div class="sc-label">⚠️ WEAKNESS</div>
              <div class="sc-value" style="font-size:0.9rem;">Kelemahan</div>
              <div class="sc-desc">Pendanaan penelitian 80% internal, keterlibatan mhs 26,67%, PkM 100% internal, rekognisi internasional rendah</div>
            </div>
            <div class="summary-card" style="border-left-color: #2196f3; background: #e3f2fd;">
              <div class="sc-label">🚀 OPPORTUNITY</div>
              <div class="sc-value" style="font-size:0.9rem;">Peluang</div>
              <div class="sc-desc">Transformasi digital & 5G/6G, IoT, AI, cloud computing, hibah nasional (BIMA, DRTPM)</div>
            </div>
            <div class="summary-card" style="border-left-color: #f44336; background: #ffebee;">
              <div class="sc-label">⚡ THREAT</div>
              <div class="sc-value" style="font-size:0.9rem;">Ancaman</div>
              <div class="sc-desc">Perubahan teknologi cepat, persaingan PT sejenis, tuntutan kompetensi DUDI dinamis</div>
            </div>
          </div>

          <h4 style="color:#e65100; margin-top:20px;">🎯 6 Tujuan Strategis</h4>
          <div class="summary-grid">
            <div class="summary-card" style="border-left-color: #e65100;">
              <div class="sc-label">Tujuan 1</div>
              <div class="sc-value" style="font-size:0.9rem;">Memperkuat relevansi & mutu pendidikan</div>
              <div class="sc-desc">Indikator: 100% CPL terukur</div>
            </div>
            <div class="summary-card" style="border-left-color: #e65100;">
              <div class="sc-label">Tujuan 2</div>
              <div class="sc-value" style="font-size:0.9rem;">Meningkatkan penelitian & hilirisasi</div>
              <div class="sc-desc">Target: ≥40% pendanaan eksternal</div>
            </div>
            <div class="summary-card" style="border-left-color: #e65100;">
              <div class="sc-label">Tujuan 3</div>
              <div class="sc-value" style="font-size:0.9rem;">Meningkatkan kualitas SDM</div>
              <div class="sc-desc">Target: 5 doktor, 50% LK</div>
            </div>
            <div class="summary-card" style="border-left-color: #e65100;">
              <div class="sc-label">Tujuan 4</div>
              <div class="sc-value" style="font-size:0.9rem;">Memperluas internasionalisasi</div>
              <div class="sc-desc">Target: ≥5 kerja sama intl</div>
            </div>
            <div class="summary-card" style="border-left-color: #e65100;">
              <div class="sc-label">Tujuan 5</div>
              <div class="sc-value" style="font-size:0.9rem;">Meningkatkan daya saing lulusan</div>
              <div class="sc-desc">Target: ≥80% sesuai bidang</div>
            </div>
            <div class="summary-card" style="border-left-color: #e65100;">
              <div class="sc-label">Tujuan 6</div>
              <div class="sc-value" style="font-size:0.9rem;">Memperkuat budaya mutu</div>
              <div class="sc-desc">Target: Siklus PPEPP berjalan</div>
            </div>
          </div>

          <h4 style="color:#e65100; margin-top:20px;">📘 6 Program Pengembangan</h4>
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
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  document.querySelectorAll('.lkps-table-panel').forEach((p, i) => {
    p.classList.toggle('active', i === 0);
  });
  document.querySelectorAll('.ledps-criteria').forEach((p, i) => {
    p.classList.toggle('active', i === 0);
  });
});
</script>

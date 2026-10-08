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
.ev-tab.sesi3.active { background: linear-gradient(135deg, #f57c00 0%, #e65100 100%); border-color: #e65100; }
.ev-tab.sesi3.active::before { background: linear-gradient(135deg, #f57c00 0%, #e65100 100%); }

.ev-content { background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1; border-radius: 0 0 16px 16px; padding: 28px; min-height: 500px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px; }
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

.session-header { padding: 24px; border-radius: 12px; margin-bottom: 20px; color: white; }
.session-header.sesi1 { background: linear-gradient(135deg, #1565c0 0%, #0d47a1 100%); }
.session-header.sesi2 { background: linear-gradient(135deg, #388e3c 0%, #2e7d32 100%); }
.session-header.sesi3 { background: linear-gradient(135deg, #f57c00 0%, #e65100 100%); }
.session-header h2 { margin: 0 0 8px 0; font-size: 1.4rem; }
.session-header .subtitle { opacity: 0.95; font-size: 0.92rem; margin-bottom: 12px; }
.session-info { display: flex; gap: 12px; flex-wrap: wrap; }
.session-info .info-item { background: rgba(255,255,255,0.2); padding: 8px 14px; border-radius: 8px; font-size: 0.85rem; backdrop-filter: blur(4px); }
.session-info .info-item strong { display: block; font-size: 1.3rem; margin-bottom: 2px; }

.lkps-section { margin-bottom: 24px; }
.lkps-section h3 { color: #0d47a1; border-left: 4px solid #0d47a1; padding-left: 12px; margin-bottom: 12px; font-size: 1.1rem; }
.lkps-section.sesi2 h3 { color: #2e7d32; border-left-color: #2e7d32; }
.lkps-section.sesi3 h3 { color: #e65100; border-left-color: #e65100; }

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
.ev-tab { min-width: 90px; flex: 0 0 auto; font-size: 0.72rem; padding: 12px 6px 16px 6px; }
.ev-content { padding: 20px; }
.summary-grid { grid-template-columns: 1fr 1fr; }
.session-info { flex-direction: column; }
.swot-grid { grid-template-columns: 1fr; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('sesi1', this)">📊<br>SESI 1<br>LKPS</div>
    <div class="ev-tab sesi2" onclick="showEvPanel('sesi2', this)">🔄<br>SESI 2<br>Penjaminan Mutu</div>
    <div class="ev-tab sesi3" onclick="showEvPanel('sesi3', this)">📕<br>SESI 3<br>LEDPS</div>
  </div>

  <div class="ev-content">

    <!-- ========== SESI 1: LKPS ========== -->
    <div class="ev-panel active" id="panel-sesi1">
      <div class="session-header sesi1">
        <h2>📊 SESI 1 — LAPORAN KINERJA PROGRAM STUDI (LKPS)</h2>
        <div class="subtitle">Data kuantitatif 3 tahun terakhir (TS-2, TS-1, TS) — Semua Kriteria C.1–C.7</div>
        <div class="session-info">
          <div class="info-item"><strong>50+</strong> Tabel Evidence</div>
          <div class="info-item"><strong>C.1–C.7</strong> Semua Kriteria</div>
          <div class="info-item"><strong>3 Tahun</strong> Periode Data</div>
        </div>
      </div>

      <div class="info-box">
        <strong>️ Informasi:</strong> Halaman ini menampilkan seluruh tabel LKPS PSBM yang telah disubmit ke SAKTI LAM Teknik. Data disajikan per kriteria dengan ringkasan dan link ke dokumen asli di Google Drive.
      </div>

      <!-- Tabel 1: VMTS -->
      <div class="lkps-section">
        <h3>📑 Tabel 1: VMTS PT, UPPS, dan Visi Keilmuan PS</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead>
              <tr><th>No</th><th>Jenis VMTS</th><th>Pernyataan (Ringkasan)</th><th>No. SK</th><th>Link Dokumen</th></tr>
            </thead>
            <tbody>
              <tr><td>1</td><td><strong>VMTS PT</strong></td><td>Visi: Menjadi politeknik unggul bertaraf internasional untuk mendukung daya saing bangsa</td><td>643/PL3/OT/2021</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU?usp=drive_link" target="_blank">📂 Buka Folder</a></td></tr>
              <tr><td>2</td><td><strong>VMTS UPPS (JTE)</strong></td><td>Visi: Menjadi Jurusan Teknik Elektro unggul bertaraf internasional untuk mendukung daya saing bangsa</td><td>2585/PL3/OT/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1JiRWv_v_-pbrFTMl74JwQzJ1ZNnCpcOt?usp=drive_link" target="_blank">📂 Buka Folder</a></td></tr>
              <tr><td>3</td><td><strong>Visi Keilmuan PS</strong></td><td>Menjadi program studi unggul bertaraf internasional di bidang broadband multimedia untuk mendukung daya saing bangsa</td><td>2589/PL3/KR.00/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf?usp=sharing" target="_blank">📂 Buka Folder</a></td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Tabel 2a1: Kerja Sama Pendidikan -->
      <div class="lkps-section">
        <h3>🤝 Tabel 2a1: Kerja Sama Pendidikan (42)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">5</div></div>
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">37</div></div>
          <div class="summary-card"><div class="sc-label">Lokal/Wilayah</div><div class="sc-value">0</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">42</div></div>
        </div>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Lembaga Mitra</th><th>Tingkat</th><th>Judul Kegiatan</th><th>Durasi</th><th>Status</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>St. John's University Taiwan</td><td>Internasional</td><td>Student Mobility</td><td>5 tahun</td><td>Valid</td></tr>
              <tr><td>2</td><td>Sultan Haji Ahmad Shah Polytechnic</td><td>Internasional</td><td>Student Exchange</td><td>—</td><td>Valid</td></tr>
              <tr><td>3</td><td>PT Kekar Karya Indonesia (Train4best)</td><td>Nasional</td><td>Pelatihan, Sertifikasi, Magang</td><td>3 tahun</td><td>Valid</td></tr>
              <tr><td>4</td><td>PT Ericsson</td><td>Internasional</td><td>Pelatihan Teknologi 5G</td><td>—</td><td>Valid</td></tr>
              <tr><td>5</td><td>PT Huawei</td><td>Internasional</td><td>Training Technology & Study Ekskursi</td><td>—</td><td>Valid</td></tr>
              <tr><td>6</td><td>PT Telkomsel Indonesia</td><td>Nasional</td><td>Training, Hands-on, Kuliah Umum</td><td>5 tahun</td><td>Valid</td></tr>
            </tbody>
          </table>
        </div>
        <p style="font-size:0.85rem; color:#666;">* Menampilkan 6 dari 42 kerja sama pendidikan. <a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU" target="_blank">Lihat semua di Google Drive →</a></p>
      </div>

      <!-- Tabel 2a2: Kerja Sama Penelitian -->
      <div class="lkps-section">
        <h3> Tabel 2a2: Kerja Sama Penelitian (17)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">1</div></div>
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">16</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">17</div></div>
        </div>
      </div>

      <!-- Tabel 2a3: Kerja Sama PkM -->
      <div class="lkps-section">
        <h3>🤝 Tabel 2a3: Kerja Sama PkM (7)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">1</div></div>
          <div class="summary-card"><div class="sc-label">Lokal/Wilayah</div><div class="sc-value">6</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">7</div></div>
        </div>
      </div>

      <!-- Tabel 2b: Penggunaan Dana -->
      <div class="lkps-section">
        <h3> Tabel 2b: Penggunaan Dana (Rupiah)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Jenis Penggunaan</th><th>UPPS TS-2</th><th>UPPS TS-1</th><th>UPPS TS</th><th>UPPS Rata-rata</th><th>PS TS-2</th><th>PS TS-1</th><th>PS TS</th><th>PS Rata-rata</th></tr></thead>
            <tbody>
              <tr><td>1</td><td><strong>Biaya Operasional Pendidikan</strong></td><td colspan="4"></td><td colspan="4"></td></tr>
              <tr><td></td><td>a. Biaya Dosen</td><td>10,37 M</td><td>11,72 M</td><td>12,40 M</td><td>11,50 M</td><td>1,57 M</td><td>1,74 M</td><td>1,80 M</td><td>1,71 M</td></tr>
              <tr><td></td><td>b. Biaya Tendik</td><td>1,18 M</td><td>0,89 M</td><td>3,27 M</td><td>1,78 M</td><td>0,18 M</td><td>0,13 M</td><td>0,47 M</td><td>0,26 M</td></tr>
              <tr><td></td><td>c. Biaya Operasional Pembelajaran</td><td>6,73 M</td><td>6,88 M</td><td>5,86 M</td><td>6,49 M</td><td>1,02 M</td><td>1,02 M</td><td>0,85 M</td><td>0,96 M</td></tr>
              <tr><td colspan="9" style="background:#f1f5f9; font-weight:700;"><strong>Jumlah Operasional + Kemahasiswaan</strong></td></tr>
              <tr><td></td><td>Total</td><td>25,70 M</td><td>25,68 M</td><td>26,09 M</td><td>25,83 M</td><td>3,91 M</td><td>3,83 M</td><td>3,79 M</td><td>3,84 M</td></tr>
              <tr><td>3</td><td><strong>Biaya Penelitian</strong></td><td>1,09 M</td><td>1,18 M</td><td>0,91 M</td><td>1,06 M</td><td>0,15 M</td><td>0,16 M</td><td>0,12 M</td><td>0,14 M</td></tr>
              <tr><td>4</td><td><strong>Biaya PkM</strong></td><td>0,40 M</td><td>0,33 M</td><td>0,31 M</td><td>0,35 M</td><td>0,09 M</td><td>0,10 M</td><td>0,06 M</td><td>0,08 M</td></tr>
              <tr><td colspan="9" style="background:#fff8e1; font-weight:700;"><strong>TOTAL KESELURUHAN</strong></td></tr>
              <tr class="highlight-data"><td></td><td><strong>Total</strong></td><td>27,21 M</td><td>27,21 M</td><td>27,31 M</td><td>27,24 M</td><td>4,15 M</td><td>4,10 M</td><td>3,98 M</td><td>4,08 M</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Tabel 3a1: Kurikulum -->
      <div class="lkps-section">
        <h3>📘 Tabel 3a1: Kurikulum (53 MK, 150 SKS)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Total MK</div><div class="sc-value">53</div></div>
          <div class="summary-card"><div class="sc-label">Total SKS</div><div class="sc-value">150</div></div>
          <div class="summary-card"><div class="sc-label">MK Kompetensi</div><div class="sc-value">25</div></div>
          <div class="summary-card"><div class="sc-label">SKS Praktik</div><div class="sc-value">80 (53,33%)</div></div>
          <div class="summary-card"><div class="sc-label">SKS Kuliah</div><div class="sc-value">68</div></div>
          <div class="summary-card"><div class="sc-label">SKS Seminar</div><div class="sc-value">2</div></div>
        </div>
      </div>

      <!-- Tabel 3b: Penelitian -->
      <div class="lkps-section">
        <h3>🔬 Tabel 3b: Penelitian DTPS (45 judul, 3 tahun)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">14</div></div>
          <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">13</div></div>
          <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">18</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">45</div></div>
          <div class="summary-card"><div class="sc-label">PT/Mandiri</div><div class="sc-value">36 (80%)</div></div>
          <div class="summary-card"><div class="sc-label">Eksternal Nasional</div><div class="sc-value">9 (20%)</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Luar Negeri</div><div class="sc-value">0</div></div>
        </div>
      </div>

      <!-- Tabel 3c: PkM -->
      <div class="lkps-section">
        <h3>🤝 Tabel 3c: PkM DTPS (14 judul, 3 tahun)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">2</div></div>
          <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">6</div></div>
          <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">6</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">14</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Internal/Mandiri</div><div class="sc-value">14 (100%)</div></div>
          <div class="summary-card"><div class="sc-label">Eksternal</div><div class="sc-value">0</div></div>
        </div>
      </div>

      <!-- Tabel 4a: DTPS -->
      <div class="lkps-section">
        <h3>‍🏫 Tabel 4a: Profil DTPS (11 Dosen)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Total DTPS</div><div class="sc-value">11</div></div>
          <div class="summary-card"><div class="sc-label">Doktor</div><div class="sc-value">3 (27,27%)</div></div>
          <div class="summary-card"><div class="sc-label">Lektor Kepala</div><div class="sc-value">4 (36,36%)</div></div>
          <div class="summary-card"><div class="sc-label">Lektor</div><div class="sc-value">6</div></div>
          <div class="summary-card"><div class="sc-label">Asisten Ahli</div><div class="sc-value">2</div></div>
          <div class="summary-card"><div class="sc-label">Tenaga Pengajar</div><div class="sc-value">1</div></div>
        </div>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Nama Dosen</th><th>NIDN</th><th>Jabatan</th><th>Pendidikan Tertinggi</th><th>Bidang Keahlian</th><th>Sertifikasi</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Dr. Isdawimah, S.T., M.T.</td><td>0005056305</td><td>Lektor Kepala</td><td>Doktor</td><td>Aplikasi Sistem Kelistrikan Energi Terbarukan</td><td>4 sertifikat</td></tr>
              <tr><td>2</td><td>Nana Sutarna, S.T., M.T., Ph.D.</td><td>0012077003</td><td>Lektor Kepala</td><td>Ph.D.</td><td>Teknologi Rekayasa Elektronika</td><td>5 sertifikat</td></tr>
              <tr><td>3</td><td>Mera Kartika Delimayanti, Ph.D.</td><td>0028047901</td><td>Lektor Kepala</td><td>Ph.D.</td><td>Sains Data Terapan</td><td>15 sertifikat</td></tr>
              <tr><td>4</td><td>Zulhelman, S.T., M.T.</td><td>0002036403</td><td>Lektor Kepala</td><td>Magister</td><td>Teknologi Rekayasa Internet</td><td>1 sertifikat</td></tr>
              <tr><td>5</td><td>Agus Wagyana, S.T., M.T.</td><td>0024086802</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Internet</td><td>2 sertifikat</td></tr>
              <tr><td>6</td><td>Asri Wulandari, S.T., M.T.</td><td>0001037501</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Telekomunikasi</td><td>5 sertifikat</td></tr>
              <tr><td>7</td><td>Dandun Widhiantoro, S.T., M.T.</td><td>0025117002</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Telekomunikasi</td><td>5 sertifikat</td></tr>
              <tr><td>8</td><td>Mohamad Fathurahman, S.T., M.T.</td><td>0024087107</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Internet</td><td>6 sertifikat</td></tr>
              <tr><td>9</td><td>Viving Frendiana, S.ST., M.T.</td><td>0715019002</td><td>Lektor</td><td>Magister</td><td>Teknologi Rekayasa Internet</td><td>3 sertifikat</td></tr>
              <tr><td>10</td><td>Toto Supriyanto, S.T., M.T.</td><td>0006036603</td><td>Lektor</td><td>Magister</td><td>Teknologi Telekomunikasi</td><td>1 sertifikat</td></tr>
              <tr><td>11</td><td>Shita Herfiah, S.Pd., M.T.</td><td>5055775676230213</td><td>Asisten Ahli</td><td>Magister</td><td>Teknologi Rekayasa Telekomunikasi</td><td>CCST Networking</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Tabel 4e: Publikasi -->
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

      <!-- Tabel 4g: Produk Diadopsi -->
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
              <tr><td>6</td><td>Mohamad Fathurahman</td><td>Smart Aquaculture LoRa BBI Ciganjur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1-BrkUP0EVaN4J3rrFYyBJtyBNRLzRwnX?usp=sharing" target="_blank"> Buka</a></td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Tabel 6a: Mahasiswa -->
      <div class="lkps-section">
        <h3>🎓 Tabel 6a: Jumlah Mahasiswa (189 aktif TS)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">192</div></div>
          <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">182</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">TS</div><div class="sc-value">189</div></div>
          <div class="summary-card"><div class="sc-label">Mhs Asing FT TS</div><div class="sc-value">0</div></div>
          <div class="summary-card"><div class="sc-label">Mhs Asing PT TS</div><div class="sc-value">12</div></div>
        </div>
      </div>

      <!-- Tabel 6b: IPK -->
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

      <!-- Tabel 6f1: Waktu Tunggu -->
      <div class="lkps-section">
        <h3>📈 Tabel 6f1: Waktu Tunggu Lulusan</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Total Lulusan</div><div class="sc-value">80</div></div>
          <div class="summary-card"><div class="sc-label">Terlacak</div><div class="sc-value">61 (76,25%)</div></div>
          <div class="summary-card"><div class="sc-label">WT < 3 bulan</div><div class="sc-value">34 (55,74%)</div></div>
          <div class="summary-card"><div class="sc-label">WT 3-18 bulan</div><div class="sc-value">27 (44,26%)</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">WT > 18 bulan</div><div class="sc-value">0</div></div>
        </div>
      </div>

      <!-- Tabel 6g2: Kepuasan Pengguna -->
      <div class="lkps-section">
        <h3>⭐ Tabel 6g2: Kepuasan Pengguna Lulusan (45 responden)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Jenis Kemampuan</th><th>Sangat Baik</th><th>Baik</th><th>Cukup</th><th>Kurang</th><th>Rencana Tindak Lanjut</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Etika</td><td class="highlight-data">80,00%</td><td>20,00%</td><td>0,00%</td><td>0,00%</td><td>Mempertahankan capaian</td></tr>
              <tr><td>2</td><td>Keahlian bidang ilmu</td><td class="highlight-data">73,30%</td><td>26,70%</td><td>0,00%</td><td>0,00%</td><td>Pemutakhiran kurikulum</td></tr>
              <tr><td>3</td><td>Bahasa asing</td><td class="highlight-data">71,10%</td><td>17,80%</td><td class="highlight-data">11,10%</td><td>0,00%</td><td>Kelas intensif, sertifikasi TOEFL/TOEIC</td></tr>
              <tr><td>4</td><td>Teknologi informasi</td><td class="highlight-data">82,20%</td><td>17,80%</td><td>0,00%</td><td>0,00%</td><td>Pelatihan/sertifikasi tambahan</td></tr>
              <tr><td>5</td><td>Berkomunikasi</td><td class="highlight-data">77,78%</td><td>22,20%</td><td>0,00%</td><td>0,00%</td><td>Soft skill, public speaking</td></tr>
              <tr><td>6</td><td>Kerjasama tim</td><td class="highlight-data">75,60%</td><td>24,40%</td><td>0,00%</td><td>0,00%</td><td>Tugas kelompok, proyek kolaboratif</td></tr>
              <tr><td>7</td><td>Pengembangan diri</td><td class="highlight-data">73,30%</td><td>26,70%</td><td>0,00%</td><td>0,00%</td><td>Organisasi, pelatihan kepemimpinan</td></tr>
            </tbody>
          </table>
        </div>
        <div class="info-box"><strong>⚠️ Catatan Kritis:</strong> Bahasa asing memiliki 11,1% "Cukup". Perlu direkonsiliasi dengan narasi RTL yang menyebut 25%.</div>
      </div>
    </div>

    <!-- ========== SESI 2: PENJAMINAN MUTU ========== -->
    <div class="ev-panel" id="panel-sesi2">
      <div class="session-header sesi2">
        <h2>🔄 SESI 2 — PENJAMINAN MUTU (SPMI)</h2>
        <div class="subtitle">Sistem Penjaminan Mutu Internal & Eksternal — Siklus PPEPP</div>
        <div class="session-info">
          <div class="info-item"><strong>10+</strong> Dokumen Evidence</div>
          <div class="info-item"><strong>C.7</strong> Fokus Utama</div>
          <div class="info-item"><strong>PPEPP</strong> Siklus Mutu</div>
        </div>
      </div>

      <!-- Tabel 7a: Dokumen SPMI -->
      <div class="lkps-section sesi2">
        <h3>📋 Tabel 7a: Dokumen SPMI (4 dokumen)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Jenis Dokumen</th><th>No Dokumen</th><th>Tanggal</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Kebijakan SPMI</td><td>No: SM/PNJ/SPMI/342</td><td>18/1/2022</td></tr>
              <tr><td>2</td><td>Pedoman penerapan siklus PPEPP</td><td>KM/PNJ/SPMI/212</td><td>18/1/2022</td></tr>
              <tr><td>3</td><td>Standar mutu penyelenggaraan pendidikan</td><td>SM/PNJ/SPMI/311</td><td>20/1/2022</td></tr>
              <tr><td>4</td><td>Tata cara pendokumentasian implementasi SPMI</td><td>KM/PNJ/SPMI/215</td><td>20/1/2022</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Tabel 7b: Pelaksanaan SPMI -->
      <div class="lkps-section sesi2">
        <h3>🔄 Tabel 7b: Pelaksanaan SPMI (Siklus PPEPP)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Tahap PPEPP</th><th>Link Dokumen</th><th>Link Laporan Audit</th><th>Link RTM</th><th>Link Peningkatan</th></tr></thead>
            <tbody>
              <tr><td>1</td><td><strong>Penetapan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S?usp=drive_link" target="_blank">📂 Buka</a></td><td>—</td><td>—</td><td>—</td></tr>
              <tr><td>2</td><td><strong>Pelaksanaan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S?usp=drive_link" target="_blank">📂 Buka</a></td><td>—</td><td>—</td><td>—</td></tr>
              <tr><td>3</td><td><strong>Evaluasi</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1ywPn4RexBzQjD6DXRT8DCXTEtemvcQLz?usp=sharing" target="_blank">📂 Buka</a></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2?usp=sharing" target="_blank"> Buka</a></td><td>—</td><td>—</td></tr>
              <tr><td>4</td><td><strong>Pengendalian</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1WFgIamM3JnSGZ-WAv-UOC1W22E0ondmV?usp=sharing" target="_blank">📂 Buka</a></td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0?usp=sharing" target="_blank">📂 Buka</a></td><td>—</td></tr>
              <tr><td>5</td><td><strong>Peningkatan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0?usp=sharing" target="_blank">📂 Buka</a></td><td>—</td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0?usp=sharing" target="_blank">📂 Buka</a></td></tr>
            </tbody>
          </table>
        </div>
        <div class="info-box"><strong>✅ Siklus PPEPP Lengkap:</strong> Semua 5 tahap (Penetapan → Pelaksanaan → Evaluasi → Pengendalian → Peningkatan) terdokumentasi dengan link Google Drive aktif.</div>
      </div>

      <!-- Dokumen Pendukung SPMI -->
      <div class="lkps-section sesi2">
        <h3>📁 Dokumen Pendukung SPMI</h3>
        <div class="summary-grid">
          <div class="summary-card" style="border-left-color: #2e7d32;">
            <div class="sc-label">📜 SK GPM</div>
            <div class="sc-value" style="font-size:1rem;">Gugus Penjaminan Mutu</div>
            <div class="sc-desc">SK resmi pembentukan GPM JTE</div>
          </div>
          <div class="summary-card" style="border-left-color: #2e7d32;">
            <div class="sc-label">🔍 Laporan AMI</div>
            <div class="sc-value" style="font-size:1rem;">Audit Mutu Internal</div>
            <div class="sc-desc">Hasil audit tahunan 7 kriteria</div>
          </div>
          <div class="summary-card" style="border-left-color: #2e7d32;">
            <div class="sc-label">📝 Notulensi RTM</div>
            <div class="sc-value" style="font-size:1rem;">Rapat Tinjauan Manajemen</div>
            <div class="sc-desc">Tinjauan hasil AMI oleh pimpinan</div>
          </div>
          <div class="summary-card" style="border-left-color: #2e7d32;">
            <div class="sc-label">📋 Dokumen RTL</div>
            <div class="sc-value" style="font-size:1rem;">Rencana Tindak Lanjut</div>
            <div class="sc-desc">15 temuan AMI dengan RTL</div>
          </div>
          <div class="summary-card" style="border-left-color: #2e7d32;">
            <div class="sc-label">⭐ Survei Kepuasan</div>
            <div class="sc-value" style="font-size:1rem;">Stakeholder</div>
            <div class="sc-desc">Mahasiswa, dosen, tendik, lulusan</div>
          </div>
          <div class="summary-card" style="border-left-color: #2e7d32;">
            <div class="sc-label">⭐ Survei Pengguna</div>
            <div class="sc-value" style="font-size:1rem;">Lulusan</div>
            <div class="sc-desc">45 responden, 7 aspek</div>
          </div>
        </div>
      </div>
    </div>

    <!-- ========== SESI 3: LEDPS ========== -->
    <div class="ev-panel" id="panel-sesi3">
      <div class="session-header sesi3">
        <h2>📕 SESI 3 — LAPORAN EVALUASI DIRI (LEDPS)</h2>
        <div class="subtitle">Analisis, SWOT, dan Program Pengembangan Berkelanjutan</div>
        <div class="session-info">
          <div class="info-item"><strong>35+</strong> Dokumen Evidence</div>
          <div class="info-item"><strong>C.1 + BAB III</strong> Fokus Utama</div>
          <div class="info-item"><strong>SWOT</strong> Analisis Strategis</div>
        </div>
      </div>

      <!-- VMTS -->
      <div class="lkps-section sesi3">
        <h3>🎯 VMTS dan Visi Keilmuan</h3>
        <div class="summary-grid">
          <div class="summary-card" style="border-left-color: #e65100;">
            <div class="sc-label">📄 VMTS PT</div>
            <div class="sc-value" style="font-size:1rem;">SK 643/PL3/OT/2021</div>
            <div class="sc-desc">Visi: Politeknik unggul bertaraf internasional</div>
          </div>
          <div class="summary-card" style="border-left-color: #e65100;">
            <div class="sc-label">📄 VMTS UPPS</div>
            <div class="sc-value" style="font-size:1rem;">SK 2585/PL3/OT/2020</div>
            <div class="sc-desc">Visi: JTE unggul bertaraf internasional</div>
          </div>
          <div class="summary-card" style="border-left-color: #e65100;">
            <div class="sc-label">📘 Visi Keilmuan PS</div>
            <div class="sc-value" style="font-size:1rem;">SK 2589/PL3/KR.00/2020</div>
            <div class="sc-desc">Broadband Multimedia unggul internasional</div>
          </div>
        </div>
      </div>

      <!-- SWOT -->
      <div class="lkps-section sesi3">
        <h3> Analisis SWOT</h3>
        <div class="swot-grid">
          <div class="swot-card strength">
            <h4>💪 Strengths (Kekuatan)</h4>
            <ul>
              <li>VMTS linear PNJ→JTE→PSBM</li>
              <li>Kekhasan Broadband Multimedia</li>
              <li>Kurikulum responsif industri</li>
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
            <h4> Opportunities (Peluang)</h4>
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

      <!-- Tujuan Strategis -->
      <div class="lkps-section sesi3">
        <h3> Tujuan Strategis</h3>
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
      </div>

      <!-- Program Pengembangan -->
      <div class="lkps-section sesi3">
        <h3>📘 Program Pengembangan</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Program</th><th>Strategi</th><th>Target</th><th>PIC</th><th>Anggaran</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Penguatan Closed-Loop CPL</td><td>WO</td><td>100% CPL terukur & ditindaklanjuti</td><td>Kurikulum/GPM</td><td>Rp 30 juta</td></tr>
              <tr><td>2</td><td>Peningkatan Pendanaan Eksternal Penelitian</td><td>WO</td><td>≥40% pendanaan eksternal (2026)</td><td>P3M</td><td>Rp 50 juta</td></tr>
              <tr><td>3</td><td>Integrasi Penelitian DTPS dengan Mahasiswa</td><td>WO</td><td>≥40% penelitian libatkan mhs</td><td>P3M/Kaprodi</td><td>Rp 40 juta</td></tr>
              <tr><td>4</td><td>Percepatan JAFA & Studi Lanjut</td><td>ST</td><td>5 doktor, 50% LK, 1 GB</td><td>Kajur</td><td>Rp 200 juta</td></tr>
              <tr><td>5</td><td>Peningkatan Response Rate Tracer</td><td>WT</td><td>≥80% response rate</td><td>CDC/GPM</td><td>Rp 20 juta</td></tr>
              <tr><td>6</td><td>Internasionalisasi Kerja Sama & Publikasi</td><td>SO</td><td>≥5 MoU intl, ≥10 publikasi Scopus</td><td>Kajur/P3M</td><td>Rp 80 juta</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Monitoring & PPEPP -->
      <div class="lkps-section sesi3">
        <h3>🔄 Monitoring & PPEPP</h3>
        <div class="summary-grid">
          <div class="summary-card" style="border-left-color: #e65100;">
            <div class="sc-label">🔍 AMI</div>
            <div class="sc-value" style="font-size:1rem;">Audit Mutu Internal</div>
            <div class="sc-desc">Audit internal tahunan terhadap 7 kriteria</div>
          </div>
          <div class="summary-card" style="border-left-color: #e65100;">
            <div class="sc-label">📝 RTM</div>
            <div class="sc-value" style="font-size:1rem;">Rapat Tinjauan Manajemen</div>
            <div class="sc-desc">Tinjauan hasil AMI oleh pimpinan</div>
          </div>
          <div class="summary-card" style="border-left-color: #e65100;">
            <div class="sc-label">📋 RTL</div>
            <div class="sc-value" style="font-size:1rem;">Rencana Tindak Lanjut</div>
            <div class="sc-desc">15 temuan AMI dengan RTL terdokumentasi</div>
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
  window.scrollTo({ top: 0, behavior: 'smooth' });
}
</script>

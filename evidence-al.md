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

.ev-content { background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1; border-radius: 0 0 16px 16px; padding: 28px; min-height: 500px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px; }
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

.ev-hero { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); color: white; padding: 28px; border-radius: 12px; margin-bottom: 20px; text-align: center; }
.ev-hero h2 { margin: 0 0 6px 0; font-size: 1.4rem; }
.ev-hero .subtitle { opacity: 0.9; font-size: 0.9rem; margin-bottom: 16px; }

.lkps-section { margin-bottom: 30px; }
.lkps-section h3 { color: #0d47a1; border-left: 4px solid #0d47a1; padding-left: 12px; margin-bottom: 12px; font-size: 1.1rem; }
.table-responsive { overflow-x: auto; border: 1px solid #e0e0e0; border-radius: 8px; margin-bottom: 20px; }
.lkps-table { width: 100%; border-collapse: collapse; font-size: 0.82rem; min-width: 600px; }
.lkps-table th, .lkps-table td { border: 1px solid #e0e0e0; padding: 8px 10px; text-align: left; vertical-align: top; }
.lkps-table th { background-color: #f1f5f9; font-weight: 600; color: #0d47a1; position: sticky; top: 0; z-index: 1; }
.lkps-table tr:nth-child(even) { background-color: #f8fafc; }
.lkps-table tr:hover { background-color: #e3f2fd; }
.highlight-data { background-color: #fff8e1 !important; font-weight: 600; color: #e65100; }
.link-cell a { color: #0d47a1; text-decoration: none; word-break: break-all; font-weight: 600; }
.link-cell a:hover { text-decoration: underline; }

.summary-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 10px; margin: 16px 0; }
.summary-card { background: white; border: 1px solid #e0e0e0; border-left: 4px solid #0d47a1; border-radius: 8px; padding: 12px; }
.summary-card .sc-label { font-size: 0.72rem; color: #666; text-transform: uppercase; letter-spacing: 0.5px; }
.summary-card .sc-value { font-size: 1.4rem; font-weight: 800; color: #0d47a1; margin: 4px 0; }
.summary-card .sc-desc { font-size: 0.78rem; color: #555; }

.info-box { background: #e3f2fd; border-left: 4px solid #0d47a1; padding: 12px 16px; border-radius: 6px; margin-bottom: 20px; font-size: 0.88rem; color: #0d47a1; }
.info-box strong { color: #0a3a8a; }

@media (max-width: 767px) {
.ev-shelf { gap: 4px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
.ev-shelf::-webkit-scrollbar { display: none; }
.ev-tab { min-width: 90px; flex: 0 0 auto; font-size: 0.72rem; padding: 12px 6px 16px 6px; }
.ev-content { padding: 20px; }
.summary-grid { grid-template-columns: 1fr 1fr; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('beranda', this)">🏠<br>Beranda</div>
    <div class="ev-tab" onclick="showEvPanel('c1', this)">📑<br>C.1 VMTS</div>
    <div class="ev-tab" onclick="showEvPanel('c2', this)">️<br>C.2 Tata Kelola</div>
    <div class="ev-tab" onclick="showEvPanel('c3', this)">📘<br>C.3 Diklitpmas</div>
    <div class="ev-tab" onclick="showEvPanel('c4', this)">👨🏫<br>C.4 SDM</div>
    <div class="ev-tab" onclick="showEvPanel('c5', this)">💰<br>C.5 Sarpras</div>
    <div class="ev-tab" onclick="showEvPanel('c6', this)">🎓<br>C.6 Luaran</div>
    <div class="ev-tab" onclick="showEvPanel('c7', this)">🔄<br>C.7 SPMI</div>
  </div>

  <div class="ev-content">

    <!-- ========== BERANDA ========== -->
    <div class="ev-panel active" id="panel-beranda">
      <div class="ev-hero">
        <h2>📂 Evidence AL PSBM</h2>
        <div class="subtitle">Portal Bukti Pendukung Asesmen Lapangan — Program Studi Broadband Multimedia</div>
      </div>

      <div class="info-box">
        <strong>ℹ️ Informasi:</strong> Halaman ini menampilkan data lengkap dari LEDPS dan LKPS PSBM yang telah disubmit ke SAKTI LAM Teknik. Data disajikan per kriteria dengan link ke dokumen asli di Google Drive.
      </div>

      <div class="summary-grid">
        <div class="summary-card">
          <div class="sc-label">Program Studi</div>
          <div class="sc-value" style="font-size:1rem;">D-IV Broadband Multimedia</div>
          <div class="sc-desc">Politeknik Negeri Jakarta</div>
        </div>
        <div class="summary-card">
          <div class="sc-label">Akreditasi</div>
          <div class="sc-value" style="font-size:1rem;">Baik Sekali</div>
          <div class="sc-desc">093/SK/LAM-INFOKOM/Ak/STr/XII/2022</div>
        </div>
        <div class="summary-card">
          <div class="sc-label">Mahasiswa Aktif</div>
          <div class="sc-value">189</div>
          <div class="sc-desc">TS 2025</div>
        </div>
        <div class="summary-card">
          <div class="sc-label">DTPS</div>
          <div class="sc-value">11</div>
          <div class="sc-desc">3 Doktor, 4 LK, 6 Lektor</div>
        </div>
        <div class="summary-card">
          <div class="sc-label">Kerja Sama</div>
          <div class="sc-value">66</div>
          <div class="sc-desc">42 Pendidikan + 17 Penelitian + 7 PkM</div>
        </div>
        <div class="summary-card">
          <div class="sc-label">Penelitian</div>
          <div class="sc-value">45</div>
          <div class="sc-desc">3 tahun terakhir</div>
        </div>
        <div class="summary-card">
          <div class="sc-label">PkM</div>
          <div class="sc-value">14</div>
          <div class="sc-desc">3 tahun terakhir</div>
        </div>
        <div class="summary-card">
          <div class="sc-label">Publikasi DTPS</div>
          <div class="sc-value">220</div>
          <div class="sc-desc">3 tahun terakhir</div>
        </div>
      </div>
    </div>

    <!-- ========== C.1 VMTS ========== -->
    <div class="ev-panel" id="panel-c1">
      <div class="lkps-section">
        <h3>📑 C.1 — Tabel 1: VMTS PT, UPPS, dan Visi Keilmuan PS</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead>
              <tr><th>No</th><th>Jenis VMTS</th><th>Pernyataan</th><th>No. SK</th><th>Link Dokumen</th></tr>
            </thead>
            <tbody>
              <tr><td>1</td><td><strong>VMTS PT</strong></td><td>Visi: Menjadi politeknik unggul bertaraf internasional untuk mendukung daya saing bangsa</td><td>643/PL3/OT/2021</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU?usp=drive_link" target="_blank">📂 Buka Folder</a></td></tr>
              <tr><td>2</td><td><strong>VMTS UPPS (JTE)</strong></td><td>Visi: Menjadi Jurusan Teknik Elektro unggul bertaraf internasional untuk mendukung daya saing bangsa</td><td>2585/PL3/OT/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1JiRWv_v_-pbrFTMl74JwQzJ1ZNnCpcOt?usp=drive_link" target="_blank">📂 Buka Folder</a></td></tr>
              <tr><td>3</td><td><strong>Visi Keilmuan PS</strong></td><td>Menjadi program studi unggul bertaraf internasional di bidang broadband multimedia untuk mendukung daya saing bangsa</td><td>2589/PL3/KR.00/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf?usp=sharing" target="_blank">📂 Buka Folder</a></td></tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>

    <!-- ========== C.2 TATA KELOLA ========== -->
    <div class="ev-panel" id="panel-c2">
      <div class="lkps-section">
        <h3>🏛️ C.2 — Tabel 2a1: Kerja Sama Pendidikan (42)</h3>
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
      </div>

      <div class="lkps-section">
        <h3>🏛️ C.2 — Tabel 2a2: Kerja Sama Penelitian (17)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">1</div></div>
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">16</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">17</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🏛️ C.2 — Tabel 2a3: Kerja Sama PkM (7)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">1</div></div>
          <div class="summary-card"><div class="sc-label">Lokal/Wilayah</div><div class="sc-value">6</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">7</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>💰 C.2 — Tabel 2b: Penggunaan Dana (Rupiah)</h3>
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
    </div>

    <!-- ========== C.3 DIKLITPMAS ========== -->
    <div class="ev-panel" id="panel-c3">
      <div class="lkps-section">
        <h3>📘 C.3 — Tabel 3a1: Kurikulum (53 MK, 150 SKS)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Total MK</div><div class="sc-value">53</div></div>
          <div class="summary-card"><div class="sc-label">Total SKS</div><div class="sc-value">150</div></div>
          <div class="summary-card"><div class="sc-label">MK Kompetensi</div><div class="sc-value">25</div></div>
          <div class="summary-card"><div class="sc-label">SKS Praktik</div><div class="sc-value">80 (53,33%)</div></div>
          <div class="summary-card"><div class="sc-label">SKS Kuliah</div><div class="sc-value">68</div></div>
          <div class="summary-card"><div class="sc-label">SKS Seminar</div><div class="sc-value">2</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>📘 C.3 — Tabel 3b: Penelitian DTPS (45 judul, 3 tahun)</h3>
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

      <div class="lkps-section">
        <h3>📘 C.3 — Tabel 3c: PkM DTPS (14 judul, 3 tahun)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">2</div></div>
          <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">6</div></div>
          <div class="summary-card"><div class="sc-label">TS</div><div class="sc-value">6</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">14</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Internal/Mandiri</div><div class="sc-value">14 (100%)</div></div>
          <div class="summary-card"><div class="sc-label">Eksternal</div><div class="sc-value">0</div></div>
        </div>
      </div>
    </div>

    <!-- ========== C.4 SDM ========== -->
    <div class="ev-panel" id="panel-c4">
      <div class="lkps-section">
        <h3>‍🏫 C.4 — Tabel 4a: Profil DTPS (11 Dosen)</h3>
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

      <div class="lkps-section">
        <h3>👨‍🏫 C.4 — Tabel 4e: Publikasi DTPS (220 total)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Jurnal Nasional Terakreditasi</div><div class="sc-value">73</div></div>
          <div class="summary-card"><div class="sc-label">Jurnal Internasional Bereputasi</div><div class="sc-value">12</div></div>
          <div class="summary-card"><div class="sc-label">Prosiding Nasional</div><div class="sc-value">92</div></div>
          <div class="summary-card"><div class="sc-label">Prosiding Scopus/WoS</div><div class="sc-value">33</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">TOTAL</div><div class="sc-value">220</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>👨🏫 C.4 — Tabel 4g: Produk/Jasa DTPS Diadopsi (13)</h3>
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
            </tbody>
          </table>
        </div>
      </div>
    </div>

    <!-- ========== C.5 SARPRAS ========== -->
    <div class="ev-panel" id="panel-c5">
      <div class="lkps-section">
        <h3>💰 C.5 — Tabel 5a: Prasarana & Peralatan Utama</h3>
        <div class="info-box"><strong>📌 Ringkasan:</strong> 16 prasarana utama (13 lab/ruang + 3 layanan nonakademik). Seluruhnya terawat, dimiliki sendiri.</div>
      </div>

      <div class="lkps-section">
        <h3> C.5 — Tabel 5b: Dokumen K3L (17 dokumen)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Jenis Dokumen</th><th>Jumlah</th><th>Tanggal Pengesahan</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Pedoman Sistem Manajemen K3 Lingkungan PNJ</td><td>1</td><td>1 Januari 2025</td></tr>
              <tr><td>2</td><td>Pedoman K3L Jurusan Teknik Elektro</td><td>1</td><td>25 Oktober 2025</td></tr>
              <tr><td>3-15</td><td>13 SOP K3L (Identifikasi Bahaya, Pelatihan, Tanggap Darurat, Audit Internal, dll.)</td><td>13</td><td>1 Januari 2025</td></tr>
              <tr><td>16</td><td>SOP Penggunaan Lab dan Bengkel</td><td>1</td><td>1 Januari 2025</td></tr>
              <tr><td>17</td><td>Hasil Tinjauan Berkala K3</td><td>1</td><td>5 November 2025</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>💰 C.5 — Tabel 5c: Fasilitas K3L (12 item, semua terawat)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Nama Sarana</th><th>Fungsi</th><th>Jumlah</th><th>Kondisi</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Hidran Pilar</td><td>Suplai air pemadam</td><td>2</td><td>✓ Terawat</td></tr>
              <tr><td>2</td><td>Layanan Kesehatan</td><td>Pengobatan pertama</td><td>1</td><td>✓ Terawat</td></tr>
              <tr><td>3</td><td>Ambulance</td><td>Evakuasi</td><td>1</td><td>✓ Terawat</td></tr>
              <tr><td>4</td><td>APAR</td><td>Pemadam api ringan</td><td>6</td><td>✓ Terawat</td></tr>
              <tr><td>5</td><td>APAB</td><td>Pemadam api besar</td><td>1</td><td>✓ Terawat</td></tr>
              <tr><td>6</td><td>Truk Damkar</td><td>Pemadam api besar</td><td>1</td><td>✓ Terawat</td></tr>
              <tr><td>7</td><td>Rambu Keselamatan Kerja</td><td>Peringatan & instruksi</td><td>7</td><td>✓ Terawat</td></tr>
              <tr><td>8</td><td>Sign System APD</td><td>Informasi APD</td><td>5</td><td>✓ Terawat</td></tr>
              <tr><td>9</td><td>Kotak P3K</td><td>Pertolongan pertama</td><td>2</td><td>✓ Terawat</td></tr>
              <tr><td>10</td><td>Lemari Bahan Kimia</td><td>Penyimpanan aman</td><td>2</td><td>✓ Terawat</td></tr>
              <tr><td>11</td><td>Tanda Jalur Evakuasi</td><td>Jalur keluar darurat</td><td>22</td><td>✓ Terawat</td></tr>
              <tr><td>12</td><td>Video Safety Induction</td><td>Instruksi keselamatan</td><td>1</td><td>✓ Terawat</td></tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>

    <!-- ========== C.6 LUARAN ========== -->
    <div class="ev-panel" id="panel-c6">
      <div class="lkps-section">
        <h3> C.6 — Tabel 6a: Jumlah Mahasiswa (189 aktif TS)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">TS-2</div><div class="sc-value">192</div></div>
          <div class="summary-card"><div class="sc-label">TS-1</div><div class="sc-value">182</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">TS</div><div class="sc-value">189</div></div>
          <div class="summary-card"><div class="sc-label">Mhs Asing FT TS</div><div class="sc-value">0</div></div>
          <div class="summary-card"><div class="sc-label">Mhs Asing PT TS</div><div class="sc-value">12</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6b: IPK Lulusan</h3>
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
        <h3>🎓 C.6 — Tabel 6f1: Waktu Tunggu Lulusan</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Total Lulusan</div><div class="sc-value">80</div></div>
          <div class="summary-card"><div class="sc-label">Terlacak</div><div class="sc-value">61 (76,25%)</div></div>
          <div class="summary-card"><div class="sc-label">WT < 3 bulan</div><div class="sc-value">34 (55,74%)</div></div>
          <div class="summary-card"><div class="sc-label">WT 3-18 bulan</div><div class="sc-value">27 (44,26%)</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">WT > 18 bulan</div><div class="sc-value">0</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6g2: Kepuasan Pengguna Lulusan (45 responden)</h3>
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

    <!-- ========== C.7 SPMI ========== -->
    <div class="ev-panel" id="panel-c7">
      <div class="lkps-section">
        <h3>🔄 C.7 — Tabel 7a: Dokumen SPMI (4 dokumen)</h3>
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

      <div class="lkps-section">
        <h3>🔄 C.7 — Tabel 7b: Pelaksanaan SPMI (Siklus PPEPP)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Tahap PPEPP</th><th>Link Dokumen</th><th>Link Laporan Audit</th><th>Link RTM</th><th>Link Peningkatan</th></tr></thead>
            <tbody>
              <tr><td>1</td><td><strong>Penetapan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S?usp=drive_link" target="_blank">📂 Buka</a></td><td>—</td><td>—</td><td>—</td></tr>
              <tr><td>2</td><td><strong>Pelaksanaan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S?usp=drive_link" target="_blank">📂 Buka</a></td><td>—</td><td>—</td><td>—</td></tr>
              <tr><td>3</td><td><strong>Evaluasi</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1ywPn4RexBzQjD6DXRT8DCXTEtemvcQLz?usp=sharing" target="_blank">📂 Buka</a></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2?usp=sharing" target="_blank">📂 Buka</a></td><td>—</td><td>—</td></tr>
              <tr><td>4</td><td><strong>Pengendalian</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1WFgIamM3JnSGZ-WAv-UOC1W22E0ondmV?usp=sharing" target="_blank">📂 Buka</a></td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0?usp=sharing" target="_blank">📂 Buka</a></td><td>—</td></tr>
              <tr><td>5</td><td><strong>Peningkatan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0?usp=sharing" target="_blank">📂 Buka</a></td><td>—</td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0?usp=sharing" target="_blank"> Buka</a></td></tr>
            </tbody>
          </table>
        </div>
        <div class="info-box"><strong>✅ Siklus PPEPP Lengkap:</strong> Semua 5 tahap (Penetapan → Pelaksanaan → Evaluasi → Pengendalian → Peningkatan) terdokumentasi dengan link Google Drive aktif.</div>
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

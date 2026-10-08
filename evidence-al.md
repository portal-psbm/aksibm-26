---
layout: default
title: Evidence AL - LKPS Lengkap
permalink: /evidence-al/
---

<style>
/* ===== CABINET & TABS ===== */
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
.ev-tab.bab3-tab { background: linear-gradient(180deg, #fff8e1 0%, #ffecb3 100%); color: #e65100; border-color: #ffcc80; }
.ev-tab.bab3-tab::before { background: linear-gradient(180deg, #ffcc80 0%, #ffb74d 100%); border-color: #ffcc80; }
.ev-tab.bab3-tab.active { background: linear-gradient(135deg, #e65100 0%, #bf360c 100%); color: white; border-color: #bf360c; }
.ev-tab.bab3-tab.active::before { background: linear-gradient(135deg, #e65100 0%, #bf360c 100%); border-color: #bf360c; }

.ev-content { background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1; border-radius: 0 0 16px 16px; padding: 28px; min-height: 500px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px; }
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

/* ===== HERO ===== */
.ev-hero { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); color: white; padding: 28px; border-radius: 12px; margin-bottom: 20px; text-align: center; }
.ev-hero h2 { margin: 0 0 6px 0; font-size: 1.4rem; }
.ev-hero .subtitle { opacity: 0.9; font-size: 0.9rem; margin-bottom: 16px; }
.ev-search-wrap { display: flex; gap: 8px; max-width: 700px; margin: 0 auto 16px auto; }
.ev-search { flex: 1; padding: 14px 22px; border-radius: 30px; border: 2px solid rgba(255,255,255,0.3); background: rgba(255,255,255,0.15); color: white; font-size: 1rem; backdrop-filter: blur(4px); }
.ev-search::placeholder { color: rgba(255,255,255,0.7); }
.ev-search:focus { outline: none; border-color: #fff; background: rgba(255,255,255,0.25); }
.ev-btn { padding: 14px 22px; border-radius: 30px; border: none; font-size: 0.95rem; font-weight: 600; cursor: pointer; transition: all 0.2s; white-space: nowrap; }
.ev-btn.search { background: #4caf50; color: white; }
.ev-btn.search:hover { background: #45a049; }
.ev-btn.clear { background: rgba(255,255,255,0.2); color: white; border: 2px solid rgba(255,255,255,0.5); }
.ev-btn.clear:hover { background: rgba(255,255,255,0.3); }

/* ===== TABLES ===== */
.lkps-section { margin-bottom: 30px; }
.lkps-section h3 { color: #0d47a1; border-left: 4px solid #0d47a1; padding-left: 12px; margin-bottom: 12px; font-size: 1.1rem; }
.lkps-section h4 { color: #1565c0; margin: 16px 0 8px 0; font-size: 0.95rem; }
.table-responsive { overflow-x: auto; border: 1px solid #e0e0e0; border-radius: 8px; margin-bottom: 20px; }
.lkps-table { width: 100%; border-collapse: collapse; font-size: 0.82rem; min-width: 600px; }
.lkps-table th, .lkps-table td { border: 1px solid #e0e0e0; padding: 8px 10px; text-align: left; vertical-align: top; }
.lkps-table th { background-color: #f1f5f9; font-weight: 600; color: #0d47a1; position: sticky; top: 0; z-index: 1; }
.lkps-table tr:nth-child(even) { background-color: #f8fafc; }
.lkps-table tr:hover { background-color: #e3f2fd; }
.highlight-data { background-color: #fff8e1 !important; font-weight: 600; color: #e65100; }
.link-cell a { color: #0d47a1; text-decoration: none; word-break: break-all; font-weight: 600; }
.link-cell a:hover { text-decoration: underline; }

/* ===== SUMMARY CARDS ===== */
.summary-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 10px; margin: 16px 0; }
.summary-card { background: white; border: 1px solid #e0e0e0; border-left: 4px solid #0d47a1; border-radius: 8px; padding: 12px; }
.summary-card .sc-label { font-size: 0.72rem; color: #666; text-transform: uppercase; letter-spacing: 0.5px; }
.summary-card .sc-value { font-size: 1.4rem; font-weight: 800; color: #0d47a1; margin: 4px 0; }
.summary-card .sc-desc { font-size: 0.78rem; color: #555; }

/* ===== INFO BOX ===== */
.info-box { background: #e3f2fd; border-left: 4px solid #0d47a1; padding: 12px 16px; border-radius: 6px; margin-bottom: 20px; font-size: 0.88rem; color: #0d47a1; }
.info-box strong { color: #0a3a8a; }

/* ===== SUB NAV ===== */
.sub-nav { display: flex; gap: 4px; margin-bottom: 16px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
.sub-nav button { padding: 8px 14px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.82rem; }
.sub-nav button:hover { color: #0d47a1; background: #f8fafc; }
.sub-nav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }

@media (max-width: 767px) {
.ev-shelf { gap: 4px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
.ev-shelf::-webkit-scrollbar { display: none; }
.ev-tab { min-width: 90px; flex: 0 0 auto; font-size: 0.72rem; padding: 12px 6px 16px 6px; }
.ev-content { padding: 20px; }
.ev-search-wrap { flex-direction: column; }
.ev-btn { width: 100%; }
.summary-grid { grid-template-columns: 1fr 1fr; }
}
</style>

<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('beranda', this)">🏠<br>Beranda</div>
    <div class="ev-tab" onclick="showEvPanel('c1', this)">📑<br>C.1 VMTS</div>
    <div class="ev-tab" onclick="showEvPanel('c2', this)">🏛️<br>C.2 Tata Kelola</div>
    <div class="ev-tab" onclick="showEvPanel('c3', this)">📘<br>C.3 Diklitpmas</div>
    <div class="ev-tab" onclick="showEvPanel('c4', this)">👨‍<br>C.4 SDM</div>
    <div class="ev-tab" onclick="showEvPanel('c5', this)">💰<br>C.5 Sarpras</div>
    <div class="ev-tab" onclick="showEvPanel('c6', this)">🎓<br>C.6 Luaran</div>
    <div class="ev-tab" onclick="showEvPanel('c7', this)">🔄<br>C.7 SPMI</div>
  </div>

  <div class="ev-content">

    <!-- ========== BERANDA ========== -->
    <div class="ev-panel active" id="panel-beranda">
      <div class="ev-hero">
        <h2>📊 LKPS PSBM — Laporan Kinerja Program Studi</h2>
        <div class="subtitle">Seluruh tabel LKPS PSBM untuk Asesmen Lapangan — Akses 1-2 klik</div>
        <div class="ev-search-wrap">
          <input type="text" class="ev-search" id="evSearch" placeholder="🔎 Cari tabel, indikator, data..." onkeypress="if(event.key==='Enter') searchEv()">
          <button class="ev-btn search" onclick="searchEv()">🔍 Cari</button>
          <button class="ev-btn clear" onclick="clearEvSearch()">✖ Clear</button>
        </div>
      </div>

      <div id="evSearchResult"></div>

      <div id="defaultBeranda">
        <div class="info-box">
          <strong>ℹ️ Informasi:</strong> Halaman ini menampilkan <strong>seluruh tabel LKPS PSBM</strong> yang telah disubmit ke SAKTI. Data disajikan per kriteria dengan ringkasan dan link ke dokumen asli di Google Drive.
        </div>

        <h3 style="color:#0d47a1; margin: 20px 0 12px 0;">📋 Ringkasan Data Kunci LKPS</h3>
        <div class="summary-grid">
          <div class="summary-card">
            <div class="sc-label">Kerja Sama Tridharma</div>
            <div class="sc-value">66</div>
            <div class="sc-desc">42 Pendidikan + 17 Penelitian + 7 PkM</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">Mata Kuliah</div>
            <div class="sc-value">53 MK</div>
            <div class="sc-desc">150 SKS, 80 SKS Praktik (53,33%)</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">DTPS</div>
            <div class="sc-value">11 Dosen</div>
            <div class="sc-desc">3 Doktor (27,27%), 4 LK (36,36%)</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">Penelitian 3 Tahun</div>
            <div class="sc-value">45</div>
            <div class="sc-desc">14 → 13 → 18, 80% internal</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">PkM 3 Tahun</div>
            <div class="sc-value">14</div>
            <div class="sc-desc">2 → 6 → 6, 100% internal</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">Publikasi DTPS</div>
            <div class="sc-value">220</div>
            <div class="sc-desc">3 tahun terakhir</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">Produk Diadopsi DTPS</div>
            <div class="sc-value">13</div>
            <div class="sc-desc">Kekuatan luaran</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">Lulusan Terlacak</div>
            <div class="sc-value">61/80</div>
            <div class="sc-desc">76,25% tracer study</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">Kesesuaian Kerja</div>
            <div class="sc-value">70,49%</div>
            <div class="sc-desc">43/61 tingkat tinggi</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">Prestasi Mahasiswa</div>
            <div class="sc-value">19</div>
            <div class="sc-desc">10 akademik + 9 nonakademik</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">Publikasi Mahasiswa</div>
            <div class="sc-value">126</div>
            <div class="sc-desc">34 jurnal terakreditasi</div>
          </div>
          <div class="summary-card">
            <div class="sc-label">Produk Mahasiswa</div>
            <div class="sc-value">16</div>
            <div class="sc-desc">Diadopsi industri/masyarakat</div>
          </div>
        </div>

        <h3 style="color:#0d47a1; margin: 20px 0 12px 0;">️ Navigasi Tabel LKPS per Kriteria</h3>
        <div class="summary-grid">
          <div class="summary-card" onclick="showEvPanel('c1', document.querySelectorAll('.ev-tab')[1])" style="cursor:pointer;">
            <div class="sc-label"> C.1</div>
            <div class="sc-value" style="font-size:1rem;">VMTS</div>
            <div class="sc-desc">Tabel 1: Visi, Misi, Tujuan, Sasaran</div>
          </div>
          <div class="summary-card" onclick="showEvPanel('c2', document.querySelectorAll('.ev-tab')[2])" style="cursor:pointer;">
            <div class="sc-label">🏛️ C.2</div>
            <div class="sc-value" style="font-size:1rem;">Tata Kelola</div>
            <div class="sc-desc">Tabel 2a1, 2a2, 2a3, 2b</div>
          </div>
          <div class="summary-card" onclick="showEvPanel('c3', document.querySelectorAll('.ev-tab')[3])" style="cursor:pointer;">
            <div class="sc-label"> C.3</div>
            <div class="sc-value" style="font-size:1rem;">Diklitpmas</div>
            <div class="sc-desc">Tabel 3a1-5, 3b, 3c</div>
          </div>
          <div class="summary-card" onclick="showEvPanel('c4', document.querySelectorAll('.ev-tab')[4])" style="cursor:pointer;">
            <div class="sc-label">👨‍🏫 C.4</div>
            <div class="sc-value" style="font-size:1rem;">SDM</div>
            <div class="sc-desc">Tabel 4a-4k (11 tabel)</div>
          </div>
          <div class="summary-card" onclick="showEvPanel('c5', document.querySelectorAll('.ev-tab')[5])" style="cursor:pointer;">
            <div class="sc-label"> C.5</div>
            <div class="sc-value" style="font-size:1rem;">Sarpras & K3L</div>
            <div class="sc-desc">Tabel 5a, 5b, 5c</div>
          </div>
          <div class="summary-card" onclick="showEvPanel('c6', document.querySelectorAll('.ev-tab')[6])" style="cursor:pointer;">
            <div class="sc-label">🎓 C.6</div>
            <div class="sc-value" style="font-size:1rem;">Mahasiswa & Luaran</div>
            <div class="sc-desc">Tabel 6a-6i (15 tabel)</div>
          </div>
          <div class="summary-card" onclick="showEvPanel('c7', document.querySelectorAll('.ev-tab')[7])" style="cursor:pointer;">
            <div class="sc-label">🔄 C.7</div>
            <div class="sc-value" style="font-size:1rem;">SPMI</div>
            <div class="sc-desc">Tabel 7a, 7b</div>
          </div>
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
              <tr><th>No</th><th>Jenis VMTS</th><th>Pernyataan (Ringkasan)</th><th>No. SK</th><th>Link Dokumen</th></tr>
            </thead>
            <tbody>
              <tr><td>1</td><td><strong>VMTS PT</strong></td><td>Visi: Menjadi politeknik unggul bertaraf internasional. Misi: Pendidikan vokasi berbasis ipteks, penelitian, pengabdian, institusi efisien.</td><td>643/PL3/OT/2021</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1EGqnMf6ZPJ_skiJBP5tOCXhlCJiYKqPU?usp=drive_link" target="_blank">📂 Buka Folder</a></td></tr>
              <tr><td>2</td><td><strong>VMTS UPPS (JTE)</strong></td><td>Visi: Menjadi Jurusan Teknik Elektro unggul bertaraf internasional. 10 sasaran strategis.</td><td>2585/PL3/OT/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1JiRWv_v_-pbrFTMl74JwQzJ1ZNnCpcOt?usp=drive_link" target="_blank">📂 Buka Folder</a></td></tr>
              <tr><td>3</td><td><strong>Visi Keilmuan PS</strong></td><td>Menjadi program studi unggul bertaraf internasional di bidang broadband multimedia.</td><td>2589/PL3/KR.00/2020</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kEN_2TU9W6vch8kkKwB0qG83rU89ujxf?usp=sharing" target="_blank"> Buka Folder</a></td></tr>
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
          <div class="summary-card"><div class="sc-label">Total</div><div class="sc-value">42</div></div>
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
              <tr><td>7</td><td>PT Eka Mas Republik (My Republik)</td><td>Nasional</td><td>Training Fiber Optik, Magang</td><td>2 tahun</td><td>Valid</td></tr>
              <tr><td>8</td><td>PT Nippon Electronic Company (NEC)</td><td>Internasional</td><td>Training Microwave</td><td>—</td><td>Valid</td></tr>
              <tr><td>9</td><td>BRIN</td><td>Nasional</td><td>Magang Mahasiswa</td><td>—</td><td>Valid</td></tr>
              <tr><td>10</td><td>Bank Rakyat Indonesia</td><td>Nasional</td><td>Kuliah Umum</td><td>—</td><td>Valid</td></tr>
            </tbody>
          </table>
        </div>
        <p style="font-size:0.85rem; color:#666;">* Menampilkan 10 dari 42 kerja sama pendidikan. <a href="#" onclick="alert('Link ke folder Google Drive Tabel 2a1')">Lihat semua di Google Drive →</a></p>
      </div>

      <div class="lkps-section">
        <h3>🏛️ C.2 — Tabel 2a2: Kerja Sama Penelitian (17)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">1</div></div>
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">16</div></div>
          <div class="summary-card"><div class="sc-label">Total</div><div class="sc-value">17</div></div>
        </div>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Lembaga Mitra</th><th>Judul Kegiatan</th><th>Durasi</th><th>Status</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Telkom University Purwokerto</td><td>Penelitian Bersama</td><td>3 tahun</td><td>Valid</td></tr>
              <tr><td>2</td><td>Politeknik Caltex Riau</td><td>Hibah BIMA 2025</td><td>—</td><td>Valid</td></tr>
              <tr><td>3</td><td>Politeknik Negeri Ujung Pandang</td><td>Hibah BIMA 2025</td><td>—</td><td>Valid</td></tr>
              <tr><td>4</td><td>PT Kekar Karya Indonesia</td><td>Hibah BIMA 2025</td><td>—</td><td>Valid</td></tr>
              <tr><td>5</td><td>PT Floatway System</td><td>Matching Fund 2023</td><td>1 tahun</td><td>Valid</td></tr>
              <tr><td>6</td><td>PT Telkomsel Indonesia</td><td>Penelitian Bersama + Matching Fund</td><td>5 tahun</td><td>Valid</td></tr>
              <tr><td>7</td><td>PT Eka Mas Republik</td><td>Penelitian Bersama</td><td>—</td><td>Valid</td></tr>
              <tr><td>8</td><td>PT NEC</td><td>Matching Fund 2023</td><td>—</td><td>Valid</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🏛️ C.2 — Tabel 2a3: Kerja Sama PkM (7)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">1</div></div>
          <div class="summary-card"><div class="sc-label">Lokal/Wilayah</div><div class="sc-value">6</div></div>
          <div class="summary-card"><div class="sc-label">Total</div><div class="sc-value">7</div></div>
        </div>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Lembaga Mitra</th><th>Judul Kegiatan</th><th>Status</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Kementerian Sosial RI</td><td>Sistem Informasi OJT Masyarakat</td><td>Valid</td></tr>
              <tr><td>2</td><td>Balai Benih Ikan Ciganjur</td><td>Smart Aquaculture Berbasis LoRa</td><td>Valid</td></tr>
              <tr><td>3</td><td>Kelurahan Beji Timur</td><td>Sistem Keamanan Lingkungan IoT</td><td>Valid</td></tr>
              <tr><td>4</td><td>Kampung Proklim Beji Timur</td><td>Aplikasi Bank Sampah</td><td>Valid</td></tr>
              <tr><td>5</td><td>Kelurahan Beji Timur</td><td>Pengembangan Kompetensi Digital</td><td>Valid</td></tr>
              <tr><td>6</td><td>Kampung Setaman Cipayung</td><td>Website Desa Wisata</td><td>Valid</td></tr>
              <tr><td>7</td><td>SMP Islam Nusantara</td><td>Web Sekolah & Sistem Pemantauan</td><td>Valid</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>️ C.2 — Tabel 2b: Penggunaan Dana (Rupiah)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Jenis Penggunaan</th><th>UPPS TS-2</th><th>UPPS TS-1</th><th>UPPS TS</th><th>UPPS Rata-rata</th><th>PS TS-2</th><th>PS TS-1</th><th>PS TS</th><th>PS Rata-rata</th></tr></thead>
            <tbody>
              <tr><td>1</td><td><strong>Biaya Operasional Pendidikan</strong></td><td colspan="4"></td><td colspan="4"></td></tr>
              <tr><td></td><td>a. Biaya Dosen</td><td>10,37 M</td><td>11,72 M</td><td>12,40 M</td><td>11,50 M</td><td>1,57 M</td><td>1,74 M</td><td>1,80 M</td><td>1,71 M</td></tr>
              <tr><td></td><td>b. Biaya Tendik</td><td>1,18 M</td><td>0,89 M</td><td>3,27 M</td><td>1,78 M</td><td>0,18 M</td><td>0,13 M</td><td>0,47 M</td><td>0,26 M</td></tr>
              <tr><td></td><td>c. Biaya Operasional Pembelajaran</td><td>6,73 M</td><td>6,88 M</td><td>5,86 M</td><td>6,49 M</td><td>1,02 M</td><td>1,02 M</td><td>0,85 M</td><td>0,96 M</td></tr>
              <tr><td></td><td>d. Biaya Tidak Langsung</td><td>2,31 M</td><td>2,04 M</td><td>1,99 M</td><td>2,12 M</td><td>0,35 M</td><td>0,30 M</td><td>0,29 M</td><td>0,31 M</td></tr>
              <tr><td></td><td>f. Biaya Investasi</td><td>4,58 M</td><td>3,42 M</td><td>2,42 M</td><td>3,47 M</td><td>0,69 M</td><td>0,51 M</td><td>0,35 M</td><td>0,52 M</td></tr>
              <tr><td>2</td><td><strong>Biaya Kemahasiswaan</strong></td><td>0,51 M</td><td>0,71 M</td><td>0,13 M</td><td>0,45 M</td><td>0,07 M</td><td>0,10 M</td><td>0,01 M</td><td>0,06 M</td></tr>
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
        <div class="info-box"><strong>📌 Catatan:</strong> Seluruh 53 MK memiliki RPS. Kurikulum dievaluasi pada 2020, 2021, dan 2024. Integrasi penelitian/PkM ≥10% MK inti.</div>
      </div>

      <div class="lkps-section">
        <h3>📘 C.3 — Tabel 3a3: Integrasi Penelitian/PkM dalam Pembelajaran</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Nama Dosen</th><th>Judul Penelitian/PkM</th><th>Mata Kuliah</th><th>Bentuk Integrasi</th><th>Tahun</th><th>Sesuai Roadmap</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Dandun Widhiantoro</td><td>CCTV Desa Wisata Kampung Setaman</td><td>Keamanan & Kehandalan Jaringan</td><td>Studi Kasus</td><td>TS</td><td>Sesuai</td></tr>
              <tr><td>2</td><td>Agus Wagyana</td><td>Indoor Positioning System ZigBee</td><td>Sistem Mikrokontroler</td><td>Bahan Ajar</td><td>TS-1</td><td>Sesuai</td></tr>
              <tr><td>3</td><td>Viving Frendiana</td><td>Sistem Keamanan IoT Beji Timur</td><td>Aplikasi Bergerak</td><td>Studi Kasus</td><td>TS</td><td>Sesuai</td></tr>
              <tr><td>4</td><td>Mohamad Fathurahman</td><td>Smart Aquaculture LoRa</td><td>Komputasi Pervasive</td><td>Bahan Ajar</td><td>TS</td><td>Sesuai</td></tr>
              <tr><td>5</td><td>Zulhelman</td><td>Antena MIMO 5G</td><td>Komunikasi Data</td><td>Bahan Ajar</td><td>TS</td><td>Sesuai</td></tr>
              <tr><td>6</td><td>Asri Wulandari</td><td>Integrated Telecom Lab</td><td>Sistem Komunikasi Seluler 2</td><td>Tambahan Materi</td><td>TS-2</td><td>Sesuai</td></tr>
              <tr><td>7</td><td>Asri Wulandari</td><td>Private 5G Network Jababeka</td><td>Jaringan Komunikasi Broadband</td><td>Tambahan Materi</td><td>TS-1</td><td>Sesuai</td></tr>
              <tr><td>8</td><td>Shita Herfiah</td><td>NTN-Geo Satellite 4G/5G</td><td>Komunikasi Radio & Satelit</td><td>Tambahan Materi</td><td>TS</td><td>Sesuai</td></tr>
            </tbody>
          </table>
        </div>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Dosen Terlibat</div><div class="sc-value">8</div></div>
          <div class="summary-card"><div class="sc-label">Judul Penelitian/PkM</div><div class="sc-value">8</div></div>
          <div class="summary-card"><div class="sc-label">MK Terintegrasi</div><div class="sc-value">8</div></div>
          <div class="summary-card"><div class="sc-label">Sesuai Roadmap</div><div class="sc-value">8 (100%)</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>📘 C.3 — Tabel 3a4: Basic Sciences & Matematika (8 SKS)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Nama Mata Kuliah</th><th>Semester</th><th>SKS</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Matematika Dasar</td><td>1</td><td>2</td></tr>
              <tr><td>2</td><td>Medan Elektromagnetik</td><td>2</td><td>2</td></tr>
              <tr><td>3</td><td>Matematika 2</td><td>2</td><td>2</td></tr>
              <tr><td>4</td><td>Matematika Teknik</td><td>3</td><td>2</td></tr>
            </tbody>
            <tfoot><tr style="background:#f1f5f9; font-weight:700;"><td colspan="3">Total SKS Basic Sciences</td><td>8</td></tr></tfoot>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>📘 C.3 — Tabel 3a5: Capstone Design (Skripsi, 10 SKS)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>MK Pendukung</th><th>SKS</th><th>Capstone</th><th>SKS</th><th>Semester</th></tr></thead>
            <tbody>
              <tr><td colspan="5" style="background:#f1f5f9; font-weight:700;">24 MK pendukung + Magang Industri (20 SKS) → Skripsi (10 SKS) di Semester 8</td></tr>
              <tr><td colspan="5"><strong>Cakupan Bahasan:</strong> a) Perancangan & optimasi jaringan telekomunikasi, b) Perancangan & fabrikasi RF/antena, c) Pengolahan sinyal digital & sistem mikrokontroler, d) Pengembangan aplikasi bergerak & komputasi awan, e) Manajemen proyek rekayasa, f) Integrasi magang industri ke permasalahan rekayasa.</td></tr>
            </tbody>
          </table>
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
        <h3>👨‍🏫 C.4 — Tabel 4a: Profil DTPS (11 Dosen)</h3>
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
        <h3>👨🏫 C.4 — Tabel 4b: Tenaga Kependidikan (8 orang)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Nama</th><th>Pendidikan Terakhir</th><th>Sertifikat Kompetensi</th><th>Unit Kerja</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Vida Farida Damayanti</td><td>D3</td><td>IoT Networking</td><td>Program Studi</td></tr>
              <tr><td>2</td><td>Achmad</td><td>D3</td><td>Teknisi Instrumentasi</td><td>UPPS</td></tr>
              <tr><td>3</td><td>Agus Setiawan</td><td>S1</td><td>Junior Network Admin</td><td>Program Studi</td></tr>
              <tr><td>4</td><td>Riri Octaviani</td><td>S1</td><td>Pelaksana Utama Tegangan Rendah</td><td>UPPS</td></tr>
              <tr><td>5</td><td>Illa Nurabika</td><td>D3</td><td>Network Admin, K3 Muda, P3K</td><td>UPPS</td></tr>
              <tr><td>6</td><td>Hari Surahman</td><td>S1</td><td>Network Engineer</td><td>Program Studi</td></tr>
              <tr><td>7</td><td>Iing Ibrahim</td><td>SMA/SMK</td><td>—</td><td>Program Studi</td></tr>
              <tr><td>8</td><td>Ilham Yanuar</td><td>D3</td><td>Pelaksana Utama Tegangan Rendah</td><td>UPPS</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>👨‍🏫 C.4 — Tabel 4c: Beban Kerja DTPS (RBK 14,77 SKS)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Nama Dosen</th><th>DTPS</th><th>Mengajar PS Diakreditasi</th><th>Mengajar PS Lain</th><th>Penelitian</th><th>PkM</th><th>Tugas Tambahan</th><th>Total/Tahun</th><th>Total/Semester</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Dr. Isdawimah</td><td>✓</td><td>2</td><td>14,9</td><td>1,91</td><td>5</td><td>2,5</td><td>26,685</td><td>13,34</td></tr>
              <tr><td>2</td><td>Nana Sutarna</td><td>✓</td><td>3</td><td>8,25</td><td>11</td><td>4</td><td>1,25</td><td>27,775</td><td>13,89</td></tr>
              <tr><td>3</td><td>Mera Kartika</td><td>✓</td><td>3</td><td>10,3</td><td>12</td><td>3</td><td>3</td><td>31,066</td><td>15,53</td></tr>
              <tr><td>4</td><td>Zulhelman</td><td>✓</td><td>22</td><td>0</td><td>4</td><td>4,1</td><td>1,5</td><td>32</td><td>15,75</td></tr>
              <tr><td>5</td><td>Agus Wagyana</td><td>✓</td><td>12</td><td>11</td><td>3</td><td>2,35</td><td>0,75</td><td>29,115</td><td>14,56</td></tr>
              <tr><td>6</td><td>Asri Wulandari</td><td>✓</td><td>15,75</td><td>4</td><td>5</td><td>2,25</td><td>2,5</td><td>29,821</td><td>14,91</td></tr>
              <tr><td>7</td><td>Dandun Widhiantoro</td><td>✓</td><td>22</td><td>0</td><td>2</td><td>4</td><td>1</td><td>29</td><td>14,33</td></tr>
              <tr><td>8</td><td>Mohamad Fathurahman</td><td>✓</td><td>24</td><td>0</td><td>1</td><td>4,35</td><td>0,875</td><td>31</td><td>15,29</td></tr>
              <tr><td>9</td><td>Viving Frendiana</td><td>✓</td><td>19,95</td><td>0</td><td>5,4</td><td>2,75</td><td>3</td><td>31,1</td><td>15,55</td></tr>
              <tr><td>10</td><td>Toto Supriyanto</td><td>✓</td><td>3</td><td>21,5</td><td>1</td><td>3</td><td>2</td><td>30,65</td><td>15,33</td></tr>
              <tr><td>11</td><td>Shita Herfiah</td><td>✓</td><td>18,65</td><td>4</td><td>2</td><td>2,15</td><td>0,75</td><td>27,985</td><td>13,99</td></tr>
            </tbody>
            <tfoot><tr class="highlight-data"><td colspan="7"><strong>Rata-rata Beban Kerja (RBK)</strong></td><td colspan="3"><strong>14,77 SKS/semester</strong></td></tr></tfoot>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>👨🏫 C.4 — Tabel 4e: Publikasi DTPS (220 total)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Jurnal Nasional Terakreditasi</div><div class="sc-value">73</div></div>
          <div class="summary-card"><div class="sc-label">Jurnal Internasional Bereputasi</div><div class="sc-value">12</div></div>
          <div class="summary-card"><div class="sc-label">Prosiding Nasional</div><div class="sc-value">92</div></div>
          <div class="summary-card"><div class="sc-label">Prosiding Scopus/WoS</div><div class="sc-value">33</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">TOTAL</div><div class="sc-value">220</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>👨🏫 C.4 — Tabel 4f: Luaran DTPS</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Paten</div><div class="sc-value">3</div></div>
          <div class="summary-card"><div class="sc-label">HKI (Hak Cipta)</div><div class="sc-value">36</div></div>
          <div class="summary-card"><div class="sc-label">Teknologi Tepat Guna</div><div class="sc-value">4</div></div>
          <div class="summary-card"><div class="sc-label">Buku/Book Chapter</div><div class="sc-value">14</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>👨‍🏫 C.4 — Tabel 4g: Produk/Jasa DTPS Diadopsi (13)</h3>
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

      <div class="lkps-section">
        <h3>👨‍🏫 C.4 — Tabel 4h: Karya Ilmiah DTPS Disitasi (20 karya, 6 dosen)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Total Karya Disitasi</div><div class="sc-value">94</div></div>
          <div class="summary-card"><div class="sc-label">Dosen Memiliki Karya</div><div class="sc-value">6</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>👨🏫 C.4 — Tabel 4j: Rekognisi DTPS (43 rekognisi)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Total Rekognisi</div><div class="sc-value">43</div></div>
          <div class="summary-card"><div class="sc-label">DTPS dengan Rekognisi</div><div class="sc-value">0</div></div>
        </div>
        <div class="info-box"><strong>️ Catatan:</strong> Data LKPS menunjukkan NR (Nasional Rekognisi) = 43, NRDTPS = 0. Perlu klarifikasi lebih lanjut.</div>
      </div>
    </div>

    <!-- ========== C.5 SARPRAS ========== -->
    <div class="ev-panel" id="panel-c5">
      <div class="lkps-section">
        <h3>💰 C.5 — Tabel 5a: Prasarana & Peralatan Utama</h3>
        <div class="info-box"><strong>📌 Ringkasan:</strong> 16 prasarana utama (13 lab/ruang + 3 layanan nonakademik). Seluruhnya terawat, dimiliki sendiri. Lihat tabel lengkap di tab C.5.</div>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Nama Sarana</th><th>Jumlah</th><th>Standar Minimal</th><th>Dimiliki</th><th>Terawat</th><th>Rata-rata Jam/Minggu</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Lab Elektronika Analog & Digital (G102)</td><td>1</td><td>Power Supply RIGOL: 6</td><td>8</td><td>✓</td><td>16</td></tr>
              <tr><td>2</td><td>Lab Sistem Transmisi (G103)</td><td>1</td><td>U Patch Panel: 6</td><td>8</td><td>✓</td><td>12</td></tr>
              <tr><td>3</td><td>Lab Sistem Telekomunikasi (G104)</td><td>1</td><td>Function Generator: 3</td><td>4</td><td>✓</td><td>18</td></tr>
              <tr><td>4</td><td>Lab Mikrokontroler (G105)</td><td>1</td><td>Meja Kayu: 11</td><td>11</td><td>✓</td><td>32</td></tr>
              <tr><td>5</td><td>Ruang Penyimpanan Alat (G106)</td><td>1</td><td>Lemari Besi: 5</td><td>5</td><td>✓</td><td>40</td></tr>
              <tr><td>6</td><td>Lab Komunikasi Data & Serat Optik (G108)</td><td>1</td><td>Meja Praktikum: 6</td><td>10</td><td>✓</td><td>12</td></tr>
              <tr><td>7</td><td>Lab Jaringan Broadband (G110)</td><td>1</td><td>Meja Praktikum: 12</td><td>12</td><td>✓</td><td>16</td></tr>
              <tr><td>8</td><td>Bengkel Elektronika (G115)</td><td>1</td><td>Bor Duduk: 2</td><td>2</td><td>✓</td><td>12</td></tr>
              <tr><td>9</td><td>Smartlab (G303)</td><td>1</td><td>Raspberry Pi 400: 12</td><td>13</td><td>✓</td><td>8</td></tr>
              <tr><td>10</td><td>Layanan Kesehatan</td><td>1</td><td>Meja: 3</td><td>3</td><td>✓</td><td>40</td></tr>
              <tr><td>11</td><td>Layanan Konseling</td><td>1</td><td>Meja: 3</td><td>3</td><td>✓</td><td>30</td></tr>
              <tr><td>12</td><td>Masjid Darul Ilmi</td><td>1</td><td>Meja: 2</td><td>2</td><td>✓</td><td>80</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>💰 C.5 — Tabel 5b: Dokumen K3L (17 dokumen)</h3>
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
        <h3>🎓 C.6 — Tabel 6a: Jumlah Mahasiswa (189 aktif TS)</h3>
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
        <h3>🎓 C.6 — Tabel 6c1: Prestasi Akademik (10)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">2</div></div>
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">8</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">10</div></div>
        </div>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Nama Kegiatan</th><th>Tanggal</th><th>Tingkat</th><th>Prestasi</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Cisco APJC NetAcad Riders 2024</td><td>26/3/2024</td><td>Internasional</td><td>Juara 2 (Silver)</td></tr>
              <tr><td>2</td><td>Cisco APJC NetAcad Riders 2024</td><td>26/3/2024</td><td>Internasional</td><td>Juara 3 (Bronze)</td></tr>
              <tr><td>3</td><td>Tech Enthusiast Day 2021</td><td>2/11/2021</td><td>Nasional</td><td>Juara 1</td></tr>
              <tr><td>4</td><td>NETCOMP 2022</td><td>9/8/2022</td><td>Nasional</td><td>Juara 2</td></tr>
              <tr><td>5</td><td>E-TIME 2022</td><td>25/7/2022</td><td>Nasional</td><td>Juara 3</td></tr>
              <tr><td>6</td><td>E-TIME 2023</td><td>27/7/2023</td><td>Nasional</td><td>Juara 1</td></tr>
              <tr><td>7</td><td>IONIC 2023</td><td>24/11/2023</td><td>Nasional</td><td>Juara 2</td></tr>
              <tr><td>8</td><td>Networking Competition TED 2021</td><td>11/12/2021</td><td>Nasional</td><td>Juara 1</td></tr>
              <tr><td>9</td><td>IONIC 2023</td><td>25/11/2023</td><td>Nasional</td><td>Juara 2</td></tr>
              <tr><td>10</td><td>NETCOMP 2024</td><td>4/2/2024</td><td>Nasional</td><td>Finalis</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6c2: Prestasi Nonakademik (9)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Internasional</div><div class="sc-value">1</div></div>
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">5</div></div>
          <div class="summary-card"><div class="sc-label">Wilayah</div><div class="sc-value">3</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">9</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6d: Masa Studi Lulusan</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>Tahun Masuk</th><th>Jumlah Masuk</th><th>3,5 &lt; MS ≤ 4,5</th><th>4,5 &lt; MS ≤ 5,5</th><th>5,5 &lt; MS ≤ 6,5</th><th>6,5 &lt; MS ≤ 8</th></tr></thead>
            <tbody>
              <tr><td>TS-7</td><td>41</td><td>39</td><td>2</td><td>0</td><td>0</td></tr>
              <tr><td>TS-6</td><td>42</td><td>39</td><td>3</td><td>0</td><td>0</td></tr>
              <tr><td>TS-5</td><td>43</td><td>42</td><td>1</td><td>0</td><td>—</td></tr>
              <tr><td>TS-4</td><td>38</td><td>36</td><td>2</td><td>—</td><td>—</td></tr>
              <tr><td>TS-3</td><td>47</td><td>43</td><td>—</td><td>—</td><td>—</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6e2: Publikasi Mahasiswa (126)</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Jurnal Nasional Terakreditasi</div><div class="sc-value">34</div></div>
          <div class="summary-card"><div class="sc-label">Jurnal Internasional Bereputasi</div><div class="sc-value">1</div></div>
          <div class="summary-card"><div class="sc-label">Prosiding Nasional</div><div class="sc-value">91</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Total</div><div class="sc-value">126</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6e3: Luaran Mahasiswa</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">HKI (Hak Cipta)</div><div class="sc-value">16</div></div>
          <div class="summary-card"><div class="sc-label">Teknologi Tepat Guna</div><div class="sc-value">1</div></div>
          <div class="summary-card"><div class="sc-label">Buku/Book Chapter</div><div class="sc-value">2</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6e4: Produk/Jasa Mahasiswa Diadopsi (16)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Nama Mahasiswa</th><th>Nama Produk/Jasa</th><th>Link Bukti</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Algifri Prayudha dkk (10 mhs)</td><td>Web Sekolah & Sistem Pemantauan KBM</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1gj3fyC_mO2c6pDTNRzhnlPcIE4_pKBYS?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>2</td><td>Muhammad Zaki Raya dkk (3 mhs)</td><td>Website Desa Wisata Kampung Setaman</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/10Uedbfz4neHCLzH0gVGHO46a18iBY_Sn?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>3</td><td>Adrian Eka Ramadhani dkk (4 mhs)</td><td>Pelatihan Kompetensi Digital Beji Timur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1_bRTrD7Biee4s4TWA7hixSnR6tAUoEs6?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>4</td><td>Bemi Raihan R dkk (3 mhs)</td><td>Aplikasi Bank Sampah "Bersih Plus"</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kOYXp1Zto8t7KmGOKmEyXLlYZgm0986E?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>5</td><td>Nabilla Farassaskya Zanna</td><td>Sistem Informasi OJT Kemensos RI</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1RtCF0v8ZWTKRa554t-tfHOazMMd1bJ-3?usp=sharing" target="_blank"> Buka</a></td></tr>
              <tr><td>6</td><td>Ilham Satria Lubis dkk (3 mhs)</td><td>Smart Aquaculture LoRa BBI Ciganjur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1sbQtwzrJmOYN8MMsVykxXJMIsNnvWPE4?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>7</td><td>Annisa Octaviani dkk (3 mhs)</td><td>Sistem Keamanan IoT Beji Timur (E-RT 01)</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1jOUQDJJjgd0QhcgX3RgIchbhu01FsJLf?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>8</td><td>Farhan Yuswa Bianto</td><td>Peduli PMI - Sistem Informasi PMI Malaysia</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1J7Mgq_AIQYyJtKua0u6g3ZuVFpMV1H22?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>9</td><td>Muhammad Djapar</td><td>Website Admin Chatbot & Voicebot Kejaksaan Agung</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1znsjt7VPRsWNueWmNr3LXIpes6v8OdPW?usp=sharing" target="_blank"> Buka</a></td></tr>
              <tr><td>10</td><td>Daniel Bastian Muhammad</td><td>Monitoring Jaringan & Automasi Router Ansible</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1Tmf7vbxX6Gfj8PhHIPZMPJJRRdqwPVDl?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>11</td><td>Fransisca Liany Zahara</td><td>Antena Mikrostrip Array Dual Band 2.4/5.8 GHz</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1lol99_4PBBxleQ-4aMl6Gq_ek6zsfwrI?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>12</td><td>Salsya Nur'Alfienda</td><td>Website Administrasi Bank Sampah Beji Timur</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1My3a8RALVQHqucIVGpKiPpD2Vx0li5X0?usp=sharing" target="_blank"> Buka</a></td></tr>
              <tr><td>13</td><td>Dhaniya Prameswari</td><td>Antena Quasi Yagi Peredam Wi-Fi</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1kGTnCs1DYVna53dUfmn_YcYFJS34OxFR?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>14</td><td>Juan Hafidz Segara</td><td>Monitoring Hidroponik IoT Tenaga Surya</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1GQBHpFVUq9rUmo_Ns-58c5D0NwPZShqG?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>15</td><td>Muhammad Hakim Ramadhan</td><td>Pemantau Suhu Mesin Roasting + Telegram</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1XLIlRTGU5Uv1_YxJoinC7tsF92ilxLd9?usp=sharing" target="_blank">📂 Buka</a></td></tr>
              <tr><td>16</td><td>Andika Yulyan Chandra</td><td>Automasi Backup VM & Konfigurasi Jaringan ISP</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/114zDOiBkoPpkiyszmO_PzwQX-bLdQtcI?usp=sharing" target="_blank"> Buka</a></td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6f1: Waktu Tunggu Lulusan</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Total Lulusan</div><div class="sc-value">80</div></div>
          <div class="summary-card"><div class="sc-label">Terlacak</div><div class="sc-value">61 (76,25%)</div></div>
          <div class="summary-card"><div class="sc-label">WT &lt; 3 bulan</div><div class="sc-value">34 (55,74%)</div></div>
          <div class="summary-card"><div class="sc-label">WT 3-18 bulan</div><div class="sc-value">27 (44,26%)</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">WT &gt; 18 bulan</div><div class="sc-value">0</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6f2: Kesesuaian Bidang Kerja</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Tinggi</div><div class="sc-value">43 (70,49%)</div></div>
          <div class="summary-card"><div class="sc-label">Sedang</div><div class="sc-value">11 (18,03%)</div></div>
          <div class="summary-card"><div class="sc-label">Rendah</div><div class="sc-value">7 (11,48%)</div></div>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6g1: Tempat Kerja Lulusan</h3>
        <div class="summary-grid">
          <div class="summary-card"><div class="sc-label">Lokal/Wilayah</div><div class="sc-value">12</div></div>
          <div class="summary-card"><div class="sc-label">Nasional</div><div class="sc-value">39</div></div>
          <div class="summary-card"><div class="sc-label">Multinasional/Internasional</div><div class="sc-value">10</div></div>
          <div class="summary-card highlight-data"><div class="sc-label">Nasional + Multinasional</div><div class="sc-value">49/61 (80,33%)</div></div>
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

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6h1: Penelitian DTPS Melibatkan Mahasiswa (12/45 = 26,67%)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Dosen</th><th>Tema</th><th>Mahasiswa</th><th>Judul Kegiatan</th><th>Tahun</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Zulhelman</td><td>Antena MIMO 5G</td><td>Muhammad Roby, Reza Pratama</td><td>Perancangan</td><td>2025</td></tr>
              <tr><td>2</td><td>Agus Wagyana</td><td>Ultra Wideband</td><td>Andafa, Ahmad Rifai</td><td>Kegiatan Lain</td><td>2023</td></tr>
              <tr><td>3</td><td>Agus Wagyana</td><td>Indoor Positioning ZigBee</td><td>Andafa, Ahmad Rifai</td><td>Kegiatan Lain</td><td>2024</td></tr>
              <tr><td>4</td><td>Agus Wagyana</td><td>AR untuk IoT</td><td>Purbo, Muhamad Reza</td><td>Kegiatan Lain</td><td>2025</td></tr>
              <tr><td>5</td><td>Asri Wulandari</td><td>Private 5G Jababeka</td><td>Akita, Raviadin</td><td>Kegiatan Lain</td><td>2023</td></tr>
              <tr><td>6</td><td>Asri Wulandari</td><td>5G FWA Alam Sutera</td><td>Ahmad Rifai, Andafa</td><td>Perancangan</td><td>2025</td></tr>
              <tr><td>7</td><td>Mohamad Fathurahman</td><td>Computer Vision</td><td>Adi Ageng, Erian</td><td>Tugas Akhir</td><td>2023</td></tr>
              <tr><td>8</td><td>Mohamad Fathurahman</td><td>Gateway LoRa</td><td>Muhammad Zaki</td><td>Kegiatan Lain</td><td>2025</td></tr>
              <tr><td>9</td><td>Viving Frendiana</td><td>SHA1/MD5/SHA-256</td><td>Muhammad Djapar, Hikam</td><td>Perancangan</td><td>2023</td></tr>
              <tr><td>10</td><td>Viving Frendiana</td><td>Flutter PjBL</td><td>Ahmad Rifai, Andafa, Muhammad Rizky</td><td>Perancangan</td><td>2024</td></tr>
              <tr><td>11</td><td>Viving Frendiana</td><td>Cloud GCP</td><td>Desi, Fadli, Poundra</td><td>Perancangan</td><td>2025</td></tr>
              <tr><td>12</td><td>Asri Wulandari</td><td>NTN-Geo Satellite</td><td>Faiz, Andafa</td><td>Perancangan</td><td>2025</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="lkps-section">
        <h3>🎓 C.6 — Tabel 6i: PkM DTPS Melibatkan Mahasiswa (7)</h3>
        <div class="table-responsive">
          <table class="lkps-table">
            <thead><tr><th>No</th><th>Dosen</th><th>Tema</th><th>Mahasiswa</th><th>Judul PkM</th><th>Tahun</th></tr></thead>
            <tbody>
              <tr><td>1</td><td>Viving Frendiana</td><td>Aplikasi Web</td><td>Muhammad Zaki, Andafa, Adinda</td><td>Website Desa Wisata Kampung Setaman</td><td>2023</td></tr>
              <tr><td>2</td><td>Viving Frendiana</td><td>Cloud Computing</td><td>Adrian, Ananda, Rakesh, Daffa</td><td>Pelatihan Kompetensi Digital Beji Timur</td><td>2024</td></tr>
              <tr><td>3</td><td>Asri Wulandari</td><td>Aplikasi Web & Mobile</td><td>Bemi, Salma, Angellia</td><td>Aplikasi Bank Sampah Beji Timur</td><td>2024</td></tr>
              <tr><td>4</td><td>Zulhelman</td><td>Aplikasi Web</td><td>Nabilla</td><td>Sistem Informasi OJT Kemensos</td><td>2025</td></tr>
              <tr><td>5</td><td>Mohamad Fathurahman</td><td>IoT & Mobile</td><td>Ilham, Emil, Mohammad Reza</td><td>Smart Aquaculture LoRa</td><td>2025</td></tr>
              <tr><td>6</td><td>Viving Frendiana</td><td>IoT & Mobile</td><td>Annisa, Fachma, Muhamad Reza</td><td>Sistem Keamanan IoT Beji Timur</td><td>2025</td></tr>
              <tr><td>7</td><td>Asri Wulandari</td><td>Aplikasi Web & Mobile</td><td>Farhan</td><td>Information System PMI Malaysia</td><td>2024</td></tr>
            </tbody>
          </table>
        </div>
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
              <tr><td>1</td><td>Kebijakan SPMI</td><td>SM/PNJ/SPMI/342</td><td>18/1/2022</td></tr>
              <tr><td>2</td><td>Pedoman PPEPP</td><td>KM/PNJ/SPMI/212</td><td>18/1/2022</td></tr>
              <tr><td>3</td><td>Standar Mutu</td><td>SM/PNJ/SPMI/311</td><td>20/1/2022</td></tr>
              <tr><td>4</td><td>Tata Cara Pendokumentasian</td><td>KM/PNJ/SPMI/215</td><td>20/1/2022</td></tr>
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
              <tr><td>2</td><td><strong>Pelaksanaan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S?usp=drive_link" target="_blank"> Buka</a></td><td>—</td><td>—</td><td>—</td></tr>
              <tr><td>3</td><td><strong>Evaluasi</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1ywPn4RexBzQjD6DXRT8DCXTEtemvcQLz?usp=sharing" target="_blank">📂 Buka</a></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2?usp=sharing" target="_blank">📂 Buka</a></td><td>—</td><td>—</td></tr>
              <tr><td>4</td><td><strong>Pengendalian</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1WFgIamM3JnSGZ-WAv-UOC1W22E0ondmV?usp=sharing" target="_blank">📂 Buka</a></td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0?usp=sharing" target="_blank"> Buka</a></td><td>—</td></tr>
              <tr><td>5</td><td><strong>Peningkatan</strong></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0?usp=sharing" target="_blank"> Buka</a></td><td>—</td><td>—</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0?usp=sharing" target="_blank">📂 Buka</a></td></tr>
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

// ===== SEARCH =====
function searchEv() {
  const query = document.getElementById('evSearch').value.toLowerCase().trim();
  const container = document.getElementById('evSearchResult');
  const defaultView = document.getElementById('defaultBeranda');

  if (!query) {
    container.innerHTML = '';
    defaultView.style.display = 'block';
    return;
  }
  defaultView.style.display = 'none';

  // Pencarian sederhana - tampilkan pesan
  container.innerHTML = '<div class="info-box"><strong>🔍 Hasil Pencarian:</strong> Anda mencari "<strong>' + query + '</strong>". Gunakan navigasi tab di atas untuk melihat tabel LKPS per kriteria, atau gunakan Ctrl+F di browser untuk mencari teks spesifik.</div>';
}

function clearEvSearch() {
  document.getElementById('evSearch').value = '';
  document.getElementById('evSearchResult').innerHTML = '';
  document.getElementById('defaultBeranda').style.display = 'block';
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  console.log('Evidence AL LKPS loaded successfully');
});
</script>

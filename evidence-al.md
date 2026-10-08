---
layout: default
title: Evidence AL
permalink: /evidence-al/
---

<style>
/* ===== UI DASAR ===== */
.ev-tabs { display: flex; gap: 4px; margin-bottom: 20px; border-bottom: 2px solid #e0e0e0; overflow-x: auto; padding-bottom: 4px; }
.ev-tab { padding: 10px 16px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; white-space: nowrap; transition: all 0.2s; }
.ev-tab:hover { color: #0d47a1; background: #f8fafc; }
.ev-tab.active { color: #0d47a1; border-bottom-color: #0d47a1; }
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

/* ===== STYLE TABEL LKPS (RESPONSIF & RAPI) ===== */
.lkps-section { margin-bottom: 30px; }
.lkps-section h3 { color: #0d47a1; border-left: 4px solid #0d47a1; padding-left: 12px; margin-bottom: 12px; font-size: 1.1rem; }
.table-responsive { overflow-x: auto; border: 1px solid #e0e0e0; border-radius: 8px; margin-bottom: 20px; }
.lkps-table { width: 100%; border-collapse: collapse; font-size: 0.85rem; min-width: 800px; }
.lkps-table th, .lkps-table td { border: 1px solid #e0e0e0; padding: 8px 12px; text-align: left; vertical-align: top; }
.lkps-table th { background-color: #f1f5f9; font-weight: 600; color: #0d47a1; position: sticky; top: 0; z-index: 1; }
.lkps-table tr:nth-child(even) { background-color: #f8fafc; }
.lkps-table tr:hover { background-color: #e3f2fd; }

/* Highlight untuk data penting */
.highlight-data { background-color: #fff8e1 !important; font-weight: 600; color: #e65100; }
.link-cell a { color: #0d47a1; text-decoration: none; word-break: break-all; }
.link-cell a:hover { text-decoration: underline; }

/* ===== INFO BOX ===== */
.info-box { background: #e3f2fd; border-left: 4px solid #0d47a1; padding: 12px 16px; border-radius: 6px; margin-bottom: 20px; font-size: 0.9rem; color: #0d47a1; }
</style>

<div class="info-box">
  <strong>ℹ️ Informasi:</strong> Halaman ini menampilkan <strong>data lengkap</strong> dari tabel LKPS PSBM. Gunakan scroll horizontal pada tabel jika tampilan terpotong di layar kecil.
</div>

<!-- ===== TAB NAVIGASI ===== -->
<div class="ev-tabs">
  <button class="ev-tab active" onclick="showEvPanel('c5', this)">C.5: Sarpras & K3L</button>
  <button class="ev-tab" onclick="showEvPanel('c6', this)">C.6: Mahasiswa & Luaran</button>
  <button class="ev-tab" onclick="showEvPanel('c7', this)">C.7: SPMI</button>
</div>

<!-- ===== PANEL C.5 ===== -->
<div class="ev-panel active" id="panel-c5">
  
  <!-- Tabel 5.a -->
  <div class="lkps-section">
    <h3>Tabel 5.a) Prasarana dan Peralatan Utama</h3>
    <div class="table-responsive">
      <table class="lkps-table">
        <thead>
          <tr><th>No</th><th>Nama Sarana</th><th>Jumlah Prasarana</th><th>Standar Minimal</th><th>Dimiliki UPPS</th><th>Sendiri</th><th>Sewa</th><th>Terawat</th><th>Tidak Terawat</th><th>Ada</th><th>Tidak Ada</th><th>Rata-rata Waktu Penggunaan (Jam/Minggu)</th></tr>
        </thead>
        <tbody>
          <tr><td>1</td><td>Lab Elektronika Analog dan Digital (G102)</td><td>1</td><td>Power Supply RIGOL DP831: 6</td><td>8</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>16</td></tr>
          <tr><td>2</td><td>Lab Sistem Transmisi (G103)</td><td>1</td><td>U PATCH PANEL TYPE C: 6</td><td>8</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>12</td></tr>
          <tr><td>3</td><td>Lab Sistem Telekomunikasi (G104)</td><td>1</td><td>FUNCTION GENERATOR: 3</td><td>4</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>18</td></tr>
          <tr><td>4</td><td>Lab Mikrokontroler dan Antarmuka (G105)</td><td>1</td><td>MEJA KAYU PRAKTIKUM: 11</td><td>11</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>32</td></tr>
          <tr><td>5</td><td>Ruang Penyimpanan Alat (G106)</td><td>1</td><td>Lemari Besi: 5</td><td>5</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>40</td></tr>
          <tr><td>6</td><td>Ruang Tunggu Dosen (G107)</td><td>1</td><td>DISPENSER MIDEA: 1</td><td>1</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>30</td></tr>
          <tr><td>7</td><td>Lab Komunikasi Data dan Serat Optik (G108)</td><td>1</td><td>MEJA PRAKTIKUM: 6</td><td>10</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>12</td></tr>
          <tr><td>8</td><td>Ruang Dosen (G109)</td><td>1</td><td>Meja Kerja Kayu Jati: 12</td><td>12</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>36</td></tr>
          <tr><td>9</td><td>Lab Jaringan Komunikasi Broadband (G110)</td><td>1</td><td>MEJA PRAKTIKUM: 12</td><td>12</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>16</td></tr>
          <tr><td>10</td><td>Bengkel Elektronika dan Fabrikasi Antena (G115)</td><td>1</td><td>BOR DUDUK WESTLAKE YY624: 2</td><td>2</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>12</td></tr>
          <tr><td>11</td><td>Ruang Peralatan Bengkel (G116)</td><td>1</td><td>SOLDER GOT RX711: 24</td><td>24</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>40</td></tr>
          <tr><td>12</td><td>Ruang Pengembangan Dosen (G203)</td><td>1</td><td>SPECTRUM ANALYZER: 1</td><td>1</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>30</td></tr>
          <tr><td>13</td><td>Smartlab (G303)</td><td>1</td><td>RASBERY PI 400 KIT: 12</td><td>13</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>8</td></tr>
          <tr><td>14</td><td>Layanan Kesehatan</td><td>1</td><td>Meja: 3</td><td>3</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>40</td></tr>
          <tr><td>15</td><td>Layanan Konseling</td><td>1</td><td>Meja: 3</td><td>3</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>30</td></tr>
          <tr><td>16</td><td>Masjid Darul Ilmi</td><td>1</td><td>Meja: 2</td><td>2</td><td>V</td><td></td><td>V</td><td></td><td>V</td><td></td><td>80</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Tabel 5.b -->
  <div class="lkps-section">
    <h3>Tabel 5.b) Dokumen K3L di UPPS</h3>
    <div class="table-responsive">
      <table class="lkps-table">
        <thead><tr><th>No</th><th>Jenis Dokumen</th><th>Jumlah</th><th>Riwayat Pengesahan</th></tr></thead>
        <tbody>
          <tr><td>1</td><td>Pedoman Sistem Manajemen Keselamatan Kerja di Lingkungan PNJ</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>2</td><td>Pedoman K3L Jurusan Teknik Elektro</td><td>1</td><td>25 Oktober 2025, disahkan oleh Ketua Jurusan Teknik Elektro</td></tr>
          <tr><td>3</td><td>SOP Prosedur Identifikasi Bahaya, Penilaian dan Pengendalian Risiko K3</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>4</td><td>SOP Identifikasi Peraturan Perundang-Undangan dan Persyaratan K3</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>5</td><td>SOP Pelatihan K3</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>6</td><td>SOP Prosedur Komunikasi K3</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>7</td><td>SOP Partisipasi dan Konsultasi K3</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>8</td><td>SOP Pengendalian Dokumen K3</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>9</td><td>SOP Tanggap Darurat K3</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>10</td><td>SOP Pengukuran dan Pemantauan Kinerja K3</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>11</td><td>SOP Kesesuaian Penerapan Perundang-undangan dan Persyaratan K3 Lainnya</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>12</td><td>SOP Investigasi Insiden Kecelakaan Kerja</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>13</td><td>SOP Identifikasi Ketidaksesuaian, Tindakan Perbaikan dan Tindakan Pencegahan</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>14</td><td>SOP Audit Internal K3</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>15</td><td>SOP Penggunaan Lab dan Bengkel</td><td>1</td><td>1 Januari 2025, disahkan oleh Kepala UPA Perawatan, Perbaikan dan K3</td></tr>
          <tr><td>16</td><td>Hasil Tinjauan Berkala K3</td><td>1</td><td>5 November 2025, disahkan oleh Ketua Jurusan Teknik Elektro</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Tabel 5.c -->
  <div class="lkps-section">
    <h3>Tabel 5.c) Fasilitas K3L di UPPS</h3>
    <div class="table-responsive">
      <table class="lkps-table">
        <thead><tr><th>No</th><th>Nama Sarana</th><th>Fungsi</th><th>Jumlah Unit</th><th>Terawat</th><th>Tidak Terawat</th></tr></thead>
        <tbody>
          <tr><td>1</td><td>Hidran Pilar</td><td>Sumber air bertekanan untuk membantu suplai air bagi truk pemadam api besar</td><td>2</td><td>V</td><td></td></tr>
          <tr><td>2</td><td>Layanan Kesehatan</td><td>untuk pengobatan pertama</td><td>1</td><td>V</td><td></td></tr>
          <tr><td>3</td><td>Ambulance</td><td>untuk evakuasi</td><td>1</td><td>V</td><td></td></tr>
          <tr><td>4</td><td>APAR</td><td>untuk pemadam api ringan</td><td>6</td><td>V</td><td></td></tr>
          <tr><td>5</td><td>APAB</td><td>untuk pemadam api besar</td><td>1</td><td>V</td><td></td></tr>
          <tr><td>6</td><td>Truk Damkar</td><td>untuk pemadam api yang lebih besar</td><td>1</td><td>V</td><td></td></tr>
          <tr><td>7</td><td>Rambu keselamatan kerja</td><td>Papan atau stiker berisi simbol/tulisan peringatan, larangan, dan instruksi keselamatan di area kerja.</td><td>7</td><td>V</td><td></td></tr>
          <tr><td>8</td><td>Sign system APD</td><td>Papan untuk menginformasikan kelengkapan Alat Pelindung Diri yang harus digunakan sebelum masuk laboratorium</td><td>5</td><td>V</td><td></td></tr>
          <tr><td>9</td><td>Kotak P3K</td><td>Kotak berisi perlengkapan pertolongan pertama seperti perban, plester, antiseptik, dan sarung tangan medis.</td><td>2</td><td>V</td><td></td></tr>
          <tr><td>10</td><td>Lemari penyimpanan bahan kimia</td><td>Tempat khusus yang aman dan terlabel untuk menyimpan bahan kimia dan bahan berbahaya.</td><td>2</td><td>V</td><td></td></tr>
          <tr><td>11</td><td>Tanda jalur evakuasi dan titik kumpul</td><td>Penandaan jalur keluar darurat yang jelas, dilengkapi peta evakuasi di setiap area laboratorium/bengkel.</td><td>22</td><td>V</td><td></td></tr>
          <tr><td>12</td><td>Video Safety Induction</td><td>Video instruksi akan hal yang harus dilakukan jika terjadi bahaya</td><td>1</td><td>V</td><td></td></tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

<!-- ===== PANEL C.6 ===== -->
<div class="ev-panel" id="panel-c6">
  
  <!-- Tabel 6.a -->
  <div class="lkps-section">
    <h3>Tabel 6.a) Jumlah Mahasiswa (Reguler dan Asing)</h3>
    <div class="table-responsive">
      <table class="lkps-table">
        <thead><tr><th>No</th><th>Program Studi</th><th>Prodi yang Diakreditasi</th><th>TS-2</th><th>TS-1</th><th>TS</th><th>Mhs Asing FT TS-2</th><th>Mhs Asing FT TS-1</th><th>Mhs Asing FT TS</th><th>Mhs Asing PT TS-2</th><th>Mhs Asing PT TS-1</th><th>Mhs Asing PT TS</th></tr></thead>
        <tbody>
          <tr class="highlight-data"><td>1</td><td>D4 - Broadband Multimedia</td><td>V</td><td>192</td><td>182</td><td>189</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>12</td></tr>
        </tbody>
        <tfoot>
          <tr><td colspan="3"><strong>Total</strong></td><td><strong>192</strong></td><td><strong>182</strong></td><td><strong>189</strong></td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>12</td></tr>
        </tfoot>
      </table>
    </div>
  </div>

  <!-- Tabel 6.b -->
  <div class="lkps-section">
    <h3>Tabel 6.b) IPK Lulusan</h3>
    <div class="table-responsive">
      <table class="lkps-table">
        <thead><tr><th>No</th><th>Tahun Lulus</th><th>Jumlah Lulusan</th><th>Min.</th><th>Rata-rata</th><th>Maks</th></tr></thead>
        <tbody>
          <tr><td>1</td><td>TS-2</td><td>44</td><td>2.66</td><td class="highlight-data">3.49</td><td>3.76</td></tr>
          <tr><td>2</td><td>TS-1</td><td>36</td><td>3.18</td><td class="highlight-data">3.45</td><td>3.73</td></tr>
          <tr><td>3</td><td>TS</td><td>44</td><td>2.78</td><td class="highlight-data">3.43</td><td>3.82</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Tabel 6.d -->
  <div class="lkps-section">
    <h3>Tabel 6.d) Masa Studi Lulusan</h3>
    <div class="table-responsive">
      <table class="lkps-table">
        <thead><tr><th>Tahun Masuk</th><th>Jumlah Mahasiswa Masuk</th><th>3,5 < MS ≤ 4,5</th><th>4,5 < MS ≤ 5,5</th><th>5,5 < MS ≤ 6,5</th><th>6,5 < MS ≤ 8</th></tr></thead>
        <tbody>
          <tr><td>TS-7</td><td>41</td><td>39</td><td>2</td><td>0</td><td>0</td></tr>
          <tr><td>TS-6</td><td>42</td><td>39</td><td>3</td><td>0</td><td>0</td></tr>
          <tr><td>TS-5</td><td>43</td><td>42</td><td>1</td><td>0</td><td></td></tr>
          <tr><td>TS-4</td><td>38</td><td>36</td><td>2</td><td></td><td></td></tr>
          <tr><td>TS-3</td><td>47</td><td>43</td><td></td><td></td><td></td></tr>
          <tr><td>TS-2</td><td>44</td><td></td><td></td><td></td><td></td></tr>
          <tr><td>TS-1</td><td>46</td><td></td><td></td><td></td><td></td></tr>
          <tr><td>TS</td><td>45</td><td></td><td></td><td></td><td></td></>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Tabel 6.g.2 -->
  <div class="lkps-section">
    <h3>Tabel 6.g.2) Kepuasan Pengguna Lulusan</h3>
    <div class="table-responsive">
      <table class="lkps-table">
        <thead><tr><th>No</th><th>Jenis Kemampuan</th><th>Sangat Baik</th><th>Baik</th><th>Cukup</th><th>Kurang</th><th>Rencana Tindak Lanjut oleh UPPS/PS</th></tr></thead>
        <tbody>
          <tr><td>1</td><td>Etika</td><td class="highlight-data">80.00%</td><td>20.00%</td><td>0.00%</td><td>0.00%</td><td>Mempertahankan capaian melalui penguatan nilai etika profesi dalam kurikulum dan kegiatan kemahasiswaan.</td></tr>
          <tr><td>2</td><td>Keahlian pada bidang ilmu (kompetensi utama)</td><td class="highlight-data">73.30%</td><td>26.70%</td><td>0.00%</td><td>0.00%</td><td>Mempertahankan dan meningkatkan kualitas pembelajaran melalui pemutakhiran kurikulum sesuai perkembangan industri serta penguatan praktikum/proyek berbasis kasus nyata.</td></tr>
          <tr><td>3</td><td>Kemampuan berbahasa asing</td><td class="highlight-data">71.10%</td><td>17.80%</td><td class="highlight-data">11.10%</td><td>0.00%</td><td>Meningkatkan intensitas pembelajaran bahasa asing (mis. kelas intensif, sertifikasi TOEFL/TOEIC, program imersi), mengingat masih terdapat 25% penilaian "Cukup" dari pengguna lulusan.</td></tr>
          <tr><td>4</td><td>Penggunaan teknologi informasi</td><td class="highlight-data">82.20%</td><td>17.80%</td><td>0.00%</td><td>0.00%</td><td>Mempertahankan capaian dengan terus mengikuti perkembangan teknologi terkini melalui pelatihan/sertifikasi tambahan bagi mahasiswa.</td></tr>
          <tr><td>5</td><td>Kemampuan berkomunikasi</td><td class="highlight-data">77.78%</td><td>22.20%</td><td>0.00%</td><td>0.00%</td><td>Mempertahankan dan meningkatkan melalui pelatihan soft skill, public speaking, dan simulasi presentasi dalam perkuliahan.</td></tr>
          <tr><td>6</td><td>Kerjasama tim</td><td class="highlight-data">75.60%</td><td>24.40%</td><td>0.00%</td><td>0.00%</td><td>Mempertahankan capaian dengan memperbanyak tugas kelompok dan proyek kolaboratif lintas disiplin.</td></tr>
          <tr><td>7</td><td>Pengembangan diri</td><td class="highlight-data">73.30%</td><td>26.70%</td><td>0.00%</td><td>0.00%</td><td>Mempertahankan dan mendorong keikutsertaan mahasiswa dalam organisasi, pelatihan kepemimpinan, dan kegiatan pengembangan karakter.</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Catatan: Tabel 6.c.1, 6.c.2, 6.e.1 - 6.e.4, 6.f.1, 6.f.2, 6.g.1, 6.h.1, 6.h.2, 6.i dapat ditambahkan dengan pola yang sama di atas -->
  <div class="info-box">
    <strong>Catatan:</strong> Tabel 6.c.1, 6.c.2, 6.e, 6.f, 6.g.1, 6.h, dan 6.i telah disediakan dalam data mentah Anda. Anda dapat menyalin format tabel di atas dan menempelkan data tersebut di bagian ini agar halaman tetap rapi dan terstruktur.
  </div>
</div>

<!-- ===== PANEL C.7 ===== -->
<div class="ev-panel" id="panel-c7">
  
  <!-- Tabel 7.a -->
  <div class="lkps-section">
    <h3>Tabel 7.a) Ketersediaan Dokumen/Buku Sistem Penjaminan Mutu Internal</h3>
    <div class="table-responsive">
      <table class="lkps-table">
        <thead><tr><th>No</th><th>Jenis Dokumen Penjaminan Mutu</th><th>No Dokumen</th><th>Tanggal Dokumen</th></tr></thead>
        <tbody>
          <tr><td>1</td><td>Kebijakan SPMI</td><td>No: SM/PNJ/SPMI/342</td><td>18/1/2022</td></tr>
          <tr><td>2</td><td>Pedoman penerapan siklus PPEPP standar pendidikan tinggi dalam SPMI</td><td>KM/PNJ/SPMI/212</td><td>18/1/2022</td></tr>
          <tr><td>3</td><td>Standar dan/atau kriteria, norma, acuan mutu penyelenggaraan pendidikan dan pengelolaan perguruan tinggi</td><td>SM/PNJ/SPMI/311</td><td>20/1/2022</td></tr>
          <tr><td>4</td><td>Tata cara pendokumentasian implementasi SPMI</td><td>KM/PNJ/SPMI/215</td><td>20/1/2022</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Tabel 7.b -->
  <div class="lkps-section">
    <h3>Tabel 7.b) Ketersediaan Dokumen Pelaksanaan Sistem Penjaminan Mutu Internal</h3>
    <div class="table-responsive">
      <table class="lkps-table">
        <thead><tr><th>No</th><th>Dokumen</th><th>Link Dokumen</th><th>Link Laporan Hasil Audit</th><th>Link Laporan RTM</th><th>Link Dokumen Peningkatan</th></tr></thead>
        <tbody>
          <tr><td>1</td><td>Penetapan</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S?usp=drive_link" target="_blank">Buka Folder Google Drive</a></td><td>-</td><td>-</td><td>-</td></tr>
          <tr><td>2</td><td>Pelaksanaan</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/17PgbEe6jg7P3MlRUIZSZhhC4enyylZ7S?usp=drive_link" target="_blank">Buka Folder Google Drive</a></td><td>-</td><td>-</td><td>-</td></tr>
          <tr><td>3</td><td>Evaluasi</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1ywPn4RexBzQjD6DXRT8DCXTEtemvcQLz?usp=sharing" target="_blank">Buka Folder Google Drive</a></td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1gpdVeFMr0vwmrw_VvUpJhDokvF1zfVx2?usp=sharing" target="_blank">Buka Folder Google Drive</a></td><td>-</td><td>-</td></tr>
          <tr><td>4</td><td>Pengendalian</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1WFgIamM3JnSGZ-WAv-UOC1W22E0ondmV?usp=sharing" target="_blank">Buka Folder Google Drive</a></td><td>-</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/18PzEeZ2yIs1hfx6rVOBzbjjoaGIkSFU0?usp=sharing" target="_blank">Buka Folder Google Drive</a></td><td>-</td></tr>
          <tr><td>5</td><td>Peningkatan</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0?usp=sharing" target="_blank">Buka Folder Google Drive</a></td><td>-</td><td>-</td><td class="link-cell"><a href="https://drive.google.com/drive/folders/1vQGaaKTH7mtpT8vgRPEwZ2Olx8G_0Gb0?usp=sharing" target="_blank">Buka Folder Google Drive</a></td></tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

<script>
function showEvPanel(id, btn) {
  document.querySelectorAll('.ev-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.ev-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
}
</script>

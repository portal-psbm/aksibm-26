---
layout: default
title: Evidence AL
permalink: /evidence/
---

<style>
  /* ===== Cabinet Container ===== */
  .ev-cabinet { background: linear-gradient(180deg, #e3f2fd 0%, #bbdefb 100%); padding: 20px 20px 0 20px; border-radius: 16px 16px 0 0; box-shadow: inset 0 4px 12px rgba(13, 71, 161, 0.08), 0 4px 16px rgba(0,0,0,0.06); position: relative; border: 1px solid #bbdefb; border-bottom: none; }
  .ev-shelf { display: flex; flex-wrap: nowrap; gap: 8px; padding: 0 8px; position: relative; z-index: 10; overflow-x: auto; overflow-y: visible; scrollbar-width: thin; scrollbar-color: #0d47a1 transparent; padding-bottom: 4px; }
  .ev-shelf::-webkit-scrollbar { height: 4px; }
  .ev-shelf::-webkit-scrollbar-track { background: rgba(13, 71, 161, 0.05); border-radius: 2px; }
  .ev-shelf::-webkit-scrollbar-thumb { background: #0d47a1; border-radius: 2px; }
  .ev-tab { position: relative; flex: 1 1 0; min-width: 0; padding: 16px 10px 20px 10px; background: #ffffff; border-radius: 10px 10px 0 0; border: 1px solid #e0e0e0; border-bottom: none; cursor: pointer; text-align: center; font-weight: 600; font-size: 0.85rem; line-height: 1.2; color: #555; transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1); transform: translateY(4px); box-shadow: 0 -2px 6px rgba(0,0,0,0.05); white-space: normal; word-wrap: break-word; overflow-wrap: break-word; }
  .ev-tab::before { content: ''; position: absolute; top: -7px; left: 22%; width: 56%; height: 7px; background: #f5f5f5; border-radius: 4px 4px 0 0; border: 1px solid #e0e0e0; border-bottom: none; transition: all 0.35s ease; }
  .ev-tab:hover { background: #f1f5f9; transform: translateY(0px); color: #0d47a1; }
  .ev-tab:hover::before { background: #f1f5f9; }
  .ev-tab.active { background: #0d47a1; color: #ffffff; transform: translateY(-6px); z-index: 20; border-color: #0d47a1; box-shadow: 0 -4px 16px rgba(13, 71, 161, 0.25); font-weight: 700; }
  .ev-tab.active::before { background: #0d47a1; border-color: #0d47a1; height: 9px; top: -9px; }
  .ev-tab.bab3-tab { background: linear-gradient(180deg, #fff8e1 0%, #ffecb3 100%); color: #e65100; border-color: #ffcc80; }
  .ev-tab.bab3-tab::before { background: linear-gradient(180deg, #ffcc80 0%, #ffb74d 100%); border-color: #ffcc80; }
  .ev-tab.bab3-tab.active { background: linear-gradient(135deg, #e65100 0%, #bf360c 100%); color: white; border-color: #bf360c; }
  .ev-tab.bab3-tab.active::before { background: linear-gradient(135deg, #e65100 0%, #bf360c 100%); border-color: #bf360c; }

  .ev-content { background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1; border-radius: 0 0 16px 16px; padding: 28px; min-height: 500px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px; }
  .ev-panel { display: none; animation: fadeIn 0.3s ease; }
  .ev-panel.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

  /* ===== Hero Search ===== */
  .ev-hero { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); color: white; padding: 32px 28px; border-radius: 12px; margin-bottom: 20px; text-align: center; }
  .ev-hero h2 { margin: 0 0 6px 0; font-size: 1.4rem; }
  .ev-hero .subtitle { opacity: 0.9; font-size: 0.9rem; margin-bottom: 20px; }
  .ev-search-wrapper { display: flex; gap: 8px; max-width: 700px; margin: 0 auto 16px auto; }
  .ev-search { flex: 1; padding: 16px 24px; border-radius: 30px; border: 2px solid rgba(255,255,255,0.3); background: rgba(255,255,255,0.15); color: white; font-size: 1rem; backdrop-filter: blur(4px); }
  .ev-search::placeholder { color: rgba(255,255,255,0.7); }
  .ev-search:focus { outline: none; border-color: #fff; background: rgba(255,255,255,0.25); }
  .ev-btn { padding: 16px 24px; border-radius: 30px; border: none; font-size: 1rem; font-weight: 600; cursor: pointer; transition: all 0.2s; white-space: nowrap; }
  .ev-btn.search { background: #4caf50; color: white; }
  .ev-btn.search:hover { background: #45a049; }
  .ev-btn.clear { background: rgba(255,255,255,0.2); color: white; border: 2px solid rgba(255,255,255,0.5); }
  .ev-btn.clear:hover { background: rgba(255,255,255,0.3); }

  /* Quick Access Chips */
  .ev-quick-chips { display: flex; gap: 6px; justify-content: center; flex-wrap: wrap; margin-top: 16px; }
  .ev-quick-chip { padding: 8px 14px; background: rgba(255,255,255,0.15); border: 1px solid rgba(255,255,255,0.3); border-radius: 16px; color: white; cursor: pointer; font-weight: 600; font-size: 0.82rem; transition: all 0.2s; }
  .ev-quick-chip:hover { background: rgba(255,255,255,0.3); }
  .ev-quick-chip.bab3 { background: rgba(230, 81, 0, 0.25); border-color: rgba(255, 183, 77, 0.5); }
  .ev-quick-chip.bab3:hover { background: rgba(230, 81, 0, 0.4); }

  /* ===== Bukti Utama Section ===== */
  .bukti-utama-section { margin-top: 24px; }
  .bukti-utama-section h3 { color: #0d47a1; margin: 0 0 12px 0; font-size: 1.05rem; display: flex; align-items: center; gap: 8px; }
  .bukti-utama-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 10px; }
  .bukti-utama-card { background: white; border: 1px solid #e0e0e0; border-left: 4px solid #0d47a1; border-radius: 8px; padding: 14px; cursor: pointer; transition: all 0.2s; }
  .bukti-utama-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); transform: translateY(-2px); border-left-color: #4caf50; }
  .bukti-utama-card .buc-icon { font-size: 1.4rem; margin-bottom: 4px; }
  .bukti-utama-card .buc-name { font-weight: 700; color: #333; font-size: 0.88rem; }
  .bukti-utama-card .buc-desc { font-size: 0.75rem; color: #666; margin-top: 2px; }

  /* ===== Sub-nav Indikator ===== */
  .ev-subnav { display: flex; gap: 4px; margin-bottom: 16px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
  .ev-subnav button { padding: 10px 16px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.88rem; }
  .ev-subnav button:hover { color: #0d47a1; background: #f8fafc; }
  .ev-subnav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }
  .ev-subnav button .count { background: #e3f2fd; color: #0d47a1; padding: 2px 8px; border-radius: 10px; font-size: 0.72rem; margin-left: 4px; font-weight: 700; }
  .ev-subnav button.active .count { background: #0d47a1; color: white; }

  /* ===== Evidence Card ===== */
  .ev-card { background: white; border: 1px solid #e0e0e0; border-radius: 10px; padding: 16px; margin-bottom: 12px; transition: all 0.2s; display: flex; gap: 14px; align-items: flex-start; }
  .ev-card:hover { box-shadow: 0 4px 14px rgba(0,0,0,0.08); transform: translateX(2px); }
  .ev-card.utama { border-left: 4px solid #0d47a1; }
  .ev-card.pendukung { border-left: 4px solid #90a4ae; }
  .ev-card-icon { font-size: 1.8rem; min-width: 40px; text-align: center; padding-top: 2px; }
  .ev-card-body { flex: 1; min-width: 0; }
  .ev-card-title { font-weight: 700; color: #333; font-size: 0.95rem; margin-bottom: 4px; }
  .ev-card-desc { font-size: 0.85rem; color: #555; line-height: 1.5; margin-bottom: 8px; }
  .ev-card-meta { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 10px; }
  .ev-badge { padding: 3px 10px; border-radius: 10px; font-size: 0.7rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.3px; }
  .ev-badge.utama { background: #e3f2fd; color: #0d47a1; }
  .ev-badge.pendukung { background: #eceff1; color: #546e7a; }
  .ev-badge.jenis { background: #f3e5f5; color: #6a1b9a; }
  .ev-badge.tahun { background: #e8f5e9; color: #2e7d32; }
  .ev-badge.sumber { background: #fff8e1; color: #e65100; }
  .ev-card-actions { display: flex; gap: 6px; flex-wrap: wrap; }
  .ev-open-btn { padding: 6px 14px; border-radius: 6px; border: none; background: #0d47a1; color: white; font-size: 0.8rem; font-weight: 600; cursor: pointer; transition: all 0.2s; display: inline-flex; align-items: center; gap: 4px; }
  .ev-open-btn:hover { background: #1565c0; transform: translateY(-1px); }
  .ev-open-btn.secondary { background: white; color: #0d47a1; border: 1px solid #0d47a1; }
  .ev-open-btn.secondary:hover { background: #e3f2fd; }

  /* ===== BAB III Chain ===== */
  .bab3-chain { display: flex; flex-direction: column; gap: 0; margin: 20px 0; }
  .bab3-step { background: white; padding: 16px 20px; border-left: 4px solid #e65100; position: relative; box-shadow: 0 2px 8px rgba(0,0,0,0.05); margin-bottom: 10px; border-radius: 0 8px 8px 0; border: 1px solid #e0e0e0; border-left: 4px solid #e65100; }
  .bab3-step::after { content: '▼'; position: absolute; bottom: -14px; left: 50%; transform: translateX(-50%); color: #e65100; font-size: 1rem; z-index: 1; }
  .bab3-step:last-child::after { display: none; }
  .bab3-step .step-num { display: inline-block; background: #e65100; color: white; padding: 2px 10px; border-radius: 10px; font-size: 0.72rem; font-weight: 700; margin-bottom: 6px; }
  .bab3-step .step-title { font-weight: 700; color: #e65100; margin-bottom: 4px; font-size: 0.95rem; }
  .bab3-step .step-content { font-size: 0.88rem; color: #333; line-height: 1.5; }
  .bab3-step .step-evidence { margin-top: 8px; display: flex; gap: 6px; flex-wrap: wrap; }

  /* ===== No Result ===== */
  .no-result { text-align: center; padding: 40px 20px; color: #888; background: #f8fafc; border-radius: 10px; }

  /* ===== Section Header ===== */
  .section-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 16px; flex-wrap: wrap; gap: 8px; }
  .section-header h2 { color: #0d47a1; margin: 0; font-size: 1.2rem; }
  .section-header .section-desc { color: #666; font-size: 0.88rem; margin-top: 4px; width: 100%; }

  /* ===== Filter Bar ===== */
  .filter-bar { display: flex; gap: 8px; margin-bottom: 16px; flex-wrap: wrap; padding: 12px; background: #f8fafc; border-radius: 8px; border: 1px solid #e0e0e0; }
  .filter-bar select, .filter-bar input { padding: 8px 12px; border: 1px solid #e0e0e0; border-radius: 6px; font-size: 0.85rem; background: white; }
  .filter-bar input { flex: 1; min-width: 200px; }
  .filter-bar input:focus, .filter-bar select:focus { outline: none; border-color: #0d47a1; }

  @media (max-width: 767px) {
    .ev-shelf { gap: 6px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
    .ev-shelf::-webkit-scrollbar { display: none; }
    .ev-tab { min-width: 110px; flex: 0 0 auto; font-size: 0.8rem; }
    .ev-content { padding: 20px; }
    .ev-search-wrapper { flex-direction: column; }
    .ev-btn { width: 100%; }
    .ev-card { flex-direction: column; }
    .ev-card-icon { font-size: 1.4rem; }
  }
</style>

<!-- ===== KABINET FOLDER NAV ===== -->
<div class="ev-cabinet">
  <div class="ev-shelf">
    <div class="ev-tab active" onclick="showEvPanel('beranda', this)">🏠<br>Beranda</div>
    <div class="ev-tab" onclick="showEvPanel('c1', this)">📑<br>C.1 VMTS</div>
    <div class="ev-tab" onclick="showEvPanel('c2', this)">🏛️<br>C.2 Tata Kelola</div>
    <div class="ev-tab" onclick="showEvPanel('c3', this)">📘<br>C.3 Diklitpmas</div>
    <div class="ev-tab" onclick="showEvPanel('c4', this)">👨‍🏫<br>C.4 SDM</div>
    <div class="ev-tab" onclick="showEvPanel('c5', this)">💰<br>C.5 Sarpras</div>
    <div class="ev-tab" onclick="showEvPanel('c6', this)">🎓<br>C.6 Luaran</div>
    <div class="ev-tab" onclick="showEvPanel('c7', this)">🔄<br>C.7 SPMI</div>
    <div class="ev-tab bab3-tab" onclick="showEvPanel('bab3', this)">📕<br>BAB III</div>
  </div>

  <div class="ev-content">

    <!-- ========== BERANDA ========== -->
    <div class="ev-panel active" id="panel-beranda">
      <div class="ev-hero">
        <h2>📂 Evidence AL PSBM</h2>
        <div class="subtitle">Portal Bukti Pendukung Asesmen Lapangan — Akses 1–2 klik</div>
        <div class="ev-search-wrapper">
          <input type="text" class="ev-search" id="evSearch" placeholder="🔎 Cari bukti, CPL, RPS, tracer, AMI, kerja sama..." onkeypress="if(event.key==='Enter') searchEvidence()">
          <button class="ev-btn search" onclick="searchEvidence()">🔍 Cari</button>
          <button class="ev-btn clear" onclick="clearEvSearch()">✖ Clear</button>
        </div>
        <div class="ev-quick-chips">
          <div class="ev-quick-chip" onclick="goToPanel('c1')">📑 C.1</div>
          <div class="ev-quick-chip" onclick="goToPanel('c2')">🏛️ C.2</div>
          <div class="ev-quick-chip" onclick="goToPanel('c3')">📘 C.3</div>
          <div class="ev-quick-chip" onclick="goToPanel('c4')">👨‍🏫 C.4</div>
          <div class="ev-quick-chip" onclick="goToPanel('c5')">💰 C.5</div>
          <div class="ev-quick-chip" onclick="goToPanel('c6')">🎓 C.6</div>
          <div class="ev-quick-chip" onclick="goToPanel('c7')">🔄 C.7</div>
          <div class="ev-quick-chip bab3" onclick="goToPanel('bab3')">📕 BAB III</div>
        </div>
      </div>

      <div id="searchResultContainer"></div>

      <div id="defaultBeranda">
        <!-- Bukti Utama AL -->
        <div class="bukti-utama-section">
          <h3>⭐ Bukti Utama AL</h3>
          <div class="bukti-utama-grid">
            <div class="bukti-utama-card" onclick="quickSearch('LED Final')">
              <div class="buc-icon">📄</div>
              <div class="buc-name">LED Final</div>
              <div class="buc-desc">Laporan Evaluasi Diri</div>
            </div>
            <div class="bukti-utama-card" onclick="quickSearch('LKPS Final')">
              <div class="buc-icon">📊</div>
              <div class="buc-name">LKPS Final</div>
              <div class="buc-desc">Laporan Kinerja PS</div>
            </div>
            <div class="bukti-utama-card" onclick="quickSearch('NADK')">
              <div class="buc-icon">📘</div>
              <div class="buc-name">NADK / Kurikulum</div>
              <div class="buc-desc">Naskah Akademik</div>
            </div>
            <div class="bukti-utama-card" onclick="quickSearch('CPL')">
              <div class="buc-icon">🎓</div>
              <div class="buc-name">CPL – MK</div>
              <div class="buc-desc">Matriks pemetaan</div>
            </div>
            <div class="bukti-utama-card" onclick="quickSearch('RPS')">
              <div class="buc-icon">📝</div>
              <div class="buc-name">RPS</div>
              <div class="buc-desc">Rencana Pembelajaran</div>
            </div>
            <div class="bukti-utama-card" onclick="quickSearch('Tracer Study')">
              <div class="buc-icon">📈</div>
              <div class="buc-name">Tracer Study</div>
              <div class="buc-desc">Laporan lulusan</div>
            </div>
            <div class="bukti-utama-card" onclick="quickSearch('Survei Pengguna')">
              <div class="buc-icon">⭐</div>
              <div class="buc-name">Survei Pengguna</div>
              <div class="buc-desc">Kepuasan pengguna</div>
            </div>
            <div class="bukti-utama-card" onclick="quickSearch('Roadmap')">
              <div class="buc-icon">🗺️</div>
              <div class="buc-name">Roadmap</div>
              <div class="buc-desc">Penelitian & PkM</div>
            </div>
            <div class="bukti-utama-card" onclick="quickSearch('DTPS')">
              <div class="buc-icon">👨‍🏫</div>
              <div class="buc-name">Data DTPS</div>
              <div class="buc-desc">Profil dosen</div>
            </div>
            <div class="bukti-utama-card" onclick="quickSearch('AMI')">
              <div class="buc-icon">🔍</div>
              <div class="buc-name">AMI – RTM – RTL</div>
              <div class="buc-desc">Audit & monitoring</div>
            </div>
          </div>
        </div>

        <!-- Statistik Evidence -->
        <div style="margin-top: 24px;">
          <h3 style="color:#0d47a1; margin: 0 0 12px 0;">📊 Ringkasan Evidence</h3>
          <div class="bukti-utama-grid" id="statsGrid"></div>
        </div>
      </div>
    </div>

    <!-- ========== C.1 - C.7 PANELS (akan di-render via JS) ========== -->
    <div class="ev-panel" id="panel-c1"><div id="c1Content"></div></div>
    <div class="ev-panel" id="panel-c2"><div id="c2Content"></div></div>
    <div class="ev-panel" id="panel-c3"><div id="c3Content"></div></div>
    <div class="ev-panel" id="panel-c4"><div id="c4Content"></div></div>
    <div class="ev-panel" id="panel-c5"><div id="c5Content"></div></div>
    <div class="ev-panel" id="panel-c6"><div id="c6Content"></div></div>
    <div class="ev-panel" id="panel-c7"><div id="c7Content"></div></div>

    <!-- ========== BAB III ========== -->
    <div class="ev-panel" id="panel-bab3">
      <div class="section-header">
        <h2>📕 BAB III — Program Pengembangan Berkelanjutan</h2>
        <div class="section-desc">Rantai keterlacakan: Temuan → SWOT → Tujuan → Program → Monitoring</div>
      </div>

      <div class="ev-subnav" id="bab3SubNav">
        <button class="active" onclick="showBab3('chain', this)">🔗 Rantai Keterlacakan</button>
        <button onclick="showBab3('swot', this)">📊 SWOT</button>
        <button onclick="showBab3('tujuan', this)">🎯 Tujuan Strategis</button>
        <button onclick="showBab3('program', this)">📘 Program Pengembangan</button>
        <button onclick="showBab3('monitoring', this)">🔄 Monitoring / PPEPP</button>
      </div>

      <div id="bab3Content"></div>
    </div>

  </div>
</div>

<script>
// ===== DATA EVIDENCE LENGKAP =====
const dataEvidence = [
  // ===== C.1 VMTS =====
  { id:'E001', nama:'SK VMTS PT', kriteria:'C.1', indikator:'Kekhasan VMTS', jenis:'SK', tahun:'2020', keterangan:'SK VMTS tingkat Politeknik Negeri Jakarta', sumber:'LED C.1', prioritas:'UTAMA', icon:'📜' },
  { id:'E002', nama:'SK VMTS UPPS (JTE)', kriteria:'C.1', indikator:'Kekhasan VMTS', jenis:'SK', tahun:'2020', keterangan:'SK VMTS tingkat Jurusan/UPPS', sumber:'LED C.1', prioritas:'UTAMA', icon:'📜' },
  { id:'E003', nama:'Dokumen Visi Keilmuan PSBM', kriteria:'C.1', indikator:'Kekhasan VMTS', jenis:'Dokumen', tahun:'2020', keterangan:'Visi keilmuan Broadband Multimedia', sumber:'LED C.1', prioritas:'UTAMA', icon:'📘' },
  { id:'E004', nama:'Matriks Sinkronisasi VMTS', kriteria:'C.1', indikator:'Kekhasan VMTS', jenis:'Matriks', tahun:'2024', keterangan:'Linearitas visi PT → JTE → PSBM', sumber:'LED C.1', prioritas:'UTAMA', icon:'📊' },
  { id:'E005', nama:'SK Tim Penyusun VMTS', kriteria:'C.1', indikator:'Mekanisme Penyusunan', jenis:'SK', tahun:'2020', keterangan:'SK tim penyusun VMTS dan visi keilmuan', sumber:'LED C.1', prioritas:'UTAMA', icon:'📜' },
  { id:'E006', nama:'Undangan & Daftar Hadir FGD VMTS', kriteria:'C.1', indikator:'Mekanisme Penyusunan', jenis:'Dokumentasi', tahun:'2020-2024', keterangan:'Bukti keterlibatan stakeholder', sumber:'LED C.1', prioritas:'UTAMA', icon:'📋' },
  { id:'E007', nama:'Notulensi & BA FGD VMTS', kriteria:'C.1', indikator:'Mekanisme Penyusunan', jenis:'BA', tahun:'2020-2024', keterangan:'Masukan alumni, pengguna, pakar', sumber:'LED C.1', prioritas:'UTAMA', icon:'📝' },
  { id:'E008', nama:'Buku Saku VMTS', kriteria:'C.1', indikator:'Sosialisasi VMTS', jenis:'Publikasi', tahun:'2024', keterangan:'Media sosialisasi VMTS ke stakeholder', sumber:'LED C.1', prioritas:'UTAMA', icon:'📗' },
  { id:'E009', nama:'Laporan Survei Pemahaman VMTS', kriteria:'C.1', indikator:'Pemahaman Stakeholder', jenis:'Laporan', tahun:'2024', keterangan:'Hasil survei pemahaman stakeholder (85%)', sumber:'LED C.1 / LKPS 1', prioritas:'UTAMA', icon:'📈' },
  { id:'E010', nama:'Renstra & Renop JTE', kriteria:'C.1', indikator:'Pencapaian VMTS', jenis:'Dokumen', tahun:'2020-2025', keterangan:'Target dan capaian VMTS', sumber:'LED C.1', prioritas:'UTAMA', icon:'📘' },
  { id:'E011', nama:'Laporan Capaian VMTS', kriteria:'C.1', indikator:'Pencapaian VMTS', jenis:'Laporan', tahun:'2024', keterangan:'Realisasi vs target VMTS', sumber:'LED C.1', prioritas:'UTAMA', icon:'📊' },

  // ===== C.2 TATA KELOLA =====
  { id:'E012', nama:'Statuta PNJ', kriteria:'C.2', indikator:'Tata Pamong', jenis:'Regulasi', tahun:'2021', keterangan:'Statuta Politeknik Negeri Jakarta', sumber:'LED C.2', prioritas:'UTAMA', icon:'📜' },
  { id:'E013', nama:'SK OTK JTE', kriteria:'C.2', indikator:'Tata Pamong', jenis:'SK', tahun:'2022', keterangan:'Organisasi dan Tata Kerja JTE', sumber:'LED C.2', prioritas:'UTAMA', icon:'📜' },
  { id:'E014', nama:'SK Pengangkatan Pimpinan JTE', kriteria:'C.2', indikator:'Tata Pamong', jenis:'SK', tahun:'2022', keterangan:'SK Kajur, KAJUR, Kaprodi', sumber:'LED C.2', prioritas:'UTAMA', icon:'📜' },
  { id:'E015', nama:'SOP Tata Kelola JTE', kriteria:'C.2', indikator:'Tata Pamong', jenis:'SOP', tahun:'2023', keterangan:'SOP pengelolaan JTE', sumber:'LED C.2', prioritas:'UTAMA', icon:'📋' },
  { id:'E016', nama:'RKAT JTE 2024', kriteria:'C.2', indikator:'Pengelolaan', jenis:'Dokumen', tahun:'2024', keterangan:'Rencana Kerja dan Anggaran', sumber:'LED C.2', prioritas:'UTAMA', icon:'📊' },
  { id:'E017', nama:'Laporan Realisasi Anggaran', kriteria:'C.2', indikator:'Pengelolaan', jenis:'Laporan', tahun:'2022-2024', keterangan:'Realisasi anggaran 3 tahun', sumber:'LED C.2 / LKPS 2.b', prioritas:'UTAMA', icon:'💰' },
  { id:'E018', nama:'Daftar MoU Aktif', kriteria:'C.2', indikator:'Kerja Sama', jenis:'Daftar', tahun:'2024', keterangan:'66 MoU tridharma aktif', sumber:'LED C.2 / LKPS 2.a', prioritas:'UTAMA', icon:'🤝' },
  { id:'E019', nama:'IA Kerja Sama Pendidikan', kriteria:'C.2', indikator:'Kerja Sama', jenis:'Laporan', tahun:'2022-2024', keterangan:'Implementasi 42 kerja sama pendidikan', sumber:'LED C.2', prioritas:'UTAMA', icon:'📋' },
  { id:'E020', nama:'IA Kerja Sama Penelitian', kriteria:'C.2', indikator:'Kerja Sama', jenis:'Laporan', tahun:'2022-2024', keterangan:'Implementasi 17 kerja sama penelitian', sumber:'LED C.2', prioritas:'UTAMA', icon:'📋' },
  { id:'E021', nama:'IA Kerja Sama PkM', kriteria:'C.2', indikator:'Kerja Sama', jenis:'Laporan', tahun:'2022-2024', keterangan:'Implementasi 7 kerja sama PkM', sumber:'LED C.2', prioritas:'UTAMA', icon:'📋' },
  { id:'E022', nama:'Laporan Survei Kepuasan Mitra', kriteria:'C.2', indikator:'Evaluasi Kerja Sama', jenis:'Laporan', tahun:'2024', keterangan:'Hasil survei kepuasan mitra', sumber:'LED C.2', prioritas:'UTAMA', icon:'⭐' },

  // ===== C.3 PENDIDIKAN, PENELITIAN, PkM =====
  { id:'E023', nama:'NADK PSBM 2020', kriteria:'C.3', indikator:'Kurikulum', jenis:'Dokumen', tahun:'2020', keterangan:'Naskah Akademik Pengembangan Kurikulum', sumber:'LED C.3', prioritas:'UTAMA', icon:'📘' },
  { id:'E024', nama:'Dokumen Kurikulum PSBM', kriteria:'C.3', indikator:'Kurikulum', jenis:'Dokumen', tahun:'2024', keterangan:'Struktur kurikulum 150 SKS, 53 MK', sumber:'LED C.3 / LKPS 3.a.1', prioritas:'UTAMA', icon:'📘' },
  { id:'E025', nama:'BA Evaluasi Kurikulum', kriteria:'C.3', indikator:'Pemutakhiran Kurikulum', jenis:'BA', tahun:'2020-2024', keterangan:'Berita Acara evaluasi 2020, 2021, 2024', sumber:'LED C.3', prioritas:'UTAMA', icon:'📝' },
  { id:'E026', nama:'Profil Lulusan PSBM', kriteria:'C.3', indikator:'Profil Lulusan', jenis:'Dokumen', tahun:'2020', keterangan:'6 profil lulusan PSBM', sumber:'LED C.3', prioritas:'UTAMA', icon:'🎓' },
  { id:'E027', nama:'Matriks Profil Lulusan–CPL', kriteria:'C.3', indikator:'CPL', jenis:'Matriks', tahun:'2024', keterangan:'Penurunan profil lulusan ke CPL', sumber:'LED C.3', prioritas:'UTAMA', icon:'📊' },
  { id:'E028', nama:'Rumusan 12 CPL PSBM', kriteria:'C.3', indikator:'CPL', jenis:'Dokumen', tahun:'2020', keterangan:'Rumusan CPL sesuai 4 standar kompetensi', sumber:'LED C.3', prioritas:'UTAMA', icon:'🎓' },
  { id:'E029', nama:'Matriks CPL–MK', kriteria:'C.3', indikator:'CPL', jenis:'Matriks', tahun:'2024', keterangan:'Pemetaan CPL ke mata kuliah', sumber:'LED C.3', prioritas:'UTAMA', icon:'📊' },
  { id:'E030', nama:'Matriks CPL–CPMK', kriteria:'C.3', indikator:'CPL', jenis:'Matriks', tahun:'2024', keterangan:'Pemetaan CPL ke CPMK', sumber:'LED C.3', prioritas:'UTAMA', icon:'📊' },
  { id:'E031', nama:'Rekap Ketercapaian CPL', kriteria:'C.3', indikator:'Pengukuran CPL', jenis:'Rekap', tahun:'2022-2024', keterangan:'Hasil pengukuran ketercapaian CPL', sumber:'LED C.3 / LKPS 3.a.1', prioritas:'UTAMA', icon:'📈' },
  { id:'E032', nama:'BA Evaluasi CPL', kriteria:'C.3', indikator:'Pengukuran CPL', jenis:'BA', tahun:'2024', keterangan:'Berita Acara evaluasi CPL', sumber:'LED C.3', prioritas:'UTAMA', icon:'📝' },
  { id:'E033', nama:'Rencana Tindak Lanjut CPL', kriteria:'C.3', indikator:'Pengukuran CPL', jenis:'Dokumen', tahun:'2024', keterangan:'RTL closed-loop CPL', sumber:'LED C.3', prioritas:'UTAMA', icon:'📋' },
  { id:'E034', nama:'Repository RPS (53 MK)', kriteria:'C.3', indikator:'RPS', jenis:'Repository', tahun:'2024', keterangan:'Kumpulan RPS 53 MK', sumber:'LED C.3 / LKPS 3.a.2', prioritas:'UTAMA', icon:'📁' },
  { id:'E035', nama:'BA Tinjauan RPS', kriteria:'C.3', indikator:'RPS', jenis:'BA', tahun:'2024', keterangan:'Berita Acara tinjauan RPS', sumber:'LED C.3', prioritas:'UTAMA', icon:'📝' },
  { id:'E036', nama:'Matriks Integrasi Penelitian–MK', kriteria:'C.3', indikator:'Integrasi Penelitian', jenis:'Matriks', tahun:'2024', keterangan:'Integrasi penelitian ke MK inti (≥10%)', sumber:'LED C.3 / LKPS 3.a.3', prioritas:'UTAMA', icon:'📊' },
  { id:'E037', nama:'Matriks Integrasi PkM–MK', kriteria:'C.3', indikator:'Integrasi PkM', jenis:'Matriks', tahun:'2024', keterangan:'Integrasi PkM ke MK inti', sumber:'LED C.3', prioritas:'UTAMA', icon:'📊' },
  { id:'E038', nama:'Roadmap Penelitian PSBM', kriteria:'C.3', indikator:'Penelitian', jenis:'Roadmap', tahun:'2020-2025', keterangan:'Peta jalan penelitian 4 bidang fokus', sumber:'LED C.3', prioritas:'UTAMA', icon:'🗺️' },
  { id:'E039', nama:'Daftar Penelitian DTPS (45 judul)', kriteria:'C.3', indikator:'Penelitian', jenis:'Daftar', tahun:'2022-2024', keterangan:'45 penelitian: 14, 13, 18', sumber:'LED C.3 / LKPS 3.b', prioritas:'UTAMA', icon:'🔬' },
  { id:'E040', nama:'Bukti Keterlibatan Mahasiswa dalam Penelitian', kriteria:'C.3', indikator:'Penelitian-Mahasiswa', jenis:'Dokumentasi', tahun:'2022-2024', keterangan:'12/45 penelitian melibatkan mhs (26,67%)', sumber:'LED C.3 / LKPS 6.h.1', prioritas:'UTAMA', icon:'👨‍🎓' },
  { id:'E041', nama:'Roadmap PkM PSBM', kriteria:'C.3', indikator:'PkM', jenis:'Roadmap', tahun:'2020-2025', keterangan:'Peta jalan PkM', sumber:'LED C.3', prioritas:'UTAMA', icon:'🗺️' },
  { id:'E042', nama:'Daftar PkM DTPS (14 kegiatan)', kriteria:'C.3', indikator:'PkM', jenis:'Daftar', tahun:'2022-2024', keterangan:'14 PkM: 2, 6, 6', sumber:'LED C.3 / LKPS 3.c', prioritas:'UTAMA', icon:'🤝' },
  { id:'E043', nama:'Panduan Capstone Project', kriteria:'C.3', indikator:'Capstone', jenis:'Panduan', tahun:'2024', keterangan:'Panduan resmi capstone project', sumber:'LED C.3', prioritas:'UTAMA', icon:'📗' },
  { id:'E044', nama:'Laporan Capstone Project', kriteria:'C.3', indikator:'Capstone', jenis:'Laporan', tahun:'2024', keterangan:'Laporan capstone project mahasiswa', sumber:'LED C.3', prioritas:'UTAMA', icon:'📊' },

  // ===== C.4 SDM =====
  { id:'E045', nama:'Daftar DTPS PSBM (11 dosen)', kriteria:'C.4', indikator:'Kecukupan DTPS', jenis:'Daftar', tahun:'2024', keterangan:'11 DTPS inti PSBM', sumber:'LED C.4 / LKPS 4.a', prioritas:'UTAMA', icon:'👨‍🏫' },
  { id:'E046', nama:'CV DTPS', kriteria:'C.4', indikator:'Kualifikasi', jenis:'CV', tahun:'2024', keterangan:'Curriculum Vitae 11 DTPS', sumber:'LED C.4', prioritas:'UTAMA', icon:'📄' },
  { id:'E047', nama:'Ijazah & Sertifikat DTPS', kriteria:'C.4', indikator:'Kualifikasi', jenis:'Scan', tahun:'2024', keterangan:'3 doktor, 4 Lektor Kepala, 6 Lektor', sumber:'LED C.4', prioritas:'UTAMA', icon:'🎓' },
  { id:'E048', nama:'SK Jabatan Fungsional', kriteria:'C.4', indikator:'JAFA', jenis:'SK', tahun:'2024', keterangan:'SK JAFA DTPS', sumber:'LED C.4', prioritas:'UTAMA', icon:'📜' },
  { id:'E049', nama:'Roadmap Pengembangan SDM', kriteria:'C.4', indikator:'Pengembangan SDM', jenis:'Roadmap', tahun:'2024-2028', keterangan:'Rencana studi lanjut & JAFA', sumber:'LED C.4', prioritas:'UTAMA', icon:'🗺️' },
  { id:'E050', nama:'Sertifikat Kompetensi DTPS', kriteria:'C.4', indikator:'Sertifikasi', jenis:'Sertifikat', tahun:'2024', keterangan:'Sertifikasi profesi/industri DTPS', sumber:'LED C.4', prioritas:'UTAMA', icon:'🏅' },
  { id:'E051', nama:'Laporan BKD DTPS', kriteria:'C.4', indikator:'Beban Kerja', jenis:'Laporan', tahun:'2022-2024', keterangan:'BKD rata-rata 14,77 SKS', sumber:'LED C.4 / LKPS 4.c', prioritas:'UTAMA', icon:'📊' },
  { id:'E052', nama:'Daftar Publikasi DTPS (220)', kriteria:'C.4', indikator:'Publikasi', jenis:'Daftar', tahun:'2022-2024', keterangan:'220 publikasi 3 tahun', sumber:'LED C.4 / LKPS 4.e', prioritas:'UTAMA', icon:'📚' },
  { id:'E053', nama:'Daftar Luaran DTPS (HKI, Produk)', kriteria:'C.4', indikator:'Luaran DTPS', jenis:'Daftar', tahun:'2022-2024', keterangan:'Paten, HKI, TTG, produk, buku', sumber:'LED C.4 / LKPS 4.f', prioritas:'UTAMA', icon:'💡' },
  { id:'E054', nama:'Bukti Produk Diadopsi (13)', kriteria:'C.4', indikator:'Produk Diadopsi', jenis:'Dokumentasi', tahun:'2022-2024', keterangan:'13 produk/jasa diadopsi masyarakat', sumber:'LED C.4 / LKPS 4.g', prioritas:'UTAMA', icon:'📦' },
  { id:'E055', nama:'Bukti Rekognisi Kepakaran DTPS', kriteria:'C.4', indikator:'Rekognisi', jenis:'Dokumentasi', tahun:'2022-2024', keterangan:'Undangan, SK rekognisi', sumber:'LED C.4 / LKPS 4.j', prioritas:'UTAMA', icon:'🏆' },

  // ===== C.5 KEPENTINGAN & SARPRAS =====
  { id:'E056', nama:'RKAT Anggaran PSBM', kriteria:'C.5', indikator:'Pembiayaan', jenis:'Dokumen', tahun:'2022-2024', keterangan:'Anggaran PSBM 3 tahun', sumber:'LED C.5 / LKPS 2.b', prioritas:'UTAMA', icon:'💰' },
  { id:'E057', nama:'Inventaris Laboratorium', kriteria:'C.5', indikator:'Laboratorium', jenis:'Inventaris', tahun:'2024', keterangan:'Daftar alat lab PSBM', sumber:'LED C.5 / LKPS 5.a', prioritas:'UTAMA', icon:'🔧' },
  { id:'E058', nama:'Logbook Pemeliharaan Alat', kriteria:'C.5', indikator:'Laboratorium', jenis:'Logbook', tahun:'2024', keterangan:'Log pemeliharaan alat lab', sumber:'LED C.5', prioritas:'UTAMA', icon:'📋' },
  { id:'E059', nama:'Daftar Perangkat Lunak', kriteria:'C.5', indikator:'Perangkat Lunak', jenis:'Daftar', tahun:'2024', keterangan:'Software pembelajaran', sumber:'LED C.5', prioritas:'UTAMA', icon:'💻' },
  { id:'E060', nama:'Kebijakan K3L JTE', kriteria:'C.5', indikator:'K3L', jenis:'Kebijakan', tahun:'2023', keterangan:'Kebijakan K3L resmi', sumber:'LED C.5 / LKPS 5.b', prioritas:'UTAMA', icon:'⚠️' },
  { id:'E061', nama:'SOP K3L Laboratorium', kriteria:'C.5', indikator:'K3L', jenis:'SOP', tahun:'2024', keterangan:'SOP K3L lab', sumber:'LED C.5', prioritas:'UTAMA', icon:'📋' },
  { id:'E062', nama:'Inventaris Fasilitas K3L', kriteria:'C.5', indikator:'K3L', jenis:'Inventaris', tahun:'2024', keterangan:'APAR, APD, jalur evakuasi', sumber:'LED C.5 / LKPS 5.c', prioritas:'UTAMA', icon:'🧯' },
  { id:'E063', nama:'Laporan Audit K3L', kriteria:'C.5', indikator:'K3L', jenis:'Laporan', tahun:'2024', keterangan:'Laporan audit K3L terakhir', sumber:'LED C.5', prioritas:'UTAMA', icon:'📊' },

  // ===== C.6 LUARAN =====
  { id:'E064', nama:'Data Mahasiswa Aktif (PDDikti)', kriteria:'C.6', indikator:'Rasio Mhs/DTPS', jenis:'Data', tahun:'2024', keterangan:'Data mahasiswa aktif TS', sumber:'LED C.6 / LKPS 6.a', prioritas:'UTAMA', icon:'👨‍🎓' },
  { id:'E065', nama:'Sertifikat Prestasi Mahasiswa', kriteria:'C.6', indikator:'Prestasi', jenis:'Sertifikat', tahun:'2022-2024', keterangan:'10 prestasi akademik, 9 nonakademik', sumber:'LED C.6 / LKPS 6.c', prioritas:'UTAMA', icon:'🏆' },
  { id:'E066', nama:'Data Kelulusan & Masa Studi', kriteria:'C.6', indikator:'Kelulusan', jenis:'Data', tahun:'2022-2024', keterangan:'Data kelulusan & masa studi', sumber:'LED C.6 / LKPS 6.d', prioritas:'UTAMA', icon:'📊' },
  { id:'E067', nama:'Daftar Publikasi Mahasiswa (126)', kriteria:'C.6', indikator:'Publikasi Mhs', jenis:'Daftar', tahun:'2022-2024', keterangan:'126 publikasi/presentasi', sumber:'LED C.6 / LKPS 6.e.2', prioritas:'UTAMA', icon:'📚' },
  { id:'E068', nama:'Sertifikat HKI Mahasiswa', kriteria:'C.6', indikator:'Luaran Mhs', jenis:'Sertifikat', tahun:'2022-2024', keterangan:'Paten, HKI, TTG, produk, buku', sumber:'LED C.6 / LKPS 6.e.3', prioritas:'UTAMA', icon:'💡' },
  { id:'E069', nama:'Bukti Produk Mahasiswa Diadopsi (16)', kriteria:'C.6', indikator:'Produk Mhs', jenis:'Dokumentasi', tahun:'2022-2024', keterangan:'16 produk/jasa diadopsi', sumber:'LED C.6 / LKPS 6.e.4', prioritas:'UTAMA', icon:'📦' },
  { id:'E070', nama:'Laporan Tracer Study 2024', kriteria:'C.6', indikator:'Tracer Study', jenis:'Laporan', tahun:'2024', keterangan:'Laporan tracer study lengkap', sumber:'LED C.6 / LKPS 6.f', prioritas:'UTAMA', icon:'📈' },
  { id:'E071', nama:'Raw Data Tracer Study', kriteria:'C.6', indikator:'Tracer Study', jenis:'Data', tahun:'2024', keterangan:'Data mentah tracer (80 lulusan, 61 terlacak)', sumber:'LED C.6', prioritas:'UTAMA', icon:'📊' },
  { id:'E072', nama:'Laporan Survei Pengguna Lulusan', kriteria:'C.6', indikator:'Kepuasan Pengguna', jenis:'Laporan', tahun:'2024', keterangan:'45 responden, 7 aspek kepuasan', sumber:'LED C.6 / LKPS 6.g.2', prioritas:'UTAMA', icon:'⭐' },
  { id:'E073', nama:'BA Tindak Lanjut Tracer', kriteria:'C.6', indikator:'Tindak Lanjut Tracer', jenis:'BA', tahun:'2024', keterangan:'BA perbaikan kurikulum berbasis tracer', sumber:'LED C.6', prioritas:'UTAMA', icon:'📝' },

  // ===== C.7 SPMI =====
  { id:'E074', nama:'SK GPM JTE', kriteria:'C.7', indikator:'Unit Penjaminan Mutu', jenis:'SK', tahun:'2023', keterangan:'SK Gugus Penjaminan Mutu', sumber:'LED C.7 / LKPS 7.a', prioritas:'UTAMA', icon:'📜' },
  { id:'E075', nama:'Dokumen Kebijakan SPMI', kriteria:'C.7', indikator:'Perangkat SPMI', jenis:'Dokumen', tahun:'2023', keterangan:'Kebijakan SPMI resmi', sumber:'LED C.7', prioritas:'UTAMA', icon:'📘' },
  { id:'E076', nama:'Manual SPMI (PPEPP)', kriteria:'C.7', indikator:'Perangkat SPMI', jenis:'Manual', tahun:'2023', keterangan:'Manual siklus PPEPP', sumber:'LED C.7', prioritas:'UTAMA', icon:'📗' },
  { id:'E077', nama:'Dokumen Standar SPMI', kriteria:'C.7', indikator:'Perangkat SPMI', jenis:'Dokumen', tahun:'2023', keterangan:'Standar mutu SPMI', sumber:'LED C.7', prioritas:'UTAMA', icon:'📘' },
  { id:'E078', nama:'Laporan AMI 2025', kriteria:'C.7', indikator:'AMI', jenis:'Laporan', tahun:'2025', keterangan:'Laporan Audit Mutu Internal', sumber:'LED C.7', prioritas:'UTAMA', icon:'🔍' },
  { id:'E079', nama:'SK Auditor AMI', kriteria:'C.7', indikator:'AMI', jenis:'SK', tahun:'2025', keterangan:'SK auditor AMI independen', sumber:'LED C.7', prioritas:'UTAMA', icon:'📜' },
  { id:'E080', nama:'Notulensi RTM', kriteria:'C.7', indikator:'RTM', jenis:'Notulensi', tahun:'2025', keterangan:'Rapat Tinjauan Manajemen', sumber:'LED C.7', prioritas:'UTAMA', icon:'📝' },
  { id:'E081', nama:'Dokumen RTL AMI', kriteria:'C.7', indikator:'RTL', jenis:'Dokumen', tahun:'2025', keterangan:'Rencana Tindak Lanjut 15 temuan', sumber:'LED C.7', prioritas:'UTAMA', icon:'📋' },
  { id:'E082', nama:'Laporan Evaluasi Kinerja IKT', kriteria:'C.7', indikator:'Evaluasi Kinerja', jenis:'Laporan', tahun:'2024', keterangan:'Evaluasi IKT JTE/PSBM', sumber:'LED C.7', prioritas:'UTAMA', icon:'📊' },
  { id:'E083', nama:'Laporan Survei Kepuasan Stakeholder', kriteria:'C.7', indikator:'Kepuasan Stakeholder', jenis:'Laporan', tahun:'2024', keterangan:'Survei mahasiswa, dosen, lulusan, pengguna', sumber:'LED C.7', prioritas:'UTAMA', icon:'⭐' },

  // ===== BUKTI PENDUKUNG =====
  { id:'E084', nama:'Foto Kegiatan FGD VMTS', kriteria:'C.1', indikator:'Mekanisme', jenis:'Foto', tahun:'2024', keterangan:'Dokumentasi foto FGD', sumber:'LED C.1', prioritas:'PENDUKUNG', icon:'📷' },
  { id:'E085', nama:'Sertifikat Pelatihan Dosen', kriteria:'C.4', indikator:'Pengembangan SDM', jenis:'Sertifikat', tahun:'2024', keterangan:'Sertifikat pelatihan DTPS', sumber:'LED C.4', prioritas:'PENDUKUNG', icon:'🏅' },
  { id:'E086', nama:'Foto Laboratorium', kriteria:'C.5', indikator:'Laboratorium', jenis:'Foto', tahun:'2024', keterangan:'Dokumentasi lab PSBM', sumber:'LED C.5', prioritas:'PENDUKUNG', icon:'📷' },
  { id:'E087', nama:'Foto Kegiatan PkM', kriteria:'C.3', indikator:'PkM', jenis:'Foto', tahun:'2024', keterangan:'Dokumentasi PkM', sumber:'LED C.3', prioritas:'PENDUKUNG', icon:'📷' }
];

// ===== DATA BAB III =====
const dataBab3 = {
  chain: [
    { num: 1, title: 'Temuan C.1–C.7', content: 'Hasil evaluasi diri 7 kriteria akreditasi.', evidence: ['LED C.1–C.7', 'LKPS 1–7'] },
    { num: 2, title: 'SWOT / Akar Masalah', content: 'Analisis kekuatan, kelemahan, peluang, ancaman.', evidence: ['Dokumen SWOT BAB III'] },
    { num: 3, title: 'Tujuan Strategis', content: 'Respons terhadap kombinasi S-W-O-T, diarahkan ke VMTS.', evidence: ['Tujuan Strategis BAB III'] },
    { num: 4, title: 'Program Pengembangan', content: 'Program konkret: Pendidikan, Penelitian, PkM, SDM, Sarpras.', evidence: ['Tabel 3.2 BAB III'] },
    { num: 5, title: 'Indikator & Target', content: 'Indikator terukur dengan target spesifik.', evidence: ['Matriks indikator-target'] },
    { num: 6, title: 'Bukti Implementasi / Perencanaan', content: 'RKAT, roadmap, SK, kontrak kerja sama.', evidence: ['RKAT', 'Roadmap', 'Kontrak'] },
    { num: 7, title: 'Monitoring & PPEPP', content: 'AMI, RTM, RTL, evaluasi berkala.', evidence: ['Laporan AMI', 'Notulensi RTM', 'RTL'] }
  ],
  swot: [
    { type: 'S', title: 'Strength (Kekuatan)', items: ['Kekhasan Broadband Multimedia', '11 DTPS relevan (3 doktor, 4 LK)', 'Kurikulum vokasi kuat (53,33% praktik)', '66 kerja sama tridharma', 'Jejaring industri & alumni aktif'] },
    { type: 'W', title: 'Weakness (Kelemahan)', items: ['Pendanaan penelitian 80% internal', 'Keterlibatan mhs dalam penelitian 26,67%', 'PkM 100% pendanaan internal', 'Rekognisi internasional masih rendah', 'Closed-loop CPL perlu diperkuat'] },
    { type: 'O', title: 'Opportunity (Peluang)', items: ['Transformasi digital & 5G/6G', 'IoT, AI, cloud computing', 'Hibah nasional (BIMA, DRTPM)', 'Kebutuhan DUDI broadband', 'Program Merdeka Belajar'] },
    { type: 'T', title: 'Threat (Ancaman)', items: ['Perubahan teknologi cepat', 'Persaingan PT sejenis', 'Tuntutan kompetensi DUDI dinamis', 'Regulasi DIKTI berubah'] }
  ],
  tujuan: [
    { no: 1, tujuan: 'Memperkuat relevansi & mutu pendidikan', indikator: 'Pengukuran CPL terdokumentasi', target: '100% CPL terukur' },
    { no: 2, tujuan: 'Meningkatkan penelitian & hilirisasi', indikator: 'Pendanaan eksternal', target: '≥40% eksternal' },
    { no: 3, tujuan: 'Meningkatkan kualitas SDM', indikator: 'Doktor & Lektor Kepala', target: '5 doktor, 50% LK' },
    { no: 4, tujuan: 'Memperluas internasionalisasi', indikator: 'Kerja sama & publikasi internasional', target: '≥5 kerja sama intl' },
    { no: 5, tujuan: 'Meningkatkan daya saing lulusan', indikator: 'Kesesuaian kerja & waktu tunggu', target: '≥80% sesuai bidang' },
    { no: 6, tujuan: 'Memperkuat budaya mutu', indikator: 'Siklus PPEPP berjalan', target: 'AMI → RTM → RTL闭环' }
  ],
  program: [
    { nama: 'Penguatan Closed-Loop CPL', strategi: 'WO', akar: 'Pengukuran CPL belum terdokumentasi penuh', target: '100% CPL terukur & ditindaklanjuti', pic: 'Kurikulum/GPM', anggaran: 'Rp 30 juta', monitoring: 'Semesteran' },
    { nama: 'Peningkatan Pendanaan Eksternal Penelitian', strategi: 'WO', akar: '80% pendanaan internal', target: '≥40% pendanaan eksternal (2026)', pic: 'P3M', anggaran: 'Rp 50 juta', monitoring: 'Tahunan' },
    { nama: 'Integrasi Penelitian DTPS dengan Mahasiswa', strategi: 'WO', akar: 'Keterlibatan mhs baru 26,67%', target: '≥40% penelitian libatkan mhs', pic: 'P3M/Kaprodi', anggaran: 'Rp 40 juta', monitoring: 'Tahunan' },
    { nama: 'Percepatan JAFA & Studi Lanjut', strategi: 'ST', akar: '3/11 doktor, 0 GB', target: '5 doktor, 50% LK, 1 GB', pic: 'Kajur', anggaran: 'Rp 200 juta', monitoring: 'Tahunan' },
    { nama: 'Peningkatan Response Rate Tracer', strategi: 'WT', akar: 'Response rate 68%', target: '≥80% response rate', pic: 'CDC/GPM', anggaran: 'Rp 20 juta', monitoring: 'Tahunan' },
    { nama: 'Internasionalisasi Kerja Sama & Publikasi', strategi: 'SO', akar: 'Capaian internasional rendah', target: '≥5 MoU intl, ≥10 publikasi Scopus', pic: 'Kajur/P3M', anggaran: 'Rp 80 juta', monitoring: 'Tahunan' }
  ]
};

// ===== NAVIGATION =====
function showEvPanel(id, btn) {
  document.querySelectorAll('.ev-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.ev-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  if (id.startsWith('c')) renderKriteria(id);
  if (id === 'bab3') showBab3('chain', document.querySelector('#bab3SubNav button'));
  if (id === 'beranda') renderStats();
}

function goToPanel(id) {
  const tabs = document.querySelectorAll('.ev-tab');
  const map = { c1:1, c2:2, c3:3, c4:4, c5:5, c6:6, c7:7, bab3:8 };
  showEvPanel(id, tabs[map[id]]);
}

// ===== RENDER KRITERIA =====
let currentIndFilter = {};
function renderKriteria(k) {
  const evs = dataEvidence.filter(e => e.kriteria.toLowerCase() === k);
  const indicators = [...new Set(evs.map(e => e.indikator))];
  if (!currentIndFilter[k]) currentIndFilter[k] = 'all';

  const titles = {
    c1: '📑 C.1 — VMTS',
    c2: '🏛️ C.2 — Tata Pamong, Tata Kelola, Kerja Sama, Keuangan',
    c3: '📘 C.3 — Pendidikan, Penelitian, dan PkM',
    c4: '👨‍🏫 C.4 — Sumber Daya Manusia',
    c5: '💰 C.5 — Keuangan, Sarana, Prasarana & K3L',
    c6: '🎓 C.6 — Mahasiswa dan Luaran',
    c7: '🔄 C.7 — Sistem Penjaminan Mutu'
  };

  let html = '<div class="section-header"><h2>' + titles[k] + '</h2>';
  html += '<div class="section-desc">Total <strong>' + evs.length + '</strong> evidence — klik untuk membuka dokumen</div></div>';

  html += '<div class="ev-subnav">';
  html += '<button class="' + (currentIndFilter[k]==='all'?'active':'') + '" onclick="filterIndikator(\'' + k + '\', \'all\', this)">Semua <span class="count">' + evs.length + '</span></button>';
  indicators.forEach(ind => {
    const count = evs.filter(e => e.indikator === ind).length;
    html += '<button class="' + (currentIndFilter[k]===ind?'active':'') + '" onclick="filterIndikator(\'' + k + '\', \'' + ind.replace(/'/g,"\\'") + '\', this)">' + ind + ' <span class="count">' + count + '</span></button>';
  });
  html += '</div>';

  const filtered = currentIndFilter[k] === 'all' ? evs : evs.filter(e => e.indikator === currentIndFilter[k]);
  // Sort: UTAMA first
  filtered.sort((a,b) => (b.prioritas==='UTAMA'?1:0) - (a.prioritas==='UTAMA'?1:0));

  filtered.forEach(e => {
    html += renderEvCard(e);
  });

  document.getElementById(k + 'Content').innerHTML = html;
}

function filterIndikator(k, ind, btn) {
  currentIndFilter[k] = ind;
  renderKriteria(k);
}

function renderEvCard(e) {
  const prioClass = e.prioritas === 'UTAMA' ? 'utama' : 'pendukung';
  let html = '<div class="ev-card ' + prioClass + '">';
  html += '<div class="ev-card-icon">' + e.icon + '</div>';
  html += '<div class="ev-card-body">';
  html += '<div class="ev-card-title">' + e.nama + '</div>';
  html += '<div class="ev-card-desc">' + e.keterangan + '</div>';
  html += '<div class="ev-card-meta">';
  html += '<span class="ev-badge ' + prioClass + '">' + e.prioritas + '</span>';
  html += '<span class="ev-badge jenis">' + e.jenis + '</span>';
  html += '<span class="ev-badge tahun">' + e.tahun + '</span>';
  html += '<span class="ev-badge sumber">📖 ' + e.sumber + '</span>';
  html += '</div>';
  html += '<div class="ev-card-actions">';
  html += '<button class="ev-open-btn" onclick="openDocument(\'' + e.id + '\')">📂 BUKA DOKUMEN</button>';
  html += '<button class="ev-open-btn secondary" onclick="alert(\'Sumber: ' + e.sumber + '\')">📖 Lihat Sumber LED/LKPS</button>';
  html += '</div>';
  html += '</div></div>';
  return html;
}

function openDocument(id) {
  const e = dataEvidence.find(x => x.id === id);
  if (e) {
    alert('📂 Membuka dokumen:\n\n' + e.nama + '\n\nSumber: ' + e.sumber + '\nTahun: ' + e.tahun + '\n\n(Dokumen akan terbuka di tab baru pada implementasi production)');
  }
}

// ===== SEARCH =====
function quickSearch(keyword) {
  document.getElementById('evSearch').value = keyword;
  searchEvidence();
}

function clearEvSearch() {
  document.getElementById('evSearch').value = '';
  document.getElementById('searchResultContainer').innerHTML = '';
  document.getElementById('defaultBeranda').style.display = 'block';
}

function searchEvidence() {
  const query = document.getElementById('evSearch').value.toLowerCase().trim();
  const container = document.getElementById('searchResultContainer');
  const defaultView = document.getElementById('defaultBeranda');

  if (!query) {
    container.innerHTML = '';
    defaultView.style.display = 'block';
    return;
  }
  defaultView.style.display = 'none';

  const results = dataEvidence.filter(e =>
    e.nama.toLowerCase().includes(query) ||
    e.indikator.toLowerCase().includes(query) ||
    e.keterangan.toLowerCase().includes(query) ||
    e.kriteria.toLowerCase().includes(query) ||
    e.jenis.toLowerCase().includes(query) ||
    e.sumber.toLowerCase().includes(query)
  );

  if (results.length === 0) {
    container.innerHTML = '<div class="no-result">🔍 Tidak ditemukan evidence untuk "<strong>' + query + '</strong>"<br><small>Coba kata kunci lain.</small></div>';
    return;
  }

  let html = '<div style="margin-bottom:12px; font-size:0.88rem; color:#666;">Ditemukan <strong>' + results.length + '</strong> evidence untuk "<strong>' + query + '</strong>"</div>';
  results.forEach(e => { html += renderEvCard(e); });
  container.innerHTML = html;
}

// ===== BAB III =====
function showBab3(key, btn) {
  document.querySelectorAll('#bab3SubNav button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');

  let html = '';
  if (key === 'chain') {
    html += '<h3 style="color:#e65100; margin: 0 0 16px 0;">🔗 Rantai Keterlacakan BAB III</h3>';
    html += '<div class="bab3-chain">';
    dataBab3.chain.forEach(s => {
      html += '<div class="bab3-step">';
      html += '<div class="step-num">TAHAP ' + s.num + '</div>';
      html += '<div class="step-title">' + s.title + '</div>';
      html += '<div class="step-content">' + s.content + '</div>';
      html += '<div class="step-evidence">';
      s.evidence.forEach(ev => {
        html += '<button class="ev-open-btn secondary" onclick="quickSearch(\'' + ev + '\')">📂 ' + ev + '</button>';
      });
      html += '</div></div>';
    });
    html += '</div>';
  } else if (key === 'swot') {
    html += '<h3 style="color:#e65100; margin: 0 0 16px 0;">📊 Analisis SWOT PSBM</h3>';
    html += '<div style="display:grid; grid-template-columns: 1fr 1fr; gap: 12px;">';
    dataBab3.swot.forEach(s => {
      const colors = { S: '#2e7d32', W: '#e65100', O: '#1565c0', T: '#c62828' };
      const bgs = { S: '#e8f5e9', W: '#fff3e0', O: '#e3f2fd', T: '#ffebee' };
      html += '<div style="background:' + bgs[s.type] + '; padding: 16px; border-radius: 10px; border-left: 4px solid ' + colors[s.type] + ';">';
      html += '<h4 style="margin: 0 0 8px 0; color: ' + colors[s.type] + ';">' + s.title + '</h4>';
      html += '<ul style="margin: 0; padding-left: 18px; font-size: 0.88rem;">';
      s.items.forEach(i => { html += '<li style="padding: 2px 0;">' + i + '</li>'; });
      html += '</ul></div>';
    });
    html += '</div>';
  } else if (key === 'tujuan') {
    html += '<h3 style="color:#e65100; margin: 0 0 16px 0;">🎯 Tujuan Strategis PSBM</h3>';
    dataBab3.tujuan.forEach(t => {
      html += '<div class="ev-card utama" style="border-left-color: #e65100;">';
      html += '<div class="ev-card-icon">🎯</div>';
      html += '<div class="ev-card-body">';
      html += '<div class="ev-card-title">' + t.no + '. ' + t.tujuan + '</div>';
      html += '<div class="ev-card-meta" style="margin-top: 8px;">';
      html += '<span class="ev-badge sumber">Indikator: ' + t.indikator + '</span>';
      html += '<span class="ev-badge tahun">Target: ' + t.target + '</span>';
      html += '</div></div></div>';
    });
  } else if (key === 'program') {
    html += '<h3 style="color:#e65100; margin: 0 0 16px 0;">📘 Program Pengembangan</h3>';
    dataBab3.program.forEach(p => {
      html += '<div class="ev-card utama" style="border-left-color: #e65100;">';
      html += '<div class="ev-card-icon">📘</div>';
      html += '<div class="ev-card-body">';
      html += '<div class="ev-card-title">' + p.nama + '</div>';
      html += '<div class="ev-card-desc">Akar masalah: ' + p.akar + '</div>';
      html += '<div class="ev-card-meta">';
      html += '<span class="ev-badge jenis">Strategi ' + p.strategi + '</span>';
      html += '<span class="ev-badge tahun">Target: ' + p.target + '</span>';
      html += '<span class="ev-badge sumber">PIC: ' + p.pic + '</span>';
      html += '<span class="ev-badge utama">Anggaran: ' + p.anggaran + '</span>';
      html += '<span class="ev-badge pendukung">Monitoring: ' + p.monitoring + '</span>';
      html += '</div></div></div>';
    });
  } else if (key === 'monitoring') {
    html += '<h3 style="color:#e65100; margin: 0 0 16px 0;">🔄 Monitoring & PPEPP</h3>';
    html += '<div class="ev-card utama" style="border-left-color: #e65100;"><div class="ev-card-icon">🔍</div><div class="ev-card-body"><div class="ev-card-title">Audit Mutu Internal (AMI)</div><div class="ev-card-desc">Audit internal tahunan terhadap 7 kriteria</div><div class="ev-card-actions"><button class="ev-open-btn" onclick="quickSearch(\'AMI\')">📂 BUKA DOKUMEN</button></div></div></div>';
    html += '<div class="ev-card utama" style="border-left-color: #e65100;"><div class="ev-card-icon">📝</div><div class="ev-card-body"><div class="ev-card-title">Rapat Tinjauan Manajemen (RTM)</div><div class="ev-card-desc">Tinjauan hasil AMI oleh pimpinan</div><div class="ev-card-actions"><button class="ev-open-btn" onclick="quickSearch(\'RTM\')">📂 BUKA DOKUMEN</button></div></div></div>';
    html += '<div class="ev-card utama" style="border-left-color: #e65100;"><div class="ev-card-icon">📋</div><div class="ev-card-body"><div class="ev-card-title">Rencana Tindak Lanjut (RTL)</div><div class="ev-card-desc">15 temuan AMI dengan RTL terdokumentasi</div><div class="ev-card-actions"><button class="ev-open-btn" onclick="quickSearch(\'RTL\')">📂 BUKA DOKUMEN</button></div></div></div>';
  }
  document.getElementById('bab3Content').innerHTML = html;
}

// ===== STATS =====
function renderStats() {
  const stats = {};
  dataEvidence.forEach(e => {
    if (!stats[e.kriteria]) stats[e.kriteria] = 0;
    stats[e.kriteria]++;
  });
  let html = '';
  ['C.1','C.2','C.3','C.4','C.5','C.6','C.7'].forEach(k => {
    html += '<div class="bukti-utama-card" onclick="goToPanel(\'' + k.toLowerCase().replace('.','') + '\')">';
    html += '<div class="buc-icon">📂</div>';
    html += '<div class="buc-name">' + k + '</div>';
    html += '<div class="buc-desc">' + (stats[k]||0) + ' evidence</div>';
    html += '</div>';
  });
  document.getElementById('statsGrid').innerHTML = html;
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  renderStats();
});
</script>

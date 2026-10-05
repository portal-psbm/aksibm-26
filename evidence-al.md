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
.ev-tab.bab3-tab { background: linear-gradient(180deg, #fff8e1 0%, #ffecb3 100%); color: #e65100; border-color: #ffcc80; }
.ev-tab.bab3-tab::before { background: linear-gradient(180deg, #ffcc80 0%, #ffb74d 100%); border-color: #ffcc80; }
.ev-tab.bab3-tab.active { background: linear-gradient(135deg, #e65100 0%, #bf360c 100%); color: white; border-color: #bf360c; }
.ev-tab.bab3-tab.active::before { background: linear-gradient(135deg, #e65100 0%, #bf360c 100%); border-color: #bf360c; }

.ev-content { background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1; border-radius: 0 0 16px 16px; padding: 28px; min-height: 500px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px; }
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

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

.ev-chips { display: flex; gap: 6px; justify-content: center; flex-wrap: wrap; margin-top: 16px; }
.ev-chip { padding: 8px 14px; background: rgba(255,255,255,0.15); border: 1px solid rgba(255,255,255,0.3); border-radius: 16px; color: white; cursor: pointer; font-weight: 600; font-size: 0.82rem; transition: all 0.2s; }
.ev-chip:hover { background: rgba(255,255,255,0.3); }
.ev-chip.bab3 { background: rgba(230, 81, 0, 0.25); border-color: rgba(255, 183, 77, 0.5); }

.bukti-section { margin: 24px 0; }
.bukti-section h3 { color: #0d47a1; margin: 0 0 14px 0; font-size: 1.1rem; display: flex; align-items: center; gap: 8px; }
.bukti-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 10px; }
.bukti-card { background: white; border: 1px solid #e0e0e0; border-left: 4px solid #0d47a1; border-radius: 8px; padding: 14px; cursor: pointer; transition: all 0.2s; }
.bukti-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); transform: translateY(-2px); border-left-color: #4caf50; }
.bukti-card .bc-icon { font-size: 1.4rem; margin-bottom: 4px; }
.bukti-card .bc-name { font-weight: 700; color: #333; font-size: 0.88rem; }
.bukti-card .bc-desc { font-size: 0.75rem; color: #666; margin-top: 2px; }

.section-header { margin-bottom: 16px; }
.section-header h2 { color: #0d47a1; margin: 0 0 4px 0; font-size: 1.2rem; }
.section-header .desc { color: #666; font-size: 0.88rem; }

.ev-subnav { display: flex; gap: 4px; margin-bottom: 16px; border-bottom: 2px solid #e0e0e0; flex-wrap: wrap; }
.ev-subnav button { padding: 8px 14px; background: transparent; border: none; cursor: pointer; font-weight: 600; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; font-size: 0.82rem; }
.ev-subnav button:hover { color: #0d47a1; background: #f8fafc; }
.ev-subnav button.active { color: #0d47a1; border-bottom-color: #0d47a1; }
.ev-subnav button .cnt { background: #e3f2fd; color: #0d47a1; padding: 2px 8px; border-radius: 10px; font-size: 0.7rem; margin-left: 4px; font-weight: 700; }
.ev-subnav button.active .cnt { background: #0d47a1; color: white; }

.ev-card { background: white; border: 1px solid #e0e0e0; border-radius: 10px; padding: 14px 16px; margin-bottom: 10px; transition: all 0.2s; display: flex; gap: 14px; align-items: flex-start; }
.ev-card:hover { box-shadow: 0 4px 14px rgba(0,0,0,0.08); transform: translateX(2px); }
.ev-card.utama { border-left: 4px solid #0d47a1; }
.ev-card.pendukung { border-left: 4px solid #90a4ae; }
.ev-card-icon { font-size: 1.6rem; min-width: 36px; text-align: center; padding-top: 2px; }
.ev-card-body { flex: 1; min-width: 0; }
.ev-card-title { font-weight: 700; color: #333; font-size: 0.92rem; margin-bottom: 4px; }
.ev-card-desc { font-size: 0.82rem; color: #555; line-height: 1.5; margin-bottom: 8px; }
.ev-card-meta { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 10px; }
.ev-badge { padding: 3px 10px; border-radius: 10px; font-size: 0.68rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.3px; }
.ev-badge.utama { background: #e3f2fd; color: #0d47a1; }
.ev-badge.pendukung { background: #eceff1; color: #546e7a; }
.ev-badge.jenis { background: #f3e5f5; color: #6a1b9a; }
.ev-badge.tahun { background: #e8f5e9; color: #2e7d32; }
.ev-badge.sumber { background: #fff8e1; color: #e65100; }
.ev-card-actions { display: flex; gap: 6px; flex-wrap: wrap; }
.ev-open-btn { padding: 6px 14px; border-radius: 6px; border: none; background: #0d47a1; color: white; font-size: 0.78rem; font-weight: 600; cursor: pointer; transition: all 0.2s; display: inline-flex; align-items: center; gap: 4px; text-decoration: none; }
.ev-open-btn:hover { background: #1565c0; transform: translateY(-1px); }
.ev-open-btn.secondary { background: white; color: #0d47a1; border: 1px solid #0d47a1; }
.ev-open-btn.secondary:hover { background: #e3f2fd; }

.bab3-chain { display: flex; flex-direction: column; gap: 0; margin: 20px 0; }
.bab3-step { background: white; padding: 16px 20px; border-left: 4px solid #e65100; position: relative; box-shadow: 0 2px 8px rgba(0,0,0,0.05); margin-bottom: 10px; border-radius: 0 8px 8px 0; border: 1px solid #e0e0e0; border-left: 4px solid #e65100; }
.bab3-step::after { content: '▼'; position: absolute; bottom: -14px; left: 50%; transform: translateX(-50%); color: #e65100; font-size: 1rem; z-index: 1; }
.bab3-step:last-child::after { display: none; }
.bab3-step .step-num { display: inline-block; background: #e65100; color: white; padding: 2px 10px; border-radius: 10px; font-size: 0.72rem; font-weight: 700; margin-bottom: 6px; }
.bab3-step .step-title { font-weight: 700; color: #e65100; margin-bottom: 4px; font-size: 0.95rem; }
.bab3-step .step-content { font-size: 0.88rem; color: #333; line-height: 1.5; }
.bab3-step .step-evidence { margin-top: 8px; display: flex; gap: 6px; flex-wrap: wrap; }

.swot-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin: 16px 0; }
.swot-card { padding: 16px; border-radius: 10px; border: 2px solid; }
.swot-card.strength { background: #e8f5e9; border-color: #4caf50; }
.swot-card.weakness { background: #fff3e0; border-color: #ff9800; }
.swot-card.opportunity { background: #e3f2fd; border-color: #2196f3; }
.swot-card.threat { background: #ffebee; border-color: #f44336; }
.swot-card h4 { margin: 0 0 8px 0; font-size: 0.9rem; }
.swot-card ul { margin: 0; padding-left: 18px; font-size: 0.85rem; }
.swot-card ul li { padding: 2px 0; }

.no-result { text-align: center; padding: 40px 20px; color: #888; background: #f8fafc; border-radius: 10px; }

.info-banner { background: #e3f2fd; border-left: 4px solid #0d47a1; padding: 12px 16px; border-radius: 6px; margin-bottom: 16px; font-size: 0.85rem; color: #0d47a1; }
.info-banner strong { color: #0a3a8a; }

@media (max-width: 767px) {
.ev-shelf { gap: 4px; padding-bottom: 8px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
.ev-shelf::-webkit-scrollbar { display: none; }
.ev-tab { min-width: 90px; flex: 0 0 auto; font-size: 0.72rem; padding: 12px 6px 16px 6px; }
.ev-content { padding: 20px; }
.ev-search-wrap { flex-direction: column; }
.ev-btn { width: 100%; }
.ev-card { flex-direction: column; }
.ev-card-icon { font-size: 1.4rem; }
.swot-grid { grid-template-columns: 1fr; }
}
</style>

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
        <div class="ev-search-wrap">
          <input type="text" class="ev-search" id="evSearch" placeholder="🔎 Cari: CPL, RPS, tracer, AMI, kerja sama, VMTS..." onkeypress="if(event.key==='Enter') searchEv()">
          <button class="ev-btn search" onclick="searchEv()"> Cari</button>
          <button class="ev-btn clear" onclick="clearEvSearch()"> Clear</button>
        </div>
        <div class="ev-chips">
          <div class="ev-chip" onclick="goToPanel('c1')">📑 C.1</div>
          <div class="ev-chip" onclick="goToPanel('c2')">🏛️ C.2</div>
          <div class="ev-chip" onclick="goToPanel('c3')">📘 C.3</div>
          <div class="ev-chip" onclick="goToPanel('c4')">👨‍ C.4</div>
          <div class="ev-chip" onclick="goToPanel('c5')">💰 C.5</div>
          <div class="ev-chip" onclick="goToPanel('c6')">🎓 C.6</div>
          <div class="ev-chip" onclick="goToPanel('c7')">🔄 C.7</div>
          <div class="ev-chip bab3" onclick="goToPanel('bab3')">📕 BAB III</div>
        </div>
      </div>

      <div id="evSearchResult"></div>

      <div id="defaultBeranda">
        <div class="info-banner">
          <strong>ℹ️ Informasi:</strong> Portal ini hanya menampilkan evidence autentik untuk asesor. Data internal (bank pertanyaan, prediksi, risiko) <strong>tidak ditampilkan</strong>.
        </div>

        <div class="bukti-section">
          <h3>⭐ Bukti Utama AL</h3>
          <div class="bukti-grid">
            <div class="bukti-card" onclick="quickEvSearch('LED Final')">
              <div class="bc-icon"></div>
              <div class="bc-name">LED Final</div>
              <div class="bc-desc">Laporan Evaluasi Diri</div>
            </div>
            <div class="bukti-card" onclick="quickEvSearch('LKPS Final')">
              <div class="bc-icon">📊</div>
              <div class="bc-name">LKPS Final</div>
              <div class="bc-desc">Laporan Kinerja PS</div>
            </div>
            <div class="bukti-card" onclick="quickEvSearch('NADK')">
              <div class="bc-icon">📘</div>
              <div class="bc-name">NADK / Kurikulum</div>
              <div class="bc-desc">Naskah Akademik</div>
            </div>
            <div class="bukti-card" onclick="quickEvSearch('CPL')">
              <div class="bc-icon">🎓</div>
              <div class="bc-name">CPL – MK</div>
              <div class="bc-desc">Matriks pemetaan</div>
            </div>
            <div class="bukti-card" onclick="quickEvSearch('RPS')">
              <div class="bc-icon">📝</div>
              <div class="bc-name">RPS</div>
              <div class="bc-desc">Rencana Pembelajaran</div>
            </div>
            <div class="bukti-card" onclick="quickEvSearch('Tracer Study')">
              <div class="bc-icon"></div>
              <div class="bc-name">Tracer Study</div>
              <div class="bc-desc">Laporan lulusan</div>
            </div>
            <div class="bukti-card" onclick="quickEvSearch('Survei Pengguna')">
              <div class="bc-icon">⭐</div>
              <div class="bc-name">Survei Pengguna</div>
              <div class="bc-desc">Kepuasan pengguna</div>
            </div>
            <div class="bukti-card" onclick="quickEvSearch('Roadmap')">
              <div class="bc-icon">🗺️</div>
              <div class="bc-name">Roadmap</div>
              <div class="bc-desc">Penelitian & PkM</div>
            </div>
            <div class="bukti-card" onclick="quickEvSearch('DTPS')">
              <div class="bc-icon">👨🏫</div>
              <div class="bc-name">Data DTPS</div>
              <div class="bc-desc">Profil dosen</div>
            </div>
            <div class="bukti-card" onclick="quickEvSearch('AMI')">
              <div class="bc-icon">🔍</div>
              <div class="bc-name">AMI – RTM – RTL</div>
              <div class="bc-desc">Audit & monitoring</div>
            </div>
          </div>
        </div>

        <div class="bukti-section">
          <h3> Ringkasan Evidence per Kriteria</h3>
          <div class="bukti-grid" id="statsGrid"></div>
        </div>
      </div>
    </div>

    <!-- ========== C.1 - C.7 ========== -->
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
        <h2 style="color:#e65100;">📕 BAB III — Program Pengembangan Berkelanjutan</h2>
        <div class="desc">Rantai keterlacakan: Temuan → SWOT → Tujuan → Program → Monitoring</div>
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
// ===== DATA EVIDENCE LENGKAP DENGAN URL =====
const dataEvidence = [
  // C.1 VMTS (11 evidence)
  { id:'E001', nama:'SK VMTS PT', k:'c1', ind:'Kekhasan VMTS', jenis:'SK', tahun:'2020', ket:'SK VMTS tingkat Politeknik Negeri Jakarta', sumber:'LED C.1', prio:'UTAMA', icon:'📜', url:'https://drive.google.com/file/d/CONTOH_ID_FILE/view?usp=sharing' },
  { id:'E002', nama:'SK VMTS UPPS (JTE)', k:'c1', ind:'Kekhasan VMTS', jenis:'SK', tahun:'2020', ket:'SK VMTS tingkat Jurusan/UPPS', sumber:'LED C.1', prio:'UTAMA', icon:'📜', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_2/view?usp=sharing' },
  { id:'E003', nama:'Dokumen Visi Keilmuan PSBM', k:'c1', ind:'Kekhasan VMTS', jenis:'Dokumen', tahun:'2020', ket:'Visi keilmuan Broadband Multimedia', sumber:'LED C.1', prio:'UTAMA', icon:'📘', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_3/view?usp=sharing' },
  { id:'E004', nama:'Matriks Sinkronisasi VMTS', k:'c1', ind:'Kekhasan VMTS', jenis:'Matriks', tahun:'2024', ket:'Linearitas visi PT → JTE → PSBM', sumber:'LED C.1', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_4/view?usp=sharing' },
  { id:'E005', nama:'SK Tim Penyusun VMTS', k:'c1', ind:'Mekanisme Penyusunan', jenis:'SK', tahun:'2020', ket:'SK tim penyusun VMTS dan visi keilmuan', sumber:'LED C.1', prio:'UTAMA', icon:'📜', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_5/view?usp=sharing' },
  { id:'E006', nama:'Undangan & Daftar Hadir FGD VMTS', k:'c1', ind:'Mekanisme Penyusunan', jenis:'Dokumentasi', tahun:'2020-2024', ket:'Bukti keterlibatan stakeholder', sumber:'LED C.1', prio:'UTAMA', icon:'📋', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E007', nama:'Notulensi & BA FGD VMTS', k:'c1', ind:'Mekanisme Penyusunan', jenis:'BA', tahun:'2020-2024', ket:'Masukan alumni, pengguna, pakar', sumber:'LED C.1', prio:'UTAMA', icon:'📝', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E008', nama:'Buku Saku VMTS', k:'c1', ind:'Sosialisasi VMTS', jenis:'Publikasi', tahun:'2024', ket:'Media sosialisasi VMTS ke stakeholder', sumber:'LED C.1', prio:'UTAMA', icon:'📗', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_8/view?usp=sharing' },
  { id:'E009', nama:'Laporan Survei Pemahaman VMTS', k:'c1', ind:'Pemahaman Stakeholder', jenis:'Laporan', tahun:'2024', ket:'Hasil survei pemahaman stakeholder (85%)', sumber:'LED C.1 / LKPS 1', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_9/view?usp=sharing' },
  { id:'E010', nama:'Renstra & Renop JTE', k:'c1', ind:'Pencapaian VMTS', jenis:'Dokumen', tahun:'2020-2025', ket:'Target dan capaian VMTS', sumber:'LED C.1', prio:'UTAMA', icon:'📘', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E011', nama:'Laporan Capaian VMTS', k:'c1', ind:'Pencapaian VMTS', jenis:'Laporan', tahun:'2024', ket:'Realisasi vs target VMTS', sumber:'LED C.1', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_11/view?usp=sharing' },

  // C.2 Tata Kelola (11 evidence)
  { id:'E012', nama:'Statuta PNJ', k:'c2', ind:'Tata Pamong', jenis:'Regulasi', tahun:'2021', ket:'Statuta Politeknik Negeri Jakarta', sumber:'LED C.2', prio:'UTAMA', icon:'📜', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_12/view?usp=sharing' },
  { id:'E013', nama:'SK OTK JTE', k:'c2', ind:'Tata Pamong', jenis:'SK', tahun:'2022', ket:'Organisasi dan Tata Kerja JTE', sumber:'LED C.2', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_13/view?usp=sharing' },
  { id:'E014', nama:'SK Pengangkatan Pimpinan JTE', k:'c2', ind:'Tata Pamong', jenis:'SK', tahun:'2022', ket:'SK Kajur, Kaprodi', sumber:'LED C.2', prio:'UTAMA', icon:'📜', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_14/view?usp=sharing' },
  { id:'E015', nama:'SOP Tata Kelola JTE', k:'c2', ind:'Tata Pamong', jenis:'SOP', tahun:'2023', ket:'SOP pengelolaan JTE', sumber:'LED C.2', prio:'UTAMA', icon:'📋', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E016', nama:'RKAT JTE 2024', k:'c2', ind:'Pengelolaan', jenis:'Dokumen', tahun:'2024', ket:'Rencana Kerja dan Anggaran', sumber:'LED C.2', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_16/view?usp=sharing' },
  { id:'E017', nama:'Laporan Realisasi Anggaran', k:'c2', ind:'Pengelolaan', jenis:'Laporan', tahun:'2022-2024', ket:'Realisasi anggaran 3 tahun', sumber:'LED C.2 / LKPS 2.b', prio:'UTAMA', icon:'', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E018', nama:'Daftar MoU Aktif (66)', k:'c2', ind:'Kerja Sama', jenis:'Daftar', tahun:'2024', ket:'66 MoU tridharma aktif', sumber:'LED C.2 / LKPS 2.a', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_18/view?usp=sharing' },
  { id:'E019', nama:'IA Kerja Sama Pendidikan (42)', k:'c2', ind:'Kerja Sama', jenis:'Laporan', tahun:'2022-2024', ket:'Implementasi 42 kerja sama pendidikan', sumber:'LED C.2', prio:'UTAMA', icon:'📋', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E020', nama:'IA Kerja Sama Penelitian (17)', k:'c2', ind:'Kerja Sama', jenis:'Laporan', tahun:'2022-2024', ket:'Implementasi 17 kerja sama penelitian', sumber:'LED C.2', prio:'UTAMA', icon:'', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E021', nama:'IA Kerja Sama PkM (7)', k:'c2', ind:'Kerja Sama', jenis:'Laporan', tahun:'2022-2024', ket:'Implementasi 7 kerja sama PkM', sumber:'LED C.2', prio:'UTAMA', icon:'📋', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E022', nama:'Laporan Survei Kepuasan Mitra', k:'c2', ind:'Evaluasi Kerja Sama', jenis:'Laporan', tahun:'2024', ket:'Hasil survei kepuasan mitra', sumber:'LED C.2', prio:'UTAMA', icon:'⭐', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_22/view?usp=sharing' },

  // C.3 Diklitpmas (22 evidence)
  { id:'E023', nama:'NADK PSBM 2020', k:'c3', ind:'Kurikulum', jenis:'Dokumen', tahun:'2020', ket:'Naskah Akademik Pengembangan Kurikulum', sumber:'LED C.3', prio:'UTAMA', icon:'📘', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_23/view?usp=sharing' },
  { id:'E024', nama:'Dokumen Kurikulum PSBM', k:'c3', ind:'Kurikulum', jenis:'Dokumen', tahun:'2024', ket:'Struktur kurikulum 150 SKS, 53 MK', sumber:'LED C.3 / LKPS 3.a.1', prio:'UTAMA', icon:'📘', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_24/view?usp=sharing' },
  { id:'E025', nama:'BA Evaluasi Kurikulum', k:'c3', ind:'Pemutakhiran Kurikulum', jenis:'BA', tahun:'2020-2024', ket:'Berita Acara evaluasi 2020, 2021, 2024', sumber:'LED C.3', prio:'UTAMA', icon:'📝', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E026', nama:'Profil Lulusan PSBM', k:'c3', ind:'Profil Lulusan', jenis:'Dokumen', tahun:'2020', ket:'6 profil lulusan PSBM', sumber:'LED C.3', prio:'UTAMA', icon:'🎓', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_26/view?usp=sharing' },
  { id:'E027', nama:'Matriks Profil Lulusan–CPL', k:'c3', ind:'CPL', jenis:'Matriks', tahun:'2024', ket:'Penurunan profil lulusan ke CPL', sumber:'LED C.3', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_27/view?usp=sharing' },
  { id:'E028', nama:'Rumusan 12 CPL PSBM', k:'c3', ind:'CPL', jenis:'Dokumen', tahun:'2020', ket:'Rumusan CPL sesuai 4 standar kompetensi', sumber:'LED C.3', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_28/view?usp=sharing' },
  { id:'E029', nama:'Matriks CPL–MK', k:'c3', ind:'CPL', jenis:'Matriks', tahun:'2024', ket:'Pemetaan CPL ke mata kuliah', sumber:'LED C.3', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_29/view?usp=sharing' },
  { id:'E030', nama:'Matriks CPL–CPMK', k:'c3', ind:'CPL', jenis:'Matriks', tahun:'2024', ket:'Pemetaan CPL ke CPMK', sumber:'LED C.3', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_30/view?usp=sharing' },
  { id:'E031', nama:'Rekap Ketercapaian CPL', k:'c3', ind:'Pengukuran CPL', jenis:'Rekap', tahun:'2022-2024', ket:'Hasil pengukuran ketercapaian CPL', sumber:'LED C.3 / LKPS 3.a.1', prio:'UTAMA', icon:'📈', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_31/view?usp=sharing' },
  { id:'E032', nama:'BA Evaluasi CPL', k:'c3', ind:'Pengukuran CPL', jenis:'BA', tahun:'2024', ket:'Berita Acara evaluasi CPL', sumber:'LED C.3', prio:'UTAMA', icon:'📝', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_32/view?usp=sharing' },
  { id:'E033', nama:'Rencana Tindak Lanjut CPL', k:'c3', ind:'Pengukuran CPL', jenis:'Dokumen', tahun:'2024', ket:'RTL closed-loop CPL', sumber:'LED C.3', prio:'UTAMA', icon:'📋', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_33/view?usp=sharing' },
  { id:'E034', nama:'Repository RPS (53 MK)', k:'c3', ind:'RPS', jenis:'Repository', tahun:'2024', ket:'Kumpulan RPS 53 MK', sumber:'LED C.3 / LKPS 3.a.2', prio:'UTAMA', icon:'📁', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E035', nama:'BA Tinjauan RPS', k:'c3', ind:'RPS', jenis:'BA', tahun:'2024', ket:'Berita Acara tinjauan RPS', sumber:'LED C.3', prio:'UTAMA', icon:'📝', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_35/view?usp=sharing' },
  { id:'E036', nama:'Matriks Integrasi Penelitian–MK', k:'c3', ind:'Integrasi Penelitian', jenis:'Matriks', tahun:'2024', ket:'Integrasi penelitian ke MK inti (≥10%)', sumber:'LED C.3 / LKPS 3.a.3', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_36/view?usp=sharing' },
  { id:'E037', nama:'Matriks Integrasi PkM–MK', k:'c3', ind:'Integrasi PkM', jenis:'Matriks', tahun:'2024', ket:'Integrasi PkM ke MK inti', sumber:'LED C.3', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_37/view?usp=sharing' },
  { id:'E038', nama:'Roadmap Penelitian PSBM', k:'c3', ind:'Penelitian', jenis:'Roadmap', tahun:'2020-2025', ket:'Peta jalan penelitian 4 bidang fokus', sumber:'LED C.3', prio:'UTAMA', icon:'🗺️', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_38/view?usp=sharing' },
  { id:'E039', nama:'Daftar Penelitian DTPS (45 judul)', k:'c3', ind:'Penelitian', jenis:'Daftar', tahun:'2022-2024', ket:'45 penelitian: 14, 13, 18', sumber:'LED C.3 / LKPS 3.b', prio:'UTAMA', icon:'🔬', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_39/view?usp=sharing' },
  { id:'E040', nama:'Bukti Keterlibatan Mahasiswa dalam Penelitian', k:'c3', ind:'Penelitian-Mahasiswa', jenis:'Dokumentasi', tahun:'2022-2024', ket:'12/45 penelitian melibatkan mhs (26,67%)', sumber:'LED C.3 / LKPS 6.h.1', prio:'UTAMA', icon:'👨‍', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E041', nama:'Roadmap PkM PSBM', k:'c3', ind:'PkM', jenis:'Roadmap', tahun:'2020-2025', ket:'Peta jalan PkM', sumber:'LED C.3', prio:'UTAMA', icon:'🗺️', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_41/view?usp=sharing' },
  { id:'E042', nama:'Daftar PkM DTPS (14 kegiatan)', k:'c3', ind:'PkM', jenis:'Daftar', tahun:'2022-2024', ket:'14 PkM: 2, 6, 6', sumber:'LED C.3 / LKPS 3.c', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_42/view?usp=sharing' },
  { id:'E043', nama:'Panduan Capstone Project', k:'c3', ind:'Capstone', jenis:'Panduan', tahun:'2024', ket:'Panduan resmi capstone project', sumber:'LED C.3', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_43/view?usp=sharing' },
  { id:'E044', nama:'Laporan Capstone Project', k:'c3', ind:'Capstone', jenis:'Laporan', tahun:'2024', ket:'Laporan capstone project mahasiswa', sumber:'LED C.3', prio:'UTAMA', icon:'', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },

  // C.4 SDM (11 evidence)
  { id:'E045', nama:'Daftar DTPS PSBM (11 dosen)', k:'c4', ind:'Kecukupan DTPS', jenis:'Daftar', tahun:'2024', ket:'11 DTPS inti PSBM', sumber:'LED C.4 / LKPS 4.a', prio:'UTAMA', icon:'👨‍', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_45/view?usp=sharing' },
  { id:'E046', nama:'CV DTPS', k:'c4', ind:'Kualifikasi', jenis:'CV', tahun:'2024', ket:'Curriculum Vitae 11 DTPS', sumber:'LED C.4', prio:'UTAMA', icon:'📄', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E047', nama:'Ijazah & Sertifikat DTPS', k:'c4', ind:'Kualifikasi', jenis:'Scan', tahun:'2024', ket:'3 doktor, 4 Lektor Kepala, 6 Lektor', sumber:'LED C.4', prio:'UTAMA', icon:'🎓', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E048', nama:'SK Jabatan Fungsional', k:'c4', ind:'JAFA', jenis:'SK', tahun:'2024', ket:'SK JAFA DTPS', sumber:'LED C.4', prio:'UTAMA', icon:'📜', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E049', nama:'Roadmap Pengembangan SDM', k:'c4', ind:'Pengembangan SDM', jenis:'Roadmap', tahun:'2024-2028', ket:'Rencana studi lanjut & JAFA', sumber:'LED C.4', prio:'UTAMA', icon:'🗺️', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_49/view?usp=sharing' },
  { id:'E050', nama:'Sertifikat Kompetensi DTPS', k:'c4', ind:'Sertifikasi', jenis:'Sertifikat', tahun:'2024', ket:'Sertifikasi profesi/industri DTPS', sumber:'LED C.4', prio:'UTAMA', icon:'🏅', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E051', nama:'Laporan BKD DTPS', k:'c4', ind:'Beban Kerja', jenis:'Laporan', tahun:'2022-2024', ket:'BKD rata-rata 14,77 SKS', sumber:'LED C.4 / LKPS 4.c', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_51/view?usp=sharing' },
  { id:'E052', nama:'Daftar Publikasi DTPS (220)', k:'c4', ind:'Publikasi', jenis:'Daftar', tahun:'2022-2024', ket:'220 publikasi 3 tahun', sumber:'LED C.4 / LKPS 4.e', prio:'UTAMA', icon:'📚', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_52/view?usp=sharing' },
  { id:'E053', nama:'Daftar Luaran DTPS (HKI, Produk)', k:'c4', ind:'Luaran DTPS', jenis:'Daftar', tahun:'2022-2024', ket:'Paten, HKI, TTG, produk, buku', sumber:'LED C.4 / LKPS 4.f', prio:'UTAMA', icon:'💡', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_53/view?usp=sharing' },
  { id:'E054', nama:'Bukti Produk Diadopsi (13)', k:'c4', ind:'Produk Diadopsi', jenis:'Dokumentasi', tahun:'2022-2024', ket:'13 produk/jasa diadopsi masyarakat', sumber:'LED C.4 / LKPS 4.g', prio:'UTAMA', icon:'📦', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E055', nama:'Bukti Rekognisi Kepakaran DTPS', k:'c4', ind:'Rekognisi', jenis:'Dokumentasi', tahun:'2022-2024', ket:'Undangan, SK rekognisi', sumber:'LED C.4 / LKPS 4.j', prio:'UTAMA', icon:'🏆', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },

  // C.5 Sarpras (8 evidence)
  { id:'E056', nama:'RKAT Anggaran PSBM', k:'c5', ind:'Pembiayaan', jenis:'Dokumen', tahun:'2022-2024', ket:'Anggaran PSBM 3 tahun', sumber:'LED C.5 / LKPS 2.b', prio:'UTAMA', icon:'💰', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E057', nama:'Inventaris Laboratorium', k:'c5', ind:'Laboratorium', jenis:'Inventaris', tahun:'2024', ket:'Daftar alat lab PSBM', sumber:'LED C.5 / LKPS 5.a', prio:'UTAMA', icon:'🔧', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_57/view?usp=sharing' },
  { id:'E058', nama:'Logbook Pemeliharaan Alat', k:'c5', ind:'Laboratorium', jenis:'Logbook', tahun:'2024', ket:'Log pemeliharaan alat lab', sumber:'LED C.5', prio:'UTAMA', icon:'📋', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E059', nama:'Daftar Perangkat Lunak', k:'c5', ind:'Perangkat Lunak', jenis:'Daftar', tahun:'2024', ket:'Software pembelajaran', sumber:'LED C.5', prio:'UTAMA', icon:'💻', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_59/view?usp=sharing' },
  { id:'E060', nama:'Kebijakan K3L JTE', k:'c5', ind:'K3L', jenis:'Kebijakan', tahun:'2023', ket:'Kebijakan K3L resmi', sumber:'LED C.5 / LKPS 5.b', prio:'UTAMA', icon:'⚠️', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_60/view?usp=sharing' },
  { id:'E061', nama:'SOP K3L Laboratorium', k:'c5', ind:'K3L', jenis:'SOP', tahun:'2024', ket:'SOP K3L lab', sumber:'LED C.5', prio:'UTAMA', icon:'📋', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_61/view?usp=sharing' },
  { id:'E062', nama:'Inventaris Fasilitas K3L', k:'c5', ind:'K3L', jenis:'Inventaris', tahun:'2024', ket:'APAR, APD, jalur evakuasi', sumber:'LED C.5 / LKPS 5.c', prio:'UTAMA', icon:'🧯', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_62/view?usp=sharing' },
  { id:'E063', nama:'Laporan Audit K3L', k:'c5', ind:'K3L', jenis:'Laporan', tahun:'2024', ket:'Laporan audit K3L terakhir', sumber:'LED C.5', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_63/view?usp=sharing' },

  // C.6 Luaran (10 evidence)
  { id:'E064', nama:'Data Mahasiswa Aktif (PDDikti)', k:'c6', ind:'Rasio Mhs/DTPS', jenis:'Data', tahun:'2024', ket:'Data mahasiswa aktif TS', sumber:'LED C.6 / LKPS 6.a', prio:'UTAMA', icon:'👨‍🎓', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_64/view?usp=sharing' },
  { id:'E065', nama:'Sertifikat Prestasi Mahasiswa', k:'c6', ind:'Prestasi', jenis:'Sertifikat', tahun:'2022-2024', ket:'10 prestasi akademik, 9 nonakademik', sumber:'LED C.6 / LKPS 6.c', prio:'UTAMA', icon:'🏆', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E066', nama:'Data Kelulusan & Masa Studi', k:'c6', ind:'Kelulusan', jenis:'Data', tahun:'2022-2024', ket:'Data kelulusan & masa studi', sumber:'LED C.6 / LKPS 6.d', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_66/view?usp=sharing' },
  { id:'E067', nama:'Daftar Publikasi Mahasiswa (126)', k:'c6', ind:'Publikasi Mhs', jenis:'Daftar', tahun:'2022-2024', ket:'126 publikasi/presentasi', sumber:'LED C.6 / LKPS 6.e.2', prio:'UTAMA', icon:'📚', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_67/view?usp=sharing' },
  { id:'E068', nama:'Sertifikat HKI Mahasiswa', k:'c6', ind:'Luaran Mhs', jenis:'Sertifikat', tahun:'2022-2024', ket:'Paten, HKI, TTG, produk, buku', sumber:'LED C.6 / LKPS 6.e.3', prio:'UTAMA', icon:'', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E069', nama:'Bukti Produk Mahasiswa Diadopsi (16)', k:'c6', ind:'Produk Mhs', jenis:'Dokumentasi', tahun:'2022-2024', ket:'16 produk/jasa diadopsi', sumber:'LED C.6 / LKPS 6.e.4', prio:'UTAMA', icon:'📦', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E070', nama:'Laporan Tracer Study 2024', k:'c6', ind:'Tracer Study', jenis:'Laporan', tahun:'2024', ket:'Laporan tracer study lengkap', sumber:'LED C.6 / LKPS 6.f', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_70/view?usp=sharing' },
  { id:'E071', nama:'Raw Data Tracer Study', k:'c6', ind:'Tracer Study', jenis:'Data', tahun:'2024', ket:'Data mentah tracer (80 lulusan, 61 terlacak)', sumber:'LED C.6', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_71/view?usp=sharing' },
  { id:'E072', nama:'Laporan Survei Pengguna Lulusan', k:'c6', ind:'Kepuasan Pengguna', jenis:'Laporan', tahun:'2024', ket:'45 responden, 7 aspek kepuasan', sumber:'LED C.6 / LKPS 6.g.2', prio:'UTAMA', icon:'⭐', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_72/view?usp=sharing' },
  { id:'E073', nama:'BA Tindak Lanjut Tracer', k:'c6', ind:'Tindak Lanjut Tracer', jenis:'BA', tahun:'2024', ket:'BA perbaikan kurikulum berbasis tracer', sumber:'LED C.6', prio:'UTAMA', icon:'📝', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_73/view?usp=sharing' },

  // C.7 SPMI (10 evidence)
  { id:'E074', nama:'SK GPM JTE', k:'c7', ind:'Unit Penjaminan Mutu', jenis:'SK', tahun:'2023', ket:'SK Gugus Penjaminan Mutu', sumber:'LED C.7 / LKPS 7.a', prio:'UTAMA', icon:'📜', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_74/view?usp=sharing' },
  { id:'E075', nama:'Dokumen Kebijakan SPMI', k:'c7', ind:'Perangkat SPMI', jenis:'Dokumen', tahun:'2023', ket:'Kebijakan SPMI resmi', sumber:'LED C.7', prio:'UTAMA', icon:'📘', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_75/view?usp=sharing' },
  { id:'E076', nama:'Manual SPMI (PPEPP)', k:'c7', ind:'Perangkat SPMI', jenis:'Manual', tahun:'2023', ket:'Manual siklus PPEPP', sumber:'LED C.7', prio:'UTAMA', icon:'📗', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_76/view?usp=sharing' },
  { id:'E077', nama:'Dokumen Standar SPMI', k:'c7', ind:'Perangkat SPMI', jenis:'Dokumen', tahun:'2023', ket:'Standar mutu SPMI', sumber:'LED C.7', prio:'UTAMA', icon:'📘', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E078', nama:'Laporan AMI 2025', k:'c7', ind:'AMI', jenis:'Laporan', tahun:'2025', ket:'Laporan Audit Mutu Internal', sumber:'LED C.7', prio:'UTAMA', icon:'🔍', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_78/view?usp=sharing' },
  { id:'E079', nama:'SK Auditor AMI', k:'c7', ind:'AMI', jenis:'SK', tahun:'2025', ket:'SK auditor AMI independen', sumber:'LED C.7', prio:'UTAMA', icon:'📜', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_79/view?usp=sharing' },
  { id:'E080', nama:'Notulensi RTM', k:'c7', ind:'RTM', jenis:'Notulensi', tahun:'2025', ket:'Rapat Tinjauan Manajemen', sumber:'LED C.7', prio:'UTAMA', icon:'📝', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E081', nama:'Dokumen RTL AMI', k:'c7', ind:'RTL', jenis:'Dokumen', tahun:'2025', ket:'Rencana Tindak Lanjut 15 temuan', sumber:'LED C.7', prio:'UTAMA', icon:'', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_81/view?usp=sharing' },
  { id:'E082', nama:'Laporan Evaluasi Kinerja IKT', k:'c7', ind:'Evaluasi Kinerja', jenis:'Laporan', tahun:'2024', ket:'Evaluasi IKT JTE/PSBM', sumber:'LED C.7', prio:'UTAMA', icon:'📊', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_82/view?usp=sharing' },
  { id:'E083', nama:'Laporan Survei Kepuasan Stakeholder', k:'c7', ind:'Kepuasan Stakeholder', jenis:'Laporan', tahun:'2024', ket:'Survei mahasiswa, dosen, lulusan, pengguna', sumber:'LED C.7', prio:'UTAMA', icon:'⭐', url:'https://drive.google.com/file/d/CONTOH_ID_FILE_83/view?usp=sharing' },

  // Bukti Pendukung (4 evidence)
  { id:'E084', nama:'Foto Kegiatan FGD VMTS', k:'c1', ind:'Mekanisme', jenis:'Foto', tahun:'2024', ket:'Dokumentasi foto FGD', sumber:'LED C.1', prio:'PENDUKUNG', icon:'📷', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E085', nama:'Sertifikat Pelatihan Dosen', k:'c4', ind:'Pengembangan SDM', jenis:'Sertifikat', tahun:'2024', ket:'Sertifikat pelatihan DTPS', sumber:'LED C.4', prio:'PENDUKUNG', icon:'🏅', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E086', nama:'Foto Laboratorium', k:'c5', ind:'Laboratorium', jenis:'Foto', tahun:'2024', ket:'Dokumentasi lab PSBM', sumber:'LED C.5', prio:'PENDUKUNG', icon:'', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' },
  { id:'E087', nama:'Foto Kegiatan PkM', k:'c3', ind:'PkM', jenis:'Foto', tahun:'2024', ket:'Dokumentasi PkM', sumber:'LED C.3', prio:'PENDUKUNG', icon:'📷', url:'https://drive.google.com/drive/folders/CONTOH_FOLDER_ID' }
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
    { no: 6, tujuan: 'Memperkuat budaya mutu', indikator: 'Siklus PPEPP berjalan', target: 'AMI → RTM → RTL' }
  ],
  program: [
    { nama: 'Penguatan Closed-Loop CPL', strategi: 'WO', target: '100% CPL terukur & ditindaklanjuti', pic: 'Kurikulum/GPM', anggaran: 'Rp 30 juta' },
    { nama: 'Peningkatan Pendanaan Eksternal Penelitian', strategi: 'WO', target: '≥40% pendanaan eksternal (2026)', pic: 'P3M', anggaran: 'Rp 50 juta' },
    { nama: 'Integrasi Penelitian DTPS dengan Mahasiswa', strategi: 'WO', target: '≥40% penelitian libatkan mhs', pic: 'P3M/Kaprodi', anggaran: 'Rp 40 juta' },
    { nama: 'Percepatan JAFA & Studi Lanjut', strategi: 'ST', target: '5 doktor, 50% LK, 1 GB', pic: 'Kajur', anggaran: 'Rp 200 juta' },
    { nama: 'Peningkatan Response Rate Tracer', strategi: 'WT', target: '≥80% response rate', pic: 'CDC/GPM', anggaran: 'Rp 20 juta' },
    { nama: 'Internasionalisasi Kerja Sama & Publikasi', strategi: 'SO', target: '≥5 MoU intl, ≥10 publikasi Scopus', pic: 'Kajur/P3M', anggaran: 'Rp 80 juta' }
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
  const map = { beranda:0, c1:1, c2:2, c3:3, c4:4, c5:5, c6:6, c7:7, bab3:8 };
  showEvPanel(id, tabs[map[id]]);
}

// ===== RENDER KRITERIA =====
let currentIndFilter = {};
function renderKriteria(k) {
  const evs = dataEvidence.filter(e => e.k === k);
  const indicators = [...new Set(evs.map(e => e.ind))];
  if (!currentIndFilter[k]) currentIndFilter[k] = 'all';

  const titles = {
    c1: '📑 C.1 — VMTS',
    c2: '🏛️ C.2 — Tata Pamong, Tata Kelola, Kerja Sama, Keuangan',
    c3: '📘 C.3 — Pendidikan, Penelitian, dan PkM',
    c4: '👨‍🏫 C.4 — Sumber Daya Manusia',
    c5: '💰 C.5 — Keuangan, Sarana, Prasarana & K3L',
    c6: ' C.6 — Mahasiswa dan Luaran',
    c7: '🔄 C.7 — Sistem Penjaminan Mutu'
  };

  let html = '<div class="section-header"><h2>' + titles[k] + '</h2>';
  html += '<div class="desc">Total <strong>' + evs.length + '</strong> evidence — klik untuk membuka dokumen</div></div>';

  html += '<div class="ev-subnav">';
  html += '<button class="' + (currentIndFilter[k]==='all'?'active':'') + '" onclick="filterIndikator(\'' + k + '\', \'all\', this)">Semua <span class="cnt">' + evs.length + '</span></button>';
  indicators.forEach(ind => {
    const count = evs.filter(e => e.ind === ind).length;
    html += '<button class="' + (currentIndFilter[k]===ind?'active':'') + '" onclick="filterIndikator(\'' + k + '\', \'' + ind.replace(/'/g,"\\'") + '\', this)">' + ind + ' <span class="cnt">' + count + '</span></button>';
  });
  html += '</div>';

  const filtered = currentIndFilter[k] === 'all' ? evs : evs.filter(e => e.ind === currentIndFilter[k]);
  filtered.sort((a,b) => (b.prio==='UTAMA'?1:0) - (a.prio==='UTAMA'?1:0));

  filtered.forEach(e => { html += renderEvCard(e); });

  document.getElementById(k + 'Content').innerHTML = html;
}

function filterIndikator(k, ind, btn) {
  currentIndFilter[k] = ind;
  renderKriteria(k);
}

function renderEvCard(e) {
  const prioClass = e.prio === 'UTAMA' ? 'utama' : 'pendukung';
  let html = '<div class="ev-card ' + prioClass + '">';
  html += '<div class="ev-card-icon">' + e.icon + '</div>';
  html += '<div class="ev-card-body">';
  html += '<div class="ev-card-title">' + e.nama + '</div>';
  html += '<div class="ev-card-desc">' + e.ket + '</div>';
  html += '<div class="ev-card-meta">';
  html += '<span class="ev-badge ' + prioClass + '">' + e.prio + '</span>';
  html += '<span class="ev-badge jenis">' + e.jenis + '</span>';
  html += '<span class="ev-badge tahun">' + e.tahun + '</span>';
  html += '<span class="ev-badge sumber">📖 ' + e.sumber + '</span>';
  html += '</div>';
  html += '<div class="ev-card-actions">';
  html += '<a href="' + e.url + '" target="_blank" class="ev-open-btn">📂 BUKA DOKUMEN</a>';
  html += '<button class="ev-open-btn secondary" onclick="alert(\'Sumber: ' + e.sumber + '\')">📖 Lihat Sumber LED/LKPS</button>';
  html += '</div>';
  html += '</div></div>';
  return html;
}

// ===== SEARCH =====
function quickEvSearch(keyword) {
  document.getElementById('evSearch').value = keyword;
  searchEv();
}

function clearEvSearch() {
  document.getElementById('evSearch').value = '';
  document.getElementById('evSearchResult').innerHTML = '';
  document.getElementById('defaultBeranda').style.display = 'block';
}

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

  const results = dataEvidence.filter(e =>
    e.nama.toLowerCase().includes(query) ||
    e.ind.toLowerCase().includes(query) ||
    e.ket.toLowerCase().includes(query) ||
    e.k.toLowerCase().includes(query) ||
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
    html += '<h3 style="color:#e65100; margin: 0 0 16px 0;"> Rantai Keterlacakan BAB III</h3>';
    html += '<div class="bab3-chain">';
    dataBab3.chain.forEach(s => {
      html += '<div class="bab3-step">';
      html += '<div class="step-num">TAHAP ' + s.num + '</div>';
      html += '<div class="step-title">' + s.title + '</div>';
      html += '<div class="step-content">' + s.content + '</div>';
      html += '<div class="step-evidence">';
      s.evidence.forEach(ev => {
        html += '<button class="ev-open-btn secondary" onclick="quickEvSearch(\'' + ev + '\')">📂 ' + ev + '</button>';
      });
      html += '</div></div>';
    });
    html += '</div>';
  } else if (key === 'swot') {
    html += '<h3 style="color:#e65100; margin: 0 0 16px 0;">📊 Analisis SWOT PSBM</h3>';
    html += '<div class="swot-grid">';
    dataBab3.swot.forEach(s => {
      const colors = { S: '#2e7d32', W: '#e65100', O: '#1565c0', T: '#c62828' };
      const bgs = { S: '#e8f5e9', W: '#fff3e0', O: '#e3f2fd', T: '#ffebee' };
      html += '<div class="swot-card ' + (s.type==='S'?'strength':s.type==='W'?'weakness':s.type==='O'?'opportunity':'threat') + '">';
      html += '<h4 style="color:' + colors[s.type] + ';">' + s.title + '</h4>';
      html += '<ul>';
      s.items.forEach(i => { html += '<li>' + i + '</li>'; });
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
      html += '<div class="ev-card-icon"></div>';
      html += '<div class="ev-card-body">';
      html += '<div class="ev-card-title">' + p.nama + '</div>';
      html += '<div class="ev-card-meta">';
      html += '<span class="ev-badge jenis">Strategi ' + p.strategi + '</span>';
      html += '<span class="ev-badge tahun">Target: ' + p.target + '</span>';
      html += '<span class="ev-badge sumber">PIC: ' + p.pic + '</span>';
      html += '<span class="ev-badge utama">Anggaran: ' + p.anggaran + '</span>';
      html += '</div></div></div>';
    });
  } else if (key === 'monitoring') {
    html += '<h3 style="color:#e65100; margin: 0 0 16px 0;">🔄 Monitoring & PPEPP</h3>';
    html += '<div class="ev-card utama" style="border-left-color: #e65100;"><div class="ev-card-icon"></div><div class="ev-card-body"><div class="ev-card-title">Audit Mutu Internal (AMI)</div><div class="ev-card-desc">Audit internal tahunan terhadap 7 kriteria</div><div class="ev-card-actions"><button class="ev-open-btn" onclick="quickEvSearch(\'AMI\')">📂 BUKA DOKUMEN</button></div></div></div>';
    html += '<div class="ev-card utama" style="border-left-color: #e65100;"><div class="ev-card-icon">📝</div><div class="ev-card-body"><div class="ev-card-title">Rapat Tinjauan Manajemen (RTM)</div><div class="ev-card-desc">Tinjauan hasil AMI oleh pimpinan</div><div class="ev-card-actions"><button class="ev-open-btn" onclick="quickEvSearch(\'RTM\')">📂 BUKA DOKUMEN</button></div></div></div>';
    html += '<div class="ev-card utama" style="border-left-color: #e65100;"><div class="ev-card-icon">📋</div><div class="ev-card-body"><div class="ev-card-title">Rencana Tindak Lanjut (RTL)</div><div class="ev-card-desc">15 temuan AMI dengan RTL terdokumentasi</div><div class="ev-card-actions"><button class="ev-open-btn" onclick="quickEvSearch(\'RTL\')">📂 BUKA DOKUMEN</button></div></div></div>';
  }
  document.getElementById('bab3Content').innerHTML = html;
}

// ===== STATS =====
function renderStats() {
  const stats = {};
  dataEvidence.forEach(e => {
    const key = e.k.toUpperCase();
    if (!stats[key]) stats[key] = 0;
    stats[key]++;
  });
  let html = '';
  ['C.1','C.2','C.3','C.4','C.5','C.6','C.7'].forEach(k => {
    const key = k.toLowerCase().replace('.','');
    html += '<div class="bukti-card" onclick="goToPanel(\'' + key + '\')">';
    html += '<div class="bc-icon">📂</div>';
    html += '<div class="bc-name">' + k + '</div>';
    html += '<div class="bc-desc">' + (stats[k]||0) + ' evidence</div>';
    html += '</div>';
  });
  html += '<div class="bukti-card" style="border-left-color:#e65100;" onclick="goToPanel(\'bab3\')">';
  html += '<div class="bc-icon">📕</div>';
  html += '<div class="bc-name">BAB III</div>';
  html += '<div class="bc-desc">Program Pengembangan</div>';
  html += '</div>';
  document.getElementById('statsGrid').innerHTML = html;
}

// ===== INIT =====
document.addEventListener('DOMContentLoaded', function() {
  renderStats();
});
</script>

---
layout: default
title: Progress Mingguan
permalink: /progress/
---

# 📊 Progress Mingguan

**Periode**: Januari – Mei 2026  
**Target Submit**: Awal Mei 2026  
**Fokus**: Penyusunan LKPS → LED → Finalisasi

<div id="countdown-container" style="text-align: center; margin: 24px 0;">
  <div id="countdown" style="font-size: 1.2rem; font-weight: 600; color: #0d47a1;"></div>
</div>

<div style="margin: 20px 0;">
  <div style="display: flex; justify-content: space-between; margin-bottom: 6px; font-size: 0.9rem;">
    <span>Jan 2026</span>
    <span><strong id="progress-percent">0%</strong></span>
    <span>Mei 2026</span>
  </div>
  <div style="height: 20px; background: #e0e0e0; border-radius: 10px; overflow: hidden;">
    <div id="progress-bar" style="height: 100%; background: linear-gradient(to right, #4caf50, #81c784); width: 0%; transition: width 0.5s ease;"></div>
  </div>
</div>

<script>
  // Progress manual (sesuaikan tiap minggu)
  const progressPercent = 5; // ← Ganti tiap minggu
  document.getElementById('progress-bar').style.width = progressPercent + '%';
  document.getElementById('progress-percent').textContent = progressPercent + '%';

  // Countdown ke awal Mei 2026
  const targetDate = new Date('2026-05-01T00:00:00');
  function updateCountdown() {
    const now = new Date();
    const diff = targetDate - now;
    if (diff <= 0) {
      document.getElementById('countdown').innerHTML = '✅ Submit Selesai!';
      return;
    }
    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const weeks = Math.floor(days / 7);
    const remainingDays = days % 7;
    document.getElementById('countdown').innerHTML = 
      `Sisa waktu: ${weeks} minggu ${remainingDays} hari`;
  }
  setInterval(updateCountdown, 60000);
  updateCountdown();
</script>

## 🗓️ Rencana Kerja Mingguan

<style>
  .weekly-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    margin: 24px 0;
    font-size: 0.92rem;
  }
  .weekly-table th,
  .weekly-table td {
    padding: 10px 8px;
    text-align: left;
    border-bottom: 1px solid #e0e0e0;
  }
  .weekly-table th {
    background-color: #f1f5f9;
    font-weight: 600;
    color: #0d47a1;
    border-top: 2px solid #0d47a1;
  }
  .weekly-table tr:last-child td {
    border-bottom: 2px solid #0d47a1;
  }
  @media (max-width: 600px) {
    .weekly-table th, .weekly-table td {
      padding: 8px 6px;
      font-size: 0.85rem;
    }
  }
</style>

<table class="weekly-table">
  <thead>
    <tr>
      <th>Minggu</th>
      <th>Kegiatan Utama</th>
      <th>Kriteria Terkait</th>
      <th>Output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Minggu 1 (5–11 Jan)</strong></td>
      <td>Sosialisasi instrumen 2025 & workshop GAP analysis</td>
      <td>I, II, III, VI</td>
      <td>Laporan GAP awal, rencana perbaikan</td>
    </tr>
    <tr>
      <td><strong>Minggu 2 (12–18 Jan)</strong></td>
      <td>Pengumpulan data dasar: VMTS, Tata Pamong, SDM</td>
      <td>I, II, IV</td>
      <td>Draft Tabel 1, 2.a, 4.a LKPS</td>
    </tr>
    <tr>
      <td><strong>Minggu 3 (19–25 Jan)</strong></td>
      <td>Pengumpulan data: Kurikulum, Penelitian, PkM</td>
      <td>III</td>
      <td>Draft Tabel 3.a–3.c LKPS</td>
    </tr>
    <tr>
      <td><strong>Minggu 4 (26 Jan–1 Feb)</strong></td>
      <td>Pengumpulan data: Sarpras, K3L, Mahasiswa</td>
      <td>V, VI</td>
      <td>Draft Tabel 5.a–5.c, 6.a–6.d LKPS</td>
    </tr>
    <tr>
      <td><strong>Minggu 5 (2–8 Feb)</strong></td>
      <td>Validasi data & lengkapi bukti pendukung</td>
      <td>Semua</td>
      <td>File bukti di folder `/bukti/`</td>
    </tr>
    <tr>
      <td><strong>Minggu 6 (9–15 Feb)</strong></td>
      <td>Finalisasi LKPS (semua tabel)</td>
      <td>Semua</td>
      <td><strong>LKPS lengkap (PDF)</strong></td>
    </tr>
    <tr>
      <td><strong>Minggu 7 (16–22 Feb)</strong></td>
      <td>Penulisan LED: Kriteria I–II</td>
      <td>I, II</td>
      <td>Draft LED bagian I–II</td>
    </tr>
    <tr>
      <td><strong>Minggu 8 (23 Feb–1 Mar)</strong></td>
      <td>Penulisan LED: Kriteria III–IV</td>
      <td>III, IV</td>
      <td>Draft LED bagian III–IV</td>
    </tr>
    <tr>
      <td><strong>Minggu 9 (2–8 Mar)</strong></td>
      <td>Penulisan LED: Kriteria V–VI</td>
      <td>V, VI</td>
      <td>Draft LED bagian V–VI</td>
    </tr>
    <tr>
      <td><strong>Minggu 10 (9–15 Mar)</strong></td>
      <td>Penulisan LED: Kriteria VII + Program Pengembangan</td>
      <td>VII, B</td>
      <td>Draft LED lengkap</td>
    </tr>
    <tr>
      <td><strong>Minggu 11 (16–22 Mar)</strong></td>
      <td>Review internal & koreksi silang</td>
      <td>Semua</td>
      <td>Revisi LED & LKPS</td>
    </tr>
    <tr>
      <td><strong>Minggu 12 (23–29 Mar)</strong></td>
      <td>Validasi oleh Ketua Jurusan</td>
      <td>Semua</td>
      <td>Approve draft final</td>
    </tr>
    <tr>
      <td><strong>Minggu 13 (30 Mar–5 Apr)</strong></td>
      <td>Finalisasi format PDF & uji tautan bukti</td>
      <td>Semua</td>
      <td>LED & LKPS siap submit</td>
    </tr>
    <tr>
      <td><strong>Minggu 14 (6–12 Apr)</strong></td>
      <td>Simulasi asesmen & persiapan presentasi</td>
      <td>VI, VII</td>
      <td>Bahan presentasi tim</td>
    </tr>
    <tr>
      <td><strong>Minggu 15 (13–19 Apr)</strong></td>
      <td>Backup dokumen & uji coba upload (jika tersedia)</td>
      <td>Semua</td>
      <td>Dokumen final di cloud & lokal</td>
    </tr>
    <tr>
      <td><strong>Minggu 16 (20–26 Apr)</strong></td>
      <td>Final check & persiapan submit</td>
      <td>Semua</td>
      <td>Daftar kelengkapan akhir</td>
    </tr>
    <tr>
      <td><strong>Minggu 17 (27 Apr–3 Mei)</strong></td>
      <td><strong>SUBMIT ke LAM Teknik</strong></td>
      <td>Semua</td>
      <td><strong>Konfirmasi submit resmi</strong></td>
    </tr>
  </tbody>
</table>

## 🔑 Catatan Penting
- ✅ **LKPS harus selesai Minggu 6** — menjadi dasar penyusunan LED
- ✅ **Kriteria VI (Mahasiswa & Luaran)** adalah penentu utama predikat
- ✅ **K3L wajib dilengkapi SOP tertulis** (Tabel 5.b–5.c)
- ⏳ Asesmen lapangan kemungkinan besar **Juni–Juli 2026**

> 💡 **Update progress setiap Jumat sore** — ganti nilai `progressPercent` di skrip sesuai persentase penyelesaian.

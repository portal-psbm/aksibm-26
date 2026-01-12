---
layout: default
title: Progress
permalink: /progress/
---

# 📊 Progress Persiapan Akreditasi 

**Periode**: Januari 2026  
**Fase**: Persiapan Awal  
**Target Submit**: September 2026 | **Asesmen Lapangan**: Oktober–November 2026

<div id="countdown-container" style="text-align: center; margin: 24px 0;">
  <div id="countdown" style="font-size: 1.2rem; font-weight: 600; color: #0d47a1;"></div>
</div>

<div style="margin: 20px 0;">
  <div style="display: flex; justify-content: space-between; margin-bottom: 6px; font-size: 0.9rem;">
    <span>Des 2025</span>
    <span><strong id="progress-percent">5%</strong></span>
    <span>Sep 2026</span>
  </div>
  <div style="height: 20px; background: #e0e0e0; border-radius: 10px; overflow: hidden;">
    <div id="progress-bar" style="height: 100%; background: linear-gradient(to right, #4caf50, #81c784); width: 5%; transition: width 0.5s ease;"></div>
  </div>
</div>

<script>
  // Progress manual (Des 2025 = awal persiapan)
  const progressPercent = 5;
  document.getElementById('progress-bar').style.width = progressPercent + '%';
  document.getElementById('progress-percent').textContent = progressPercent + '%';

  // Countdown ke September 2026
  const targetDate = new Date('2026-09-01T00:00:00');
  function updateCountdown() {
    const now = new Date();
    const diff = targetDate - now;
    if (diff <= 0) {
      document.getElementById('countdown').innerHTML = '✅ Submit Selesai!';
      return;
    }
    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const months = Math.floor(days / 30);
    const remainingDays = days % 30;
    document.getElementById('countdown').innerHTML = 
      `Sisa waktu: ${months} bulan ${remainingDays} hari`;
  }
  setInterval(updateCountdown, 60000);
  updateCountdown();
</script>

## 📋 Status Per Kriteria (Januari 2026)

<style>
  .progress-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    margin: 24px 0;
    font-size: 0.95rem;
  }
  .progress-table th,
  .progress-table td {
    padding: 12px 10px;
    text-align: left;
    border-bottom: 1px solid #e0e0e0;
  }
  .progress-table th {
    background-color: #f1f5f9;
    font-weight: 600;
    color: #0d47a1;
    border-top: 2px solid #0d47a1;
  }
  .progress-table tr:last-child td {
    border-bottom: 2px solid #0d47a1;
  }
  .status-badge {
    display: inline-block;
    padding: 4px 10px;
    border-radius: 20px;
    font-size: 0.85rem;
    font-weight: 600;
  }
  .status-belum {
    background-color: #ffebee;
    color: #d32f2f;
  }
  .status-persiapan {
    background-color: #fff8e1;
    color: #f57c00;
  }
  @media (max-width: 600px) {
    .progress-table th, .progress-table td {
      padding: 10px 8px;
      font-size: 0.88rem;
    }
  }
</style>

<table class="progress-table">
  <thead>
    <tr>
      <th>Kriteria</th>
      <th>Judul</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>I</td>
      <td>VMTS</td>
      <td><span class="status-badge status-persiapan">Persiapan</span></td>
    </tr>
    <tr>
      <td>II</td>
      <td>Tata Pamong, Tata Kelola, Kerja Sama, Keuangan</td>
      <td><span class="status-badge status-persiapan">Persiapan</span></td>
    </tr>
    <tr>
      <td>III</td>
      <td>Relevansi Pendidikan, Penelitian, dan PkM</td>
      <td><span class="status-badge status-belum">Belum Dimulai</span></td>
    </tr>
    <tr>
      <td>IV</td>
      <td>Sumber Daya Manusia</td>
      <td><span class="status-badge status-belum">Belum Dimulai</span></td>
    </tr>
    <tr>
      <td>V</td>
      <td>Sarpras & K3L</td>
      <td><span class="status-badge status-belum">Belum Dimulai</span></td>
    </tr>
    <tr>
      <td><strong>VI</strong></td>
      <td><strong>Mahasiswa dan Luaran Mahasiswa</strong></td>
      <td><span class="status-badge status-belum">Belum Dimulai</span></td>
    </tr>
    <tr>
      <td>VII</td>
      <td>Sistem Penjaminan Mutu</td>
      <td><span class="status-badge status-belum">Belum Dimulai</span></td>
    </tr>
  </tbody>
</table>

## 📌 Rincian Aktivitas Desember 2025
- ✅ **Struktur folder bukti digital** disiapkan (`I_VMTS/` hingga `VII_SPMI/`)
- ✅ **Website akreditasi** aktif di [https://portal-psbm.github.io/aksibm-26/](https://portal-psbm.github.io/aksibm-26/)

## 🗓️ Rencana Januari 2026
- **Sosialisasi instrumen** ke dosen PSBM
- **GAP Analysis** per 7 kriteria
- Mulai **pengumpulan data dasar** untuk LKPS

> 💡 **Fokus Utama 2026**:  
> - **Kriteria VI (Mahasiswa & Luaran)** adalah penentu predikat  
> - **Kriteria V (K3L)** wajib dilengkapi dokumen SOP keselamatan  
> - Semua kriteria harus mendukung pembuktian **outcome lulusan**

> 📅 **Milestone Berikutnya**:  
> - **Maret 2026**: LKPS lengkap  
> - **Mei 2026**: LED final  
> - **September 2026**: Submit ke LAM Teknik

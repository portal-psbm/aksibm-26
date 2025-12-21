---
layout: default
title: Beranda
permalink: /
---

# 🎯 Akreditasi PSBM LAM Teknik 2026

<div id="countdown-container" style="text-align: center; margin: 20px 0;">
  <div id="countdown" style="font-size: 1.2rem; font-weight: 600; color: #0d47a1;"></div>
</div>

<div style="margin: 30px 0;">
  <div style="display: flex; justify-content: space-between; margin-bottom: 6px; font-size: 0.9rem;">
    <span>Oktober 2025</span>
    <span><strong id="progress-percent">0%</strong></span>
    <span>September 2026</span>
  </div>
  <div style="height: 24px; background: #e0e0e0; border-radius: 12px; overflow: hidden;">
    <div id="progress-bar" style="height: 100%; background: linear-gradient(to right, #4caf50, #81c784); width: 0%; transition: width 0.5s ease;"></div>
  </div>
</div>

<script>
  // Target: 1 September 2026
  const targetDate = new Date('2026-09-01T00:00:00');

  function updateCountdown() {
    const now = new Date();
    const diff = targetDate - now;

    if (diff <= 0) {
      document.getElementById('countdown').innerHTML = '✅ Asesmen Selesai!';
      document.getElementById('progress-bar').style.width = '100%';
      document.getElementById('progress-percent').textContent = '100%';
      return;
    }

    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const months = Math.floor(days / 30);
    const remainingDays = days % 30;

    document.getElementById('countdown').innerHTML = 
      `Sisa waktu: ${months} bulan ${remainingDays} hari`;

    // Progress: dari 1 Okt 2025 → 1 Sep 2026 (total ~335 hari)
    const startDate = new Date('2025-10-01T00:00:00');
    const totalDuration = targetDate - startDate;
    const elapsed = now - startDate;
    const progress = Math.min(100, Math.max(0, (elapsed / totalDuration) * 100));

    document.getElementById('progress-bar').style.width = progress.toFixed(2) + '%';
    document.getElementById('progress-percent').textContent = Math.round(progress) + '%';
  }

  // Update setiap detik
  setInterval(updateCountdown, 1000);
  updateCountdown(); // init
</script>

**Program Studi**: S1 Terapan Broadband Multimedia  
**Target Asesmen**: **September 2026**  
**Tim**: AW, BU, DW, MF, SH, VF, Z

> Website ini merefleksikan progres real-time persiapan akreditasi LAM Teknik.

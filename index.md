---
layout: default
title: Beranda
permalink: /
---

# 🎯 Akreditasi Program Studi Broadband Multimedia 2026

**Target Submit**: **Awal September 2026**  
<br>
> Website ini merefleksikan progres persiapan akreditasi PSBM sesuai Pedoman LAM Teknik Edisi 2025.

<!-- 🖼️ Carousel Slide -->
<div style="max-width: 900px; margin: 40px auto; position: relative; border-radius: 12px; overflow: hidden; box-shadow: 0 8px 24px rgba(0,0,0,0.15);">
  <div id="slide-container" style="display: flex; transition: transform 0.5s ease-in-out; width: 100%;">
    <img src="/aksibm-26/assets/images/slide1.jpg" alt="Gedung G - Lab Telekomunikasi" style="min-width: 100%; display: block;">
    <img src="/aksibm-26/assets/images/slide2.jpeg" alt="Tim Akreditasi PSBM" style="min-width: 100%; display: block;">
    <img src="/aksibm-26/assets/images/slide3.jpeg" alt="Studio Produksi Multimedia" style="min-width: 100%; display: block;">
    <img src="/aksibm-26/assets/images/slide4.jpeg" alt="Pelatihan KLSD 2026" style="min-width: 100%; display: block;">
    <img src="/aksibm-26/assets/images/slide5.jpeg" alt="Capstone Project Showcase" style="min-width: 100%; display: block;">
    <img src="/aksibm-26/assets/images/slide6.jpeg" alt="Kegiatan Matching Fund" style="min-width: 100%; display: block;">
    <img src="/aksibm-26/assets/images/slide7.jpeg" alt="Workshop GAP Analysis" style="min-width: 100%; display: block;">
  </div>

  <!-- Tombol Navigasi -->
  <button onclick="moveSlide(-1)" style="position: absolute; left: 16px; top: 50%; transform: translateY(-50%); background: rgba(255,255,255,0.8); border: none; width: 40px; height: 40px; border-radius: 50%; cursor: pointer; font-weight: bold; box-shadow: 0 2px 6px rgba(0,0,0,0.2);">
    &#8249;
  </button>
  <button onclick="moveSlide(1)" style="position: absolute; right: 16px; top: 50%; transform: translateY(-50%); background: rgba(255,255,255,0.8); border: none; width: 40px; height: 40px; border-radius: 50%; cursor: pointer; font-weight: bold; box-shadow: 0 2px 6px rgba(0,0,0,0.2);">
    &#8250;
  </button>

  <!-- Indikator -->
  <div id="indicators" style="position: absolute; bottom: 16px; left: 50%; transform: translateX(-50%); display: flex; gap: 8px;"></div>
</div>

<script>
  let currentSlide = 0;
  const slides = document.querySelectorAll('#slide-container img');
  const totalSlides = slides.length;

  // Buat indikator
  const indicatorsContainer = document.getElementById('indicators');
  for (let i = 0; i < totalSlides; i++) {
    const dot = document.createElement('div');
    dot.style.width = '10px';
    dot.style.height = '10px';
    dot.style.borderRadius = '50%';
    dot.style.backgroundColor = i === 0 ? '#0d47a1' : '#ccc';
    dot.addEventListener('click', () => goToSlide(i));
    indicatorsContainer.appendChild(dot);
  }

  function updateSlide() {
    const container = document.getElementById('slide-container');
    container.style.transform = `translateX(-${currentSlide * 100}%)`;

    const dots = indicatorsContainer.children;
    for (let i = 0; i < dots.length; i++) {
      dots[i].style.backgroundColor = i === currentSlide ? '#0d47a1' : '#ccc';
    }
  }

  function moveSlide(direction) {
    currentSlide += direction;
    if (currentSlide < 0) currentSlide = totalSlides - 1;
    if (currentSlide >= totalSlides) currentSlide = 0;
    updateSlide();
  }

  function goToSlide(index) {
    currentSlide = index;
    updateSlide();
  }

  // Auto slide setiap 4 detik
  setInterval(() => {
    moveSlide(1);
  }, 4000);
</script>

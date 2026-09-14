---
layout: default
title: Beranda
permalink: /
---

# 🎯 Akreditasi Program Studi Broadband Multimedia 2026

**Target Submit**: **Awal September 2026**  
<br>
> Website ini merefleksikan progres real-time persiapan akreditasi PSBM sesuai Pedoman LAM Teknik Edisi 2025.

<!-- 🖼️ Modern Carousel Slide -->
<div class="carousel-container">
  <div id="slide-container">
    
    <!-- Slide 1 -->
    <div class="slide active">
      <img src="/aksibm-26/assets/images/slide1.jpg" alt="Gedung G - Lab Telekomunikasi">
      <div class="slide-caption">
        <h3>Gedung G - Lab Telekomunikasi</h3>
        <p>Fasilitas laboratorium modern untuk mendukung pembelajaran praktik.</p>
      </div>
    </div>

    <!-- Slide 2 -->
    <div class="slide">
      <img src="/aksibm-26/assets/images/slide2.jpeg" alt="Tim Akreditasi PSBM">
      <div class="slide-caption">
        <h3>Tim Akreditasi PSBM</h3>
        <p>Bersinergi mewujudkan akreditasi unggul tahun 2026.</p>
      </div>
    </div>

    <!-- Slide 3 -->
    <div class="slide">
      <img src="/aksibm-26/assets/images/slide3.jpeg" alt="Kegiatan Akademik">
      <div class="slide-caption">
        <h3>Suasana Akademik</h3>
        <p>Lingkungan belajar yang kondusif dan inovatif.</p>
      </div>
    </div>

    <!-- Slide 4 -->
    <div class="slide">
      <img src="/aksibm-26/assets/images/slide4.jpeg" alt="Kegiatan Mahasiswa">
      <div class="slide-caption">
        <h3>Prestasi Mahasiswa</h3>
        <p>Mengukir prestasi di tingkat nasional dan internasional.</p>
      </div>
    </div>

    <!-- Slide 5 -->
    <div class="slide">
      <img src="/aksibm-26/assets/images/slide5.jpeg" alt="Capstone Project">
      <div class="slide-caption">
        <h3>Capstone Project</h3>
        <p>Proyek rekayasa terapan sebagai puncak kompetensi mahasiswa.</p>
      </div>
    </div>

    <!-- Slide 6 -->
    <div class="slide">
      <img src="/aksibm-26/assets/images/slide6.jpeg" alt="Kerja Sama Industri">
      <div class="slide-caption">
        <h3>Kerja Sama Industri</h3>
        <p>Kolaborasi strategis untuk relevansi kurikulum dan lulusan.</p>
      </div>
    </div>

    <!-- Slide 7 -->
    <div class="slide">
      <img src="/aksibm-26/assets/images/slide7.jpeg" alt="Workshop & Pelatihan">
      <div class="slide-caption">
        <h3>Workshop & Pelatihan</h3>
        <p>Peningkatan kompetensi dosen dan tenaga kependidikan.</p>
      </div>
    </div>

    <!-- Slide 8 -->
    <div class="slide">
      <img src="/aksibm-26/assets/images/slide8.jpeg" alt="Fasilitas Pendukung">
      <div class="slide-caption">
        <h3>Fasilitas Pendukung</h3>
        <p>Sarana dan prasarana yang memenuhi standar K3L.</p>
      </div>
    </div>

  </div>

  <!-- Tombol Navigasi (Glassmorphism) -->
  <button class="nav-btn prev" onclick="moveSlide(-1)">&#8249;</button>
  <button class="nav-btn next" onclick="moveSlide(1)">&#8250;</button>

  <!-- Kontrol Bawah: Indikator & Progress Bar -->
  <div class="carousel-controls">
    <div id="indicators"></div>
    <div class="progress-bar"><div class="progress-fill"></div></div>
  </div>
</div>

<style>
  /* Container Utama */
  .carousel-container {
    max-width: 900px;
    margin: 40px auto;
    position: relative;
    border-radius: 16px;
    overflow: hidden;
    box-shadow: 0 12px 32px rgba(0,0,0,0.2);
    aspect-ratio: 16/9; /* Menjaga proporsi agar tidak gepeng di semua layar */
    background: #111;
  }

  /* Slide Wrapper */
  #slide-container {
    display: flex;
    width: 100%;
    height: 100%;
    transition: transform 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  }

  .slide {
    min-width: 100%;
    height: 100%;
    position: relative;
    display: flex;
    align-items: flex-end; /* Caption di bawah */
  }

  .slide img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Gambar tidak akan terdistorsi */
    display: block;
  }

  /* Gradient Overlay agar teks terbaca jelas di atas foto apapun */
  .slide::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 60%;
    background: linear-gradient(to top, rgba(0,0,0,0.85) 0%, transparent 100%);
    pointer-events: none;
  }

  /* Caption Text dengan Animasi */
  .slide-caption {
    position: absolute;
    bottom: 70px;
    left: 30px;
    right: 30px;
    color: white;
    z-index: 2;
    opacity: 0;
    transform: translateY(20px);
    transition: all 0.5s ease 0.2s; /* Delay agar muncul setelah slide geser */
  }

  .slide.active .slide-caption {
    opacity: 1;
    transform: translateY(0);
  }

  .slide-caption h3 {
    margin: 0 0 8px 0;
    font-size: 1.6rem;
    font-weight: 700;
    text-shadow: 0 2px 4px rgba(0,0,0,0.5);
  }

  .slide-caption p {
    margin: 0;
    font-size: 1.05rem;
    opacity: 0.9;
    text-shadow: 0 1px 2px rgba(0,0,0,0.5);
  }

  /* Tombol Navigasi */
  .nav-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(8px);
    -webkit-backdrop-filter: blur(8px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    color: white;
    width: 48px;
    height: 48px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 1.5rem;
    font-weight: bold;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s ease;
    z-index: 10;
  }

  .nav-btn:hover {
    background: rgba(255, 255, 255, 0.35);
    transform: translateY(-50%) scale(1.1);
  }

  .nav-btn.prev { left: 16px; }
  .nav-btn.next { right: 16px; }

  /* Kontrol Bawah */
  .carousel-controls {
    position: absolute;
    bottom: 24px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
    z-index: 10;
    width: 80%;
  }

  /* Indikator Dot */
  #indicators {
    display: flex;
    gap: 8px;
  }

  .dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.4);
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .dot.active {
    background: #fff;
    transform: scale(1.3);
  }

  /* Progress Bar Auto-slide */
  .progress-bar {
    width: 100%;
    height: 3px;
    background: rgba(255, 255, 255, 0.2);
    border-radius: 2px;
    overflow: hidden;
  }

  .progress-fill {
    height: 100%;
    background: #4caf50; /* Warna hijau progres */
    width: 0%;
    transition: width 0.05s linear;
  }

  /* Responsif untuk Mobile */
  @media (max-width: 600px) {
    .carousel-container {
      margin: 24px 16px;
      border-radius: 12px;
      aspect-ratio: 4/3; /* Lebih tinggi di HP agar foto terlihat jelas */
    }
    .slide-caption {
      bottom: 60px;
      left: 20px;
      right: 20px;
    }
    .slide-caption h3 { font-size: 1.2rem; }
    .slide-caption p { font-size: 0.9rem; }
    .nav-btn { width: 40px; height: 40px; font-size: 1.2rem; }
  }
</style>

<script>
  let currentSlide = 0;
  const slides = document.querySelectorAll('.slide');
  const totalSlides = slides.length;
  const indicatorsContainer = document.getElementById('indicators');
  const progressFill = document.querySelector('.progress-fill');
  
  let autoSlideInterval;
  let progressInterval;
  const slideDuration = 5000; // 5 detik per slide
  let progress = 0;

  // Buat indikator dots secara otomatis sesuai jumlah slide
  slides.forEach((_, i) => {
    const dot = document.createElement('div');
    dot.classList.add('dot');
    if (i === 0) dot.classList.add('active');
    dot.addEventListener('click', () => goToSlide(i));
    indicatorsContainer.appendChild(dot);
  });

  function updateSlide() {
    const container = document.getElementById('slide-container');
    container.style.transform = `translateX(-${currentSlide * 100}%)`;

    // Update active class untuk animasi caption & dot
    slides.forEach((slide, i) => {
      slide.classList.toggle('active', i === currentSlide);
    });
    
    const dots = indicatorsContainer.children;
    for (let i = 0; i < dots.length; i++) {
      dots[i].classList.toggle('active', i === currentSlide);
    }

    resetProgress();
  }

  function moveSlide(direction) {
    currentSlide += direction;
    if (currentSlide < 0) currentSlide = totalSlides - 1;
    if (currentSlide >= totalSlides) currentSlide = 0;
    updateSlide();
    restartAutoSlide();
  }

  function goToSlide(index) {
    currentSlide = index;
    updateSlide();
    restartAutoSlide();
  }

  function resetProgress() {
    progress = 0;
    progressFill.style.width = '0%';
  }

  function startAutoSlide() {
    resetProgress();
    clearInterval(autoSlideInterval);
    clearInterval(progressInterval);
    
    // Animasi progress bar
    progressInterval = setInterval(() => {
      progress += 100 / (slideDuration / 50); 
      progressFill.style.width = `${progress}%`;
    }, 50);

    // Ganti slide
    autoSlideInterval = setInterval(() => {
      moveSlide(1);
    }, slideDuration);
  }

  function restartAutoSlide() {
    startAutoSlide();
  }

  // Mulai auto slide saat halaman dimuat
  startAutoSlide();

  // Pause saat mouse hover (UX yang baik agar asesor bisa membaca)
  const carouselContainer = document.querySelector('.carousel-container');
  carouselContainer.addEventListener('mouseenter', () => {
    clearInterval(autoSlideInterval);
    clearInterval(progressInterval);
  });
  
  carouselContainer.addEventListener('mouseleave', () => {
    startAutoSlide();
  });
</script>

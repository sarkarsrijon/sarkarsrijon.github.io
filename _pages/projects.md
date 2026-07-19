---
layout: page
title: projects
permalink: /projects/
description: A growing collection of my cool projects.
nav: true
nav_order: 2
display_categories: [work, research]
horizontal: false
---

<style>
/* ---------- PROJECTS: 3 per row, square, captioned ---------- */
.proj-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
  margin-top: 1rem;
}
.proj-item { display: flex; flex-direction: column; }
.proj-box {
  aspect-ratio: 1 / 1;
  border: 1px solid var(--global-divider-color, #e0e0e0);
  border-radius: 8px;
  overflow: hidden;
  display: flex; align-items: center; justify-content: center;
  background: var(--global-card-bg-color, #fafafa);
  transition: transform .2s ease, box-shadow .2s ease;
}
.proj-box:hover { transform: translateY(-3px); box-shadow: 0 6px 18px rgba(0,0,0,.12); }
.proj-box img { width: 100%; height: 100%; object-fit: contain; padding: 10px; }
.proj-caption { margin-top: .6rem; font-size: .85rem; line-height: 1.35; text-align: center; }
.proj-caption b { display: block; margin-bottom: .15rem; }

/* ---------- PARTNERS: 5 per row logos ---------- */
.partner-grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 1.5rem 1.25rem;
  align-items: center;
  margin-top: 1rem;
}
.partner-box {
  aspect-ratio: 1 / 1;
  display: flex; align-items: center; justify-content: center;
  padding: 10px;
}
.partner-box img {
  max-width: 100%; max-height: 100%;
  object-fit: contain;
  filter: grayscale(100%); opacity: .7;
  transition: filter .2s ease, opacity .2s ease;
}
.partner-box:hover img { filter: grayscale(0); opacity: 1; }

@media (max-width: 768px) {
  .proj-grid { grid-template-columns: repeat(2, 1fr); }
  .partner-grid { grid-template-columns: repeat(3, 1fr); }
}
@media (max-width: 480px) {
  .proj-grid { grid-template-columns: 1fr; }
  .partner-grid { grid-template-columns: repeat(2, 1fr); }
}
</style>

## projects

<div class="proj-grid">

  <!-- ===== Project 1 ===== -->
  <div class="proj-item">
    <a class="proj-box" href="{{ '/assets/pdf/liebau-poster.pdf' | relative_url }}" target="_blank" rel="noopener">
      <img src="{{ '/assets/img/proj/liebau.png' | relative_url }}" alt="Liebau pump">
    </a>
    <div class="proj-caption">
      <b>Liebau Pump Modeling</b>
      Physics-based traveling-wave model of valveless pumping.
    </div>
  </div>

  <!-- ===== Project 2 ===== -->
  <div class="proj-item">
    <a class="proj-box" href="https://your-journal-link.com" target="_blank" rel="noopener">
      <img src="{{ '/assets/img/proj/vpac1.png' | relative_url }}" alt="VPAC1 antagonist">
    </a>
    <div class="proj-caption">
      <b>VPAC1 Antagonist Design</b>
      Sequence-agnostic design of VIP-receptor antagonists.
    </div>
  </div>

  <!-- ===== Project 3 ===== -->
  <div class="proj-item">
    <a class="proj-box" href="{{ '/assets/pdf/kronecker.pdf' | relative_url }}" target="_blank" rel="noopener">
      <img src="{{ '/assets/img/proj/kronecker.png' | relative_url }}" alt="Kronecker covariance">
    </a>
    <div class="proj-caption">
      <b>Kronecker Covariance</b>
      Approximations for large-scale Bayesian inverse problems.
    </div>
  </div>

  <!-- ===== Project 4 ===== -->
  <div class="proj-item">
    <a class="proj-box" href="#" target="_blank" rel="noopener">
      <img src="{{ '/assets/img/proj/proj4.png' | relative_url }}" alt="Project 4">
    </a>
    <div class="proj-caption">
      <b>Project Four</b>
      Short description here.
    </div>
  </div>

  <!-- ===== Project 5 ===== -->
  <div class="proj-item">
    <a class="proj-box" href="#" target="_blank" rel="noopener">
      <img src="{{ '/assets/img/proj/proj5.png' | relative_url }}" alt="Project 5">
    </a>
    <div class="proj-caption">
      <b>Project Five</b>
      Short description here.
    </div>
  </div>

  <!-- ===== Project 6 ===== -->
  <div class="proj-item">
    <a class="proj-box" href="#" target="_blank" rel="noopener">
      <img src="{{ '/assets/img/proj/proj6.png' | relative_url }}" alt="Project 6">
    </a>
    <div class="proj-caption">
      <b>Project Six</b>
      Short description here.
    </div>
  </div>

</div>

<hr style="margin: 3rem 0;">

## partners &amp; institutions

<div class="partner-grid">

  <a class="partner-box" href="https://cambiumoncology.com" target="_blank" rel="noopener">
    <img src="{{ '/assets/img/partners/cambium.png' | relative_url }}" alt="Cambium Oncology">
  </a>
  <a class="partner-box" href="https://icerm.brown.edu" target="_blank" rel="noopener">
    <img src="{{ '/assets/img/partners/icerm.png' | relative_url }}" alt="Brown ICERM">
  </a>
  <a class="partner-box" href="#" target="_blank" rel="noopener">
    <img src="{{ '/assets/img/partners/partner3.png' | relative_url }}" alt="Partner 3">
  </a>
  <a class="partner-box" href="#" target="_blank" rel="noopener">
    <img src="{{ '/assets/img/partners/partner4.png' | relative_url }}" alt="Partner 4">
  </a>
  <a class="partner-box" href="#" target="_blank" rel="noopener">
    <img src="{{ '/assets/img/partners/partner5.png' | relative_url }}" alt="Partner 5">
  </a>

  <!-- duplicate the block above for slots 6–15 -->
  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner6.png' | relative_url }}" alt="Partner 6"></a>
  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner7.png' | relative_url }}" alt="Partner 7"></a>
  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner8.png' | relative_url }}" alt="Partner 8"></a>
  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner9.png' | relative_url }}" alt="Partner 9"></a>
  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner10.png' | relative_url }}" alt="Partner 10"></a>

  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner11.png' | relative_url }}" alt="Partner 11"></a>
  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner12.png' | relative_url }}" alt="Partner 12"></a>
  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner13.png' | relative_url }}" alt="Partner 13"></a>
  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner14.png' | relative_url }}" alt="Partner 14"></a>
  <a class="partner-box" href="#"><img src="{{ '/assets/img/partners/partner15.png' | relative_url }}" alt="Partner 15"></a>

</div>

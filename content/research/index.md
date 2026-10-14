---
title: Research
date: 2026-10-14
share: false
---

<style>
  .article > .article-container {
    max-width: min(1480px, calc(100vw - 48px));
  }

  .article > .article-container.pt-3 {
    display: none;
  }
</style>

<section class="lab-page-intro">
  <div class="lab-eyebrow">Research</div>
  <h1>Major Research Directions</h1>
  <p>Our work connects tissue mechanics, magnetic resonance imaging, computational modeling, and MRI-compatible robotic intervention. Each direction below includes representative papers from the supplied materials. The visual areas are reserved for paper framework figures and graphical abstracts.</p>
</section>

<div class="research-grid">
  <article class="research-card">
    <div class="paper-carousel" data-paper-carousel>
      <div class="paper-carousel-track">
        <figure class="paper-slide">
          <img src="{{< asset-url "media/research/brain-biomechanics/1.jpg" >}}" alt="Framework figure for multiscale measurement of brain tissue and cell biomechanics">
          <figcaption>Multiscale measurement of brain tissue and cell biomechanics using a mouse model</figcaption>
        </figure>
        <figure class="paper-slide">
          <img src="{{< asset-url "media/research/brain-biomechanics/2.jpg" >}}" alt="Framework figure for transcranial vibration stimulation at 40 Hz">
          <figcaption>Transcranial vibration stimulation at 40 Hz induced neural activity and promoted the coupling of global brain activity and cerebrospinal fluid flow</figcaption>
        </figure>
        <figure class="paper-slide">
          <img src="{{< asset-url "media/research/brain-biomechanics/3.jpg" >}}" alt="Framework figure for vibration modulated regional cerebral blood flow with MRI">
          <figcaption>Assessment of vibration modulated regional cerebral blood flow with MRI</figcaption>
        </figure>
      </div>
      <div class="paper-carousel-controls">
        <button type="button" class="paper-carousel-prev" aria-label="Previous paper figure">&lsaquo;</button>
        <div class="paper-carousel-dots" aria-hidden="true"></div>
        <button type="button" class="paper-carousel-next" aria-label="Next paper figure">&rsaquo;</button>
      </div>
    </div>
    <div class="research-card-body">
      <span class="research-index">01</span>
      <h2>Brain Biomechanics and Mechanobiology</h2>
      <p>Quantifying brain tissue and cellular biomechanics, neural response to mechanical stimulation, and fluid-structure interactions in the brain.</p>
    </div>
  </article>

  <article class="research-card">
    <div class="paper-carousel" data-paper-carousel>
      <div class="paper-carousel-track">
        <figure class="paper-slide">
          <div class="paper-figure-placeholder">Framework Figure</div>
          <figcaption>Noninvasive 3D mapping of tissue stress using reverberant shear wave</figcaption>
        </figure>
        <figure class="paper-slide">
          <div class="paper-figure-placeholder">Framework Figure</div>
          <figcaption>Measurement of biomechanical properties of transversely isotropic biological tissue using traveling wave expansion</figcaption>
        </figure>
        <figure class="paper-slide">
          <div class="paper-figure-placeholder">Framework Figure</div>
          <figcaption>A 3D fast MR elastography sequence with interleaved multislab acquisition and Hadamard encoding</figcaption>
        </figure>
        <figure class="paper-slide">
          <div class="paper-figure-placeholder">Framework Figure</div>
          <figcaption>Indirect Shear Wave Excitation for Brain Magnetic Resonance Elastography With Minimal Cerebral Blood Flow Alteration</figcaption>
        </figure>
        <figure class="paper-slide">
          <div class="paper-figure-placeholder">Framework Figure</div>
          <figcaption>MR Elastography With Optimization-Based Phase Unwrapping and Traveling Wave Expansion-Based Neural Network (TWENN)</figcaption>
        </figure>
      </div>
      <div class="paper-carousel-controls">
        <button type="button" class="paper-carousel-prev" aria-label="Previous paper figure">&lsaquo;</button>
        <div class="paper-carousel-dots" aria-hidden="true"></div>
        <button type="button" class="paper-carousel-next" aria-label="Next paper figure">&rsaquo;</button>
      </div>
    </div>
    <div class="research-card-body">
      <span class="research-index">02</span>
      <h2>MR Elastography</h2>
      <p>Developing MRE acquisition, actuation, reconstruction, inversion, and biomechanical mapping methods for tissues, organs, and disease models.</p>
    </div>
  </article>

  <article class="research-card">
    <div class="paper-carousel" data-paper-carousel>
      <div class="paper-carousel-track">
        <figure class="paper-slide">
          <div class="paper-figure-placeholder">Framework Figure</div>
          <figcaption>Magnetically Guided Microrobots for Targeted Drug Delivery</figcaption>
        </figure>
        <figure class="paper-slide">
          <div class="paper-figure-placeholder">Framework Figure</div>
          <figcaption>Hybrid pneumatic-hydraulic actuation for MRI-guided robotic stereotactic neurointervention</figcaption>
        </figure>
        <figure class="paper-slide">
          <div class="paper-figure-placeholder">Framework Figure</div>
          <figcaption>A deep unrolled neural network for real-time MRI-guided brain intervention</figcaption>
        </figure>
      </div>
      <div class="paper-carousel-controls">
        <button type="button" class="paper-carousel-prev" aria-label="Previous paper figure">&lsaquo;</button>
        <div class="paper-carousel-dots" aria-hidden="true"></div>
        <button type="button" class="paper-carousel-next" aria-label="Next paper figure">&rsaquo;</button>
      </div>
    </div>
    <div class="research-card-body">
      <span class="research-index">03</span>
      <h2>MRI-Guided Micro/Nano Robots</h2>
      <p>Creating MRI-compatible robotic systems, magnetic microrobots, and real-time image guidance workflows for precise brain and targeted drug delivery interventions.</p>
    </div>
  </article>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.querySelectorAll('[data-paper-carousel]').forEach(function (carousel) {
      const track = carousel.querySelector('.paper-carousel-track');
      const slides = Array.from(carousel.querySelectorAll('.paper-slide'));
      const prev = carousel.querySelector('.paper-carousel-prev');
      const next = carousel.querySelector('.paper-carousel-next');
      const dots = carousel.querySelector('.paper-carousel-dots');
      let current = 0;

      slides.forEach(function (_, index) {
        const dot = document.createElement('button');
        dot.type = 'button';
        dot.setAttribute('aria-label', 'Show paper figure ' + (index + 1));
        dot.addEventListener('click', function () {
          current = index;
          update();
        });
        dots.appendChild(dot);
      });

      const dotButtons = Array.from(dots.querySelectorAll('button'));
      const update = function () {
        track.style.transform = 'translateX(-' + current * 100 + '%)';
        dotButtons.forEach(function (dot, index) {
          dot.classList.toggle('active', index === current);
        });
      };

      prev.addEventListener('click', function () {
        current = (current - 1 + slides.length) % slides.length;
        update();
      });

      next.addEventListener('click', function () {
        current = (current + 1) % slides.length;
        update();
      });

      update();
    });
  });
</script>

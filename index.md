---
layout: landing
title: Transition Timer
permalink: /
---

<style>
  /* ── Landing page scoped styles ── */
  .tt-hero { padding: 3rem 1.5rem 1rem; text-align: center; }
  .tt-hero h1 {
    font-size: clamp(2rem, 6vw, 4.5rem);
    font-weight: 900;
    line-height: 1.1;
    color: #fff;
    margin-bottom: 1.25rem;
  }
  .tt-hero h1 .accent { color: #6366f1; }
  .tt-hero p {
    font-size: clamp(1rem, 2vw, 1.25rem);
    color: #d1d5db;
    max-width: 42rem;
    margin: 0 auto 2rem;
  }

  .store-badges {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1rem;
    margin-bottom: 3rem;
  }
  .store-badges a img { height: 48px; width: auto; }

  .screenshots {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1.5rem;
    margin-bottom: 1rem;
  }
  .screenshots img {
    width: clamp(80px, 12vw, 160px);
    border-radius: 0.75rem;
    box-shadow: 0 0 16px 4px rgba(99, 102, 241, 0.45);
    cursor: pointer;
    transition: transform 0.2s;
  }
  .screenshots img:hover { transform: scale(1.05); }

  /* ── Features ── */
  .tt-section { padding: 5rem 1.5rem; }
  .tt-section-dark { background: #000; }
  .tt-section-darker { background: #030712; }

  .tt-section-heading {
    text-align: center;
    margin-bottom: 3.5rem;
  }
  .tt-section-heading h2 {
    font-size: clamp(1.75rem, 4vw, 3.75rem);
    font-weight: 800;
    color: #fff;
    margin-bottom: .75rem;
  }
  .tt-section-heading p { color: #9ca3af; font-size: 1.125rem; max-width: 48rem; margin: .25rem auto 0; }

  .tt-cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 2rem;
    max-width: 1100px;
    margin: 0 auto;
  }
  .tt-card {
    background: #111827;
    border: 1px solid #1f2937;
    border-radius: 1rem;
    padding: 2rem;
    text-align: center;
    transition: box-shadow .3s;
  }
  .tt-card:hover { box-shadow: 0 0 24px rgba(99,102,241,.25); }
  .tt-card-icon {
    width: 4rem; height: 4rem;
    background: #374151;
    border: 1px solid #4b5563;
    border-radius: 1rem;
    display: flex; align-items: center; justify-content: center;
    margin: 0 auto 1.5rem;
    font-size: 2rem;
  }
  .tt-card h3 {
    font-size: 1.125rem;
    font-weight: 700;
    color: #fff;
    margin-bottom: .75rem;
    text-transform: uppercase;
    letter-spacing: .05em;
  }
  .tt-card p { color: #9ca3af; line-height: 1.6; }

  /* ── Full feature list ── */
  .tt-toolkit-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 3rem;
    max-width: 1100px;
    margin: 0 auto;
  }
  .tt-toolkit-col h4 {
    font-size: 1.125rem;
    font-weight: 700;
    color: #818cf8;
    margin-bottom: 1.5rem;
  }
  .tt-toolkit-col ul { list-style: none; padding: 0; margin: 0; }
  .tt-toolkit-col li {
    display: flex;
    align-items: flex-start;
    gap: .75rem;
    margin-bottom: 1rem;
    color: #d1d5db;
    line-height: 1.5;
  }
  .tt-toolkit-col li svg { flex-shrink: 0; color: #818cf8; }
  .tt-toolkit-col li strong { color: #fff; }

  /* ── Testimonials ── */
  .tt-testimonials-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 2rem;
    max-width: 900px;
    margin: 0 auto;
  }
  .tt-testimonial {
    background: #111827;
    border: 1px solid #1f2937;
    border-radius: 1rem;
    padding: 2rem;
    transition: transform .3s;
  }
  .tt-testimonial:hover { transform: scale(1.02); }
  .tt-testimonial blockquote {
    font-size: 1.1rem;
    font-style: italic;
    color: #d1d5db;
    margin: 0 0 1.5rem;
    border: none;
    padding: 0;
  }
  .tt-testimonial-meta { display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: .5rem; }
  .tt-testimonial-meta strong { color: #fff; display: block; }
  .tt-testimonial-meta span { color: #9ca3af; font-size: .875rem; }

  /* ── Final CTA ── */
  .tt-cta { padding: 3.5rem 1.5rem; background: #312e81; text-align: center; }
  .tt-cta h2 { font-size: clamp(1.75rem, 4vw, 3rem); font-weight: 800; font-style: italic; color: #fff; margin-bottom: .5rem; }
  .tt-cta p { color: #c7d2fe; font-size: 1.25rem; margin-bottom: 2rem; }

  /* ── Screenshot modal ── */
  #tt-modal {
    display: none;
    position: fixed; inset: 0; z-index: 9999;
    background: rgba(0,0,0,.92);
    align-items: center; justify-content: center;
  }
  #tt-modal.open { display: flex; }
  #tt-modal img { max-width: 90vw; max-height: 90vh; border-radius: 1rem; }
</style>

<!-- HERO -->
<div class="tt-hero">
  <h1>
    End Time Blindness<br>
    <span class="accent">Master Hyperfocus</span>
  </h1>
  <p>Overcome time blindness and break the hyperfocus spell with an intelligent co-pilot that makes task transitions easier.</p>

  <div class="store-badges">
    <a href="https://apps.apple.com/us/app/time-blindness-hyper-focus/id6634579526" target="_blank" rel="noopener">
      <img src="/assets/img/svg/appstore.svg" alt="Download on the App Store">
    </a>
    <a href="https://play.google.com/store/apps/details?id=com.workbreaktimer" target="_blank" rel="noopener">
      <img src="/assets/img/svg/google.svg" alt="Get it on Google Play">
    </a>
    <a href="https://www.amazon.com/gp/product/B0DSGTM66Y" target="_blank" rel="noopener">
      <img src="/assets/img/svg/amazon.svg" alt="Get it on Amazon Appstore">
    </a>
  </div>

  <div class="screenshots">
    <img src="/assets/img/screenshots/02.png" alt="App screenshot 1" class="tt-screenshot">
    <img src="/assets/img/screenshots/03.png" alt="App screenshot 2" class="tt-screenshot">
    <img src="/assets/img/screenshots/04.png" alt="App screenshot 3" class="tt-screenshot">
    <img src="/assets/img/screenshots/07.png" alt="App screenshot 4" class="tt-screenshot">
    <img src="/assets/img/screenshots/08.png" alt="App screenshot 5" class="tt-screenshot">
  </div>
</div>

<!-- FEATURES — 3 CARDS -->
<section class="tt-section tt-section-dark">
  <div class="tt-section-heading">
    <h2>Built for ADHD+</h2>
    <p>Translates abstract time into clear, tangible signals that work for your brain.</p>
    <p>Finally, put an end to "just one more minute" spiraling into hours!</p>
  </div>

  <div class="tt-cards">
    <div class="tt-card">
      <div class="tt-card-icon">🕒</div>
      <h3>Become Time Aware</h3>
      <p>The Visual Linear Clock instantly eliminates time blindness. See your day unfold at a glance and get the clarity and control you need.</p>
    </div>
    <div class="tt-card">
      <div class="tt-card-icon">✨</div>
      <h3>Break the Hyperfocus Spell</h3>
      <p>Seamless transitions start with gentle, clear alerts. If you go over your time, the app gently persists with non-stressful reminders to keep you on schedule.</p>
    </div>
    <div class="tt-card">
      <div class="tt-card-icon">🚀</div>
      <h3>Sustain Your Momentum</h3>
      <p>Get smart insights to perfectly balance effort and rest, helping you decide when to push forward and when to recharge.</p>
    </div>
  </div>
</section>

<!-- FULL FEATURE TOOLKIT -->
<section class="tt-section tt-section-darker">
  <div class="tt-section-heading">
    <div style="font-size:5rem;margin-bottom:.75rem;">🛠</div>
    <h2>Your Complete<br>Timing Toolkit</h2>
    <p>All the tools you need to visualize time and build focus.</p>
  </div>

  <div class="tt-toolkit-grid">
    <div class="tt-toolkit-col">
      <h4>👨‍✈️ YOUR ADHD CO-PILOT</h4>
      <ul>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Smart Time Blocking:</strong> Plan your day with intention and focus.</span>
        </li>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Automatic Break Calculations:</strong> Actively prevents burnout without you having to think about it.</span>
        </li>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Visual &amp; Spoken Alerts:</strong> A gentle co-pilot for task transitions.</span>
        </li>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Persistent Reminders:</strong> Gently breaks through hyperfocus without stress.</span>
        </li>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Multiple Timer Modes:</strong> The right tool for any timing need.</span>
        </li>
      </ul>
    </div>

    <div class="tt-toolkit-col">
      <h4>⏳ VISUALIZE YOUR TIME</h4>
      <ul>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Linear Clock:</strong> See your entire workday at a glance to fight time blindness.</span>
        </li>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Session Map:</strong> Understand exactly where your time goes.</span>
        </li>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Detailed Graphs &amp; Statistics:</strong> See your progress, discover patterns, and celebrate wins.</span>
        </li>
      </ul>
    </div>

    <div class="tt-toolkit-col">
      <h4>🎯 DESIGNED FOR FOCUS</h4>
      <ul>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Full Screen 'ZEN' Mode:</strong> A minimalist, distraction-free view.</span>
        </li>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Multiple Timer Face Styles:</strong> Customize your timer to fit your task.</span>
        </li>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Different English Accents:</strong> Choose a voice that feels comfortable and effective.</span>
        </li>
        <li>
          <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span><strong>Constant Time Awareness:</strong> Shows current day/time to keep you grounded.</span>
        </li>
      </ul>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section class="tt-section tt-section-dark">
  <div class="tt-section-heading">
    <h2>Loved by users everywhere</h2>
  </div>

  <div class="tt-testimonials-grid">
    <div class="tt-testimonial">
      <blockquote>"I've finally stopped my hyper focus ruining my ergonomics. Now I rarely work late into the evening."</blockquote>
      <div class="tt-testimonial-meta">
        <div><strong>Simon V.</strong><span>Designer</span></div>
        <span>⭐️⭐️⭐️⭐️⭐️</span>
      </div>
    </div>
    <div class="tt-testimonial">
      <blockquote>"Simple, effective! I wouldn't mind crisper graphics, but this is nice. I will tell other special educators about it!"</blockquote>
      <div class="tt-testimonial-meta">
        <div><strong>Anonymous</strong><span>Special Educator</span></div>
        <span>⭐️⭐️⭐️⭐️⭐️</span>
      </div>
    </div>
  </div>
</section>

<!-- FINAL CTA -->
<div class="tt-cta">
  <h2>Download TransitionTIMER</h2>
  <p>and take control of your day</p>

  <div class="store-badges">
    <a href="https://apps.apple.com/us/app/time-blindness-hyper-focus/id6634579526" target="_blank" rel="noopener">
      <img src="/assets/img/svg/appstore.svg" alt="Download on the App Store">
    </a>
    <a href="https://play.google.com/store/apps/details?id=com.workbreaktimer" target="_blank" rel="noopener">
      <img src="/assets/img/svg/google.svg" alt="Get it on Google Play">
    </a>
    <a href="https://www.amazon.com/gp/product/B0DSGTM66Y" target="_blank" rel="noopener">
      <img src="/assets/img/svg/amazon.svg" alt="Get it on Amazon Appstore">
    </a>
  </div>
</div>

<!-- SCREENSHOT MODAL -->
<div id="tt-modal" role="dialog" aria-modal="true" aria-label="Screenshot preview">
  <img id="tt-modal-img" src="" alt="Full size screenshot">
</div>

<script>
(function () {
  var modal = document.getElementById('tt-modal');
  var modalImg = document.getElementById('tt-modal-img');

  document.querySelectorAll('.tt-screenshot').forEach(function (img) {
    img.addEventListener('click', function () {
      modalImg.src = img.src;
      modal.classList.add('open');
    });
  });

  modal.addEventListener('click', function () {
    modal.classList.remove('open');
    modalImg.src = '';
  });

  document.addEventListener('keydown', function (e) {
    if (e.key === 'Escape') {
      modal.classList.remove('open');
      modalImg.src = '';
    }
  });
})();
</script>


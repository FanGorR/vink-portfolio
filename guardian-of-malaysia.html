/* ============================================================
   VinK Portfolio — Shared Scripts
   Include this in every page with:  <script src="../js/main.js"></script>
   (or "js/main.js" from root-level pages)
   ============================================================ */

(function () {
  /* ── CURSOR ──────────────────────────────────────────── */
  const cursor = document.getElementById('cursor');
  const ring   = document.getElementById('cursor-ring');
  if (cursor && ring) {
    let mx = 0, my = 0, rx = 0, ry = 0;
    document.addEventListener('mousemove', e => {
      mx = e.clientX; my = e.clientY;
      cursor.style.left = mx + 'px';
      cursor.style.top  = my + 'px';
      cursor.style.opacity = '1';
      ring.style.opacity   = '1';
    });
    (function animRing() {
      rx += (mx - rx) * 0.12;
      ry += (my - ry) * 0.12;
      ring.style.left = rx + 'px';
      ring.style.top  = ry + 'px';
      requestAnimationFrame(animRing);
    })();
    document.querySelectorAll('a, button, .card, .project-nav-link').forEach(el => {
      el.addEventListener('mouseenter', () => {
        cursor.style.width  = '18px'; cursor.style.height = '18px';
        ring.style.width    = '56px'; ring.style.height   = '56px';
      });
      el.addEventListener('mouseleave', () => {
        cursor.style.width  = '10px'; cursor.style.height = '10px';
        ring.style.width    = '36px'; ring.style.height   = '36px';
      });
    });
  }

  /* ── SCROLL REVEAL ───────────────────────────────────── */
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) e.target.classList.add('visible');
    });
  }, { threshold: 0.1 });
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

})();

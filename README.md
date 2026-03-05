/* ================================================
   CAFÉ LUMIÈRE – Main JavaScript
   ================================================ */

document.addEventListener('DOMContentLoaded', () => {

  /* ──────────────────────────────────────────
     1. HEADER – Scroll behaviour
  ────────────────────────────────────────── */
  const header = document.getElementById('header');

  window.addEventListener('scroll', () => {
    if (window.scrollY > 60) {
      header.classList.add('scrolled');
    } else {
      header.classList.remove('scrolled');
    }
  }, { passive: true });


  /* ──────────────────────────────────────────
     2. HERO – Ken Burns effect on load
  ────────────────────────────────────────── */
  const hero = document.querySelector('.hero');
  if (hero) {
    setTimeout(() => hero.classList.add('loaded'), 100);
  }


  /* ──────────────────────────────────────────
     3. HAMBURGER MENU
  ────────────────────────────────────────── */
  const hamburger   = document.getElementById('hamburger');
  const mobileMenu  = document.getElementById('mobileMenu');
  const mobileLinks = document.querySelectorAll('.mobile-link');

  const toggleMenu = (open) => {
    hamburger.classList.toggle('open', open);
    mobileMenu.classList.toggle('open', open);
    document.body.style.overflow = open ? 'hidden' : '';
  };

  hamburger.addEventListener('click', () => {
    const isOpen = mobileMenu.classList.contains('open');
    toggleMenu(!isOpen);
  });

  mobileLinks.forEach(link => {
    link.addEventListener('click', () => toggleMenu(false));
  });


  /* ──────────────────────────────────────────
     4. SMOOTH SCROLL (offset for fixed header)
  ────────────────────────────────────────── */
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', (e) => {
      const target = document.querySelector(anchor.getAttribute('href'));
      if (!target) return;
      e.preventDefault();
      const offset = header.offsetHeight + 20;
      const top = target.getBoundingClientRect().top + window.scrollY - offset;
      window.scrollTo({ top, behavior: 'smooth' });
    });
  });


  /* ──────────────────────────────────────────
     5. SCROLL REVEAL
  ────────────────────────────────────────── */
  const revealEls = document.querySelectorAll(
    '.about__text, .about__images, .feature, .menu__card, ' +
    '.gallery__item, .testimonial, .access__item, .access__map, ' +
    '.menu__seasonal-banner, .stat, .section__header'
  );

  revealEls.forEach(el => el.classList.add('reveal'));

  const revealObserver = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry, i) => {
        if (entry.isIntersecting) {
          // Stagger delay for siblings
          const siblings = [...entry.target.parentElement.children];
          const idx = siblings.indexOf(entry.target);
          entry.target.style.transitionDelay = `${idx * 0.08}s`;
          entry.target.classList.add('visible');
          revealObserver.unobserve(entry.target);
        }
      });
    },
    { threshold: 0.12 }
  );

  revealEls.forEach(el => revealObserver.observe(el));


  /* ──────────────────────────────────────────
     6. MENU TABS
  ────────────────────────────────────────── */
  const tabs     = document.querySelectorAll('.menu__tab');
  const contents = document.querySelectorAll('.menu__content');

  tabs.forEach(tab => {
    tab.addEventListener('click', () => {
      const target = tab.dataset.tab;

      tabs.forEach(t => t.classList.remove('active'));
      contents.forEach(c => c.classList.remove('active'));

      tab.classList.add('active');
      const content = document.getElementById(`tab-${target}`);
      if (content) content.classList.add('active');
    });
  });


  /* ──────────────────────────────────────────
     7. TESTIMONIALS SLIDER
  ────────────────────────────────────────── */
  const track = document.getElementById('testimonialTrack');
  const dotsContainer = document.getElementById('testimonialDots');

  if (track && dotsContainer) {
    const slides     = track.children;
    const totalSlides = slides.length;
    let current       = 0;
    let autoSlideTimer;

    // Build dots
    for (let i = 0; i < totalSlides; i++) {
      const dot = document.createElement('button');
      dot.className = 'dot' + (i === 0 ? ' active' : '');
      dot.setAttribute('aria-label', `スライド ${i + 1}`);
      dot.addEventListener('click', () => goTo(i));
      dotsContainer.appendChild(dot);
    }

    const goTo = (n) => {
      current = (n + totalSlides) % totalSlides;
      track.style.transform = `translateX(-${current * 100}%)`;
      dotsContainer.querySelectorAll('.dot').forEach((d, i) => {
        d.classList.toggle('active', i === current);
      });
    };

    const startAuto = () => {
      clearInterval(autoSlideTimer);
      autoSlideTimer = setInterval(() => goTo(current + 1), 5000);
    };

    dotsContainer.addEventListener('click', () => startAuto());
    startAuto();
  }


  /* ──────────────────────────────────────────
     8. CONTACT FORM
  ────────────────────────────────────────── */
  const contactForm    = document.getElementById('contactForm');
  const contactSuccess = document.getElementById('contactSuccess');

  if (contactForm) {
    contactForm.addEventListener('submit', async (e) => {
      e.preventDefault();

      const btn = contactForm.querySelector('.form__submit');
      btn.disabled = true;
      btn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> 送信中...';

      // Simulate async (or could POST to Table API)
      await new Promise(r => setTimeout(r, 1200));

      contactForm.style.display = 'none';
      contactSuccess.style.display = 'flex';

      // Save to Table API (optional persistence)
      try {
        const data = Object.fromEntries(new FormData(contactForm));
        await fetch('tables/reservations', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify(data)
        });
      } catch (_) { /* silent */ }
    });
  }


  /* ──────────────────────────────────────────
     9. NEWSLETTER FORM
  ────────────────────────────────────────── */
  const newsletterForm = document.getElementById('newsletterForm');

  if (newsletterForm) {
    newsletterForm.addEventListener('submit', async (e) => {
      e.preventDefault();
      const input = newsletterForm.querySelector('input');
      const btn   = newsletterForm.querySelector('button');

      btn.innerHTML = '<i class="fas fa-check"></i>';
      btn.style.background = '#4caf50';
      input.value = '';
      input.placeholder = '登録しました！';
      input.disabled = true;

      // Persist
      try {
        await fetch('tables/newsletter', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({ email: input.value })
        });
      } catch (_) { /* silent */ }
    });
  }


  /* ──────────────────────────────────────────
     10. BACK TO TOP
  ────────────────────────────────────────── */
  const backToTop = document.getElementById('backToTop');

  window.addEventListener('scroll', () => {
    backToTop.classList.toggle('visible', window.scrollY > 400);
  }, { passive: true });

  backToTop.addEventListener('click', () => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  });


  /* ──────────────────────────────────────────
     11. GALLERY – Lightbox
  ────────────────────────────────────────── */
  const galleryItems = document.querySelectorAll('.gallery__item');

  const lightbox = Object.assign(document.createElement('div'), {
    className: 'lightbox',
    innerHTML: `
      <button class="lightbox__close" aria-label="閉じる">&times;</button>
      <button class="lightbox__prev" aria-label="前の画像">&#8249;</button>
      <button class="lightbox__next" aria-label="次の画像">&#8250;</button>
      <div class="lightbox__img-wrap"><img class="lightbox__img" src="" alt="" /></div>
    `
  });
  document.body.appendChild(lightbox);

  // Lightbox styles (injected)
  const lbStyle = document.createElement('style');
  lbStyle.textContent = `
    .lightbox {
      display: none; position: fixed; inset: 0; z-index: 9000;
      background: rgba(0,0,0,0.92); align-items: center; justify-content: center;
    }
    .lightbox.open { display: flex; }
    .lightbox__img-wrap { max-width: 90vw; max-height: 85vh; }
    .lightbox__img { max-width: 90vw; max-height: 85vh; object-fit: contain; border-radius: 4px; }
    .lightbox__close {
      position: absolute; top: 1.5rem; right: 2rem; font-size: 2.5rem;
      color: #fff; background: none; border: none; cursor: pointer; line-height: 1; opacity: 0.8;
    }
    .lightbox__close:hover { opacity: 1; }
    .lightbox__prev, .lightbox__next {
      position: absolute; top: 50%; transform: translateY(-50%);
      font-size: 3rem; color: rgba(255,255,255,0.7); background: none; border: none;
      cursor: pointer; padding: 0 1rem; transition: color 0.2s;
    }
    .lightbox__prev { left: 1rem; }
    .lightbox__next { right: 1rem; }
    .lightbox__prev:hover, .lightbox__next:hover { color: #fff; }
  `;
  document.head.appendChild(lbStyle);

  const lbImg     = lightbox.querySelector('.lightbox__img');
  const lbClose   = lightbox.querySelector('.lightbox__close');
  const lbPrev    = lightbox.querySelector('.lightbox__prev');
  const lbNext    = lightbox.querySelector('.lightbox__next');
  let lbCurrent   = 0;
  const lbSrcs    = [...galleryItems].map(item => item.querySelector('img').src);

  const openLb = (i) => {
    lbCurrent = i;
    lbImg.src = lbSrcs[lbCurrent];
    lightbox.classList.add('open');
    document.body.style.overflow = 'hidden';
  };

  const closeLb = () => {
    lightbox.classList.remove('open');
    document.body.style.overflow = '';
  };

  const navLb = (dir) => {
    lbCurrent = (lbCurrent + dir + lbSrcs.length) % lbSrcs.length;
    lbImg.src = lbSrcs[lbCurrent];
  };

  galleryItems.forEach((item, i) => item.addEventListener('click', () => openLb(i)));
  lbClose.addEventListener('click', closeLb);
  lbPrev.addEventListener('click', () => navLb(-1));
  lbNext.addEventListener('click', () => navLb(1));
  lightbox.addEventListener('click', (e) => { if (e.target === lightbox) closeLb(); });
  document.addEventListener('keydown', (e) => {
    if (!lightbox.classList.contains('open')) return;
    if (e.key === 'Escape')      closeLb();
    if (e.key === 'ArrowLeft')   navLb(-1);
    if (e.key === 'ArrowRight')  navLb(1);
  });


  /* ──────────────────────────────────────────
     12. Active nav link on scroll
  ────────────────────────────────────────── */
  const sections    = document.querySelectorAll('section[id]');
  const navAnchors  = document.querySelectorAll('.nav__links a');

  const activateNav = () => {
    const scrollY = window.scrollY + header.offsetHeight + 80;
    sections.forEach(sec => {
      const top    = sec.offsetTop;
      const bottom = top + sec.offsetHeight;
      if (scrollY >= top && scrollY < bottom) {
        navAnchors.forEach(a => {
          a.style.color = '';
          if (a.getAttribute('href') === `#${sec.id}`) {
            a.style.color = 'var(--color-brown)';
          }
        });
      }
    });
  };

  window.addEventListener('scroll', activateNav, { passive: true });
  activateNav();

}); // end DOMContentLoaded

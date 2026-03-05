/* ================================================
   CAFÉ LUMIÈRE – Main Stylesheet
   ================================================ */

/* ---------- CSS Variables ---------- */
:root {
  --color-bg:         #faf8f4;
  --color-bg2:        #f3ede4;
  --color-dark:       #1a1410;
  --color-brown:      #6b4226;
  --color-gold:       #c9a96e;
  --color-gold-light: #e8d5b0;
  --color-text:       #3a2e26;
  --color-text-mute:  #7a6a5a;
  --color-white:      #ffffff;
  --color-border:     #e5ddd0;

  --font-serif:   'Playfair Display', 'Cormorant Garamond', Georgia, serif;
  --font-sans:    'Noto Sans JP', sans-serif;
  --font-eng:     'Cormorant Garamond', Georgia, serif;

  --radius:   12px;
  --shadow:   0 8px 40px rgba(107, 66, 38, 0.1);
  --shadow-sm: 0 4px 16px rgba(107, 66, 38, 0.08);
  --transition: 0.35s ease;
  --max-w: 1200px;
}

/* ---------- Reset & Base ---------- */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; font-size: 16px; }

body {
  font-family: var(--font-sans);
  background-color: var(--color-bg);
  color: var(--color-text);
  line-height: 1.8;
  overflow-x: hidden;
}

img { display: block; width: 100%; height: 100%; object-fit: cover; }

a { text-decoration: none; color: inherit; }

ul { list-style: none; }

button { cursor: pointer; border: none; background: none; font-family: inherit; }

/* ---------- Utility ---------- */
.container {
  max-width: var(--max-w);
  margin: 0 auto;
  padding: 0 2rem;
}

.section { padding: 100px 0; }

.section__header {
  text-align: center;
  margin-bottom: 4rem;
}

.section__label {
  display: inline-block;
  font-size: 0.72rem;
  font-family: var(--font-eng);
  letter-spacing: 0.25em;
  color: var(--color-gold);
  border-bottom: 1px solid var(--color-gold);
  padding-bottom: 4px;
  margin-bottom: 1rem;
}

.section__title {
  font-family: var(--font-serif);
  font-size: clamp(2rem, 4vw, 2.8rem);
  line-height: 1.4;
  color: var(--color-dark);
  margin-bottom: 1rem;
}

.section__desc {
  font-size: 0.95rem;
  color: var(--color-text-mute);
  max-width: 540px;
  margin: 0 auto;
}

/* ---------- Animations ---------- */
.fade-up {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeUp 0.9s var(--transition) forwards;
}
.delay-1 { animation-delay: 0.2s; }
.delay-2 { animation-delay: 0.4s; }
.delay-3 { animation-delay: 0.6s; }

@keyframes fadeUp {
  to { opacity: 1; transform: translateY(0); }
}

.reveal {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* ================================================
   HEADER / NAV
   ================================================ */
.header {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 1000;
  padding: 1.2rem 2.5rem;
  transition: background var(--transition), box-shadow var(--transition), padding var(--transition);
}

.header.scrolled {
  background: rgba(250, 248, 244, 0.97);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 20px rgba(107, 66, 38, 0.08);
  padding: 0.8rem 2.5rem;
}

.nav {
  max-width: var(--max-w);
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.nav__logo {
  font-family: var(--font-eng);
  font-size: 1.5rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  color: var(--color-dark);
  transition: color var(--transition);
}
.nav__logo:hover { color: var(--color-brown); }

.nav__links {
  display: flex;
  gap: 2.5rem;
  align-items: center;
}

.nav__links a {
  font-size: 0.72rem;
  letter-spacing: 0.18em;
  font-family: var(--font-eng);
  color: var(--color-text);
  position: relative;
  transition: color var(--transition);
}

.nav__links a::after {
  content: '';
  position: absolute;
  bottom: -3px; left: 0;
  width: 0; height: 1px;
  background: var(--color-gold);
  transition: width var(--transition);
}

.nav__links a:hover { color: var(--color-brown); }
.nav__links a:hover::after { width: 100%; }

.nav__cta {
  background: var(--color-brown) !important;
  color: var(--color-white) !important;
  padding: 0.55rem 1.4rem !important;
  border-radius: 2px;
  letter-spacing: 0.1em !important;
}
.nav__cta::after { display: none !important; }
.nav__cta:hover { background: var(--color-gold) !important; }

.nav__hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  width: 26px;
}
.nav__hamburger span {
  display: block;
  height: 1.5px;
  background: var(--color-dark);
  transition: all var(--transition);
  border-radius: 2px;
}
.nav__hamburger.open span:nth-child(1) { transform: rotate(45deg) translate(4px, 4px); }
.nav__hamburger.open span:nth-child(2) { opacity: 0; }
.nav__hamburger.open span:nth-child(3) { transform: rotate(-45deg) translate(4px, -4px); }

/* Mobile Menu */
.mobile-menu {
  position: fixed;
  top: 0; left: 0; right: 0;
  height: 100vh;
  background: var(--color-bg);
  z-index: 999;
  display: flex;
  align-items: center;
  justify-content: center;
  transform: translateY(-100%);
  transition: transform 0.5s cubic-bezier(0.77, 0, 0.175, 1);
}
.mobile-menu.open { transform: translateY(0); }

.mobile-menu ul {
  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 2.5rem;
}

.mobile-menu a {
  font-family: var(--font-eng);
  font-size: 1.8rem;
  letter-spacing: 0.2em;
  color: var(--color-dark);
  transition: color var(--transition);
}
.mobile-menu a:hover { color: var(--color-brown); }

/* ================================================
   HERO
   ================================================ */
.hero {
  position: relative;
  height: 100vh;
  min-height: 700px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.hero__bg {
  position: absolute;
  inset: 0;
  background: url('https://images.unsplash.com/photo-1511920170033-f8396924c348?w=1800&q=80') center/cover no-repeat;
  transform: scale(1.05);
  transition: transform 8s ease;
}

.hero.loaded .hero__bg { transform: scale(1); }

.hero__overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    135deg,
    rgba(26, 20, 16, 0.68) 0%,
    rgba(107, 66, 38, 0.3) 60%,
    rgba(201, 169, 110, 0.15) 100%
  );
}

.hero__content {
  position: relative;
  z-index: 2;
  text-align: center;
  color: var(--color-white);
  padding: 0 1.5rem;
  max-width: 780px;
}

.hero__sub {
  font-family: var(--font-eng);
  font-size: 0.85rem;
  letter-spacing: 0.35em;
  color: var(--color-gold-light);
  margin-bottom: 1.5rem;
}

.hero__title {
  font-family: var(--font-serif);
  font-size: clamp(2.8rem, 7vw, 5.5rem);
  line-height: 1.25;
  font-weight: 700;
  margin-bottom: 1.5rem;
  text-shadow: 0 2px 20px rgba(0,0,0,0.3);
}

.hero__desc {
  font-size: 1rem;
  line-height: 2;
  color: rgba(255,255,255,0.85);
  margin-bottom: 2.5rem;
  font-weight: 300;
}

.hero__btn {
  display: inline-block;
  padding: 1rem 3rem;
  border: 1.5px solid rgba(255,255,255,0.7);
  color: var(--color-white);
  font-family: var(--font-eng);
  font-size: 0.8rem;
  letter-spacing: 0.25em;
  transition: all var(--transition);
  position: relative;
  overflow: hidden;
}

.hero__btn::before {
  content: '';
  position: absolute;
  inset: 0;
  background: var(--color-gold);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform var(--transition);
  z-index: -1;
}

.hero__btn:hover {
  border-color: var(--color-gold);
  color: var(--color-dark);
}
.hero__btn:hover::before { transform: scaleX(1); }

.hero__scroll {
  position: absolute;
  bottom: 2.5rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.8rem;
  color: rgba(255,255,255,0.6);
  font-size: 0.65rem;
  letter-spacing: 0.2em;
  font-family: var(--font-eng);
  z-index: 2;
}

.hero__scroll-line {
  width: 1px;
  height: 50px;
  background: linear-gradient(to bottom, rgba(255,255,255,0.6), transparent);
  animation: scrollLine 2s ease-in-out infinite;
}

@keyframes scrollLine {
  0%, 100% { transform: scaleY(1); opacity: 1; }
  50% { transform: scaleY(0.5); opacity: 0.4; }
}

/* ================================================
   ABOUT
   ================================================ */
.about {
  background: var(--color-bg);
}

.about__grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: center;
}

.about__images {
  position: relative;
  height: 560px;
}

.about__img {
  position: absolute;
  border-radius: var(--radius);
  overflow: hidden;
  box-shadow: var(--shadow);
}

.about__img--main {
  width: 75%;
  height: 80%;
  top: 0; left: 0;
}

.about__img--sub {
  width: 52%;
  height: 50%;
  bottom: 0; right: 0;
  border: 6px solid var(--color-bg);
}

.about__text .section__label { margin-bottom: 0.8rem; }
.about__text .section__title { text-align: left; margin-bottom: 1.5rem; }

.about__text p {
  color: var(--color-text-mute);
  margin-bottom: 1rem;
  font-size: 0.95rem;
}

.about__stats {
  display: flex;
  gap: 2.5rem;
  margin-top: 2.5rem;
  padding-top: 2rem;
  border-top: 1px solid var(--color-border);
}

.stat { display: flex; flex-direction: column; }
.stat strong {
  font-family: var(--font-serif);
  font-size: 2rem;
  color: var(--color-brown);
  line-height: 1;
}
.stat span {
  font-size: 0.78rem;
  color: var(--color-text-mute);
  margin-top: 0.3rem;
}

/* ================================================
   FEATURES
   ================================================ */
.features {
  background: var(--color-dark);
  padding: 5rem 0;
}

.features__grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0;
}

.feature {
  padding: 3rem 2rem;
  text-align: center;
  border-right: 1px solid rgba(255,255,255,0.08);
  transition: background var(--transition);
}
.feature:last-child { border-right: none; }
.feature:hover { background: rgba(201, 169, 110, 0.08); }

.feature__icon {
  width: 64px; height: 64px;
  border: 1px solid var(--color-gold);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
  transition: all var(--transition);
}

.feature:hover .feature__icon {
  background: var(--color-gold);
  color: var(--color-dark);
}

.feature__icon i { font-size: 1.3rem; color: var(--color-gold); }
.feature:hover .feature__icon i { color: var(--color-dark); }

.feature h3 {
  font-family: var(--font-eng);
  font-size: 1.1rem;
  letter-spacing: 0.05em;
  color: var(--color-white);
  margin-bottom: 0.8rem;
}

.feature p {
  font-size: 0.85rem;
  color: rgba(255,255,255,0.55);
  line-height: 1.8;
}

/* ================================================
   MENU
   ================================================ */
.menu { background: var(--color-bg2); }

.menu__tabs {
  display: flex;
  justify-content: center;
  gap: 0;
  margin-bottom: 3rem;
  border: 1px solid var(--color-border);
  border-radius: 4px;
  overflow: hidden;
  width: fit-content;
  margin-left: auto;
  margin-right: auto;
}

.menu__tab {
  padding: 0.75rem 2.5rem;
  font-size: 0.75rem;
  letter-spacing: 0.18em;
  font-family: var(--font-eng);
  color: var(--color-text-mute);
  background: transparent;
  transition: all var(--transition);
  border-right: 1px solid var(--color-border);
}
.menu__tab:last-child { border-right: none; }
.menu__tab.active, .menu__tab:hover {
  background: var(--color-brown);
  color: var(--color-white);
}

.menu__content { display: none; }
.menu__content.active { display: block; }

.menu__grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
}

.menu__card {
  background: var(--color-white);
  border-radius: var(--radius);
  overflow: hidden;
  box-shadow: var(--shadow-sm);
  transition: transform var(--transition), box-shadow var(--transition);
}

.menu__card:hover {
  transform: translateY(-6px);
  box-shadow: var(--shadow);
}

.menu__card-img {
  height: 200px;
  overflow: hidden;
}
.menu__card-img img { transition: transform 0.6s ease; }
.menu__card:hover .menu__card-img img { transform: scale(1.07); }

.menu__card-body {
  padding: 1.4rem;
}
.menu__card-body h3 {
  font-family: var(--font-serif);
  font-size: 1.15rem;
  margin-bottom: 0.5rem;
  color: var(--color-dark);
}
.menu__card-body p {
  font-size: 0.83rem;
  color: var(--color-text-mute);
  line-height: 1.7;
  margin-bottom: 1rem;
}
.menu__price {
  font-family: var(--font-eng);
  font-size: 1.1rem;
  color: var(--color-brown);
  font-weight: 600;
}

/* Seasonal */
.menu__seasonal-banner {
  background: var(--color-white);
  border-radius: var(--radius);
  padding: 3.5rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
  box-shadow: var(--shadow-sm);
}

.menu__seasonal-text h3 {
  font-family: var(--font-serif);
  font-size: 2rem;
  line-height: 1.4;
  color: var(--color-dark);
  margin: 0.8rem 0 1rem;
}

.menu__seasonal-text p {
  color: var(--color-text-mute);
  font-size: 0.9rem;
}

.menu__seasonal-items {
  display: flex;
  flex-direction: column;
  gap: 0;
}

.seasonal-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.2rem 0;
  border-bottom: 1px dashed var(--color-border);
}
.seasonal-item:last-child { border-bottom: none; }

.seasonal-item__name {
  font-family: var(--font-eng);
  font-size: 1.05rem;
  color: var(--color-dark);
}
.seasonal-item__price {
  font-family: var(--font-eng);
  font-size: 1.1rem;
  color: var(--color-brown);
  font-weight: 600;
}

/* ================================================
   GALLERY
   ================================================ */
.gallery { background: var(--color-bg); }

.gallery__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: auto auto;
  gap: 8px;
  margin-top: 1rem;
}

.gallery__item {
  position: relative;
  overflow: hidden;
  aspect-ratio: 1;
  cursor: pointer;
}

.gallery__item--tall {
  grid-row: span 2;
  aspect-ratio: unset;
}

.gallery__item--wide {
  grid-column: span 2;
  aspect-ratio: 2/1;
}

.gallery__item img {
  width: 100%; height: 100%;
  transition: transform 0.6s ease;
}
.gallery__item:hover img { transform: scale(1.06); }

.gallery__overlay {
  position: absolute;
  inset: 0;
  background: rgba(26, 20, 16, 0);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background var(--transition);
}

.gallery__overlay span {
  color: var(--color-white);
  font-family: var(--font-eng);
  font-size: 0.85rem;
  letter-spacing: 0.3em;
  opacity: 0;
  transform: translateY(10px);
  transition: all var(--transition);
}

.gallery__item:hover .gallery__overlay {
  background: rgba(26, 20, 16, 0.45);
}
.gallery__item:hover .gallery__overlay span {
  opacity: 1;
  transform: translateY(0);
}

/* ================================================
   TESTIMONIALS
   ================================================ */
.testimonials { background: var(--color-bg2); }

.testimonials__slider {
  position: relative;
  overflow: hidden;
  max-width: 720px;
  margin: 0 auto;
}

.testimonials__track {
  display: flex;
  transition: transform 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

.testimonial {
  min-width: 100%;
  padding: 3rem;
  background: var(--color-white);
  border-radius: var(--radius);
  text-align: center;
  box-shadow: var(--shadow-sm);
}

.testimonial__stars {
  color: var(--color-gold);
  margin-bottom: 1.5rem;
  font-size: 1rem;
  letter-spacing: 4px;
}

.testimonial__text {
  font-size: 1rem;
  line-height: 1.9;
  color: var(--color-text);
  font-style: italic;
  margin-bottom: 2rem;
}

.testimonial__author {
  display: flex;
  flex-direction: column;
  gap: 0.2rem;
}
.testimonial__author strong {
  font-family: var(--font-eng);
  font-size: 1rem;
  color: var(--color-dark);
}
.testimonial__author span {
  font-size: 0.8rem;
  color: var(--color-text-mute);
}

.testimonials__dots {
  display: flex;
  justify-content: center;
  gap: 0.6rem;
  margin-top: 1.8rem;
}

.dot {
  width: 8px; height: 8px;
  border-radius: 50%;
  background: var(--color-border);
  cursor: pointer;
  transition: all var(--transition);
}
.dot.active {
  background: var(--color-brown);
  width: 24px;
  border-radius: 4px;
}

/* ================================================
   ACCESS
   ================================================ */
.access { background: var(--color-bg); }

.access__grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.access__item {
  display: flex;
  gap: 1.2rem;
  align-items: flex-start;
  padding: 1.5rem 0;
  border-bottom: 1px solid var(--color-border);
}
.access__item:last-child { border-bottom: none; }

.access__item > i {
  font-size: 1rem;
  color: var(--color-gold);
  margin-top: 0.25rem;
  width: 20px;
  flex-shrink: 0;
}

.access__item strong {
  display: block;
  font-size: 0.78rem;
  letter-spacing: 0.1em;
  color: var(--color-text-mute);
  margin-bottom: 0.4rem;
}

.access__item p {
  font-size: 0.92rem;
  line-height: 1.8;
  color: var(--color-dark);
}

.access__map {
  border-radius: var(--radius);
  overflow: hidden;
  height: 420px;
  box-shadow: var(--shadow);
}

.map__placeholder {
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, var(--color-bg2), var(--color-gold-light));
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  text-align: center;
  cursor: pointer;
  transition: background var(--transition);
}
.map__placeholder:hover { background: linear-gradient(135deg, var(--color-gold-light), var(--color-gold)); }

.map__placeholder i {
  font-size: 3rem;
  color: var(--color-brown);
}
.map__placeholder p {
  font-size: 0.9rem;
  color: var(--color-dark);
}
.map__placeholder span {
  font-family: var(--font-eng);
  font-size: 0.85rem;
  color: var(--color-brown);
  border-bottom: 1px solid var(--color-brown);
  padding-bottom: 2px;
}

/* ================================================
   CONTACT
   ================================================ */
.contact {
  background: var(--color-dark);
}

.contact .section__label { color: var(--color-gold); }
.contact .section__title { color: var(--color-white); }
.contact .section__desc { color: rgba(255,255,255,0.55); }

.contact__form {
  max-width: 720px;
  margin: 0 auto;
}

.form__row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5rem;
  margin-bottom: 1.5rem;
}

.form__group {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}
.form__row .form__group { margin-bottom: 0; }

.form__group label {
  font-size: 0.78rem;
  letter-spacing: 0.08em;
  color: rgba(255,255,255,0.65);
}

.form__group input,
.form__group select,
.form__group textarea {
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: 6px;
  padding: 0.85rem 1.1rem;
  color: var(--color-white);
  font-family: var(--font-sans);
  font-size: 0.9rem;
  transition: border-color var(--transition), background var(--transition);
  outline: none;
  width: 100%;
}

.form__group select option { background: var(--color-dark); color: var(--color-white); }

.form__group input::placeholder,
.form__group textarea::placeholder {
  color: rgba(255,255,255,0.3);
}

.form__group input:focus,
.form__group select:focus,
.form__group textarea:focus {
  border-color: var(--color-gold);
  background: rgba(201, 169, 110, 0.06);
}

.form__group textarea { resize: vertical; }

.form__submit {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  padding: 1rem 3rem;
  background: var(--color-gold);
  color: var(--color-dark);
  font-family: var(--font-sans);
  font-size: 0.9rem;
  font-weight: 500;
  border-radius: 4px;
  margin: 0 auto;
  transition: all var(--transition);
  letter-spacing: 0.05em;
}

.form__submit:hover {
  background: var(--color-white);
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(201, 169, 110, 0.3);
}

.contact__success {
  display: none;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  text-align: center;
  padding: 3rem;
  max-width: 480px;
  margin: 0 auto;
}

.contact__success i {
  font-size: 3rem;
  color: var(--color-gold);
}

.contact__success p {
  color: rgba(255,255,255,0.8);
  line-height: 1.9;
}

/* ================================================
   FOOTER
   ================================================ */
.footer {
  background: #120e0b;
  padding: 5rem 0 2rem;
}

.footer__grid {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 2fr;
  gap: 3rem;
  padding-bottom: 3rem;
  border-bottom: 1px solid rgba(255,255,255,0.08);
  margin-bottom: 2rem;
}

.footer__logo {
  font-family: var(--font-eng);
  font-size: 1.6rem;
  color: var(--color-white);
  letter-spacing: 0.15em;
  margin-bottom: 0.8rem;
}

.footer__tagline {
  font-size: 0.82rem;
  color: rgba(255,255,255,0.45);
  margin-bottom: 1.5rem;
}

.footer__social {
  display: flex;
  gap: 0.8rem;
}

.footer__social a {
  width: 38px; height: 38px;
  border: 1px solid rgba(255,255,255,0.15);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgba(255,255,255,0.6);
  font-size: 0.85rem;
  transition: all var(--transition);
}
.footer__social a:hover {
  border-color: var(--color-gold);
  color: var(--color-gold);
  background: rgba(201, 169, 110, 0.1);
}

.footer__links h4,
.footer__newsletter h4 {
  font-size: 0.72rem;
  letter-spacing: 0.2em;
  color: var(--color-gold);
  margin-bottom: 1.5rem;
  font-family: var(--font-eng);
}

.footer__links ul {
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
}

.footer__links li,
.footer__links a {
  font-size: 0.85rem;
  color: rgba(255,255,255,0.5);
  transition: color var(--transition);
}
.footer__links a:hover { color: var(--color-gold); }

.footer__newsletter p {
  font-size: 0.83rem;
  color: rgba(255,255,255,0.45);
  margin-bottom: 1rem;
  line-height: 1.7;
}

.newsletter__form {
  display: flex;
  border: 1px solid rgba(255,255,255,0.15);
  border-radius: 4px;
  overflow: hidden;
}

.newsletter__form input {
  flex: 1;
  background: transparent;
  border: none;
  padding: 0.75rem 1rem;
  color: var(--color-white);
  font-family: var(--font-sans);
  font-size: 0.85rem;
  outline: none;
}
.newsletter__form input::placeholder { color: rgba(255,255,255,0.3); }

.newsletter__form button {
  padding: 0 1.2rem;
  background: var(--color-gold);
  color: var(--color-dark);
  transition: background var(--transition);
}
.newsletter__form button:hover { background: var(--color-white); }

.footer__bottom {
  text-align: center;
  font-size: 0.78rem;
  color: rgba(255,255,255,0.25);
  letter-spacing: 0.05em;
}

/* ================================================
   BACK TO TOP
   ================================================ */
.back-to-top {
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  width: 46px; height: 46px;
  background: var(--color-brown);
  color: var(--color-white);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 20px rgba(107, 66, 38, 0.3);
  opacity: 0;
  transform: translateY(20px);
  transition: all var(--transition);
  z-index: 500;
  pointer-events: none;
}

.back-to-top.visible {
  opacity: 1;
  transform: translateY(0);
  pointer-events: all;
}

.back-to-top:hover {
  background: var(--color-gold);
  transform: translateY(-4px);
}

/* ================================================
   RESPONSIVE
   ================================================ */
@media (max-width: 1024px) {
  .about__grid { grid-template-columns: 1fr; gap: 3rem; }
  .about__images { height: 380px; max-width: 560px; margin: 0 auto; }
  .features__grid { grid-template-columns: repeat(2, 1fr); }
  .feature { border-right: none; border-bottom: 1px solid rgba(255,255,255,0.08); }
  .feature:nth-child(odd) { border-right: 1px solid rgba(255,255,255,0.08); }
  .feature:nth-last-child(-n+2) { border-bottom: none; }
  .menu__grid { grid-template-columns: repeat(2, 1fr); }
  .footer__grid { grid-template-columns: 1fr 1fr; gap: 2.5rem; }
}

@media (max-width: 768px) {
  .section { padding: 70px 0; }
  .nav__links { display: none; }
  .nav__hamburger { display: flex; }
  .hero__title { font-size: clamp(2.4rem, 9vw, 3.5rem); }
  .about__images { height: 300px; }
  .about__stats { gap: 1.5rem; }
  .menu__grid { grid-template-columns: 1fr; }
  .menu__seasonal-banner { grid-template-columns: 1fr; padding: 2rem; }
  .gallery__grid { grid-template-columns: 1fr 1fr; }
  .gallery__item--tall { grid-row: span 1; }
  .gallery__item--wide { grid-column: span 2; }
  .access__grid { grid-template-columns: 1fr; }
  .access__map { height: 280px; }
  .form__row { grid-template-columns: 1fr; }
  .footer__grid { grid-template-columns: 1fr; gap: 2rem; }
  .testimonial { padding: 2rem 1.5rem; }
}

@media (max-width: 480px) {
  .container { padding: 0 1.2rem; }
  .section__title { font-size: 1.8rem; }
  .gallery__grid { grid-template-columns: 1fr; }
  .gallery__item--wide { grid-column: span 1; aspect-ratio: 1; }
  .gallery__item--tall { aspect-ratio: 1; }
  .features__grid { grid-template-columns: 1fr; }
  .feature:nth-child(odd) { border-right: none; }
  .feature { border-bottom: 1px solid rgba(255,255,255,0.08); }
  .about__stats { flex-direction: column; gap: 1rem; }
}

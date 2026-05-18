[index (16).html](https://github.com/user-attachments/files/27978325/index.16.html)
# my-website<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Waymaker Auto Services LLC</title>
  <link rel="icon" type="image/x-icon" href="waymaker_favicon.ico" />
  <link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;600;700;800&family=Barlow:wght@400;500;600&display=swap" rel="stylesheet" />
  <style>
    :root {
      --navy: #0d1b2e;
      --navy-mid: #162440;
      --red: #b81c2e;
      --red-dark: #8f1522;
      --silver: #c8cdd4;
      --white: #f5f7fa;
      --light-bg: #f0f2f5;
      --text-dark: #0d1b2e;
      --text-muted: #5a6a7e;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Barlow', sans-serif;
      background: var(--white);
      color: var(--text-dark);
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 1000;
      background: rgba(13, 27, 46, 0.97);
      backdrop-filter: blur(8px);
      border-bottom: 2px solid var(--red);
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 5%;
      height: 72px;
    }

    .nav-logo {
      display: flex;
      align-items: center;
      gap: 12px;
      text-decoration: none;
    }

    .nav-logo img {
      height: 58px;
      object-fit: contain;
      background: #ffffff;
      border-radius: 10px;
      padding: 4px 14px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.2);
    }

    .nav-links {
      display: flex;
      gap: 32px;
      list-style: none;
    }

    .nav-links a {
      color: var(--silver);
      text-decoration: none;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1rem;
      font-weight: 600;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--red); }

    .nav-cta {
      background: var(--red);
      color: #fff !important;
      padding: 10px 22px;
      border-radius: 4px;
      transition: background 0.2s !important;
    }

    .nav-cta:hover { background: var(--red-dark) !important; color: #fff !important; }

    .hamburger {
      display: none;
      flex-direction: column;
      gap: 5px;
      cursor: pointer;
      padding: 4px;
    }

    .hamburger span {
      display: block;
      width: 26px;
      height: 2px;
      background: var(--silver);
      transition: all 0.3s;
    }

    /* ── HERO ── */
    #home {
      min-height: 100vh;
      background: linear-gradient(135deg, var(--navy) 0%, #1a2e4a 60%, #0d1b2e 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 120px 5% 80px;
      position: relative;
      overflow: hidden;
    }

    #home::before {
      content: '';
      position: absolute;
      inset: 0;
      background:
        radial-gradient(ellipse 80% 60% at 50% 110%, rgba(184,28,46,0.18) 0%, transparent 70%),
        radial-gradient(ellipse 60% 40% at 80% 20%, rgba(200,205,212,0.05) 0%, transparent 60%);
      pointer-events: none;
    }

    /* Diagonal accent lines */
    #home::after {
      content: '';
      position: absolute;
      top: 0; left: -10%;
      width: 120%;
      height: 100%;
      background: repeating-linear-gradient(
        -55deg,
        transparent,
        transparent 80px,
        rgba(255,255,255,0.012) 80px,
        rgba(255,255,255,0.012) 81px
      );
      pointer-events: none;
    }

    .hero-content { position: relative; z-index: 1; max-width: 800px; }

    .hero-logo {
      width: min(360px, 78vw);
      margin-bottom: 36px;
      background: #ffffff;
      border-radius: 18px;
      padding: 16px 28px;
      box-shadow: 0 8px 32px rgba(0,0,0,0.3);
      animation: fadeUp 0.9s ease both;
    }

    .hero-tagline {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: clamp(2rem, 5vw, 3.2rem);
      font-weight: 800;
      color: #fff;
      text-transform: uppercase;
      letter-spacing: 0.04em;
      line-height: 1.1;
      margin-bottom: 18px;
      animation: fadeUp 0.9s 0.15s ease both;
    }

    .hero-tagline span { color: var(--red); }

    .hero-sub {
      font-size: clamp(1rem, 2.5vw, 1.15rem);
      color: var(--silver);
      max-width: 580px;
      margin: 0 auto 36px;
      line-height: 1.7;
      animation: fadeUp 0.9s 0.3s ease both;
    }

    .hero-buttons {
      display: flex;
      gap: 16px;
      justify-content: center;
      flex-wrap: wrap;
      animation: fadeUp 0.9s 0.45s ease both;
    }

    .btn-primary {
      background: var(--red);
      color: #fff;
      padding: 14px 32px;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.05rem;
      font-weight: 700;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      text-decoration: none;
      border-radius: 4px;
      border: 2px solid var(--red);
      transition: all 0.25s;
      cursor: pointer;
      display: inline-block;
    }

    .btn-primary:hover {
      background: var(--red-dark);
      border-color: var(--red-dark);
      transform: translateY(-2px);
      box-shadow: 0 8px 24px rgba(184,28,46,0.35);
    }

    .btn-outline {
      background: transparent;
      color: #fff;
      padding: 14px 32px;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.05rem;
      font-weight: 700;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      text-decoration: none;
      border-radius: 4px;
      border: 2px solid rgba(255,255,255,0.4);
      transition: all 0.25s;
      cursor: pointer;
      display: inline-block;
    }

    .btn-outline:hover {
      border-color: #fff;
      background: rgba(255,255,255,0.07);
      transform: translateY(-2px);
    }

    .hero-scripture {
      margin-top: 48px;
      font-size: 0.85rem;
      color: rgba(200,205,212,0.45);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      animation: fadeUp 0.9s 0.6s ease both;
    }

    /* ── TRUST BAR ── */
    .trust-bar {
      background: var(--red);
      padding: 18px 5%;
      display: flex;
      justify-content: center;
      gap: clamp(24px, 5vw, 80px);
      flex-wrap: wrap;
    }

    .trust-item {
      display: flex;
      align-items: center;
      gap: 10px;
      color: #fff;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1rem;
      font-weight: 600;
      letter-spacing: 0.07em;
      text-transform: uppercase;
    }

    .trust-item svg { flex-shrink: 0; }

    /* ── SECTION BASE ── */
    section { padding: 90px 5%; }

    .section-label {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--red);
      margin-bottom: 10px;
    }

    .section-title {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: clamp(1.9rem, 4vw, 2.8rem);
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 0.03em;
      color: var(--navy);
      line-height: 1.1;
      margin-bottom: 16px;
    }

    .section-sub {
      font-size: 1.05rem;
      color: var(--text-muted);
      max-width: 560px;
      line-height: 1.7;
    }

    .section-divider {
      width: 52px;
      height: 3px;
      background: var(--red);
      margin: 16px 0 32px;
    }

    /* ── SERVICES ── */
    #services { background: var(--light-bg); }

    .services-header { text-align: center; margin-bottom: 56px; }
    .services-header .section-sub { margin: 0 auto; }
    .services-header .section-divider { margin: 16px auto 0; }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 28px;
      max-width: 1200px;
      margin: 0 auto;
    }

    .service-card {
      background: #fff;
      border-radius: 8px;
      padding: 36px 30px;
      border-top: 4px solid var(--red);
      box-shadow: 0 2px 16px rgba(13,27,46,0.07);
      transition: transform 0.25s, box-shadow 0.25s;
    }

    .service-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 12px 32px rgba(13,27,46,0.13);
    }

    .service-icon {
      width: 52px;
      height: 52px;
      background: var(--navy);
      border-radius: 6px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 20px;
    }

    .service-card h3 {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.25rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: var(--navy);
      margin-bottom: 12px;
    }

    .service-card p {
      font-size: 0.95rem;
      color: var(--text-muted);
      line-height: 1.7;
    }

    /* ── HOW IT WORKS ── */
    #how-it-works { background: var(--navy); }

    #how-it-works .section-title { color: #fff; }
    #how-it-works .section-sub { color: var(--silver); }

    .steps-wrapper {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 0;
      max-width: 1100px;
      margin: 0 auto;
      position: relative;
    }

    .steps-wrapper::before {
      content: '';
      position: absolute;
      top: 36px;
      left: 10%;
      right: 10%;
      height: 2px;
      background: linear-gradient(90deg, var(--red) 0%, rgba(184,28,46,0.2) 100%);
    }

    .step {
      text-align: center;
      padding: 0 20px;
      position: relative;
    }

    .step-number {
      width: 72px;
      height: 72px;
      background: var(--red);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 20px;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.6rem;
      font-weight: 800;
      color: #fff;
      position: relative;
      z-index: 1;
      border: 3px solid var(--navy);
      box-shadow: 0 0 0 3px var(--red);
    }

    .step h3 {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.1rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      color: #fff;
      margin-bottom: 10px;
    }

    .step p {
      font-size: 0.9rem;
      color: var(--silver);
      line-height: 1.6;
    }

    /* ── ABOUT ── */
    #about {
      background: var(--white);
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 64px;
      align-items: center;
      max-width: 1200px;
      margin: 0 auto;
    }

    #about-section { background: var(--white); }

    .about-visual {
      position: relative;
    }

    .about-badge {
      background: #ffffff;
      border-radius: 10px;
      padding: 48px 40px;
      text-align: center;
      border: 2px solid rgba(13,27,46,0.1);
      box-shadow: 0 8px 40px rgba(13,27,46,0.12);
    }

    .about-badge img {
      width: 240px;
      margin-bottom: 28px;
      background: #ffffff;
      border-radius: 12px;
      padding: 10px 20px;
    }

    .about-values {
      display: flex;
      justify-content: center;
      gap: 24px;
      flex-wrap: wrap;
    }

    .value-pill {
      background: var(--navy);
      color: #fff;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.85rem;
      font-weight: 700;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      padding: 8px 18px;
      border-radius: 20px;
    }

    .about-text p {
      font-size: 1rem;
      color: var(--text-muted);
      line-height: 1.8;
      margin-bottom: 18px;
    }

    .about-scripture {
      margin-top: 28px;
      padding: 20px 24px;
      background: var(--light-bg);
      border-left: 4px solid var(--red);
      border-radius: 0 6px 6px 0;
    }

    .about-scripture p {
      font-style: italic;
      color: var(--text-muted);
      margin-bottom: 6px !important;
      font-size: 0.95rem !important;
    }

    .about-scripture cite {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.8rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--red);
      font-style: normal;
    }

    /* ── CONTACT ── */
    #contact { background: var(--light-bg); }

    .contact-wrapper {
      display: grid;
      grid-template-columns: 1fr 1.4fr;
      gap: 56px;
      max-width: 1100px;
      margin: 0 auto;
      align-items: start;
    }

    .contact-info h3 {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.5rem;
      font-weight: 700;
      text-transform: uppercase;
      color: var(--navy);
      margin-bottom: 16px;
    }

    .contact-info p {
      color: var(--text-muted);
      line-height: 1.7;
      margin-bottom: 28px;
    }

    .contact-detail {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-bottom: 16px;
      font-size: 0.97rem;
      color: var(--text-dark);
    }

    .contact-detail-icon {
      width: 40px;
      height: 40px;
      background: var(--navy);
      border-radius: 6px;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
    }

    .contact-form {
      background: #fff;
      border-radius: 10px;
      padding: 40px;
      box-shadow: 0 4px 24px rgba(13,27,46,0.09);
    }

    .form-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
    }

    .form-group {
      margin-bottom: 18px;
    }

    .form-group label {
      display: block;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.85rem;
      font-weight: 700;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--navy);
      margin-bottom: 7px;
    }

    .form-group input,
    .form-group select,
    .form-group textarea {
      width: 100%;
      padding: 12px 16px;
      border: 1.5px solid #dde2ea;
      border-radius: 5px;
      font-family: 'Barlow', sans-serif;
      font-size: 0.97rem;
      color: var(--text-dark);
      background: #fafbfc;
      transition: border-color 0.2s, box-shadow 0.2s;
      appearance: none;
    }

    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus {
      outline: none;
      border-color: var(--red);
      box-shadow: 0 0 0 3px rgba(184,28,46,0.1);
      background: #fff;
    }

    .form-group textarea { resize: vertical; min-height: 110px; }

    .form-submit {
      width: 100%;
      background: var(--red);
      color: #fff;
      border: none;
      padding: 15px;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.1rem;
      font-weight: 700;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.25s, transform 0.2s;
      margin-top: 6px;
    }

    .form-submit:hover {
      background: var(--red-dark);
      transform: translateY(-2px);
    }

    /* ── FAQ ── */
    #faq { background: var(--white); }
    .faq-inner { max-width: 780px; margin: 0 auto; }
    .faq-header { text-align: center; margin-bottom: 48px; }
    .faq-header .section-divider { margin: 16px auto 0; }

    .faq-item {
      border-bottom: 1px solid #e2e6ed;
      overflow: hidden;
    }

    .faq-question {
      width: 100%;
      background: none;
      border: none;
      padding: 22px 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      cursor: pointer;
      text-align: left;
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.1rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: var(--navy);
      gap: 16px;
    }

    .faq-question:hover { color: var(--red); }

    .faq-icon {
      width: 28px;
      height: 28px;
      background: var(--navy);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
      transition: background 0.2s, transform 0.3s;
      color: #fff;
      font-size: 1.1rem;
      font-weight: 400;
      line-height: 1;
    }

    .faq-item.open .faq-icon {
      background: var(--red);
      transform: rotate(45deg);
    }

    .faq-answer {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.35s ease, padding 0.3s;
    }

    .faq-answer p {
      padding-bottom: 22px;
      font-size: 0.97rem;
      color: var(--text-muted);
      line-height: 1.75;
    }

    /* ── FOOTER ── */
    footer {
      background: var(--navy);
      padding: 56px 5% 32px;
      border-top: 3px solid var(--red);
    }

    .footer-top {
      display: grid;
      grid-template-columns: 1.5fr 1fr 1fr;
      gap: 48px;
      margin-bottom: 40px;
    }

    .footer-brand img {
      height: 70px;
      margin-bottom: 16px;
      background: #ffffff;
      border-radius: 10px;
      padding: 6px 16px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.2);
      display: block;
    }

    .footer-brand p {
      color: var(--silver);
      font-size: 0.9rem;
      line-height: 1.7;
      max-width: 300px;
    }

    .footer-col h4 {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 0.85rem;
      font-weight: 700;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--red);
      margin-bottom: 16px;
    }

    .footer-col ul { list-style: none; }
    .footer-col ul li { margin-bottom: 10px; }
    .footer-col ul li a {
      color: var(--silver);
      text-decoration: none;
      font-size: 0.92rem;
      transition: color 0.2s;
    }
    .footer-col ul li a:hover { color: #fff; }

    .footer-bottom {
      border-top: 1px solid rgba(255,255,255,0.1);
      padding-top: 24px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 12px;
    }

    .footer-bottom p {
      color: rgba(200,205,212,0.5);
      font-size: 0.82rem;
    }

    .footer-scripture {
      color: rgba(200,205,212,0.45);
      font-size: 0.78rem;
      letter-spacing: 0.08em;
      font-style: italic;
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── SUCCESS MESSAGE ── */
    .form-success {
      display: none;
      text-align: center;
      padding: 24px;
    }
    .form-success.show { display: block; }
    .form-success h3 {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.4rem;
      color: var(--navy);
      text-transform: uppercase;
      margin-bottom: 8px;
    }
    .form-success p { color: var(--text-muted); }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      #about {
        grid-template-columns: 1fr;
        gap: 40px;
        padding: 70px 5%;
      }

      .contact-wrapper {
        grid-template-columns: 1fr;
      }

      .footer-top {
        grid-template-columns: 1fr 1fr;
      }

      .steps-wrapper::before { display: none; }

      .form-row { grid-template-columns: 1fr; }
    }

    @media (max-width: 640px) {
      nav { padding: 0 4%; }
      .nav-links { display: none; }
      .nav-links.open {
        display: flex;
        flex-direction: column;
        position: absolute;
        top: 72px;
        left: 0; right: 0;
        background: var(--navy);
        padding: 20px 5%;
        border-bottom: 2px solid var(--red);
        gap: 16px;
      }
      .hamburger { display: flex; }
      .footer-top { grid-template-columns: 1fr; }
      .contact-form { padding: 28px 20px; }
      .steps-wrapper { gap: 32px; }
      .pricing-bottom-grid { grid-template-columns: 1fr !important; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#home" class="nav-logo">
    <img src="logosealedbadge.png" alt="Waymaker Auto Services" />
  </a>
  <ul class="nav-links" id="navLinks">
    <li><a href="#services">Services</a></li>
    <li><a href="#how-it-works">How It Works</a></li>
    <li><a href="#about-section">About</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#faq">FAQ</a></li>
    <li><a href="#contact" class="nav-cta">Get Started</a></li>
  </ul>
  <div class="hamburger" id="hamburger" onclick="toggleMenu()" aria-label="Menu">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- HERO -->
<section id="home">
  <div class="hero-content">
    <img src="logosealedbadge.png" alt="Waymaker Auto Services" class="hero-logo" />
    <h1 class="hero-tagline">We Make A <span>Way</span><br>For Your Next Vehicle</h1>
    <p class="hero-sub">We handle the search, negotiation, inspection, and paperwork — so you drive away with confidence and zero stress.</p>
    <div class="hero-buttons">
      <a href="#contact" class="btn-primary">Book a Free Consultation</a>
      <a href="#how-it-works" class="btn-outline">See How It Works</a>
    </div>
    <p class="hero-scripture">John 14:6 · Honesty · Transparency · Results</p>
  </div>
</section>

<!-- TRUST BAR -->
<div class="trust-bar">
  <div class="trust-item">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
    No Hidden Fees
  </div>
  <div class="trust-item">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
    3rd Party Inspection
  </div>
  <div class="trust-item">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
    Expert Negotiation
  </div>
  <div class="trust-item">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
    Trade-In Assistance
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="services-header">
    <p class="section-label">What We Do</p>
    <h2 class="section-title">Our Services</h2>
    <div class="section-divider"></div>
    <p class="section-sub">From the first search to the final signature, we stand beside you every step of the way.</p>
  </div>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-icon">
        <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
      </div>
      <h3>Vehicle Search &amp; Matching</h3>
      <p>Not sure what you need? We take the time to understand your lifestyle, budget, and priorities — then find vehicles that truly fit. If you already know what you want, we'll track it down.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">
        <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
      </div>
      <h3>Price Negotiation</h3>
      <p>We fight for your best deal. Our team negotiates directly with dealers so you never have to feel pressured or unsure if you paid too much.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">
        <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/></svg>
      </div>
      <h3>Contract Review</h3>
      <p>Confused by the paperwork? We review every line of the contract with you, flag hidden fees, and make sure you fully understand what you're signing before you commit.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">
        <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>
      </div>
      <h3>3rd Party Inspection</h3>
      <p>Before you buy, we coordinate an independent inspection of the vehicle so there are no surprises after you drive off the lot. Your peace of mind is our priority.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">
        <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="1" y="3" width="15" height="13" rx="2"/><path d="M16 8h4l3 3v5h-7V8z"/><circle cx="5.5" cy="18.5" r="2.5"/><circle cx="18.5" cy="18.5" r="2.5"/></svg>
      </div>
      <h3>Trade-In Assistance</h3>
      <p>Have a vehicle to trade in? We help you understand its true value and make sure you're getting a fair trade — not just whatever the dealer offers first.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">
        <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
      </div>
      <h3>Full Consultation &amp; Guidance</h3>
      <p>Never purchased a car before? Going through a difficult financial situation? We walk with you through the entire process — from first call to keys in hand.</p>
    </div>
  </div>
</section>

<!-- HOW IT WORKS -->
<section id="how-it-works">
  <div style="text-align:center; margin-bottom: 56px;">
    <p class="section-label" style="color: rgba(200,205,212,0.7);">The Process</p>
    <h2 class="section-title">How It Works</h2>
    <div class="section-divider" style="margin: 16px auto 16px;"></div>
    <p class="section-sub" style="margin: 0 auto;">Simple, transparent, and built around you.</p>
  </div>
  <div class="steps-wrapper">
    <div class="step">
      <div class="step-number">1</div>
      <h3>Free Consultation</h3>
      <p>We start with a conversation — understanding your needs, budget, and timeline. No commitment required.</p>
    </div>
    <div class="step">
      <div class="step-number">2</div>
      <h3>We Search &amp; Source</h3>
      <p>We find the best options available — whether you already know the car or need help narrowing it down.</p>
    </div>
    <div class="step">
      <div class="step-number">3</div>
      <h3>Inspect &amp; Verify</h3>
      <p>Every vehicle gets a 3rd party inspection. We review the Carfax, history, and condition on your behalf.</p>
    </div>
    <div class="step">
      <div class="step-number">4</div>
      <h3>Negotiate the Deal</h3>
      <p>We handle all price negotiations with the dealer — ensuring you get the best deal without the stress.</p>
    </div>
    <div class="step">
      <div class="step-number">5</div>
      <h3>Review &amp; Sign</h3>
      <p>We walk through the contract with you line by line. No hidden fees. No surprises. Just clarity.</p>
    </div>
    <div class="step">
      <div class="step-number">6</div>
      <h3>Drive Away</h3>
      <p>You get in your car and go — confident you made the right decision and got the best possible deal.</p>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about-section" style="padding: 90px 5%; background: var(--white);">
  <div id="about">
    <div class="about-visual">
      <div class="about-badge">
        <img src="logosealedbadge.png" alt="Waymaker Auto Services" />
        <div class="about-values">
          <span class="value-pill">Honesty</span>
          <span class="value-pill">Transparency</span>
          <span class="value-pill">Results</span>
        </div>
      </div>
    </div>
    <div class="about-text">
      <p class="section-label">Our Story</p>
      <h2 class="section-title">Built on Faith,<br>Driven by Purpose</h2>
      <div class="section-divider"></div>
      <p>Waymaker Auto Services LLC was founded with a clear mission: to be the trusted guide that makes the car-buying process accessible, fair, and stress-free for everyone.</p>
      <p>We know that buying a car can be one of the most overwhelming experiences — full of confusing contracts, pressure tactics, and hidden costs. We started this business to change that. We work for <em>you</em>, not the dealer.</p>
      <p>Our name and cross reflect our Christian foundation. We believe in doing business with integrity — treating every client the way we would want to be treated. That means honesty when it's inconvenient, transparency when it's costly, and results that genuinely serve your best interests.</p>
      <div class="about-scripture">
        <p>"For God so loved the world that he gave his one and only Son, that whoever believes in him shall not perish but have eternal life."</p>
        <cite>— John 3:16</cite>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact" style="background: var(--light-bg);">
  <div style="text-align:center; margin-bottom: 52px;">
    <p class="section-label">Get Started Today</p>
    <h2 class="section-title">How Would You Like To Connect?</h2>
    <div class="section-divider" style="margin: 16px auto;"></div>
    <p class="section-sub" style="margin: 0 auto;">Select the path that best fits your timeline and needs. We're ready when you are.</p>
  </div>

  <div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 28px; max-width: 1100px; margin: 0 auto 32px;">

    <!-- Option 1: Call or Text -->
    <div style="background: #fff; border-radius: 12px; padding: 40px 32px; display: flex; flex-direction: column; align-items: center; text-align: center; box-shadow: 0 4px 20px rgba(13,27,46,0.08); border-top: 4px solid var(--navy);">
      <div style="width: 64px; height: 64px; background: var(--light-bg); border-radius: 50%; display:flex; align-items:center; justify-content:center; margin-bottom: 20px;">
        <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#0d1b2e" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12a19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 3.62 1h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 8.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
      </div>
      <p style="font-family:'Barlow Condensed',sans-serif; font-size:0.8rem; font-weight:700; letter-spacing:0.15em; text-transform:uppercase; color:var(--text-muted); margin-bottom:8px;">Option 1</p>
      <h3 style="font-family:'Barlow Condensed',sans-serif; font-size:1.4rem; font-weight:800; text-transform:uppercase; color:var(--navy); margin-bottom:14px;">Call or Text Us Now</h3>
      <p style="font-size:0.95rem; color:var(--text-muted); line-height:1.7; flex-grow:1; margin-bottom:28px;">Have an urgent question or need immediate advice? Reach our team directly — we're here to help.</p>
      <div style="width:100%; display:flex; flex-direction:column; gap:10px;">
        <a href="tel:2035272834" style="display:block; background:var(--light-bg); color:var(--navy); padding:14px; border-radius:6px; font-family:'Barlow Condensed',sans-serif; font-size:1rem; font-weight:700; letter-spacing:0.08em; text-transform:uppercase; text-decoration:none; text-align:center; border: 2px solid #dde2ea;">
          📞 Call: 203-527-2834
        </a>
        <a href="sms:2035272834" style="display:block; background:var(--navy); color:#fff; padding:14px; border-radius:6px; font-family:'Barlow Condensed',sans-serif; font-size:1rem; font-weight:700; letter-spacing:0.08em; text-transform:uppercase; text-decoration:none; text-align:center; transition: background 0.2s;" onmouseover="this.style.background='#1a2e4a'" onmouseout="this.style.background='var(--navy)'">
          💬 Text: 203-527-2834
        </a>
        <a href="mailto:waymakerautoservices@gmail.com" style="display:block; background:var(--light-bg); color:var(--navy); padding:14px; border-radius:6px; font-family:'Barlow Condensed',sans-serif; font-size:0.9rem; font-weight:700; letter-spacing:0.05em; text-transform:uppercase; text-decoration:none; text-align:center; border: 2px solid #dde2ea;">
          ✉️ Email Us
        </a>
      </div>
    </div>

    <!-- Option 2: Book Free Consultation -->
    <div style="background: #fff; border-radius: 12px; padding: 40px 32px; display: flex; flex-direction: column; align-items: center; text-align: center; box-shadow: 0 8px 32px rgba(184,28,46,0.15); border-top: 4px solid var(--red); transform: scale(1.02);">
      <div style="background: var(--red); color:#fff; font-family:'Barlow Condensed',sans-serif; font-size:0.75rem; font-weight:700; letter-spacing:0.15em; text-transform:uppercase; padding:5px 14px; border-radius:20px; margin-bottom:16px;">Most Popular</div>
      <div style="width: 64px; height: 64px; background: #fff5f5; border-radius: 50%; display:flex; align-items:center; justify-content:center; margin-bottom: 20px;">
        <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#b81c2e" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>
      </div>
      <p style="font-family:'Barlow Condensed',sans-serif; font-size:0.8rem; font-weight:700; letter-spacing:0.15em; text-transform:uppercase; color:var(--red); margin-bottom:8px;">Option 2</p>
      <h3 style="font-family:'Barlow Condensed',sans-serif; font-size:1.4rem; font-weight:800; text-transform:uppercase; color:var(--navy); margin-bottom:14px;">Book a Free 15-Min Call</h3>
      <p style="font-size:0.95rem; color:var(--text-muted); line-height:1.7; flex-grow:1; margin-bottom:28px;">Schedule a no-obligation call. We'll discuss your specific situation, answer your questions, and walk you through exactly how we can help.</p>
      <a href="https://calendly.com/waymakerautoservices/30min" target="_blank" style="display:block; width:100%; background:var(--red); color:#fff; padding:16px; border-radius:6px; font-family:'Barlow Condensed',sans-serif; font-size:1.05rem; font-weight:700; letter-spacing:0.1em; text-transform:uppercase; text-decoration:none; text-align:center; box-shadow: 0 4px 16px rgba(184,28,46,0.3);">
        Book Free Strategy Call
      </a>
    </div>

    <!-- Option 3: Purchase Now -->
    <div style="background: #fff; border-radius: 12px; padding: 40px 32px; display: flex; flex-direction: column; align-items: center; text-align: center; box-shadow: 0 4px 20px rgba(13,27,46,0.08); border-top: 4px solid #2a7a2a;">
      <div style="width: 64px; height: 64px; background: #f0faf0; border-radius: 50%; display:flex; align-items:center; justify-content:center; margin-bottom: 20px;">
        <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#2a7a2a" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="1" y="4" width="22" height="16" rx="2" ry="2"/><line x1="1" y1="10" x2="23" y2="10"/></svg>
      </div>
      <p style="font-family:'Barlow Condensed',sans-serif; font-size:0.8rem; font-weight:700; letter-spacing:0.15em; text-transform:uppercase; color:#2a7a2a; margin-bottom:8px;">Option 3</p>
      <h3 style="font-family:'Barlow Condensed',sans-serif; font-size:1.4rem; font-weight:800; text-transform:uppercase; color:var(--navy); margin-bottom:14px;">Purchase &amp; Get Started</h3>
      <p style="font-size:0.95rem; color:var(--text-muted); line-height:1.7; flex-grow:1; margin-bottom:28px;">Ready to go? Pay the one-time $497 flat fee now and we'll get to work immediately.</p>
      <a href="#" id="stripePayBtn" style="display:block; width:100%; background:#2a7a2a; color:#fff; padding:16px; border-radius:6px; font-family:'Barlow Condensed',sans-serif; font-size:1.05rem; font-weight:700; letter-spacing:0.1em; text-transform:uppercase; text-decoration:none; text-align:center; box-shadow: 0 4px 16px rgba(42,122,42,0.25);">
        Purchase Service — $497
      </a>
    </div>

  </div>

  <!-- Bottom note + scripture -->
  <div style="max-width: 1100px; margin: 0 auto; display: grid; grid-template-columns: 1fr 1fr; gap: 20px; align-items: center;">
    <p style="font-size:0.88rem; color:var(--text-muted); font-style:italic; line-height:1.7;">
      <strong>Note on Option 3:</strong> After your purchase is confirmed, a detailed intake form will be immediately sent to your email to begin the advisory process.
    </p>
    <div style="padding: 16px 20px; background: var(--navy); border-radius: 8px; border-left: 3px solid var(--red);">
      <p style="color: var(--silver); font-size: 0.88rem; line-height: 1.65; font-style: italic; margin:0;">"And I will ask the Father, and he will give you another advocate to help you and be with you forever."<br><span style="color: var(--red); font-family: 'Barlow Condensed', sans-serif; font-style: normal; font-size: 0.8rem; letter-spacing: 0.1em; text-transform: uppercase;">— John 14:16</span></p>
    </div>
  </div>

</section>


<!-- PRICING -->
<section id="pricing" style="background: var(--navy); padding: 90px 5%;">
  <div style="text-align:center; margin-bottom: 56px;">
    <p class="section-label" style="color: rgba(200,205,212,0.7);">No Surprises. No Gimmicks.</p>
    <h2 class="section-title" style="color:#fff;">Transparent Pricing</h2>
    <div class="section-divider" style="margin: 16px auto;"></div>
    <p class="section-sub" style="color: var(--silver); margin: 0 auto;">We charge one flat fee. That's it. No commissions, no percentages, no hidden charges.</p>
  </div>
  <div style="max-width: 1100px; margin: 0 auto;">
    <div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 24px; margin-bottom: 32px;">

      <!-- Flat Fee -->
      <div style="background: #fff; border-radius: 10px; padding: 40px 32px; text-align: center; border-top: 5px solid var(--red);">
        <p style="font-family: 'Barlow Condensed', sans-serif; font-size: 0.8rem; font-weight: 700; letter-spacing: 0.2em; text-transform: uppercase; color: var(--red); margin-bottom: 12px;">One-Time Investment</p>
        <p style="font-family: 'Barlow Condensed', sans-serif; font-size: 5rem; font-weight: 900; color: var(--navy); line-height: 1; margin-bottom: 8px;">$497</p>
        <p style="font-family: 'Barlow Condensed', sans-serif; font-size: 1rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.08em; color: var(--text-muted); margin-bottom: 20px;">Flat Service Fee</p>
        <div style="border-top: 1px solid #e2e6ed; padding-top: 20px;">
          <p style="font-size: 0.9rem; color: var(--text-muted); line-height: 1.7;">Paid upfront. No surprises at the end. Covers the full car-buying process from search to signature.</p>
        </div>
      </div>

      <!-- What's included -->
      <div style="background: var(--red); border-radius: 10px; padding: 40px 32px; text-align: center; border-top: 5px solid #8f1522;">
        <p style="font-family: 'Barlow Condensed', sans-serif; font-size: 0.8rem; font-weight: 700; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(255,255,255,0.8); margin-bottom: 20px;">Everything Included</p>
        <div style="display: flex; flex-direction: column; gap: 13px; text-align: left;">
          <div style="display:flex; align-items:center; gap:10px; color:#fff; font-size:0.95rem;"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>Vehicle Search &amp; Matching</div>
          <div style="display:flex; align-items:center; gap:10px; color:#fff; font-size:0.95rem;"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>Expert Price Negotiation</div>
          <div style="display:flex; align-items:center; gap:10px; color:#fff; font-size:0.95rem;"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>3rd Party Inspection</div>
          <div style="display:flex; align-items:center; gap:10px; color:#fff; font-size:0.95rem;"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>Contract Review</div>
          <div style="display:flex; align-items:center; gap:10px; color:#fff; font-size:0.95rem;"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>Trade-In Assistance</div>
          <div style="display:flex; align-items:center; gap:10px; color:#fff; font-size:0.95rem;"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>No Commissions. Ever.</div>
        </div>
      </div>

      <!-- Avg savings -->
      <div style="background: #fff; border-radius: 10px; padding: 40px 32px; text-align: center; border-top: 5px solid var(--navy);">
        <p style="font-family: 'Barlow Condensed', sans-serif; font-size: 0.8rem; font-weight: 700; letter-spacing: 0.2em; text-transform: uppercase; color: var(--red); margin-bottom: 12px;">Average Client Savings</p>
        <p style="font-family: 'Barlow Condensed', sans-serif; font-size: 5rem; font-weight: 900; color: var(--navy); line-height: 1; margin-bottom: 8px;">4x</p>
        <p style="font-family: 'Barlow Condensed', sans-serif; font-size: 1rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.08em; color: var(--text-muted); margin-bottom: 20px;">Your Investment</p>
        <div style="border-top: 1px solid #e2e6ed; padding-top: 20px;">
          <p style="font-size: 0.9rem; color: var(--text-muted); line-height: 1.7;">We aim to save you <strong>$2,000+</strong> on your vehicle — that's at least 4x what you pay us.</p>
        </div>
      </div>
    </div>

    <!-- Referral banner -->
    <div style="background: rgba(255,255,255,0.06); border: 2px solid rgba(255,255,255,0.12); border-radius: 10px; padding: 36px 40px; display: flex; align-items: center; justify-content: space-between; gap: 32px; flex-wrap: wrap;">
      <div style="display:flex; align-items:center; gap: 20px;">
        <div style="width: 60px; height: 60px; background: var(--red); border-radius: 50%; display:flex; align-items:center; justify-content:center; flex-shrink:0;">
          <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
        </div>
        <div>
          <p style="font-family: 'Barlow Condensed', sans-serif; font-size: 1.3rem; font-weight: 800; text-transform: uppercase; letter-spacing: 0.05em; color: #fff; margin-bottom: 6px;">Refer a Friend, Earn $100</p>
          <p style="font-size: 0.95rem; color: var(--silver); line-height: 1.6; max-width: 520px;">Know someone buying a car? Send them our way. Every time a referral purchases with us, we send you <strong style="color:#fff;">$100 cash</strong> — no limit, no expiration.</p>
        </div>
      </div>
      <a href="#contact" class="btn-primary" style="white-space: nowrap;">Refer Someone Now</a>
    </div>
  </div>
</section>

<!-- FAQ -->
<section id="faq">
  <div class="faq-inner">
    <div class="faq-header">
      <p class="section-label">Common Questions</p>
      <h2 class="section-title">FAQ</h2>
      <div class="section-divider"></div>
    </div>

    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        How much does your service cost?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        <p>Our pricing is straightforward and transparent — just like everything else we do. We charge a flat service fee based on the scope of assistance you need. There are no surprise charges or commissions from dealers. We'll go over all costs during your free initial consultation.</p>
      </div>
    </div>

    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        Do I need to know what car I want before contacting you?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        <p>Not at all. Whether you have a specific vehicle in mind or have no idea where to start, we're here to help. If you need guidance, we'll ask the right questions and recommend vehicles that fit your actual needs — not just what's in stock somewhere.</p>
      </div>
    </div>

    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        Do you work with dealerships or private sellers?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        <p>We primarily work with dealerships, but we can assist with private party purchases as well. Wherever you find your vehicle, we can help you evaluate, inspect, and negotiate the deal.</p>
      </div>
    </div>

    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        What does the 3rd party inspection involve?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        <p>We coordinate with an independent, certified mechanic who has no relationship with the seller to inspect the vehicle. They check for mechanical issues, frame damage, safety concerns, and anything that might not show up on a Carfax report. You'll receive a full report before you commit to buying.</p>
      </div>
    </div>

    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        Can you help if I have bad credit or a complicated financial situation?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        <p>Absolutely. We work with clients in all kinds of financial situations. We'll help you understand your financing options honestly and clearly, and we'll work to find a deal that doesn't leave you underwater or locked into unfair terms.</p>
      </div>
    </div>

    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        How long does the process take?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">
        <p>It depends on your situation. If you already know the vehicle you want, we can often complete the process in just a few days. If you need help with the search, it typically takes 1–2 weeks to find the right match, get it inspected, and close the deal. We work at your pace.</p>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <img src="logosealedbadge.png" alt="Waymaker Auto Services" />
      <p>Making a way for people to purchase their vehicles with honesty, transparency, and results. We do the hard work so you don't have to.</p>
    </div>
    <div class="footer-col">
      <h4>Services</h4>
      <ul>
        <li><a href="#services">Vehicle Search</a></li>
        <li><a href="#services">Price Negotiation</a></li>
        <li><a href="#services">Contract Review</a></li>
        <li><a href="#services">3rd Party Inspection</a></li>
        <li><a href="#services">Trade-In Assistance</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Company</h4>
      <ul>
        <li><a href="#about-section">About Us</a></li>
        <li><a href="#how-it-works">How It Works</a></li>
        <li><a href="#faq">FAQ</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2025 Waymaker Auto Services LLC. All rights reserved.</p>
    <p class="footer-scripture">"I am the way, the truth, and the life." — John 14:6</p>
  </div>
</footer>

<script>
  function toggleMenu() {
    const links = document.getElementById('navLinks');
    links.classList.toggle('open');
  }

  // Close nav on link click (mobile)
  document.querySelectorAll('.nav-links a').forEach(link => {
    link.addEventListener('click', () => {
      document.getElementById('navLinks').classList.remove('open');
    });
  });

  function toggleFaq(btn) {
    const item = btn.parentElement;
    const answer = item.querySelector('.faq-answer');
    const isOpen = item.classList.contains('open');

    // Close all
    document.querySelectorAll('.faq-item').forEach(i => {
      i.classList.remove('open');
      i.querySelector('.faq-answer').style.maxHeight = '0';
    });

    if (!isOpen) {
      item.classList.add('open');
      answer.style.maxHeight = answer.scrollHeight + 'px';
    }
  }

  function submitForm() {
    const required = ['fname', 'lname', 'email', 'service'];
    let valid = true;
    required.forEach(id => {
      const el = document.getElementById(id);
      if (!el.value.trim()) {
        el.style.borderColor = 'var(--red)';
        valid = false;
      } else {
        el.style.borderColor = '#dde2ea';
      }
    });
    if (!valid) return;
    document.getElementById('formMain').style.display = 'none';
    document.getElementById('formSuccess').classList.add('show');
  }

  // Fade-in on scroll
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = '1';
        entry.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.service-card, .step').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(20px)';
    el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    observer.observe(el);
  });
</script>
</body>
</html>

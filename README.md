# UNIBRIDGE
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UniBridge — Your Gateway to France</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #0B1D3A;
    --blue: #1A4A8A;
    --gold: #D4A847;
    --cream: #FAF6EF;
    --white: #FFFFFF;
    --red: #C1392B;
    --light-blue: #E8F0F8;
    --text-muted: #6B7A8D;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--cream);
    color: var(--navy);
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; width: 100%; z-index: 100;
    background: rgba(11,29,58,0.96);
    backdrop-filter: blur(12px);
    display: flex; justify-content: space-between; align-items: center;
    padding: 1rem 6%;
    border-bottom: 1px solid rgba(212,168,71,0.3);
  }
  .logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem; font-weight: 900;
    color: var(--white); letter-spacing: -0.5px;
  }
  .logo span { color: var(--gold); }
  nav ul { list-style: none; display: flex; gap: 2rem; }
  nav ul a {
    text-decoration: none; color: rgba(255,255,255,0.75);
    font-size: 0.9rem; font-weight: 500; letter-spacing: 0.3px;
    transition: color 0.2s;
  }
  nav ul a:hover { color: var(--gold); }
  .nav-cta {
    background: var(--gold); color: var(--navy) !important;
    padding: 0.5rem 1.2rem; border-radius: 50px;
    font-weight: 600 !important;
  }
  .nav-cta:hover { background: #e8bb52 !important; color: var(--navy) !important; }

  /* HERO */
  .hero {
    min-height: 100vh;
    background: var(--navy);
    position: relative;
    display: flex; align-items: center;
    padding: 7rem 6% 4rem;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 70% 60% at 70% 50%, rgba(26,74,138,0.5) 0%, transparent 70%),
      radial-gradient(ellipse 40% 40% at 90% 10%, rgba(212,168,71,0.15) 0%, transparent 60%);
  }
  .hero::after {
    content: '';
    position: absolute; right: 0; top: 0; bottom: 0; width: 4px;
    background: linear-gradient(to bottom, #002395 33%, #FFFFFF 33%, #FFFFFF 66%, #ED2939 66%);
  }
  .hero-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 4rem; align-items: center; position: relative; z-index: 1;
    width: 100%; max-width: 1200px; margin: 0 auto;
  }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: rgba(212,168,71,0.15); border: 1px solid rgba(212,168,71,0.4);
    color: var(--gold); padding: 0.4rem 1rem; border-radius: 50px;
    font-size: 0.8rem; font-weight: 600; letter-spacing: 1px; text-transform: uppercase;
    margin-bottom: 1.5rem;
    animation: fadeUp 0.8s ease both;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.8rem, 5vw, 4.5rem);
    font-weight: 900; line-height: 1.1;
    color: var(--white); margin-bottom: 1.5rem;
    animation: fadeUp 0.8s 0.15s ease both;
  }
  .hero h1 em { color: var(--gold); font-style: italic; }
  .hero p {
    font-size: 1.1rem; line-height: 1.75;
    color: rgba(255,255,255,0.7);
    max-width: 480px; margin-bottom: 2.5rem;
    animation: fadeUp 0.8s 0.3s ease both;
  }
  .hero-btns {
    display: flex; gap: 1rem; flex-wrap: wrap;
    animation: fadeUp 0.8s 0.45s ease both;
  }
  .btn-primary {
    background: var(--gold); color: var(--navy);
    padding: 0.85rem 2rem; border-radius: 50px;
    font-weight: 700; font-size: 1rem; text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 4px 20px rgba(212,168,71,0.4);
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(212,168,71,0.5); }
  .btn-secondary {
    border: 1px solid rgba(255,255,255,0.3); color: white;
    padding: 0.85rem 2rem; border-radius: 50px;
    font-weight: 500; font-size: 1rem; text-decoration: none;
    transition: background 0.2s;
  }
  .btn-secondary:hover { background: rgba(255,255,255,0.1); }
  .hero-stats {
    display: grid; grid-template-columns: repeat(3,1fr); gap: 1.5rem;
    animation: fadeUp 0.8s 0.6s ease both;
  }
  .stat-card {
    background: rgba(255,255,255,0.07);
    border: 1px solid rgba(255,255,255,0.1);
    padding: 1.5rem; border-radius: 16px; text-align: center;
    backdrop-filter: blur(8px); transition: transform 0.2s;
  }
  .stat-card:hover { transform: translateY(-4px); }
  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 2.2rem; font-weight: 900; color: var(--gold);
  }
  .stat-label { font-size: 0.8rem; color: rgba(255,255,255,0.55); margin-top: 0.3rem; }

  /* SECTION SHARED */
  section { padding: 6rem 6%; }
  .section-label {
    font-size: 0.75rem; font-weight: 700; letter-spacing: 2.5px;
    text-transform: uppercase; color: var(--gold); margin-bottom: 0.75rem;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3.5vw, 3rem);
    font-weight: 800; line-height: 1.2;
    color: var(--navy); margin-bottom: 1.2rem;
  }
  .section-sub {
    font-size: 1.05rem; color: var(--text-muted);
    line-height: 1.7; max-width: 560px;
  }

  /* ABOUT */
  #about { background: var(--white); }
  .about-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 5rem; align-items: center; max-width: 1200px; margin: 0 auto;
  }
  .about-visual { position: relative; height: 420px; }
  .about-card {
    position: absolute; border-radius: 20px; overflow: hidden;
    box-shadow: 0 20px 60px rgba(11,29,58,0.15);
  }
  .card-main {
    width: 280px; height: 340px; top: 0; left: 40px;
    background: linear-gradient(135deg, var(--navy) 0%, var(--blue) 100%);
    display: flex; flex-direction: column; justify-content: flex-end; padding: 2rem;
  }
  .card-main-emoji { font-size: 4rem; margin-bottom: 1rem; }
  .card-main h3 { font-family: 'Playfair Display', serif; color: white; font-size: 1.3rem; }
  .card-main p { color: rgba(255,255,255,0.65); font-size: 0.85rem; margin-top: 0.3rem; }
  .card-accent {
    width: 180px; height: 140px; bottom: 20px; left: 0;
    background: var(--gold);
    display: flex; flex-direction: column; justify-content: center; padding: 1.5rem;
  }
  .card-accent .big { font-family: 'Playfair Display', serif; font-size: 2rem; font-weight: 900; color: var(--navy); }
  .card-accent p { font-size: 0.75rem; color: var(--navy); font-weight: 600; }
  .card-mini {
    width: 160px; height: 120px; top: 20px; right: 0;
    background: var(--light-blue);
    display: flex; flex-direction: column;
    justify-content: center; align-items: center; text-align: center; padding: 1rem;
  }
  .card-mini .emoji { font-size: 2rem; }
  .card-mini p { font-size: 0.8rem; color: var(--navy); font-weight: 600; margin-top: 0.4rem; }
  .about-values { display: flex; flex-direction: column; gap: 1.5rem; margin-top: 2.5rem; }
  .value-item { display: flex; gap: 1rem; align-items: flex-start; }
  .value-icon {
    width: 44px; height: 44px; border-radius: 12px;
    background: var(--light-blue);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.2rem; flex-shrink: 0;
  }
  .value-item h4 { font-weight: 700; margin-bottom: 0.2rem; }
  .value-item p { font-size: 0.9rem; color: var(--text-muted); }

  /* SERVICES */
  #services { background: var(--cream); }
  .services-header { text-align: center; margin-bottom: 4rem; max-width: 600px; margin-left: auto; margin-right: auto; }
  .services-header .section-sub { margin: 0 auto; }
  .services-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem; max-width: 1200px; margin: 0 auto;
  }
  .service-card {
    background: var(--white); border-radius: 20px; padding: 2rem;
    border: 1px solid rgba(11,29,58,0.06);
    box-shadow: 0 4px 20px rgba(11,29,58,0.05);
    transition: transform 0.3s, box-shadow 0.3s;
    position: relative; overflow: hidden;
  }
  .service-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: linear-gradient(to right, var(--gold), var(--blue));
    transform: scaleX(0); transform-origin: left; transition: transform 0.3s;
  }
  .service-card:hover { transform: translateY(-6px); box-shadow: 0 16px 40px rgba(11,29,58,0.12); }
  .service-card:hover::before { transform: scaleX(1); }
  .service-icon {
    font-size: 2.5rem; margin-bottom: 1.2rem;
    width: 60px; height: 60px; display: flex; align-items: center; justify-content: center;
    background: var(--light-blue); border-radius: 16px;
  }
  .service-card h3 { font-size: 1.1rem; font-weight: 700; margin-bottom: 0.75rem; }
  .service-card p { font-size: 0.9rem; color: var(--text-muted); line-height: 1.65; }
  .service-tag {
    display: inline-block; margin-top: 1.2rem;
    background: var(--light-blue); color: var(--blue);
    padding: 0.3rem 0.8rem; border-radius: 50px;
    font-size: 0.75rem; font-weight: 600;
  }

  /* PRICING */
  #pricing { background: var(--navy); padding: 6rem 6%; }
  #pricing .section-title { color: var(--white); text-align: center; }
  #pricing .section-label { text-align: center; }
  #pricing .section-sub { color: rgba(255,255,255,0.6); text-align: center; margin: 0 auto 3.5rem; }
  .pricing-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem; max-width: 1100px; margin: 0 auto; align-items: stretch;
  }
  .price-card {
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.12);
    border-radius: 24px; padding: 2.5rem 2rem;
    position: relative; transition: transform 0.3s;
  }
  .price-card:hover { transform: translateY(-6px); }
  .price-card.featured {
    background: var(--gold); border-color: var(--gold); transform: scale(1.04);
  }
  .price-card.featured:hover { transform: scale(1.04) translateY(-6px); }
  .price-card.featured h3,
  .price-card.featured .price-amount,
  .price-card.featured li { color: var(--navy); }
  .price-card.featured .price-period { color: rgba(11,29,58,0.65); }
  .price-card.featured .feature-check { color: var(--navy); }
  .price-badge {
    position: absolute; top: -14px; left: 50%; transform: translateX(-50%);
    background: var(--red); color: white;
    padding: 0.3rem 1rem; border-radius: 50px;
    font-size: 0.75rem; font-weight: 700; letter-spacing: 1px;
  }
  .price-card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem; color: white; margin-bottom: 0.5rem;
  }
  .price-card .price-desc { font-size: 0.85rem; color: rgba(255,255,255,0.5); margin-bottom: 1.5rem; }
  .price-amount { font-family: 'Playfair Display', serif; font-size: 3rem; font-weight: 900; color: white; }
  .price-period { font-size: 0.9rem; color: rgba(255,255,255,0.5); }
  .price-divider { height: 1px; background: rgba(255,255,255,0.1); margin: 1.5rem 0; }
  .price-card.featured .price-divider { background: rgba(11,29,58,0.15); }
  .price-card ul { list-style: none; display: flex; flex-direction: column; gap: 0.75rem; }
  .price-card li { display: flex; align-items: flex-start; gap: 0.6rem; font-size: 0.9rem; color: rgba(255,255,255,0.8); }
  .feature-check { color: var(--gold); font-weight: 700; flex-shrink: 0; }
  .btn-plan {
    display: block; width: 100%; margin-top: 2rem;
    padding: 0.85rem; border-radius: 50px;
    font-weight: 700; font-size: 0.95rem; text-align: center;
    cursor: pointer; text-decoration: none; transition: opacity 0.2s; border: none;
  }
  .btn-plan-outline { background: transparent; border: 1.5px solid rgba(255,255,255,0.3); color: white; }
  .btn-plan-outline:hover { background: rgba(255,255,255,0.1); }
  .btn-plan-dark { background: var(--navy); color: var(--gold); }
  .btn-plan-dark:hover { opacity: 0.9; }

  /* HOW IT WORKS */
  .steps {
    display: grid; grid-template-columns: repeat(4, 1fr);
    gap: 2rem; max-width: 1100px; margin: 3rem auto 0; position: relative;
  }
  .steps::before {
    content: ''; position: absolute; top: 32px; left: 10%; right: 10%; height: 2px;
    background: linear-gradient(to right, var(--gold), var(--blue)); z-index: 0;
  }
  .step { text-align: center; position: relative; z-index: 1; }
  .step-num {
    width: 64px; height: 64px; border-radius: 50%;
    background: var(--navy); color: var(--gold);
    font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 900;
    display: flex; align-items: center; justify-content: center;
    margin: 0 auto 1.2rem; border: 3px solid var(--cream);
    box-shadow: 0 4px 20px rgba(11,29,58,0.2);
  }
  .step h4 { font-weight: 700; margin-bottom: 0.5rem; }
  .step p { font-size: 0.88rem; color: var(--text-muted); line-height: 1.6; }

  /* SUSTAINABILITY */
  #sustainability { background: var(--cream); }
  .sus-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 4rem; align-items: center; max-width: 1200px; margin: 3rem auto 0;
  }
  .sus-cards { display: flex; flex-direction: column; gap: 1.2rem; }
  .sus-card {
    display: flex; gap: 1.2rem; align-items: flex-start;
    background: var(--white); padding: 1.5rem; border-radius: 16px;
    border: 1px solid rgba(11,29,58,0.06);
    box-shadow: 0 2px 12px rgba(11,29,58,0.05); transition: transform 0.2s;
  }
  .sus-card:hover { transform: translateX(6px); }
  .sus-icon {
    width: 50px; height: 50px; border-radius: 14px; flex-shrink: 0;
    display: flex; align-items: center; justify-content: center; font-size: 1.4rem;
  }
  .sus-green { background: #E8F5E9; }
  .sus-blue  { background: #E3F2FD; }
  .sus-orange{ background: #FFF3E0; }
  .sus-purple{ background: #F3E5F5; }
  .sus-card h4 { font-weight: 700; margin-bottom: 0.3rem; }
  .sus-card p { font-size: 0.88rem; color: var(--text-muted); line-height: 1.6; }
  .sus-impact { background: var(--navy); border-radius: 24px; padding: 3rem; color: white; }
  .sus-impact h3 { font-family: 'Playfair Display', serif; font-size: 1.8rem; color: var(--gold); margin-bottom: 1rem; }
  .sus-impact p { color: rgba(255,255,255,0.7); line-height: 1.75; margin-bottom: 2rem; }
  .impact-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .impact-stat { background: rgba(255,255,255,0.07); border-radius: 14px; padding: 1.2rem; text-align: center; }
  .impact-stat .num { font-family: 'Playfair Display', serif; font-size: 1.8rem; font-weight: 900; color: var(--gold); }
  .impact-stat .lbl { font-size: 0.78rem; color: rgba(255,255,255,0.55); margin-top: 0.2rem; }

  /* TESTIMONIALS */
  .testimonials-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem; max-width: 1100px; margin: 3rem auto 0;
  }
  .testimonial { background: var(--light-blue); border-radius: 20px; padding: 2rem; position: relative; }
  .testimonial::before {
    content: '"'; font-family: 'Playfair Display', serif;
    font-size: 5rem; color: var(--blue); opacity: 0.15;
    position: absolute; top: 0.5rem; left: 1.5rem; line-height: 1;
  }
  .testimonial p { font-size: 0.95rem; line-height: 1.7; color: var(--navy); margin-bottom: 1.5rem; }
  .testimonial-author { display: flex; align-items: center; gap: 0.8rem; }
  .author-avatar {
    width: 42px; height: 42px; border-radius: 50%;
    background: var(--blue); color: white;
    display: flex; align-items: center; justify-content: center;
    font-weight: 700; font-size: 0.9rem;
  }
  .author-name { font-weight: 700; font-size: 0.9rem; }
  .author-origin { font-size: 0.8rem; color: var(--text-muted); }

  /* CTA */
  #cta {
    background: linear-gradient(135deg, var(--navy) 0%, var(--blue) 100%);
    text-align: center; padding: 7rem 6%; position: relative; overflow: hidden;
  }
  #cta::before {
    content: ''; position: absolute; inset: 0;
    background: radial-gradient(ellipse 60% 50% at 50% 50%, rgba(212,168,71,0.1) 0%, transparent 70%);
  }
  #cta h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4vw, 3.5rem);
    color: white; margin-bottom: 1rem; position: relative;
  }
  #cta h2 em { color: var(--gold); font-style: italic; }
  #cta p { color: rgba(255,255,255,0.7); font-size: 1.1rem; margin-bottom: 2.5rem; position: relative; }
  #cta .btn-primary { font-size: 1.05rem; padding: 1rem 2.5rem; position: relative; }

  /* FOOTER */
  footer { background: #060e1c; color: rgba(255,255,255,0.6); padding: 4rem 6% 2rem; }
  .footer-grid {
    display: grid; grid-template-columns: 2fr 1fr 1fr 1fr;
    gap: 3rem; margin-bottom: 3rem;
  }
  footer .logo { display: block; margin-bottom: 1rem; }
  .footer-desc { font-size: 0.9rem; line-height: 1.7; max-width: 280px; }
  .footer-col h4 { color: white; font-weight: 700; margin-bottom: 1.2rem; font-size: 0.95rem; }
  .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 0.6rem; }
  .footer-col ul li { font-size: 0.88rem; cursor: pointer; }
  .footer-col ul li:hover { color: var(--gold); }
  .footer-flags { font-size: 1.2rem; letter-spacing: 0.3rem; margin-bottom: 0.5rem; }
  .footer-bottom {
    border-top: 1px solid rgba(255,255,255,0.08); padding-top: 1.5rem;
    display: flex; justify-content: space-between; align-items: center; font-size: 0.83rem;
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  .fade-up { opacity: 0; transform: translateY(28px); transition: opacity 0.7s ease, transform 0.7s ease; }
  .fade-up.visible { opacity: 1; transform: translateY(0); }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    .hero-grid, .about-grid, .sus-grid { grid-template-columns: 1fr; }
    .services-grid, .pricing-grid, .testimonials-grid { grid-template-columns: 1fr; }
    .steps { grid-template-columns: 1fr 1fr; }
    .steps::before { display: none; }
    .footer-grid { grid-template-columns: 1fr 1fr; }
    .hero-stats { grid-template-columns: repeat(3, 1fr); }
    .price-card.featured { transform: none; }
    .about-visual { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">Uni<span>Bridge</span></div>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#sustainability">Impact</a></li>
    <li><a href="#cta" class="nav-cta">Get Started</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid">
    <div>
      <div class="hero-badge">🎓 For International Students in France</div>
      <h1>Your <em>Bridge</em> to Life in France</h1>
      <p>UniBridge helps international students navigate university life in France — from housing and admin to social integration — so you can focus on what matters: thriving.</p>
      <div class="hero-btns">
        <a href="#pricing" class="btn-primary">See Our Plans</a>
        <a href="#services" class="btn-secondary">Explore Services</a>
      </div>
    </div>
    <div class="hero-stats">
      <div class="stat-card"><div class="stat-num">400K+</div><div class="stat-label">Foreign students in France yearly</div></div>
      <div class="stat-card"><div class="stat-num">72%</div><div class="stat-label">Face major admin challenges</div></div>
      <div class="stat-card"><div class="stat-num">3×</div><div class="stat-label">Faster settling with our support</div></div>
      <div class="stat-card"><div class="stat-num">50+</div><div class="stat-label">Partner universities</div></div>
      <div class="stat-card"><div class="stat-num">12</div><div class="stat-label">Cities covered in France</div></div>
      <div class="stat-card"><div class="stat-num">4.9★</div><div class="stat-label">Average satisfaction score</div></div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-grid">
    <div>
      <div class="section-label">Who We Are</div>
      <h2 class="section-title">Making France Feel Like Home</h2>
      <p class="section-sub">Moving to a new country is exciting — but also overwhelming. UniBridge was built by students who experienced the chaos firsthand: confusing paperwork, housing scams, language barriers, loneliness.</p>
      <div class="about-values">
        <div class="value-item">
          <div class="value-icon">🎯</div>
          <div>
            <h4>Our Mission</h4>
            <p>Remove every barrier that stops talented international students from fully enjoying their French university experience.</p>
          </div>
        </div>
        <div class="value-item">
          <div class="value-icon">🤝</div>
          <div>
            <h4>Human-First Approach</h4>
            <p>Real advisors, peer mentors, and local experts — not just chatbots. We believe in human connection.</p>
          </div>
        </div>
        <div class="value-item">
          <div class="value-icon">🌍</div>
          <div>
            <h4>Inclusive by Design</h4>
            <p>Services available in 8 languages. No student left behind regardless of their background or budget.</p>
          </div>
        </div>
      </div>
    </div>
    <div class="about-visual">
      <div class="about-card card-main">
        <div class="card-main-emoji">🗼</div>
        <h3>From Lost to Settled</h3>
        <p>In as little as 7 days</p>
      </div>
      <div class="about-card card-accent">
        <div class="big">98%</div>
        <p>Student satisfaction rate</p>
      </div>
      <div class="about-card card-mini">
        <div class="emoji">🌐</div>
        <p>8 languages supported</p>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="services-header fade-up">
    <div class="section-label">What We Offer</div>
    <h2 class="section-title">Everything You Need to Settle in France</h2>
    <p class="section-sub">From the moment you land to the day you graduate, UniBridge has a service for every step of your journey.</p>
  </div>
  <div class="services-grid">
    <div class="service-card fade-up">
      <div class="service-icon">🏠</div>
      <h3>Housing &amp; Accommodation</h3>
      <p>Curated listings of verified, student-friendly apartments and residences. We review contracts, negotiate rent, and alert you to scams before you sign anything.</p>
      <span class="service-tag">Most Popular</span>
    </div>
    <div class="service-card fade-up">
      <div class="service-icon">📋</div>
      <h3>Administrative Guidance</h3>
      <p>CAF applications, carte de séjour, bank accounts, health insurance (CPAM), and university enrollment — we walk you through every step in your language.</p>
      <span class="service-tag">Included in all plans</span>
    </div>
    <div class="service-card fade-up">
      <div class="service-icon">🗣️</div>
      <h3>Language &amp; Culture</h3>
      <p>Weekly French conversation groups, cultural workshops, and a buddy system pairing you with a French student to help you adapt naturally.</p>
      <span class="service-tag">Community</span>
    </div>
    <div class="service-card fade-up">
      <div class="service-icon">💼</div>
      <h3>Career &amp; Internships</h3>
      <p>CV adaptation for French standards, mock interviews in French, employer connections, and guidance on work permits for students.</p>
      <span class="service-tag">Premium</span>
    </div>
    <div class="service-card fade-up">
      <div class="service-icon">🏥</div>
      <h3>Health &amp; Wellbeing</h3>
      <p>Navigating the French healthcare system, mental health support referrals, and a 24/7 emergency helpline in your native language.</p>
      <span class="service-tag">24/7 Support</span>
    </div>
    <div class="service-card fade-up">
      <div class="service-icon">🎉</div>
      <h3>Social Integration</h3>
      <p>Monthly mixers, city tours, cultural events, and a vibrant community app to meet fellow internationals and local students across France.</p>
      <span class="service-tag">Community</span>
    </div>
  </div>
</section>

<!-- HOW IT WORKS -->
<section id="how" style="background:var(--white); padding:6rem 6%;">
  <div style="text-align:center; max-width:600px; margin:0 auto;">
    <div class="section-label">Process</div>
    <h2 class="section-title">How UniBridge Works</h2>
  </div>
  <div class="steps fade-up">
    <div class="step">
      <div class="step-num">1</div>
      <h4>Sign Up Online</h4>
      <p>Create your profile, share your university, arrival date and key needs in 5 minutes.</p>
    </div>
    <div class="step">
      <div class="step-num">2</div>
      <h4>Meet Your Advisor</h4>
      <p>Get matched with a bilingual advisor who knows your city and your university system.</p>
    </div>
    <div class="step">
      <div class="step-num">3</div>
      <h4>Get Your Action Plan</h4>
      <p>Receive a personalised checklist: housing, admin tasks, healthcare, and social events.</p>
    </div>
    <div class="step">
      <div class="step-num">4</div>
      <h4>Thrive in France</h4>
      <p>Ongoing support throughout your stay so you never feel alone or lost again.</p>
    </div>
  </div>
</section>

<!-- PRICING -->
<section id="pricing">
  <div class="section-label" style="text-align:center">Transparent Pricing</div>
  <h2 class="section-title" style="text-align:center">Choose Your Package</h2>
  <p class="section-sub" style="text-align:center; margin:0 auto 3.5rem">One-time payment. No subscriptions, no hidden fees. Yours for your entire stay in France.</p>
  <div class="pricing-grid fade-up">
    <div class="price-card">
      <h3>Starter</h3>
      <p class="price-desc">Essential support to get you started</p>
      <div><span class="price-amount">€29</span><span class="price-period"> one-time</span></div>
      <div class="price-divider"></div>
      <ul>
        <li><span class="feature-check">✓</span> Welcome guide &amp; city orientation</li>
        <li><span class="feature-check">✓</span> Administrative checklists</li>
        <li><span class="feature-check">✓</span> Housing listings access</li>
        <li><span class="feature-check">✓</span> Community forum access</li>
        <li><span class="feature-check">✓</span> Email support (48h response)</li>
      </ul>
      <a href="#cta" class="btn-plan btn-plan-outline">Get This Package</a>
    </div>
    <div class="price-card featured">
      <div class="price-badge">MOST POPULAR</div>
      <h3>Essential</h3>
      <p class="price-desc" style="color:rgba(11,29,58,0.6)">Full settling support — our bestseller</p>
      <div><span class="price-amount">€50</span><span class="price-period" style="color:rgba(11,29,58,0.6)"> one-time</span></div>
      <div class="price-divider"></div>
      <ul>
        <li><span class="feature-check">✓</span> Everything in Starter</li>
        <li><span class="feature-check">✓</span> 1-on-1 bilingual advisor sessions</li>
        <li><span class="feature-check">✓</span> CAF &amp; admin form assistance</li>
        <li><span class="feature-check">✓</span> Housing contract review</li>
        <li><span class="feature-check">✓</span> French conversation groups</li>
        <li><span class="feature-check">✓</span> Priority chat support (4h response)</li>
        <li><span class="feature-check">✓</span> Monthly social events</li>
      </ul>
      <a href="#cta" class="btn-plan btn-plan-dark">Get This Package</a>
    </div>
    <div class="price-card">
      <h3>Premium</h3>
      <p class="price-desc">For ambitious students who want it all</p>
      <div><span class="price-amount">€150</span><span class="price-period"> one-time</span></div>
      <div class="price-divider"></div>
      <ul>
        <li><span class="feature-check">✓</span> Everything in Essential</li>
        <li><span class="feature-check">✓</span> Unlimited advisor access</li>
        <li><span class="feature-check">✓</span> Career &amp; internship coaching</li>
        <li><span class="feature-check">✓</span> CV &amp; LinkedIn review</li>
        <li><span class="feature-check">✓</span> Health system concierge</li>
        <li><span class="feature-check">✓</span> 24/7 emergency helpline</li>
        <li><span class="feature-check">✓</span> Airport pickup coordination</li>
      </ul>
      <a href="#cta" class="btn-plan btn-plan-outline">Get This Package</a>
    </div>
  </div>
  <p style="text-align:center; color:rgba(255,255,255,0.45); margin-top:2rem; font-size:0.88rem;">
    🎓 University partnerships available — contact us for institutional pricing &nbsp;|&nbsp; 💳 Pay once, supported for life
  </p>
</section>

<!-- SUSTAINABILITY -->
<section id="sustainability">
  <div class="section-label">Our Commitment</div>
  <h2 class="section-title">Building a Sustainable Future</h2>
  <p class="section-sub">UniBridge believes that integration and sustainability go hand in hand. Our business model is designed to create long-term positive impact — for people and the planet.</p>
  <div class="sus-grid fade-up">
    <div class="sus-cards">
      <div class="sus-card">
        <div class="sus-icon sus-green">🌱</div>
        <div>
          <h4>Carbon-Neutral Operations</h4>
          <p>All our offices and servers run on renewable energy. We offset 100% of travel emissions through verified reforestation programmes.</p>
        </div>
      </div>
      <div class="sus-card">
        <div class="sus-icon sus-blue">🤝</div>
        <div>
          <h4>Social Inclusion Fund</h4>
          <p>5% of every subscription funds grants for students from low-income countries, ensuring UniBridge is accessible regardless of financial background.</p>
        </div>
      </div>
      <div class="sus-card">
        <div class="sus-icon sus-orange">🏘️</div>
        <div>
          <h4>Local Community Partnerships</h4>
          <p>We partner with local associations, food banks, and cultural centres to strengthen the bridge between international students and French communities.</p>
        </div>
      </div>
      <div class="sus-card">
        <div class="sus-icon sus-purple">📚</div>
        <div>
          <h4>Knowledge Sharing</h4>
          <p>Our free resource library, published in open-access format, helps universities across Europe improve their international student support systems.</p>
        </div>
      </div>
    </div>
    <div class="sus-impact">
      <h3>Our 2025 Impact Goals</h3>
      <p>We measure our success not just in revenue, but in the lives we transform and the communities we strengthen.</p>
      <div class="impact-stats">
        <div class="impact-stat"><div class="num">10,000</div><div class="lbl">Students supported annually</div></div>
        <div class="impact-stat"><div class="num">500</div><div class="lbl">Scholarships granted via our fund</div></div>
        <div class="impact-stat"><div class="num">0</div><div class="lbl">Net carbon footprint</div></div>
        <div class="impact-stat"><div class="num">25</div><div class="lbl">Local NGO partnerships</div></div>
      </div>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section id="testimonials" style="background:var(--white); padding:6rem 6%">
  <div style="text-align:center; max-width:600px; margin:0 auto 0.5rem">
    <div class="section-label">Stories</div>
    <h2 class="section-title">What Our Students Say</h2>
  </div>
  <div class="testimonials-grid fade-up">
    <div class="testimonial">
      <p>UniBridge saved me weeks of stress. My advisor helped me open a bank account, register at the CAF, and find an apartment — all in my first two weeks in Paris.</p>
      <div class="testimonial-author">
        <div class="author-avatar">AM</div>
        <div><div class="author-name">Amara M.</div><div class="author-origin">🇸🇳 Senegal → Sciences Po Paris</div></div>
      </div>
    </div>
    <div class="testimonial">
      <p>I was terrified of the French admin system. UniBridge made it feel manageable. The WhatsApp group with other students also helped me make my first French friends.</p>
      <div class="testimonial-author">
        <div class="author-avatar">JL</div>
        <div><div class="author-name">Ji-ho L.</div><div class="author-origin">🇰🇷 South Korea → ESSEC Paris</div></div>
      </div>
    </div>
    <div class="testimonial">
      <p>The housing contract review alone is worth the subscription. My advisor caught a clause that would have cost me my deposit — absolutely essential service.</p>
      <div class="testimonial-author">
        <div class="author-avatar">RS</div>
        <div><div class="author-name">Rania S.</div><div class="author-origin">🇲🇦 Morocco → Université de Lyon</div></div>
      </div>
    </div>
  </div>
</section>

<!-- CTA -->
<section id="cta">
  <h2>Ready to Start Your <em>French Adventure</em>?</h2>
  <p>Join thousands of international students who chose UniBridge. Your first 7 days are completely free.</p>
  <a href="#pricing" class="btn-primary">Get Your Free Trial →</a>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-grid">
    <div>
      <div class="logo">Uni<span style="color:var(--gold)">Bridge</span></div>
      <p class="footer-desc">Helping international students settle, thrive, and belong in France. Founded by students, for students.</p>
      <div style="margin-top:1.5rem">
        <div class="footer-flags">🇫🇷 🇪🇺 🌍</div>
        <p style="font-size:0.82rem">Operating across 12 French cities</p>
      </div>
    </div>
    <div class="footer-col">
      <h4>Services</h4>
      <ul>
        <li>Housing Support</li>
        <li>Admin Guidance</li>
        <li>Language &amp; Culture</li>
        <li>Career Support</li>
        <li>Health &amp; Wellbeing</li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Company</h4>
      <ul>
        <li>About Us</li>
        <li>Our Team</li>
        <li>Sustainability</li>
        <li>University Partners</li>
        <li>Press</li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Support</h4>
      <ul>
        <li>Help Centre</li>
        <li>Contact Us</li>
        <li>Community Forum</li>
        <li>Privacy Policy</li>
        <li>Terms of Service</li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2025 UniBridge SAS. All rights reserved.</span>
    <span>Made with ❤️ in Paris, France</span>
  </div>
</footer>

<script>
  // Scroll-triggered fade-up animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });
  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  // Active nav highlight on scroll
  const sections = document.querySelectorAll('section[id]');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(s => { if (window.scrollY >= s.offsetTop - 100) current = s.id; });
    document.querySelectorAll('nav ul a').forEach(a => {
      a.style.color = a.getAttribute('href') === '#' + current ? 'var(--gold)' : '';
    });
  });
</script>
</body>
</html>

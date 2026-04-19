<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bennett Goldmacher — Marketing Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --white: #f8f7f4;
    --gray: #8a8a8a;
    --light: #efefec;
    --accent: #c8a96e;
    --serif: 'Instrument Serif', Georgia, serif;
    --sans: 'DM Sans', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--white);
    color: var(--black);
    font-family: var(--sans);
    font-size: 16px;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem 3rem;
    background: rgba(248,247,244,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(0,0,0,0.06);
  }

  .nav-logo {
    font-family: var(--serif);
    font-size: 1.1rem;
    letter-spacing: 0.01em;
    color: var(--black);
    text-decoration: none;
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
    align-items: center;
  }

  .nav-links a {
    font-size: 0.8rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gray);
    text-decoration: none;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--black); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 8rem 3rem 6rem;
    position: relative;
    overflow: hidden;
  }

  .hero-bg-text {
    position: absolute;
    top: 50%;
    right: 18%;
    transform: translateY(-50%);
    font-family: var(--serif);
    font-size: clamp(10rem, 16vw, 16rem);
    color: rgba(200, 169, 110, 0.18);
    line-height: 1;
    pointer-events: none;
    user-select: none;
    white-space: nowrap;
  }

  .hero-content {
    max-width: 900px;
    opacity: 0;
    transform: translateY(30px);
    animation: fadeUp 0.9s ease forwards 0.2s;
  }

  .hero-tag {
    display: inline-block;
    font-size: 0.75rem;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 2rem;
    font-weight: 500;
  }

  .hero-title {
    font-family: var(--serif);
    font-size: clamp(3.5rem, 7vw, 6.5rem);
    line-height: 1.05;
    font-weight: 400;
    margin-bottom: 2rem;
    letter-spacing: -0.01em;
  }

  .hero-title em {
    font-style: italic;
    color: var(--accent);
  }

  .hero-desc {
    font-size: 1.1rem;
    color: var(--gray);
    max-width: 520px;
    line-height: 1.75;
    font-weight: 300;
    margin-bottom: 3rem;
  }

  .hero-cta {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    font-size: 0.85rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--black);
    text-decoration: none;
    border-bottom: 1.5px solid var(--black);
    padding-bottom: 0.25rem;
    transition: gap 0.2s;
  }

  .hero-cta:hover { gap: 1.25rem; }

  .hero-scroll {
    position: absolute;
    bottom: 3rem;
    left: 3rem;
    font-size: 0.72rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gray);
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .hero-scroll::before {
    content: '';
    display: block;
    width: 40px;
    height: 1px;
    background: var(--gray);
  }

  /* ABOUT */
  .about {
    padding: 8rem 3rem;
    display: grid;
    grid-template-columns: 1fr;
    gap: 0;
    align-items: start;
    max-width: 700px;
    margin: 0 auto;
    border-top: 1px solid rgba(0,0,0,0.08);
  }

  .section-label {
    font-size: 0.72rem;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--accent);
    font-weight: 500;
    margin-bottom: 2rem;
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .section-label::before {
    content: '';
    display: block;
    width: 24px;
    height: 1px;
    background: var(--accent);
  }

  .about-heading {
    font-family: var(--serif);
    font-size: clamp(2rem, 3.5vw, 3rem);
    line-height: 1.2;
    font-weight: 400;
    margin-bottom: 1.5rem;
  }

  .about-heading em { font-style: italic; color: var(--accent); }

  .about-text {
    font-size: 1rem;
    color: var(--gray);
    line-height: 1.85;
    font-weight: 300;
  }

  .about-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    padding-top: 1rem;
  }

  .stat-item {
    border-top: 1px solid rgba(0,0,0,0.1);
    padding-top: 1.5rem;
  }

  .stat-num {
    font-family: var(--serif);
    font-size: 2.8rem;
    line-height: 1;
    color: var(--black);
    margin-bottom: 0.5rem;
  }

  .stat-label {
    font-size: 0.78rem;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--gray);
  }

  /* WORK */
  .work {
    padding: 8rem 3rem;
    background: var(--black);
    color: var(--white);
  }

  .work-header {
    max-width: 1200px;
    margin: 0 auto 5rem;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
  }

  .work-title {
    font-family: var(--serif);
    font-size: clamp(2.5rem, 5vw, 4.5rem);
    font-weight: 400;
    line-height: 1.05;
  }

  .work-title em { font-style: italic; color: var(--accent); }

  .work-sub {
    font-size: 0.85rem;
    color: rgba(248,247,244,0.4);
    max-width: 280px;
    text-align: right;
    line-height: 1.7;
  }

  .projects-grid {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    gap: 1.5px;
    background: rgba(255,255,255,0.06);
  }

  .project-card {
    background: var(--black);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
    cursor: pointer;
    transition: background 0.3s;
    position: relative;
    overflow: hidden;
  }

  .project-card:hover { background: #111; }

  .project-card:hover .project-arrow { transform: translate(4px, -4px); }

  .project-info {
    padding: 3rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    border-right: 1px solid rgba(255,255,255,0.06);
  }

  .project-num {
    font-family: var(--serif);
    font-size: 0.85rem;
    color: rgba(248,247,244,0.25);
    margin-bottom: 2rem;
  }

  .project-brand {
    font-family: var(--serif);
    font-size: clamp(1.8rem, 3vw, 2.6rem);
    font-weight: 400;
    line-height: 1.1;
    color: var(--white);
    margin-bottom: 0.75rem;
  }

  .project-tagline {
    font-size: 0.9rem;
    color: rgba(248,247,244,0.45);
    font-style: italic;
    margin-bottom: 2rem;
    font-family: var(--serif);
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .tag {
    font-size: 0.68rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 0.35rem 0.8rem;
    border: 1px solid rgba(255,255,255,0.15);
    color: rgba(248,247,244,0.5);
    border-radius: 100px;
  }

  .project-visual {
    padding: 2rem;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    min-height: 280px;
    height: 280px;
  }

  .project-visual > div {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .project-arrow {
    position: absolute;
    top: 2rem;
    right: 2rem;
    font-size: 1.1rem;
    color: rgba(248,247,244,0.3);
    transition: transform 0.2s;
  }

  /* Project visuals */
  .visual-cuties {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: radial-gradient(circle at 60% 50%, #f4832020 0%, transparent 65%);
  }

  .cuties-circle {
    width: 160px;
    height: 160px;
    border-radius: 50%;
    background: linear-gradient(135deg, #f4a020, #e8601a);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--serif);
    font-size: 1.1rem;
    color: white;
    letter-spacing: 0.05em;
    box-shadow: 0 20px 60px rgba(244,130,32,0.3);
    position: relative;
  }

  .cuties-ring {
    position: absolute;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    border: 1px solid rgba(244,130,32,0.2);
  }

  .visual-burberry {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #1a1a1a 0%, #0a0a0a 100%);
  }

  .burberry-plaid {
    width: 160px;
    height: 160px;
    position: relative;
    overflow: hidden;
  }

  .burberry-plaid svg { width: 100%; height: 100%; }

  .visual-lego {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    background: radial-gradient(circle at 50% 50%, #e8380020 0%, transparent 60%);
  }

  .lego-brick {
    width: 44px;
    height: 32px;
    border-radius: 4px;
    position: relative;
    box-shadow: 0 4px 12px rgba(0,0,0,0.4);
  }

  .lego-brick::before {
    content: '';
    position: absolute;
    top: -7px;
    left: 50%;
    transform: translateX(-50%);
    width: 18px;
    height: 8px;
    border-radius: 50%;
    background: inherit;
    filter: brightness(1.1);
  }

  .brick-red { background: #e83800; top: 8px; }
  .brick-yellow { background: #ffd700; top: -8px; }
  .brick-dark { background: #333; top: 4px; }

  .visual-boxed {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: radial-gradient(circle at 50% 50%, #3a8cc020 0%, transparent 65%);
  }

  .boxed-carton {
    width: 80px;
    height: 120px;
    background: var(--white);
    border-radius: 6px 6px 3px 3px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    box-shadow: 0 20px 50px rgba(255,255,255,0.08);
    position: relative;
    overflow: hidden;
  }

  .boxed-carton::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 30px;
    background: #2d7ab8;
    clip-path: polygon(0 0, 100% 0, 100% 60%, 50% 100%, 0 60%);
  }

  .boxed-text {
    font-size: 0.5rem;
    font-weight: 700;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: #2d7ab8;
    margin-top: 2rem;
  }

  /* PROCESS */
  .process {
    padding: 8rem 3rem;
    max-width: 1200px;
    margin: 0 auto;
  }

  .process-header {
    margin-bottom: 5rem;
  }

  .process-title {
    font-family: var(--serif);
    font-size: clamp(2rem, 4vw, 3.5rem);
    font-weight: 400;
    line-height: 1.1;
    max-width: 600px;
  }

  .process-title em { font-style: italic; color: var(--accent); }

  .process-steps {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 3rem;
  }

  .step {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.5s, transform 0.5s;
  }

  .step.visible { opacity: 1; transform: translateY(0); }

  .step-num {
    font-family: var(--serif);
    font-size: 3rem;
    color: rgba(0,0,0,0.08);
    line-height: 1;
    margin-bottom: 1.5rem;
  }

  .step-title {
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 1rem;
    color: var(--black);
  }

  .step-desc {
    font-size: 0.9rem;
    color: var(--gray);
    line-height: 1.75;
    font-weight: 300;
  }

  /* CONTACT */
  .contact {
    padding: 8rem 3rem;
    background: var(--light);
    border-top: 1px solid rgba(0,0,0,0.06);
  }

  .contact-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: center;
  }

  .contact-heading {
    font-family: var(--serif);
    font-size: clamp(2.5rem, 5vw, 5rem);
    font-weight: 400;
    line-height: 1.05;
  }

  .contact-heading em { font-style: italic; color: var(--accent); }

  .contact-links {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .contact-link {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    text-decoration: none;
    color: var(--black);
    padding: 1.75rem;
    background: var(--white);
    border: 1px solid rgba(0,0,0,0.08);
    transition: border-color 0.2s, transform 0.2s;
  }

  .contact-link:hover {
    border-color: var(--accent);
    transform: translateX(6px);
  }

  .contact-link-icon {
    width: 40px;
    height: 40px;
    background: var(--black);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .contact-link-icon svg { width: 18px; height: 18px; fill: var(--white); }

  .contact-link-text {
    display: flex;
    flex-direction: column;
    gap: 0.2rem;
  }

  .link-label {
    font-size: 0.7rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gray);
  }

  .link-value {
    font-size: 0.95rem;
    font-weight: 400;
    color: var(--black);
  }

  /* FOOTER */
  footer {
    padding: 2.5rem 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid rgba(0,0,0,0.08);
    background: var(--white);
  }

  .footer-copy {
    font-size: 0.75rem;
    color: var(--gray);
    letter-spacing: 0.06em;
  }

  .footer-name {
    font-family: var(--serif);
    font-size: 0.9rem;
    color: var(--black);
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }

  .fade-up {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }

  .fade-up.visible { opacity: 1; transform: translateY(0); }

  /* MODAL */
  .modal-overlay {
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.85);
    z-index: 1000;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 2rem;
  }

  .modal-overlay.open { opacity: 1; pointer-events: all; }

  .modal {
    background: var(--white);
    max-width: 780px;
    width: 100%;
    max-height: 85vh;
    overflow-y: auto;
    padding: 3.5rem;
    position: relative;
    transform: translateY(20px);
    transition: transform 0.3s;
  }

  .modal-overlay.open .modal { transform: translateY(0); }

  .modal-close {
    position: absolute;
    top: 1.5rem;
    right: 1.5rem;
    background: none;
    border: none;
    font-size: 1.5rem;
    cursor: pointer;
    color: var(--gray);
    line-height: 1;
    padding: 0.25rem;
  }

  .modal-brand {
    font-family: var(--serif);
    font-size: 0.75rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 1rem;
  }

  .modal-title {
    font-family: var(--serif);
    font-size: 2.2rem;
    font-weight: 400;
    line-height: 1.2;
    margin-bottom: 1.5rem;
  }

  .modal-divider {
    height: 1px;
    background: rgba(0,0,0,0.08);
    margin: 2rem 0;
  }

  .modal-section-title {
    font-size: 0.72rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gray);
    margin-bottom: 0.75rem;
    font-weight: 500;
  }

  .modal-body {
    font-size: 0.95rem;
    color: #444;
    line-height: 1.85;
    font-weight: 300;
    margin-bottom: 2rem;
  }

  .modal-metrics {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
    margin: 2rem 0;
  }

  .metric {
    padding: 1.25rem;
    background: var(--light);
    text-align: center;
  }

  .metric-num {
    font-family: var(--serif);
    font-size: 1.8rem;
    color: var(--black);
    display: block;
    margin-bottom: 0.35rem;
  }

  .metric-label {
    font-size: 0.68rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gray);
  }

  /* Academic badge */
  .academic-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.68rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: rgba(248,247,244,0.4);
    border: 1px solid rgba(248,247,244,0.12);
    padding: 0.3rem 0.75rem;
    border-radius: 100px;
    margin-bottom: 1.25rem;
  }

  .academic-badge::before {
    content: '';
    display: block;
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: var(--accent);
    opacity: 0.8;
  }

  .work-context {
    font-size: 0.82rem;
    color: rgba(248,247,244,0.35);
    font-style: italic;
    margin-top: 1rem;
    font-family: var(--serif);
    max-width: 340px;
  }

  .hero-context {
    font-size: 0.78rem;
    color: var(--gray);
    margin-top: 1.5rem;
    padding-top: 1.5rem;
    border-top: 1px solid rgba(0,0,0,0.08);
    font-style: italic;
    font-family: var(--serif);
    max-width: 480px;
  }

  .modal-slogan {
    font-family: var(--serif);
    font-size: 1.4rem;
    font-style: italic;
    color: var(--accent);
    margin-bottom: 1.25rem;
    padding: 1rem 1.5rem;
    border-left: 3px solid var(--accent);
    background: rgba(200,169,110,0.06);
    letter-spacing: 0.01em;
    line-height: 1.4;
  }

  .modal-academic {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.68rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gray);
    border: 1px solid rgba(0,0,0,0.12);
    padding: 0.3rem 0.75rem;
    border-radius: 100px;
    margin-bottom: 1.5rem;
  }

  .modal-academic::before {
    content: '';
    display: block;
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: var(--accent);
  }

  /* Responsive */
  @media (max-width: 768px) {
    nav { padding: 1.25rem 1.5rem; }
    .nav-links { display: none; }
    .hero { padding: 7rem 1.5rem 5rem; }
    .about { grid-template-columns: 1fr; padding: 5rem 1.5rem; gap: 3rem; }
    .work { padding: 5rem 1.5rem; }
    .work-header { flex-direction: column; align-items: flex-start; gap: 1.5rem; }
    .work-sub { text-align: left; }
    .project-card { grid-template-columns: 1fr; }
    .project-visual { min-height: 180px; }
    .process { padding: 5rem 1.5rem; }
    .process-steps { grid-template-columns: 1fr 1fr; gap: 2rem; }
    .contact { padding: 5rem 1.5rem; }
    .contact-inner { grid-template-columns: 1fr; gap: 3rem; }
    .modal { padding: 2rem; }
    .modal-metrics { grid-template-columns: 1fr 1fr; }
    footer { padding: 2rem 1.5rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">Bennett Goldmacher</a>
  <ul class="nav-links">
    <li><a href="#work">Work</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg-text">BG</div>
  <div class="hero-content">
    <span class="hero-tag">Brand Management · Marketing Strategy</span>
    <h1 class="hero-title">
      Building brands<br>
      that <em>move</em> people.
    </h1>
    <p class="hero-desc">
      Northeastern University, D'Amore-McKim School of Business. 
      Concentration in Brand Management. Driven by the intersection 
      of consumer psychology and creative strategy.
    </p>
    <a href="#work" class="hero-cta">
      View campaign work
      <span>→</span>
    </a>
    <p class="hero-context">All campaigns below were developed as academic case studies at Northeastern University's D'Amore-McKim School of Business.</p>
  </div>
  <div class="hero-scroll">Scroll to explore</div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="fade-up">
    <div class="section-label">About</div>
    <h2 class="about-heading">
      Strategy meets<br><em>creativity.</em>
    </h2>
    <p class="about-text">
      I'm a Business Administration & Psychology student at Northeastern University 
      with a concentration in Brand Management. I've developed full Go-To-Market 
      strategies for brands like Cuties, Burberry, LEGO, and Allbirds — blending 
      consumer insight with bold creative direction. I believe the best marketing 
      starts with understanding how people actually think.
    </p>
  </div>

</section>

<!-- WORK -->
<section class="work" id="work">
  <div class="work-header fade-up">
    <h2 class="work-title">Selected<br><em>campaigns.</em></h2>
    <p class="work-sub">Full Go-To-Market strategies developed as academic case studies at Northeastern's D'Amore-McKim School of Business.</p>
  </div>

  <div class="projects-grid">

    <!-- Cuties -->
    <div class="project-card" onclick="openModal('cuties')">
      <div class="project-info">
        <div class="project-num">01</div>
        <div>
          <div class="academic-badge">Academic Project · Northeastern University</div>
          <div class="project-brand">Cuties</div>
          <div class="project-tagline">"Spark Your Potential"</div>
          <div class="project-tags">
            <span class="tag">CPG</span>
            <span class="tag">Brand Strategy</span>
            <span class="tag">Experiential</span>
            <span class="tag">Social</span>
          </div>
        </div>
      </div>
      <div class="project-visual" style="padding:2rem;">
        <span class="project-arrow">↗</span>
        <div style="width:100%;height:100%;display:flex;align-items:center;justify-content:center;">
          <img src="data:image/jpeg;base64,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" style="width:160px;height:160px;object-fit:contain;" alt="Cuties logo"/>
        </div>
      </div>
    </div>

    <!-- Burberry -->
    <div class="project-card" onclick="openModal('burberry')">
      <div class="project-info">
        <div class="project-num">02</div>
        <div>
          <div class="academic-badge">Academic Project · Northeastern University</div>
          <div class="project-brand">Burberry</div>
          <div class="project-tagline">"Making the Aspirational Attainable"</div>
          <div class="project-tags">
            <span class="tag">Luxury</span>
            <span class="tag">Fashion</span>
            <span class="tag">Brand Identity</span>
          </div>
        </div>
      </div>
      <div class="project-visual" style="padding:2rem;" style="background:#111;">
        <span class="project-arrow">↗</span>
        <div style="width:100%;height:100%;display:flex;align-items:center;justify-content:center;">
          <img src="data:image/jpeg;base64,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" style="width:160px;height:160px;object-fit:contain;background:#fff;" alt="Burberry logo"/>
        </div>
      </div>
    </div>

    <!-- LEGO -->
    <div class="project-card" onclick="openModal('lego')">
      <div class="project-info">
        <div class="project-num">03</div>
        <div>
          <div class="academic-badge">Academic Project · Northeastern University</div>
          <div class="project-brand">LEGO</div>
          <div class="project-tagline">"Ignore the Instructions"</div>
          <div class="project-tags">
            <span class="tag">Toys</span>
            <span class="tag">Adult Market</span>
            <span class="tag">Campaign</span>
            <span class="tag">Creative</span>
          </div>
        </div>
      </div>
      <div class="project-visual" style="padding:2rem;">
        <span class="project-arrow">↗</span>
        <div style="width:100%;height:100%;display:flex;align-items:center;justify-content:center;">
          <img src="data:image/png;base64,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" style="width:160px;height:160px;object-fit:contain;" alt="LEGO logo"/>
        </div>
      </div>
    </div>

    <!-- Boxed Water -->
    <div class="project-card" onclick="openModal('boxed')">
      <div class="project-info">
        <div class="project-num">04</div>
        <div>
          <div class="academic-badge">Academic Project · Northeastern University</div>
          <div class="project-brand">Boxed Water</div>
          <div class="project-tagline">"Think Outside the Box"</div>
          <div class="project-tags">
            <span class="tag">Sustainability</span>
            <span class="tag">CPG</span>
            <span class="tag">Go-To-Market</span>
          </div>
        </div>
      </div>
      <div class="project-visual" style="padding:2rem;">
        <span class="project-arrow">↗</span>
        <div style="width:100%;height:100%;display:flex;align-items:center;justify-content:center;">
          <div style="width:160px;height:160px;background:#fff;display:flex;align-items:center;justify-content:center;">
            <div style="text-align:center;line-height:1;">
              <div style="font-size:2.2rem;font-weight:900;color:#000;letter-spacing:-0.02em;font-family:sans-serif;">BOXED</div>
              <div style="font-size:2.2rem;font-weight:900;color:#000;letter-spacing:-0.02em;font-family:sans-serif;">WATER</div>
              <div style="font-size:1.6rem;color:#000;font-family:sans-serif;">&#9646;</div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Alfa Romeo -->
    <div class="project-card" onclick="openModal('alfa')">
      <div class="project-info">
        <div class="project-num">05</div>
        <div>
          <div class="academic-badge">Independent Strategy Paper</div>
          <div class="project-brand">Alfa Romeo</div>
          <div class="project-tagline">"Drive the Noise Away"</div>
          <div class="project-tags">
            <span class="tag">Automotive</span>
            <span class="tag">Luxury</span>
            <span class="tag">Brand Strategy</span>
            <span class="tag">TV</span>
          </div>
        </div>
      </div>
      <div class="project-visual" style="padding:2rem;">
        <span class="project-arrow">↗</span>
        <div style="width:100%;height:100%;display:flex;align-items:center;justify-content:center;">
          <img src="data:image/jpeg;base64,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" style="width:160px;height:160px;object-fit:contain;" alt="Alfa Romeo logo"/>
        </div>
      </div>
    </div>

  </div>
</section>
<section class="process">
  <div class="process-header fade-up">
    <div class="section-label">Approach</div>
    <h2 class="process-title">How I build<br>a <em>campaign.</em></h2>
  </div>
  <div class="process-steps">
    <div class="step">
      <div class="step-num">01</div>
      <div class="step-title">Consumer Insight</div>
      <div class="step-desc">Research the audience's psychology and motivations before touching strategy. Great brands solve real tensions.</div>
    </div>
    <div class="step">
      <div class="step-num">02</div>
      <div class="step-title">Brand Positioning</div>
      <div class="step-desc">Define the Why, How, and What — building a clear brand ladder that guides every creative decision.</div>
    </div>
    <div class="step">
      <div class="step-num">03</div>
      <div class="step-title">Creative Direction</div>
      <div class="step-desc">Develop a campaign idea that's memorable, ownable, and consistent across every channel and touchpoint.</div>
    </div>
    <div class="step">
      <div class="step-num">04</div>
      <div class="step-title">Go-To-Market</div>
      <div class="step-desc">Plan activations — from OOH and social to partnerships and experiential — that bring the idea to life at scale.</div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="contact-inner">
    <div class="fade-up">
      <div class="section-label">Contact</div>
      <h2 class="contact-heading">Let's<br>work<br><em>together.</em></h2>
    </div>
    <div class="contact-links fade-up">
      <a href="mailto:goldmacher.b@northeastern.edu" class="contact-link">
        <div class="contact-link-icon">
          <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
          </svg>
        </div>
        <div class="contact-link-text">
          <span class="link-label">Email</span>
          <span class="link-value">goldmacher.b@northeastern.edu</span>
        </div>
      </a>
      <a href="https://www.linkedin.com/in/bennett-goldmacher" target="_blank" class="contact-link">
        <div class="contact-link-icon">
          <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
          </svg>
        </div>
        <div class="contact-link-text">
          <span class="link-label">LinkedIn</span>
          <span class="link-value">linkedin.com/in/bennett-goldmacher</span>
        </div>
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <span class="footer-copy">© 2025 Bennett Goldmacher. All rights reserved.</span>
  <span class="footer-name">Bennett Goldmacher</span>
</footer>

<!-- MODALS -->
<div class="modal-overlay" id="modal-overlay" onclick="closeModal(event)">
  <div class="modal" id="modal-content">
    <button class="modal-close" onclick="closeModalDirect()">×</button>
    <div id="modal-body"></div>
  </div>
</div>

<script>
const projects = {
  cuties: {
    brand: 'Cuties',
    title: 'Spark Your Potential',
    slogan: 'Spark Your Potential',
    body: `People settle. They find a routine, they get comfortable, and before they know it they stop pushing themselves. That was the tension we built this whole campaign around. Cuties mandarins are natural, portable, and actually give you energy, so we wanted to position them as the thing that sparks you back into action. The brand's purpose became awakening dormant potential in people who are tired of just going through the motions.

The target audience is defined by mindset, not age. These are people who refuse to settle into one routine and need something to remind them of that.`,
    strategy: `To bring it to life we designed a few different activations. A TikTok challenge called SparkYourPotential got people posting their goals and tagging Cuties. We created three versions of a highway billboard all using the same tagline but in different colorways. We also pitched a partnership with IRONMAN Triathlon because the audience overlap is perfect, a campus Cuties Kitchen pop-up to reach college students, AMC movie marathon sponsorships where oranges were handed out every two hours, and a Spartan Race course integration where Cuties branded obstacles were part of the race itself.`,
    metrics: [
      { num: '3', label: 'OOH billboard variants' },
      { num: '2', label: 'Brand partnerships' },
      { num: '100K+', label: 'Estimated reach' },
    ],
    tags: ['CPG', 'Brand Strategy', 'Experiential', 'Social', 'OOH', 'Partnerships']
  },
  burberry: {
    brand: 'Burberry',
    title: 'The Knights Trial Program',
    slogan: 'Making the Aspirational Attainable',
    body: `Burberry has over 150 years of heritage and some of the most recognizable brand codes in fashion. The trench coat, the check pattern, the Equestrian Knight. The challenge we found interesting was figuring out how to honor all of that while still making the brand feel relevant to a younger audience without watering it down. The answer was not a rebrand. It was a program.

We created the Knights Trial, a lifelong loyalty program where you work toward earning a full Burberry trench coat by hitting major life milestones. The idea is that aspiration is not just a feeling, it is something you earn over time.`,
    strategy: `Here is how the Knights Trial works. Every time you hit a significant life milestone, Burberry sends you an authenticated piece of fabric. Three fabrics become a scarf. Four more fabrics and your scarf earn you a jacket. A jacket and three more fabrics earn you the final trench coat. Every single piece comes with a certificate of authenticity, a thread specially woven into the fabric that is only identifiable under a microscope, and signature embroidery. To keep it exclusive no one can receive more than two pieces in a month or five in a year.

The milestones include getting your driver's license, graduating high school, getting into your dream school, graduating college, landing your first job, earning a big promotion, getting married, having your first kid, buying a home, and the tenth and final milestone is receiving the full trench coat. The final delivery arrives in a Burberry box with a sunset lamp inside, designed to feel like a moment, like opening something that means something. We presented the program through a live skit where a narrator walked through each life stage while a character sitting at one desk received each Burberry piece, with two supporting actors bringing out the items at every milestone.`,
    metrics: [
      { num: '150+', label: 'Years of heritage' },
      { num: '10', label: 'Life milestones' },
      { num: 'Global', label: 'Campaign scope' },
    ],
    tags: ['Luxury', 'Fashion', 'Loyalty Program', 'Brand Identity', 'Heritage']
  },
  lego: {
    brand: 'LEGO',
    title: 'Ignore the Instructions',
    slogan: 'Ignore the Instructions',
    body: `Adults are constantly told to follow the rules, be productive, and stay in line. LEGO has always been a product that pushes back on that but their marketing was not really saying it out loud. We wanted to build a campaign that gave adults permission to just build whatever they want with no plan and no pressure.

The big idea came from the most obvious place possible. What if LEGO told you to throw away the instruction manual? That is the campaign.`,
    strategy: `The creative hook was a set of fake LEGO-style instruction sheets showing you how to destroy the manual, throw it in the trash, light it on fire, tear it apart. It was irreverent in a way that felt true to the brand. From there the activations spread across social content, retail displays, and out of home placements all carrying the same energy. The message was simple: you already know how to build, you do not need anyone telling you how.`,
    metrics: [
      { num: 'Adults 25-45', label: 'Target segment' },
      { num: '1', label: 'Disruptive tagline' },
      { num: '360', label: 'Campaign execution' },
    ],
    tags: ['Toys', 'Adult Market', 'Creative Campaign', 'Social', 'OOH']
  },
  boxed: {
    brand: 'Boxed Water',
    title: 'The Intentional Consumer',
    slogan: 'Think Outside the Box',
    body: `This campaign was not really about sustainability in the traditional sense. We were not trying to guilt anyone into making a switch. The people we were going after already think of themselves as intentional. Every purchase they make, every brand they support, every product on their desk or in their bag says something about who they are. They are the kind of people who notice details, do their research, and make choices with purpose.

Boxed Water fits that identity perfectly. It is clean, it is considered, and it signals something about the person holding it without them having to say a word.`,
    strategy: `Our strategy was about placing Boxed Water inside the moments and spaces that intentional consumers already occupy. We focused on campus and creative workplace distribution, partnerships with brands and spaces that share the same values, and a social campaign built around the idea that the small choices add up. The tone was never preachy. We leaned into the identity angle because people do not just buy products, they buy what those products say about them.`,
    metrics: [
      { num: 'Gen Z', label: 'Primary audience' },
      { num: '92%', label: 'Renewable materials' },
      { num: 'Multi', label: 'Channel strategy' },
    ],
    tags: ['Rebrand', 'CPG', 'Identity-Driven', 'Go-To-Market', 'Social']
  },
  alfa: {
    brand: 'Alfa Romeo',
    title: 'Drive the Noise Away',
    body: `In 2026 people think happiness is all about optics. Who has more friends, more money, more expensive vacations. Luxury cars are right in the middle of that because they attract attention and attention attracts the wrong people. Fake friends, clout chasers, people who want something from you. But the truly successful people I was thinking about when I wrote this paper understand that real wealth is not about any of that. Real wealth is time. Time for yourself, time for the things you love, time for the people who actually matter.

Alfa Romeo is different from BMW or Mercedes because it is built around the driver's experience, not what other people think of the car. That became the whole idea.`,
    strategy: `I designed three activations. The first was a TV spot set in San Francisco where a successful guy is surrounded by cameras and people demanding his attention in a parking garage. He gets in his Alfa Romeo and drives. Eventually he loses everyone and ends up alone at the top of Mount Tamalpais. He steps out, takes a breath, and gets back in. The second was a wedding gift program where select high profile newlyweds stepping away from public life receive an Alfa Romeo experience. The third was simple billboards in Class A office parks that just say Drive The Noise Away.`,
    metrics: [
      { num: '$200K+', label: 'HHI target segment' },
      { num: '3', label: 'Campaign activations' },
      { num: 'Solo', label: 'Independent work' },
    ],
    tags: ['Automotive', 'Luxury', 'Brand Strategy', 'TV', 'OOH', 'Independent']
  }
};

function openModal(key) {
  const p = projects[key];
  document.getElementById('modal-body').innerHTML = `
    <div class="modal-brand">${p.brand}</div>
    <h3 class="modal-title">${p.title}</h3>
    ${p.slogan ? `<div class="modal-slogan">"${p.slogan}"</div>` : ''}
    <div class="modal-academic">Academic Case Study · D'Amore-McKim School of Business, Northeastern University</div>
    <div class="project-tags" style="margin-bottom:1rem;">
      ${p.tags.map(t => `<span class="tag" style="color:#666;border-color:rgba(0,0,0,0.15);">${t}</span>`).join('')}
    </div>
    <div class="modal-divider"></div>
    <div class="modal-section-title">Campaign Overview</div>
    <p class="modal-body">${p.body}</p>
    <div class="modal-metrics">
      ${p.metrics.map(m => `<div class="metric"><span class="metric-num">${m.num}</span><span class="metric-label">${m.label}</span></div>`).join('')}
    </div>
    <div class="modal-divider"></div>
    <div class="modal-section-title">Strategy & Activations</div>
    <p class="modal-body">${p.strategy}</p>
  `;
  document.getElementById('modal-overlay').classList.add('open');
  document.body.style.overflow = 'hidden';
}

function closeModal(e) {
  if (e.target === document.getElementById('modal-overlay')) closeModalDirect();
}

function closeModalDirect() {
  document.getElementById('modal-overlay').classList.remove('open');
  document.body.style.overflow = '';
}

document.addEventListener('keydown', e => { if (e.key === 'Escape') closeModalDirect(); });

// Scroll animations
const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry, i) => {
    if (entry.isIntersecting) {
      entry.target.style.transitionDelay = `${i * 0.08}s`;
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.15 });

document.querySelectorAll('.fade-up, .step').forEach(el => observer.observe(el));
</script>
</body>
</html>

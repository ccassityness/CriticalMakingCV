<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Cailey Cassity-Ness — Scholar, Educator, Writer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,700;1,400;1,500&family=Jost:wght@300;400;500&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet">
  <style>
    :root {
      --ink:        #141a14;
      --off-white:  #f5f8f4;
      --blush:      #deeade;
      --blush-mid:  #a8c9a8;
      --blush-deep: #6a9e72;
      --rose:       #3d7048;
      --charcoal:   #1e2b1e;
      --muted:      #627062;
      --border:     #cfdecf;
      --parchment:  #eaf2e8;
      --dark-bg:    #1a261a;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }

    body {
      font-family: 'Jost', sans-serif;
      background: var(--off-white);
      color: var(--ink);
      overflow-x: hidden;
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 200;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 3rem;
      height: 60px;
      background: rgba(250,248,245,0.94);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--border);
    }
    .nav-name {
      font-family: 'Playfair Display', serif;
      font-size: 1rem;
      font-weight: 400;
      letter-spacing: 0.03em;
      color: var(--rose);
      text-decoration: none;
    }
    .nav-links {
      display: flex;
      gap: 0;
      list-style: none;
    }
    .nav-links a {
      display: block;
      padding: 0 1.1rem;
      height: 60px;
      line-height: 60px;
      font-family: 'DM Mono', monospace;
      font-size: 0.58rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--muted);
      text-decoration: none;
      border-bottom: 2px solid transparent;
      transition: color 0.2s, border-color 0.2s;
    }
    .nav-links a:hover,
    .nav-links a.active { color: var(--rose); border-bottom-color: var(--rose); }
    .nav-cv {
      font-family: 'DM Mono', monospace;
      font-size: 0.58rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--off-white);
      background: var(--rose);
      padding: 0.55rem 1.2rem;
      text-decoration: none;
      transition: background 0.2s;
    }
    .nav-cv:hover { background: var(--blush-deep); }

    /* HERO */
    #hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      position: relative;
      overflow: hidden;
      padding-top: 60px;
    }
    .hero-bg {
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, var(--blush) 0%, var(--off-white) 55%, var(--parchment) 100%);
    }
    .hero-circle {
      position: absolute;
      right: -8rem;
      top: 50%;
      transform: translateY(-50%);
      width: 55vw;
      height: 55vw;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(222,234,222,0.65) 0%, rgba(222,234,222,0) 70%);
      pointer-events: none;
    }
    .hero-inner {
      position: relative;
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 3rem;
      width: 100%;
    }
    .hero-eyebrow {
      font-family: 'DM Mono', monospace;
      font-size: 0.65rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--blush-deep);
      margin-bottom: 1.5rem;
      opacity: 0;
      animation: riseIn 0.9s 0.2s forwards;
    }
    h1.hero-name {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3.5rem, 7vw, 6.5rem);
      font-weight: 400;
      line-height: 1.02;
      letter-spacing: -0.01em;
      color: var(--charcoal);
      opacity: 0;
      animation: riseIn 0.9s 0.4s forwards;
    }
    h1.hero-name em {
      display: block;
      font-style: italic;
      color: var(--rose);
    }
    .hero-tagline {
      margin-top: 1.8rem;
      max-width: 520px;
      font-size: 1.1rem;
      font-weight: 300;
      line-height: 1.75;
      color: var(--muted);
      opacity: 0;
      animation: riseIn 0.9s 0.6s forwards;
    }
    .hero-chips {
      margin-top: 2rem;
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      opacity: 0;
      animation: riseIn 0.9s 0.8s forwards;
    }
    .chip {
      display: inline-block;
      padding: 0.35rem 0.9rem;
      background: var(--blush);
      border: 1px solid var(--blush-mid);
      color: var(--rose);
      font-family: 'DM Mono', monospace;
      font-size: 0.6rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      border-radius: 2px;
    }
    .hero-actions {
      margin-top: 2.5rem;
      display: flex;
      gap: 1rem;
      opacity: 0;
      animation: riseIn 0.9s 1s forwards;
    }
    .btn {
      display: inline-block;
      padding: 0.85rem 2rem;
      font-family: 'DM Mono', monospace;
      font-size: 0.65rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      text-decoration: none;
      transition: all 0.2s;
    }
    .btn-filled { background: var(--rose); color: #fff; }
    .btn-filled:hover { background: var(--blush-deep); }
    .btn-outline { border: 1.5px solid var(--rose); color: var(--rose); }
    .btn-outline:hover { background: var(--blush); }

    .scroll-hint {
      position: absolute;
      bottom: 2.5rem;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.5rem;
      opacity: 0;
      animation: riseIn 1s 1.4s forwards;
    }
    .scroll-hint span {
      font-family: 'DM Mono', monospace;
      font-size: 0.55rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--muted);
    }
    .scroll-hint-line {
      width: 1px;
      height: 40px;
      background: linear-gradient(to bottom, var(--blush-deep), transparent);
      animation: drip 2s 2s infinite;
    }
    @keyframes drip {
      0%, 100% { transform: scaleY(1); opacity: 1; }
      50% { transform: scaleY(0.5); opacity: 0.4; }
    }

    /* SECTION COMMONS */
    .section { padding: 6rem 3rem; }
    .section-inner { max-width: 1100px; margin: 0 auto; }
    .section-header {
      display: flex;
      align-items: baseline;
      gap: 1.5rem;
      margin-bottom: 3.5rem;
    }
    .section-num {
      font-family: 'DM Mono', monospace;
      font-size: 0.62rem;
      letter-spacing: 0.15em;
      color: var(--blush-deep);
    }
    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.8rem, 3vw, 2.6rem);
      font-weight: 400;
      line-height: 1.15;
      color: var(--charcoal);
    }
    .section-title em { font-style: italic; color: var(--rose); }
    .section-rule { flex: 1; height: 1px; background: var(--border); }

    .reveal {
      opacity: 0;
      transform: translateY(22px);
      transition: opacity 0.65s ease, transform 0.65s ease;
    }
    .reveal.in { opacity: 1; transform: none; }

    /* ABOUT + EDUCATION */
    #about { background: var(--off-white); }
    .about-layout {
      display: grid;
      grid-template-columns: 3fr 2fr;
      gap: 4rem;
      align-items: start;
    }
    .about-text p {
      font-size: 1.1rem;
      font-weight: 300;
      line-height: 1.85;
      color: var(--ink);
      margin-bottom: 1.25rem;
    }
    .about-text p strong { font-weight: 500; color: var(--rose); }

    .edu-side h3 {
      font-family: 'DM Mono', monospace;
      font-size: 0.62rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--blush-deep);
      margin-bottom: 1.5rem;
    }
    .edu-entry {
      position: relative;
      padding: 0 0 1.75rem 1.5rem;
      border-left: 1.5px solid var(--blush-mid);
    }
    .edu-entry::before {
      content: '';
      position: absolute;
      left: -5px; top: 6px;
      width: 8px; height: 8px;
      border-radius: 50%;
      background: var(--rose);
    }
    .edu-year {
      font-family: 'DM Mono', monospace;
      font-size: 0.58rem;
      letter-spacing: 0.1em;
      color: var(--muted);
      margin-bottom: 0.25rem;
    }
    .edu-deg {
      font-family: 'Playfair Display', serif;
      font-size: 1rem;
      font-style: italic;
      color: var(--charcoal);
      line-height: 1.3;
      margin-bottom: 0.2rem;
    }
    .edu-inst { font-size: 0.85rem; color: var(--muted); }
    .edu-badge {
      display: inline-block;
      margin-top: 0.35rem;
      font-family: 'DM Mono', monospace;
      font-size: 0.55rem;
      letter-spacing: 0.08em;
      background: var(--blush);
      color: var(--rose);
      padding: 0.15rem 0.55rem;
    }

    /* EXPERIENCE */
    #experience { background: var(--parchment); }
    .exp-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
    }
    .exp-card {
      background: var(--off-white);
      border: 1px solid var(--border);
      padding: 1.75rem;
      border-top: 3px solid var(--blush-mid);
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .exp-card:hover { transform: translateY(-3px); box-shadow: 0 6px 20px rgba(0,0,0,0.06); }
    .exp-org {
      font-family: 'DM Mono', monospace;
      font-size: 0.58rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--rose);
      margin-bottom: 0.4rem;
    }
    .exp-role {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem;
      font-weight: 400;
      margin-bottom: 0.2rem;
      line-height: 1.3;
    }
    .exp-dates {
      font-family: 'DM Mono', monospace;
      font-size: 0.57rem;
      color: var(--muted);
      letter-spacing: 0.08em;
      margin-bottom: 0.9rem;
    }
    .exp-desc {
      font-size: 0.9rem;
      font-weight: 300;
      color: var(--muted);
      line-height: 1.7;
    }

    /* TEACHING */
    #teaching { background: var(--blush); }
    .teaching-intro {
      font-size: 1.1rem;
      font-weight: 300;
      font-style: italic;
      color: var(--charcoal);
      max-width: 640px;
      line-height: 1.8;
      margin-bottom: 3rem;
      border-left: 3px solid var(--rose);
      padding-left: 1.5rem;
    }
    .teaching-stats {
      display: flex;
      gap: 0;
      margin-bottom: 3rem;
      border: 1px solid var(--blush-mid);
      background: white;
    }
    .t-stat {
      flex: 1;
      text-align: center;
      padding: 2rem 1rem;
      border-right: 1px solid var(--blush-mid);
    }
    .t-stat:last-child { border-right: none; }
    .t-stat-num {
      font-family: 'Playfair Display', serif;
      font-size: 2.8rem;
      font-weight: 400;
      color: var(--rose);
      line-height: 1;
    }
    .t-stat-label {
      font-family: 'DM Mono', monospace;
      font-size: 0.58rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--muted);
      margin-top: 0.4rem;
    }
    .courses-wrap { overflow-x: auto; }
    table.courses {
      width: 100%;
      border-collapse: collapse;
      background: white;
    }
    table.courses th {
      font-family: 'DM Mono', monospace;
      font-size: 0.58rem;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      color: var(--muted);
      padding: 0.85rem 1.2rem;
      text-align: left;
      background: var(--blush);
      border-bottom: 1px solid var(--blush-mid);
    }
    table.courses td {
      padding: 0.85rem 1.2rem;
      font-size: 0.9rem;
      border-bottom: 1px solid var(--blush);
      vertical-align: middle;
    }
    table.courses tr:last-child td { border-bottom: none; }
    table.courses tr:hover td { background: #fdf9f9; }
    .modality-tag {
      display: inline-block;
      font-family: 'DM Mono', monospace;
      font-size: 0.52rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      padding: 0.15rem 0.5rem;
      margin: 0.1rem;
      border-radius: 2px;
    }
    .m-online  { background: #f0faf5; color: #3d8a5e; }
    .m-trad    { background: var(--blush); color: var(--rose); }
    .m-hybrid  { background: #f0eefa; color: #6b52a8; }

    /* PROJECTS */
    #projects { background: var(--off-white); }
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }
    .proj-card {
      border: 1px solid var(--border);
      padding: 2rem;
      background: white;
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .proj-card:hover { transform: translateY(-4px); box-shadow: 0 8px 28px rgba(0,0,0,0.07); }
    .proj-n {
      font-family: 'Playfair Display', serif;
      font-size: 3.5rem;
      font-weight: 400;
      color: var(--blush);
      line-height: 1;
      margin-bottom: 0.75rem;
    }
    .proj-tag {
      display: inline-block;
      font-family: 'DM Mono', monospace;
      font-size: 0.55rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      background: var(--blush);
      color: var(--rose);
      padding: 0.2rem 0.6rem;
      margin-bottom: 0.75rem;
    }
    .proj-title {
      font-family: 'Playfair Display', serif;
      font-size: 1rem;
      font-style: italic;
      line-height: 1.4;
      margin-bottom: 0.75rem;
      color: var(--charcoal);
    }
    .proj-desc {
      font-size: 0.88rem;
      font-weight: 300;
      color: var(--muted);
      line-height: 1.65;
    }
    .proj-date {
      margin-top: 1.25rem;
      font-family: 'DM Mono', monospace;
      font-size: 0.55rem;
      letter-spacing: 0.08em;
      color: var(--blush-mid);
    }

    /* PRESENTATIONS */
    #presentations { background: var(--parchment); }
    .pres-list { border-top: 1px solid var(--border); }
    .pres-row {
      display: grid;
      grid-template-columns: 80px 1fr;
      gap: 2rem;
      padding: 1.5rem 0;
      border-bottom: 1px solid var(--border);
      align-items: start;
    }
    .pres-year {
      font-family: 'DM Mono', monospace;
      font-size: 0.65rem;
      letter-spacing: 0.08em;
      color: var(--rose);
      padding-top: 0.15rem;
    }
    .pres-title {
      font-family: 'Playfair Display', serif;
      font-size: 1rem;
      font-style: italic;
      color: var(--charcoal);
      line-height: 1.4;
      margin-bottom: 0.3rem;
    }
    .pres-venue {
      font-family: 'DM Mono', monospace;
      font-size: 0.58rem;
      letter-spacing: 0.08em;
      color: var(--muted);
      text-transform: uppercase;
    }

    /* PUBLICATIONS */
    #publications { background: var(--blush); }
    .pub-card {
      background: white;
      border: 1px solid var(--blush-mid);
      border-left: 4px solid var(--rose);
      padding: 2rem 2.5rem;
      max-width: 700px;
    }
    .pub-type {
      font-family: 'DM Mono', monospace;
      font-size: 0.58rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--rose);
      margin-bottom: 0.6rem;
    }
    .pub-title {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem;
      font-style: italic;
      color: var(--charcoal);
      margin-bottom: 0.4rem;
    }
    .pub-meta {
      font-size: 0.9rem;
      font-weight: 300;
      color: var(--muted);
    }

    /* AWARDS */
    #awards { background: var(--dark-bg); }
    #awards .section-num { color: var(--blush-mid); }
    #awards .section-title { color: #f5eeea; }
    #awards .section-rule { background: rgba(255,255,255,0.1); }
    .awards-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }
    .award-card {
      border: 1px solid rgba(255,255,255,0.1);
      padding: 2rem;
      background: rgba(255,255,255,0.03);
      transition: background 0.2s;
    }
    .award-card:hover { background: rgba(222,234,222,0.08); }
    .award-star {
      font-size: 1.2rem;
      color: var(--blush-mid);
      margin-bottom: 1rem;
    }
    .award-year {
      font-family: 'DM Mono', monospace;
      font-size: 0.6rem;
      letter-spacing: 0.12em;
      color: var(--blush-mid);
      margin-bottom: 0.6rem;
    }
    .award-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.05rem;
      font-weight: 400;
      color: #f0e8e8;
      line-height: 1.4;
    }

    /* CONTACT */
    #contact {
      background: var(--off-white);
      padding: 6rem 3rem;
      text-align: center;
    }
    .contact-inner { max-width: 580px; margin: 0 auto; }
    .contact-tagline {
      font-size: 1.05rem;
      font-weight: 300;
      color: var(--muted);
      line-height: 1.8;
      margin: 0 auto 3rem;
    }
    .contact-cards {
      display: flex;
      justify-content: center;
      gap: 1.2rem;
      flex-wrap: wrap;
    }
    .contact-card {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.4rem;
      text-decoration: none;
      padding: 1.5rem 2rem;
      border: 1px solid var(--border);
      background: var(--parchment);
      min-width: 130px;
      transition: border-color 0.2s, transform 0.2s;
    }
    .contact-card:hover { border-color: var(--rose); transform: translateY(-3px); }
    .contact-icon { font-size: 1.4rem; }
    .contact-label {
      font-family: 'DM Mono', monospace;
      font-size: 0.55rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--muted);
    }
    .contact-val { font-size: 0.85rem; color: var(--charcoal); }

    footer {
      background: var(--dark-bg);
      color: rgba(240,232,232,0.35);
      text-align: center;
      padding: 1.75rem;
      font-family: 'DM Mono', monospace;
      font-size: 0.58rem;
      letter-spacing: 0.1em;
    }
    footer a { color: var(--blush-mid); text-decoration: none; }

    @keyframes riseIn {
      from { opacity: 0; transform: translateY(18px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    @media (max-width: 900px) {
      nav { padding: 0 1.5rem; }
      .nav-links { display: none; }
      .section { padding: 4rem 1.5rem; }
      .about-layout { grid-template-columns: 1fr; }
      .exp-grid { grid-template-columns: 1fr; }
      .projects-grid { grid-template-columns: 1fr 1fr; }
      .awards-grid { grid-template-columns: 1fr; }
    }
    @media (max-width: 600px) {
      .projects-grid { grid-template-columns: 1fr; }
      .teaching-stats { flex-direction: column; }
      .t-stat { border-right: none; border-bottom: 1px solid var(--blush-mid); }
      .pres-row { grid-template-columns: 60px 1fr; gap: 1rem; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-name" href="#hero">Cailey Cassity-Ness</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#teaching">Teaching</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#presentations">Presentations</a></li>
    <li><a href="#publications">Publications</a></li>
    <li><a href="#awards">Awards</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a class="nav-cv" href="CassityNess_CV.docx" download>&#8595; CV</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-circle"></div>
  <div class="hero-inner">
    <p class="hero-eyebrow">PhD Candidate &middot; Scholar &middot; Educator &middot; Writer</p>
    <h1 class="hero-name">Cailey<br><em>Cassity-Ness</em></h1>
    <p class="hero-tagline">Texts &amp; Technology doctoral student at the University of Central Florida, dedicated to the intersections of rhetoric, digital humanities, writing pedagogy, and community engagement.</p>
    <div class="hero-actions">
      <a class="btn btn-filled" href="CassityNess_CV.docx" download>Download CV</a>
    </div>
  </div>
  <div class="scroll-hint">
    <span>Scroll</span>
    <div class="scroll-hint-line"></div>
  </div>
</section>

<!-- ABOUT + EDUCATION -->
<section class="section" id="about">
  <div class="section-inner">
    <div class="section-header reveal">
      <span class="section-num">01</span>
      <h2 class="section-title">About &amp; <em>Education</em></h2>
      <div class="section-rule"></div>
    </div>
    <div class="about-layout">
      <div class="about-text">
        <p class="reveal">I'm a <strong>PhD student in Texts &amp; Technology</strong> at the University of Central Florida, where I explore the intersections of language, digital tools, and critical making — and what they mean for how we teach, communicate, and build community.</p>
        <p class="reveal">My path has been deliberately wide. A <strong>BA in Greek &amp; Roman Studies</strong> with a chemistry minor and biochemistry honors thesis taught me to move between disciplines without apology. An <strong>MA in English/Technical Communication</strong> (4.0 GPA, Summa Cum Laude) sharpened my instincts for writing, rhetoric, and teaching. Years of instruction at four institutions across Texas and Florida reinforced that every classroom is a community, and every modality demands its own care.</p>
        <p class="reveal">Outside the classroom, I lead community engagement and career development work at Rollins College — planning large-scale service events, advising student organizations, administering CRM systems, and translating institutional impact into narrative. I believe the writing center, the classroom, and the civic square all do the same essential work: they make room for voices to grow.</p>
      </div>
      <div class="edu-side reveal">
        <h3>Education</h3>
        <div class="edu-entry">
          <div class="edu-year">2025 &ndash; Present</div>
          <div class="edu-deg">Ph.D. in Texts &amp; Technology</div>
          <div class="edu-inst">University of Central Florida</div>
          <span class="edu-badge">In Progress</span>
        </div>
        <div class="edu-entry">
          <div class="edu-year">2021</div>
          <div class="edu-deg">M.A. in English, Technical Communication</div>
          <div class="edu-inst">University of Central Florida</div>
          <span class="edu-badge">Summa Cum Laude &middot; 4.00 GPA</span>
        </div>
        <div class="edu-entry">
          <div class="edu-year">2020</div>
          <div class="edu-deg">B.A. in Greek &amp; Roman Studies</div>
          <div class="edu-inst">Millsaps College &middot; Minor in Chemistry &middot; Honors Thesis in Biochemistry</div>
          <span class="edu-badge">Magna Cum Laude &middot; 3.82 GPA</span>
        </div>
        <div class="edu-entry">
          <div class="edu-year">2017</div>
          <div class="edu-deg">A.A. in General Studies</div>
          <div class="edu-inst">Northwest Florida State College</div>
          <span class="edu-badge">Magna Cum Laude &middot; 3.87 GPA</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section class="section" id="experience">
  <div class="section-inner">
    <div class="section-header reveal">
      <span class="section-num">02</span>
      <h2 class="section-title">Professional <em>Experience</em></h2>
      <div class="section-rule"></div>
    </div>
    <div class="exp-grid">
      <div class="exp-card reveal">
        <div class="exp-org">Rollins College &middot; Winter Park, FL</div>
        <div class="exp-role">Program Coordinator, Center for Career &amp; Life Planning</div>
        <div class="exp-dates">Aug. 2025 &ndash; Present</div>
        <p class="exp-desc">Administers Handshake CRM, compiles monthly and annual usage and First Destination Survey data for assessment storytelling, coordinates major recruiting and networking events, and manages office budget while serving as the front-facing coordinator for students, alumni, employers, and faculty.</p>
      </div>
      <div class="exp-card reveal">
        <div class="exp-org">Rollins College &middot; Winter Park, FL</div>
        <div class="exp-role">Program Assistant, Center for Leadership &amp; Community Engagement</div>
        <div class="exp-dates">July 2024 &ndash; Aug. 2025</div>
        <p class="exp-desc">Led planning for MLK Jr. Day of Service, President's Day of Service, Spring SPARC, SeniorServe, and SummerServe. Co-advised the JUMP program and Democracy Project; co-led Rollins Relief Program and campus-wide civic engagement efforts.</p>
      </div>
      <div class="exp-card reveal">
        <div class="exp-org">Blinn College &middot; Bryan, TX (Remote)</div>
        <div class="exp-role">Faculty, English Department</div>
        <div class="exp-dates">Aug. 2022 &ndash; Present</div>
        <p class="exp-desc">Teaches Composition I and II across traditional, hybrid, and asynchronous formats; progressed from part-time to full-time and back to strategic part-time alongside doctoral studies. Nominated for Teaching Excellence Award 2024.</p>
      </div>
      <div class="exp-card reveal">
        <div class="exp-org">Valencia College &middot; Orlando, FL</div>
        <div class="exp-role">Part-time Faculty, English Department</div>
        <div class="exp-dates">July 2024 &ndash; Apr. 2025</div>
        <p class="exp-desc">Taught freshman composition I and II across traditional, hybrid, and asynchronous modalities at the Downtown Campus. Applied metacognitive and active learning frameworks through Valencia's Digital Professor Certificate program.</p>
      </div>
      <div class="exp-card reveal">
        <div class="exp-org">Texas A&amp;M University &middot; College Station, TX</div>
        <div class="exp-role">Program Aide, Office of Admissions</div>
        <div class="exp-dates">Oct. 2022 &ndash; Mar. 2024</div>
        <p class="exp-desc">Holistically reviewed freshman applications at an average rate of 3.25 min/application across two admission seasons, balancing thoroughness with professional efficiency and objectivity.</p>
      </div>
      <div class="exp-card reveal">
        <div class="exp-org">Freelance &middot; Orlando, FL</div>
        <div class="exp-role">Writer &amp; Editor</div>
        <div class="exp-dates">Oct. 2024 &ndash; Present</div>
        <p class="exp-desc">Co-led writing and editing of Rollins College's 2026 Carnegie Foundation Community Engagement Reclassification Application. Edited an EdD dissertation in Higher Education Leadership post-defense, including APA citation and formatting review.</p>
      </div>
    </div>
  </div>
</section>

<!-- TEACHING -->
<section class="section" id="teaching">
  <div class="section-inner">
    <div class="section-header reveal">
      <span class="section-num">03</span>
      <h2 class="section-title"><em>Teaching</em> Record</h2>
      <div class="section-rule"></div>
    </div>
    <p class="teaching-intro reveal">I teach writing as a practice of thinking &mdash; not a set of rules to follow. My courses meet students where they are and challenge them to go further, whether they're reaching for clarity, argumentation, or their own voice.</p>
    <div class="teaching-stats reveal">
      <div class="t-stat">
        <div class="t-stat-num">4+</div>
        <div class="t-stat-label">Years Teaching</div>
      </div>
      <div class="t-stat">
        <div class="t-stat-num">2</div>
        <div class="t-stat-label">Institutions</div>
      </div>
      <div class="t-stat">
        <div class="t-stat-num">40+</div>
        <div class="t-stat-label">Sections Taught</div>
      </div>
      <div class="t-stat">
        <div class="t-stat-num">3</div>
        <div class="t-stat-label">Modalities</div>
      </div>
    </div>
    <div class="courses-wrap reveal">
      <table class="courses">
        <thead>
          <tr>
            <th>Institution</th>
            <th>Course</th>
            <th>Modality</th>
            <th>Dates</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td rowspan="2" style="font-weight:500; border-right:2px solid var(--blush-mid); vertical-align:middle;">Blinn College</td>
            <td>ENGL 1301 Composition I</td>
            <td><span class="modality-tag m-online">Async Online</span> <span class="modality-tag m-trad">Traditional</span></td>
            <td>Fall 2022 &ndash; Present</td>
          </tr>
          <tr>
            <td>ENGL 1302 Composition II</td>
            <td><span class="modality-tag m-trad">Traditional</span></td>
            <td>Spring 2023 &ndash; Spring 2024</td>
          </tr>
          <tr>
            <td rowspan="2" style="font-weight:500; border-right:2px solid var(--blush-mid); border-top:2px solid var(--blush-mid); vertical-align:middle;">Valencia College</td>
            <td style="border-top:2px solid var(--blush-mid);">ENC 1101 Freshman Composition I</td>
            <td style="border-top:2px solid var(--blush-mid);"><span class="modality-tag m-trad">Traditional</span> <span class="modality-tag m-hybrid">Hybrid</span> <span class="modality-tag m-online">Async Online</span></td>
            <td style="border-top:2px solid var(--blush-mid);">Fall 2024 &ndash; Spring 2025</td>
          </tr>
          <tr>
            <td>ENC 1102 Freshman Composition II</td>
            <td><span class="modality-tag m-trad">Traditional</span></td>
            <td>Fall 2024 &ndash; Spring 2025</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section class="section" id="projects">
  <div class="section-inner">
    <div class="section-header reveal">
      <span class="section-num">04</span>
      <h2 class="section-title">Selected <em>Projects</em></h2>
      <div class="section-rule"></div>
    </div>
    <div class="projects-grid">
      <div class="proj-card reveal">
        <div class="proj-n">01</div>
        <span class="proj-tag">Network Analysis &middot; GIS</span>
        <div class="proj-title">Mapping the Lineages of Stardew Valley's Music</div>
        <p class="proj-desc">A network analysis and visualization built in ArcGIS StoryMap tracing the cultural, geographical, and historical lineages converging in <em>Stardew Valley</em>'s soundtrack &mdash; and what happens to those lineages along the way.</p>
        <div class="proj-date">March 2026</div>
      </div>
      <div class="proj-card reveal">
        <div class="proj-n">02</div>
        <span class="proj-tag">Digital Media &middot; Art History</span>
        <div class="proj-title">Haunted Nations: Art, Grief, and the Ghost After World War I</div>
        <p class="proj-desc">A digital media library of post-WWI visual art depicting ghosts and spectral imagery, drawing thematic threads across national contexts to examine how grief and collective trauma were aestheticized in the aftermath of war.</p>
        <div class="proj-date">April 2026</div>
      </div>
      <div class="proj-card reveal">
        <div class="proj-n">03</div>
        <span class="proj-tag">Biochemistry &middot; Undergraduate Research</span>
        <div class="proj-title">Method Development for Total Mitochondrial DNA Sequencing of Plethodon Species</div>
        <p class="proj-desc">Honors thesis research developing sequencing methods for <em>Plethodon websteri</em> and <em>Plethodon ventralis</em>, presented at two national conferences &mdash; evidence of genuine breadth across scientific and humanistic inquiry.</p>
        <div class="proj-date">2019 &ndash; 2020</div>
      </div>
    </div>
  </div>
</section>

<!-- PRESENTATIONS -->
<section class="section" id="presentations">
  <div class="section-inner">
    <div class="section-header reveal">
      <span class="section-num">05</span>
      <h2 class="section-title">Conference <em>Presentations</em></h2>
      <div class="section-rule"></div>
    </div>
    <div class="pres-list">
      <div class="pres-row reveal">
        <div class="pres-year">2026</div>
        <div>
          <div class="pres-title">Cultural and Geographical Influences of Stardew Valley</div>
          <div class="pres-venue">Amy Zeh High-Impact Practices Showcase</div>
        </div>
      </div>
      <div class="pres-row reveal">
        <div class="pres-year">2020</div>
        <div>
          <div class="pres-title">Method Development for Total Mitochondrial DNA Sequencing of Plethodon websteri and Plethodon ventralis</div>
          <div class="pres-venue">Millsaps College Honors Research Conference</div>
        </div>
      </div>
      <div class="pres-row reveal">
        <div class="pres-year">2020</div>
        <div>
          <div class="pres-title">Method Development for Total Mitochondrial DNA Sequencing of Plethodon websteri and Plethodon ventralis</div>
          <div class="pres-venue">Millsaps College Beta Beta Beta Research Symposium</div>
        </div>
      </div>
      <div class="pres-row reveal">
        <div class="pres-year">2020</div>
        <div>
          <div class="pres-title">Weeds or Wildflowers? Examining Writing Center and Academic Success Center Collaborations</div>
          <div class="pres-venue">Southeastern Writing Center Association &middot; with Liz Egan et al.</div>
        </div>
      </div>
      <div class="pres-row reveal">
        <div class="pres-year">2019</div>
        <div>
          <div class="pres-title">Mapping the Blues: Linking the Communities of Mississippi's Writing Centers</div>
          <div class="pres-venue">National Conference on Peer Tutoring in Writing / International Writing Center Association Joint Conference</div>
        </div>
      </div>
      <div class="pres-row reveal">
        <div class="pres-year">2019</div>
        <div>
          <div class="pres-title">Are You My Neighbor? Building Connections between Mississippi's Writing Centers</div>
          <div class="pres-venue">Mississippi Writing Center Association Conference</div>
        </div>
      </div>
      <div class="pres-row reveal">
        <div class="pres-year">2019</div>
        <div>
          <div class="pres-title">Citizen, Connection, and Collaboration: Understanding Diversity in Jackson's Writing Centers</div>
          <div class="pres-venue">Mississippi Writing Center Association Conference &middot; with Morgan Moss</div>
        </div>
      </div>
      <div class="pres-row reveal">
        <div class="pres-year">2019</div>
        <div>
          <div class="pres-title">Forced into Fatalism</div>
          <div class="pres-venue">Millsaps Feminist Colloquium &middot; Roundtable Panelist</div>
        </div>
      </div>
      <div class="pres-row reveal">
        <div class="pres-year">2018</div>
        <div>
          <div class="pres-title">Psychosocial Predictors of Antidepressant Prescriptions in Pediatric Oncology Patients</div>
          <div class="pres-venue">69th Annual Convention, Mississippi Psychological Association &middot; Poster Presentation</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PUBLICATIONS -->
<section class="section" id="publications">
  <div class="section-inner">
    <div class="section-header reveal">
      <span class="section-num">06</span>
      <h2 class="section-title"><em>Publications</em></h2>
      <div class="section-rule"></div>
    </div>
    <div class="pub-card reveal">
      <div class="pub-type">Poetry &middot; Creative Writing</div>
      <div class="pub-title">&ldquo;Hope&rdquo;</div>
      <p class="pub-meta"><em>Mississippi Poetry Journal</em>, 2020 Contest Edition &middot; Summer 2020</p>
    </div>
  </div>
</section>

<!-- AWARDS -->
<section class="section" id="awards">
  <div class="section-inner">
    <div class="section-header reveal">
      <span class="section-num">07</span>
      <h2 class="section-title">Awards &amp; <em>Honors</em></h2>
      <div class="section-rule"></div>
    </div>
    <div class="awards-grid">
      <div class="award-card reveal">
        <div class="award-star">&#10022;</div>
        <div class="award-year">2025</div>
        <div class="award-name">Rollins College Departmental Service Excellence Award &mdash; Center for Leadership &amp; Community Engagement</div>
      </div>
      <div class="award-card reveal">
        <div class="award-star">&#10022;</div>
        <div class="award-year">2024</div>
        <div class="award-name">Blinn College Teaching Excellence Award Nominee</div>
      </div>
      <div class="award-card reveal">
        <div class="award-star">&#10022;</div>
        <div class="award-year">2020</div>
        <div class="award-name">Fulbright English Teaching Assistant &mdash; Vietnam (Alternate; cycle cancelled due to COVID-19)</div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-inner">
    <div class="section-header reveal" style="justify-content:center; margin-bottom:1.5rem;">
      <span class="section-num">08</span>
      <h2 class="section-title">Get in <em>Touch</em></h2>
    </div>
    <p class="contact-tagline reveal">Whether you're interested in teaching collaborations, research conversations, writing center work, or community engagement &mdash; I'd love to connect.</p>
    <div class="contact-cards reveal">
      <a href="mailto:Cailey.Cassity-Ness@ucf.edu" class="contact-card">
        <span class="contact-icon">&#9993;</span>
        <span class="contact-label">Email</span>
        <span class="contact-val">UCF Email</span>
      </a>
      <a href="CassityNess_CV.docx" class="contact-card" download>
        <span class="contact-icon">&#8659;</span>
        <span class="contact-label">Download</span>
        <span class="contact-val">Full CV</span>
      </a>
      <a href="https://github.com/ccassityness/CriticalMakingCV" class="contact-card" target="_blank" rel="noopener">
        <span class="contact-icon">&#8984;</span>
        <span class="contact-label">GitHub</span>
        <span class="contact-val">CV Repository</span>
      </a>
    </div>
  </div>
</section>

<footer>
  <p>&copy; 2026 Cailey Cassity-Ness &nbsp;&middot;&nbsp; PhD Candidate, Texts &amp; Technology, University of Central Florida &nbsp;&middot;&nbsp; <a href="CassityNess_CV.docx" download>Download CV</a></p>
</footer>

<script>
  const obs = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('in'), i * 70);
        obs.unobserve(e.target);
      }
    });
  }, { threshold: 0.08 });
  document.querySelectorAll('.reveal').forEach(el => obs.observe(el));

  const sectionEls = document.querySelectorAll('section[id]');
  const navAs = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll', () => {
    let cur = '';
    sectionEls.forEach(s => { if (scrollY >= s.offsetTop - 80) cur = s.id; });
    navAs.forEach(a => a.classList.toggle('active', a.getAttribute('href') === `#${cur}`));
  }, { passive: true });
</script>
</body>
</html>

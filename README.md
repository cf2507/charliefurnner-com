<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Charlie Furnner — Marketing & Operations</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Inter+Tight:wght@400;500;600;700;800;900&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --paper: #F5F2EC;
    --ink: #1A1A1A;
    --muted: #6F6B63;
    --line: #D9D4C8;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  html, body { overflow-x: hidden; }
  body {
    background: var(--paper);
    color: var(--ink);
    font-family: 'Inter Tight', sans-serif;
    -webkit-font-smoothing: antialiased;
    font-feature-settings: "ss01", "cv11";
  }
  a { color: inherit; text-decoration: none; }
  ::selection { background: var(--ink); color: var(--paper); }

  @keyframes fadeUp { from { opacity: 0; transform: translateY(32px); } to { opacity: 1; transform: translateY(0); } }
  @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

  /* ===== HEADER ===== */
  header {
    padding: 28px 32px;
    display: flex; justify-content: space-between; align-items: center;
    font-family: 'JetBrains Mono', monospace; font-size: 11px;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--muted);
  }
  header .logo { color: var(--ink); font-weight: 500; }
  header nav { display: flex; gap: 28px; }
  header nav a { transition: color 200ms; }
  header nav a:hover { color: var(--ink); }

  /* ===== HERO ===== */
  .hero {
    padding: 80px 32px 120px;
    position: relative;
  }
  .hero-meta {
    font-family: 'JetBrains Mono', monospace; font-size: 11px;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--muted); margin-bottom: 64px;
    display: flex; justify-content: space-between; flex-wrap: wrap; gap: 12px;
    animation: fadeIn 800ms ease both;
  }

  .hero h1 {
    font-family: 'Inter Tight', sans-serif;
    font-weight: 800;
    font-size: clamp(72px, 18vw, 240px);
    line-height: 0.86;
    letter-spacing: -0.055em;
    text-transform: none;
    color: var(--ink);
    animation: fadeUp 900ms cubic-bezier(.2,.7,.2,1) both;
  }
  .hero h1 .serif {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-weight: 400;
    letter-spacing: -0.025em;
  }

  .hero-tag {
    display: flex; justify-content: space-between; align-items: flex-end;
    flex-wrap: wrap; gap: 32px;
    margin-top: 80px; padding-top: 32px;
    border-top: 1px solid var(--line);
  }
  .hero-tag p {
    font-size: clamp(20px, 2.6vw, 28px);
    line-height: 1.25; font-weight: 500;
    max-width: 720px; color: var(--ink);
    animation: fadeUp 900ms cubic-bezier(.2,.7,.2,1) 300ms both;
  }
  .hero-tag .status {
    font-family: 'JetBrains Mono', monospace; font-size: 11px;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--muted); text-align: right;
    animation: fadeUp 900ms cubic-bezier(.2,.7,.2,1) 500ms both;
  }
  .hero-tag .status .available {
    display: block; color: var(--ink); margin-top: 4px; font-weight: 500;
  }

  /* ===== SECTION LABELS ===== */
  .sec-label {
    font-family: 'JetBrains Mono', monospace; font-size: 11px;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--muted); margin-bottom: 32px;
    display: flex; justify-content: space-between; align-items: baseline;
    padding-bottom: 16px; border-bottom: 1px solid var(--line);
  }

  /* ===== WORK ===== */
  section.work {
    padding: 80px 32px 40px;
  }
  .project {
    padding: 56px 0;
    border-top: 1px solid var(--line);
    display: grid;
    grid-template-columns: 1fr;
    gap: 24px;
    position: relative;
    transition: padding 400ms cubic-bezier(.2,.7,.2,1);
  }
  .project:last-child { border-bottom: 1px solid var(--line); }

  .project .idx {
    font-family: 'JetBrains Mono', monospace; font-size: 11px;
    color: var(--muted); text-transform: uppercase; letter-spacing: 0.12em;
  }
  .project h2 {
    font-family: 'Inter Tight', sans-serif;
    font-weight: 700;
    font-size: clamp(56px, 12vw, 140px);
    line-height: 0.88;
    letter-spacing: -0.04em;
    color: var(--ink);
    transition: transform 500ms cubic-bezier(.2,.7,.2,1);
  }
  .project:hover h2 { transform: translateX(12px); }

  .project .role {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: clamp(20px, 2.5vw, 28px);
    color: var(--muted);
    letter-spacing: -0.01em;
  }
  .project .desc {
    font-size: clamp(16px, 1.6vw, 19px);
    line-height: 1.55;
    color: var(--ink);
    max-width: 720px;
    margin-top: 8px;
  }
  .project .meta-row {
    display: flex; flex-wrap: wrap; gap: 20px;
    margin-top: 16px;
    font-family: 'JetBrains Mono', monospace; font-size: 11px;
    text-transform: uppercase; letter-spacing: 0.1em;
    color: var(--muted);
  }
  .project .meta-row span {
    display: flex; align-items: center; gap: 8px;
  }
  .project .meta-row span::before {
    content: ""; width: 4px; height: 4px; background: var(--muted);
    border-radius: 50%; display: inline-block;
  }
  .project .meta-row span:first-child::before { display: none; }

  .project .link {
    align-self: start;
    font-family: 'JetBrains Mono', monospace; font-size: 11px;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--ink);
    border-bottom: 1px solid var(--ink);
    padding-bottom: 2px;
    margin-top: 8px;
    transition: padding-right 300ms;
  }
  .project:hover .link { padding-right: 8px; }

  /* Full-bleed editorial — Smokin' Jack's feature */
  .editorial {
    /* Break out of the section's horizontal padding */
    margin-left: -32px;
    margin-right: -32px;
    margin-top: 48px;
    position: relative;
  }

  /* Lead image: full-bleed, with project name slashing across the bottom edge */
  .editorial-lead {
    position: relative;
    background: var(--ink);
    overflow: hidden;
  }
  .editorial-lead img {
    display: block;
    width: 100%;
    height: auto;
    opacity: 0;
    transform: scale(1.04);
    transition: opacity 1200ms cubic-bezier(.2,.7,.2,1), transform 1800ms cubic-bezier(.2,.7,.2,1);
  }
  .editorial-lead.shown img {
    opacity: 1;
    transform: scale(1);
  }

  /* Editorial heading that sits above full-bleed lead image */
  .editorial-heading {
    padding: 0 0 24px;
  }
  .editorial-heading h2 {
    font-family: 'Inter Tight', sans-serif;
    font-weight: 700;
    font-size: clamp(56px, 12vw, 140px);
    line-height: 0.88;
    letter-spacing: -0.04em;
    color: var(--ink);
  }
  .editorial-heading h2 .serif {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-weight: 400;
    letter-spacing: -0.025em;
  }
  .editorial-heading .role {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: clamp(20px, 2.5vw, 28px);
    color: var(--muted);
    letter-spacing: -0.01em;
    margin-top: 8px;
  }

  /* Tipsy Turtle paired layout — portrait menu next to copy */
  .paired {
    margin-top: 32px;
    display: grid;
    grid-template-columns: 1fr;
    gap: 32px;
  }
  @media (min-width: 880px) {
    .paired {
      grid-template-columns: minmax(0, 5fr) minmax(0, 4fr);
      gap: 48px;
      align-items: start;
    }
  }
  .paired-image {
    position: relative;
    overflow: hidden;
    background: var(--ink);
    border: 1px solid var(--line);
  }
  .paired-image img {
    display: block;
    width: 100%;
    height: auto;
    opacity: 0;
    transform: scale(1.03);
    transition: opacity 1000ms cubic-bezier(.2,.7,.2,1), transform 1500ms cubic-bezier(.2,.7,.2,1);
  }
  .paired-image.shown img { opacity: 1; transform: scale(1); }
  .paired-image .lbl {
    position: absolute; top: 14px; left: 14px;
    background: var(--paper);
    padding: 6px 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--ink);
    border: 1px solid var(--ink);
  }
  .paired-body {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }
  .paired-body .caption {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: clamp(18px, 2vw, 22px);
    line-height: 1.3;
    color: var(--ink);
    letter-spacing: -0.005em;
  }
  .paired-body .caption .mark {
    display: inline;
    border-bottom: 1.5px solid var(--ink);
    padding-bottom: 1px;
  }
  @media (min-width: 880px) {
    .paired-body { padding-top: 24px; }
  }

  /* Caption strip */
  .editorial-cap {
    padding: 20px 32px 8px;
    display: flex; justify-content: space-between; gap: 24px; flex-wrap: wrap;
    font-family: 'JetBrains Mono', monospace; font-size: 10px;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--muted);
    border-bottom: 1px solid var(--line);
  }
  .editorial-cap .num { color: var(--muted); }
  .editorial-cap .info { color: var(--muted); }

  /* Follow-up pieces — broken asymmetric grid, no uniform container */
  .editorial-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 48px;
    padding: 48px 32px 0;
  }
  @media (min-width: 760px) {
    .editorial-grid {
      grid-template-columns: repeat(12, 1fr);
      gap: 8px 16px;
    }
  }
  .ed-piece {
    position: relative;
    display: flex; flex-direction: column; gap: 12px;
  }
  .ed-piece figure { margin: 0; position: relative; overflow: hidden; background: var(--ink); }
  .ed-piece img {
    display: block; width: 100%; height: auto;
    transform: scale(1.05);
    opacity: 0;
    transition: opacity 900ms cubic-bezier(.2,.7,.2,1), transform 1400ms cubic-bezier(.2,.7,.2,1);
  }
  .ed-piece.shown img { opacity: 1; transform: scale(1); }

  .ed-piece .lbl {
    font-family: 'JetBrains Mono', monospace; font-size: 10px;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--muted);
    display: flex; justify-content: space-between; gap: 16px;
  }
  .ed-piece .desc {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: clamp(16px, 1.8vw, 20px);
    line-height: 1.25;
    letter-spacing: -0.005em;
    color: var(--ink);
    max-width: 480px;
  }

  /* Asymmetric placement on desktop */
  @media (min-width: 760px) {
    .ed-piece.a { grid-column: 2 / span 7; }  /* wide, left-weighted */
    .ed-piece.b { grid-column: 7 / span 5; margin-top: 80px; }  /* narrower, offset down, overlaps a */
    .ed-piece.c { grid-column: 1 / span 4; margin-top: -40px; }  /* square post, pulled up */
  }

  /* Closing editorial line */
  .editorial-close {
    padding: 64px 32px 16px;
    max-width: 760px;
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: clamp(22px, 3vw, 34px);
    line-height: 1.25;
    letter-spacing: -0.01em;
    color: var(--ink);
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 900ms cubic-bezier(.2,.7,.2,1), transform 900ms cubic-bezier(.2,.7,.2,1);
  }
  .editorial-close.shown { opacity: 1; transform: translateY(0); }
  .editorial-close .mark {
    display: inline-block;
    border-bottom: 2px solid var(--ink);
    padding-bottom: 2px;
  }

  /* ===== ABOUT ===== */
  section.about {
    padding: 120px 32px;
    border-top: 1px solid var(--line);
  }
  .about-grid {
    display: grid; grid-template-columns: 1fr; gap: 40px;
  }
  @media (min-width: 860px) {
    .about-grid { grid-template-columns: 1fr 1.4fr; gap: 80px; }
  }
  .about h2 {
    font-family: 'Inter Tight', sans-serif;
    font-weight: 700;
    font-size: clamp(44px, 6vw, 88px);
    line-height: 0.9;
    letter-spacing: -0.04em;
    color: var(--ink);
  }
  .about h2 .serif {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-weight: 400;
    letter-spacing: -0.025em;
  }
  .about-body {
    display: flex; flex-direction: column; gap: 20px;
    font-size: clamp(16px, 1.5vw, 18px);
    line-height: 1.6;
    color: var(--ink);
    max-width: 580px;
  }
  .about-body b { font-weight: 600; }

  /* ===== FACTS ===== */
  section.facts {
    padding: 40px 32px 120px;
  }
  .facts-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 1px;
    background: var(--line);
    border: 1px solid var(--line);
  }
  @media (min-width: 720px) {
    .facts-grid { grid-template-columns: repeat(4, 1fr); }
  }
  .fact {
    background: var(--paper);
    padding: 32px 24px;
    display: flex; flex-direction: column; gap: 12px;
  }
  .fact .num {
    font-family: 'Inter Tight', sans-serif;
    font-weight: 700;
    font-size: clamp(36px, 5vw, 56px);
    line-height: 0.9;
    letter-spacing: -0.04em;
  }
  .fact .lbl {
    font-family: 'JetBrains Mono', monospace; font-size: 10px;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--muted);
    line-height: 1.5;
  }

  /* ===== CONTACT ===== */
  section.contact {
    padding: 120px 32px;
    border-top: 1px solid var(--line);
  }
  .contact h2 {
    font-family: 'Inter Tight', sans-serif;
    font-weight: 700;
    font-size: clamp(56px, 11vw, 160px);
    line-height: 0.88;
    letter-spacing: -0.045em;
    margin-bottom: 48px;
  }
  .contact h2 .serif {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-weight: 400;
  }

  .contact .email {
    display: inline-block;
    font-family: 'Inter Tight', sans-serif;
    font-weight: 600;
    font-size: clamp(22px, 3vw, 36px);
    letter-spacing: -0.02em;
    padding-bottom: 6px;
    border-bottom: 1px solid var(--ink);
    color: var(--ink);
    transition: padding-right 300ms;
    word-break: break-all;
  }
  .contact .email:hover { padding-right: 12px; }

  .contact .links {
    display: flex; flex-wrap: wrap; gap: 24px;
    margin-top: 56px; padding-top: 24px;
    border-top: 1px solid var(--line);
    font-family: 'JetBrains Mono', monospace; font-size: 11px;
    text-transform: uppercase; letter-spacing: 0.12em;
  }
  .contact .links a {
    color: var(--muted);
    transition: color 200ms;
  }
  .contact .links a:hover { color: var(--ink); }

  /* ===== FOOTER ===== */
  footer {
    padding: 32px; border-top: 1px solid var(--line);
    display: flex; justify-content: space-between; flex-wrap: wrap; gap: 16px;
    font-family: 'JetBrains Mono', monospace; font-size: 10px;
    text-transform: uppercase; letter-spacing: 0.12em;
    color: var(--muted);
  }

  /* ===== REVEAL ===== */
  .reveal { opacity: 0; transform: translateY(32px); transition: opacity 800ms cubic-bezier(.2,.7,.2,1), transform 800ms cubic-bezier(.2,.7,.2,1); }
  .reveal.shown { opacity: 1; transform: translateY(0); }
</style>
</head>
<body>

<header>
  <div class="logo">Charlie Furnner</div>
  <nav>
    <a href="#work">Work</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<section class="hero">
  <div class="hero-meta">
    <span>Milwaukee, WI</span>
    <span>Portfolio / 2026</span>
  </div>

  <h1>
    Charlie<br>
    <span class="serif">Furnner.</span>
  </h1>

  <div class="hero-tag">
    <p>Marketing and operations manager at Smokin' Jack's BBQ. Founder of LocalPost, a marketing software product for local businesses.</p>
    <div class="status">
      <div>Status</div>
      <div class="available">Available for select work</div>
    </div>
  </div>
</section>

<section class="work" id="work">
  <div class="sec-label reveal">
    <span>Selected Work</span>
    <span>04</span>
  </div>

  <article class="project reveal">
    <div class="idx">01 — Restaurant</div>
    <div class="editorial-heading">
      <h2>Smokin' <span class="serif">Jack's.</span></h2>
      <div class="role">Marketing &amp; Operations Manager · Milwaukee, WI · Nov 2025—</div>
    </div>
      <div class="editorial">
      <div class="editorial-lead" data-reveal>
        <img src="assets/sj-1.png" alt="Smokin' Jack's featured menu graphic">
      </div>

      <div class="editorial-cap">
        <span class="num">Fig. 01 / 04</span>
        <span class="info">American Family Field booth · Section 206</span>
      </div>

      <p class="desc" style="padding: 32px 32px 0; max-width: 720px;">Running social, creative, partnerships, and day-to-day operations. Grew TikTok from 200 to 780 followers with multiple videos past 20,000 views. Designed in-house creative including an American Family Field concession stand rollout and a March Madness bracket activation. Built custom internal tools, including a receipt scanner, to automate back-of-house work.</p>

      <div class="meta-row" style="padding: 16px 32px 0;">
        <span>Social</span>
        <span>Brand</span>
        <span>Operations</span>
        <span>Internal tools</span>
      </div>

      <div class="editorial-grid">
        <div class="ed-piece a" data-reveal>
          <figure><img src="assets/sj-2.png" alt="Smokin' Jack's We Cater booth graphic with QR codes"></figure>
          <div class="lbl"><span>Fig. 02</span><span>Catering CTA</span></div>
          <div class="desc">Booth graphic driving scans to the catering menu, ordering, and food-truck bookings — designed for a high-traffic sports venue.</div>
        </div>

        <div class="ed-piece b" data-reveal>
          <figure><img src="assets/sj-3.png" alt="Three Smokin' Jack's locations — the OG, Flagship, and Downtown"></figure>
          <div class="lbl"><span>Fig. 03</span><span>Locations</span></div>
          <div class="desc">Three Milwaukee locations. One brand system — photography, type hierarchy, and the checkered motif running through every piece.</div>
        </div>

        <div class="ed-piece c" data-reveal>
          <figure><img src="assets/sj-4.png" alt="Patio Season coming soon social post"></figure>
          <div class="lbl"><span>Fig. 04</span><span>Seasonal social</span></div>
          <div class="desc">Seasonal social campaign teaser — same identity system, adapted for a square format and a scroll-stopping feed moment.</div>
        </div>
      </div>

      <p class="editorial-close" data-reveal>
        One brand. Three locations. <span class="mark">Every piece designed in-house.</span>
      </p>
    </div>
  </article>

  <article class="project reveal">
    <div class="idx">02 — Software</div>
    <h2>LocalPost</h2>
    <div class="role">Founder · 2025—</div>
    <p class="desc">Originally built as an internal marketing tool at Smokin' Jack's BBQ, LocalPost is now expanding as a marketing software product for local businesses. It automates social media campaign generation and works as a centralized marketing calendar. Currently in beta with live customers. AI-powered image generation shipping next.</p>
    <div class="meta-row">
      <span>Product</span>
      <span>Design</span>
      <span>Go-to-market</span>
      <span>In beta</span>
    </div>
    <a class="link" href="https://trylocalpost.com" target="_blank" rel="noopener">Visit trylocalpost.com →</a>
  </article>

  <article class="project reveal">
    <div class="idx">03 — Freelance</div>
    <h2>Tipsy Turtle</h2>
    <div class="role">Marketing &amp; Design · Muskego, WI · Apr 2026—</div>
    <p class="desc">Designing print menus for a patio and grill in Muskego. Onboarded as an early LocalPost client, with scope expanding into ongoing social media management.</p>
    <div class="meta-row">
      <span>Menu design</span>
      <span>Print</span>
      <span>Social</span>
    </div>

    <div class="paired">
      <div class="paired-image" data-reveal>
        <img src="assets/tt-1.png" alt="Tipsy Turtle Taco Tuesday menu — weekly specials print piece">
      </div>
      <div class="paired-body">
        <p class="caption">A weekly specials menu for a family-owned patio grill in Muskego. <span class="mark">A different brand voice than Smokin' Jack's — warmer, quieter, built around the client's existing identity.</span></p>
        <p class="caption" style="font-style: normal; font-family: 'Inter Tight', sans-serif; font-size: clamp(15px, 1.5vw, 17px); line-height: 1.55; color: var(--ink);">
          Designed with a clear price column, "Most Popular" and "Local Favorite" tags to guide ordering, and a star system marking dishes that don't include rice &amp; beans — footnoted at the bottom instead of repeated in every line.
        </p>
      </div>
    </div>
  </article>

  <article class="project reveal">
    <div class="idx">04 — Retail</div>
    <h2>Trendcheck Vintage</h2>
    <div class="role">Founder · 2023 – 2024</div>
    <p class="desc">Vintage clothing operation I founded in high school. Scaled to $25,000 in revenue across Depop and in-person flea markets. Built the Depop storefront to 2,000+ followers and earned verified Top Seller status through consistent listings, product photography, and customer service.</p>
    <div class="meta-row">
      <span>E-commerce</span>
      <span>Photography</span>
      <span>Retail</span>
    </div>
  </article>
</section>

<section class="about" id="about">
  <div class="sec-label reveal">
    <span>About</span>
    <span>01</span>
  </div>

  <div class="about-grid">
    <div class="reveal">
      <h2>I do marketing<br>and build the<br><span class="serif">tools for it.</span></h2>
    </div>
    <div class="about-body reveal">
      <p>Based in Milwaukee, Wisconsin. I run marketing and operations at <b>Smokin' Jack's BBQ</b>, where the work spans social, creative, partnerships, and any back-of-house system worth automating.</p>
      <p>On the side, I'm building <b>LocalPost</b> — a marketing software product that started as an internal tool at Smokin' Jack's and is now opening up to other local businesses that don't have a full marketing team.</p>
      <p>Before all of this, I ran <b>Trendcheck Vintage</b> on Depop and at flea markets during high school. That's where I learned the fundamentals: good product, clear story, consistent effort.</p>
      <p>I work best with operators who care about the details and want one person who can actually do the work — not pitch it.</p>
    </div>
  </div>
</section>

<section class="facts">
  <div class="facts-grid reveal">
    <div class="fact">
      <div class="num">4&times;</div>
      <div class="lbl">TikTok growth<br>Smokin' Jack's BBQ</div>
    </div>
    <div class="fact">
      <div class="num">20K+</div>
      <div class="lbl">Top video views<br>Organic / 2025</div>
    </div>
    <div class="fact">
      <div class="num">$25K</div>
      <div class="lbl">Revenue generated<br>Trendcheck Vintage</div>
    </div>
    <div class="fact">
      <div class="num">2K+</div>
      <div class="lbl">Followers built<br>Depop / Trendcheck</div>
    </div>
  </div>
</section>

<section class="contact" id="contact">
  <div class="sec-label reveal">
    <span>Contact</span>
    <span>Available</span>
  </div>

  <h2 class="reveal">
    Get in<br>
    <span class="serif">touch.</span>
  </h2>

  <a class="email reveal" href="mailto:charliefurnner@gmail.com">charliefurnner@gmail.com →</a>

  <div class="links reveal">
    <a href="https://www.linkedin.com/in/charlie-furnner-454242315" target="_blank" rel="noopener">LinkedIn</a>
    <a href="https://trylocalpost.com" target="_blank" rel="noopener">LocalPost</a>
    <a href="resume.pdf" download="Charlie_Furnner_Resume.pdf">Download Resume</a>
  </div>
</section>

<footer>
  <span>© Charlie Furnner, 2026</span>
  <span>Milwaukee, WI</span>
</footer>

<script>
  const io = new IntersectionObserver((entries) => {
    entries.forEach((e) => {
      if (e.isIntersecting) { e.target.classList.add("shown"); io.unobserve(e.target); }
    });
  }, { threshold: 0.12, rootMargin: "0px 0px -60px 0px" });
  document.querySelectorAll(".reveal").forEach((el) => io.observe(el));

  /* Editorial reveal — staggered, slightly earlier trigger than .reveal */
  const edIo = new IntersectionObserver((entries) => {
    entries.forEach((e) => {
      if (e.isIntersecting) { e.target.classList.add("shown"); edIo.unobserve(e.target); }
    });
  }, { threshold: 0.2, rootMargin: "0px 0px -120px 0px" });
  document.querySelectorAll("[data-reveal]").forEach((el) => edIo.observe(el));
</script>
</body>
</html>

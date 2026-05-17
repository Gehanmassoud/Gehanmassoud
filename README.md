[index.html](https://github.com/user-attachments/files/27918204/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Gehan Massoud — Azure Data & AI Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500;600&family=DM+Mono&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

:root {
  --ink: #0a0f1e;
  --ink2: #1a2035;
  --blue: #0078D4;
  --blue-l: #50a8f5;
  --teal: #00B4D8;
  --gold: #FFB900;
  --green: #00c896;
  --white: #ffffff;
  --off: #f0f4f9;
  --muted: #8090a8;
  --border: rgba(255,255,255,0.08);
}

html { scroll-behavior: smooth; }

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--ink);
  color: var(--white);
  font-size: 15px;
  line-height: 1.7;
  overflow-x: hidden;
}

/* ── NOISE TEXTURE OVERLAY ── */
body::before {
  content: '';
  position: fixed; inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
  pointer-events: none; z-index: 0; opacity: .4;
}

/* ── NAV ── */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 100;
  display: flex; align-items: center; justify-content: space-between;
  padding: 1rem 3rem;
  background: rgba(10,15,30,0.85);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid var(--border);
}

.nav-name {
  font-family: 'Fraunces', serif;
  font-size: 18px; font-weight: 700;
  color: var(--white);
  letter-spacing: -.01em;
}

.nav-links {
  display: flex; gap: 2rem;
  list-style: none;
}

.nav-links a {
  color: var(--muted); font-size: 13px; text-decoration: none;
  transition: color .2s;
}

.nav-links a:hover { color: var(--white); }

.nav-cta {
  background: var(--blue); color: var(--white);
  font-size: 12.5px; font-weight: 600;
  padding: 8px 20px; border-radius: 6px;
  text-decoration: none; transition: opacity .2s;
}

.nav-cta:hover { opacity: .85; }

/* ── HERO ── */
.hero {
  min-height: 100vh;
  display: flex; flex-direction: column;
  justify-content: center; align-items: flex-start;
  padding: 8rem 3rem 5rem;
  position: relative;
}

.hero-grid-bg {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(0,120,212,0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,120,212,0.05) 1px, transparent 1px);
  background-size: 60px 60px;
  mask-image: radial-gradient(ellipse 80% 70% at 60% 40%, black 30%, transparent 100%);
}

.hero-glow {
  position: absolute;
  width: 600px; height: 600px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(0,120,212,0.15) 0%, transparent 70%);
  top: 10%; right: -100px;
  pointer-events: none;
}

.hero-glow2 {
  position: absolute;
  width: 300px; height: 300px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(0,180,216,0.1) 0%, transparent 70%);
  bottom: 15%; left: 40%;
  pointer-events: none;
}

.hero-eyebrow {
  display: inline-flex; align-items: center; gap: 8px;
  font-size: 11px; font-weight: 600; letter-spacing: .12em;
  color: var(--blue-l);
  background: rgba(0,120,212,0.12);
  border: 1px solid rgba(0,120,212,0.25);
  padding: 6px 14px; border-radius: 20px;
  margin-bottom: 1.5rem;
}

.hero-eyebrow span { width: 6px; height: 6px; border-radius: 50%; background: var(--blue-l); }

.hero h1 {
  font-family: 'Fraunces', serif;
  font-size: clamp(3rem, 6vw, 5.5rem);
  font-weight: 900; line-height: 1.05;
  letter-spacing: -.03em;
  margin-bottom: 1.5rem;
  max-width: 700px;
}

.hero h1 .accent { color: var(--blue-l); }
.hero h1 .muted-word { color: var(--muted); font-weight: 400; font-style: italic; }

.hero-sub {
  font-size: 17px; color: var(--muted);
  max-width: 560px; line-height: 1.7;
  margin-bottom: 2.5rem;
}

.hero-sub strong { color: rgba(255,255,255,0.8); font-weight: 500; }

.hero-actions {
  display: flex; gap: 12px; flex-wrap: wrap;
  margin-bottom: 4rem;
}

.btn-primary {
  display: inline-flex; align-items: center; gap: 8px;
  background: var(--blue); color: white;
  font-size: 14px; font-weight: 600;
  padding: 12px 28px; border-radius: 8px;
  text-decoration: none; transition: all .2s;
}

.btn-primary:hover { background: #0063b1; transform: translateY(-1px); }

.btn-ghost {
  display: inline-flex; align-items: center; gap: 8px;
  background: transparent; color: rgba(255,255,255,0.7);
  font-size: 14px; font-weight: 500;
  padding: 12px 28px; border-radius: 8px;
  border: 1px solid rgba(255,255,255,0.15);
  text-decoration: none; transition: all .2s;
}

.btn-ghost:hover { border-color: rgba(255,255,255,0.3); color: white; }

.stats-row {
  display: flex; gap: 3rem; flex-wrap: wrap;
}

.stat { }
.stat-num {
  font-family: 'Fraunces', serif;
  font-size: 2.2rem; font-weight: 900;
  color: white; line-height: 1;
}

.stat-num .unit { font-size: 1.2rem; color: var(--blue-l); }

.stat-label {
  font-size: 12px; color: var(--muted);
  margin-top: 4px; letter-spacing: .02em;
}

/* ── SECTION WRAPPER ── */
section { padding: 6rem 3rem; max-width: 1100px; margin: 0 auto; }

.section-tag {
  display: inline-block;
  font-size: 10px; font-weight: 700; letter-spacing: .14em;
  color: var(--blue-l);
  margin-bottom: 1rem;
}

.section-heading {
  font-family: 'Fraunces', serif;
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 900; line-height: 1.1;
  letter-spacing: -.02em;
  margin-bottom: 1rem;
}

.section-sub {
  font-size: 16px; color: var(--muted);
  max-width: 540px; line-height: 1.7;
  margin-bottom: 3rem;
}

/* ── DIVIDER LINE ── */
.divider {
  width: 100%; height: 1px;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.06), transparent);
  margin: 0 3rem;
  max-width: calc(1100px - 6rem);
}

/* ── MICROSOFT SIGNAL BANNER ── */
.ms-banner {
  background: rgba(0,120,212,0.08);
  border: 1px solid rgba(0,120,212,0.2);
  border-radius: 12px;
  padding: 1.25rem 1.75rem;
  margin-bottom: 2.5rem;
  display: flex; gap: 14px; align-items: flex-start;
}

.ms-banner-icon { font-size: 20px; flex-shrink: 0; margin-top: 2px; }

.ms-banner-text { font-size: 13.5px; color: rgba(255,255,255,0.75); line-height: 1.65; }
.ms-banner-text strong { color: var(--blue-l); font-weight: 500; }

/* ── PROJECT CARDS ── */
.projects-grid { display: grid; gap: 1.5rem; }

.proj-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 16px;
  overflow: hidden;
  transition: border-color .25s, transform .25s;
}

.proj-card:hover {
  border-color: rgba(0,120,212,0.35);
  transform: translateY(-2px);
}

.proj-card-inner {
  display: grid; grid-template-columns: 1fr 340px;
}

.proj-left { padding: 2rem 2rem 2rem 2.5rem; }
.proj-right {
  padding: 2rem;
  border-left: 1px solid rgba(255,255,255,0.06);
  display: flex; flex-direction: column; gap: 1.5rem;
}

.proj-num-badge {
  display: inline-flex; align-items: center; gap: 8px;
  font-size: 11px; font-weight: 700; letter-spacing: .1em;
  margin-bottom: 1rem;
}

.proj-num {
  width: 28px; height: 28px; border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 12px; font-weight: 700;
}

.p1 .proj-num { background: rgba(0,120,212,0.2); color: var(--blue-l); }
.p2 .proj-num { background: rgba(0,180,216,0.2); color: var(--teal); }
.p3 .proj-num { background: rgba(0,200,150,0.2); color: var(--green); }
.p4 .proj-num { background: rgba(255,185,0,0.2); color: var(--gold); }

.proj-num-text { color: var(--muted); font-size: 11px; }

.proj-title {
  font-family: 'Fraunces', serif;
  font-size: 1.5rem; font-weight: 700;
  line-height: 1.2; letter-spacing: -.02em;
  margin-bottom: .75rem;
}

.proj-problem {
  font-size: 13px; color: var(--muted);
  line-height: 1.7; margin-bottom: 1.25rem;
}

.ms-signal-box {
  background: rgba(255,185,0,0.06);
  border: 1px solid rgba(255,185,0,0.15);
  border-radius: 8px;
  padding: 10px 14px;
  font-size: 12.5px;
  color: rgba(255,255,255,0.6);
  line-height: 1.6;
  margin-bottom: 1.25rem;
}

.ms-signal-box strong { color: var(--gold); font-weight: 500; }

.badge-row { display: flex; flex-wrap: wrap; gap: 6px; }

.badge {
  font-size: 11px; font-weight: 500;
  padding: 4px 10px; border-radius: 20px;
  font-family: 'DM Mono', monospace;
}

.p1 .badge { background: rgba(0,120,212,0.15); color: #60a5fa; border: 1px solid rgba(0,120,212,0.2); }
.p2 .badge { background: rgba(0,180,216,0.12); color: #67e8f9; border: 1px solid rgba(0,180,216,0.2); }
.p3 .badge { background: rgba(0,200,150,0.12); color: #6ee7b7; border: 1px solid rgba(0,200,150,0.2); }
.p4 .badge { background: rgba(255,185,0,0.12); color: #fcd34d; border: 1px solid rgba(255,185,0,0.2); }

.proj-right-label {
  font-size: 10px; font-weight: 700; letter-spacing: .1em;
  color: var(--muted); margin-bottom: 8px;
}

.metric-list { display: flex; flex-direction: column; gap: 6px; }

.metric-item {
  display: flex; align-items: center; gap: 10px;
  font-size: 13px;
}

.metric-dot {
  width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0;
}

.p1 .metric-dot { background: var(--blue-l); }
.p2 .metric-dot { background: var(--teal); }
.p3 .metric-dot { background: var(--green); }
.p4 .metric-dot { background: var(--gold); }

.metric-item span { color: rgba(255,255,255,0.75); }

.proj-gh-link {
  display: inline-flex; align-items: center; gap: 8px;
  font-size: 12.5px; font-weight: 500;
  color: var(--muted);
  font-family: 'DM Mono', monospace;
  padding: 8px 0;
  text-decoration: none;
  border-top: 1px solid rgba(255,255,255,0.06);
  margin-top: auto;
  transition: color .2s;
}

.proj-gh-link:hover { color: white; }

/* ── HOW I SOLVED IT ── */
.solved-block {
  background: rgba(0,120,212,0.06);
  border: 1px solid rgba(0,120,212,0.15);
  border-radius: 10px;
  padding: 1rem 1.25rem;
}

.solved-label {
  font-size: 10px; font-weight: 700; letter-spacing: .1em;
  color: var(--blue-l); margin-bottom: 8px;
}

.solved-text {
  font-size: 13px; color: rgba(255,255,255,0.7); line-height: 1.7;
}

/* ── EXPERIENCE STRIP ── */
.exp-strip {
  padding: 5rem 3rem;
  background: rgba(255,255,255,0.02);
  border-top: 1px solid rgba(255,255,255,0.05);
  border-bottom: 1px solid rgba(255,255,255,0.05);
}

.exp-strip-inner { max-width: 1100px; margin: 0 auto; }

.exp-grid {
  display: grid; grid-template-columns: repeat(4, 1fr);
  gap: 2rem; margin-top: 2.5rem;
}

.exp-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.06);
  border-radius: 12px; padding: 1.5rem;
}

.exp-company {
  font-size: 12px; font-weight: 600; color: var(--blue-l);
  letter-spacing: .04em; margin-bottom: 4px;
}

.exp-title {
  font-size: 13.5px; font-weight: 500; color: white;
  line-height: 1.3; margin-bottom: 8px;
}

.exp-dates { font-size: 11px; color: var(--muted); }

.exp-metrics { margin-top: 12px; display: flex; flex-direction: column; gap: 4px; }

.exp-metric { font-size: 12px; color: rgba(255,255,255,0.55); }
.exp-metric strong { color: var(--green); font-weight: 600; }

/* ── CERTS SECTION ── */
.certs-grid {
  display: grid; grid-template-columns: repeat(3, 1fr);
  gap: 12px; margin-top: 2rem;
}

.cert-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 10px; padding: 1rem 1.25rem;
  transition: border-color .2s;
}

.cert-card:hover { border-color: rgba(0,120,212,0.3); }

.cert-card.inprogress { border-color: rgba(0,120,212,0.25); background: rgba(0,120,212,0.06); }

.cert-status {
  font-size: 10px; font-weight: 700; letter-spacing: .1em;
  margin-bottom: 6px;
}

.cert-card.inprogress .cert-status { color: var(--blue-l); }
.cert-card:not(.inprogress) .cert-status { color: var(--green); }

.cert-name { font-size: 13.5px; font-weight: 500; color: white; line-height: 1.3; margin-bottom: 4px; }
.cert-issuer { font-size: 12px; color: var(--muted); }

/* ── STAND OUT SECTION ── */
.standout-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 2rem; }

.standout-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 14px; padding: 1.75rem;
}

.standout-num {
  font-family: 'Fraunces', serif;
  font-size: 2.5rem; font-weight: 900;
  line-height: 1; margin-bottom: .5rem;
}

.standout-card:nth-child(1) .standout-num { color: var(--blue-l); }
.standout-card:nth-child(2) .standout-num { color: var(--teal); }
.standout-card:nth-child(3) .standout-num { color: var(--green); }
.standout-card:nth-child(4) .standout-num { color: var(--gold); }

.standout-title { font-size: 15px; font-weight: 600; color: white; margin-bottom: 8px; }
.standout-text { font-size: 13px; color: var(--muted); line-height: 1.7; }

/* ── FOOTER CTA ── */
.footer-cta {
  text-align: center;
  padding: 6rem 3rem;
  background: rgba(0,120,212,0.06);
  border-top: 1px solid rgba(0,120,212,0.15);
}

.footer-cta h2 {
  font-family: 'Fraunces', serif;
  font-size: clamp(2rem, 4vw, 3.2rem);
  font-weight: 900; letter-spacing: -.02em;
  margin-bottom: 1rem;
}

.footer-cta p { font-size: 16px; color: var(--muted); margin-bottom: 2.5rem; max-width: 480px; margin-left: auto; margin-right: auto; }

.contact-row { display: flex; justify-content: center; gap: 12px; flex-wrap: wrap; }

.contact-pill {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(255,255,255,0.05); border: 1px solid rgba(255,255,255,0.1);
  color: rgba(255,255,255,0.75); font-size: 13.5px;
  padding: 10px 20px; border-radius: 8px; text-decoration: none;
  transition: all .2s;
}

.contact-pill:hover { background: rgba(255,255,255,0.08); color: white; }

/* ── FADE-IN ANIMATION ── */
.fade-up {
  opacity: 0; transform: translateY(24px);
  transition: opacity .6s ease, transform .6s ease;
}

.fade-up.visible { opacity: 1; transform: translateY(0); }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-name">Gehan Massoud</div>
  <ul class="nav-links">
    <li><a href="#projects">Projects</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#certifications">Certifications</a></li>
  </ul>
  <a class="nav-cta" href="mailto:gehan.massoud2020@gmail.com">Contact Me</a>
</nav>

<!-- HERO -->
<div class="hero" id="home">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>

  <div class="hero-eyebrow"><span></span>MICROSOFT AZURE  ·  AI & DATA PLATFORM  ·  CLOUD SOLUTION ARCHITECT</div>

  <h1>
    Built the solutions<br>
    Microsoft customers<br>
    <span class="muted-word">need</span> <span class="accent">right now.</span>
  </h1>

  <p class="hero-sub">
    <strong>19+ years</strong> delivering AI-ready, well-architected Azure data platforms.
    Four production-grade PoC projects on <strong>Microsoft Fabric, Databricks, Cosmos DB,</strong>
    and <strong>Azure Purview</strong> — targeting the exact problems announced at FabCon 2026.
  </p>

  <div class="hero-actions">
    <a class="btn-primary" href="#projects">View Projects ↓</a>
    <a class="btn-ghost" href="https://github.com/Gehanmassoud" target="_blank">GitHub →</a>
    <a class="btn-ghost" href="https://linkedin.com/in/gehanmassoud" target="_blank">LinkedIn →</a>
  </div>

  <div class="stats-row">
    <div class="stat">
      <div class="stat-num">19<span class="unit">+</span></div>
      <div class="stat-label">Years experience</div>
    </div>
    <div class="stat">
      <div class="stat-num">300<span class="unit">+</span></div>
      <div class="stat-label">Databases architected</div>
    </div>
    <div class="stat">
      <div class="stat-num">1M<span class="unit">+</span></div>
      <div class="stat-label">Users served</div>
    </div>
    <div class="stat">
      <div class="stat-num">54</div>
      <div class="stat-label">Enterprise accounts</div>
    </div>
    <div class="stat">
      <div class="stat-num">4</div>
      <div class="stat-label">Live PoC projects</div>
    </div>
  </div>
</div>

<!-- PROJECTS -->
<div class="divider"></div>
<section id="projects">
  <div class="section-tag fade-up">GITHUB PORTFOLIO</div>
  <h2 class="section-heading fade-up">Four projects.<br>Four Microsoft customer problems solved.</h2>
  <p class="section-sub fade-up">Each project targets a top enterprise pain point announced at FabCon 2026 — the largest Microsoft data platform conference of the year.</p>

  <div class="ms-banner fade-up">
    <div class="ms-banner-icon">📡</div>
    <div class="ms-banner-text">
      <strong>FabCon 2026 (March, Atlanta):</strong> Microsoft announced that Fabric now serves 31,000+ customers and is the fastest-growing data platform in its history. Every project below directly targets a problem Microsoft's Customer Success team is being asked to solve this year.
    </div>
  </div>

  <div class="projects-grid fade-up">

    <!-- PROJECT 1 -->
    <div class="proj-card p1">
      <div class="proj-card-inner">
        <div class="proj-left">
          <div class="proj-num-badge">
            <div class="proj-num">01</div>
            <span class="proj-num-text">HIGHEST PRIORITY — FABRIC MODERNIZATION</span>
          </div>
          <div class="proj-title">Enterprise Data Lakehouse on Microsoft Fabric + OneLake</div>
          <p class="proj-problem">Most enterprises run 4–5 disconnected Microsoft tools — ADF, Synapse, ADLS, Power BI — each with separate billing, governance, and security. Data engineers spend 60% of their time moving data between tools instead of building AI value. This project replaces that entire stack.</p>
          <div class="ms-signal-box">
            <strong>Microsoft's stated problem (FabCon 2026):</strong> "The biggest challenge is not technology — it is organizational readiness, including data quality, governance, and operating models."
          </div>
          <div class="badge-row">
            <span class="badge">Microsoft Fabric</span>
            <span class="badge">OneLake</span>
            <span class="badge">Delta Lake</span>
            <span class="badge">Data Factory</span>
            <span class="badge">PySpark</span>
            <span class="badge">Power BI Direct Lake</span>
            <span class="badge">Azure Purview</span>
          </div>
        </div>
        <div class="proj-right">
          <div>
            <div class="proj-right-label">HOW I SOLVED THIS</div>
            <div class="solved-block">
              <div class="solved-label">ARCHITECTURAL APPROACH</div>
              <div class="solved-text">Built a complete Bronze→Silver→Gold medallion lakehouse on OneLake. All data lands in one place, transforms via PySpark notebooks, serves Power BI via Direct Lake — zero data copies. Purview auto-classifies every table on ingestion, making the entire estate AI-ready from day one.</div>
            </div>
          </div>
          <div>
            <div class="proj-right-label">MEASURED OUTCOMES</div>
            <div class="metric-list">
              <div class="metric-item"><div class="metric-dot"></div><span>4-tool legacy stack → 1 Fabric capacity</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>40% reduction in data engineering overhead</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>100% data lineage visibility for AI activation</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>Zero data copies — Direct Lake mode</span></div>
            </div>
          </div>
          <a class="proj-gh-link" href="https://github.com/Gehanmassoud/fabric-retail-lakehouse" target="_blank">
            ⬡ github.com/Gehanmassoud/fabric-retail-lakehouse →
          </a>
        </div>
      </div>
    </div>

    <!-- PROJECT 2 -->
    <div class="proj-card p2">
      <div class="proj-card-inner">
        <div class="proj-left">
          <div class="proj-num-badge">
            <div class="proj-num">02</div>
            <span class="proj-num-text">AI AGENT INFRASTRUCTURE</span>
          </div>
          <div class="proj-title">AI Data Agent — Fabric IQ + Cosmos DB Multi-Agent Architecture</div>
          <p class="proj-problem">AI agents built by different teams operate from different definitions of "customer," "order," and "region." When those definitions diverge, AI decisions break down — not from model failure, but from fragmented context. This is the #1 enterprise AI failure mode of 2026.</p>
          <div class="ms-signal-box">
            <strong>Microsoft's stated problem (VentureBeat / FabCon 2026):</strong> "Agents built on different platforms don't share a common understanding of the business. When those definitions diverge across a workforce of agents, decisions break down."
          </div>
          <div class="badge-row">
            <span class="badge">Copilot Studio</span>
            <span class="badge">Fabric Data Agent</span>
            <span class="badge">Azure OpenAI GPT-4o</span>
            <span class="badge">Cosmos DB</span>
            <span class="badge">Power Automate</span>
            <span class="badge">Azure Purview</span>
          </div>
        </div>
        <div class="proj-right">
          <div>
            <div class="proj-right-label">HOW I SOLVED THIS</div>
            <div class="solved-block">
              <div class="solved-label">ARCHITECTURAL APPROACH</div>
              <div class="solved-text">Grounded all AI agent responses in a governed Fabric semantic layer (Fabric IQ), so every query resolves against the same definition of business entities. Cosmos DB provides persistent session state, enabling multi-turn reasoning without context loss. Purview audits every prompt/response for compliance.</div>
            </div>
          </div>
          <div>
            <div class="proj-right-label">MEASURED OUTCOMES</div>
            <div class="metric-list">
              <div class="metric-item"><div class="metric-dot"></div><span>Zero hallucination on governed business entities</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>Persistent session state across conversations</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>Full Purview audit trail on all AI interactions</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>Natural language → governed data in &lt;2 seconds</span></div>
            </div>
          </div>
          <a class="proj-gh-link" href="https://github.com/Gehanmassoud/fabric-ai-data-agent" target="_blank">
            ⬡ github.com/Gehanmassoud/fabric-ai-data-agent →
          </a>
        </div>
      </div>
    </div>

    <!-- PROJECT 3 -->
    <div class="proj-card p3">
      <div class="proj-card-inner">
        <div class="proj-left">
          <div class="proj-num-badge">
            <div class="proj-num">03</div>
            <span class="proj-num-text">RESPONSIBLE AI GOVERNANCE</span>
          </div>
          <div class="proj-title">Responsible AI Governance — Purview DSPM + Fabric Security</div>
          <p class="proj-problem">86% of organizations have zero visibility into what data their AI agents are accessing. Microsoft released Purview DSPM for AI at FabCon 2026 because customers were deploying Copilots and Data Agents with no idea what sensitive data was being surfaced in responses.</p>
          <div class="ms-signal-box">
            <strong>Microsoft's stated problem (Purview Blog, March 2026):</strong> "86% of organizations lack visibility into AI data flows. 67% of executives are uncomfortable using data for AI due to quality concerns."
          </div>
          <div class="badge-row">
            <span class="badge">Azure Purview</span>
            <span class="badge">Purview DSPM for AI</span>
            <span class="badge">DLP Policies</span>
            <span class="badge">Sensitivity Labels</span>
            <span class="badge">Microsoft Fabric</span>
            <span class="badge">Responsible AI</span>
          </div>
        </div>
        <div class="proj-right">
          <div>
            <div class="proj-right-label">HOW I SOLVED THIS</div>
            <div class="solved-block">
              <div class="solved-label">ARCHITECTURAL APPROACH</div>
              <div class="solved-text">Auto-discovers all Fabric assets, classifies 100% of data with sensitivity labels, enforces DLP policies blocking sensitive data from AI prompts, and deploys DSPM for AI to monitor every agent interaction in real time. Governance is day one — not phase two.</div>
            </div>
          </div>
          <div>
            <div class="proj-right-label">MEASURED OUTCOMES</div>
            <div class="metric-list">
              <div class="metric-item"><div class="metric-dot"></div><span>0% → 100% sensitive asset classification</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>DLP active on all AI-accessible data</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>Full audit trail for regulatory compliance</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>DSPM monitoring all Copilot/Agent interactions</span></div>
            </div>
          </div>
          <a class="proj-gh-link" href="https://github.com/Gehanmassoud/responsible-ai-governance-fabric" target="_blank">
            ⬡ github.com/Gehanmassoud/responsible-ai-governance-fabric →
          </a>
        </div>
      </div>
    </div>

    <!-- PROJECT 4 -->
    <div class="proj-card p4">
      <div class="proj-card-inner">
        <div class="proj-left">
          <div class="proj-num-badge">
            <div class="proj-num">04</div>
            <span class="proj-num-text">HYBRID ARCHITECTURE — DATABRICKS + FABRIC</span>
          </div>
          <div class="proj-title">Hybrid Lakehouse — Azure Databricks Unity Catalog + Fabric OneLake</div>
          <p class="proj-problem">The hottest CSA question of 2026: customers have Databricks for ML and want Fabric for BI — but Unity Catalog and Purview don't automatically synchronize governance. Microsoft put OneLake ↔ Databricks Unity Catalog into public preview at FabCon 2026. This project implements it.</p>
          <div class="ms-signal-box">
            <strong>Microsoft's stated announcement (FabCon 2026):</strong> "Native reading from OneLake through Azure Databricks Unity Catalog is now in public preview." — The governance gap "needs to be designed explicitly across both layers rather than assumed to be inherited."
          </div>
          <div class="badge-row">
            <span class="badge">Azure Databricks</span>
            <span class="badge">Unity Catalog</span>
            <span class="badge">OneLake Shortcuts</span>
            <span class="badge">MLflow</span>
            <span class="badge">Delta Lake</span>
            <span class="badge">Power BI</span>
            <span class="badge">Azure Purview</span>
          </div>
        </div>
        <div class="proj-right">
          <div>
            <div class="proj-right-label">HOW I SOLVED THIS</div>
            <div class="solved-block">
              <div class="solved-label">ARCHITECTURAL APPROACH</div>
              <div class="solved-text">Databricks handles ML processing and model training with MLflow. OneLake Shortcuts provide zero-copy access to Databricks Delta tables inside Fabric. Power BI Direct Lake serves governed BI. Documented explicit governance bridge pattern ensuring Purview and Unity Catalog policy parity.</div>
            </div>
          </div>
          <div>
            <div class="proj-right-label">MEASURED OUTCOMES</div>
            <div class="metric-list">
              <div class="metric-item"><div class="metric-dot"></div><span>Zero data duplication across platforms</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>ML predictions surfaced in Power BI in real time</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>Explicit governance bridge — Purview + Unity Catalog</span></div>
              <div class="metric-item"><div class="metric-dot"></div><span>No forced Databricks migration required</span></div>
            </div>
          </div>
          <a class="proj-gh-link" href="https://github.com/Gehanmassoud/databricks-fabric-hybrid-lakehouse" target="_blank">
            ⬡ github.com/Gehanmassoud/databricks-fabric-hybrid-lakehouse →
          </a>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- EXPERIENCE -->
<div class="exp-strip" id="experience">
  <div class="exp-strip-inner">
    <div class="section-tag fade-up">PROFESSIONAL EXPERIENCE</div>
    <h2 class="section-heading fade-up">19 years. Every role<br>built toward this one.</h2>
    <div class="exp-grid fade-up">
      <div class="exp-card">
        <div class="exp-company">SELF-EMPLOYED</div>
        <div class="exp-title">Cloud Solution Architect — AI & Data Platform</div>
        <div class="exp-dates">Jan 2025 – Present</div>
        <div class="exp-metrics">
          <div class="exp-metric"><strong>4</strong> enterprise PoC architectures on Fabric + AI</div>
          <div class="exp-metric"><strong>30%</strong> proj. improvement in AI response time</div>
          <div class="exp-metric"><strong>95%</strong> proj. on-time delivery (AI Order Mgmt)</div>
        </div>
      </div>
      <div class="exp-card">
        <div class="exp-company">NAYLOR ASSOCIATION SOLUTIONS</div>
        <div class="exp-title">Senior Data Solution Engineer</div>
        <div class="exp-dates">Apr 2022 – Jan 2025</div>
        <div class="exp-metrics">
          <div class="exp-metric"><strong>300+</strong> databases · <strong>1M+</strong> users · 99.9% uptime</div>
          <div class="exp-metric"><strong>80%</strong> reduction in manual processing</div>
          <div class="exp-metric"><strong>32</strong> production DevOps releases</div>
        </div>
      </div>
      <div class="exp-card">
        <div class="exp-company">GLOBAL IT SERVICES</div>
        <div class="exp-title">Senior Intelligence Technology Specialist</div>
        <div class="exp-dates">Sep 2018 – Apr 2022</div>
        <div class="exp-metrics">
          <div class="exp-metric"><strong>30%</strong> increase in ML predictive accuracy</div>
          <div class="exp-metric"><strong>50%</strong> improvement in reporting performance</div>
          <div class="exp-metric"><strong>50%</strong> reduction in manual workflow effort</div>
        </div>
      </div>
      <div class="exp-card">
        <div class="exp-company">NOKIA / ALCATEL-LUCENT</div>
        <div class="exp-title">Business Excellence PM + Senior Technical Roles</div>
        <div class="exp-dates">Feb 2006 – Feb 2018</div>
        <div class="exp-metrics">
          <div class="exp-metric"><strong>54</strong> enterprise accounts globally</div>
          <div class="exp-metric"><strong>+21%</strong> CSAT · <strong>+13%</strong> NPS</div>
          <div class="exp-metric"><strong>+67%</strong> productivity · <strong>−25%</strong> OPEX</div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- CERTIFICATIONS -->
<section id="certifications">
  <div class="section-tag fade-up">CREDENTIALS</div>
  <h2 class="section-heading fade-up">Certifications</h2>
  <div class="certs-grid fade-up">
    <div class="cert-card inprogress">
      <div class="cert-status">⟳ IN PROGRESS</div>
      <div class="cert-name">Azure AI Engineer Associate</div>
      <div class="cert-issuer">Microsoft · Expected Nov 2025</div>
    </div>
    <div class="cert-card inprogress">
      <div class="cert-status">⟳ IN PROGRESS</div>
      <div class="cert-name">Power Platform Solution Architect Expert</div>
      <div class="cert-issuer">Microsoft · Expected Dec 2025</div>
    </div>
    <div class="cert-card">
      <div class="cert-status">✓ CERTIFIED</div>
      <div class="cert-name">Project Management Professional (PMP)</div>
      <div class="cert-issuer">Project Management Institute</div>
    </div>
    <div class="cert-card">
      <div class="cert-status">✓ CERTIFIED</div>
      <div class="cert-name">Big Data Architect Master's Program</div>
      <div class="cert-issuer">Intellipaat · 2021</div>
    </div>
    <div class="cert-card">
      <div class="cert-status">✓ CERTIFIED</div>
      <div class="cert-name">Tableau Desktop Certified Associate</div>
      <div class="cert-issuer">Intellipaat · 2021</div>
    </div>
    <div class="cert-card">
      <div class="cert-status">✓ CERTIFIED</div>
      <div class="cert-name">Spark Fundamentals I · Python for Data Science</div>
      <div class="cert-issuer">IBM · 2021</div>
    </div>
  </div>
</section>

<!-- FOOTER CTA -->
<div class="footer-cta">
  <h2>Let's build what's next<br>for Microsoft customers.</h2>
  <p>Available immediately for the Cloud Solution Architect — Cloud & AI Data Platform role. Authorized to work in the US without sponsorship.</p>
  <div class="contact-row">
    <a class="contact-pill" href="mailto:gehan.massoud2020@gmail.com">✉ gehan.massoud2020@gmail.com</a>
    <a class="contact-pill" href="tel:9293533677">📞 929-353-3677</a>
    <a class="contact-pill" href="https://linkedin.com/in/gehanmassoud" target="_blank">in linkedin.com/in/gehanmassoud</a>
    <a class="contact-pill" href="https://github.com/Gehanmassoud" target="_blank">⬡ github.com/Gehanmassoud</a>
  </div>
</div>

<script>
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
}, { threshold: 0.1, rootMargin: '0px 0px -40px 0px' });

document.querySelectorAll('.fade-up').forEach(el => {
  observer.observe(el);
});
</script>
</body>
</html>

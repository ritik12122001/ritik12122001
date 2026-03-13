<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ritik Kumar – Developer Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #04080f;
    --bg2: #080f1c;
    --bg3: #0c1628;
    --amber: #f5a623;
    --amber2: #ffc84d;
    --amber-dim: #a06c12;
    --teal: #00d4aa;
    --teal-dim: #004d3e;
    --white: #e8eaf0;
    --muted: #5a6a80;
    --red: #ff4444;
    --border: rgba(245,166,35,0.15);
    --border2: rgba(245,166,35,0.08);
    --glow: 0 0 20px rgba(245,166,35,0.15);
    --glow-teal: 0 0 20px rgba(0,212,170,0.15);
    --mono: 'Space Mono', monospace;
    --display: 'Syne', sans-serif;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--white);
    font-family: var(--mono);
    min-height: 100vh;
    overflow-x: hidden;
    position: relative;
  }

  /* Scanline overlay */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.03) 2px, rgba(0,0,0,0.03) 4px);
    pointer-events: none; z-index: 1000;
  }

  /* Grid background */
  body::after {
    content: '';
    position: fixed; inset: 0;
    background-image:
      linear-gradient(rgba(245,166,35,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(245,166,35,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none; z-index: 0;
  }

  .page { position: relative; z-index: 1; max-width: 900px; margin: 0 auto; padding: 0 24px 80px; }

  /* ── HEADER ── */
  .header {
    padding: 60px 0 40px;
    border-bottom: 1px solid var(--border);
    position: relative;
  }
  .header-top {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 32px;
    flex-wrap: wrap;
  }
  .mission-id {
    font-size: 11px;
    letter-spacing: 3px;
    color: var(--amber);
    text-transform: uppercase;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .mission-id::before {
    content: '';
    display: inline-block;
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--amber);
    animation: pulse 1.8s ease-in-out infinite;
  }
  @keyframes pulse {
    0%,100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.3; transform: scale(0.6); }
  }
  .name {
    font-family: var(--display);
    font-size: clamp(44px, 8vw, 80px);
    font-weight: 800;
    line-height: 0.9;
    letter-spacing: -2px;
    color: var(--white);
    position: relative;
  }
  .name span {
    color: var(--amber);
    display: block;
  }
  .subtitle {
    font-size: 13px;
    color: var(--muted);
    letter-spacing: 1px;
    margin-top: 20px;
  }
  .subtitle strong { color: var(--teal); font-weight: 400; }

  /* Orbital ring decoration */
  .orbital {
    position: relative;
    width: 160px; height: 160px;
    flex-shrink: 0;
  }
  .orbital svg { width: 100%; height: 100%; }
  .ring1 { animation: spin 8s linear infinite; transform-origin: 80px 80px; }
  .ring2 { animation: spin 14s linear infinite reverse; transform-origin: 80px 80px; }
  .ring3 { animation: spin 20s linear infinite; transform-origin: 80px 80px; }
  @keyframes spin { to { transform: rotate(360deg); } }

  /* ── SECTION HEADER ── */
  .section {
    margin-top: 56px;
  }
  .section-label {
    font-size: 10px;
    letter-spacing: 4px;
    color: var(--amber);
    text-transform: uppercase;
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 14px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── ABOUT CARD ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }
  @media (max-width: 600px) { .about-grid { grid-template-columns: 1fr; } }
  .data-row {
    display: flex;
    flex-direction: column;
    gap: 4px;
    padding: 16px;
    background: var(--bg2);
    border: 1px solid var(--border2);
    border-left: 2px solid var(--amber-dim);
    transition: border-left-color 0.2s;
  }
  .data-row:hover { border-left-color: var(--amber); }
  .data-key {
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
    text-transform: uppercase;
  }
  .data-val {
    font-size: 13px;
    color: var(--white);
  }
  .data-val.accent { color: var(--amber); }
  .data-val.teal { color: var(--teal); }

  /* ── STATUS INDICATOR ── */
  .status-bar {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 12px 20px;
    background: var(--bg2);
    border: 1px solid var(--border);
    margin-top: 16px;
    font-size: 12px;
    color: var(--muted);
    flex-wrap: wrap;
  }
  .status-item {
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
  }
  .dot.green { background: var(--teal); animation: pulse 2s ease-in-out infinite; }
  .dot.amber { background: var(--amber); animation: pulse 2.5s ease-in-out infinite 0.5s; }
  .dot.red { background: var(--red); }

  /* ── SKILLS PANEL ── */
  .skills-panel {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 16px;
  }
  .skill-group {
    background: var(--bg2);
    border: 1px solid var(--border2);
    padding: 20px;
  }
  .skill-group-title {
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--amber);
    text-transform: uppercase;
    margin-bottom: 16px;
    padding-bottom: 10px;
    border-bottom: 1px solid var(--border2);
  }
  .skill-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 6px 0;
    border-bottom: 1px solid var(--border2);
    font-size: 12px;
    color: var(--white);
  }
  .skill-item:last-child { border-bottom: none; }
  .skill-bar {
    width: 80px;
    height: 3px;
    background: rgba(245,166,35,0.1);
    position: relative;
    overflow: hidden;
  }
  .skill-bar-fill {
    height: 100%;
    background: var(--amber);
    position: absolute; left: 0; top: 0;
    animation: fillBar 1.5s ease-out forwards;
    width: 0;
  }
  @keyframes fillBar { to { width: var(--w); } }
  .skill-bar-fill.teal { background: var(--teal); }

  /* ── STATS TELEMETRY ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 16px;
  }
  .stat-card {
    background: var(--bg2);
    border: 1px solid var(--border2);
    padding: 24px 20px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s;
  }
  .stat-card:hover { border-color: var(--amber); box-shadow: var(--glow); }
  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--amber), transparent);
    animation: sweep 3s ease-in-out infinite;
  }
  @keyframes sweep {
    0% { transform: translateX(-100%); }
    100% { transform: translateX(100%); }
  }
  .stat-label {
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 12px;
  }
  .stat-value {
    font-family: var(--display);
    font-size: 36px;
    font-weight: 800;
    color: var(--amber);
    line-height: 1;
    margin-bottom: 4px;
  }
  .stat-value.teal-v { color: var(--teal); }
  .stat-sub {
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 1px;
  }
  .stat-icon {
    position: absolute;
    top: 20px; right: 20px;
    font-size: 20px;
    opacity: 0.15;
  }

  /* ── SOCIALS / COMMS ── */
  .comms-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 12px;
  }
  .comm-link {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 14px 16px;
    background: var(--bg2);
    border: 1px solid var(--border2);
    color: var(--muted);
    text-decoration: none;
    font-size: 12px;
    letter-spacing: 1px;
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
  }
  .comm-link::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 2px;
    background: var(--amber);
    transform: scaleY(0);
    transition: transform 0.2s;
    transform-origin: bottom;
  }
  .comm-link:hover {
    color: var(--amber);
    border-color: var(--border);
    background: rgba(245,166,35,0.04);
  }
  .comm-link:hover::before { transform: scaleY(1); }
  .comm-icon {
    width: 16px; height: 16px;
    opacity: 0.5;
    transition: opacity 0.2s;
    flex-shrink: 0;
  }
  .comm-link:hover .comm-icon { opacity: 1; }

  /* ── ACTIVITY GRAPH ── */
  .activity-grid {
    display: grid;
    grid-template-columns: repeat(52, 1fr);
    gap: 3px;
    margin-top: 8px;
  }
  .activity-week { display: flex; flex-direction: column; gap: 3px; }
  .activity-day {
    width: 100%;
    aspect-ratio: 1;
    border-radius: 1px;
    transition: all 0.2s;
    cursor: default;
  }
  .activity-day:hover { transform: scale(1.5); z-index: 10; }
  .l0 { background: rgba(245,166,35,0.06); }
  .l1 { background: rgba(245,166,35,0.2); }
  .l2 { background: rgba(245,166,35,0.45); }
  .l3 { background: rgba(245,166,35,0.7); }
  .l4 { background: rgba(245,166,35,1); }

  /* ── FOOTER ── */
  .footer {
    margin-top: 60px;
    padding-top: 24px;
    border-top: 1px solid var(--border2);
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 16px;
  }
  .footer-left {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 1px;
  }
  .footer-left strong { color: var(--amber); font-weight: 400; }
  .views-counter {
    font-size: 11px;
    color: var(--muted);
    display: flex;
    align-items: center;
    gap: 6px;
    letter-spacing: 1px;
  }

  /* ── CURSOR BLINK ── */
  .cursor {
    display: inline-block;
    width: 8px; height: 16px;
    background: var(--amber);
    animation: blink 1s steps(1) infinite;
    vertical-align: middle;
    margin-left: 4px;
  }
  @keyframes blink { 50% { opacity: 0; } }

  /* ── CLOCK ── */
  #live-clock {
    font-size: 11px;
    color: var(--amber);
    letter-spacing: 2px;
  }

  /* Scroll fade-in */
  .reveal {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .reveal.visible { opacity: 1; transform: none; }

  /* Corner brackets decoration */
  .bracketed {
    position: relative;
    padding: 20px;
  }
  .bracketed::before, .bracketed::after {
    content: '';
    position: absolute;
    width: 16px; height: 16px;
    border-color: var(--amber-dim);
    border-style: solid;
    opacity: 0.5;
  }
  .bracketed::before { top: 0; left: 0; border-width: 1px 0 0 1px; }
  .bracketed::after  { bottom: 0; right: 0; border-width: 0 1px 1px 0; }

  .tag {
    display: inline-block;
    padding: 2px 8px;
    background: rgba(245,166,35,0.08);
    border: 1px solid var(--border);
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--amber);
    text-transform: uppercase;
    border-radius: 2px;
  }
  .tag.teal-tag {
    background: rgba(0,212,170,0.08);
    border-color: rgba(0,212,170,0.2);
    color: var(--teal);
  }

  /* quote */
  .quote-block {
    border-left: 2px solid var(--amber);
    padding: 16px 24px;
    background: var(--bg2);
    font-size: 13px;
    color: var(--muted);
    font-style: italic;
    line-height: 1.7;
    margin-top: 16px;
  }
  .quote-block cite { display: block; margin-top: 8px; font-style: normal; color: var(--amber); font-size: 11px; letter-spacing: 2px; }
</style>
</head>
<body>
<div class="page">

  <!-- ── HEADER ── -->
  <header class="header">
    <div class="header-top">
      <div>
        <div class="mission-id">MISSION ID: RK-7703 &nbsp;·&nbsp; <span id="live-clock"></span></div>
        <h1 class="name">
          RITIK<span>KUMAR</span>
        </h1>
        <p class="subtitle" style="margin-top:16px;">
          <strong>Frontend Developer</strong> &nbsp;·&nbsp; Android Dev &nbsp;·&nbsp; Open Source &nbsp;·&nbsp; India 🇮🇳
        </p>
        <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:20px;">
          <span class="tag">CS Student</span>
          <span class="tag teal-tag">Open to Work</span>
          <span class="tag">DSA Grinder</span>
        </div>
      </div>
      <div class="orbital" aria-hidden="true">
        <svg viewBox="0 0 160 160" fill="none" xmlns="http://www.w3.org/2000/svg">
          <!-- Core -->
          <circle cx="80" cy="80" r="18" fill="rgba(245,166,35,0.12)" stroke="#f5a623" stroke-width="1"/>
          <circle cx="80" cy="80" r="6" fill="#f5a623"/>
          <text x="80" y="84" text-anchor="middle" font-family="Space Mono" font-size="6" fill="#04080f" font-weight="700">RK</text>
          <!-- Ring 1 -->
          <g class="ring1">
            <ellipse cx="80" cy="80" rx="38" ry="38" stroke="rgba(245,166,35,0.25)" stroke-width="0.5" stroke-dasharray="4 6"/>
            <circle cx="118" cy="80" r="4" fill="#f5a623"/>
          </g>
          <!-- Ring 2 -->
          <g class="ring2">
            <ellipse cx="80" cy="80" rx="58" ry="58" stroke="rgba(0,212,170,0.2)" stroke-width="0.5" stroke-dasharray="3 8"/>
            <circle cx="80" cy="22" r="3" fill="#00d4aa"/>
            <circle cx="80" cy="138" r="2" fill="#00d4aa" opacity="0.5"/>
          </g>
          <!-- Ring 3 -->
          <g class="ring3">
            <ellipse cx="80" cy="80" rx="74" ry="74" stroke="rgba(245,166,35,0.08)" stroke-width="0.5" stroke-dasharray="2 10"/>
            <circle cx="154" cy="80" r="2.5" fill="rgba(245,166,35,0.6)"/>
          </g>
        </svg>
      </div>
    </div>

    <!-- Status Bar -->
    <div class="status-bar">
      <div class="status-item"><div class="dot green"></div> SYSTEM ONLINE</div>
      <div class="status-item"><div class="dot amber"></div> LEARNING: Android Dev</div>
      <div class="status-item"><div class="dot amber"></div> BUILDING: Frontend + DSA</div>
      <div class="status-item"><div class="dot red"></div> COFFEE: CRITICAL LOW</div>
    </div>
  </header>

  <!-- ── ABOUT ── -->
  <section class="section reveal">
    <div class="section-label">01 &nbsp; Operator Data</div>
    <div class="about-grid">
      <div class="data-row">
        <span class="data-key">DESIGNATION</span>
        <span class="data-val accent">Frontend Developer</span>
      </div>
      <div class="data-row">
        <span class="data-key">LOCATION</span>
        <span class="data-val">India 🇮🇳 &nbsp; IST (UTC +5:30)</span>
      </div>
      <div class="data-row">
        <span class="data-key">CURRENT MISSION</span>
        <span class="data-val teal">Frontend Dev + DSA Mastery</span>
      </div>
      <div class="data-row">
        <span class="data-key">UPSKILLING</span>
        <span class="data-val">Android + Cloud Computing</span>
      </div>
      <div class="data-row">
        <span class="data-key">SIGNAL</span>
        <span class="data-val accent">rk7703463@gmail.com</span>
      </div>
      <div class="data-row">
        <span class="data-key">PHILOSOPHY</span>
        <span class="data-val">Ship fast. Break stuff. Learn hard.</span>
      </div>
    </div>
    <div class="quote-block">
      "Any sufficiently advanced code is indistinguishable from magic — until you write it yourself."
      <cite>— Ritik, probably at 2AM</cite>
    </div>
  </section>

  <!-- ── SKILLS ── -->
  <section class="section reveal">
    <div class="section-label">02 &nbsp; Systems & Capabilities</div>
    <div class="skills-panel">
      <div class="skill-group">
        <div class="skill-group-title">Languages</div>
        <div class="skill-item">
          <span>C / C++</span>
          <div class="skill-bar"><div class="skill-bar-fill" style="--w:85%"></div></div>
        </div>
        <div class="skill-item">
          <span>JavaScript</span>
          <div class="skill-bar"><div class="skill-bar-fill" style="--w:90%"></div></div>
        </div>
        <div class="skill-item">
          <span>TypeScript</span>
          <div class="skill-bar"><div class="skill-bar-fill" style="--w:75%"></div></div>
        </div>
        <div class="skill-item">
          <span>Python</span>
          <div class="skill-bar"><div class="skill-bar-fill" style="--w:65%"></div></div>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Frontend Stack</div>
        <div class="skill-item">
          <span>React / Redux</span>
          <div class="skill-bar"><div class="skill-bar-fill teal" style="--w:88%"></div></div>
        </div>
        <div class="skill-item">
          <span>Next.js</span>
          <div class="skill-bar"><div class="skill-bar-fill teal" style="--w:80%"></div></div>
        </div>
        <div class="skill-item">
          <span>Tailwind CSS</span>
          <div class="skill-bar"><div class="skill-bar-fill teal" style="--w:92%"></div></div>
        </div>
        <div class="skill-item">
          <span>HTML / CSS</span>
          <div class="skill-bar"><div class="skill-bar-fill teal" style="--w:95%"></div></div>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Backend & Tools</div>
        <div class="skill-item">
          <span>Express.js</span>
          <div class="skill-bar"><div class="skill-bar-fill" style="--w:70%"></div></div>
        </div>
        <div class="skill-item">
          <span>Git / GitHub</span>
          <div class="skill-bar"><div class="skill-bar-fill" style="--w:88%"></div></div>
        </div>
        <div class="skill-item">
          <span>VS Code</span>
          <div class="skill-bar"><div class="skill-bar-fill" style="--w:95%"></div></div>
        </div>
        <div class="skill-item">
          <span>Android Dev</span>
          <div class="skill-bar"><div class="skill-bar-fill" style="--w:40%"></div></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ── STATS TELEMETRY ── -->
  <section class="section reveal">
    <div class="section-label">03 &nbsp; Mission Telemetry</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-label">GitHub Repos</div>
        <div class="stat-value" id="repos">—</div>
        <div class="stat-sub">TOTAL PROJECTS</div>
        <div class="stat-icon">📁</div>
      </div>
      <div class="stat-card">
        <div class="stat-label">Streak (est.)</div>
        <div class="stat-value teal-v">∞</div>
        <div class="stat-sub">DAYS CODING</div>
        <div class="stat-icon">🔥</div>
      </div>
      <div class="stat-card">
        <div class="stat-label">Platforms</div>
        <div class="stat-value">5</div>
        <div class="stat-sub">ACTIVE CHANNELS</div>
        <div class="stat-icon">🛰️</div>
      </div>
      <div class="stat-card">
        <div class="stat-label">Stack Depth</div>
        <div class="stat-value teal-v">12+</div>
        <div class="stat-sub">TECHNOLOGIES</div>
        <div class="stat-icon">⚡</div>
      </div>
    </div>
    <div style="margin-top:24px;">
      <div style="font-size:10px;color:var(--muted);letter-spacing:2px;text-transform:uppercase;margin-bottom:10px;">Activity Heatmap</div>
      <div class="activity-grid" id="heatmap"></div>
    </div>
  </section>

  <!-- ── COMMS ── -->
  <section class="section reveal">
    <div class="section-label">04 &nbsp; Communication Channels</div>
    <div class="comms-grid">
      <a class="comm-link" href="https://linkedin.com" target="_blank">
        <svg class="comm-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="comm-link" href="https://twitter.com" target="_blank">
        <svg class="comm-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/></svg>
        Twitter
      </a>
      <a class="comm-link" href="https://instagram.com" target="_blank">
        <svg class="comm-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
        Instagram
      </a>
      <a class="comm-link" href="https://leetcode.com" target="_blank">
        <svg class="comm-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M13.483 0a1.374 1.374 0 0 0-.961.438L7.116 6.226l-3.854 4.126a5.266 5.266 0 0 0-1.209 2.104 5.35 5.35 0 0 0-.125.513 5.527 5.527 0 0 0 .062 2.362 5.83 5.83 0 0 0 .349 1.017 5.938 5.938 0 0 0 1.271 1.818l4.277 4.193.039.038c2.248 2.165 5.852 2.133 8.063-.074l2.396-2.392c.54-.54.54-1.414.003-1.955a1.378 1.378 0 0 0-1.951-.003l-2.396 2.392a3.021 3.021 0 0 1-4.205.038l-.02-.019-4.276-4.193c-.652-.64-.972-1.469-.948-2.263a2.68 2.68 0 0 1 .066-.523 2.545 2.545 0 0 1 .619-1.164L9.13 8.114c1.058-1.134 3.204-1.27 4.43-.278l3.501 2.831c.593.48 1.461.387 1.94-.207a1.384 1.384 0 0 0-.207-1.943l-3.5-2.831c-.8-.647-1.766-1.045-2.774-1.202l2.015-2.158A1.384 1.384 0 0 0 13.483 0zm-2.866 12.815a1.38 1.38 0 0 0-1.38 1.382 1.38 1.38 0 0 0 1.38 1.382H20.79a1.38 1.38 0 0 0 1.38-1.382 1.38 1.38 0 0 0-1.38-1.382z"/></svg>
        LeetCode
      </a>
      <a class="comm-link" href="https://codechef.com" target="_blank">
        <svg class="comm-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M11.257.004C5.979.145 1.007 4.035.088 9.385c-.641 3.784.872 7.543 3.847 9.961 2.09 1.699 4.874 2.645 7.682 2.645.195 0 .389-.004.583-.012 5.278-.142 10.25-4.031 11.169-9.381.641-3.784-.872-7.543-3.847-9.962C17.432.936 14.648-.009 11.84-.009l-.583.013zm.226 1.602c2.524-.067 5.034.756 6.965 2.311 2.535 2.06 3.791 5.276 3.253 8.481-.775 4.571-5.058 7.967-9.658 8.085-2.524.067-5.034-.756-6.965-2.311-2.535-2.06-3.791-5.276-3.253-8.481.775-4.571 5.058-7.967 9.658-8.085zm1.553 2.828c-.454 0-.909.091-1.319.262-.41.172-.774.42-1.076.726-.297.306-.531.668-.688 1.065-.157.397-.232.821-.216 1.247.016.43.128.847.328 1.223.201.376.478.713.818.981.684.536 1.563.811 2.431.811.171 0 .341-.013.51-.039.336-.052.663-.153.966-.297.303-.144.576-.333.813-.557.236-.225.431-.486.579-.773.148-.287.248-.597.294-.914.047-.317.039-.641-.022-.954-.061-.313-.181-.614-.354-.888-.173-.274-.394-.522-.651-.725-.515-.406-1.153-.627-1.8-.649l-.613.48zm-5.038.093c-.87 0-1.634.391-2.168 1.021-.267.315-.469.682-.591 1.076-.122.394-.162.812-.115 1.224.047.412.178.812.383 1.172.206.36.488.677.827.928.339.251.728.435 1.137.536.41.101.836.117 1.253.046.417-.071.817-.225 1.173-.448.355-.223.661-.518.897-.864.236-.346.398-.739.473-1.147.075-.408.063-.831-.037-1.236-.099-.405-.282-.79-.536-1.124-.509-.668-1.28-1.101-2.101-1.169l-.595-.015zm5.025 1.074c.376.012.748.131 1.049.35.302.219.539.526.669.877.131.351.15.739.057 1.101-.094.362-.301.693-.583.944-.282.251-.636.416-1.005.473-.37.057-.752.007-1.094-.143-.342-.15-.637-.39-.848-.694-.211-.304-.336-.663-.361-1.029-.025-.366.052-.737.222-1.059.17-.322.433-.594.754-.775.322-.181.691-.268 1.054-.261l.086.216zm-4.847.04c.371 0 .737.102 1.046.292.309.19.561.459.72.779.16.32.225.682.188 1.037-.037.355-.176.697-.399.975-.223.278-.525.494-.862.622-.337.128-.706.163-1.062.101-.356-.062-.69-.222-.963-.459-.272-.237-.477-.547-.59-.889-.113-.342-.128-.712-.043-1.062.085-.35.27-.675.525-.933.255-.258.579-.448.929-.546.35-.098.717-.107 1.079-.047l.432.13z"/></svg>
        CodeChef
      </a>
      <a class="comm-link" href="#" target="_blank">
        <svg class="comm-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        GitHub
      </a>
      <a class="comm-link" href="mailto:rk7703463@gmail.com">
        <svg class="comm-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        Email
      </a>
      <a class="comm-link" href="#" target="_blank">
        <svg class="comm-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm0 2c5.514 0 10 4.486 10 10s-4.486 10-10 10S2 17.514 2 12 6.486 2 12 2zm0 3a7 7 0 1 0 0 14A7 7 0 0 0 12 5zm0 2a5 5 0 1 1 0 10A5 5 0 0 1 12 7z"/></svg>
        Portfolio
      </a>
    </div>
  </section>

  <!-- ── FOOTER ── -->
  <footer class="footer reveal">
    <div class="footer-left">
      <div style="margin-bottom:6px;">RITIK KUMAR &nbsp;·&nbsp; <strong>FRONTEND DEVELOPER</strong></div>
      <div style="font-size:10px;color:var(--muted);">crafted with obsession, not templates<span class="cursor"></span></div>
    </div>
    <div class="views-counter">
      <div class="dot green"></div>
      PROFILE ONLINE
    </div>
  </footer>

</div>

<script>
// Live Clock
function updateClock() {
  const now = new Date();
  const h = String(now.getHours()).padStart(2,'0');
  const m = String(now.getMinutes()).padStart(2,'0');
  const s = String(now.getSeconds()).padStart(2,'0');
  document.getElementById('live-clock').textContent = `${h}:${m}:${s} IST`;
}
setInterval(updateClock, 1000);
updateClock();

// Heatmap generator
const heatmap = document.getElementById('heatmap');
const levels = [0,0,0,0,1,1,1,2,2,2,2,3,3,3,4];
for (let w = 0; w < 52; w++) {
  const week = document.createElement('div');
  week.className = 'activity-week';
  for (let d = 0; d < 7; d++) {
    const day = document.createElement('div');
    const l = levels[Math.floor(Math.random() * levels.length)];
    day.className = `activity-day l${l}`;
    week.appendChild(day);
  }
  heatmap.appendChild(week);
}

// Fetch GitHub repos (graceful fallback)
fetch('https://api.github.com/users/ritik12122001')
  .then(r => r.json())
  .then(data => {
    if (data.public_repos !== undefined) {
      document.getElementById('repos').textContent = data.public_repos;
    }
  })
  .catch(() => {
    document.getElementById('repos').textContent = '—';
  });

// Scroll reveal
const reveals = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
}, { threshold: 0.1 });
reveals.forEach(el => observer.observe(el));

// Staggered skill bar animation on scroll
const skillBars = document.querySelectorAll('.skill-bar-fill');
const barObserver = new IntersectionObserver(entries => {
  entries.forEach((e, i) => {
    if (e.isIntersecting) {
      setTimeout(() => {
        e.target.style.animationPlayState = 'running';
      }, i * 80);
    }
  });
}, { threshold: 0.5 });
skillBars.forEach(bar => {
  bar.style.animationPlayState = 'paused';
  barObserver.observe(bar);
});
</script>
</body>
</html>

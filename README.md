<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ritik Kumar – Developer Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
<style>
  :root{--bg:#04080f;--bg2:#080f1c;--amber:#f5a623;--amber2:#ffc84d;--adim:#a06c12;--teal:#00d4aa;--white:#e8eaf0;--muted:#5a6a80;--red:#ff4444;--green:#39ff8a;--border:rgba(245,166,35,.15);--border2:rgba(245,166,35,.07);--glow:0 0 24px rgba(245,166,35,.12);--mono:'Space Mono',monospace;--display:'Syne',sans-serif;}
  *,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
  html{scroll-behavior:smooth;}
  body{background:var(--bg);color:var(--white);font-family:var(--mono);min-height:100vh;overflow-x:hidden;position:relative;}
  body::before{content:'';position:fixed;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,.025) 2px,rgba(0,0,0,.025) 4px);pointer-events:none;z-index:1000;}
  body::after{content:'';position:fixed;inset:0;background-image:linear-gradient(rgba(245,166,35,.025) 1px,transparent 1px),linear-gradient(90deg,rgba(245,166,35,.025) 1px,transparent 1px);background-size:52px 52px;pointer-events:none;z-index:0;}
  .page{position:relative;z-index:1;max-width:940px;margin:0 auto;padding:0 28px 100px;}
  .header{padding:56px 0 36px;border-bottom:1px solid var(--border);}
  .header-inner{display:flex;align-items:flex-start;justify-content:space-between;gap:32px;flex-wrap:wrap;}
  .mission-badge{font-size:10px;letter-spacing:3px;color:var(--amber);text-transform:uppercase;margin-bottom:18px;display:flex;align-items:center;gap:10px;}
  .mission-badge::before{content:'';display:inline-block;width:7px;height:7px;border-radius:50%;background:var(--amber);animation:pulse 1.8s ease-in-out infinite;}
  @keyframes pulse{0%,100%{opacity:1;transform:scale(1);}50%{opacity:.25;transform:scale(.55);}}
  .name{font-family:var(--display);font-size:clamp(48px,9vw,86px);font-weight:800;line-height:.88;letter-spacing:-3px;color:var(--white);}
  .name span{color:var(--amber);display:block;}
  .role-line{font-size:13px;color:var(--muted);letter-spacing:1px;margin-top:18px;line-height:1.8;}
  .role-line strong{color:var(--teal);font-weight:400;}
  .tags{display:flex;gap:8px;flex-wrap:wrap;margin-top:18px;}
  .tag{display:inline-block;padding:3px 10px;font-size:10px;letter-spacing:2px;text-transform:uppercase;border-radius:2px;border:1px solid;}
  .tag-a{background:rgba(245,166,35,.08);border-color:rgba(245,166,35,.3);color:var(--amber);}
  .tag-t{background:rgba(0,212,170,.07);border-color:rgba(0,212,170,.25);color:var(--teal);}
  .tag-g{background:rgba(57,255,138,.07);border-color:rgba(57,255,138,.25);color:var(--green);}
  .orbital{position:relative;width:170px;height:170px;flex-shrink:0;}
  .orbital svg{width:100%;height:100%;}
  .ring1{animation:spin 8s linear infinite;transform-origin:85px 85px;}
  .ring2{animation:spin 15s linear infinite reverse;transform-origin:85px 85px;}
  .ring3{animation:spin 22s linear infinite;transform-origin:85px 85px;}
  @keyframes spin{to{transform:rotate(360deg);}}
  .status-bar{display:flex;align-items:center;gap:16px;flex-wrap:wrap;padding:12px 20px;background:var(--bg2);border:1px solid var(--border);margin-top:20px;font-size:11px;color:var(--muted);letter-spacing:1px;}
  .si{display:flex;align-items:center;gap:7px;}
  .dot{width:6px;height:6px;border-radius:50%;}
  .d-g{background:var(--teal);animation:pulse 2.2s ease-in-out infinite;}
  .d-a{background:var(--amber);animation:pulse 2.8s ease-in-out infinite .5s;}
  .d-r{background:var(--red);}
  .section{margin-top:60px;}
  .sec-label{font-size:10px;letter-spacing:4px;color:var(--amber);text-transform:uppercase;margin-bottom:24px;display:flex;align-items:center;gap:14px;}
  .sec-label::after{content:'';flex:1;height:1px;background:var(--border);}
  .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;}
  @media(max-width:560px){.about-grid{grid-template-columns:1fr;}}
  .data-row{display:flex;flex-direction:column;gap:5px;padding:16px 18px;background:var(--bg2);border:1px solid var(--border2);border-left:2px solid var(--adim);transition:border-left-color .2s,box-shadow .2s;}
  .data-row:hover{border-left-color:var(--amber);box-shadow:var(--glow);}
  .dk{font-size:9px;letter-spacing:2.5px;color:var(--muted);text-transform:uppercase;}
  .dv{font-size:12px;color:var(--white);line-height:1.5;}
  .dv.a{color:var(--amber);}.dv.t{color:var(--teal);}.dv.g{color:var(--green);}
  .exp-list{display:flex;flex-direction:column;gap:0;}
  .exp-item{display:grid;grid-template-columns:3px 1fr;gap:0 24px;position:relative;padding-bottom:36px;}
  .exp-item:last-child{padding-bottom:0;}
  .exp-line{background:var(--border);position:relative;}
  .exp-line::before{content:'';position:absolute;top:6px;left:50%;transform:translateX(-50%);width:11px;height:11px;border-radius:50%;background:var(--amber);border:2px solid var(--bg);box-shadow:0 0 10px var(--amber);}
  .exp-content{padding-top:2px;}
  .exp-header{display:flex;align-items:flex-start;justify-content:space-between;gap:16px;flex-wrap:wrap;margin-bottom:10px;}
  .exp-title{font-family:var(--display);font-size:15px;font-weight:700;color:var(--white);}
  .exp-org{font-size:11px;color:var(--teal);letter-spacing:1px;margin-top:4px;}
  .exp-date{font-size:10px;color:var(--amber);letter-spacing:2px;white-space:nowrap;padding-top:4px;}
  .exp-bullets{list-style:none;padding:0;}
  .exp-bullets li{font-size:11px;color:var(--muted);line-height:1.7;padding:3px 0 3px 14px;position:relative;border-bottom:1px solid var(--border2);}
  .exp-bullets li:last-child{border-bottom:none;}
  .exp-bullets li::before{content:'›';position:absolute;left:0;color:var(--amber);}
  .exp-badge{display:inline-block;margin-top:8px;margin-right:6px;padding:3px 10px;font-size:9px;letter-spacing:2px;background:rgba(245,166,35,.08);border:1px solid rgba(245,166,35,.2);color:var(--amber);text-transform:uppercase;border-radius:2px;}
  .exp-badge.teal{background:rgba(0,212,170,.08);border-color:rgba(0,212,170,.2);color:var(--teal);}
  .skills-panel{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:16px;}
  .skill-group{background:var(--bg2);border:1px solid var(--border2);padding:22px;}
  .sg-title{font-size:10px;letter-spacing:3px;color:var(--amber);text-transform:uppercase;margin-bottom:16px;padding-bottom:10px;border-bottom:1px solid var(--border2);}
  .skill-item{display:flex;align-items:center;justify-content:space-between;padding:7px 0;border-bottom:1px solid var(--border2);font-size:11px;color:var(--white);}
  .skill-item:last-child{border-bottom:none;}
  .sbar{width:76px;height:3px;background:rgba(245,166,35,.1);position:relative;overflow:hidden;}
  .sbf{height:100%;background:var(--amber);position:absolute;left:0;top:0;animation:fillBar 1.6s ease-out forwards;width:0;}
  .sbf.t{background:var(--teal);}.sbf.g{background:var(--green);}
  @keyframes fillBar{to{width:var(--w);}}
  .cert-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:10px;}
  .cert-item{padding:12px 14px;background:var(--bg2);border:1px solid var(--border2);font-size:10px;color:var(--muted);letter-spacing:.5px;line-height:1.5;border-left:2px solid transparent;transition:all .2s;}
  .cert-item:hover{border-left-color:var(--teal);color:var(--white);}
  .cert-item.ibm:hover{border-left-color:var(--amber);}
  .cert-provider{font-size:9px;letter-spacing:2px;text-transform:uppercase;margin-bottom:5px;}
  .cert-provider.google{color:var(--teal);}.cert-provider.ibm{color:var(--amber);}.cert-provider.other{color:var(--muted);}
  .stats-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(170px,1fr));gap:14px;}
  .stat-card{background:var(--bg2);border:1px solid var(--border2);padding:24px 20px;position:relative;overflow:hidden;transition:border-color .3s;}
  .stat-card:hover{border-color:var(--amber);box-shadow:var(--glow);}
  .stat-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--amber),transparent);animation:sweep 3.5s ease-in-out infinite;}
  .stat-card.tc::before{background:linear-gradient(90deg,transparent,var(--teal),transparent);}
  @keyframes sweep{0%{transform:translateX(-100%);}100%{transform:translateX(100%);}}
  .stat-label{font-size:9px;letter-spacing:2.5px;color:var(--muted);text-transform:uppercase;margin-bottom:12px;}
  .stat-value{font-family:var(--display);font-size:40px;font-weight:800;color:var(--amber);line-height:1;margin-bottom:4px;}
  .stat-value.t{color:var(--teal);}.stat-value.g{color:var(--green);}
  .stat-sub{font-size:9px;color:var(--muted);letter-spacing:1px;}
  .stat-icon{position:absolute;top:18px;right:18px;font-size:22px;opacity:.12;}
  .heatmap-wrap{overflow-x:auto;margin-top:8px;}
  .activity-grid{display:grid;grid-template-columns:repeat(52,1fr);gap:3px;min-width:480px;}
  .activity-week{display:flex;flex-direction:column;gap:3px;}
  .activity-day{width:100%;aspect-ratio:1;border-radius:1px;transition:transform .15s;}
  .activity-day:hover{transform:scale(1.6);z-index:10;}
  .l0{background:rgba(245,166,35,.05);}.l1{background:rgba(245,166,35,.2);}.l2{background:rgba(245,166,35,.45);}.l3{background:rgba(245,166,35,.7);}.l4{background:rgba(245,166,35,1);}
  .comms-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:10px;}
  .comm-link{display:flex;align-items:center;gap:10px;padding:14px 16px;background:var(--bg2);border:1px solid var(--border2);color:var(--muted);text-decoration:none;font-size:11px;letter-spacing:1.5px;text-transform:uppercase;transition:all .2s;position:relative;overflow:hidden;}
  .comm-link::before{content:'';position:absolute;left:0;top:0;bottom:0;width:2px;background:var(--amber);transform:scaleY(0);transition:transform .2s;transform-origin:bottom;}
  .comm-link.tl::before{background:var(--teal);}
  .comm-link:hover{color:var(--amber);border-color:var(--border);background:rgba(245,166,35,.03);}
  .comm-link.tl:hover{color:var(--teal);}
  .comm-link:hover::before{transform:scaleY(1);}
  .ci{width:15px;height:15px;opacity:.45;transition:opacity .2s;flex-shrink:0;}
  .comm-link:hover .ci{opacity:1;}
  .footer{margin-top:64px;padding-top:24px;border-top:1px solid var(--border2);display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:16px;}
  .footer-left{font-size:10px;color:var(--muted);letter-spacing:1px;line-height:1.8;}
  .footer-left strong{color:var(--amber);font-weight:400;}
  .cursor{display:inline-block;width:8px;height:14px;background:var(--amber);animation:blink 1s steps(1) infinite;vertical-align:middle;margin-left:3px;}
  @keyframes blink{50%{opacity:0;}}
  #live-clock{font-size:10px;color:var(--amber);letter-spacing:2px;}
  .reveal{opacity:0;transform:translateY(18px);transition:opacity .6s ease,transform .6s ease;}
  .reveal.visible{opacity:1;transform:none;}
  .quote-block{border-left:2px solid var(--amber);padding:16px 22px;background:var(--bg2);font-size:12px;color:var(--muted);font-style:italic;line-height:1.8;margin-top:14px;}
  .quote-block cite{display:block;margin-top:8px;font-style:normal;color:var(--amber);font-size:10px;letter-spacing:2px;}
</style>
</head>
<body>
<div class="page">

  <header class="header">
    <div class="header-inner">
      <div>
        <div class="mission-badge">OPERATOR ID: RK-7703463 &nbsp;·&nbsp; <span id="live-clock"></span></div>
        <h1 class="name">RITIK<span>KUMAR</span></h1>
        <p class="role-line" style="margin-top:16px;"><strong>Android Dev</strong> &nbsp;·&nbsp; <strong>AI / ML</strong> &nbsp;·&nbsp; Cloud &nbsp;·&nbsp; Frontend &nbsp;·&nbsp; India 🇮🇳</p>
        <div class="tags">
          <span class="tag tag-a">B.Tech CSE '25</span>
          <span class="tag tag-t">GDG Associate Lead</span>
          <span class="tag tag-g">Open to Work</span>
          <span class="tag tag-a">Hackathon Builder</span>
        </div>
      </div>
      <div class="orbital" aria-hidden="true">
        <svg viewBox="0 0 170 170" fill="none">
          <circle cx="85" cy="85" r="20" fill="rgba(245,166,35,.1)" stroke="#f5a623" stroke-width="1"/>
          <circle cx="85" cy="85" r="7" fill="#f5a623"/>
          <text x="85" y="89" text-anchor="middle" font-family="Space Mono" font-size="7" fill="#04080f" font-weight="700">RK</text>
          <g class="ring1"><ellipse cx="85" cy="85" rx="42" ry="42" stroke="rgba(245,166,35,.22)" stroke-width=".6" stroke-dasharray="4 7"/><circle cx="127" cy="85" r="4.5" fill="#f5a623"/></g>
          <g class="ring2"><ellipse cx="85" cy="85" rx="63" ry="63" stroke="rgba(0,212,170,.18)" stroke-width=".5" stroke-dasharray="3 9"/><circle cx="85" cy="22" r="3.5" fill="#00d4aa"/><circle cx="85" cy="148" r="2.5" fill="#00d4aa" opacity=".5"/></g>
          <g class="ring3"><ellipse cx="85" cy="85" rx="80" ry="80" stroke="rgba(245,166,35,.07)" stroke-width=".4" stroke-dasharray="2 11"/><circle cx="165" cy="85" r="2.5" fill="rgba(245,166,35,.55)"/><circle cx="5" cy="85" r="2" fill="rgba(0,212,170,.4)"/></g>
        </svg>
      </div>
    </div>
    <div class="status-bar">
      <div class="si"><div class="dot d-g"></div> SYSTEM ONLINE</div>
      <div class="si"><div class="dot d-a"></div> CURRENT: Python Dev @ QSpiders Noida</div>
      <div class="si"><div class="dot d-a"></div> UPSKILLING: Cloud Architect · Android</div>
      <div class="si"><div class="dot d-r"></div> COFFEE: CRITICALLY LOW</div>
    </div>
  </header>

  <section class="section reveal">
    <div class="sec-label">01 &nbsp; Operator Profile</div>
    <div class="about-grid">
      <div class="data-row"><span class="dk">FULL NAME</span><span class="dv a">Ritik Kumar</span></div>
      <div class="data-row"><span class="dk">EDUCATION</span><span class="dv t">B.Tech CSE — Class of 2025</span></div>
      <div class="data-row"><span class="dk">PRIMARY STACK</span><span class="dv">Android · AI/ML · Cloud · Frontend</span></div>
      <div class="data-row"><span class="dk">CURRENT DEPLOYMENT</span><span class="dv a">Python Dev @ QSpiders Noida</span></div>
      <div class="data-row"><span class="dk">COMMUNITY RANK</span><span class="dv t">GDG Associate Lead · 400+ Members</span></div>
      <div class="data-row"><span class="dk">EMAIL SIGNAL</span><span class="dv a">rk7703463@gmail.com</span></div>
      <div class="data-row"><span class="dk">PHONE</span><span class="dv">+91 9693149491</span></div>
      <div class="data-row"><span class="dk">VERIFIED CERTS</span><span class="dv g">14+ (IBM · Google Cloud · Android)</span></div>
    </div>
    <div class="quote-block">
      "Passionate about bridging mobile applications and intelligent systems — where clean UI meets real-world data."
      <cite>— Ritik Kumar &nbsp;·&nbsp; rk7703463@gmail.com</cite>
    </div>
  </section>

  <section class="section reveal">
    <div class="sec-label">02 &nbsp; Mission Log</div>
    <div class="exp-list">

      <div class="exp-item">
        <div class="exp-line"></div>
        <div class="exp-content">
          <div class="exp-header">
            <div><div class="exp-title">Python Developer (Trainee)</div><div class="exp-org">QSpiders Noida · Software Development</div></div>
            <div class="exp-date">05/2025 — PRESENT</div>
          </div>
          <ul class="exp-bullets">
            <li>Core Python — data types, functions, OOP, exception handling</li>
            <li>Hands-on with Django and Flask for backend development</li>
            <li>Data analysis & automation projects; SDLC & code optimization</li>
            <li>Team-oriented mini-projects to strengthen programming fundamentals</li>
          </ul>
          <span class="exp-badge">Active</span>
          <span class="exp-badge teal">Python · Django · Flask</span>
        </div>
      </div>

      <div class="exp-item">
        <div class="exp-line"></div>
        <div class="exp-content">
          <div class="exp-header">
            <div><div class="exp-title">Associate Lead — Google Developer Group</div><div class="exp-org">BPMCE, Bihar</div></div>
            <div class="exp-date">05/2024 — 05/2025</div>
          </div>
          <ul class="exp-bullets">
            <li>Led &amp; managed <strong style="color:var(--amber)">400+ member</strong> community as Arcade Facilitator, Cohort 1 (2025)</li>
            <li>Organised technical events, workshops & coding sessions on Android, Cloud, AI/ML</li>
            <li>Mentored students through Google Cloud skill badge pathways</li>
            <li>Collaborated with Google mentors on knowledge-sharing community initiatives</li>
            <li>Built leadership, communication & project management skills hands-on</li>
          </ul>
          <span class="exp-badge teal">GDG · Arcade Facilitator · Mentorship</span>
        </div>
      </div>

      <div class="exp-item">
        <div class="exp-line"></div>
        <div class="exp-content">
          <div class="exp-header">
            <div><div class="exp-title">Salesforce Developer Intern (Virtual)</div><div class="exp-org">SmartInternz · QA & Development</div></div>
            <div class="exp-date">12/2023 — 02/2024</div>
          </div>
          <ul class="exp-bullets">
            <li>Built process automations via Workflow Rules, Process Builder & Flow Builder</li>
            <li>Developed Apex classes, triggers & test classes with full code coverage</li>
            <li>Responsive UIs with Lightning Web Components (LWC) & Salesforce APIs</li>
            <li>3 Superbadges: Apex Specialist · Process Automation · Developer Super Set</li>
          </ul>
          <span class="exp-badge">Cert: SISFVIPAD2024-86867</span>
        </div>
      </div>

    </div>
  </section>

  <section class="section reveal">
    <div class="sec-label">03 &nbsp; Systems &amp; Capabilities</div>
    <div class="skills-panel">
      <div class="skill-group">
        <div class="sg-title">Mobile &amp; Android</div>
        <div class="skill-item"><span>Jetpack Compose</span><div class="sbar"><div class="sbf t" style="--w:85%"></div></div></div>
        <div class="skill-item"><span>Kotlin</span><div class="sbar"><div class="sbf t" style="--w:82%"></div></div></div>
        <div class="skill-item"><span>Firebase</span><div class="sbar"><div class="sbf t" style="--w:78%"></div></div></div>
        <div class="skill-item"><span>UI/UX Material</span><div class="sbar"><div class="sbf t" style="--w:80%"></div></div></div>
      </div>
      <div class="skill-group">
        <div class="sg-title">AI / ML &amp; Data</div>
        <div class="skill-item"><span>Python</span><div class="sbar"><div class="sbf" style="--w:88%"></div></div></div>
        <div class="skill-item"><span>Pandas / NumPy</span><div class="sbar"><div class="sbf" style="--w:80%"></div></div></div>
        <div class="skill-item"><span>Scikit-learn</span><div class="sbar"><div class="sbf" style="--w:72%"></div></div></div>
        <div class="skill-item"><span>Predictive Models</span><div class="sbar"><div class="sbf" style="--w:68%"></div></div></div>
      </div>
      <div class="skill-group">
        <div class="sg-title">Frontend</div>
        <div class="skill-item"><span>React / Next.js</span><div class="sbar"><div class="sbf t" style="--w:82%"></div></div></div>
        <div class="skill-item"><span>TypeScript</span><div class="sbar"><div class="sbf t" style="--w:74%"></div></div></div>
        <div class="skill-item"><span>Tailwind CSS</span><div class="sbar"><div class="sbf t" style="--w:90%"></div></div></div>
        <div class="skill-item"><span>HTML / CSS / JS</span><div class="sbar"><div class="sbf t" style="--w:95%"></div></div></div>
      </div>
      <div class="skill-group">
        <div class="sg-title">Cloud &amp; Tools</div>
        <div class="skill-item"><span>Google Cloud (GCP)</span><div class="sbar"><div class="sbf g" style="--w:78%"></div></div></div>
        <div class="skill-item"><span>Firebase / REST APIs</span><div class="sbar"><div class="sbf g" style="--w:80%"></div></div></div>
        <div class="skill-item"><span>Salesforce / LWC</span><div class="sbar"><div class="sbf g" style="--w:65%"></div></div></div>
        <div class="skill-item"><span>Git / GitHub</span><div class="sbar"><div class="sbf g" style="--w:88%"></div></div></div>
      </div>
    </div>
  </section>

  <section class="section reveal">
    <div class="sec-label">04 &nbsp; Verified Credentials</div>
    <div class="cert-grid">
      <div class="cert-item ibm"><div class="cert-provider ibm">IBM</div>Data Science</div>
      <div class="cert-item"><div class="cert-provider google">Google Cloud</div>Cloud Architect Prep</div>
      <div class="cert-item"><div class="cert-provider google">Google Cloud</div>Core Infrastructure</div>
      <div class="cert-item"><div class="cert-provider google">Google Cloud</div>Essential Infra: Core Services</div>
      <div class="cert-item"><div class="cert-provider google">Google Cloud</div>Essential Infra: Foundation</div>
      <div class="cert-item"><div class="cert-provider google">Google Cloud</div>Elastic Infra: Scaling & Automation</div>
      <div class="cert-item"><div class="cert-provider google">Google Cloud</div>Kubernetes Engine: Foundations</div>
      <div class="cert-item"><div class="cert-provider google">Google Cloud</div>Reliable Infra: Design & Process</div>
      <div class="cert-item"><div class="cert-provider other">Android</div>App Components: Services & IPC</div>
      <div class="cert-item"><div class="cert-provider other">Android</div>Intents, Activities & Receivers</div>
      <div class="cert-item ibm"><div class="cert-provider ibm">IBM</div>Intro to Web Dev: HTML, CSS, JS</div>
      <div class="cert-item ibm"><div class="cert-provider ibm">IBM</div>Intro to Cloud Computing</div>
      <div class="cert-item ibm"><div class="cert-provider ibm">IBM</div>Getting Started with Git & GitHub</div>
    </div>
  </section>

  <section class="section reveal">
    <div class="sec-label">05 &nbsp; Mission Telemetry</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-label">Community Led</div>
        <div class="stat-value">400<span style="font-size:22px">+</span></div>
        <div class="stat-sub">GDG MEMBERS</div>
        <div class="stat-icon">👥</div>
      </div>
      <div class="stat-card tc">
        <div class="stat-label">Certifications</div>
        <div class="stat-value t">14<span style="font-size:22px">+</span></div>
        <div class="stat-sub">VERIFIED BADGES</div>
        <div class="stat-icon">🏅</div>
      </div>
      <div class="stat-card">
        <div class="stat-label">Superbadges</div>
        <div class="stat-value">3</div>
        <div class="stat-sub">SALESFORCE</div>
        <div class="stat-icon">⚡</div>
      </div>
      <div class="stat-card tc">
        <div class="stat-label">Tech Stacks</div>
        <div class="stat-value t">15<span style="font-size:22px">+</span></div>
        <div class="stat-sub">TECHNOLOGIES</div>
        <div class="stat-icon">🛰️</div>
      </div>
    </div>
    <div style="margin-top:28px;">
      <div style="font-size:9px;color:var(--muted);letter-spacing:2.5px;text-transform:uppercase;margin-bottom:10px;">Contribution Heatmap</div>
      <div class="heatmap-wrap"><div class="activity-grid" id="heatmap"></div></div>
    </div>
  </section>

  <section class="section reveal">
    <div class="sec-label">06 &nbsp; Communication Channels</div>
    <div class="comms-grid">
      <a class="comm-link tl" href="https://www.linkedin.com/in/u-r-ri8/" target="_blank">
        <svg class="ci" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="comm-link" href="mailto:rk7703463@gmail.com">
        <svg class="ci" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        Email
      </a>
      <a class="comm-link" href="https://github.com/ritik12122001" target="_blank">
        <svg class="ci" viewBox="0 0 24 24" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        GitHub
      </a>
      <a class="comm-link" href="https://leetcode.com" target="_blank">
        <svg class="ci" viewBox="0 0 24 24" fill="currentColor"><path d="M13.483 0a1.374 1.374 0 0 0-.961.438L7.116 6.226l-3.854 4.126a5.266 5.266 0 0 0-1.209 2.104 5.35 5.35 0 0 0-.125.513 5.527 5.527 0 0 0 .062 2.362 5.83 5.83 0 0 0 .349 1.017 5.938 5.938 0 0 0 1.271 1.818l4.277 4.193.039.038c2.248 2.165 5.852 2.133 8.063-.074l2.396-2.392c.54-.54.54-1.414.003-1.955a1.378 1.378 0 0 0-1.951-.003l-2.396 2.392a3.021 3.021 0 0 1-4.205.038l-.02-.019-4.276-4.193c-.652-.64-.972-1.469-.948-2.263a2.68 2.68 0 0 1 .066-.523 2.545 2.545 0 0 1 .619-1.164L9.13 8.114c1.058-1.134 3.204-1.27 4.43-.278l3.501 2.831c.593.48 1.461.387 1.94-.207a1.384 1.384 0 0 0-.207-1.943l-3.5-2.831c-.8-.647-1.766-1.045-2.774-1.202l2.015-2.158A1.384 1.384 0 0 0 13.483 0zm-2.866 12.815a1.38 1.38 0 0 0-1.38 1.382 1.38 1.38 0 0 0 1.38 1.382H20.79a1.38 1.38 0 0 0 1.38-1.382 1.38 1.38 0 0 0-1.38-1.382z"/></svg>
        LeetCode
      </a>
      <a class="comm-link tl" href="https://codechef.com" target="_blank">
        <svg class="ci" viewBox="0 0 24 24" fill="currentColor"><path d="M11.257.004C5.979.145 1.007 4.035.088 9.385c-.641 3.784.872 7.543 3.847 9.961 2.09 1.699 4.874 2.645 7.682 2.645.195 0 .389-.004.583-.012 5.278-.142 10.25-4.031 11.169-9.381.641-3.784-.872-7.543-3.847-9.962C17.432.936 14.648-.009 11.84-.009l-.583.013z"/></svg>
        CodeChef
      </a>
      <a class="comm-link" href="https://instagram.com" target="_blank">
        <svg class="ci" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
        Instagram
      </a>
    </div>
  </section>

  <footer class="footer reveal">
    <div class="footer-left">
      <div style="margin-bottom:5px;">RITIK KUMAR &nbsp;·&nbsp; <strong>ANDROID DEV · AI/ML · CLOUD</strong></div>
      <div>B.Tech CSE '25 &nbsp;·&nbsp; GDG Associate Lead &nbsp;·&nbsp; <strong>+91 9693149491</strong></div>
      <div style="margin-top:6px;color:var(--muted);">built from scratch. no templates. no shortcuts.<span class="cursor"></span></div>
    </div>
    <div style="font-size:10px;color:var(--muted);display:flex;align-items:center;gap:7px;letter-spacing:1px;">
      <div class="dot d-g"></div> PROFILE ONLINE
    </div>
  </footer>

</div>
<script>
function tick(){const n=new Date(),p=x=>String(x).padStart(2,'0');document.getElementById('live-clock').textContent=`${p(n.getHours())}:${p(n.getMinutes())}:${p(n.getSeconds())} IST`;}
setInterval(tick,1000);tick();
const hm=document.getElementById('heatmap'),lv=[0,0,0,0,1,1,1,2,2,2,3,3,4];
for(let w=0;w<52;w++){const wk=document.createElement('div');wk.className='activity-week';for(let d=0;d<7;d++){const day=document.createElement('div');day.className=`activity-day l${lv[Math.floor(Math.random()*lv.length)]}`;wk.appendChild(day);}hm.appendChild(wk);}
const obs=new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting)e.target.classList.add('visible');}),{threshold:.08});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));
const bars=document.querySelectorAll('.sbf');
const bo=new IntersectionObserver(es=>{es.forEach((e,i)=>{if(e.isIntersecting)setTimeout(()=>{e.target.style.animationPlayState='running';},i*70);});},{threshold:.4});
bars.forEach(b=>{b.style.animationPlayState='paused';bo.observe(b);});
</script>
</body>
</html>

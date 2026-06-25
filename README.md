<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Runak Das — GitHub Profile README</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500&family=Syne:wght@700;800&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg: #0a0a0f;
    --bg2: #0f0f1a;
    --card: #12121e;
    --border: rgba(120, 80, 255, 0.18);
    --accent: #7c3aed;
    --accent2: #a855f7;
    --glow: #c084fc;
    --gold: #f59e0b;
    --cyan: #22d3ee;
    --green: #10b981;
    --text: #e2e8f0;
    --muted: #64748b;
    --dim: #94a3b8;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Ambient background */
  body::before {
    content: '';
    position: fixed;
    top: -50%;
    left: -20%;
    width: 70%;
    height: 70%;
    background: radial-gradient(ellipse, rgba(124, 58, 237, 0.12) 0%, transparent 70%);
    pointer-events: none;
    animation: drift 8s ease-in-out infinite alternate;
  }
  body::after {
    content: '';
    position: fixed;
    bottom: -30%;
    right: -10%;
    width: 60%;
    height: 60%;
    background: radial-gradient(ellipse, rgba(34, 211, 238, 0.07) 0%, transparent 70%);
    pointer-events: none;
    animation: drift 10s ease-in-out infinite alternate-reverse;
  }
  @keyframes drift { 0% { transform: translate(0,0); } 100% { transform: translate(30px, 20px); } }

  .wrapper {
    max-width: 900px;
    margin: 0 auto;
    padding: 48px 24px;
    position: relative;
    z-index: 1;
  }

  /* ─── HERO ─── */
  .hero {
    display: flex;
    gap: 40px;
    align-items: center;
    margin-bottom: 56px;
    padding: 40px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent), var(--glow), var(--cyan), transparent);
    animation: scan 3s linear infinite;
  }
  @keyframes scan { 0% { opacity: 0.4; } 50% { opacity: 1; } 100% { opacity: 0.4; } }

  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
  }
  .avatar-ring {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--cyan));
    padding: 3px;
    animation: spin-ring 6s linear infinite;
  }
  @keyframes spin-ring {
    0% { box-shadow: 0 0 0 0 rgba(124,58,237,0.4), 0 0 20px rgba(34,211,238,0.3); }
    50% { box-shadow: 0 0 0 8px rgba(124,58,237,0), 0 0 30px rgba(34,211,238,0.5); }
    100% { box-shadow: 0 0 0 0 rgba(124,58,237,0.4), 0 0 20px rgba(34,211,238,0.3); }
  }
  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--bg2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 40px;
    font-weight: 800;
    color: var(--glow);
    letter-spacing: -1px;
  }

  .status-dot {
    position: absolute;
    bottom: 6px;
    right: 6px;
    width: 18px;
    height: 18px;
    background: var(--green);
    border-radius: 50%;
    border: 3px solid var(--bg);
    animation: pulse-dot 2s ease infinite;
  }
  @keyframes pulse-dot {
    0%, 100% { box-shadow: 0 0 0 0 rgba(16,185,129,0.5); }
    50% { box-shadow: 0 0 0 6px rgba(16,185,129,0); }
  }

  .hero-text { flex: 1; }

  .hero-eyebrow {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--accent2);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .hero-eyebrow span { color: var(--cyan); }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: 42px;
    font-weight: 800;
    line-height: 1;
    background: linear-gradient(135deg, #fff 30%, var(--glow) 70%, var(--cyan));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 6px;
  }

  .hero-handle {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 16px;
  }
  .hero-handle strong { color: var(--accent2); }

  .hero-bio {
    font-size: 14px;
    color: var(--dim);
    line-height: 1.7;
    max-width: 440px;
    margin-bottom: 20px;
  }

  .hero-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    padding: 4px 10px;
    border-radius: 6px;
    border: 1px solid;
  }
  .tag-purple { color: var(--glow); border-color: rgba(192,132,252,0.3); background: rgba(124,58,237,0.1); }
  .tag-cyan { color: var(--cyan); border-color: rgba(34,211,238,0.3); background: rgba(34,211,238,0.08); }
  .tag-gold { color: var(--gold); border-color: rgba(245,158,11,0.3); background: rgba(245,158,11,0.08); }
  .tag-green { color: var(--green); border-color: rgba(16,185,129,0.3); background: rgba(16,185,129,0.08); }

  /* ─── SECTION HEADER ─── */
  .section-label {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 20px;
  }
  .section-label span {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent2);
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ─── TYPING TERMINAL ─── */
  .terminal {
    background: #0c0c14;
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px 28px;
    margin-bottom: 36px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    position: relative;
    overflow: hidden;
  }
  .terminal-bar {
    display: flex;
    gap: 6px;
    margin-bottom: 20px;
  }
  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }

  .t-line { margin-bottom: 6px; line-height: 1.7; }
  .t-prompt { color: var(--accent2); }
  .t-cmd { color: var(--cyan); }
  .t-key { color: var(--gold); }
  .t-val { color: var(--green); }
  .t-muted { color: var(--muted); }
  .cursor {
    display: inline-block;
    width: 8px;
    height: 14px;
    background: var(--glow);
    vertical-align: middle;
    animation: blink 1s step-end infinite;
  }
  @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

  /* ─── STATS GRID ─── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    margin-bottom: 36px;
  }
  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 22px 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
  }
  .stat-card:hover { border-color: var(--accent); transform: translateY(-3px); }
  .stat-card::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--gradient, linear-gradient(90deg, var(--accent), var(--glow)));
  }
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 36px;
    font-weight: 800;
    line-height: 1;
    margin-bottom: 4px;
  }
  .stat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  /* ─── PROJECTS ─── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 36px;
  }
  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
    cursor: default;
  }
  .project-card:hover { border-color: var(--card-accent, var(--accent)); transform: translateY(-3px); }
  .project-card::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: var(--card-grad, linear-gradient(90deg, var(--accent), var(--glow)));
  }

  .project-icon { font-size: 28px; margin-bottom: 12px; }
  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 17px;
    font-weight: 700;
    margin-bottom: 6px;
    color: #fff;
  }
  .project-desc {
    font-size: 12.5px;
    color: var(--dim);
    line-height: 1.6;
    margin-bottom: 14px;
  }
  .project-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }
  .pill {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    padding: 3px 8px;
    border-radius: 4px;
    background: rgba(255,255,255,0.05);
    color: var(--dim);
    border: 1px solid rgba(255,255,255,0.08);
  }

  /* ─── TECH STACK ─── */
  .tech-section { margin-bottom: 36px; }
  .tech-category { margin-bottom: 20px; }
  .tech-cat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .tech-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }
  .tech-badge {
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 7px 14px;
    border-radius: 8px;
    background: var(--card);
    border: 1px solid var(--border);
    font-size: 12px;
    font-weight: 500;
    transition: border-color 0.2s, transform 0.2s;
  }
  .tech-badge:hover { transform: translateY(-2px); border-color: var(--accent2); }
  .tech-icon { font-size: 16px; }

  /* ─── SKILL BARS ─── */
  .skills-section { margin-bottom: 36px; }
  .skill-item { margin-bottom: 16px; }
  .skill-header {
    display: flex;
    justify-content: space-between;
    margin-bottom: 6px;
  }
  .skill-name { font-size: 13px; font-weight: 500; }
  .skill-pct { font-family: 'JetBrains Mono', monospace; font-size: 12px; color: var(--accent2); }
  .skill-bar {
    height: 5px;
    background: rgba(255,255,255,0.06);
    border-radius: 4px;
    overflow: hidden;
  }
  .skill-fill {
    height: 100%;
    border-radius: 4px;
    background: var(--bar-grad, linear-gradient(90deg, var(--accent), var(--glow)));
    animation: fillup 1.5s cubic-bezier(0.22,1,0.36,1) forwards;
    transform-origin: left;
  }
  @keyframes fillup { from { transform: scaleX(0); } to { transform: scaleX(1); } }

  /* ─── GITHUB STREAK ─── */
  .streak-box {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 30px;
    text-align: center;
    margin-bottom: 36px;
    position: relative;
    overflow: hidden;
  }
  .streak-box::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at 50% 120%, rgba(124,58,237,0.15) 0%, transparent 60%);
  }
  .streak-num {
    font-family: 'Syne', sans-serif;
    font-size: 72px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--gold), #f97316);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
  }
  .streak-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-top: 4px;
  }
  .streak-sub {
    font-size: 13px;
    color: var(--dim);
    margin-top: 12px;
  }
  .streak-sub strong { color: var(--glow); }

  /* ─── CONNECT ─── */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 36px;
  }
  .connect-btn {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    padding: 18px 12px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    text-decoration: none;
    font-size: 12px;
    color: var(--dim);
    transition: all 0.3s;
    font-family: 'JetBrains Mono', monospace;
  }
  .connect-btn:hover { border-color: var(--btn-accent, var(--accent)); color: #fff; transform: translateY(-3px); }
  .connect-icon { font-size: 22px; }

  /* ─── FOOTER ─── */
  .footer {
    text-align: center;
    padding: 24px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    border-top: 1px solid var(--border);
    margin-top: 8px;
  }
  .footer span { color: var(--accent2); }
  .footer .glow-text {
    background: linear-gradient(90deg, var(--accent), var(--glow));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-weight: 600;
  }

  /* animated banner */
  .banner {
    text-align: center;
    padding: 16px;
    background: linear-gradient(90deg, rgba(124,58,237,0.15), rgba(34,211,238,0.1), rgba(124,58,237,0.15));
    border: 1px solid var(--border);
    border-radius: 12px;
    margin-bottom: 28px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--cyan);
    letter-spacing: 1px;
    position: relative;
    overflow: hidden;
  }
  .banner::before {
    content: '';
    position: absolute;
    top: 0; left: -100%; width: 60%; height: 100%;
    background: linear-gradient(90deg, transparent, rgba(124,58,237,0.15), transparent);
    animation: slide-light 3s linear infinite;
  }
  @keyframes slide-light { to { left: 160%; } }

  @media (max-width: 640px) {
    .hero { flex-direction: column; text-align: center; }
    .projects-grid { grid-template-columns: 1fr; }
    .stats-grid { grid-template-columns: 1fr 1fr; }
    .connect-grid { grid-template-columns: 1fr 1fr; }
    .hero-bio { max-width: 100%; }
    .hero-tags { justify-content: center; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- BANNER -->
  <div class="banner">⚡ Open to internships & collabs — Building in public since 2024</div>

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar-ring">
        <div class="avatar-inner">RD</div>
      </div>
      <div class="status-dot"></div>
    </div>
    <div class="hero-text">
      <div class="hero-eyebrow">// <span>hello, world</span> — I'm</div>
      <div class="hero-name">Runak Das</div>
      <div class="hero-handle"><strong>@Ruru2810</strong> · he/him · Parul University</div>
      <div class="hero-bio">
        🚀 B.Tech AI & DS student obsessed with building smart, slick software. 
        I live at the intersection of <strong style="color:#c084fc">AI</strong>, <strong style="color:#22d3ee">Web Dev</strong> & <strong style="color:#f59e0b">Problem Solving</strong>. 
        On a journey to 30+ LPA — one commit at a time.
      </div>
      <div class="hero-tags">
        <span class="tag tag-purple">🤖 AI/ML</span>
        <span class="tag tag-cyan">🌐 Web Dev</span>
        <span class="tag tag-gold">⚡ React</span>
        <span class="tag tag-green">📍 Vadodara, IN</span>
      </div>
    </div>
  </div>

  <!-- TERMINAL -->
  <div class="section-label"><span>// about.json</span></div>
  <div class="terminal">
    <div class="terminal-bar">
      <div class="dot dot-r"></div>
      <div class="dot dot-y"></div>
      <div class="dot dot-g"></div>
    </div>
    <div class="t-line"><span class="t-prompt">runak@dev</span><span class="t-muted">:~$</span> <span class="t-cmd">cat about.json</span></div>
    <div class="t-line" style="margin-top: 12px;">{</div>
    <div class="t-line">&nbsp;&nbsp;<span class="t-key">"name"</span>: <span class="t-val">"Runak Das"</span>,</div>
    <div class="t-line">&nbsp;&nbsp;<span class="t-key">"role"</span>: <span class="t-val">"AI & DS Student @ Parul University"</span>,</div>
    <div class="t-line">&nbsp;&nbsp;<span class="t-key">"building"</span>: [<span class="t-val">"RURU AI"</span>, <span class="t-val">"Runiqode"</span>, <span class="t-val">"next big thing 👀"</span>],</div>
    <div class="t-line">&nbsp;&nbsp;<span class="t-key">"learning"</span>: [<span class="t-val">"LLM internals"</span>, <span class="t-val">"FastAPI"</span>, <span class="t-val">"Electron"</span>],</div>
    <div class="t-line">&nbsp;&nbsp;<span class="t-key">"goal"</span>: <span class="t-val">"30+ LPA &amp; products that matter"</span>,</div>
    <div class="t-line">&nbsp;&nbsp;<span class="t-key">"funFact"</span>: <span class="t-val">"I talk to my AI like it's my co-founder"</span></div>
    <div class="t-line">} <span class="cursor"></span></div>
  </div>

  <!-- STATS -->
  <div class="section-label"><span>// metrics</span></div>
  <div class="stats-grid">
    <div class="stat-card" style="--gradient: linear-gradient(90deg, #7c3aed, #a855f7)">
      <div class="stat-num" style="color: #c084fc">4+</div>
      <div class="stat-label">Projects Built</div>
    </div>
    <div class="stat-card" style="--gradient: linear-gradient(90deg, #0891b2, #22d3ee)">
      <div class="stat-num" style="color: #22d3ee">17</div>
      <div class="stat-label">Languages Supported</div>
    </div>
    <div class="stat-card" style="--gradient: linear-gradient(90deg, #d97706, #f59e0b)">
      <div class="stat-num" style="color: #f59e0b">∞</div>
      <div class="stat-label">Ideas / Day</div>
    </div>
  </div>

  <!-- FEATURED PROJECTS -->
  <div class="section-label"><span>// featured.projects</span></div>
  <div class="projects-grid">

    <div class="project-card" style="--card-accent: #a855f7; --card-grad: linear-gradient(90deg, #7c3aed, #c084fc)">
      <div class="project-icon">🤖</div>
      <div class="project-name">RURU AI</div>
      <div class="project-desc">Voice-interactive AI companion with Hinglish personality, plasma orb UI, long-term memory & Gemini 2.5 Flash backend.</div>
      <div class="project-pills">
        <span class="pill">React</span>
        <span class="pill">Gemini 2.5</span>
        <span class="pill">FastAPI</span>
        <span class="pill">Web Speech API</span>
        <span class="pill">Electron</span>
      </div>
    </div>

    <div class="project-card" style="--card-accent: #22d3ee; --card-grad: linear-gradient(90deg, #0891b2, #22d3ee)">
      <div class="project-icon">🚀</div>
      <div class="project-name">Runiqode</div>
      <div class="project-desc">Multi-language online compiler supporting 17 languages in a deep-space dark animated interface powered by the Piston API.</div>
      <div class="project-pills">
        <span class="pill">React</span>
        <span class="pill">Piston API</span>
        <span class="pill">17 languages</span>
        <span class="pill">Dark UI</span>
      </div>
    </div>

    <div class="project-card" style="--card-accent: #f59e0b; --card-grad: linear-gradient(90deg, #d97706, #f59e0b)">
      <div class="project-icon">📋</div>
      <div class="project-name">Taskmanager Runak</div>
      <div class="project-desc">Clean task management app built in JavaScript — organize, prioritize, and crush your to-do list.</div>
      <div class="project-pills">
        <span class="pill">JavaScript</span>
        <span class="pill">Productivity</span>
      </div>
    </div>

    <div class="project-card" style="--card-accent: #10b981; --card-grad: linear-gradient(90deg, #059669, #10b981)">
      <div class="project-icon">🏆</div>
      <div class="project-name">Hackathon</div>
      <div class="project-desc">Hackathon project repo — where speed meets creativity under the clock. Details inside.</div>
      <div class="project-pills">
        <span class="pill">HTML</span>
        <span class="pill">Fast-built</span>
      </div>
    </div>

  </div>

  <!-- TECH STACK -->
  <div class="section-label"><span>// tech.stack</span></div>
  <div class="tech-section">
    <div class="tech-category">
      <div class="tech-cat-label">// Frontend</div>
      <div class="tech-row">
        <span class="tech-badge"><span class="tech-icon">⚛️</span> React</span>
        <span class="tech-badge"><span class="tech-icon">🌐</span> HTML/CSS</span>
        <span class="tech-badge"><span class="tech-icon">✨</span> JavaScript</span>
        <span class="tech-badge"><span class="tech-icon">🎨</span> Tailwind</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-cat-label">// Backend & AI</div>
      <div class="tech-row">
        <span class="tech-badge"><span class="tech-icon">🐍</span> Python</span>
        <span class="tech-badge"><span class="tech-icon">⚡</span> FastAPI</span>
        <span class="tech-badge"><span class="tech-icon">🤖</span> Gemini API</span>
        <span class="tech-badge"><span class="tech-icon">🔥</span> Node.js</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-cat-label">// Tools</div>
      <div class="tech-row">
        <span class="tech-badge"><span class="tech-icon">🐙</span> Git</span>
        <span class="tech-badge"><span class="tech-icon">🖥️</span> Electron</span>
        <span class="tech-badge"><span class="tech-icon">🔗</span> REST APIs</span>
        <span class="tech-badge"><span class="tech-icon">📦</span> VS Code</span>
      </div>
    </div>
  </div>

  <!-- SKILL BARS -->
  <div class="section-label"><span>// proficiency</span></div>
  <div class="skills-section">
    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">React / Frontend</span>
        <span class="skill-pct">88%</span>
      </div>
      <div class="skill-bar"><div class="skill-fill" style="width:88%; --bar-grad: linear-gradient(90deg,#7c3aed,#c084fc)"></div></div>
    </div>
    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">AI / LLM Integration</span>
        <span class="skill-pct">82%</span>
      </div>
      <div class="skill-bar"><div class="skill-fill" style="width:82%; --bar-grad: linear-gradient(90deg,#0891b2,#22d3ee)"></div></div>
    </div>
    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">Python / FastAPI</span>
        <span class="skill-pct">74%</span>
      </div>
      <div class="skill-bar"><div class="skill-fill" style="width:74%; --bar-grad: linear-gradient(90deg,#059669,#10b981)"></div></div>
    </div>
    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">Problem Solving</span>
        <span class="skill-pct">90%</span>
      </div>
      <div class="skill-bar"><div class="skill-fill" style="width:90%; --bar-grad: linear-gradient(90deg,#d97706,#f59e0b)"></div></div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section-label"><span>// connect.with.me</span></div>
  <div class="connect-grid">
    <a class="connect-btn" href="mailto:runakdas00067@gmail.com" style="--btn-accent:#ea4335">
      <span class="connect-icon">📧</span>
      <span>Email</span>
    </a>
    <a class="connect-btn" href="https://github.com/Ruru2810" style="--btn-accent:#a855f7">
      <span class="connect-icon">🐙</span>
      <span>GitHub</span>
    </a>
    <a class="connect-btn" href="#" style="--btn-accent:#0077b5">
      <span class="connect-icon">💼</span>
      <span>LinkedIn</span>
    </a>
    <a class="connect-btn" href="#" style="--btn-accent:#22d3ee">
      <span class="connect-icon">🌐</span>
      <span>Portfolio</span>
    </a>
  </div>

  <div class="footer">
    <div style="margin-bottom: 8px;">
      <span class="glow-text">⚡ Let's build something legendary together</span>
    </div>
    <div>Made with <span>💜</span> by <span>Runak Das</span> · profile views <span style="color:var(--green)">↑</span></div>
  </div>

</div>
</body>
</html>

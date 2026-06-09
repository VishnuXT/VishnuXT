
<style>
  @import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@400;500;600;700&family=Orbitron:wght@400;700;900&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .readme-wrap {
    background: #050505;
    color: #e2e8f0;
    font-family: 'Rajdhani', sans-serif;
    min-height: 100vh;
    padding: 0;
    overflow: hidden;
  }

  .scanlines {
    position: fixed; top: 0; left: 0; right: 0; bottom: 0;
    background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,255,255,0.015) 2px, rgba(0,255,255,0.015) 4px);
    pointer-events: none; z-index: 0;
  }

  .content { position: relative; z-index: 1; }

  /* HERO */
  .hero {
    padding: 60px 32px 40px;
    text-align: center;
    border-bottom: 1px solid rgba(0,255,255,0.15);
    position: relative;
  }

  .hero-grid {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(0,255,255,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,255,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
  }

  .status-pill {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(0,255,100,0.08);
    border: 1px solid rgba(0,255,100,0.3);
    border-radius: 20px;
    padding: 6px 16px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    color: #00ff64;
    margin-bottom: 24px;
  }

  .status-dot {
    width: 6px; height: 6px; border-radius: 50%;
    background: #00ff64;
    animation: pulse 2s infinite;
  }

  @keyframes pulse { 0%,100%{opacity:1;} 50%{opacity:0.3;} }

  .hero-name {
    font-family: 'Orbitron', monospace;
    font-size: clamp(48px, 10vw, 80px);
    font-weight: 900;
    letter-spacing: 8px;
    line-height: 1;
    margin-bottom: 8px;
    background: linear-gradient(135deg, #00d4ff 0%, #b400ff 50%, #00d4ff 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-sub {
    font-family: 'Share Tech Mono', monospace;
    font-size: 14px;
    color: rgba(0,212,255,0.7);
    letter-spacing: 3px;
    margin-bottom: 20px;
  }

  .typing-display {
    font-family: 'Share Tech Mono', monospace;
    font-size: 18px;
    color: #b400ff;
    min-height: 28px;
    margin-bottom: 28px;
  }

  .cursor { animation: blink 1s infinite; }
  @keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0;} }

  .hero-badges {
    display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;
    margin-bottom: 28px;
  }

  .badge {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    padding: 5px 12px;
    border-radius: 4px;
    border: 1px solid;
    letter-spacing: 1px;
  }
  .badge-cyan { color: #00d4ff; border-color: rgba(0,212,255,0.4); background: rgba(0,212,255,0.06); }
  .badge-purple { color: #b400ff; border-color: rgba(180,0,255,0.4); background: rgba(180,0,255,0.06); }
  .badge-green { color: #00ff64; border-color: rgba(0,255,100,0.4); background: rgba(0,255,100,0.06); }

  .hero-btns {
    display: flex; flex-wrap: wrap; justify-content: center; gap: 12px;
    margin-bottom: 36px;
  }

  .btn {
    font-family: 'Orbitron', monospace;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    padding: 10px 22px;
    border-radius: 4px;
    border: none;
    cursor: pointer;
    transition: all 0.2s;
    text-transform: uppercase;
  }

  .btn-primary {
    background: linear-gradient(135deg, #00d4ff, #b400ff);
    color: #fff;
  }
  .btn-primary:hover { opacity: 0.85; transform: translateY(-2px); }

  .btn-outline {
    background: transparent;
    color: #00d4ff;
    border: 1px solid rgba(0,212,255,0.5);
  }
  .btn-outline:hover { background: rgba(0,212,255,0.1); transform: translateY(-2px); }

  .social-links {
    display: flex; justify-content: center; gap: 16px;
    flex-wrap: wrap;
  }

  .social-link {
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    color: rgba(226,232,240,0.5);
    text-decoration: none;
    display: flex; align-items: center; gap: 6px;
    transition: color 0.2s;
  }
  .social-link:hover { color: #00d4ff; }
  .social-link i { font-size: 16px; }

  /* SECTION LAYOUT */
  .section {
    padding: 36px 32px;
    border-bottom: 1px solid rgba(0,255,255,0.08);
  }

  .section-header {
    display: flex; align-items: center; gap: 12px;
    margin-bottom: 24px;
  }

  .section-tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    color: rgba(0,212,255,0.5);
    letter-spacing: 3px;
    text-transform: uppercase;
  }

  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: 20px;
    font-weight: 700;
    color: #e2e8f0;
    letter-spacing: 2px;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, rgba(0,212,255,0.3), transparent);
  }

  /* STATS GRID */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 12px;
  }

  .stat-card {
    background: rgba(15,23,42,0.8);
    border: 1px solid rgba(0,212,255,0.15);
    border-radius: 8px;
    padding: 16px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .stat-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, #00d4ff, transparent);
  }

  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 28px;
    font-weight: 900;
    color: #00d4ff;
    display: block;
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    color: rgba(226,232,240,0.4);
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  /* SKILL BARS */
  .skill-grid { display: flex; flex-direction: column; gap: 14px; }

  .skill-row { }

  .skill-meta {
    display: flex; justify-content: space-between; align-items: center;
    margin-bottom: 6px;
  }

  .skill-name {
    font-family: 'Rajdhani', sans-serif;
    font-size: 14px;
    font-weight: 600;
    color: #e2e8f0;
    letter-spacing: 1px;
  }

  .skill-pct {
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px;
    color: #00d4ff;
  }

  .skill-track {
    height: 6px;
    background: rgba(255,255,255,0.06);
    border-radius: 3px;
    overflow: hidden;
    position: relative;
  }

  .skill-fill {
    height: 100%;
    border-radius: 3px;
    position: relative;
    transition: width 1s ease;
  }

  .skill-fill::after {
    content: '';
    position: absolute; right: 0; top: -2px;
    width: 10px; height: 10px;
    border-radius: 50%;
    background: inherit;
    filter: blur(4px);
  }

  .fill-cyan { background: linear-gradient(90deg, #003d4d, #00d4ff); }
  .fill-purple { background: linear-gradient(90deg, #2d0040, #b400ff); }
  .fill-teal { background: linear-gradient(90deg, #004040, #00ffcc); }
  .fill-green { background: linear-gradient(90deg, #003300, #00ff64); }
  .fill-orange { background: linear-gradient(90deg, #3d2000, #ff8c00); }

  /* SKILL CHIPS */
  .chips { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 12px; }

  .chip {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    padding: 4px 10px;
    border-radius: 3px;
    border: 1px solid rgba(0,212,255,0.2);
    color: rgba(0,212,255,0.7);
    background: rgba(0,212,255,0.05);
    letter-spacing: 0.5px;
  }

  .chip.purple { border-color: rgba(180,0,255,0.25); color: rgba(180,0,255,0.8); background: rgba(180,0,255,0.05); }
  .chip.green { border-color: rgba(0,255,100,0.25); color: rgba(0,255,100,0.7); background: rgba(0,255,100,0.05); }
  .chip.orange { border-color: rgba(255,140,0,0.25); color: rgba(255,140,0,0.7); background: rgba(255,140,0,0.05); }

  /* SKILL GROUPS */
  .skill-group {
    background: rgba(15,23,42,0.6);
    border: 1px solid rgba(0,212,255,0.1);
    border-radius: 8px;
    padding: 20px;
    margin-bottom: 16px;
  }

  .group-header {
    display: flex; justify-content: space-between; align-items: center;
    margin-bottom: 12px;
  }

  .group-title {
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  .level-badge {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 12px;
    border: 1px solid;
  }

  /* GITHUB DASHBOARD */
  .gh-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 12px;
    margin-bottom: 20px;
  }

  .gh-card {
    background: rgba(15,23,42,0.8);
    border: 1px solid rgba(0,212,255,0.12);
    border-radius: 8px;
    padding: 14px;
    text-align: center;
  }

  .gh-icon { font-size: 20px; margin-bottom: 8px; color: #00d4ff; }
  .gh-val {
    font-family: 'Orbitron', monospace;
    font-size: 22px; font-weight: 700;
    color: #00d4ff; display: block;
  }
  .gh-lab {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px; color: rgba(226,232,240,0.4);
    letter-spacing: 1.5px; text-transform: uppercase;
  }

  /* CONTRIBUTION GRID */
  .contrib-wrap {
    background: rgba(15,23,42,0.6);
    border: 1px solid rgba(0,212,255,0.1);
    border-radius: 8px;
    padding: 20px;
  }

  .contrib-title {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px; color: rgba(0,212,255,0.5);
    letter-spacing: 2px; text-transform: uppercase;
    margin-bottom: 14px;
  }

  .contrib-grid {
    display: flex; gap: 3px; flex-wrap: wrap;
  }

  .contrib-week { display: flex; flex-direction: column; gap: 3px; }

  .contrib-day {
    width: 11px; height: 11px;
    border-radius: 2px;
  }

  /* LANG BARS */
  .lang-bar-wrap { margin-top: 16px; }
  .lang-combined {
    height: 8px; border-radius: 4px; overflow: hidden;
    display: flex; margin-bottom: 12px;
  }
  .lang-seg { height: 100%; }
  .lang-legend { display: flex; flex-wrap: wrap; gap: 12px; }
  .lang-item {
    display: flex; align-items: center; gap: 6px;
    font-family: 'Share Tech Mono', monospace; font-size: 11px;
    color: rgba(226,232,240,0.6);
  }
  .lang-dot { width: 8px; height: 8px; border-radius: 50%; }

  /* TIMELINE */
  .timeline { position: relative; padding-left: 24px; }
  .timeline::before {
    content: '';
    position: absolute; left: 0; top: 8px; bottom: 0;
    width: 1px; background: linear-gradient(180deg, #00d4ff, rgba(180,0,255,0.3), transparent);
  }

  .tl-item {
    position: relative; margin-bottom: 28px;
  }

  .tl-dot {
    position: absolute; left: -28px; top: 4px;
    width: 10px; height: 10px; border-radius: 50%;
    border: 2px solid #00d4ff;
    background: #00d4ff;
    box-shadow: 0 0 8px #00d4ff;
  }

  .tl-year {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px; color: #00d4ff;
    letter-spacing: 2px; margin-bottom: 4px;
  }

  .tl-role {
    font-family: 'Orbitron', monospace;
    font-size: 13px; font-weight: 700;
    color: #e2e8f0; letter-spacing: 1px;
    margin-bottom: 4px;
  }

  .tl-desc {
    font-size: 13px; color: rgba(226,232,240,0.5);
    line-height: 1.6;
  }

  /* ACHIEVEMENTS */
  .ach-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 12px;
  }

  .ach-card {
    background: rgba(15,23,42,0.6);
    border: 1px solid rgba(0,212,255,0.12);
    border-radius: 8px;
    padding: 14px 12px;
    text-align: center;
    transition: border-color 0.2s, transform 0.2s;
    cursor: default;
  }
  .ach-card:hover { border-color: rgba(0,212,255,0.5); transform: translateY(-3px); }

  .ach-icon { font-size: 24px; margin-bottom: 8px; }
  .ach-name {
    font-family: 'Rajdhani', sans-serif;
    font-size: 12px; font-weight: 600;
    color: rgba(226,232,240,0.8);
    letter-spacing: 1px; text-transform: uppercase;
  }

  /* ABOUT */
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  @media (max-width: 520px) { .about-grid { grid-template-columns: 1fr; } }

  .info-card {
    background: rgba(15,23,42,0.6);
    border: 1px solid rgba(0,212,255,0.1);
    border-radius: 8px;
    padding: 16px;
  }

  .info-card-title {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px; color: rgba(0,212,255,0.5);
    letter-spacing: 2px; text-transform: uppercase;
    margin-bottom: 10px;
  }

  .info-card-body {
    font-size: 13px; line-height: 1.7;
    color: rgba(226,232,240,0.65);
  }

  /* PROJECTS */
  .project-cards { display: flex; flex-direction: column; gap: 14px; }

  .project-card {
    background: rgba(15,23,42,0.6);
    border: 1px solid rgba(0,212,255,0.12);
    border-radius: 8px;
    padding: 18px 20px;
    display: flex; gap: 16px;
    align-items: flex-start;
    transition: border-color 0.2s;
  }
  .project-card:hover { border-color: rgba(0,212,255,0.4); }

  .project-icon {
    width: 44px; height: 44px; border-radius: 8px;
    background: rgba(0,212,255,0.08);
    border: 1px solid rgba(0,212,255,0.2);
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    font-size: 20px; color: #00d4ff;
  }

  .project-info { flex: 1; }
  .project-name {
    font-family: 'Orbitron', monospace;
    font-size: 13px; font-weight: 700;
    color: #e2e8f0; letter-spacing: 1px;
    margin-bottom: 4px;
  }
  .project-desc {
    font-size: 13px; color: rgba(226,232,240,0.5);
    line-height: 1.5; margin-bottom: 10px;
  }
  .project-stack { display: flex; flex-wrap: wrap; gap: 6px; }
  .stack-tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px; letter-spacing: 0.5px;
    padding: 2px 8px; border-radius: 3px;
    border: 1px solid rgba(180,0,255,0.3);
    color: rgba(180,0,255,0.7);
    background: rgba(180,0,255,0.05);
  }

  /* LOADING */
  .loading-screen {
    position: fixed; inset: 0;
    background: #050505;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    z-index: 1000;
    transition: opacity 0.6s;
  }

  .loading-screen.fade-out { opacity: 0; pointer-events: none; }

  .loading-logo {
    font-family: 'Orbitron', monospace;
    font-size: 36px; font-weight: 900;
    letter-spacing: 8px;
    background: linear-gradient(135deg, #00d4ff, #b400ff);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 32px;
  }

  .loading-msgs {
    font-family: 'Share Tech Mono', monospace;
    font-size: 12px; color: rgba(0,212,255,0.6);
    letter-spacing: 2px;
    min-height: 20px; margin-bottom: 24px;
    text-align: center;
  }

  .progress-track {
    width: 240px; height: 3px;
    background: rgba(255,255,255,0.08);
    border-radius: 2px; overflow: hidden;
    margin-bottom: 12px;
  }
  .progress-fill {
    height: 100%;
    background: linear-gradient(90deg, #00d4ff, #b400ff);
    border-radius: 2px;
    transition: width 0.4s;
  }
  .progress-pct {
    font-family: 'Orbitron', monospace;
    font-size: 14px; font-weight: 700; color: #00d4ff;
  }

  /* FOOTER */
  .footer {
    padding: 28px 32px;
    text-align: center;
    border-top: 1px solid rgba(0,255,255,0.08);
  }
  .footer-text {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px; color: rgba(226,232,240,0.25);
    letter-spacing: 2px;
  }
</style>

<div class="loading-screen" id="loader">
  <div class="loading-logo">VISHNU</div>
  <div class="loading-msgs" id="loadMsg">Initializing Interface...</div>
  <div class="progress-track">
    <div class="progress-fill" id="progBar" style="width: 0%"></div>
  </div>
  <div class="progress-pct" id="progPct">0%</div>
</div>

<div class="readme-wrap" id="mainContent" style="opacity:0; transition: opacity 0.8s;">
  <div class="scanlines"></div>
  <div class="content">

    <!-- HERO -->
    <div class="hero">
      <div class="hero-grid"></div>
      <div style="position:relative; z-index:1;">
        <div class="status-pill">
          <div class="status-dot"></div>
          OPEN TO OPPORTUNITIES
        </div>
        <div class="hero-name">VISHNU</div>
        <div class="hero-sub">FRONTEND DEVELOPER • GRAPHIC DESIGNER • REACT SPECIALIST</div>
        <div class="typing-display" id="typer"><span id="typed-text"></span><span class="cursor">_</span></div>
        <div class="hero-badges">
          <span class="badge badge-cyan">⚡ REACT</span>
          <span class="badge badge-purple">🎨 DESIGN</span>
          <span class="badge badge-cyan">⚙️ JAVASCRIPT</span>
          <span class="badge badge-green">✅ OPEN SOURCE</span>
          <span class="badge badge-purple">🌐 FREELANCE</span>
          <span class="badge badge-cyan">🚀 VITE</span>
        </div>
        <div class="hero-btns">
          <button class="btn btn-primary" onclick="scrollTo('projects')">⚡ View Projects</button>
          <button class="btn btn-outline" onclick="scrollTo('contact')">📡 Contact Me</button>
          <button class="btn btn-outline" onclick="scrollTo('github')">🔗 GitHub Stats</button>
        </div>
        <div class="social-links">
          <a class="social-link" href="#"><i class="ti ti-brand-github"></i> GitHub</a>
          <a class="social-link" href="#"><i class="ti ti-brand-linkedin"></i> LinkedIn</a>
          <a class="social-link" href="#"><i class="ti ti-brand-instagram"></i> Instagram</a>
          <a class="social-link" href="#"><i class="ti ti-brand-behance"></i> Behance</a>
          <a class="social-link" href="#"><i class="ti ti-mail"></i> Email</a>
        </div>
      </div>
    </div>

    <!-- ABOUT -->
    <div class="section" id="about">
      <div class="section-header">
        <span class="section-tag">01</span>
        <span class="section-title">ABOUT ME</span>
        <div class="section-line"></div>
      </div>
      <div class="about-grid">
        <div class="info-card">
          <div class="info-card-title">// identity</div>
          <div class="info-card-body">Passionate Frontend Developer & Graphic Designer bridging the gap between clean code and stunning visuals. I transform ideas into digital products that stand out.</div>
        </div>
        <div class="info-card">
          <div class="info-card-title">// specialization</div>
          <div class="info-card-body">React development, responsive web design, poster creation, digital magazines, marketing creatives, and interactive user interfaces.</div>
        </div>
        <div class="info-card">
          <div class="info-card-title">// currently</div>
          <div class="info-card-body">Exploring new technologies, creative trends, and digital experiences to continuously push both technical and design skill boundaries.</div>
        </div>
        <div class="info-card">
          <div class="info-card-title">// tools</div>
          <div class="info-card-body">React · Vite · Tailwind CSS · Figma · Adobe Suite · Blender · Node.js · MongoDB</div>
        </div>
      </div>
    </div>

    <!-- STATS -->
    <div class="section">
      <div class="section-header">
        <span class="section-tag">02</span>
        <span class="section-title">OPERATOR STATS</span>
        <div class="section-line"></div>
      </div>
      <div class="stats-grid">
        <div class="stat-card">
          <span class="stat-num" id="s1">0</span>
          <span class="stat-label">Projects Shipped</span>
        </div>
        <div class="stat-card">
          <span class="stat-num" id="s2">0</span>
          <span class="stat-label">Design Works</span>
        </div>
        <div class="stat-card">
          <span class="stat-num" id="s3">0</span>
          <span class="stat-label">Technologies</span>
        </div>
        <div class="stat-card">
          <span class="stat-num" id="s4">0</span>
          <span class="stat-label">GitHub Repos</span>
        </div>
      </div>
    </div>

    <!-- SKILL TREE -->
    <div class="section" id="skills">
      <div class="section-header">
        <span class="section-tag">03</span>
        <span class="section-title">SKILL TREE</span>
        <div class="section-line"></div>
      </div>

      <div class="skill-group">
        <div class="group-header">
          <span class="group-title" style="color:#00d4ff">⚡ Frontend Development</span>
          <span class="level-badge" style="color:#00d4ff; border-color:rgba(0,212,255,0.4)">LVL 95</span>
        </div>
        <div class="skill-track" style="margin-bottom:12px;">
          <div class="skill-fill fill-cyan" style="width:95%"></div>
        </div>
        <div class="chips">
          <span class="chip">React</span><span class="chip">JavaScript</span><span class="chip">HTML5</span>
          <span class="chip">CSS3</span><span class="chip">Tailwind</span><span class="chip">Vite</span>
          <span class="chip">Responsive Design</span><span class="chip">UI Components</span>
        </div>
      </div>

      <div class="skill-group">
        <div class="group-header">
          <span class="group-title" style="color:#b400ff">🎨 Graphic Design</span>
          <span class="level-badge" style="color:#b400ff; border-color:rgba(180,0,255,0.4)">LVL 90</span>
        </div>
        <div class="skill-track" style="margin-bottom:12px;">
          <div class="skill-fill fill-purple" style="width:90%"></div>
        </div>
        <div class="chips">
          <span class="chip purple">Poster Design</span><span class="chip purple">Social Media</span>
          <span class="chip purple">Branding</span><span class="chip purple">Digital Magazines</span>
          <span class="chip purple">Event Posters</span><span class="chip purple">Marketing</span>
          <span class="chip purple">Brochures</span><span class="chip purple">Layout Design</span>
        </div>
      </div>

      <div class="skill-group">
        <div class="group-header">
          <span class="group-title" style="color:#00ffcc">⚛️ React Development</span>
          <span class="level-badge" style="color:#00ffcc; border-color:rgba(0,255,204,0.4)">LVL 88</span>
        </div>
        <div class="skill-track" style="margin-bottom:12px;">
          <div class="skill-fill fill-teal" style="width:88%"></div>
        </div>
        <div class="chips">
          <span class="chip">Hooks</span><span class="chip">React Router</span>
          <span class="chip">State Mgmt</span><span class="chip">API Integration</span>
          <span class="chip">Component Architecture</span><span class="chip">Performance</span>
        </div>
      </div>

      <div style="display:grid; grid-template-columns:1fr 1fr; gap:12px;">
        <div class="skill-group">
          <div class="group-header">
            <span class="group-title" style="color:#00ff64; font-size:11px">🔧 Backend</span>
            <span class="level-badge" style="color:#00ff64; border-color:rgba(0,255,100,0.4); font-size:10px">LVL 70</span>
          </div>
          <div class="skill-track" style="margin-bottom:10px;">
            <div class="skill-fill fill-green" style="width:70%"></div>
          </div>
          <div class="chips">
            <span class="chip green">Node.js</span><span class="chip green">Express</span>
            <span class="chip green">MongoDB</span><span class="chip green">FastAPI</span>
          </div>
        </div>
        <div class="skill-group">
          <div class="group-header">
            <span class="group-title" style="color:#ff8c00; font-size:11px">🔮 3D Design</span>
            <span class="level-badge" style="color:#ff8c00; border-color:rgba(255,140,0,0.4); font-size:10px">LVL 65</span>
          </div>
          <div class="skill-track" style="margin-bottom:10px;">
            <div class="skill-fill fill-orange" style="width:65%"></div>
          </div>
          <div class="chips">
            <span class="chip orange">Blender</span><span class="chip orange">3D Modeling</span>
            <span class="chip orange">Animation</span><span class="chip orange">Visualization</span>
          </div>
        </div>
      </div>
    </div>

    <!-- GITHUB DASHBOARD -->
    <div class="section" id="github">
      <div class="section-header">
        <span class="section-tag">04</span>
        <span class="section-title">GITHUB DASHBOARD</span>
        <div class="section-line"></div>
      </div>
      <div class="gh-grid">
        <div class="gh-card">
          <div class="gh-icon"><i class="ti ti-git-fork" aria-hidden="true"></i></div>
          <span class="gh-val">24+</span>
          <span class="gh-lab">Repositories</span>
        </div>
        <div class="gh-card">
          <div class="gh-icon" style="color:#b400ff"><i class="ti ti-flame" aria-hidden="true"></i></div>
          <span class="gh-val" style="color:#b400ff">180+</span>
          <span class="gh-lab">Day Streak</span>
        </div>
        <div class="gh-card">
          <div class="gh-icon" style="color:#00ff64"><i class="ti ti-git-commit" aria-hidden="true"></i></div>
          <span class="gh-val" style="color:#00ff64">500+</span>
          <span class="gh-lab">Commits</span>
        </div>
        <div class="gh-card">
          <div class="gh-icon" style="color:#ff8c00"><i class="ti ti-star" aria-hidden="true"></i></div>
          <span class="gh-val" style="color:#ff8c00">50+</span>
          <span class="gh-lab">Stars Earned</span>
        </div>
      </div>
      <div class="contrib-wrap">
        <div class="contrib-title">// contribution activity — last 24 weeks</div>
        <div class="contrib-grid" id="contribGrid"></div>
        <div class="lang-bar-wrap">
          <div style="font-family:'Share Tech Mono',monospace; font-size:10px; color:rgba(0,212,255,0.5); letter-spacing:2px; margin-bottom:8px;">// top languages</div>
          <div class="lang-combined">
            <div class="lang-seg" style="width:42%; background:#00d4ff;"></div>
            <div class="lang-seg" style="width:28%; background:#b400ff;"></div>
            <div class="lang-seg" style="width:18%; background:#00ff64;"></div>
            <div class="lang-seg" style="width:12%; background:#ff8c00;"></div>
          </div>
          <div class="lang-legend">
            <div class="lang-item"><div class="lang-dot" style="background:#00d4ff;"></div>JavaScript 42%</div>
            <div class="lang-item"><div class="lang-dot" style="background:#b400ff;"></div>CSS 28%</div>
            <div class="lang-item"><div class="lang-dot" style="background:#00ff64;"></div>HTML 18%</div>
            <div class="lang-item"><div class="lang-dot" style="background:#ff8c00;"></div>Python 12%</div>
          </div>
        </div>
      </div>
    </div>

    <!-- PROJECTS -->
    <div class="section" id="projects">
      <div class="section-header">
        <span class="section-tag">05</span>
        <span class="section-title">DEVELOPMENT PROJECTS</span>
        <div class="section-line"></div>
      </div>
      <div class="project-cards">
        <div class="project-card">
          <div class="project-icon"><i class="ti ti-device-desktop" aria-hidden="true"></i></div>
          <div class="project-info">
            <div class="project-name">PORTFOLIO WEBSITE</div>
            <div class="project-desc">Premium gaming-inspired personal portfolio with immersive animations, particle effects, and interactive skill trees.</div>
            <div class="project-stack">
              <span class="stack-tag">React</span><span class="stack-tag">Vite</span>
              <span class="stack-tag">Tailwind CSS</span><span class="stack-tag">Framer Motion</span>
            </div>
          </div>
        </div>
        <div class="project-card">
          <div class="project-icon"><i class="ti ti-layout-dashboard" aria-hidden="true"></i></div>
          <div class="project-info">
            <div class="project-name">UI COMPONENT LIBRARY</div>
            <div class="project-desc">Reusable React component library with dark-mode support, accessibility-first design, and Storybook documentation.</div>
            <div class="project-stack">
              <span class="stack-tag">React</span><span class="stack-tag">TypeScript</span>
              <span class="stack-tag">Storybook</span><span class="stack-tag">CSS Modules</span>
            </div>
          </div>
        </div>
        <div class="project-card">
          <div class="project-icon"><i class="ti ti-brand-react" aria-hidden="true"></i></div>
          <div class="project-info">
            <div class="project-name">FULLSTACK WEB APP</div>
            <div class="project-desc">Full-stack web application with React frontend, Node.js REST API, and MongoDB database with JWT authentication.</div>
            <div class="project-stack">
              <span class="stack-tag">React</span><span class="stack-tag">Node.js</span>
              <span class="stack-tag">MongoDB</span><span class="stack-tag">Express</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- TIMELINE -->
    <div class="section" id="timeline">
      <div class="section-header">
        <span class="section-tag">06</span>
        <span class="section-title">MISSION LOG</span>
        <div class="section-line"></div>
      </div>
      <div class="timeline">
        <div class="tl-item">
          <div class="tl-dot"></div>
          <div class="tl-year">2024 — PRESENT</div>
          <div class="tl-role">SENIOR FRONTEND DEVELOPER</div>
          <div class="tl-desc">Building production-grade React applications with performance optimization, modern state management, and responsive design systems.</div>
        </div>
        <div class="tl-item">
          <div class="tl-dot" style="border-color:#b400ff; background:#b400ff; box-shadow: 0 0 8px #b400ff;"></div>
          <div class="tl-year" style="color:#b400ff;">2023</div>
          <div class="tl-role">GRAPHIC DESIGNER — FREELANCE</div>
          <div class="tl-desc">Designed 100+ posters, digital magazines, event materials, and social media creatives for clients across industries.</div>
        </div>
        <div class="tl-item">
          <div class="tl-dot" style="border-color:#00ff64; background:#00ff64; box-shadow: 0 0 8px #00ff64;"></div>
          <div class="tl-year" style="color:#00ff64;">2022</div>
          <div class="tl-role">REACT DEVELOPER — LEARNING PHASE</div>
          <div class="tl-desc">Mastered React ecosystem: Hooks, Router, Context API, Redux, and third-party integrations. Built 15+ personal projects.</div>
        </div>
        <div class="tl-item">
          <div class="tl-dot" style="border-color:#ff8c00; background:#ff8c00; box-shadow: 0 0 8px #ff8c00;"></div>
          <div class="tl-year" style="color:#ff8c00;">2021</div>
          <div class="tl-role">WEB DEVELOPMENT JOURNEY BEGINS</div>
          <div class="tl-desc">Started with HTML, CSS, JavaScript. Discovered a passion for creating interactive and visually compelling web experiences.</div>
        </div>
      </div>
    </div>

    <!-- ACHIEVEMENTS -->
    <div class="section" id="achievements">
      <div class="section-header">
        <span class="section-tag">07</span>
        <span class="section-title">ACHIEVEMENTS UNLOCKED</span>
        <div class="section-line"></div>
      </div>
      <div class="ach-grid">
        <div class="ach-card"><div class="ach-icon">🏆</div><div class="ach-name">Frontend Specialist</div></div>
        <div class="ach-card"><div class="ach-icon">⚛️</div><div class="ach-name">React Developer</div></div>
        <div class="ach-card"><div class="ach-icon">🎨</div><div class="ach-name">Graphic Designer</div></div>
        <div class="ach-card"><div class="ach-icon">📰</div><div class="ach-name">Magazine Creator</div></div>
        <div class="ach-card"><div class="ach-icon">🖼️</div><div class="ach-name">Poster Expert</div></div>
        <div class="ach-card"><div class="ach-icon">💡</div><div class="ach-name">UI Designer</div></div>
        <div class="ach-card"><div class="ach-icon">🔮</div><div class="ach-name">Creative Thinker</div></div>
        <div class="ach-card"><div class="ach-icon">⚙️</div><div class="ach-name">Problem Solver</div></div>
      </div>
    </div>

    <!-- CONTACT -->
    <div class="section" id="contact">
      <div class="section-header">
        <span class="section-tag">08</span>
        <span class="section-title">COMMAND CENTER</span>
        <div class="section-line"></div>
      </div>
      <div style="display:grid; grid-template-columns:1fr 1fr; gap:16px;">
        <div class="info-card">
          <div class="info-card-title">// transmission channels</div>
          <div style="display:flex; flex-direction:column; gap:12px; margin-top:8px;">
            <a class="social-link" href="#" style="font-size:14px;">
              <i class="ti ti-brand-github" style="font-size:18px;"></i> github.com/vishnu
            </a>
            <a class="social-link" href="#" style="font-size:14px;">
              <i class="ti ti-brand-linkedin" style="font-size:18px;"></i> linkedin.com/in/vishnu
            </a>
            <a class="social-link" href="#" style="font-size:14px;">
              <i class="ti ti-brand-instagram" style="font-size:18px;"></i> @vishnu.design
            </a>
            <a class="social-link" href="#" style="font-size:14px;">
              <i class="ti ti-brand-behance" style="font-size:18px;"></i> behance.net/vishnu
            </a>
            <a class="social-link" href="#" style="font-size:14px;">
              <i class="ti ti-mail" style="font-size:18px;"></i> vishnu@email.com
            </a>
          </div>
        </div>
        <div class="info-card">
          <div class="info-card-title">// availability status</div>
          <div style="margin-top:8px;">
            <div style="display:flex; align-items:center; gap:8px; margin-bottom:16px;">
              <div class="status-dot"></div>
              <span style="font-family:'Share Tech Mono',monospace; font-size:12px; color:#00ff64;">AVAILABLE FOR FREELANCE</span>
            </div>
            <div style="font-size:13px; color:rgba(226,232,240,0.5); line-height:1.7;">
              Open to frontend dev projects, graphic design work, UI/UX contracts, and creative collaborations. Response within 24 hours.
            </div>
            <div style="margin-top:16px;">
              <button class="btn btn-primary" style="width:100%; font-size:10px;" onclick="sendPrompt('How do I contact Vishnu for a project?')">
                ⚡ Send Message ↗
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- FOOTER -->
    <div class="footer">
      <div class="footer-text">
        ⚡ VISHNU • FRONTEND DEVELOPER & GRAPHIC DESIGNER • BUILT WITH REACT + VITE ⚡
      </div>
      <div style="margin-top:8px; font-family:'Share Tech Mono',monospace; font-size:10px; color:rgba(0,212,255,0.2); letter-spacing:2px;">
        &lt;/&gt; CRAFTED WITH CODE AND CREATIVITY
      </div>
    </div>

  </div>
</div>

<script>
  const loadMsgs = [
    "Initializing Interface...",
    "Loading Design Assets...",
    "Loading Developer Profile...",
    "Loading Creative Portfolio...",
    "Connecting GitHub...",
    "System Ready."
  ];

  let msgIdx = 0;
  let pct = 0;

  function runLoader() {
    const interval = setInterval(() => {
      pct += Math.floor(Math.random() * 22) + 10;
      if (pct > 100) pct = 100;
      document.getElementById('progBar').style.width = pct + '%';
      document.getElementById('progPct').textContent = pct + '%';

      if (msgIdx < loadMsgs.length) {
        document.getElementById('loadMsg').textContent = loadMsgs[msgIdx];
        msgIdx++;
      }

      if (pct >= 100) {
        clearInterval(interval);
        setTimeout(() => {
          document.getElementById('loader').classList.add('fade-out');
          document.getElementById('mainContent').style.opacity = '1';
          startTyper();
          animateStats();
          buildContrib();
        }, 500);
      }
    }, 350);
  }

  const roles = ["Frontend Developer","React Developer","Graphic Designer","Creative UI Designer","Digital Creator","Photo Editor"];
  let roleIdx = 0, charIdx = 0, deleting = false;

  function startTyper() {
    function tick() {
      const current = roles[roleIdx];
      const el = document.getElementById('typed-text');
      if (!deleting) {
        el.textContent = current.substring(0, charIdx + 1);
        charIdx++;
        if (charIdx === current.length) {
          deleting = true;
          setTimeout(tick, 1600);
          return;
        }
      } else {
        el.textContent = current.substring(0, charIdx - 1);
        charIdx--;
        if (charIdx === 0) {
          deleting = false;
          roleIdx = (roleIdx + 1) % roles.length;
        }
      }
      setTimeout(tick, deleting ? 60 : 90);
    }
    tick();
  }

  function animateStats() {
    const targets = [{id:'s1',val:20},{id:'s2',val:50},{id:'s3',val:15},{id:'s4',val:24}];
    targets.forEach(t => {
      let n = 0;
      const step = Math.ceil(t.val / 30);
      const iv = setInterval(() => {
        n = Math.min(n + step, t.val);
        document.getElementById(t.id).textContent = n + '+';
        if (n >= t.val) clearInterval(iv);
      }, 40);
    });
  }

  function buildContrib() {
    const grid = document.getElementById('contribGrid');
    const levels = ['#0d1117','#0e4429','#006d32','#26a641','#39d353'];
    const cyans = ['#0a1a1a','#003333','#005555','#008888','#00d4ff'];
    const purps = ['#0a0010','#200040','#400080','#7700cc','#b400ff'];
    const cols = 24;
    for (let w = 0; w < cols; w++) {
      const week = document.createElement('div');
      week.className = 'contrib-week';
      for (let d = 0; d < 7; d++) {
        const day = document.createElement('div');
        day.className = 'contrib-day';
        const r = Math.random();
        const palette = r > 0.6 ? cyans : r > 0.3 ? purps : levels;
        const li = r > 0.7 ? 4 : r > 0.5 ? 3 : r > 0.3 ? 2 : r > 0.15 ? 1 : 0;
        day.style.background = palette[li];
        week.appendChild(day);
      }
      grid.appendChild(week);
    }
  }

  window.scrollTo = function(id) {
    const el = document.getElementById(id);
    if (el) el.scrollIntoView({behavior:'smooth'});
  };

  runLoader();
</script>

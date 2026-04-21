<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GitHub Profile README — Preview</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    min-height: 100vh;
    background: #07070f;
    font-family: 'Inter', sans-serif;
    color: #e8e8f0;
    overflow-x: hidden;
  }

  /* ── Aurora background ── */
  .aurora {
    position: fixed;
    inset: 0;
    z-index: 0;
    overflow: hidden;
    pointer-events: none;
  }
  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(100px);
    opacity: 0.18;
    animation: drift linear infinite;
  }
  .orb1 { width: 700px; height: 700px; background: #6C63FF; top: -200px; left: -150px; animation-duration: 22s; animation-name: drift1; }
  .orb2 { width: 500px; height: 500px; background: #1e9fff; top: 30%; right: -100px; animation-duration: 28s; animation-name: drift2; }
  .orb3 { width: 600px; height: 600px; background: #0fd4b0; bottom: -150px; left: 30%; animation-duration: 34s; animation-name: drift3; }
  .orb4 { width: 400px; height: 400px; background: #c463ff; top: 55%; left: 10%; animation-duration: 19s; animation-name: drift4; }

  @keyframes drift1 { 0%,100%{transform:translate(0,0) scale(1)} 33%{transform:translate(80px,60px) scale(1.05)} 66%{transform:translate(-40px,100px) scale(0.95)} }
  @keyframes drift2 { 0%,100%{transform:translate(0,0) scale(1)} 33%{transform:translate(-90px,50px) scale(1.08)} 66%{transform:translate(30px,-80px) scale(0.96)} }
  @keyframes drift3 { 0%,100%{transform:translate(0,0) scale(1)} 50%{transform:translate(-60px,-70px) scale(1.06)} }
  @keyframes drift4 { 0%,100%{transform:translate(0,0) scale(1)} 40%{transform:translate(70px,-50px) scale(1.04)} 80%{transform:translate(-30px,60px) scale(0.97)} }

  /* ── Layout ── */
  .page {
    position: relative;
    z-index: 1;
    max-width: 780px;
    margin: 0 auto;
    padding: 60px 24px 80px;
  }

  /* ── Glass card ── */
  .glass {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 20px;
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    padding: 36px 40px;
    margin-bottom: 20px;
    transition: border-color 0.4s;
  }
  .glass:hover { border-color: rgba(108,99,255,0.3); }

  /* ── Hero ── */
  .hero { text-align: center; padding: 50px 40px; }
  .avatar-ring {
    width: 90px; height: 90px;
    border-radius: 50%;
    margin: 0 auto 24px;
    background: linear-gradient(135deg, #6C63FF, #0fd4b0);
    padding: 2px;
    animation: spin-slow 8s linear infinite;
  }
  @keyframes spin-slow { to { transform: rotate(360deg); } }
  .avatar-inner {
    width: 100%; height: 100%;
    border-radius: 50%;
    background: #10101a;
    display: flex; align-items: center; justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 28px; font-weight: 500;
    color: #e8e8f0;
  }
  .hero h1 {
    font-size: 2.2rem; font-weight: 600;
    background: linear-gradient(120deg, #ffffff 30%, #9b8fff);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
    letter-spacing: -0.5px;
  }
  .role-badge {
    display: inline-block;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    color: #8b7ff0;
    border: 1px solid rgba(108,99,255,0.35);
    border-radius: 20px;
    padding: 5px 16px;
    letter-spacing: 0.04em;
    margin-bottom: 20px;
  }
  .hero p { font-size: 0.95rem; color: #9090b0; line-height: 1.75; max-width: 480px; margin: 0 auto 28px; }

  /* ── Typing cursor ── */
  .typed-wrap { font-family: 'JetBrains Mono', monospace; font-size: 0.82rem; color: #6C63FF; }
  .cursor { display: inline-block; animation: blink 1s step-end infinite; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ── Social row ── */
  .socials { display: flex; gap: 10px; justify-content: center; flex-wrap: wrap; margin-top: 20px; }
  .social-btn {
    display: flex; align-items: center; gap: 7px;
    padding: 8px 16px; border-radius: 10px;
    border: 1px solid rgba(255,255,255,0.1);
    background: rgba(255,255,255,0.04);
    color: #c0c0d8; font-size: 0.78rem; text-decoration: none;
    transition: all 0.25s;
    font-family: 'Inter', sans-serif;
  }
  .social-btn:hover { background: rgba(108,99,255,0.15); border-color: rgba(108,99,255,0.4); color: #fff; }
  .social-btn .dot { width: 6px; height: 6px; border-radius: 50%; }

  /* ── Section header ── */
  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    color: #6C63FF;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 18px;
    display: flex; align-items: center; gap: 10px;
  }
  .section-label::after { content:''; flex:1; height:1px; background: rgba(108,99,255,0.2); }

  /* ── About ── */
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-top: 16px; }
  .about-item {
    display: flex; align-items: flex-start; gap: 10px;
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px; padding: 14px 16px;
  }
  .about-icon { font-size: 15px; margin-top: 1px; }
  .about-item span { font-size: 0.82rem; color: #9090b0; line-height: 1.5; }
  .about-item strong { color: #d8d8ee; font-weight: 500; }

  /* ── Skills ── */
  .skill-group { margin-bottom: 20px; }
  .skill-group:last-child { margin-bottom: 0; }
  .skill-group-title { font-size: 0.72rem; color: #6060a0; letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 10px; font-family: 'JetBrains Mono', monospace; }
  .tags { display: flex; flex-wrap: wrap; gap: 8px; }
  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    padding: 5px 12px;
    border-radius: 8px;
    border: 1px solid;
    transition: all 0.2s;
    cursor: default;
  }
  .tag:hover { transform: translateY(-1px); }
  .tag.violet { background: rgba(108,99,255,0.1); border-color: rgba(108,99,255,0.3); color: #a89fff; }
  .tag.teal   { background: rgba(15,212,176,0.08); border-color: rgba(15,212,176,0.25); color: #5ee8cc; }
  .tag.blue   { background: rgba(30,159,255,0.08); border-color: rgba(30,159,255,0.25); color: #70bfff; }
  .tag.gray   { background: rgba(255,255,255,0.05); border-color: rgba(255,255,255,0.1); color: #9898b8; }

  /* ── Projects ── */
  .projects-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-top: 4px; }
  .project-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 14px; padding: 20px 22px;
    transition: all 0.3s;
    cursor: pointer;
    text-decoration: none;
    display: block;
  }
  .project-card:hover { border-color: rgba(108,99,255,0.4); background: rgba(108,99,255,0.06); transform: translateY(-2px); }
  .project-top { display: flex; align-items: center; justify-content: space-between; margin-bottom: 8px; }
  .project-name { font-size: 0.9rem; font-weight: 500; color: #d8d8f0; }
  .project-arrow { color: #6C63FF; font-size: 0.9rem; opacity: 0; transition: opacity 0.2s; }
  .project-card:hover .project-arrow { opacity: 1; }
  .project-desc { font-size: 0.78rem; color: #6868a0; line-height: 1.55; margin-bottom: 14px; }
  .project-tech { display: flex; gap: 6px; flex-wrap: wrap; }
  .tech-pip { font-family: 'JetBrains Mono', monospace; font-size: 0.65rem; padding: 3px 8px; border-radius: 6px; background: rgba(255,255,255,0.06); color: #8888b0; border: 1px solid rgba(255,255,255,0.08); }

  /* ── Stats ── */
  .stats-row { display: grid; grid-template-columns: repeat(3,1fr); gap: 12px; margin-top: 4px; }
  .stat-card { background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.07); border-radius: 14px; padding: 20px; text-align: center; }
  .stat-num { font-size: 1.8rem; font-weight: 600; font-family: 'JetBrains Mono', monospace; }
  .stat-num.violet { color: #8b7fff; }
  .stat-num.teal   { color: #0fd4b0; }
  .stat-num.blue   { color: #4ea9ff; }
  .stat-lbl { font-size: 0.72rem; color: #5858a0; margin-top: 4px; letter-spacing: 0.05em; }

  .streak-bar { margin-top: 20px; }
  .streak-label { display: flex; justify-content: space-between; font-size: 0.72rem; color: #5858a0; margin-bottom: 8px; font-family: 'JetBrains Mono', monospace; }
  .bar-track { height: 4px; background: rgba(255,255,255,0.06); border-radius: 4px; overflow: hidden; }
  .bar-fill { height: 100%; border-radius: 4px; background: linear-gradient(90deg, #6C63FF, #0fd4b0); animation: fill-in 1.8s ease forwards; transform-origin: left; }
  @keyframes fill-in { from{width:0} }

  /* ── Fun facts ── */
  .code-block {
    background: rgba(0,0,0,0.35);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 14px; padding: 22px 26px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem; line-height: 1.8;
    color: #9090b0;
    margin-top: 4px;
  }
  .code-block .k { color: #8b7fff; }
  .code-block .s { color: #5ed4b0; }
  .code-block .c { color: #4a4a70; }
  .code-block .f { color: #e8c96a; }
  .code-block .n { color: #e8e8f0; }

  /* ── Footer ── */
  .footer { text-align: center; padding-top: 10px; }
  .footer p { font-size: 0.75rem; color: #3a3a60; font-family: 'JetBrains Mono', monospace; }
  .footer span { color: #6C63FF; }

  /* ── Animations ── */
  .fade-up { opacity: 0; transform: translateY(24px); animation: fadeup 0.7s ease forwards; }
  @keyframes fadeup { to { opacity:1; transform:translateY(0); } }
  .d1{animation-delay:0.1s} .d2{animation-delay:0.2s} .d3{animation-delay:0.3s}
  .d4{animation-delay:0.4s} .d5{animation-delay:0.5s} .d6{animation-delay:0.6s}

  @media(max-width:600px) {
    .about-grid, .projects-grid, .stats-row { grid-template-columns: 1fr; }
    .hero h1 { font-size: 1.7rem; }
    .glass { padding: 24px 20px; }
  }
</style>
</head>
<body>

<div class="aurora">
  <div class="orb orb1"></div>
  <div class="orb orb2"></div>
  <div class="orb orb3"></div>
  <div class="orb orb4"></div>
</div>

<div class="page">

  <!-- HERO -->
  <div class="glass hero fade-up d1">
    <div class="avatar-ring">
      <div class="avatar-inner">YN</div>
    </div>
    <h1>Your Name</h1>
    <div class="role-badge">// Full Stack Developer</div>
    <p>I craft scalable, thoughtful software — from clean APIs to pixel-perfect interfaces. Passionate about turning complex problems into elegant solutions.</p>
    <div class="typed-wrap">
      <span id="typed-text"></span><span class="cursor">▌</span>
    </div>
    <div class="socials">
      <a href="mailto:you@email.com" class="social-btn"><span class="dot" style="background:#ff7070"></span>Email</a>
      <a href="#" class="social-btn"><span class="dot" style="background:#0077B5"></span>LinkedIn</a>
      <a href="#" class="social-btn"><span class="dot" style="background:#6C63FF"></span>GitHub</a>
      <a href="#" class="social-btn"><span class="dot" style="background:#0fd4b0"></span>Portfolio</a>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="glass fade-up d2">
    <div class="section-label">01 · About</div>
    <div class="about-grid">
      <div class="about-item"><span class="about-icon">🔭</span><span>Working on <strong>[Your Current Project]</strong></span></div>
      <div class="about-item"><span class="about-icon">🌱</span><span>Currently learning <strong>[New Skill / Tech]</strong></span></div>
      <div class="about-item"><span class="about-icon">🤝</span><span>Open to <strong>open-source collabs</strong></span></div>
      <div class="about-item"><span class="about-icon">📍</span><span>Based in <strong>[Your City, Country]</strong></span></div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="glass fade-up d3">
    <div class="section-label">02 · Tech Stack</div>
    <div class="skill-group">
      <div class="skill-group-title">Languages</div>
      <div class="tags">
        <span class="tag violet">Python</span>
        <span class="tag violet">JavaScript</span>
        <span class="tag violet">TypeScript</span>
        <span class="tag violet">Go</span>
        <span class="tag violet">C++</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Frameworks</div>
      <div class="tags">
        <span class="tag teal">React</span>
        <span class="tag teal">Next.js</span>
        <span class="tag teal">Node.js</span>
        <span class="tag teal">FastAPI</span>
        <span class="tag teal">Express</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-title">Cloud & Tools</div>
      <div class="tags">
        <span class="tag blue">AWS</span>
        <span class="tag blue">Docker</span>
        <span class="tag blue">PostgreSQL</span>
        <span class="tag blue">Redis</span>
        <span class="tag gray">Git</span>
        <span class="tag gray">Linux</span>
        <span class="tag gray">Figma</span>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="glass fade-up d4">
    <div class="section-label">03 · Featured Projects</div>
    <div class="projects-grid">
      <a href="#" class="project-card">
        <div class="project-top">
          <div class="project-name">Project Alpha</div>
          <div class="project-arrow">↗</div>
        </div>
        <div class="project-desc">A short description of what this does and why it's interesting. Replace with your actual project.</div>
        <div class="project-tech">
          <span class="tech-pip">React</span>
          <span class="tech-pip">Node.js</span>
          <span class="tech-pip">PostgreSQL</span>
        </div>
      </a>
      <a href="#" class="project-card">
        <div class="project-top">
          <div class="project-name">Project Beta</div>
          <div class="project-arrow">↗</div>
        </div>
        <div class="project-desc">A short description of what this does and why it's interesting. Replace with your actual project.</div>
        <div class="project-tech">
          <span class="tech-pip">Python</span>
          <span class="tech-pip">FastAPI</span>
          <span class="tech-pip">Docker</span>
        </div>
      </a>
      <a href="#" class="project-card">
        <div class="project-top">
          <div class="project-name">Project Gamma</div>
          <div class="project-arrow">↗</div>
        </div>
        <div class="project-desc">A short description of what this does and why it's interesting. Replace with your actual project.</div>
        <div class="project-tech">
          <span class="tech-pip">Next.js</span>
          <span class="tech-pip">TypeScript</span>
          <span class="tech-pip">AWS</span>
        </div>
      </a>
      <a href="#" class="project-card">
        <div class="project-top">
          <div class="project-name">Project Delta</div>
          <div class="project-arrow">↗</div>
        </div>
        <div class="project-desc">A short description of what this does and why it's interesting. Replace with your actual project.</div>
        <div class="project-tech">
          <span class="tech-pip">Go</span>
          <span class="tech-pip">Redis</span>
          <span class="tech-pip">Linux</span>
        </div>
      </a>
    </div>
  </div>

  <!-- STATS -->
  <div class="glass fade-up d5">
    <div class="section-label">04 · GitHub Stats</div>
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-num violet" id="cnt-repos">0</div>
        <div class="stat-lbl">Repositories</div>
      </div>
      <div class="stat-card">
        <div class="stat-num teal" id="cnt-commits">0</div>
        <div class="stat-lbl">Commits (2024)</div>
      </div>
      <div class="stat-card">
        <div class="stat-num blue" id="cnt-stars">0</div>
        <div class="stat-lbl">Stars Earned</div>
      </div>
    </div>
    <div class="streak-bar">
      <div class="streak-label"><span>Current Streak</span><span>🔥 Replace with real data</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:72%"></div></div>
    </div>
    <p style="font-size:0.72rem;color:#404070;font-family:'JetBrains Mono',monospace;margin-top:14px;text-align:center;">
      ↳ Replace numbers with your real stats from github-readme-stats.vercel.app
    </p>
  </div>

  <!-- FUN FACTS -->
  <div class="glass fade-up d6">
    <div class="section-label">05 · When Not Coding</div>
    <div class="code-block">
<span class="c">// life.yaml</span>
<br><span class="k">const</span> <span class="n">me</span> = {
<br>&nbsp;&nbsp;<span class="f">currently_obsessed_with</span>: <span class="s">"[latest thing]"</span>,
<br>&nbsp;&nbsp;<span class="f">hobbies</span>: [<span class="s">"gaming"</span>, <span class="s">"reading"</span>, <span class="s">"[your hobby]"</span>],
<br>&nbsp;&nbsp;<span class="f">fuel</span>: <span class="s">"coffee ☕ and curiosity"</span>,
<br>&nbsp;&nbsp;<span class="f">fun_fact</span>: <span class="s">"[Something surprising about you]"</span>,
<br>&nbsp;&nbsp;<span class="f">life_motto</span>: <span class="s">"Ship it. Learn from it. Improve it."</span>
<br>}
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer fade-up" style="animation-delay:0.7s">
    <p>Built with <span>♥</span> &nbsp;·&nbsp; Open to opportunities &nbsp;·&nbsp; Let's build something great</p>
  </div>

</div>

<script>
  // Typing animation
  const phrases = [
    "Building things that matter.",
    "Open to new opportunities.",
    "Always shipping, always learning.",
    "Let's collaborate on something great."
  ];
  let pi = 0, ci = 0, del = false;
  const el = document.getElementById('typed-text');
  function type() {
    const word = phrases[pi];
    if (!del) {
      el.textContent = word.slice(0, ++ci);
      if (ci === word.length) { del = true; setTimeout(type, 2200); return; }
    } else {
      el.textContent = word.slice(0, --ci);
      if (ci === 0) { del = false; pi = (pi + 1) % phrases.length; }
    }
    setTimeout(type, del ? 40 : 65);
  }
  setTimeout(type, 800);

  // Count-up animation
  function countUp(id, target, suffix = '') {
    const el = document.getElementById(id);
    let cur = 0;
    const step = Math.ceil(target / 60);
    const t = setInterval(() => {
      cur = Math.min(cur + step, target);
      el.textContent = cur + suffix;
      if (cur >= target) clearInterval(t);
    }, 25);
  }
  setTimeout(() => {
    countUp('cnt-repos', 42);
    countUp('cnt-commits', 847);
    countUp('cnt-stars', 230);
  }, 600);
</script>
</body>
</html>

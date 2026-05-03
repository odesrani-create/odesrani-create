<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Om Desrani — Void Circuit Profile</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Rajdhani:wght@600;700&display=swap');

* { box-sizing: border-box; margin: 0; padding: 0; }
body { 
  background: #0d1117; 
  color: #c9d1d9; 
  font-family: 'JetBrains Mono', monospace; 
  line-height: 1.6;
}

.container { max-width: 1200px; margin: 0 auto; }

/* ═══ HERO ═══ */
.hero {
  background: #0d1117;
  padding: 50px 24px 32px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.grid-bg {
  position: absolute;
  inset: 0;
  background: 
    repeating-linear-gradient(0deg, transparent, transparent 39px, #00f5ff0a 39px, #00f5ff0a 40px),
    repeating-linear-gradient(90deg, transparent, transparent 39px, #00f5ff0a 39px, #00f5ff0a 40px);
  pointer-events: none;
}
.hero-title {
  font-family: 'Rajdhani', sans-serif;
  font-size: 64px;
  font-weight: 700;
  color: #00f5ff;
  letter-spacing: 8px;
  text-shadow: 0 0 40px #00f5ff44;
  position: relative;
  margin-bottom: 8px;
}
.hero-subtitle {
  font-size: 14px;
  color: #7efff5;
  letter-spacing: 4px;
  position: relative;
  margin-bottom: 20px;
}
.typing-wrapper {
  font-size: 16px;
  color: #c9d1d9;
  min-height: 28px;
  position: relative;
  margin: 16px 0;
}
.cursor {
  display: inline-block;
  width: 2px;
  height: 1em;
  background: #00f5ff;
  margin-left: 3px;
  vertical-align: text-bottom;
  animation: blink 1s step-end infinite;
}
@keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

.badge-row {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
  margin-top: 20px;
  position: relative;
}
.badge {
  background: #0d1117;
  border: 1px solid #00f5ff;
  color: #00f5ff;
  font-size: 11px;
  padding: 6px 14px;
  border-radius: 3px;
  letter-spacing: 2px;
}
.badge.dim { border-color: #00f5ff44; color: #00f5ff88; }

/* ═══ BINARY RAIN ═══ */
.rain-container {
  width: 100%;
  height: 80px;
  background: #0d1117;
  overflow: hidden;
  position: relative;
}
canvas.rain { width: 100%; height: 100%; }

/* ═══ SECTIONS ═══ */
.section { padding: 40px 24px; }
.section-header {
  font-size: 11px;
  letter-spacing: 3px;
  color: #00f5ff;
  margin-bottom: 24px;
  display: flex;
  align-items: center;
  gap: 12px;
  font-family: 'JetBrains Mono', monospace;
}
.section-header::before {
  content: '╔══════════════════════════════════════════════════════════════╗\a║  ';
  white-space: pre;
  font-size: 10px;
  color: #00f5ff88;
}
.section-header::after {
  content: '\a╚══════════════════════════════════════════════════════════════╝';
  white-space: pre;
  font-size: 10px;
  color: #00f5ff88;
  flex: 1;
}

.divider {
  height: 1px;
  background: linear-gradient(90deg, transparent, #00f5ff33, transparent);
  margin: 0 24px;
}

/* ═══ ABOUT ═══ */
.about-card {
  background: #111820;
  border: 1px solid #00f5ff22;
  border-left: 3px solid #00f5ff;
  border-radius: 6px;
  padding: 24px 28px;
  font-size: 15px;
  line-height: 2;
}
.about-card .highlight { color: #00f5ff; font-weight: 600; }
.about-table {
  width: 100%;
  margin-top: 16px;
  border-collapse: collapse;
}
.about-table td {
  padding: 8px 12px;
  border: 1px solid #00f5ff11;
}
.about-table td:first-child { color: #00f5ff; font-weight: 600; width: 150px; }

/* ═══ TECH STACK ═══ */
.tech-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  justify-content: center;
}
.tech-badge {
  background: #0d1117;
  border: 1px solid;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 1px;
}

/* ═══ STATS ═══ */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 16px;
  margin-bottom: 20px;
}
.stat-card {
  background: #111820;
  border: 1px solid #00f5ff22;
  border-radius: 6px;
  padding: 20px;
  text-align: center;
}
.stat-value {
  font-size: 42px;
  font-weight: 700;
  color: #00f5ff;
  font-family: 'Rajdhani', sans-serif;
  display: block;
}
.stat-label {
  font-size: 11px;
  color: #7efff5;
  letter-spacing: 2px;
  margin-top: 8px;
  display: block;
}

.streak-card {
  background: #111820;
  border: 1px solid #00f5ff44;
  border-radius: 6px;
  padding: 24px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.streak-item { text-align: center; }
.streak-value {
  font-size: 38px;
  color: #00f5ff;
  font-family: 'Rajdhani', sans-serif;
  font-weight: 700;
}
.streak-value.fire { color: #ff6b6b; }
.streak-label {
  font-size: 10px;
  color: #7efff5;
  letter-spacing: 2px;
  margin-top: 6px;
}
.streak-divider { width: 1px; height: 60px; background: #00f5ff22; }

/* ═══ LANGUAGES ═══ */
.lang-list { display: flex; flex-direction: column; gap: 12px; }
.lang-item { display: flex; align-items: center; gap: 12px; }
.lang-name { font-size: 14px; width: 120px; flex-shrink: 0; }
.lang-bar-bg {
  flex: 1;
  height: 8px;
  background: #ffffff0a;
  border-radius: 4px;
  overflow: hidden;
}
.lang-bar { height: 100%; border-radius: 4px; }
.lang-percent {
  font-size: 13px;
  color: #00f5ff;
  width: 50px;
  text-align: right;
  flex-shrink: 0;
}

/* ═══ PROJECTS ═══ */
.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 16px;
}
.project-card {
  background: #111820;
  border: 1px solid #00f5ff22;
  border-radius: 6px;
  padding: 24px;
  position: relative;
  overflow: hidden;
}
.project-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, #00f5ff, transparent);
}
.project-title {
  font-size: 18px;
  font-weight: 700;
  color: #00f5ff;
  font-family: 'Rajdhani', sans-serif;
  margin-bottom: 8px;
  letter-spacing: 1px;
}
.project-desc {
  font-size: 14px;
  color: #8b949e;
  line-height: 1.8;
  margin-bottom: 16px;
}
.project-tag {
  background: #00f5ff0f;
  border: 1px solid #00f5ff33;
  color: #00f5ff;
  font-size: 11px;
  padding: 4px 10px;
  border-radius: 3px;
  letter-spacing: 1px;
  margin-right: 6px;
  display: inline-block;
}

/* ═══ TROPHIES ═══ */
.trophy-grid {
  display: flex;
  gap: 12px;
  overflow-x: auto;
  padding-bottom: 8px;
}
.trophy-card {
  background: #111820;
  border: 1px solid #00f5ff22;
  border-radius: 6px;
  padding: 16px 20px;
  text-align: center;
  flex-shrink: 0;
  min-width: 120px;
}
.trophy-icon { font-size: 28px; display: block; margin-bottom: 8px; }
.trophy-label {
  font-size: 10px;
  color: #7efff5;
  letter-spacing: 1px;
}

/* ═══ CONTACT ═══ */
.contact-buttons {
  display: flex;
  justify-content: center;
  gap: 16px;
  flex-wrap: wrap;
  padding: 20px 0;
}
.contact-btn {
  background: #111820;
  border: 1px solid #00f5ff44;
  color: #00f5ff;
  font-size: 13px;
  padding: 12px 24px;
  border-radius: 4px;
  letter-spacing: 2px;
  font-family: 'JetBrains Mono', monospace;
  cursor: pointer;
  transition: all 0.2s;
  text-decoration: none;
  display: inline-block;
}
.contact-btn:hover {
  background: #00f5ff11;
  border-color: #00f5ff;
}

/* ═══ FOOTER ═══ */
.footer {
  text-align: center;
  padding: 30px 24px 20px;
  font-size: 11px;
  color: #00f5ff44;
  border-top: 1px solid #00f5ff11;
  letter-spacing: 2px;
}
</style>
</head>
<body>

<div class="container">

  <!-- ═══════════════════════════════════════════════════════════ -->
  <!--  HERO SECTION                                              -->
  <!-- ═══════════════════════════════════════════════════════════ -->
  <div class="hero">
    <div class="grid-bg"></div>
    <div class="hero-title">OM DESRANI</div>
    <div class="hero-subtitle">STUDENT · DEVELOPER · BUILDER</div>
    <div class="typing-wrapper">
      <span id="typed-text"></span><span class="cursor"></span>
    </div>
    <div class="badge-row">
      <span class="badge">OPEN TO COLLAB</span>
      <span class="badge">INDIA 🇮🇳</span>
      <span class="badge dim">odesrani-create</span>
    </div>
  </div>

  <!-- BINARY RAIN #1 -->
  <div class="rain-container"><canvas class="rain" id="rain1"></canvas></div>

  <!-- ═══════════════════════════════════════════════════════════ -->
  <!--  ABOUT SECTION                                             -->
  <!-- ═══════════════════════════════════════════════════════════ -->
  <div class="section">
    <h2 class="section-header">/whoami</h2>
    <div class="about-card">
      <p><strong class="highlight">Student & Developer</strong> on a mission to build things that matter.<br>
      I write code, break things, learn from it, and repeat.<br>
      Currently diving deep into <strong class="highlight">Web Development</strong> — one commit at a time.</p>
      
      <table class="about-table">
        <tr>
          <td>🌱 Learning</td>
          <td>React ecosystem, APIs, backend basics</td>
        </tr>
        <tr>
          <td>🚀 Building</td>
          <td>Personal projects that solve real problems</td>
        </tr>
        <tr>
          <td>⚡ Superpower</td>
          <td>Turning curiosity into working prototypes</td>
        </tr>
        <tr>
          <td>🎯 Goal 2025</td>
          <td>5 shipped projects + open source contributions</td>
        </tr>
        <tr>
          <td>🌐 Based in</td>
          <td>India 🇮🇳</td>
        </tr>
      </table>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ═══════════════════════════════════════════════════════════ -->
  <!--  TECH STACK                                                -->
  <!-- ═══════════════════════════════════════════════════════════ -->
  <div class="section">
    <h2 class="section-header">/tech-stack</h2>
    <div class="tech-grid">
      <span class="tech-badge" style="border-color:#3572a5; color:#3572a5;">Python</span>
      <span class="tech-badge" style="border-color:#f7df1e; color:#f7df1e;">JavaScript</span>
      <span class="tech-badge" style="border-color:#61dafb; color:#61dafb;">React</span>
      <span class="tech-badge" style="border-color:#e34f26; color:#e34f26;">HTML5</span>
      <span class="tech-badge" style="border-color:#1572b6; color:#1572b6;">CSS3</span>
      <span class="tech-badge" style="border-color:#3c873a; color:#3c873a;">Node.js</span>
      <span class="tech-badge" style="border-color:#f05032; color:#f05032;">Git</span>
      <span class="tech-badge" style="border-color:#00f5ff44; color:#00f5ff88;">TypeScript ↗</span>
      <span class="tech-badge" style="border-color:#00f5ff44; color:#00f5ff88;">Tailwind ↗</span>
    </div>
  </div>

  <!-- BINARY RAIN #2 -->
  <div class="rain-container" style="height:60px"><canvas class="rain" id="rain2"></canvas></div>

  <!-- ═══════════════════════════════════════════════════════════ -->
  <!--  GITHUB STATS                                              -->
  <!-- ═══════════════════════════════════════════════════════════ -->
  <div class="section">
    <h2 class="section-header">/github-stats</h2>
    <div class="stats-grid">
      <div class="stat-card">
        <span class="stat-value">50+</span>
        <span class="stat-label">COMMITS</span>
      </div>
      <div class="stat-card">
        <span class="stat-value" id="repo-count">—</span>
        <span class="stat-label">PUBLIC REPOS</span>
      </div>
    </div>
    
    <div class="streak-card">
      <div class="streak-item">
        <div class="streak-value">7</div>
        <div class="streak-label">TOTAL DAYS</div>
      </div>
      <div class="streak-divider"></div>
      <div class="streak-item">
        <div class="streak-value fire">3 🔥</div>
        <div class="streak-label">CURRENT</div>
      </div>
      <div class="streak-divider"></div>
      <div class="streak-item">
        <div class="streak-value">7</div>
        <div class="streak-label">LONGEST</div>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ═══════════════════════════════════════════════════════════ -->
  <!--  TOP LANGUAGES                                             -->
  <!-- ═══════════════════════════════════════════════════════════ -->
  <div class="section">
    <h2 class="section-header">/top-languages</h2>
    <div class="lang-list">
      <div class="lang-item">
        <span class="lang-name">Python</span>
        <div class="lang-bar-bg">
          <div class="lang-bar" style="width:60%; background:linear-gradient(90deg,#3572a5,#00f5ff)"></div>
        </div>
        <span class="lang-percent">60%</span>
      </div>
      <div class="lang-item">
        <span class="lang-name">JavaScript</span>
        <div class="lang-bar-bg">
          <div class="lang-bar" style="width:25%; background:linear-gradient(90deg,#f7df1e,#e0c700)"></div>
        </div>
        <span class="lang-percent">25%</span>
      </div>
      <div class="lang-item">
        <span class="lang-name">HTML / CSS</span>
        <div class="lang-bar-bg">
          <div class="lang-bar" style="width:15%; background:linear-gradient(90deg,#e34f26,#ff6b35)"></div>
        </div>
        <span class="lang-percent">15%</span>
      </div>
    </div>
  </div>

  <!-- BINARY RAIN #3 -->
  <div class="rain-container" style="height:60px"><canvas class="rain" id="rain3"></canvas></div>

  <!-- ═══════════════════════════════════════════════════════════ -->
  <!--  FEATURED PROJECTS                                         -->
  <!-- ═══════════════════════════════════════════════════════════ -->
  <div class="section">
    <h2 class="section-header">/featured-projects</h2>
    <div class="project-grid">
      <div class="project-card">
        <div class="project-title">⬡ PROJECT ALPHA</div>
        <div class="project-desc">
          Python automation tool — clean, utility-focused, built for real problems.
        </div>
        <span class="project-tag">PYTHON</span>
        <span class="project-tag" style="border-color:#f7df1e33; color:#f7df1e;">IN PROGRESS</span>
      </div>
      <div class="project-card">
        <div class="project-title">⬡ PROJECT BETA</div>
        <div class="project-desc">
          React frontend app exploring components, state management, and API integration.
        </div>
        <span class="project-tag" style="border-color:#61dafb33; color:#61dafb;">REACT</span>
        <span class="project-tag">LEARNING</span>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ═══════════════════════════════════════════════════════════ -->
  <!--  TROPHIES                                                  -->
  <!-- ═══════════════════════════════════════════════════════════ -->
  <div class="section">
    <h2 class="section-header">/trophies</h2>
    <div class="trophy-grid">
      <div class="trophy-card">
        <span class="trophy-icon">🏆</span>
        <span class="trophy-label">FIRST COMMIT</span>
      </div>
      <div class="trophy-card">
        <span class="trophy-icon">⭐</span>
        <span class="trophy-label">FIRST STAR</span>
      </div>
      <div class="trophy-card">
        <span class="trophy-icon">🔥</span>
        <span class="trophy-label">STREAK</span>
      </div>
      <div class="trophy-card">
        <span class="trophy-icon">🚀</span>
        <span class="trophy-label">BUILDER</span>
      </div>
      <div class="trophy-card">
        <span class="trophy-icon">📦</span>
        <span class="trophy-label">MULTI-REPO</span>
      </div>
    </div>
  </div>

  <!-- BINARY RAIN #4 -->
  <div class="rain-container" style="height:60px"><canvas class="rain" id="rain4"></canvas></div>

  <!-- ═══════════════════════════════════════════════════════════ -->
  <!--  CONNECT                                                   -->
  <!-- ═══════════════════════════════════════════════════════════ -->
  <div class="section">
    <h2 class="section-header">/connect</h2>
    <p style="text-align:center; font-style:italic; margin-bottom:20px;">Let's build something together.</p>
    <div class="contact-buttons">
      <a href="https://github.com/odesrani-create" class="contact-btn">GITHUB</a>
      <a href="https://linkedin.com/in/your-profile" class="contact-btn">LINKEDIN</a>
      <a href="mailto:your@email.com" class="contact-btn">EMAIL</a>
    </div>
  </div>

  <!-- ═══════════════════════════════════════════════════════════ -->
  <!--  FOOTER                                                    -->
  <!-- ═══════════════════════════════════════════════════════════ -->
  <div class="footer">
    // BUILT WITH ❤️ AND LATE NIGHTS · THEME: VOID CIRCUIT · OM DESRANI · 2025
  </div>

</div>

<script>
// ═══════════════════════════════════════════════════════════════════
//  TYPING ANIMATION
// ═══════════════════════════════════════════════════════════════════
const phrases = [
  '01001000 01100101 01101100 01101100 01101111 👾',
  "Hello, World. I'm Om.",
  '01000010 01110101 01101001 01101100 01100100 01101001 01101110 01100111...',
  'Student & Developer in the making',
  '01010111 01100101 01100010 00100000 01000100 01100101 01110110',
  'Turning coffee → code → products',
  '01001111 01110000 01100101 01101110 00100000 01010011 01101111 01110101 01110010 01100011 01100101',
  'Always learning. Always building.'
];

let phraseIndex = 0;
let charIndex = 0;
let isDeleting = false;
const typedElement = document.getElementById('typed-text');

function typeEffect() {
  const currentPhrase = phrases[phraseIndex];
  
  if (!isDeleting) {
    typedElement.textContent = currentPhrase.slice(0, ++charIndex);
    if (charIndex === currentPhrase.length) {
      isDeleting = true;
      setTimeout(typeEffect, 1800);
      return;
    }
  } else {
    typedElement.textContent = currentPhrase.slice(0, --charIndex);
    if (charIndex === 0) {
      isDeleting = false;
      phraseIndex = (phraseIndex + 1) % phrases.length;
      setTimeout(typeEffect, 300);
      return;
    }
  }
  
  setTimeout(typeEffect, isDeleting ? 30 : (charIndex > currentPhrase.length * 0.6 ? 60 : 80));
}

typeEffect();

// ═══════════════════════════════════════════════════════════════════
//  GITHUB API — LIVE REPO COUNT
// ═══════════════════════════════════════════════════════════════════
fetch('https://api.github.com/users/odesrani-create')
  .then(response => response.json())
  .then(data => {
    const repoElement = document.getElementById('repo-count');
    if (repoElement && data.public_repos != null) {
      repoElement.textContent = data.public_repos;
    }
  })
  .catch(() => {});

// ═══════════════════════════════════════════════════════════════════
//  BINARY RAIN ENGINE
// ═══════════════════════════════════════════════════════════════════
function initBinaryRain(canvasId, height) {
  const canvas = document.getElementById(canvasId);
  if (!canvas) return;
  
  const parent = canvas.parentElement;
  const width = parent.offsetWidth;
  canvas.width = width;
  canvas.height = height;
  
  const ctx = canvas.getContext('2d');
  const columns = Math.floor(width / 18);
  const drops = Array.from({ length: columns }, () => Math.random() * -height * 1.5);
  const speeds = Array.from({ length: columns }, () => 0.4 + Math.random() * 1.0);
  
  function draw() {
    ctx.fillStyle = 'rgba(13, 17, 23, 0.20)';
    ctx.fillRect(0, 0, width, height);
    
    for (let i = 0; i < columns; i++) {
      const yPos = drops[i];
      const bit = Math.random() < 0.5 ? '0' : '1';
      const progress = yPos / height;
      const isHead = progress > 0.6 && progress < 0.75;
      
      if (isHead) {
        ctx.fillStyle = '#ffffff';
        ctx.font = 'bold 14px JetBrains Mono, monospace';
      } else {
        const alpha = Math.max(0.08, Math.min(0.75, progress * 0.85));
        ctx.fillStyle = `rgba(0, 245, 255, ${alpha})`;
        ctx.font = '13px JetBrains Mono, monospace';
      }
      
      ctx.fillText(bit, i * 18 + 3, yPos);
      
      drops[i] += speeds[i] * 14;
      
      if (drops[i] > height + 20) {
        drops[i] = Math.random() * -height * 0.6;
        speeds[i] = 0.4 + Math.random() * 1.0;
      }
    }
  }
  
  setInterval(draw, 60);
}

// Initialize all rain canvases
initBinaryRain('rain1', 80);
initBinaryRain('rain2', 60);
initBinaryRain('rain3', 60);
initBinaryRain('rain4', 60);
</script>

</body>
</html>

<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Kleber Junior — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet"/>
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg:       #060b18;
  --surface:  #0a1020;
  --surface2: #0d1530;
  --border:   #1a2540;
  --border2:  #1e2d52;
  --blue:     #3b82f6;
  --blue2:    #60a5fa;
  --blue3:    #93c5fd;
  --blue4:    #1d4ed8;
  --text:     #e2e8f0;
  --muted:    #64748b;
  --muted2:   #94a3b8;
  --green:    #22d3ee;
}

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Plus Jakarta Sans', sans-serif;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  padding: 40px 16px;
  background-image:
    radial-gradient(ellipse 60% 40% at 80% 10%, rgba(59,130,246,0.07) 0%, transparent 60%),
    radial-gradient(ellipse 50% 30% at 20% 90%, rgba(29,78,216,0.06) 0%, transparent 60%);
}

.wrapper {
  max-width: 760px;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 14px;
}

/* ── HEADER ── */
.header {
  text-align: center;
  padding: 52px 28px 36px;
  background: var(--surface);
  border: 1px solid var(--border2);
  border-radius: 16px;
  position: relative;
  overflow: hidden;
  animation: fadeUp .7s ease both;
}
.header::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse 90% 55% at 50% -5%, rgba(59,130,246,0.2) 0%, transparent 65%);
  pointer-events: none;
}
.header::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, transparent, var(--blue), var(--blue2), transparent);
}

.ascii {
  font-family: 'Fira Code', monospace;
  font-size: clamp(5.5px, 1.3vw, 11px);
  color: var(--blue2);
  line-height: 1.35;
  letter-spacing: 0.05em;
  margin-bottom: 22px;
  opacity: 0.85;
  text-shadow: 0 0 20px rgba(59,130,246,0.4);
}

.name-line {
  font-family: 'Fira Code', monospace;
  font-size: .95rem;
  color: var(--muted2);
  margin-bottom: 16px;
}
.name-line strong { color: var(--text); font-weight: 600; }

.typing-wrap {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(59,130,246,0.08);
  border: 1px solid rgba(59,130,246,0.22);
  border-radius: 8px;
  padding: 7px 18px;
  font-family: 'Fira Code', monospace;
  font-size: .78rem;
  color: var(--blue2);
}
.cursor {
  display: inline-block;
  width: 2px; height: 1em;
  background: var(--blue2);
  vertical-align: middle;
  animation: blink 1s step-end infinite;
}

/* ── CARD ── */
.card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 28px 32px;
  animation: fadeUp .8s ease both;
  position: relative;
  overflow: hidden;
}
.card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(59,130,246,0.3), transparent);
}

h2 {
  font-size: .78rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: .14em;
  color: var(--blue2);
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 10px;
}
h2::after {
  content: '';
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, var(--border2), transparent);
}

p {
  color: var(--muted2);
  font-size: .9rem;
  line-height: 1.8;
  margin-bottom: 12px;
}
p strong { color: var(--text); font-weight: 600; }

/* ── CODE BLOCK ── */
.codeblock {
  background: #04080f;
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 20px 24px;
  font-family: 'Fira Code', monospace;
  font-size: .8rem;
  line-height: 2;
  margin-top: 10px;
  position: relative;
  overflow: hidden;
}
.codeblock::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: linear-gradient(135deg, rgba(59,130,246,0.04) 0%, transparent 60%);
  pointer-events: none;
}
.kw  { color: #7dd3fc; }
.str { color: #bae6fd; }
.key { color: var(--blue2); }
.brace { color: var(--text); }
.cm  { color: #475569; font-style: italic; }

/* ── BADGE SECTIONS ── */
.badge-section-label {
  font-family: 'Fira Code', monospace;
  font-size: .68rem;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: .1em;
  margin: 16px 0 8px;
}
.badge-section-label:first-child { margin-top: 0; }

.badge-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  background: #04080f;
  border: 1px solid var(--border2);
  border-radius: 7px;
  padding: 6px 14px;
  font-family: 'Fira Code', monospace;
  font-size: .76rem;
  color: var(--text);
  transition: border-color .2s, transform .2s, box-shadow .2s;
  cursor: default;
}
.badge:hover {
  border-color: var(--blue);
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(59,130,246,0.15);
}
.dot {
  width: 7px; height: 7px;
  border-radius: 50%;
  background: var(--blue);
  flex-shrink: 0;
  box-shadow: 0 0 6px rgba(59,130,246,0.6);
}

/* ── STATS MOCK ── */
.stats-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 14px;
}
@media (max-width: 500px) { .stats-grid { grid-template-columns: 1fr; } }

.stats-card {
  background: #04080f;
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 18px 20px;
}
.stats-title {
  font-size: .68rem;
  font-family: 'Fira Code', monospace;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: .08em;
  margin-bottom: 14px;
}
.stat-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Fira Code', monospace;
  font-size: .78rem;
  color: var(--muted2);
  padding: 5px 0;
  border-bottom: 1px solid rgba(26,37,64,0.6);
}
.stat-row:last-child { border-bottom: none; }
.stat-row .vn { color: var(--blue2); font-weight: 600; }

.bar-wrap {
  height: 5px;
  background: var(--border);
  border-radius: 3px;
  margin: 8px 0 4px;
  overflow: hidden;
}
.bar-fill {
  height: 100%;
  border-radius: 3px;
  background: linear-gradient(90deg, var(--blue4), var(--blue), var(--blue2));
  animation: growBar 1.8s ease both;
  animation-delay: .4s;
}

.streak-card {
  background: #04080f;
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 18px 24px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  flex-wrap: wrap;
  gap: 16px;
}
.streak-item { text-align: center; }
.streak-num {
  font-family: 'Fira Code', monospace;
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--blue2);
  text-shadow: 0 0 16px rgba(96,165,250,0.4);
}
.streak-label {
  font-family: 'Fira Code', monospace;
  font-size: .68rem;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: .08em;
  margin-top: 4px;
}

/* ── LINKS ── */
.link-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 12px;
  margin-top: 8px;
}
.link-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: #04080f;
  border: 1px solid var(--border2);
  border-radius: 10px;
  padding: 10px 22px;
  font-family: 'Fira Code', monospace;
  font-size: .82rem;
  color: var(--text);
  text-decoration: none;
  transition: border-color .2s, transform .2s, box-shadow .2s;
}
.link-btn:hover {
  border-color: var(--blue);
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(59,130,246,0.18);
}

/* ── FOOTER ── */
.footer {
  text-align: center;
  padding: 30px 28px;
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 14px;
  position: relative;
  overflow: hidden;
  animation: fadeUp 1.1s ease both;
}
.footer::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, transparent, var(--blue4), var(--blue), transparent);
}
.footer q {
  font-size: .92rem;
  color: var(--muted2);
  font-style: italic;
  line-height: 1.7;
}
.visitor-badge {
  display: inline-block;
  margin-top: 14px;
  background: #04080f;
  border: 1px solid var(--border2);
  border-radius: 6px;
  padding: 4px 14px;
  font-family: 'Fira Code', monospace;
  font-size: .72rem;
  color: var(--blue2);
}

/* ── ANIMATIONS ── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(18px); }
  to   { opacity: 1; transform: translateY(0); }
}
@keyframes blink {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0; }
}
@keyframes growBar {
  from { width: 0; }
}
</style>
</head>
<body>
<div class="wrapper">

  <!-- HEADER -->
  <div class="header">
    <div class="ascii">
██╗  ██╗██╗     ███████╗██████╗ ███████╗██████╗ &nbsp;<br>
██║ ██╔╝██║     ██╔════╝██╔══██╗██╔════╝██╔══██╗<br>
█████╔╝ ██║     █████╗  ██████╔╝█████╗  ██████╔╝<br>
██╔═██╗ ██║     ██╔══╝  ██╔══██╗██╔══╝  ██╔══██╗<br>
██║  ██╗███████╗███████╗██████╔╝███████╗██║  ██║&nbsp;<br>
╚═╝  ╚═╝╚══════╝╚══════╝╚═════╝ ╚══════╝╚═╝  ╚═╝<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;J U N I O R
    </div>
    <div class="name-line"><strong>> Kleber Junior</strong> &nbsp;·&nbsp; estudante &nbsp;·&nbsp; dev &nbsp;·&nbsp; entusiasta de IA</div>
    <div class="typing-wrap"><span id="typing"></span><span class="cursor"></span></div>
  </div>

  <!-- ABOUT -->
  <div class="card">
    <h2>🚀 Sobre mim</h2>
    <p>
      Sou estudante de <strong>Engenharia da Computação</strong> na <strong>Universidade Federal do Pará (UFPA)</strong>,
      movido pela curiosidade e pela vontade de construir coisas que façam sentido no mundo real.
    </p>
    <p>
      Tenho interesse em <strong>desenvolvimento de software</strong> — do front ao back — e em tudo que envolve
      <strong>Inteligência Artificial</strong>: desde modelos que aprendem a partir de dados até sistemas que tomam decisões inteligentes.
      Acredito que código bem escrito é uma forma de arte, e que boa engenharia começa com fazer as perguntas certas.
    </p>
    <div class="codeblock">
<span class="kw">kleber</span> <span class="brace">= {</span><br>
&nbsp;&nbsp;<span class="key">"formação"</span>:    <span class="str">"Engenharia da Computação @ UFPA"</span>,<br>
&nbsp;&nbsp;<span class="key">"localização"</span>: <span class="str">"Pará, Brasil 🌊"</span>,<br>
&nbsp;&nbsp;<span class="key">"interesses"</span>:  <span class="brace">[</span><span class="str">"Desenvolvimento Web"</span>, <span class="str">"Inteligência Artificial"</span>, <span class="str">"Algoritmos"</span><span class="brace">]</span>,<br>
&nbsp;&nbsp;<span class="key">"atualmente"</span>:  <span class="str">"Aprofundando conhecimentos em IA e frameworks modernos"</span>,<br>
&nbsp;&nbsp;<span class="key">"objetivo"</span>:    <span class="str">"Construir soluções que importam — com elegância e propósito"</span><br>
<span class="brace">}</span>
    </div>
  </div>

  <!-- STACK -->
  <div class="card">
    <h2>🛠 Tecnologias &amp; Ferramentas</h2>

    <div class="badge-section-label">Linguagens</div>
    <div class="badge-grid">
      <span class="badge"><span class="dot"></span>Python</span>
      <span class="badge"><span class="dot"></span>C</span>
      <span class="badge"><span class="dot"></span>JavaScript</span>
      <span class="badge"><span class="dot"></span>Java</span>
    </div>

    <div class="badge-section-label">Frontend</div>
    <div class="badge-grid">
      <span class="badge"><span class="dot"></span>React</span>
      <span class="badge"><span class="dot"></span>Next.js</span>
      <span class="badge"><span class="dot"></span>Tailwind CSS</span>
      <span class="badge"><span class="dot"></span>HTML5</span>
      <span class="badge"><span class="dot"></span>CSS3</span>
    </div>

    <div class="badge-section-label">Ferramentas</div>
    <div class="badge-grid">
      <span class="badge"><span class="dot"></span>Git</span>
      <span class="badge"><span class="dot"></span>VS Code</span>
      <span class="badge"><span class="dot"></span>Linux</span>
    </div>
  </div>

  <!-- STATS -->
  <div class="card">
    <h2>📊 GitHub Stats</h2>
    <div class="stats-grid">
      <div class="stats-card">
        <div class="stats-title">github_stats.json</div>
        <div class="stat-row"><span>commits</span><span class="vn">↑ crescendo</span></div>
        <div class="stat-row"><span>repos públicos</span><span class="vn" style="color:#22d3ee">✦</span></div>
        <div class="stat-row"><span>pull requests</span><span class="vn">merged</span></div>
        <div class="stat-row"><span>contribuições</span><span class="vn">📈</span></div>
        <div class="bar-wrap"><div class="bar-fill" style="width:68%"></div></div>
        <span style="font-size:.68rem;font-family:'Fira Code',monospace;color:var(--muted)">consistência.exe rodando</span>
      </div>
      <div class="stats-card">
        <div class="stats-title">top_langs.json</div>
        <div class="stat-row"><span>Python</span><span class="vn">████ 45%</span></div>
        <div class="stat-row"><span>Java</span><span class="vn">███ 25%</span></div>
        <div class="stat-row"><span>JavaScript</span><span class="vn">██ 20%</span></div>
        <div class="stat-row"><span>C</span><span class="vn">█ 10%</span></div>
      </div>
    </div>
    <div class="streak-card">
      <div class="streak-item">
        <div class="streak-num" style="font-size:1.1rem;color:var(--muted2)">🔥</div>
        <div class="streak-num" id="streak-num">0</div>
        <div class="streak-label">streak atual</div>
      </div>
      <div class="streak-item">
        <div class="streak-num" id="longest-num">0</div>
        <div class="streak-label">maior streak</div>
      </div>
      <div class="streak-item">
        <div class="streak-num" id="total-num">0</div>
        <div class="streak-label">contribuições</div>
      </div>
    </div>
    <p style="margin-top:12px;font-size:.72rem;color:var(--muted);font-family:'Fira Code',monospace;text-align:center;">
      * substitua SEU_USERNAME nos links do README.md para ativar os stats reais
    </p>
  </div>

  <!-- LINKS -->
  <div class="card" style="text-align:center;">
    <h2>🌐 Onde me encontrar</h2>
    <div class="link-grid">
      <a class="link-btn" href="#">
        <svg width="15" height="15" fill="#0A66C2" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="link-btn" href="#">
        <svg width="15" height="15" fill="#EA4335" viewBox="0 0 24 24"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.910 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        Email
      </a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <q>A melhor forma de prever o futuro é programá-lo.</q>
    <br>
    <span class="visitor-badge">👁 visitor count</span>
  </div>

</div>
<script>
// Typing effect
const lines = [
  "Engenharia da Computação @ UFPA",
  "Apaixonado por desenvolvimento e IA",
  "Sempre aprendendo, sempre construindo",
  "Transformando lógica em soluções reais"
];
let i = 0, j = 0, del = false;
const el = document.getElementById('typing');
function type() {
  const cur = lines[i];
  if (!del) {
    el.textContent = cur.slice(0, j + 1);
    j++;
    if (j === cur.length) { del = true; setTimeout(type, 1800); return; }
  } else {
    el.textContent = cur.slice(0, j);
    j--;
    if (j < 0) { del = false; i = (i + 1) % lines.length; setTimeout(type, 400); return; }
  }
  setTimeout(type, del ? 38 : 58);
}
type();

// Counter animation
function animCount(id, target, duration) {
  const el = document.getElementById(id);
  let start = 0;
  const step = target / (duration / 16);
  const timer = setInterval(() => {
    start += step;
    if (start >= target) { el.textContent = target; clearInterval(timer); return; }
    el.textContent = Math.floor(start);
  }, 16);
}
setTimeout(() => {
  animCount('streak-num', 12, 900);
  animCount('longest-num', 30, 1100);
  animCount('total-num', 247, 1400);
}, 600);
</script>
</body>
</html>

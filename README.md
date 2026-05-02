

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
  --bg:      #060b18;
  --surface: #0a1020;
  --border:  #1a2540;
  --border2: #1e2d52;
  --blue:    #3b82f6;
  --blue2:   #60a5fa;
  --blue3:   #93c5fd;
  --blue4:   #1d4ed8;
  --text:    #e2e8f0;
  --muted:   #64748b;
  --muted2:  #94a3b8;
}
body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Plus Jakarta Sans', sans-serif;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  /* extra bottom padding so fixed bar doesn't cover content */
  padding: 40px 16px 110px;
  background-image:
    radial-gradient(ellipse 60% 40% at 80% 10%, rgba(59,130,246,0.07) 0%, transparent 60%),
    radial-gradient(ellipse 50% 30% at 20% 90%, rgba(29,78,216,0.06) 0%, transparent 60%);
}
 
.wrapper { max-width: 760px; width: 100%; display: flex; flex-direction: column; gap: 14px; }
 
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
  content:'';position:absolute;inset:0;
  background:radial-gradient(ellipse 90% 55% at 50% -5%,rgba(59,130,246,.2) 0%,transparent 65%);
  pointer-events:none;
}
.header::after {
  content:'';position:absolute;bottom:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--blue),var(--blue2),transparent);
}
.ascii {
  font-family:'Fira Code',monospace;
  font-size:clamp(5.5px,1.3vw,11px);
  color:var(--blue2);line-height:1.35;letter-spacing:.05em;
  margin-bottom:22px;opacity:.85;
  text-shadow:0 0 20px rgba(59,130,246,.4);
}
.name-line { font-family:'Fira Code',monospace;font-size:.95rem;color:var(--muted2);margin-bottom:16px; }
.name-line strong { color:var(--text);font-weight:600; }
.typing-wrap {
  display:inline-flex;align-items:center;gap:8px;
  background:rgba(59,130,246,.08);border:1px solid rgba(59,130,246,.22);
  border-radius:8px;padding:7px 18px;
  font-family:'Fira Code',monospace;font-size:.78rem;color:var(--blue2);
}
.cursor {
  display:inline-block;width:2px;height:1em;
  background:var(--blue2);vertical-align:middle;
  animation:blink 1s step-end infinite;
}
 
/* ── CARD ── */
.card {
  background:var(--surface);border:1px solid var(--border);
  border-radius:14px;padding:28px 32px;
  animation:fadeUp .8s ease both;position:relative;overflow:hidden;
}
.card::before {
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,rgba(59,130,246,.3),transparent);
}
h2 {
  font-size:.78rem;font-weight:700;text-transform:uppercase;
  letter-spacing:.14em;color:var(--blue2);margin-bottom:20px;
  display:flex;align-items:center;gap:10px;
}
h2::after { content:'';flex:1;height:1px;background:linear-gradient(90deg,var(--border2),transparent); }
p { color:var(--muted2);font-size:.9rem;line-height:1.8;margin-bottom:12px; }
p strong { color:var(--text);font-weight:600; }
 
.codeblock {
  background:#04080f;border:1px solid var(--border);border-radius:10px;
  padding:20px 24px;font-family:'Fira Code',monospace;font-size:.8rem;
  line-height:2;margin-top:10px;position:relative;overflow:hidden;
}
.codeblock::before {
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(59,130,246,.04) 0%,transparent 60%);
  pointer-events:none;
}
.kw{color:#7dd3fc}.str{color:#bae6fd}.key{color:var(--blue2)}.brace{color:var(--text)}
 
/* ── CAROUSEL ── */
.carousel-section { overflow:hidden; }
 
.carousel-label {
  font-family:'Fira Code',monospace;font-size:.7rem;color:var(--muted);
  text-transform:uppercase;letter-spacing:.1em;
  margin-bottom:12px;display:flex;align-items:center;gap:8px;
}
.carousel-label::before {
  content:'//';color:var(--blue4);font-size:.72rem;
}
 
.track-wrap {
  overflow:hidden;
  padding:10px 0;
  mask-image:linear-gradient(90deg,transparent 0%,black 8%,black 92%,transparent 100%);
  -webkit-mask-image:linear-gradient(90deg,transparent 0%,black 8%,black 92%,transparent 100%);
  margin-bottom:22px;
}
.track {
  display:flex;
  gap:14px;
  width:max-content;
  animation:slide 22s linear infinite;
}
.track:hover { animation-play-state:paused; }
 
.tech-card {
  display:flex;flex-direction:column;align-items:center;gap:8px;
  background:#04080f;border:1px solid var(--border2);
  border-radius:12px;padding:14px 18px;min-width:82px;
  transition:border-color .2s,transform .2s,box-shadow .2s;
  cursor:default;flex-shrink:0;
}
.tech-card:hover {
  border-color:var(--blue);transform:translateY(-4px);
  box-shadow:0 8px 24px rgba(59,130,246,.2);
}
.tech-icon { width:36px;height:36px;display:flex;align-items:center;justify-content:center; }
.tech-icon svg,.tech-icon img { width:36px;height:36px; }
.tech-name {
  font-family:'Fira Code',monospace;font-size:.65rem;
  color:var(--muted2);white-space:nowrap;
}
 
/* ── STATS ── */
.stats-grid { display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:14px; }
@media(max-width:500px){.stats-grid{grid-template-columns:1fr}}
.stats-card {
  background:#04080f;border:1px solid var(--border);border-radius:10px;padding:18px 20px;
}
.stats-title {
  font-size:.68rem;font-family:'Fira Code',monospace;color:var(--muted);
  text-transform:uppercase;letter-spacing:.08em;margin-bottom:14px;
}
.stat-row {
  display:flex;justify-content:space-between;align-items:center;
  font-family:'Fira Code',monospace;font-size:.78rem;color:var(--muted2);
  padding:5px 0;border-bottom:1px solid rgba(26,37,64,.6);
}
.stat-row:last-child{border-bottom:none}
.stat-row .vn{color:var(--blue2);font-weight:600}
.bar-wrap{height:5px;background:var(--border);border-radius:3px;margin:8px 0 4px;overflow:hidden}
.bar-fill{height:100%;border-radius:3px;background:linear-gradient(90deg,var(--blue4),var(--blue),var(--blue2));animation:growBar 1.8s ease both;animation-delay:.4s}
 
.streak-card {
  background:#04080f;border:1px solid var(--border);border-radius:10px;
  padding:18px 24px;display:flex;align-items:center;justify-content:space-around;flex-wrap:wrap;gap:16px;
}
.streak-item{text-align:center}
.streak-num{font-family:'Fira Code',monospace;font-size:1.5rem;font-weight:600;color:var(--blue2);text-shadow:0 0 16px rgba(96,165,250,.4)}
.streak-label{font-family:'Fira Code',monospace;font-size:.68rem;color:var(--muted);text-transform:uppercase;letter-spacing:.08em;margin-top:4px}
 
/* ── FIXED CONTACT BAR ── */
.contact-bar {
  position:fixed;bottom:0;left:0;right:0;
  background:rgba(6,11,24,0.92);
  backdrop-filter:blur(20px);
  border-top:1px solid var(--border2);
  padding:14px 20px;
  display:flex;align-items:center;justify-content:center;gap:16px;
  z-index:100;
  animation:slideUp .6s ease both;
  animation-delay:.3s;
}
.contact-bar::before {
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--blue),var(--blue2),transparent);
}
.contact-label {
  font-family:'Fira Code',monospace;font-size:.7rem;
  color:var(--muted);text-transform:uppercase;letter-spacing:.1em;
}
.contact-btn {
  display:inline-flex;align-items:center;gap:8px;
  background:var(--surface);border:1px solid var(--border2);
  border-radius:10px;padding:9px 20px;
  font-family:'Fira Code',monospace;font-size:.82rem;
  color:var(--text);text-decoration:none;
  transition:border-color .2s,transform .2s,box-shadow .2s;
}
.contact-btn:hover {
  border-color:var(--blue);transform:translateY(-2px);
  box-shadow:0 6px 20px rgba(59,130,246,.2);
}
.contact-divider {
  width:1px;height:28px;background:var(--border2);
}
 
/* QUOTE */
.quote-footer {
  text-align:center;padding:28px;background:var(--surface);
  border:1px solid var(--border);border-radius:14px;
  position:relative;overflow:hidden;animation:fadeUp 1.1s ease both;
}
.quote-footer q { font-size:.92rem;color:var(--muted2);font-style:italic;line-height:1.7; }
.visitor-badge {
  display:inline-block;margin-top:14px;
  background:#04080f;border:1px solid var(--border2);border-radius:6px;
  padding:4px 14px;font-family:'Fira Code',monospace;font-size:.72rem;color:var(--blue2);
}
 
/* ANIMATIONS */
@keyframes fadeUp{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:translateY(0)}}
@keyframes slideUp{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
@keyframes growBar{from{width:0}}
@keyframes slide{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
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
  <p>Sou estudante de <strong>Engenharia da Computação</strong> na <strong>Universidade Federal do Pará (UFPA)</strong>, movido pela curiosidade e pela vontade de construir coisas que façam sentido no mundo real.</p>
  <p>Tenho interesse em <strong>desenvolvimento de software</strong> — do front ao back — e em tudo que envolve <strong>Inteligência Artificial</strong>: desde modelos que aprendem com dados até sistemas que tomam decisões inteligentes.</p>
  <div class="codeblock">
<span class="kw">kleber</span> <span class="brace">= {</span><br>
&nbsp;&nbsp;<span class="key">"formação"</span>:    <span class="str">"Engenharia da Computação @ UFPA"</span>,<br>
&nbsp;&nbsp;<span class="key">"localização"</span>: <span class="str">"Pará, Brasil 🌊"</span>,<br>
&nbsp;&nbsp;<span class="key">"interesses"</span>:  <span class="brace">[</span><span class="str">"Dev Web"</span>, <span class="str">"Inteligência Artificial"</span>, <span class="str">"Algoritmos"</span><span class="brace">]</span>,<br>
&nbsp;&nbsp;<span class="key">"objetivo"</span>:    <span class="str">"Construir soluções que importam — com elegância e propósito"</span><br>
<span class="brace">}</span>
  </div>
</div>
 
<!-- CAROUSEL -->
<div class="card carousel-section">
  <h2>🛠 Linguagens &amp; Frameworks</h2>
 
  <div class="carousel-label">Linguagens de programação</div>
  <div class="track-wrap">
    <div class="track" id="track-lang">
      <!-- duplicated for seamless loop, JS will handle -->
    </div>
  </div>
 
  <div class="carousel-label">Frontend &amp; Ferramentas</div>
  <div class="track-wrap">
    <div class="track" id="track-tools" style="animation-direction:reverse;animation-duration:26s">
    </div>
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
      <div class="stat-row"><span>Python</span><span class="vn">████ 40%</span></div>
      <div class="stat-row"><span>Java</span><span class="vn">███ 25%</span></div>
      <div class="stat-row"><span>JavaScript</span><span class="vn">██ 20%</span></div>
      <div class="stat-row"><span>C</span><span class="vn">█ 15%</span></div>
    </div>
  </div>
  <div class="streak-card">
    <div class="streak-item">
      <div class="streak-num" style="font-size:1.1rem;color:var(--muted2)">🔥</div>
      <div class="streak-num" id="sn1">0</div>
      <div class="streak-label">streak atual</div>
    </div>
    <div class="streak-item">
      <div class="streak-num" id="sn2">0</div>
      <div class="streak-label">maior streak</div>
    </div>
    <div class="streak-item">
      <div class="streak-num" id="sn3">0</div>
      <div class="streak-label">contribuições</div>
    </div>
  </div>
</div>
 
<!-- FOOTER QUOTE -->
<div class="quote-footer">
  <q>A melhor forma de prever o futuro é programá-lo.</q>
  <br>
  <span class="visitor-badge">👁 visitor count</span>
</div>
 
</div><!-- end wrapper -->
 
<!-- FIXED CONTACT BAR -->
<div class="contact-bar">
  <span class="contact-label">contato</span>
  <a class="contact-btn" href="#">
    <svg width="15" height="15" fill="#0A66C2" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
    LinkedIn
  </a>
  <div class="contact-divider"></div>
  <a class="contact-btn" href="#">
    <svg width="15" height="15" viewBox="0 0 24 24" fill="none">
      <path d="M2 6a2 2 0 012-2h16a2 2 0 012 2v12a2 2 0 01-2 2H4a2 2 0 01-2-2V6z" stroke="#EA4335" stroke-width="1.5"/>
      <path d="M2 6l10 7 10-7" stroke="#EA4335" stroke-width="1.5" stroke-linecap="round"/>
    </svg>
    Email
  </a>
</div>
 
<script>
/* ── TYPING ── */
const lines=["Engenharia da Computação @ UFPA","Apaixonado por desenvolvimento e IA","Sempre aprendendo, sempre construindo","Transformando lógica em soluções reais"];
let i=0,j=0,del=false;
const el=document.getElementById('typing');
function type(){
  const cur=lines[i];
  if(!del){el.textContent=cur.slice(0,j+1);j++;if(j===cur.length){del=true;setTimeout(type,1800);return}}
  else{el.textContent=cur.slice(0,j);j--;if(j<0){del=false;i=(i+1)%lines.length;setTimeout(type,400);return}}
  setTimeout(type,del?38:58);
}
type();
 
/* ── CAROUSEL DATA ── */
const langs = [
  { name:'Python',   color:'#3776AB', svg:`<svg viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M24.047 5c-1.555.005-3.04.138-4.34.38C16.007 6.04 15.359 7.57 15.359 10.19v3.43h9.369v1.14H11.85c-2.72 0-5.105 1.636-5.852 4.742-.856 3.566-.895 5.787 0 9.504.663 2.768 2.249 4.742 4.968 4.742H14.5v-4.262c0-3.095 2.677-5.826 5.852-5.826h9.364c2.602 0 4.681-2.145 4.681-4.762V10.19c0-2.542-2.143-4.45-4.681-4.81A29.23 29.23 0 0024.047 5zm-5.066 2.83c.967 0 1.755.799 1.755 1.786 0 .984-.788 1.779-1.755 1.779-.97 0-1.756-.795-1.756-1.779 0-.987.786-1.786 1.756-1.786z" fill="#3776AB"/><path d="M34.308 14.76v4.14c0 3.227-2.733 5.947-5.852 5.947H19.09c-2.563 0-4.681 2.19-4.681 4.762v8.928c0 2.542 2.21 4.034 4.681 4.762 2.963.871 5.808.028 9.364 0 2.472-.035 4.68-1.32 4.68-4.762v-3.43h-9.36v-1.14h14.04c2.72 0 3.733-1.895 4.682-4.742.978-2.928.937-5.745 0-9.504-.674-2.706-1.957-4.742-4.682-4.742h-3.507zm-5.258 22.89c.97 0 1.756.795 1.756 1.78 0 .987-.786 1.785-1.756 1.785-.967 0-1.755-.798-1.755-1.785 0-.985.788-1.78 1.755-1.78z" fill="#FFD43B"/></svg>` },
  { name:'Java',     color:'#ED8B00', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M20.184 36.836s-2.135 1.241 1.52 1.661c4.43.505 6.694.433 11.573-.488 0 0 1.282.804 3.072 1.5C27.31 43.656 9.958 39.28 20.184 36.836z" fill="#0074BD"/><path d="M18.795 30.229s-2.396 1.774 1.264 2.153c4.736.489 8.481.529 14.956-.718 0 0 .893.905 2.298 1.399-13.243 3.873-27.994.305-18.518-2.834z" fill="#0074BD"/><path d="M29.448 21.723c2.699 3.106-.71 5.9-.71 5.9s6.851-3.539 3.702-7.967c-2.942-4.13-5.199-6.185 7.012-13.26 0 0-19.165 4.787-10.004 15.327z" fill="#EA2D2E"/><path d="M42.74 40.23s1.58 1.301-1.739 2.308c-6.312 1.912-26.268 2.49-31.827.076-1.994-.866.742-2.067 1.629-2.232.903-.177 1.419-.144 1.419-.144-1.633-1.15-10.552 2.259-4.528 3.234C26.418 46.47 49.104 43.07 42.74 40.23z" fill="#0074BD"/><path d="M21.125 23.515s-7.473 1.775-2.647 2.42c2.039.273 6.096.211 9.882-.107 3.092-.262 6.198-.817 6.198-.817s-1.092.467-1.88.605c-7.587 1.997-22.237 1.068-18.026-.587 3.571-1.421 6.473-1.514 6.473-1.514z" fill="#0074BD"/><path d="M38.851 35.063c7.712-4.008 4.147-7.861 1.659-7.342-.609.127-.88.237-.88.237s.226-.354.657-.506c4.908-1.726 8.682 5.093-1.591 7.795 0-.001.12-.108.155-.184z" fill="#0074BD"/><path d="M32.015 4s4.273 4.275-4.054 10.848c-6.676 5.272-1.523 8.277-.002 11.706-3.896-3.516-6.754-6.61-4.839-9.49C25.945 12.717 34.087 10.612 32.015 4z" fill="#EA2D2E"/><path d="M22.694 48.031c7.403.474 18.77-.263 19.037-3.764 0 0-.517 1.327-6.12 2.38-6.325 1.19-14.124 1.05-18.751.288 0 0 .946.784 5.834 1.096z" fill="#0074BD"/></svg>` },
  { name:'Node.js',  color:'#339933', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M24 3.998L5 14.999v18.004L24 44 43 33.003V14.999L24 3.998z" fill="#21a366"/><path d="M24 3.998v40.003L43 33.003V14.999L24 3.998z" fill="#35b558"/><path d="M24 3.998L5 14.999 24 26l19-11.001L24 3.998z" fill="#3dca6a"/><path d="M24 26L5 14.999v18.004L24 44V26z" fill="#21a366"/><path fill="#fff" d="M21.002 32.987v-1.5l-1.499-.858-1.502.858v1.5l1.502.857 1.499-.857z"/><path fill="#fff" d="M24 16.499c-1.5 0-2.748.5-3.748 1.499-1 1-1.502 2.25-1.502 3.749s.501 2.748 1.502 3.748c1 1 2.248 1.502 3.748 1.502s2.748-.501 3.748-1.502c1-1 1.502-2.249 1.502-3.748s-.501-2.748-1.502-3.749C26.748 16.999 25.5 16.499 24 16.499zm0 8.998c-.75 0-1.374-.25-1.874-.75s-.75-1.124-.75-1.874.25-1.374.75-1.874.874-.75 1.874-.75c.75 0 1.374.25 1.874.75s.75 1.124.75 1.874-.25 1.374-.75 1.874-.874.75-1.874.75z"/></svg>` },
  { name:'C',        color:'#A8B9CC', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M24 4L6 14v20l18 10 18-10V14L24 4z" fill="#3949AB"/><path d="M33.5 28.5c-.8 2.1-2.3 3.8-4.1 4.9-1.8 1.1-4 1.6-6.4 1.6-3.5 0-6.3-1.1-8.4-3.3-2.1-2.2-3.1-5.1-3.1-8.7s1-6.5 3.1-8.7c2.1-2.2 4.9-3.3 8.4-3.3 2.4 0 4.5.5 6.3 1.6 1.8 1.1 3.2 2.6 4.2 4.7l-4.1 2.4c-.6-1.3-1.4-2.3-2.4-2.9-1-.7-2.4-1-4-1-2.1 0-3.8.7-5.1 2.1-1.3 1.4-1.9 3.4-1.9 6.1 0 2.7.6 4.7 1.9 6.1 1.3 1.4 3 2.1 5.1 2.1 1.5 0 2.8-.3 3.9-1 1.1-.7 2-1.7 2.7-3.1l3.9 2.3z" fill="#fff"/></svg>` },
  { name:'JavaScript',color:'#F7DF1E',svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path fill="#F7DF1E" d="M6 42V6h36v36z"/><path d="M29.538 32.947c.692 1.124 1.444 2.201 3.037 2.201 1.338 0 2.04-.665 2.04-1.585 0-1.101-.726-1.492-2.198-2.133l-.807-.344c-2.329-.988-3.878-2.226-3.878-4.841 0-2.41 1.845-4.244 4.728-4.244 2.053 0 3.528.711 4.592 2.573l-2.514 1.607c-.553-.988-1.151-1.377-2.078-1.377-.946 0-1.545.597-1.545 1.377 0 .964.6 1.354 1.985 1.951l.807.344C36.452 29.645 38 30.839 38 33.523 38 36.415 35.716 38 32.65 38c-2.999 0-4.702-1.505-5.65-3.368l2.538-1.685zm-10.001.857c.504.905 1.006 1.667 2.138 1.667 1.134 0 1.853-.444 1.853-2.173V22h3.166v11.297c0 3.578-2.097 5.203-5.151 5.203-2.764 0-4.553-1.492-5.429-3.276l3.423-1.42z"/></svg>` },
];
 
const tools = [
  { name:'React',    color:'#61DAFB', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><circle cx="24" cy="24" r="4.5" fill="#61DAFB"/><path d="M24 14.7c9.39 0 17 4.163 17 9.3s-7.61 9.3-17 9.3S7 29.137 7 24s7.61-9.3 17-9.3z" stroke="#61DAFB" stroke-width="1.5" fill="none"/><path d="M16.825 19.35C21.52 11.168 27.815 5.948 32.5 8.52c4.685 2.57 4.024 12.084-.67 20.267-4.695 8.183-10.99 13.403-15.675 10.83C11.47 37.047 12.13 27.533 16.825 19.35z" stroke="#61DAFB" stroke-width="1.5" fill="none"/><path d="M16.825 28.65C12.13 20.467 11.47 10.953 16.155 8.38c4.685-2.572 10.98 2.648 15.675 10.83 4.694 8.183 5.355 17.697.67 20.27-4.685 2.572-10.98-2.648-15.675-10.83z" stroke="#61DAFB" stroke-width="1.5" fill="none"/></svg>` },
  { name:'Next.js',  color:'#ffffff', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><circle cx="24" cy="24" r="20" fill="#000"/><path d="M16 32V16h13.5l-2 2H18v5h8l-2 2h-6v5h9.5l2 2H16z" fill="#fff"/><path d="M28 16l8 16h-2.5L28 23.5V16z" fill="#fff"/></svg>` },
  { name:'Tailwind', color:'#06B6D4', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M24 12c-5.333 0-8.667 2.667-10 8 2-2.667 4.333-3.667 7-3 1.518.38 2.604 1.482 3.806 2.699C26.658 21.56 28.727 24 33 24c5.333 0 8.667-2.667 10-8-2 2.667-4.333 3.667-7 3-1.518-.38-2.604-1.482-3.806-2.699C30.342 14.44 28.273 12 24 12zM14 24c-5.333 0-8.667 2.667-10 8 2-2.667 4.333-3.667 7-3 1.518.38 2.604 1.482 3.806 2.699C16.658 33.56 18.727 36 23 36c5.333 0 8.667-2.667 10-8-2 2.667-4.333 3.667-7 3-1.518-.38-2.604-1.482-3.806-2.699C20.342 26.44 18.273 24 14 24z" fill="#38BDF8"/></svg>` },
  { name:'HTML5',    color:'#E34F26', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M8 4l3.5 39L24 47l12.5-4L40 4H8z" fill="#E44D26"/><path d="M24 43.5l10.1-2.8 3-33.7H24v36.5z" fill="#F16529"/><path d="M24 20h5.4l.4-4H24v-4h10.2l-.1 1.4-1 11.6H24v-5z" fill="#fff"/><path d="M24 30.9v-4.1l-.1.1-4.6-1.2-.3-3.4H15l.6 6.7 8.4 2.4.1-.5z" fill="#EBEBEB"/><path d="M24 20v4h-4.8l-.4-4H24zm0-8h-9.8l.4 4H24v-4z" fill="#EBEBEB"/><path d="M24 30.9l-.1.5-4.6-1.3-.3-3.2h-4l.6 6.7 8.4 2.4v-5.1z" fill="#EBEBEB"/><path d="M24 34.3v4.4l-8.3-2.3-1.1-12.5h4l.6 6.7 4.8 1.3v2.4z" fill="#EBEBEB"/><path d="M24 34.3l4.5-1.3.6-6.7h4l-1.1 12.5L24 41.2v-6.9z" fill="#fff"/><path d="M24 20h5.4l-.4 4H24v-4zm0-8h9.8l-.4 4H24v-4z" fill="#fff"/></svg>` },
  { name:'CSS3',     color:'#1572B6', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M8 4l3.5 39L24 47l12.5-4L40 4H8z" fill="#1572B6"/><path d="M24 43.5l10.1-2.8 3-33.7H24v36.5z" fill="#33A9DC"/><path d="M24 20h5.4l.4-4H24v-4h10.2l-.1 1.4-.5 6H24v-3.4z" fill="#fff"/><path d="M24 20v-3.4H13.9l.3 3.4H24z" fill="#EBEBEB"/><path d="M24 27.8h4.7l-.4 4.6L24 33.5v4.4l8.3-2.3 1.1-12.5H24v4.7z" fill="#fff"/><path d="M19.7 27.8l.5 4.6 3.8 1.1v4.4l-8.3-2.3-1.1-12.5H24v4.7h-4.3z" fill="#EBEBEB"/></svg>` },
  { name:'Git',      color:'#F05032', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M44.57 21.61L26.39 3.43a2.65 2.65 0 00-3.75 0l-3.72 3.72 4.74 4.74a3.14 3.14 0 013.97 4L31.9 20.1a3.14 3.14 0 11-1.88 1.88l-4.15-4.16v10.94a3.14 3.14 0 11-2.58-.08V17.63a3.14 3.14 0 01-1.66-4.12L17 8.79 3.43 22.36a2.65 2.65 0 000 3.75l18.18 18.18a2.65 2.65 0 003.75 0l19.21-19.21a2.65 2.65 0 000-3.47z" fill="#F05032"/></svg>` },
  { name:'VS Code',  color:'#007ACC', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M34 5L19 21.5l-7-5.5-5 2.5v13l5 2.5 7-5.5L34 45l8-3.5V8.5L34 5z" fill="#007ACC"/><path d="M42 8.5L34 5 19.5 20.5 12 15l-5 2.5v13l5 2.5 7.5-5.5L34 45l8-3.5V8.5z" fill="#1F9CF0"/><path opacity=".25" d="M34 5L12 27l-5 3v3l5 2.5L34 45l8-3.5v-7L22.5 24 42 11.5V8.5L34 5z" fill="#000"/></svg>` },
  { name:'Linux',    color:'#FCC624', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M24 4C13 4 9 17.5 9 22c0 5 2 9.5 4 12.5C15 37.5 15.5 43 17 43.5c2.5.8 5.5-1 7-1s4.5 1.8 7 1c1.5-.5 2-6 4-8.5 2-2.5 4-7.5 4-12.5 0-5.5-4-18.5-15-18.5z" fill="#FCC624"/><path d="M16.5 23.5c-.8 0-1.5-.7-1.5-1.5v-4c0-.8.7-1.5 1.5-1.5S18 17.2 18 18v4c0 .8-.7 1.5-1.5 1.5zm15 0c-.8 0-1.5-.7-1.5-1.5v-4c0-.8.7-1.5 1.5-1.5S33 17.2 33 18v4c0 .8-.7 1.5-1.5 1.5z" fill="#3E2723"/><path d="M19 30h10s-1 4-5 4-5-4-5-4z" fill="#fff"/></svg>` },
  { name:'Figma',    color:'#F24E1E', svg:`<svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg"><path d="M16 44c4.4 0 8-3.6 8-8v-8h-8c-4.4 0-8 3.6-8 8s3.6 8 8 8z" fill="#0ACF83"/><path d="M8 24c0-4.4 3.6-8 8-8h8v16h-8c-4.4 0-8-3.6-8-8z" fill="#A259FF"/><path d="M8 12c0-4.4 3.6-8 8-8h8v16h-8c-4.4 0-8-3.6-8-8z" fill="#F24E1E"/><path d="M24 4h8c4.4 0 8 3.6 8 8s-3.6 8-8 8h-8V4z" fill="#FF7262"/><path d="M40 24c0 4.4-3.6 8-8 8s-8-3.6-8-8 3.6-8 8-8 8 3.6 8 8z" fill="#1ABCFE"/></svg>` },
];
 
function buildTrack(trackId, items) {
  const track = document.getElementById(trackId);
  // duplicate for seamless loop
  const doubled = [...items, ...items];
  track.innerHTML = doubled.map(t => `
    <div class="tech-card">
      <div class="tech-icon">${t.svg}</div>
      <span class="tech-name">${t.name}</span>
    </div>
  `).join('');
}
 
buildTrack('track-lang', langs);
buildTrack('track-tools', tools);
 
/* ── COUNTERS ── */
function animCount(id,target,dur){
  const el=document.getElementById(id);
  let s=0,step=target/(dur/16);
  const t=setInterval(()=>{s+=step;if(s>=target){el.textContent=target;clearInterval(t);return}el.textContent=Math.floor(s)},16);
}
setTimeout(()=>{animCount('sn1',12,900);animCount('sn2',30,1100);animCount('sn3',247,1400)},600);
</script>
</body>
</html>

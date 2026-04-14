
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Quicksand:wght@400;500;600;700&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body, .root {
    font-family: 'Quicksand', sans-serif;
    background: #0d0d1a;
    color: #e8e0ff;
    min-height: 100vh;
  }

  .wrap {
    max-width: 860px;
    margin: 0 auto;
    padding: 0 1.5rem 4rem;
  }

  /* ── HEADER ── */
  .hero {
    position: relative;
    text-align: center;
    padding: 3.5rem 1rem 2rem;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background: linear-gradient(135deg, #1a0a2e 0%, #0d0d1a 40%, #0a1a2e 100%);
    z-index: 0;
  }
  .stars {
    position: absolute; inset: 0; z-index: 1;
    overflow: hidden;
  }
  .star {
    position: absolute;
    border-radius: 50%;
    background: white;
    animation: twinkle 3s infinite alternate;
  }
  @keyframes twinkle { from { opacity: 0.2; } to { opacity: 1; } }

  .hero-content { position: relative; z-index: 2; }

  .avatar-ring {
    width: 110px; height: 110px;
    border-radius: 50%;
    background: linear-gradient(135deg, #FF6B9D, #C44DFF, #4D9FFF, #00D4AA);
    padding: 3px;
    margin: 0 auto 1.2rem;
    animation: spin-slow 8s linear infinite;
  }
  @keyframes spin-slow { to { filter: hue-rotate(360deg); } }

  .avatar-inner {
    width: 100%; height: 100%;
    border-radius: 50%;
    background: #0d0d1a;
    display: flex; align-items: center; justify-content: center;
    font-size: 2.8rem;
  }

  .hero h1 {
    font-size: 2.4rem;
    font-weight: 700;
    background: linear-gradient(90deg, #FF6B9D, #C44DFF, #4D9FFF, #00D4AA);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 0.4rem;
  }

  .hero .tagline {
    font-family: 'Space Mono', monospace;
    font-size: 0.85rem;
    color: #8877bb;
    letter-spacing: 0.1em;
    margin-bottom: 1.5rem;
  }

  .badge-row {
    display: flex; flex-wrap: wrap; justify-content: center; gap: 8px;
    margin-bottom: 1.5rem;
  }
  .badge {
    padding: 5px 14px;
    border-radius: 100px;
    font-size: 0.75rem;
    font-weight: 600;
    font-family: 'Space Mono', monospace;
  }
  .badge-pink   { background: #2d0e1e; color: #FF6B9D; border: 1px solid #FF6B9D44; }
  .badge-purple { background: #1a0d2e; color: #C44DFF; border: 1px solid #C44DFF44; }
  .badge-blue   { background: #0a1628; color: #4D9FFF; border: 1px solid #4D9FFF44; }
  .badge-teal   { background: #041a14; color: #00D4AA; border: 1px solid #00D4AA44; }
  .badge-gold   { background: #1c1200; color: #FFD93D; border: 1px solid #FFD93D44; }

  /* ── SECTION HEADERS ── */
  .sec-head {
    display: flex; align-items: center; gap: 12px;
    margin: 2.5rem 0 1.2rem;
  }
  .sec-head-line { flex: 1; height: 1px; background: linear-gradient(90deg, #C44DFF33, transparent); }
  .sec-head-line.r { background: linear-gradient(270deg, #C44DFF33, transparent); }
  .sec-head h2 {
    font-size: 1rem;
    font-weight: 700;
    font-family: 'Space Mono', monospace;
    color: #C44DFF;
    letter-spacing: 0.08em;
    white-space: nowrap;
  }

  /* ── ABOUT ME ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }
  @media (max-width: 560px) { .about-grid { grid-template-columns: 1fr; } }

  .about-card {
    background: #13102a;
    border: 1px solid #2a2050;
    border-radius: 16px;
    padding: 1rem 1.2rem;
    transition: border-color 0.25s, transform 0.25s;
    cursor: default;
  }
  .about-card:hover { border-color: #C44DFF88; transform: translateY(-2px); }

  .about-card .card-icon {
    font-size: 1.4rem;
    margin-bottom: 0.5rem;
  }
  .about-card .card-title {
    font-size: 0.7rem;
    font-family: 'Space Mono', monospace;
    color: #6655aa;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 0.3rem;
  }
  .about-card .card-text {
    font-size: 0.9rem;
    color: #c8bfee;
    line-height: 1.5;
  }
  .about-card.wide { grid-column: 1 / -1; }
  .about-card .highlight { color: #FF6B9D; font-weight: 700; }
  .about-card .highlight2 { color: #00D4AA; font-weight: 700; }
  .about-card .highlight3 { color: #FFD93D; font-weight: 700; }

  .terminal-line {
    font-family: 'Space Mono', monospace;
    font-size: 0.78rem;
    color: #8877bb;
    margin-top: 0.6rem;
    padding: 6px 10px;
    background: #0a0818;
    border-radius: 8px;
    border-left: 2px solid #C44DFF;
  }
  .terminal-line .prompt { color: #FF6B9D; }
  .terminal-line .cmd { color: #00D4AA; }
  .terminal-line .out { color: #FFD93D; }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
    margin-bottom: 14px;
  }
  @media (max-width: 560px) { .stats-row { grid-template-columns: repeat(2, 1fr); } }

  .stat-orb {
    background: #13102a;
    border: 1px solid #2a2050;
    border-radius: 16px;
    padding: 1rem 0.8rem;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: border-color 0.25s;
  }
  .stat-orb:hover { border-color: #FF6B9D88; }
  .stat-orb::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse at 50% 0%, #FF6B9D08 0%, transparent 70%);
  }
  .stat-orb .num {
    font-size: 1.8rem;
    font-weight: 700;
    font-family: 'Space Mono', monospace;
    background: linear-gradient(135deg, #FF6B9D, #C44DFF);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .stat-orb .lbl {
    font-size: 0.68rem;
    font-family: 'Space Mono', monospace;
    color: #6655aa;
    letter-spacing: 0.05em;
    margin-top: 2px;
  }

  /* skill bars */
  .skill-bars { display: flex; flex-direction: column; gap: 10px; }
  .skill-row { display: flex; align-items: center; gap: 12px; }
  .skill-name {
    font-family: 'Space Mono', monospace;
    font-size: 0.72rem;
    color: #8877bb;
    width: 80px;
    flex-shrink: 0;
  }
  .skill-bar-bg {
    flex: 1;
    height: 6px;
    background: #1e1840;
    border-radius: 100px;
    overflow: hidden;
  }
  .skill-bar-fill {
    height: 100%;
    border-radius: 100px;
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 1s cubic-bezier(.16,1,.3,1);
  }
  .skill-pct {
    font-family: 'Space Mono', monospace;
    font-size: 0.68rem;
    color: #6655aa;
    width: 32px;
    text-align: right;
  }

  /* ── MINI GAME ── */
  .game-wrap {
    background: #0a0818;
    border: 1px solid #2a2050;
    border-radius: 20px;
    padding: 1.2rem;
    position: relative;
  }
  .game-header {
    display: flex; justify-content: space-between; align-items: center;
    margin-bottom: 0.8rem;
    font-family: 'Space Mono', monospace;
    font-size: 0.75rem;
  }
  .game-title { color: #C44DFF; font-weight: 700; }
  .game-score { color: #FFD93D; }
  .game-meta { display: flex; gap: 16px; color: #6655aa; font-size: 0.68rem; }

  #gameCanvas {
    width: 100%;
    border-radius: 12px;
    display: block;
    cursor: pointer;
    image-rendering: pixelated;
  }

  .game-instructions {
    font-family: 'Space Mono', monospace;
    font-size: 0.68rem;
    color: #6655aa;
    text-align: center;
    margin-top: 0.6rem;
    letter-spacing: 0.05em;
  }

  /* ── TECH STACK ── */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .tech-pill {
    display: flex; align-items: center; gap: 6px;
    padding: 6px 14px;
    background: #13102a;
    border: 1px solid #2a2050;
    border-radius: 100px;
    font-size: 0.78rem;
    font-weight: 600;
    color: #c8bfee;
    transition: all 0.2s;
    cursor: default;
  }
  .tech-pill:hover { border-color: #C44DFF88; color: #fff; transform: translateY(-2px); }
  .tech-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 2.5rem 1rem 0;
    font-family: 'Space Mono', monospace;
    font-size: 0.72rem;
    color: #3d3365;
  }
  .views-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: #13102a;
    border: 1px solid #2a2050;
    border-radius: 100px;
    padding: 8px 20px;
    margin-top: 1rem;
  }
  .views-dot { width: 8px; height: 8px; border-radius: 50%; background: #FF6B9D; animation: pulse 1.5s infinite; }
  @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.4;transform:scale(0.7)} }
  .views-num { font-size: 1rem; font-weight: 700; color: #FF6B9D; }
</style>

<div class="wrap">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-bg"></div>
    <div class="stars" id="stars"></div>
    <div class="hero-content">
      <div class="avatar-ring">
        <div class="avatar-inner">🌸</div>
      </div>
      <h1>Hazel Ann Sadangsal</h1>
      <p class="tagline">// frontend_developer · student · PH 🇵🇭</p>
      <div class="badge-row">
        <span class="badge badge-pink">React</span>
        <span class="badge badge-purple">TypeScript</span>
        <span class="badge badge-blue">Next.js</span>
        <span class="badge badge-teal">Supabase</span>
        <span class="badge badge-gold">Figma</span>
      </div>
    </div>
  </div>

  <!-- ABOUT ME -->
  <div class="sec-head">
    <div class="sec-head-line"></div>
    <h2>✦ about.me()</h2>
    <div class="sec-head-line r"></div>
  </div>

  <div class="about-grid">
    <div class="about-card">
      <div class="card-icon">🎓</div>
      <div class="card-title">origin story</div>
      <div class="card-text">Student dev from the <span class="highlight">Philippines</span> who discovered that turning blank screens into living, breathing interfaces is basically magic — and never looked back.</div>
    </div>
    <div class="about-card">
      <div class="card-icon">🎨</div>
      <div class="card-title">obsession</div>
      <div class="card-text">I don't just build UIs — I <span class="highlight2">craft experiences</span>. Every pixel, every transition, every hover state is a tiny decision I genuinely care about.</div>
    </div>
    <div class="about-card wide">
      <div class="card-icon">⚡</div>
      <div class="card-title">current arc</div>
      <div class="card-text">Deep in the trenches with <span class="highlight3">TypeScript + React + Supabase</span>, building real systems that solve real problems. Dashboards, auth flows, real-time updates — if it's complex, I'm interested.</div>
      <div class="terminal-line">
        <span class="prompt">hazel@dev</span>:<span class="cmd">~</span>$ <span class="out">npm run build-something-amazing</span>
      </div>
    </div>
    <div class="about-card">
      <div class="card-icon">🌙</div>
      <div class="card-title">at 2am</div>
      <div class="card-text">Debugging a CSS animation that's <span class="highlight">3px off</span> — and refusing to sleep until it's perfect.</div>
    </div>
    <div class="about-card">
      <div class="card-icon">🚀</div>
      <div class="card-title">life goal</div>
      <div class="card-text">Ship apps that make people say <span class="highlight2">"wait, a student made this?"</span> — then nod quietly and keep shipping.</div>
    </div>
  </div>

  <!-- STATS -->
  <div class="sec-head">
    <div class="sec-head-line"></div>
    <h2>✦ stats.json</h2>
    <div class="sec-head-line r"></div>
  </div>

  <div class="stats-row">
    <div class="stat-orb"><div class="num" id="s1">0</div><div class="lbl">repos</div></div>
    <div class="stat-orb"><div class="num" id="s2">0</div><div class="lbl">commits</div></div>
    <div class="stat-orb"><div class="num" id="s3">0</div><div class="lbl">stars earned</div></div>
    <div class="stat-orb"><div class="num" id="s4">0</div><div class="lbl">streak days</div></div>
  </div>

  <!-- SKILL BARS -->
  <div class="skill-bars" id="skillBars">
    <div class="skill-row">
      <div class="skill-name">JavaScript</div>
      <div class="skill-bar-bg"><div class="skill-bar-fill" data-pct="88" style="background:linear-gradient(90deg,#F7DF1E,#FFD93D)"></div></div>
      <div class="skill-pct">88%</div>
    </div>
    <div class="skill-row">
      <div class="skill-name">TypeScript</div>
      <div class="skill-bar-bg"><div class="skill-bar-fill" data-pct="75" style="background:linear-gradient(90deg,#4D9FFF,#007ACC)"></div></div>
      <div class="skill-pct">75%</div>
    </div>
    <div class="skill-row">
      <div class="skill-name">React</div>
      <div class="skill-bar-bg"><div class="skill-bar-fill" data-pct="85" style="background:linear-gradient(90deg,#61DAFB,#4D9FFF)"></div></div>
      <div class="skill-pct">85%</div>
    </div>
    <div class="skill-row">
      <div class="skill-name">CSS / UI</div>
      <div class="skill-bar-bg"><div class="skill-bar-fill" data-pct="92" style="background:linear-gradient(90deg,#FF6B9D,#C44DFF)"></div></div>
      <div class="skill-pct">92%</div>
    </div>
    <div class="skill-row">
      <div class="skill-name">Python</div>
      <div class="skill-bar-bg"><div class="skill-bar-fill" data-pct="65" style="background:linear-gradient(90deg,#00D4AA,#4D9FFF)"></div></div>
      <div class="skill-pct">65%</div>
    </div>
  </div>

  <!-- MINI GAME -->
  <div class="sec-head">
    <div class="sec-head-line"></div>
    <h2>✦ contribution_quest.exe</h2>
    <div class="sec-head-line r"></div>
  </div>

  <div class="game-wrap">
    <div class="game-header">
      <span class="game-title">◆ COMMIT CATCHER</span>
      <div class="game-meta">
        <span>SCORE: <span class="game-score" id="scoreDisplay">0</span></span>
        <span>LEVEL: <span class="game-score" id="levelDisplay">1</span></span>
        <span>LIVES: <span class="game-score" id="livesDisplay">♥♥♥</span></span>
      </div>
    </div>
    <canvas id="gameCanvas" width="800" height="280"></canvas>
    <div class="game-instructions" id="gameInstr">[ CLICK or TAP canvas to start — catch the commits! ]</div>
  </div>

  <!-- TECH STACK -->
  <div class="sec-head">
    <div class="sec-head-line"></div>
    <h2>✦ tech_stack[]</h2>
    <div class="sec-head-line r"></div>
  </div>

  <div class="tech-grid">
    <span class="tech-pill"><span class="tech-dot" style="background:#E34F26"></span>HTML5</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#1572B6"></span>CSS3</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#F7DF1E"></span>JavaScript</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#007ACC"></span>TypeScript</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#3670A0"></span>Python</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#ED8B00"></span>Java</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#239120"></span>C#</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#61DAFB"></span>React</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#fff"></span>Next.js</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#6DA55F"></span>Node.js</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#38B2AC"></span>TailwindCSS</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#FFCA28"></span>Firebase</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#3ECF8E"></span>Supabase</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#000"></span>Vercel</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#4479A1"></span>MySQL</span>
    <span class="tech-pill"><span class="tech-dot" style="background:#F24E1E"></span>Figma</span>
  </div>

  <!-- SOCIALS -->
  <div class="sec-head">
    <div class="sec-head-line"></div>
    <h2>✦ connect()</h2>
    <div class="sec-head-line r"></div>
  </div>

  <div style="display:flex;flex-wrap:wrap;gap:10px;justify-content:center">
    <a href="https://linkedin.com/in/Hazel%20Ann%20Sadangsal" style="text-decoration:none">
      <div class="tech-pill" style="font-size:0.8rem;padding:10px 20px">
        <span style="color:#0077B5;font-size:1rem">in</span> LinkedIn
      </div>
    </a>
    <a href="mailto:hazelann.dg.sadangsal@gmail.com" style="text-decoration:none">
      <div class="tech-pill" style="font-size:0.8rem;padding:10px 20px">
        <span style="color:#D14836;font-size:1rem">✉</span> Gmail
      </div>
    </a>
    <a href="https://github.com/aziel123-de" style="text-decoration:none">
      <div class="tech-pill" style="font-size:0.8rem;padding:10px 20px">
        <span style="color:#fff;font-size:1rem">⌥</span> GitHub
      </div>
    </a>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="views-badge">
      <div class="views-dot"></div>
      <span>profile views</span>
      <span class="views-num" id="viewCount">—</span>
    </div>
    <div style="margin-top:1.5rem;color:#2a2050">
      made with ♥ by hazel · aziel123-de
    </div>
  </div>

</div>

<script>
// ── STARS ──
(function(){
  const c = document.getElementById('stars');
  for(let i=0;i<60;i++){
    const s = document.createElement('div');
    s.className='star';
    const sz = Math.random()*2+0.5;
    s.style.cssText=`width:${sz}px;height:${sz}px;top:${Math.random()*100}%;left:${Math.random()*100}%;animation-delay:${Math.random()*3}s;animation-duration:${2+Math.random()*3}s`;
    c.appendChild(s);
  }
})();

// ── COUNTER ANIM ──
function countUp(el, target, dur=1200){
  let start=0, step=target/60;
  const t=setInterval(()=>{
    start+=step;
    if(start>=target){start=target;clearInterval(t);}
    el.textContent = start>=1000 ? Math.round(start/100)/10+'k' : Math.round(start);
  }, dur/60);
}
setTimeout(()=>{
  countUp(document.getElementById('s1'), 24);
  countUp(document.getElementById('s2'), 847);
  countUp(document.getElementById('s3'), 63);
  countUp(document.getElementById('s4'), 42);
  countUp(document.getElementById('viewCount'), 1247);
}, 300);

// ── SKILL BARS ──
setTimeout(()=>{
  document.querySelectorAll('.skill-bar-fill').forEach(b=>{
    b.style.transform = `scaleX(${b.dataset.pct/100})`;
  });
}, 500);

// ── MINI GAME ──
(function(){
  const canvas = document.getElementById('gameCanvas');
  const ctx = canvas.getContext('2d');
  const W = canvas.width, H = canvas.height;
  let state='idle', score=0, level=1, lives=3, frame=0, raf;
  let player = { x:W/2, y:H-40, w:60, h:16, vx:0 };
  let commits=[], particles=[], bugs=[];
  let keys={};

  const EMOJIS = ['💾','⚡','🔥','⭐','🎯'];
  const BUG_EMOJIS = ['🐛','💀','❌'];

  function spawnCommit(){
    commits.push({
      x: 40+Math.random()*(W-80),
      y: -20,
      vy: 1.5 + level*0.4,
      emoji: EMOJIS[Math.floor(Math.random()*EMOJIS.length)],
      sz: 20
    });
  }

  function spawnBug(){
    bugs.push({
      x: Math.random()*(W-40)+20,
      y: -20,
      vy: 1.8 + level*0.5,
      vx: (Math.random()-0.5)*1.5,
      emoji: BUG_EMOJIS[Math.floor(Math.random()*BUG_EMOJIS.length)]
    });
  }

  function spawnParticle(x,y,color){
    for(let i=0;i<8;i++){
      const a=Math.random()*Math.PI*2;
      const sp=2+Math.random()*3;
      particles.push({x,y,vx:Math.cos(a)*sp,vy:Math.sin(a)*sp,life:1,color,r:3+Math.random()*3});
    }
  }

  function drawPlayer(){
    const {x,y,w,h}=player;
    const grd = ctx.createLinearGradient(x-w/2,y,x+w/2,y+h);
    grd.addColorStop(0,'#FF6B9D');
    grd.addColorStop(1,'#C44DFF');
    ctx.fillStyle=grd;
    ctx.beginPath();
    ctx.roundRect(x-w/2, y, w, h, 8);
    ctx.fill();
    ctx.fillStyle='rgba(255,255,255,0.25)';
    ctx.beginPath();
    ctx.roundRect(x-w/2+4, y+2, w-8, 4, 3);
    ctx.fill();
  }

  function drawHUD(){
    ctx.fillStyle='#1a0a2e';
    ctx.fillRect(0,0,W,40);
    ctx.strokeStyle='#2a1040';
    ctx.lineWidth=1;
    ctx.beginPath(); ctx.moveTo(0,40); ctx.lineTo(W,40); ctx.stroke();

    ctx.font='bold 13px Space Mono,monospace';
    ctx.fillStyle='#C44DFF'; ctx.fillText('◆ COMMIT CATCHER', 12, 26);
    ctx.fillStyle='#FFD93D'; ctx.fillText('SCORE: '+score, W-240, 26);
    ctx.fillStyle='#FF6B9D';
    const hearts = '♥'.repeat(lives) + '♡'.repeat(Math.max(0,3-lives));
    ctx.fillText(hearts, W-100, 26);
  }

  function drawBg(){
    ctx.fillStyle='#080613';
    ctx.fillRect(0,40,W,H-40);
    ctx.fillStyle='rgba(255,255,255,0.025)';
    for(let y=50;y<H;y+=40) { ctx.fillRect(0,y,W,1); }
    for(let x=0;x<W;x+=80) { ctx.fillRect(x,40,1,H-40); }
  }

  function loop(){
    ctx.clearRect(0,0,W,H);
    drawBg();

    // player move
    if(state==='playing'){
      if(keys['ArrowLeft']||keys['a']) player.vx -= 1.5;
      if(keys['ArrowRight']||keys['d']) player.vx += 1.5;
      player.vx *= 0.82;
      player.x = Math.max(player.w/2, Math.min(W-player.w/2, player.x+player.vx));

      // spawn
      if(frame%Math.max(30,60-level*5)===0) spawnCommit();
      if(level>=2 && frame%90===0) spawnBug();
      if(frame%(300-level*20)===0) level = Math.min(8,level+1);
      frame++;

      // commits
      commits = commits.filter(c=>{
        c.y += c.vy;
        ctx.font = c.sz+'px serif';
        ctx.fillText(c.emoji, c.x-c.sz/2, c.y);
        if(c.y > player.y && c.y < player.y+player.h &&
           Math.abs(c.x-player.x) < player.w/2+c.sz/2){
          score+=10; spawnParticle(c.x,c.y,'#FFD93D');
          document.getElementById('scoreDisplay').textContent=score;
          document.getElementById('levelDisplay').textContent=level;
          return false;
        }
        if(c.y > H){ spawnParticle(c.x,H,'#FF6B9D30'); return false; }
        return true;
      });

      // bugs
      bugs = bugs.filter(b=>{
        b.y += b.vy; b.x += b.vx;
        if(b.x<10||b.x>W-10) b.vx*=-1;
        ctx.font='16px serif'; ctx.fillText(b.emoji, b.x-8, b.y);
        if(b.y > player.y && b.y < player.y+player.h &&
           Math.abs(b.x-player.x) < player.w/2+12){
          lives = Math.max(0, lives-1);
          spawnParticle(b.x,b.y,'#FF3333');
          const h='♥'.repeat(lives)+'♡'.repeat(3-lives);
          document.getElementById('livesDisplay').textContent=h;
          if(lives<=0) endGame();
          return false;
        }
        if(b.y>H) return false;
        return true;
      });
    }

    // particles
    particles = particles.filter(p=>{
      p.x+=p.vx; p.y+=p.vy; p.life-=0.035; p.r*=0.97;
      ctx.globalAlpha=p.life;
      ctx.fillStyle=p.color;
      ctx.beginPath(); ctx.arc(p.x,p.y,p.r,0,Math.PI*2); ctx.fill();
      ctx.globalAlpha=1;
      return p.life>0;
    });

    drawHUD();
    drawPlayer();

    if(state==='idle'){
      ctx.fillStyle='rgba(10,8,24,0.75)';
      ctx.fillRect(0,40,W,H-40);
      ctx.fillStyle='#C44DFF';
      ctx.font='bold 22px Space Mono,monospace';
      ctx.textAlign='center';
      ctx.fillText('COMMIT CATCHER', W/2, H/2-30);
      ctx.fillStyle='#8877bb';
      ctx.font='13px Space Mono,monospace';
      ctx.fillText('← → or A D to move · catch commits · dodge bugs', W/2, H/2+5);
      ctx.fillStyle='#FFD93D';
      ctx.fillText('[ CLICK TO START ]', W/2, H/2+35);
      ctx.textAlign='left';
    }

    if(state==='over'){
      ctx.fillStyle='rgba(10,8,24,0.85)';
      ctx.fillRect(0,40,W,H-40);
      ctx.fillStyle='#FF6B9D';
      ctx.font='bold 24px Space Mono,monospace';
      ctx.textAlign='center';
      ctx.fillText('GAME OVER', W/2, H/2-30);
      ctx.fillStyle='#FFD93D';
      ctx.font='16px Space Mono,monospace';
      ctx.fillText('FINAL SCORE: '+score, W/2, H/2+5);
      ctx.fillStyle='#8877bb';
      ctx.font='12px Space Mono,monospace';
      ctx.fillText('[ CLICK TO RESTART ]', W/2, H/2+35);
      ctx.textAlign='left';
    }

    raf=requestAnimationFrame(loop);
  }

  function startGame(){
    state='playing'; score=0; level=1; lives=3; frame=0;
    commits=[]; bugs=[]; particles=[];
    player.x=W/2; player.vx=0;
    document.getElementById('scoreDisplay').textContent=0;
    document.getElementById('levelDisplay').textContent=1;
    document.getElementById('livesDisplay').textContent='♥♥♥';
    document.getElementById('gameInstr').textContent='← → / A D to move  ·  catch commits 💾  ·  dodge bugs 🐛';
  }
  function endGame(){ state='over'; }

  canvas.addEventListener('click', ()=>{ if(state==='idle'||state==='over') startGame(); });
  canvas.addEventListener('touchstart',e=>{ e.preventDefault(); if(state==='idle'||state==='over') startGame(); },{passive:false});

  let touchX=null;
  canvas.addEventListener('touchmove',e=>{ e.preventDefault(); const t=e.touches[0]; if(touchX!==null){ const dx=t.clientX-touchX; player.vx+=dx*0.4; } touchX=t.clientX; },{passive:false});
  canvas.addEventListener('touchend',()=>{ touchX=null; });

  document.addEventListener('keydown',e=>keys[e.key]=true);
  document.addEventListener('keyup',e=>keys[e.key]=false);

  loop();
})();
</script>

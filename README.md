<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>GitHub Profile — Maya Reyes</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=Space+Mono:wght@400;700&family=Inter:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{
  font-family:'Inter',sans-serif;
  background:#06060f;
  color:#e2e8f0;
  min-height:100vh;
}

/* ── BACKGROUND EFFECTS ── */
.aurora{
  position:fixed;inset:0;z-index:0;pointer-events:none;
  background:
    radial-gradient(ellipse 80% 40% at 10% 0%,rgba(139,92,246,0.12) 0%,transparent 60%),
    radial-gradient(ellipse 60% 50% at 90% 10%,rgba(236,72,153,0.08) 0%,transparent 60%),
    radial-gradient(ellipse 50% 30% at 50% 100%,rgba(6,182,212,0.07) 0%,transparent 50%);
}
.scanlines{
  position:fixed;inset:0;z-index:0;pointer-events:none;
  background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.025) 2px,rgba(0,0,0,0.025) 4px);
}

/* ── LAYOUT ── */
.page{
  position:relative;z-index:1;
  max-width:1000px;margin:0 auto;
  padding:2rem 1.5rem;
}

/* ── TOP NAV ── */
.topbar{
  display:flex;align-items:center;justify-content:space-between;
  padding-bottom:1.75rem;margin-bottom:2rem;
  border-bottom:1px solid rgba(255,255,255,0.05);
}
.topbar-brand{font-family:'Space Mono',monospace;font-size:11px;letter-spacing:0.2em;color:rgba(255,255,255,0.2);}
.topbar-btns{display:flex;gap:8px;}
.tbtn{
  padding:6px 16px;border-radius:100px;font-size:11px;font-family:'Space Mono',monospace;
  cursor:pointer;border:1px solid rgba(255,255,255,0.1);background:rgba(255,255,255,0.04);
  color:rgba(255,255,255,0.5);transition:all 0.2s;
}
.tbtn:hover{border-color:rgba(139,92,246,0.5);color:#c4b5fd;}
.tbtn.hi{background:linear-gradient(135deg,#7c3aed,#db2777);border-color:transparent;color:#fff;}
.tbtn.hi:hover{opacity:0.85;}

/* ── HERO ── */
.hero{
  display:grid;
  grid-template-columns:1fr 300px;
  gap:2.5rem;margin-bottom:2.5rem;align-items:start;
}
@media(max-width:700px){
  .hero{grid-template-columns:1fr;}
  .avatar-col{order:-1;}
}

.hero-name{
  font-family:'Syne',sans-serif;font-size:52px;font-weight:800;
  line-height:0.95;letter-spacing:-2px;color:#fff;margin-bottom:0.5rem;
}
.name-accent{
  display:block;
  background:linear-gradient(90deg,#a78bfa,#f472b6,#fb923c);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.hero-role{
  font-family:'Space Mono',monospace;font-size:12px;letter-spacing:0.15em;
  color:rgba(167,139,250,0.6);margin-bottom:1.25rem;
  display:flex;align-items:center;gap:10px;
}
.role-dot{
  width:6px;height:6px;border-radius:50%;background:#10b981;
  box-shadow:0 0 6px #10b981;animation:blink 2s infinite;
}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:0.3;}}

.hero-bio{
  font-size:14px;color:rgba(255,255,255,0.45);line-height:1.75;
  max-width:460px;margin-bottom:1.5rem;
}
.bio-em{color:rgba(167,139,250,0.8);font-weight:500;}

.meta-pills{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:1.75rem;}
.mpill{
  display:flex;align-items:center;gap:6px;
  padding:5px 13px;border-radius:100px;
  background:rgba(255,255,255,0.03);border:1px solid rgba(255,255,255,0.07);
  font-size:11px;font-family:'Space Mono',monospace;color:rgba(255,255,255,0.35);
  cursor:pointer;transition:all 0.2s;text-decoration:none;
}
.mpill:hover{border-color:rgba(167,139,250,0.4);color:#c4b5fd;}
.mpill svg{flex-shrink:0;}

.stat-strip{display:flex;gap:0;}
.sstat{
  padding:1rem 1.5rem;
  border:1px solid rgba(255,255,255,0.05);
  border-right:none;
}
.sstat:first-child{border-radius:12px 0 0 12px;}
.sstat:last-child{border-radius:0 12px 12px 0;border-right:1px solid rgba(255,255,255,0.05);}
.sstat-num{
  font-family:'Syne',sans-serif;font-size:28px;font-weight:800;
  background:linear-gradient(135deg,#c4b5fd,#f9a8d4);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.sstat-lbl{
  font-size:10px;color:rgba(255,255,255,0.25);
  font-family:'Space Mono',monospace;letter-spacing:0.08em;margin-top:2px;
}

/* ── AVATAR COLUMN ── */
.avatar-col{display:flex;flex-direction:column;gap:12px;}
.avatar-showcase{
  position:relative;border-radius:20px;overflow:hidden;
  background:#0e0e1c;border:1px solid rgba(255,255,255,0.07);
  padding:1.5rem;display:flex;flex-direction:column;align-items:center;gap:1rem;
}
.avatar-showcase::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,#a78bfa 40%,#f472b6 60%,transparent);
}

.svg-avatar-wrap{position:relative;width:140px;height:140px;}
.avatar-ring{
  position:absolute;inset:-4px;border-radius:50%;
  background:conic-gradient(from 0deg,#7c3aed,#db2777,#f97316,#06b6d4,#7c3aed);
  animation:spin 8s linear infinite;
}
@keyframes spin{to{transform:rotate(360deg);}}
.avatar-ring-inner{
  position:absolute;inset:3px;border-radius:50%;
  background:#0e0e1c;z-index:1;
  display:flex;align-items:center;justify-content:center;overflow:hidden;
}

.open-badge{
  display:flex;align-items:center;gap:6px;padding:5px 14px;border-radius:100px;
  background:rgba(16,185,129,0.08);border:1px solid rgba(16,185,129,0.2);
  font-size:11px;color:#6ee7b7;font-family:'Space Mono',monospace;
}
.follow-btn{
  width:100%;padding:11px;border-radius:12px;
  background:rgba(124,58,237,0.15);border:1px solid rgba(124,58,237,0.3);
  color:#c4b5fd;font-size:13px;font-weight:500;cursor:pointer;
  font-family:'Inter',sans-serif;letter-spacing:0.02em;transition:all 0.25s;
}
.follow-btn:hover{background:rgba(124,58,237,0.3);border-color:#a78bfa;}
.social-row{display:flex;gap:8px;width:100%;}
.soc{
  flex:1;padding:9px;border-radius:10px;
  background:rgba(255,255,255,0.03);border:1px solid rgba(255,255,255,0.07);
  display:flex;align-items:center;justify-content:center;
  cursor:pointer;transition:all 0.2s;
}
.soc:hover{border-color:rgba(167,139,250,0.4);background:rgba(167,139,250,0.08);}
.soc svg{width:15px;height:15px;fill:rgba(255,255,255,0.3);transition:fill 0.2s;}
.soc:hover svg{fill:#c4b5fd;}

/* ── SECTION HEADER ── */
.sec-row{display:flex;align-items:center;justify-content:space-between;margin-bottom:1rem;}
.sec-label{
  font-family:'Space Mono',monospace;font-size:10px;letter-spacing:0.25em;
  color:rgba(167,139,250,0.4);text-transform:uppercase;
  display:flex;align-items:center;gap:10px;
}
.sec-label::before{content:'';display:inline-block;width:18px;height:1px;background:rgba(124,58,237,0.6);}
.sec-more{font-family:'Space Mono',monospace;font-size:10px;color:rgba(255,255,255,0.2);cursor:pointer;transition:color 0.2s;}
.sec-more:hover{color:#a78bfa;}

/* ── PINNED GRID ── */
.pinned{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:2.5rem;}
@media(max-width:560px){.pinned{grid-template-columns:1fr;}}

.pcard{
  background:#0a0a16;border:1px solid rgba(255,255,255,0.06);
  border-radius:16px;padding:1.25rem;
  display:flex;flex-direction:column;gap:10px;
  cursor:pointer;transition:all 0.25s;position:relative;overflow:hidden;
}
.pcard:hover{border-color:rgba(167,139,250,0.3);transform:translateY(-3px);box-shadow:0 12px 40px rgba(139,92,246,0.1);}
.pcard-glow{
  position:absolute;width:80px;height:80px;border-radius:50%;
  filter:blur(30px);opacity:0;transition:opacity 0.3s;top:-20px;right:-20px;
}
.pcard:hover .pcard-glow{opacity:1;}
.pcard-top{display:flex;justify-content:space-between;align-items:flex-start;}
.pcard-icon{
  width:40px;height:40px;border-radius:10px;
  background:rgba(255,255,255,0.04);border:1px solid rgba(255,255,255,0.07);
  display:flex;align-items:center;justify-content:center;
}
.pcard-icon svg{width:18px;height:18px;}
.pcard-pub{
  font-family:'Space Mono',monospace;font-size:9px;letter-spacing:0.1em;
  color:rgba(167,139,250,0.4);border:1px solid rgba(139,92,246,0.15);
  border-radius:100px;padding:2px 9px;
}
.pcard-name{font-family:'Space Mono',monospace;font-size:13px;color:#c4b5fd;}
.pcard-desc{font-size:12px;color:rgba(255,255,255,0.3);line-height:1.6;flex:1;}
.pcard-foot{display:flex;align-items:center;gap:14px;}
.lang-dot-wrap{display:flex;align-items:center;gap:5px;font-size:11px;color:rgba(255,255,255,0.25);font-family:'Space Mono',monospace;}
.ldot{width:9px;height:9px;border-radius:50%;flex-shrink:0;}
.pstat{font-size:11px;color:rgba(255,255,255,0.2);font-family:'Space Mono',monospace;}

/* ── BOTTOM GRID ── */
.bottom{display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;}
@media(max-width:600px){.bottom{grid-template-columns:1fr;}}

.glass{
  background:#0a0a16;border:1px solid rgba(255,255,255,0.05);
  border-radius:16px;padding:1.5rem;position:relative;overflow:hidden;
}
.glass::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,rgba(167,139,250,0.2),transparent);
}

/* ── SKILLS ── */
.skill-groups{display:flex;flex-direction:column;gap:16px;}
.sg-lbl{
  font-family:'Space Mono',monospace;font-size:9px;letter-spacing:0.15em;
  color:rgba(255,255,255,0.2);text-transform:uppercase;margin-bottom:8px;
}
.chips{display:flex;flex-wrap:wrap;gap:6px;}
.chip{
  padding:4px 12px;border-radius:100px;font-family:'Space Mono',monospace;
  font-size:10px;letter-spacing:0.03em;cursor:pointer;transition:all 0.2s;
}
.c-p{background:rgba(139,92,246,0.08);border:1px solid rgba(139,92,246,0.2);color:#c4b5fd;}
.c-p:hover{background:rgba(139,92,246,0.2);}
.c-k{background:rgba(236,72,153,0.08);border:1px solid rgba(236,72,153,0.2);color:#f9a8d4;}
.c-k:hover{background:rgba(236,72,153,0.2);}
.c-t{background:rgba(6,182,212,0.08);border:1px solid rgba(6,182,212,0.2);color:#67e8f9;}
.c-t:hover{background:rgba(6,182,212,0.2);}

/* ── STATS ── */
.stat-items{display:flex;flex-direction:column;}
.si{
  display:flex;align-items:center;gap:12px;
  padding:12px 0;border-bottom:1px solid rgba(255,255,255,0.04);
}
.si:last-child{border-bottom:none;}
.si-icon{
  width:34px;height:34px;border-radius:9px;
  background:rgba(255,255,255,0.04);border:1px solid rgba(255,255,255,0.06);
  display:flex;align-items:center;justify-content:center;flex-shrink:0;
}
.si-icon svg{width:15px;height:15px;fill:none;stroke:rgba(255,255,255,0.4);stroke-width:1.5;stroke-linecap:round;stroke-linejoin:round;}
.si-body{flex:1;}
.si-name{font-size:11px;color:rgba(255,255,255,0.3);font-family:'Space Mono',monospace;margin-bottom:5px;}
.si-track{height:3px;background:rgba(255,255,255,0.06);border-radius:2px;overflow:hidden;}
.si-fill{height:100%;border-radius:2px;}
.si-val{
  font-family:'Syne',sans-serif;font-size:16px;font-weight:800;
  background:linear-gradient(135deg,#a78bfa,#f472b6);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  min-width:40px;text-align:right;
}
</style>
</head>
<body>

<div class="aurora"></div>
<div class="scanlines"></div>

<div class="page">

  <!-- NAV -->
  <div class="topbar">
    <div class="topbar-brand">github / portfolio</div>
    <div class="topbar-btns">
      <button class="tbtn">Sign in</button>
      <button class="tbtn hi">Follow</button>
    </div>
  </div>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-left">
      <div class="hero-name">
        Maya<br>
        <span class="name-accent">Reyes.</span>
      </div>
      <div class="hero-role">
        <div class="role-dot"></div>
        Creative Designer &amp; Technologist
      </div>
      <div class="hero-bio">
        I craft <span class="bio-em">immersive visual experiences</span> where design meets code. From dark design systems to generative WebGL art — I build things that feel alive and look unforgettable.
      </div>
      <div class="meta-pills">
        <a class="mpill" href="#">
          <svg width="12" height="12" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
          Los Angeles, CA
        </a>
        <a class="mpill" href="#">
          <svg width="12" height="12" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M13.828 10.172a4 4 0 00-5.656 0l-4 4a4 4 0 105.656 5.656l1.102-1.101m-.758-4.899a4 4 0 005.656 0l4-4a4 4 0 00-5.656-5.656l-1.1 1.1"/></svg>
          mayareyes.design
        </a>
        <a class="mpill" href="#">
          <svg width="12" height="12" fill="currentColor" viewBox="0 0 24 24"><path d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"/></svg>
          @mayareyes_
        </a>
        <a class="mpill" href="#">
          <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="4" fill="#06060f"/></svg>
          Dribbble
        </a>
      </div>
      <div class="stat-strip">
        <div class="sstat"><div class="sstat-num">312</div><div class="sstat-lbl">followers</div></div>
        <div class="sstat"><div class="sstat-num">2.1k</div><div class="sstat-lbl">stars</div></div>
        <div class="sstat"><div class="sstat-num">34</div><div class="sstat-lbl">repos</div></div>
        <div class="sstat"><div class="sstat-num">847</div><div class="sstat-lbl">commits</div></div>
      </div>
    </div>

    <!-- AVATAR -->
    <div class="avatar-col">
      <div class="avatar-showcase">
        <div class="svg-avatar-wrap">
          <div class="avatar-ring"></div>
          <div class="avatar-ring-inner">
            <svg viewBox="0 0 140 140" xmlns="http://www.w3.org/2000/svg" width="134" height="134">
              <defs>
                <radialGradient id="bg" cx="50%" cy="30%" r="70%">
                  <stop offset="0%" stop-color="#1a1030"/>
                  <stop offset="100%" stop-color="#06060f"/>
                </radialGradient>
                <radialGradient id="skin" cx="45%" cy="40%" r="60%">
                  <stop offset="0%" stop-color="#c8845a"/>
                  <stop offset="100%" stop-color="#a0623e"/>
                </radialGradient>
                <radialGradient id="glow1" cx="50%" cy="50%" r="50%">
                  <stop offset="0%" stop-color="#7c3aed" stop-opacity="0.5"/>
                  <stop offset="100%" stop-color="#7c3aed" stop-opacity="0"/>
                </radialGradient>
                <radialGradient id="glow2" cx="50%" cy="50%" r="50%">
                  <stop offset="0%" stop-color="#db2777" stop-opacity="0.4"/>
                  <stop offset="100%" stop-color="#db2777" stop-opacity="0"/>
                </radialGradient>
                <clipPath id="circ"><circle cx="70" cy="70" r="67"/></clipPath>
              </defs>
              <circle cx="70" cy="70" r="70" fill="url(#bg)"/>
              <ellipse cx="30" cy="40" rx="50" ry="40" fill="url(#glow1)" clip-path="url(#circ)"/>
              <ellipse cx="110" cy="100" rx="45" ry="35" fill="url(#glow2)" clip-path="url(#circ)"/>
              <polygon points="70,8 110,30 110,72 70,94 30,72 30,30" fill="none" stroke="rgba(167,139,250,0.08)" stroke-width="1" clip-path="url(#circ)"/>
              <polygon points="70,20 100,36 100,68 70,84 40,68 40,36" fill="none" stroke="rgba(167,139,250,0.06)" stroke-width="0.5" clip-path="url(#circ)"/>
              <path d="M32 140 Q32 105 70 100 Q108 105 108 140 Z" fill="#0f0820" clip-path="url(#circ)"/>
              <rect x="62" y="88" width="16" height="18" rx="6" fill="url(#skin)" clip-path="url(#circ)"/>
              <ellipse cx="70" cy="72" rx="26" ry="28" fill="url(#skin)" clip-path="url(#circ)"/>
              <path d="M44 68 Q44 44 70 42 Q96 44 96 68 Q96 55 88 50 Q80 36 70 36 Q60 36 52 50 Q44 55 44 68Z" fill="#1a0a2e" clip-path="url(#circ)"/>
              <path d="M44 65 Q42 58 46 52 Q50 42 60 40" fill="none" stroke="#1a0a2e" stroke-width="8" stroke-linecap="round" clip-path="url(#circ)"/>
              <path d="M96 65 Q98 58 94 52 Q90 42 80 40" fill="none" stroke="#1a0a2e" stroke-width="8" stroke-linecap="round" clip-path="url(#circ)"/>
              <ellipse cx="44" cy="72" rx="5" ry="7" fill="#b5723a" clip-path="url(#circ)"/>
              <ellipse cx="96" cy="72" rx="5" ry="7" fill="#b5723a" clip-path="url(#circ)"/>
              <ellipse cx="59" cy="70" rx="6" ry="7" fill="#fff" clip-path="url(#circ)"/>
              <ellipse cx="81" cy="70" rx="6" ry="7" fill="#fff" clip-path="url(#circ)"/>
              <ellipse cx="60" cy="71" rx="4" ry="4.5" fill="#2d1b69" clip-path="url(#circ)"/>
              <ellipse cx="82" cy="71" rx="4" ry="4.5" fill="#2d1b69" clip-path="url(#circ)"/>
              <circle cx="61" cy="70" r="1.5" fill="#a78bfa" clip-path="url(#circ)"/>
              <circle cx="83" cy="70" r="1.5" fill="#a78bfa" clip-path="url(#circ)"/>
              <circle cx="62.5" cy="68.5" r="1" fill="#fff" clip-path="url(#circ)"/>
              <circle cx="84.5" cy="68.5" r="1" fill="#fff" clip-path="url(#circ)"/>
              <path d="M53 63 Q59 60 65 62" fill="none" stroke="#1a0a2e" stroke-width="2" stroke-linecap="round" clip-path="url(#circ)"/>
              <path d="M75 62 Q81 60 87 63" fill="none" stroke="#1a0a2e" stroke-width="2" stroke-linecap="round" clip-path="url(#circ)"/>
              <path d="M68 74 Q70 80 72 74" fill="none" stroke="#a0623e" stroke-width="1.5" stroke-linecap="round" clip-path="url(#circ)"/>
              <path d="M63 83 Q70 88 77 83" fill="none" stroke="#8b4513" stroke-width="2" stroke-linecap="round" clip-path="url(#circ)"/>
              <path d="M63 83 Q66 85 70 85 Q74 85 77 83" fill="rgba(180,80,60,0.4)" clip-path="url(#circ)"/>
              <path d="M44 68 Q40 65 40 72 Q40 78 44 76" fill="none" stroke="#a78bfa" stroke-width="1.5" stroke-linecap="round" clip-path="url(#circ)"/>
              <circle cx="40" cy="72" r="2" fill="#7c3aed" clip-path="url(#circ)"/>
              <path d="M96 68 Q100 65 100 72 Q100 78 96 76" fill="none" stroke="#f472b6" stroke-width="1.5" stroke-linecap="round" clip-path="url(#circ)"/>
              <circle cx="100" cy="72" r="2" fill="#db2777" clip-path="url(#circ)"/>
              <circle cx="18" cy="25" r="2" fill="rgba(167,139,250,0.5)" clip-path="url(#circ)"/>
              <circle cx="122" cy="30" r="1.5" fill="rgba(244,114,182,0.5)" clip-path="url(#circ)"/>
              <circle cx="15" cy="110" r="1" fill="rgba(103,232,249,0.4)" clip-path="url(#circ)"/>
              <circle cx="125" cy="105" r="2" fill="rgba(167,139,250,0.3)" clip-path="url(#circ)"/>
            </svg>
          </div>
        </div>
        <div class="open-badge">
          <div class="role-dot"></div>
          open to work
        </div>
        <button class="follow-btn" id="followBtn">+ Follow Maya</button>
        <div class="social-row">
          <div class="soc" title="Twitter">
            <svg viewBox="0 0 24 24" fill="rgba(255,255,255,0.3)" width="15" height="15"><path d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"/></svg>
          </div>
          <div class="soc" title="Dribbble">
            <svg viewBox="0 0 24 24" fill="rgba(255,255,255,0.3)" width="15" height="15"><circle cx="12" cy="12" r="10"/><path fill="#0a0a16" d="M8.56 2.75c4.37 6.03 6.02 9.42 8.03 17.72m2.54-15.38c-3.72 4.35-8.94 5.66-16.88 5.85m19.5 1.9c-3.5-.93-6.63-.82-8.94 0-2.58.92-5.01 2.86-7.44 6.32"/></svg>
          </div>
          <div class="soc" title="LinkedIn">
            <svg viewBox="0 0 24 24" fill="rgba(255,255,255,0.3)" width="15" height="15"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
          </div>
          <div class="soc" title="Email">
            <svg viewBox="0 0 24 24" fill="none" stroke="rgba(255,255,255,0.3)" stroke-width="1.5" width="15" height="15"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- PINNED PROJECTS -->
  <div class="sec-row">
    <div class="sec-label">Pinned projects</div>
    <div class="sec-more">View all repos →</div>
  </div>
  <div class="pinned">

    <div class="pcard">
      <div class="pcard-glow" style="background:#7c3aed;"></div>
      <div class="pcard-top">
        <div class="pcard-icon">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#a78bfa" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
        </div>
        <div class="pcard-pub">public</div>
      </div>
      <div class="pcard-name">aurora-design-system</div>
      <div class="pcard-desc">Dark-mode-first design system with 80+ components, motion tokens, and Figma source files.</div>
      <div class="pcard-foot">
        <div class="lang-dot-wrap"><div class="ldot" style="background:#f472b6;"></div>Figma</div>
        <div class="pstat">★ 934</div>
        <div class="pstat">⑂ 142</div>
      </div>
    </div>

    <div class="pcard">
      <div class="pcard-glow" style="background:#db2777;"></div>
      <div class="pcard-top">
        <div class="pcard-icon">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#f472b6" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>
        </div>
        <div class="pcard-pub">public</div>
      </div>
      <div class="pcard-name">glitch-canvas-kit</div>
      <div class="pcard-desc">WebGL + GLSL toolkit for generative glitch art and procedural visual effects in the browser.</div>
      <div class="pcard-foot">
        <div class="lang-dot-wrap"><div class="ldot" style="background:#a78bfa;"></div>GLSL</div>
        <div class="pstat">★ 617</div>
        <div class="pstat">⑂ 88</div>
      </div>
    </div>

    <div class="pcard">
      <div class="pcard-glow" style="background:#0891b2;"></div>
      <div class="pcard-top">
        <div class="pcard-icon">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#67e8f9" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><path d="M8 14s1.5 2 4 2 4-2 4-2"/><line x1="9" y1="9" x2="9.01" y2="9"/><line x1="15" y1="9" x2="15.01" y2="9"/></svg>
        </div>
        <div class="pcard-pub">public</div>
      </div>
      <div class="pcard-name">motion-primitives</div>
      <div class="pcard-desc">Framer Motion animation presets and spring physics utilities for React — copy-paste ready.</div>
      <div class="pcard-foot">
        <div class="lang-dot-wrap"><div class="ldot" style="background:#67e8f9;"></div>TypeScript</div>
        <div class="pstat">★ 402</div>
        <div class="pstat">⑂ 61</div>
      </div>
    </div>

    <div class="pcard">
      <div class="pcard-glow" style="background:#d97706;"></div>
      <div class="pcard-top">
        <div class="pcard-icon">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#fbbf24" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="5"/><path d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"/></svg>
        </div>
        <div class="pcard-pub">public</div>
      </div>
      <div class="pcard-name">void-palette</div>
      <div class="pcard-desc">AI-powered dark color palette generator that creates harmonious schemes from any seed image.</div>
      <div class="pcard-foot">
        <div class="lang-dot-wrap"><div class="ldot" style="background:#fbbf24;"></div>Python</div>
        <div class="pstat">★ 289</div>
        <div class="pstat">⑂ 34</div>
      </div>
    </div>

  </div>

  <!-- SKILLS + STATS -->
  <div class="bottom">

    <div class="glass">
      <div class="sec-row" style="margin-bottom:1.25rem;">
        <div class="sec-label">Tech stack</div>
      </div>
      <div class="skill-groups">
        <div>
          <div class="sg-lbl">Design</div>
          <div class="chips">
            <div class="chip c-k">Figma</div>
            <div class="chip c-k">Framer</div>
            <div class="chip c-k">After Effects</div>
            <div class="chip c-k">Spline</div>
            <div class="chip c-k">Blender</div>
          </div>
        </div>
        <div>
          <div class="sg-lbl">Code</div>
          <div class="chips">
            <div class="chip c-p">React</div>
            <div class="chip c-p">GSAP</div>
            <div class="chip c-p">Three.js</div>
            <div class="chip c-p">GLSL</div>
            <div class="chip c-p">CSS</div>
          </div>
        </div>
        <div>
          <div class="sg-lbl">Tools</div>
          <div class="chips">
            <div class="chip c-t">Vercel</div>
            <div class="chip c-t">Storybook</div>
            <div class="chip c-t">GitHub</div>
            <div class="chip c-t">Notion</div>
          </div>
        </div>
      </div>
    </div>

    <div class="glass">
      <div class="sec-row" style="margin-bottom:1.25rem;">
        <div class="sec-label">GitHub stats</div>
      </div>
      <div class="stat-items">
        <div class="si">
          <div class="si-icon">
            <svg viewBox="0 0 24 24" width="15" height="15" fill="none" stroke="rgba(255,255,255,0.4)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
          </div>
          <div class="si-body">
            <div class="si-name">total stars earned</div>
            <div class="si-track"><div class="si-fill" style="width:85%;background:linear-gradient(90deg,#7c3aed,#a78bfa);"></div></div>
          </div>
          <div class="si-val">2.1k</div>
        </div>
        <div class="si">
          <div class="si-icon">
            <svg viewBox="0 0 24 24" width="15" height="15" fill="none" stroke="rgba(255,255,255,0.4)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
          </div>
          <div class="si-body">
            <div class="si-name">commits in 2025</div>
            <div class="si-track"><div class="si-fill" style="width:70%;background:linear-gradient(90deg,#db2777,#f472b6);"></div></div>
          </div>
          <div class="si-val">847</div>
        </div>
        <div class="si">
          <div class="si-icon">
            <svg viewBox="0 0 24 24" width="15" height="15" fill="none" stroke="rgba(255,255,255,0.4)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="18" cy="18" r="3"/><circle cx="6" cy="6" r="3"/><path d="M6 21V9a9 9 0 009 9"/></svg>
          </div>
          <div class="si-body">
            <div class="si-name">pull requests merged</div>
            <div class="si-track"><div class="si-fill" style="width:55%;background:linear-gradient(90deg,#0891b2,#67e8f9);"></div></div>
          </div>
          <div class="si-val">193</div>
        </div>
        <div class="si">
          <div class="si-icon">
            <svg viewBox="0 0 24 24" width="15" height="15" fill="none" stroke="rgba(255,255,255,0.4)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>
          </div>
          <div class="si-body">
            <div class="si-name">issues resolved</div>
            <div class="si-track"><div class="si-fill" style="width:42%;background:linear-gradient(90deg,#059669,#6ee7b7);"></div></div>
          </div>
          <div class="si-val">124</div>
        </div>
        <div class="si">
          <div class="si-icon">
            <svg viewBox="0 0 24 24" width="15" height="15" fill="none" stroke="rgba(255,255,255,0.4)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M22 19a2 2 0 01-2 2H4a2 2 0 01-2-2V5a2 2 0 012-2h5l2 3h9a2 2 0 012 2z"/></svg>
          </div>
          <div class="si-body">
            <div class="si-name">repos contributed to</div>
            <div class="si-track"><div class="si-fill" style="width:30%;background:linear-gradient(90deg,#d97706,#fbbf24);"></div></div>
          </div>
          <div class="si-val">61</div>
        </div>
      </div>
    </div>

  </div>
</div>

<script>
  document.getElementById('followBtn').addEventListener('click', function(){
    this.textContent = '✓ Following';
    this.style.background = 'rgba(16,185,129,0.15)';
    this.style.borderColor = 'rgba(16,185,129,0.3)';
    this.style.color = '#6ee7b7';
  });
</script>

</body>
</html>

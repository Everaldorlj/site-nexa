[index.html](https://github.com/user-attachments/files/26800600/index.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NEXA Comunicação Visual — João Pessoa, PB</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;900&display=swap" rel="stylesheet">
<style>
:root {
  --cyan:#29B6F6;
  --black:#000; --dark:#070a0f; --dark2:#04070c; --dark3:#0d1117;
  --white:#fff; --gray:#888; --gray2:#777;
}
*{margin:0;padding:0;box-sizing:border-box;}
html { scroll-behavior:smooth; }
body {
  font-family:'Montserrat',sans-serif;
  background:var(--dark); color:var(--white);
  overflow-x:hidden;
}
body::before {
  content:''; position:fixed; inset:0; z-index:0; pointer-events:none;
  opacity:0.025;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
  background-size:200px 200px;
}

/* ══════════════ NAV ══════════════ */
nav {
  position:fixed; top:0; left:0; right:0; z-index:100;
  background:rgba(0,0,0,0.92); backdrop-filter:blur(12px);
  border-bottom:1px solid #111;
  padding:0 60px; height:64px;
  display:flex; align-items:center; justify-content:space-between;
  transition:background .3s;
}
.nav-logo { font-size:20px; font-weight:900; letter-spacing:6px; }
.nav-logo .x { color:var(--cyan); text-shadow:0 0 12px rgba(41,182,246,0.6); }
.nav-links { display:flex; gap:36px; }
.nav-links a {
  font-size:12px; font-weight:700; letter-spacing:2px;
  color:var(--gray2); text-decoration:none; text-transform:uppercase;
  transition:color .2s;
}
.nav-links a:hover { color:var(--white); }
.nav-cta {
  background:var(--cyan); color:var(--black); border:none;
  padding:10px 24px; font-family:'Montserrat',sans-serif;
  font-size:12px; font-weight:900; letter-spacing:2px;
  cursor:pointer; text-transform:uppercase;
  transition:background .2s, transform .1s;
  text-decoration:none;
}
.nav-cta:hover { background:#1da8e8; transform:translateY(-1px); }

/* ══════════════ HERO ══════════════ */
#hero {
  position:relative; min-height:100vh;
  display:flex; align-items:center; justify-content:center;
  overflow:hidden; padding:120px 60px 80px;
}
#hero-canvas { position:absolute; inset:0; z-index:0; }
.hero-glow {
  position:absolute; width:600px; height:600px; border-radius:50%;
  background:radial-gradient(circle, rgba(41,182,246,0.06), transparent 70%);
  top:50%; left:50%; transform:translate(-50%,-50%);
  pointer-events:none; z-index:1;
}
.hero-content {
  position:relative; z-index:2; text-align:center;
  max-width:800px;
}
.hero-eyebrow {
  font-size:10px; font-weight:700; letter-spacing:6px;
  color:var(--cyan); text-transform:uppercase; margin-bottom:24px;
  opacity:0; transform:translateY(20px);
  animation:fadeUp .8s ease .2s forwards;
}
.hero-title {
  font-size:clamp(48px, 7vw, 88px); font-weight:900;
  line-height:1.0; letter-spacing:-2px;
  opacity:0; transform:translateY(20px);
  animation:fadeUp .8s ease .4s forwards;
}
.hero-title .x { color:var(--cyan); text-shadow:0 0 40px rgba(41,182,246,0.4), 0 0 80px rgba(41,182,246,0.15); }
.hero-title .big { display:block; }
.hero-sub {
  font-size:16px; font-weight:600; color:var(--gray);
  line-height:1.7; margin-top:28px; max-width:520px; margin-left:auto; margin-right:auto;
  opacity:0; transform:translateY(20px);
  animation:fadeUp .8s ease .6s forwards;
}
.hero-sub strong { color:var(--white); }
.hero-actions {
  display:flex; gap:16px; justify-content:center; margin-top:44px;
  opacity:0; transform:translateY(20px);
  animation:fadeUp .8s ease .8s forwards;
}
.btn-primary {
  background:var(--cyan); color:var(--black); border:none;
  padding:16px 36px; font-family:'Montserrat',sans-serif;
  font-size:11px; font-weight:900; letter-spacing:3px;
  cursor:pointer; text-transform:uppercase;
  text-decoration:none; display:inline-block;
  transition:background .2s, transform .1s;
}
.btn-primary:hover { background:#1da8e8; transform:translateY(-2px); }
.btn-ghost {
  background:transparent; color:#555;
  border:1px solid #222; padding:16px 36px;
  font-family:'Montserrat',sans-serif;
  font-size:11px; font-weight:600; letter-spacing:3px;
  cursor:pointer; text-transform:uppercase;
  text-decoration:none; display:inline-block;
  transition:border-color .2s, color .2s, transform .1s;
}
.btn-ghost:hover { border-color:#555; color:#aaa; transform:translateY(-2px); }

.hero-badge {
  display:inline-flex; align-items:center; gap:8px;
  border:1px solid #333; padding:8px 20px;
  font-size:12px; color:#aaa; letter-spacing:2px;
  margin-top:50px;
  opacity:0; animation:fadeUp .8s ease 1s forwards;
}
.hero-badge .dot { width:6px; height:6px; background:var(--cyan); border-radius:50%; animation:pulse 2s infinite; }
@keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.5;transform:scale(0.8)} }

/* corners */
#hero::before, #hero::after {
  content:''; position:absolute;
  width:100px; height:100px;
  border-color:rgba(41,182,246,0.15); border-style:solid;
  z-index:2; pointer-events:none;
}
#hero::before { top:80px; left:40px; border-width:1px 0 0 1px; }
#hero::after  { bottom:40px; right:40px; border-width:0 1px 1px 0; }

/* scanlines hero */
.hero-scan {
  position:absolute; inset:0; z-index:1; pointer-events:none;
  background:repeating-linear-gradient(0deg,transparent,transparent 5px,rgba(0,0,0,0.015) 5px,rgba(0,0,0,0.015) 10px);
}

@keyframes fadeUp { to { opacity:1; transform:translateY(0); } }

/* ══════════════ STRIP ══════════════ */
.strip {
  background:#000; border-top:1px solid #0d0d0d; border-bottom:1px solid #0d0d0d;
  padding:20px 60px; overflow:hidden;
  display:flex; align-items:center; gap:0;
}
.strip-inner {
  display:flex; gap:60px; align-items:center;
  animation:scroll 20s linear infinite;
  white-space:nowrap;
}
.strip-item {
  font-size:11px; font-weight:700; letter-spacing:3px; color:#555;
  text-transform:uppercase; flex-shrink:0;
}
.strip-item span { color:var(--cyan); }
.strip-dot { color:#1a1a1a; font-size:18px; flex-shrink:0; }
@keyframes scroll { 0%{transform:translateX(0)} 100%{transform:translateX(-50%)} }

/* ══════════════ SECTIONS ══════════════ */
section { padding:100px 60px; max-width:1200px; margin:0 auto; }
.sec-label {
  font-size:11px; font-weight:700; letter-spacing:4px;
  color:var(--cyan); text-transform:uppercase; margin-bottom:14px;
}
.sec-title {
  font-size:clamp(32px, 4vw, 52px); font-weight:900;
  line-height:1.1; letter-spacing:-1px; margin-bottom:20px;
}
.sec-sub {
  font-size:15px; color:var(--gray); line-height:1.8;
  max-width:560px;
}

/* ══════════════ SOBRE ══════════════ */
#sobre {
  display:grid; grid-template-columns:1fr 1fr; gap:80px; align-items:center;
}
.sobre-visual {
  position:relative; aspect-ratio:1; max-width:480px;
  background:#000; overflow:hidden;
  border:1px solid #111;
}
.sobre-x {
  position:absolute; font-size:500px; font-weight:900;
  color:var(--cyan); opacity:0.04; right:-80px; bottom:-100px; line-height:1;
}
.sobre-glow {
  position:absolute; inset:0;
  background:radial-gradient(circle at 40% 40%, rgba(41,182,246,0.07), transparent 60%);
}
.sobre-corners::before, .sobre-corners::after {
  content:''; position:absolute; width:40px; height:40px;
  border-color:rgba(41,182,246,0.4); border-style:solid;
}
.sobre-corners::before { top:20px; left:20px; border-width:1.5px 0 0 1.5px; }
.sobre-corners::after  { bottom:20px; right:20px; border-width:0 1.5px 1.5px 0; }
.sobre-center {
  position:absolute; inset:0; display:flex; flex-direction:column;
  align-items:center; justify-content:center; gap:12px; z-index:2;
}
.sobre-logo { font-size:52px; font-weight:900; letter-spacing:8px; }
.sobre-logo .x {
  color:var(--cyan); font-size:84px;
  text-shadow:0 0 40px rgba(41,182,246,0.5);
}
.sobre-tag { font-size:9px; font-weight:700; letter-spacing:5px; color:var(--cyan); text-transform:uppercase; }
.sobre-year { font-size:11px; color:#222; letter-spacing:4px; margin-top:16px; font-family:monospace; }

.sobre-text { display:flex; flex-direction:column; gap:28px; }
.sobre-text p { font-size:15px; color:var(--gray); line-height:1.8; }
.sobre-text strong { color:var(--white); }
.sobre-stats { display:grid; grid-template-columns:1fr 1fr; gap:2px; margin-top:8px; }
.stat-box { background:#000; padding:20px; border:1px solid #111; }
.stat-num { font-size:32px; font-weight:900; color:var(--cyan); line-height:1; }
.stat-lbl { font-size:9px; color:var(--gray2); letter-spacing:2px; text-transform:uppercase; margin-top:4px; }

/* ══════════════ SERVIÇOS ══════════════ */
#servicos { border-top:1px solid #0d0d0d; }
.servicos-header { margin-bottom:60px; }
.servicos-grid {
  display:grid; grid-template-columns:repeat(3, 1fr); gap:2px;
}
.srv-card {
  background:#04070c; border:1px solid #0d1117;
  transition:border-color .3s, background .3s;
  position:relative; overflow:hidden;
  display:flex; flex-direction:column;
}
.srv-card:hover { background:#060a10; border-color:#1a2a3a; }
.srv-card:hover .srv-icon { color:var(--cyan); }
.srv-photo {
  width:100%; height:200px; overflow:hidden; flex-shrink:0;
}
.srv-photo img {
  width:100%; height:100%; object-fit:cover;
  opacity:0.65; filter:grayscale(20%);
  transition:opacity .4s ease, transform .5s ease;
  display:block;
}
.srv-card:hover .srv-photo img { opacity:0.85; transform:scale(1.04); filter:grayscale(0%); }
.srv-card-inner { padding:32px 36px 40px; }
.srv-num {
  font-size:9px; color:#1a1a1a; font-weight:700;
  letter-spacing:3px; font-family:monospace; margin-bottom:20px;
}
.srv-icon { font-size:28px; margin-bottom:20px; transition:color .2s; color:#333; }
.srv-title { font-size:18px; font-weight:900; color:var(--white); margin-bottom:12px; letter-spacing:-0.3px; }
.srv-desc { font-size:15px; color:var(--gray2); line-height:1.7; }
.srv-tag {
  display:inline-block; margin-top:20px;
  font-size:11px; font-weight:700; letter-spacing:2px;
  color:var(--cyan); text-transform:uppercase;
  background:rgba(41,182,246,0.06); padding:5px 12px;
}

/* ══════════════ DIFERENCIAIS ══════════════ */
#diferenciais {
  display:grid; grid-template-columns:1fr 1fr; gap:80px; align-items:start;
  border-top:1px solid #0d0d0d;
}
.dif-list { display:flex; flex-direction:column; gap:2px; margin-top:40px; }
.dif-item {
  display:flex; gap:20px; align-items:flex-start;
  padding:24px; background:#000; border:1px solid #0d0d0d;
  transition:border-color .2s;
}
.dif-item:hover { border-color:#1a1a1a; }
.dif-ico { color:var(--cyan); font-size:20px; flex-shrink:0; margin-top:2px; }
.dif-text .dif-title { font-size:14px; font-weight:700; color:var(--white); margin-bottom:4px; }
.dif-text .dif-desc { font-size:12px; color:var(--gray2); line-height:1.6; }

.dif-visual { position:sticky; top:100px; }
.quote-block {
  background:#000; border:1px solid #111;
  border-left:3px solid var(--cyan);
  padding:36px 32px; margin-bottom:2px;
}
.quote-text {
  font-size:18px; font-weight:700; color:var(--white);
  line-height:1.5; letter-spacing:-0.3px;
}
.quote-text .c { color:var(--cyan); }
.quote-source { font-size:9px; color:var(--gray2); letter-spacing:3px; text-transform:uppercase; margin-top:16px; }

/* ══════════════ CLIENTES ══════════════ */
#clientes { text-align:center; border-top:1px solid #0d0d0d; }
.clientes-header { margin-bottom:60px; }
.clientes-grid {
  display:flex; gap:2px; justify-content:center; flex-wrap:wrap;
}
.cli-card {
  background:#000; border:1px solid #0d0d0d;
  padding:28px 40px; display:flex; flex-direction:column;
  align-items:center; gap:10px; min-width:180px;
  transition:border-color .2s;
}
.cli-card:hover { border-color:#1a1a1a; }
.cli-name { font-size:11px; font-weight:900; letter-spacing:3px; color:var(--white); }
.cli-seg { font-size:8px; color:var(--gray2); letter-spacing:2px; text-transform:uppercase; }
.cli-badge { font-size:8px; color:var(--cyan); letter-spacing:2px; background:rgba(41,182,246,0.06); padding:3px 8px; }

/* ══════════════ CTA ══════════════ */
#cta {
  text-align:center; border-top:1px solid #0d0d0d;
  position:relative; overflow:hidden;
}
.cta-glow {
  position:absolute; width:800px; height:400px; border-radius:50%;
  background:radial-gradient(circle, rgba(41,182,246,0.05), transparent 70%);
  top:50%; left:50%; transform:translate(-50%,-50%);
  pointer-events:none;
}
.cta-x {
  position:absolute; font-size:600px; font-weight:900;
  color:var(--cyan); opacity:0.02; right:-120px; bottom:-160px; line-height:1;
}
.cta-content { position:relative; z-index:2; }
.cta-tag {
  display:inline-block; background:rgba(41,182,246,0.1);
  border:1px solid rgba(41,182,246,0.2);
  padding:8px 20px; font-size:9px; font-weight:700;
  letter-spacing:4px; color:var(--cyan); text-transform:uppercase;
  margin-bottom:30px;
}
.cta-title { font-size:clamp(36px, 5vw, 64px); font-weight:900; line-height:1.1; letter-spacing:-1px; margin-bottom:20px; }
.cta-title .c { color:var(--cyan); }
.cta-sub { font-size:15px; color:var(--gray); max-width:480px; margin:0 auto 44px; line-height:1.7; }
.cta-contacts {
  display:flex; gap:2px; justify-content:center; flex-wrap:wrap; margin-top:40px;
}
.contact-chip {
  background:#000; border:1px solid #111;
  padding:16px 28px; display:flex; align-items:center; gap:12px;
  text-decoration:none; transition:border-color .2s;
}
.contact-chip:hover { border-color:var(--cyan); }
.chip-ico { font-size:18px; }
.chip-info { text-align:left; }
.chip-label { font-size:11px; color:var(--gray2); letter-spacing:2px; text-transform:uppercase; }
.chip-value { font-size:13px; font-weight:700; color:var(--white); }

/* ══════════════ FOOTER ══════════════ */
footer {
  background:#000; border-top:1px solid #0d0d0d;
  padding:40px 60px;
  display:flex; justify-content:space-between; align-items:center;
  flex-wrap:wrap; gap:20px;
}
.foot-logo { font-size:18px; font-weight:900; letter-spacing:6px; }
.foot-logo .x { color:var(--cyan); }
.foot-info { font-size:11px; color:#555; letter-spacing:1px; line-height:2; }
.foot-links { display:flex; gap:24px; }
.foot-links a {
  font-size:11px; color:#555; letter-spacing:2px; text-decoration:none;
  text-transform:uppercase; font-weight:700; transition:color .2s;
}
.foot-links a:hover { color:var(--cyan); }

/* ══════════════ UTILS ══════════════ */
.accent-line {
  width:40px; height:2px;
  background:var(--cyan);
  margin:20px 0;
}

/* ══════════════ REDUCED MOTION ══════════════ */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation-duration:0.01ms !important; transition-duration:0.01ms !important; }
  .strip-inner { animation:none; }
}

/* ══════════════ RESPONSIVE ══════════════ */
@media (max-width:900px) {
  nav { padding:0 24px; }
  .nav-links { display:none; }
  #hero { padding:100px 24px 60px; }
  section { padding:60px 24px; }
  #sobre { grid-template-columns:1fr; gap:40px; }
  .sobre-visual { max-width:100%; aspect-ratio:1; }
  #diferenciais { grid-template-columns:1fr; gap:40px; }
  .dif-visual { position:static; }
  .servicos-grid { grid-template-columns:1fr 1fr; }
  footer { padding:32px 24px; flex-direction:column; align-items:flex-start; }
  .sobre-stats { grid-template-columns:1fr 1fr; }
}

@media (max-width:560px) {
  .servicos-grid { grid-template-columns:1fr; }
  .hero-actions { flex-direction:column; align-items:center; }
  .btn-primary, .btn-ghost { width:100%; text-align:center; }
  .cta-contacts { flex-direction:column; align-items:center; }
  .contact-chip { width:100%; justify-content:center; }
  #sobre { padding:60px 20px; }
  .sobre-stats { grid-template-columns:1fr 1fr; }
  .clientes-grid { flex-direction:column; align-items:center; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo"><img src="FOTOS/NEXA FULLHD.png" alt="NEXA" style="height:128px;width:auto;display:block;"></div>
  <div class="nav-links">
    <a href="#sobre">Sobre</a>
    <a href="#servicos">Serviços</a>
    <a href="#diferenciais">Diferenciais</a>
    <a href="#clientes">Clientes</a>
    <a href="#cta">Contato</a>
  </div>
  <a class="nav-cta" href="#cta">Orçamento Grátis</a>
</nav>

<!-- HERO -->
<div id="hero" style="background:radial-gradient(ellipse 80% 60% at 50% 0%, rgba(41,182,246,0.05) 0%, var(--dark) 70%);">
  <canvas id="hero-canvas"></canvas>
  <div class="hero-glow"></div>
  <div class="hero-scan"></div>
  <div class="hero-content">
    <div class="hero-eyebrow">Comunicação Visual · João Pessoa, PB</div>
    <h1 class="hero-title">
      <span class="big">SUA <span style="color:#29B6F6">MARCA</span></span>
      <span class="big">FALA ANTES</span>
      <span class="big">DE VOCÊ.</span>
    </h1>
    <p class="hero-sub">
      A NEXA transforma fachadas comuns em <strong>ativos de negócio</strong>.
      Letras caixa, fachadas, adesivos e sinalização que geram
      <strong>resultado real</strong> para o seu comércio.
    </p>
    <div class="hero-actions">
      <a class="btn-primary" href="#cta">Quero um orçamento grátis</a>
      <a class="btn-ghost" href="#servicos">Ver serviços</a>
    </div>
    <div class="hero-badge">
      <div class="dot"></div>
      Atendendo João Pessoa e região
    </div>
  </div>
</div>

<!-- STRIP -->
<div class="strip">
  <div class="strip-inner">
    <span class="strip-item">Fachadas <span>·</span></span>
    <span class="strip-item">Letras Caixa <span>·</span></span>
    <span class="strip-item">Adesivos e Plotagem <span>·</span></span>
    <span class="strip-item">Lonas e Impressão <span>·</span></span>
    <span class="strip-item">Sinalização <span>·</span></span>
    <span class="strip-item">Comunicação Visual <span>·</span></span>
    <span class="strip-item">João Pessoa · PB <span>·</span></span>
    <span class="strip-item">Fachadas <span>·</span></span>
    <span class="strip-item">Letras Caixa <span>·</span></span>
    <span class="strip-item">Adesivos e Plotagem <span>·</span></span>
    <span class="strip-item">Lonas e Impressão <span>·</span></span>
    <span class="strip-item">Sinalização <span>·</span></span>
    <span class="strip-item">Comunicação Visual <span>·</span></span>
    <span class="strip-item">João Pessoa · PB <span>·</span></span>
  </div>
</div>

<!-- SOBRE -->
<section id="sobre">
  <div class="sobre-visual">
    <div class="sobre-x">X</div>
    <div class="sobre-glow"></div>
    <div class="sobre-corners"></div>
    <div class="sobre-center">
      <div class="sobre-logo"><img src="FOTOS/NEXA FULLHD.png" alt="NEXA" style="height:360px;width:auto;display:block;"></div>
      <div class="sobre-tag">Comunicação Visual</div>
      <div class="sobre-year">João Pessoa · PB · Fundada em 2010</div>
    </div>
  </div>
  <div class="sobre-text">
    <div class="sec-label">Sobre nós</div>
    <h2 class="sec-title">Pai e filho.<br>Uma geração de<br>conexões.</h2>
    <p>A NEXA nasceu da evolução de uma história construída por anos de dedicação à comunicação visual. Hoje, unimos a experiência de quem fundou o negócio com a visão de quem quer levá-lo ao próximo nível.</p>
    <p>Atendemos desde <strong>pequenos comércios</strong> que querem se destacar na rua até <strong>grandes indústrias alimentícias</strong> que precisam de soluções visuais de alta precisão.</p>
    <div class="sobre-stats">
      <div class="stat-box">
        <div class="stat-num">10+</div>
        <div class="stat-lbl">Anos de mercado</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">1h</div>
        <div class="stat-lbl">Resposta ao orçamento</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">JP</div>
        <div class="stat-lbl">João Pessoa e região</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">∞</div>
        <div class="stat-lbl">Compromisso com qualidade</div>
      </div>
    </div>
  </div>
</section>

<!-- SERVIÇOS -->
<section id="servicos" style="max-width:100%;padding:100px 60px;background:var(--dark2);">
  <div class="servicos-header" style="max-width:1200px;margin:0 auto 60px;">
    <div class="sec-label">O que fazemos</div>
    <h2 class="sec-title" style="max-width:500px;">Cada serviço,<br>um resultado visível.</h2>
  </div>
  <div class="servicos-grid" style="max-width:1200px;margin:0 auto;">

    <div class="srv-card">
      <div class="srv-photo"><img src="FOTOS/fachadamdias.jpeg" alt="Fachada NEXA" loading="lazy"></div>
      <div class="srv-card-inner">
        <div class="srv-num">01</div>
        <div class="srv-icon"><svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="1"/><path d="M3 9h18M9 21V9M15 21V9"/></svg></div>
        <div class="srv-title">Fachadas</div>
        <div class="srv-desc">Fachadas com o projeto completo, do design à instalação. Sua <span style="color:#29B6F6;">fachada</span> fala por si antes do cliente entrar.</div>
        <div class="srv-tag">Alta visibilidade</div>
      </div>
    </div>

    <div class="srv-card">
      <div class="srv-photo"><img src="FOTOS/fachadamdias(2).jpeg" alt="Letras Caixa NEXA" loading="lazy"></div>
      <div class="srv-card-inner">
        <div class="srv-num">02</div>
        <div class="srv-icon"><svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="1"/><path d="M8 12h8M12 8v8"/></svg></div>
        <div class="srv-title">Letras Caixa</div>
        <div class="srv-desc">Letras em acrílico e ACM com iluminação em LED. Identidade forte, presença constante — de dia e de noite.</div>
        <div class="srv-tag">Com iluminação LED</div>
      </div>
    </div>

    <div class="srv-card">
      <div class="srv-photo"><img src="FOTOS/VESTUÁRIO INSTRUÇÕES.jpeg" alt="Adesivos e Plotagem NEXA" loading="lazy"></div>
      <div class="srv-card-inner">
        <div class="srv-num">03</div>
        <div class="srv-icon"><svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg></div>
        <div class="srv-title">Adesivos e Plotagem</div>
        <div class="srv-desc">Plotagem de alta resolução para vitrines, paredes, pisos e frotas. Comunicação visual que transforma qualquer superfície em ponto de atenção.</div>
        <div class="srv-tag">Alta resolução</div>
      </div>
    </div>

    <div class="srv-card">
      <div class="srv-photo"><img src="FOTOS/PAINEL + CRACHÁS.jpeg" alt="Lonas e Impressão NEXA" loading="lazy"></div>
      <div class="srv-card-inner">
        <div class="srv-num">04</div>
        <div class="srv-icon"><svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="1"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="M21 15l-5-5L5 21"/></svg></div>
        <div class="srv-title">Lonas e Impressão</div>
        <div class="srv-desc">Lonas para fachadas, eventos, banners e PDV. Impressão em larga escala com qualidade que chama atenção a quilômetros de distância.</div>
        <div class="srv-tag">Larga escala</div>
      </div>
    </div>

    <div class="srv-card">
      <div class="srv-photo"><img src="FOTOS/SINALIZAÇÃO HIGIENIZAÇÃO.jpeg" alt="Sinalização NEXA" loading="lazy"></div>
      <div class="srv-card-inner">
        <div class="srv-num">05</div>
        <div class="srv-icon"><svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7z"/><circle cx="12" cy="9" r="2.5"/></svg></div>
        <div class="srv-title">Sinalização</div>
        <div class="srv-desc">Placas, totens, sinalização interna e externa. Guiamos seus clientes e reforçamos sua identidade em cada ponto do espaço.</div>
        <div class="srv-tag">Interno e externo</div>
      </div>
    </div>

    <div class="srv-card" style="border-left:2px solid var(--cyan);">
      <div class="srv-photo"><img src="FOTOS/fachadamdias(3).jpeg" alt="Projeto Completo NEXA" loading="lazy"></div>
      <div class="srv-card-inner">
        <div class="srv-num">06</div>
        <div class="srv-icon" style="color:var(--cyan);"><svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/><polyline points="22 4 12 14.01 9 11.01"/></svg></div>
        <div class="srv-title">Projeto Completo</div>
        <div class="srv-desc">Do diagnóstico ao acabamento. Assumimos toda a comunicação visual do seu espaço — projeto, produção, instalação e suporte.</div>
        <div class="srv-tag" style="background:rgba(41,182,246,0.12);">Solução total</div>
      </div>
    </div>

  </div>
</section>

<!-- DIFERENCIAIS -->
<section id="diferenciais">
  <div class="dif-visual">
    <div class="sec-label">Por que a NEXA</div>
    <h2 class="sec-title">Não somos<br>a mais barata.<br>Somos a <span style="color:var(--cyan)">melhor escolha.</span></h2>
    <div class="accent-line"></div>
    <div class="quote-block">
      <div class="quote-text">Em <span class="c">7 segundos</span>, seu cliente já formou uma opinião sobre o seu negócio. Sua fachada está falando o que você quer?</div>
      <div class="quote-source">Universidade de Cincinnati — Signage Research</div>
    </div>
    <div class="quote-block">
      <div class="quote-text"><span class="c">76%</span> dos consumidores entram em um estabelecimento pela primeira vez baseados somente na comunicação visual.</div>
      <div class="quote-source">FedEx Office — Small Business Survey</div>
    </div>
  </div>
  <div>
    <div class="dif-list">
      <div class="dif-item">
        <div class="dif-ico"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg></div>
        <div class="dif-text">
          <div class="dif-title">Orçamento em menos de 1h</div>
          <div class="dif-desc">Você não fica esperando dias. Enviamos a proposta em até 1 hora após o contato.</div>
        </div>
      </div>
      <div class="dif-item">
        <div class="dif-ico"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M3 21h18M4 21V5a1 1 0 0 1 1-1h14a1 1 0 0 1 1 1v16M9 21V11h6v10"/></svg></div>
        <div class="dif-text">
          <div class="dif-title">Estrutura própria</div>
          <div class="dif-desc">Galpão, máquinas e equipe própria. Controlamos cada etapa da produção.</div>
        </div>
      </div>
      <div class="dif-item">
        <div class="dif-ico"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg></div>
        <div class="dif-text">
          <div class="dif-title">Atendimento especializado</div>
          <div class="dif-desc">Cada projeto tem um responsável dedicado. Você fala diretamente com quem produz.</div>
        </div>
      </div>
      <div class="dif-item">
        <div class="dif-ico"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/></svg></div>
        <div class="dif-text">
          <div class="dif-title">Do projeto à instalação</div>
          <div class="dif-desc">Criamos, produzimos e instalamos. Uma empresa, um processo, nenhuma dor de cabeça.</div>
        </div>
      </div>
      <div class="dif-item">
        <div class="dif-ico"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7z"/><circle cx="12" cy="9" r="2.5"/></svg></div>
        <div class="dif-text">
          <div class="dif-title">João Pessoa e região</div>
          <div class="dif-desc">Atendimento local, presença de verdade. Visitamos o espaço antes de propor qualquer solução.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CLIENTES -->
<section id="clientes" style="max-width:100%;padding:100px 60px;border-top:1px solid #0d0d0d;">
  <div class="clientes-header">
    <div class="sec-label" style="text-align:center;font-size:18px;letter-spacing:6px;">Quem confia na</div>
    <div style="text-align:center;margin:-10px 0 12px">
      <img src="FOTOS/NEXA FULLHD.png" alt="NEXA" style="height:480px;width:auto;display:inline-block;">
    </div>
    <h2 class="sec-title" style="text-align:center;max-width:500px;margin:0 auto 8px;">Marcas que já<br>são mais visíveis.</h2>
    <p style="font-size:13px;color:#fff;text-align:center;letter-spacing:1px;">Atendemos empresas que exigem qualidade e prazo.</p>
  </div>
  <div class="clientes-grid">
    <div class="cli-card">
      <div class="cli-name">GRUPO M. DIAS BRANCO</div>
      <div class="cli-seg" style="color:#fff;">Indústria Alimentícia</div>
      <div class="cli-badge">Cliente há anos</div>
    </div>
  </div>
</section>

<!-- CTA -->
<section id="cta" style="max-width:100%;padding:100px 60px;border-top:1px solid #0d0d0d;position:relative;overflow:hidden;background:radial-gradient(ellipse 60% 80% at 50% 100%, rgba(41,182,246,0.05) 0%, var(--dark) 70%);">
  <div class="cta-glow"></div>
  <div class="cta-x">X</div>
  <div class="cta-content">
    <div class="cta-tag">Peça seu orçamento agora</div>
    <h2 class="cta-title">Pronto para ser<br>visto de <span class="c">verdade?</span></h2>
    <p class="cta-sub">Entre em contato agora. Em menos de 1 hora você recebe a proposta personalizada para o seu negócio.</p>
    <a class="btn-primary" href="https://wa.me/5583991160827?text=Ol%C3%A1%2C+vim+pelo+site+e+quero+um+or%C3%A7amento!" style="font-size:12px;padding:18px 48px;">
      Falar no WhatsApp agora
    </a>
    <div class="cta-contacts">
      <a class="contact-chip" href="https://wa.me/5583991160827">
        <div class="chip-ico"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#29B6F6" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="5" y="2" width="14" height="20" rx="2"/><line x1="12" y1="18" x2="12.01" y2="18"/></svg></div>
        <div class="chip-info">
          <div class="chip-label">WhatsApp</div>
          <div class="chip-value">(83) 99116-0827</div>
        </div>
      </a>
      <a class="contact-chip" href="https://instagram.com/nexacv.jp" target="_blank">
        <div class="chip-ico"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#29B6F6" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="0.5" fill="#29B6F6"/></svg></div>
        <div class="chip-info">
          <div class="chip-label">Instagram</div>
          <div class="chip-value">@nexacv.jp</div>
        </div>
      </a>
      <div class="contact-chip">
        <div class="chip-ico">📍</div>
        <div class="chip-info">
          <div class="chip-label">Localização</div>
          <div class="chip-value">João Pessoa, PB</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="foot-logo"><img src="FOTOS/NEXA FULLHD.png" alt="NEXA" style="height:160px;width:auto;display:block;"></div>
  <div class="foot-info">
    NEXA Comunicação Visual · CNPJ 54.964.210/0001-29<br>
    João Pessoa – PB · (83) 99116-0827
  </div>
  <div class="foot-links">
    <a href="#sobre">Sobre</a>
    <a href="#servicos">Serviços</a>
    <a href="#cta">Contato</a>
    <a href="https://instagram.com/nexacv.jp" target="_blank">Instagram</a>
  </div>
</footer>

<script>
/* ── PARTICLE CANVAS ── */
const canvas = document.getElementById('hero-canvas');
const ctx = canvas.getContext('2d');
let W, H, particles = [];

function resize() {
  W = canvas.width = window.innerWidth;
  H = canvas.height = window.innerHeight;
}
resize();
window.addEventListener('resize', resize);

class P {
  constructor() { this.reset(); }
  reset() {
    this.x = Math.random() * W;
    this.y = Math.random() * H;
    this.vx = (Math.random() - .5) * .4;
    this.vy = (Math.random() - .5) * .4;
    this.r = Math.random() * 1.5 + .5;
    this.a = Math.random() * .6 + .1;
  }
  update() {
    this.x += this.vx; this.y += this.vy;
    if (this.x < 0 || this.x > W || this.y < 0 || this.y > H) this.reset();
  }
  draw() {
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.r, 0, Math.PI * 2);
    ctx.fillStyle = `rgba(0,200,240,${this.a})`;
    ctx.fill();
  }
}

for (let i = 0; i < 80; i++) particles.push(new P());

function loop() {
  ctx.clearRect(0, 0, W, H);
  particles.forEach(p => { p.update(); p.draw(); });
  for (let i = 0; i < particles.length; i++) {
    for (let j = i + 1; j < particles.length; j++) {
      const dx = particles[i].x - particles[j].x;
      const dy = particles[i].y - particles[j].y;
      const d = Math.sqrt(dx*dx + dy*dy);
      if (d < 120) {
        ctx.beginPath();
        ctx.moveTo(particles[i].x, particles[i].y);
        ctx.lineTo(particles[j].x, particles[j].y);
        ctx.strokeStyle = `rgba(0,200,240,${0.06 * (1 - d/120)})`;
        ctx.lineWidth = .5;
        ctx.stroke();
      }
    }
  }
  requestAnimationFrame(loop);
}
loop();

/* ── SCROLL ANIMATIONS ── */
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.style.opacity = '1';
      e.target.style.transform = 'translateY(0)';
    }
  });
}, { threshold: 0.1 });

document.querySelectorAll('.srv-card, .dif-item, .cli-card, .stat-box, .quote-block').forEach(el => {
  el.style.opacity = '0';
  el.style.transform = 'translateY(20px)';
  el.style.transition = 'opacity .6s ease, transform .6s ease';
  observer.observe(el);
});
</script>
</body>
</html>

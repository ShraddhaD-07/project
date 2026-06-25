<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Personal Cash Flow Predictor — README Presentation</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
<style>
:root{
  --bg:#0a0f1e;
  --bg-deep:#060912;
  --panel: rgba(255,255,255,0.04);
  --panel-border: rgba(255,255,255,0.09);
  --blue:#3b82f6;
  --blue-bright:#60a5fa;
  --emerald:#10d9a0;
  --emerald-deep:#059669;
  --amber:#fbbf24;
  --pink:#f472b6;
  --text:#e7ecf7;
  --text-dim:#8d97b8;
  --text-faint:#5b6486;
}
*{margin:0;padding:0;box-sizing:border-box;}
html,body{
  background:var(--bg);
  color:var(--text);
  font-family:'Inter',sans-serif;
  overflow:hidden;
  height:100vh;
  width:100vw;
}
::selection{background:var(--emerald);color:#06210e;}
.font-display{font-family:'Space Grotesk',sans-serif;}
.font-mono{font-family:'JetBrains Mono',monospace;}

/* ===== Deck shell ===== */
#deck{
  position:relative;
  height:100vh;
  width:100vw;
}
.slide{
  position:absolute;
  inset:0;
  width:100%;
  height:100%;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  padding:5vh 6vw;
  opacity:0;
  visibility:hidden;
  transform:scale(0.96) translateY(24px);
  transition:opacity .55s cubic-bezier(.22,.61,.36,1), transform .55s cubic-bezier(.22,.61,.36,1);
  background:
    radial-gradient(circle at 85% 8%, rgba(59,130,246,0.10), transparent 45%),
    radial-gradient(circle at 10% 92%, rgba(16,217,160,0.08), transparent 45%),
    var(--bg);
}
.slide.active{
  opacity:1;
  visibility:visible;
  transform:scale(1) translateY(0);
  z-index:5;
}
.slide.exit-left{ transform:scale(0.96) translateX(-40px); }
.slide.exit-right{ transform:scale(0.96) translateX(40px); }

.slide-inner{
  width:100%;
  max-width:1280px;
  height:100%;
  display:flex;
  flex-direction:column;
  justify-content:center;
}

/* ===== Chrome: progress, counter, nav ===== */
#progress-track{
  position:fixed;
  top:0; left:0; right:0;
  height:3px;
  background:rgba(255,255,255,0.06);
  z-index:100;
}
#progress-bar{
  height:100%;
  width:0%;
  background:linear-gradient(90deg,var(--blue),var(--emerald));
  box-shadow:0 0 12px rgba(16,217,160,0.6);
  transition:width .5s cubic-bezier(.22,.61,.36,1);
}
.slide-counter{
  position:fixed;
  top:28px; right:32px;
  font-family:'JetBrains Mono',monospace;
  font-size:13px;
  letter-spacing:0.12em;
  color:var(--text-dim);
  z-index:100;
  background:rgba(10,15,30,0.55);
  border:1px solid var(--panel-border);
  padding:7px 14px;
  border-radius:99px;
  backdrop-filter:blur(8px);
}
.slide-counter b{color:var(--emerald);font-weight:600;}
.brand-mark{
  position:fixed;
  top:28px; left:32px;
  z-index:100;
  display:flex;
  align-items:center;
  gap:8px;
  font-family:'Space Grotesk',sans-serif;
  font-size:13px;
  font-weight:600;
  letter-spacing:0.03em;
  color:var(--text-dim);
}
.brand-mark .dot{width:7px;height:7px;border-radius:50%;background:var(--emerald);box-shadow:0 0 10px var(--emerald);}

.nav-arrow{
  position:fixed;
  top:50%;
  transform:translateY(-50%);
  z-index:100;
  width:48px;height:48px;
  border-radius:50%;
  background:rgba(255,255,255,0.04);
  border:1px solid var(--panel-border);
  color:var(--text-dim);
  display:flex;align-items:center;justify-content:center;
  cursor:pointer;
  backdrop-filter:blur(8px);
  transition:all .25s ease;
  font-size:16px;
}
.nav-arrow:hover{background:rgba(16,217,160,0.12);color:var(--emerald);border-color:rgba(16,217,160,0.4);}
.nav-arrow.prev{left:24px;}
.nav-arrow.next{right:24px;}
.nav-arrow:disabled{opacity:0.25;cursor:not-allowed;}

#dots{
  position:fixed;
  bottom:22px; left:50%;
  transform:translateX(-50%);
  display:flex;
  gap:9px;
  z-index:100;
  background:rgba(10,15,30,0.55);
  border:1px solid var(--panel-border);
  padding:10px 16px;
  border-radius:99px;
  backdrop-filter:blur(8px);
}
.dot-btn{
  width:7px;height:7px;
  border-radius:50%;
  background:rgba(255,255,255,0.18);
  border:none;
  cursor:pointer;
  transition:all .3s ease;
  padding:0;
}
.dot-btn:hover{background:rgba(255,255,255,0.4);}
.dot-btn.active{
  width:22px;
  border-radius:99px;
  background:linear-gradient(90deg,var(--blue),var(--emerald));
}

/* ===== Shared typography ===== */
.eyebrow{
  font-family:'JetBrains Mono',monospace;
  font-size:12.5px;
  letter-spacing:0.18em;
  text-transform:uppercase;
  color:var(--emerald);
  display:flex;
  align-items:center;
  gap:10px;
  margin-bottom:18px;
}
.eyebrow::before{
  content:'';
  width:22px;height:1px;
  background:var(--emerald);
}
.gradient-text{
  background:linear-gradient(90deg, var(--blue-bright) 0%, var(--emerald) 50%, var(--blue-bright) 100%);
  background-size:200% auto;
  -webkit-background-clip:text;
  background-clip:text;
  -webkit-text-fill-color:transparent;
  animation:gradientShift 6s ease infinite;
}
@keyframes gradientShift{
  0%{background-position:0% center;}
  50%{background-position:100% center;}
  100%{background-position:0% center;}
}
.slide-title{
  font-family:'Space Grotesk',sans-serif;
  font-weight:700;
  font-size:clamp(2.1rem, 4vw, 3.4rem);
  line-height:1.05;
  letter-spacing:-0.01em;
  margin-bottom:14px;
}
.slide-sub{
  font-size:clamp(0.95rem,1.3vw,1.15rem);
  color:var(--text-dim);
  max-width:680px;
  line-height:1.55;
  margin-bottom:36px;
}
.glass{
  background:var(--panel);
  border:1px solid var(--panel-border);
  border-radius:18px;
  backdrop-filter:blur(14px);
  -webkit-backdrop-filter:blur(14px);
}
.section-header{margin-bottom:clamp(28px,4vh,46px);}

/* ===== Slide 0: HERO ===== */
#slide-0{padding:0;}
.hero-bg{
  position:absolute;inset:0;
  background:
    linear-gradient(180deg, rgba(6,9,18,0.55) 0%, rgba(6,9,18,0.86) 65%, var(--bg) 100%),
    url('https://images.unsplash.com/photo-1551288049-bebda4e38f71?q=80&w=1920&auto=format&fit=crop')
    center/cover no-repeat;
  z-index:0;
}
#particles{position:absolute;inset:0;z-index:1;overflow:hidden;pointer-events:none;}
.particle{
  position:absolute;
  border-radius:50%;
  background:var(--emerald);
  opacity:0.5;
  filter:blur(0.5px);
  animation:floatUp linear infinite;
}
@keyframes floatUp{
  0%{transform:translateY(0) translateX(0);opacity:0;}
  10%{opacity:0.6;}
  90%{opacity:0.4;}
  100%{transform:translateY(-100vh) translateX(20px);opacity:0;}
}
.hero-content{position:relative;z-index:2;text-align:center;max-width:920px;padding:0 24px;}
.hero-kicker{
  font-family:'JetBrains Mono',monospace;
  font-size:13px;
  letter-spacing:0.22em;
  text-transform:uppercase;
  color:var(--emerald);
  margin-bottom:26px;
  display:inline-flex;
  align-items:center;
  gap:10px;
  border:1px solid rgba(16,217,160,0.35);
  padding:8px 18px;
  border-radius:99px;
  background:rgba(16,217,160,0.07);
}
.hero-title{
  font-family:'Space Grotesk',sans-serif;
  font-weight:700;
  font-size:clamp(2.6rem,7vw,5.4rem);
  line-height:1.0;
  letter-spacing:-0.02em;
  margin-bottom:22px;
}
.hero-tagline{
  font-family:'Space Grotesk',sans-serif;
  font-size:clamp(1.1rem,2vw,1.5rem);
  font-weight:500;
  color:var(--text);
  margin-bottom:14px;
}
.hero-tagline .cursor{
  display:inline-block;width:3px;height:1.1em;background:var(--emerald);
  vertical-align:text-bottom;margin-left:4px;
  animation:blink 1s step-end infinite;
}
@keyframes blink{50%{opacity:0;}}
.hero-desc{
  font-size:1rem;
  color:var(--text-dim);
  max-width:560px;
  margin:0 auto 38px;
  line-height:1.6;
}
.hero-badges{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;}
.hero-badge{
  font-family:'JetBrains Mono',monospace;
  font-size:12px;
  padding:9px 16px;
  border-radius:99px;
  border:1px solid var(--panel-border);
  background:rgba(255,255,255,0.05);
  color:var(--text-dim);
  display:flex;align-items:center;gap:7px;
}
.hero-badge i{color:var(--emerald);}
.hero-scroll-hint{
  position:absolute;bottom:70px;left:50%;transform:translateX(-50%);
  z-index:2;font-size:11px;letter-spacing:0.15em;text-transform:uppercase;
  color:var(--text-faint);display:flex;flex-direction:column;align-items:center;gap:8px;
  font-family:'JetBrains Mono',monospace;
}
.hero-scroll-hint i{animation:bounce 1.8s ease-in-out infinite;color:var(--blue-bright);}
@keyframes bounce{0%,100%{transform:translateY(0);}50%{transform:translateY(7px);}}

/* ===== Generic grid helpers ===== */
.grid-3{display:grid;grid-template-columns:repeat(3,1fr);gap:22px;}
.grid-2{display:grid;grid-template-columns:repeat(2,1fr);gap:22px;}
.card{
  padding:28px 26px;
  position:relative;
  overflow:hidden;
  transition:transform .3s ease, border-color .3s ease;
}
.card:hover{transform:translateY(-4px);border-color:rgba(16,217,160,0.4);}
.card .icon-badge{
  width:46px;height:46px;border-radius:12px;
  display:flex;align-items:center;justify-content:center;
  font-size:18px;margin-bottom:16px;
}
.card h3{font-family:'Space Grotesk',sans-serif;font-size:1.05rem;font-weight:600;margin-bottom:9px;}
.card p{font-size:0.88rem;color:var(--text-dim);line-height:1.55;}

/* ===== Slide 1: Overview ===== */
.overview-quote{
  font-family:'Space Grotesk',sans-serif;
  font-size:clamp(1.3rem,2.4vw,1.9rem);
  font-weight:600;
  line-height:1.4;
  margin-bottom:30px;
  max-width:780px;
}
.overview-quote .gradient-text{display:inline;}
.icon-blue{background:rgba(59,130,246,0.14);color:var(--blue-bright);}
.icon-emerald{background:rgba(16,217,160,0.14);color:var(--emerald);}
.icon-amber{background:rgba(251,191,36,0.14);color:var(--amber);}
.icon-pink{background:rgba(244,114,182,0.14);color:var(--pink);}

/* ===== Slide 2: Problem ===== */
.problem-card{border-color:rgba(248,113,113,0.18);}
.problem-card .icon-badge{background:rgba(248,113,113,0.13);color:#f87171;}
.problem-flow{display:flex;align-items:center;justify-content:center;gap:14px;margin-top:30px;flex-wrap:wrap;}
.flow-result{
  text-align:center;font-family:'Space Grotesk',sans-serif;font-weight:600;
  color:var(--pink);font-size:0.95rem;
  padding:16px 22px;border:1px solid rgba(244,114,182,0.35);border-radius:14px;
  background:rgba(244,114,182,0.06);
}

/* ===== Slide 3: Why it matters ===== */
.principle-card{text-align:left;}
.principle-num{
  font-family:'JetBrains Mono',monospace;
  font-size:0.75rem;color:var(--text-faint);letter-spacing:0.1em;margin-bottom:14px;
}

/* ===== Slide 4: Features ===== */
.feat-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:16px;}
.feat-item{
  display:flex;gap:16px;padding:20px 22px;align-items:flex-start;
}
.feat-item .icon-badge{flex-shrink:0;margin-bottom:0;width:42px;height:42px;font-size:16px;}
.feat-item h3{font-size:0.98rem;margin-bottom:6px;}
.feat-item p{font-size:0.82rem;}

/* ===== Slide 5: Demo Walkthrough (stepper) ===== */
.stepper{position:relative;padding-left:4px;}
.stepper::before{
  content:'';position:absolute;left:23px;top:14px;bottom:14px;width:2px;
  background:linear-gradient(180deg,var(--blue),var(--emerald));
  opacity:0.4;
}
.step-row{display:flex;gap:22px;align-items:flex-start;position:relative;padding:13px 0;}
.step-num{
  width:46px;height:46px;border-radius:50%;flex-shrink:0;
  display:flex;align-items:center;justify-content:center;
  font-family:'Space Grotesk',sans-serif;font-weight:700;font-size:1rem;
  background:var(--bg);border:2px solid var(--emerald);color:var(--emerald);
  z-index:2;
}
.step-body h3{font-family:'Space Grotesk',sans-serif;font-size:1rem;font-weight:600;margin-bottom:4px;}
.step-body p{font-size:0.85rem;color:var(--text-dim);line-height:1.5;max-width:560px;}

/* ===== Slide 6: Architecture ===== */
.arch-wrap{display:flex;justify-content:center;}
.arch-svg-box{width:100%;max-width:980px;}
.arch-principle{
  text-align:center;font-size:0.85rem;color:var(--text-dim);max-width:680px;
  margin:22px auto 0;line-height:1.55;
}
.arch-principle b{color:var(--emerald);}

/* ===== Slide 7: Tech stack ===== */
.tech-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:14px;}
.tech-chip{
  display:flex;flex-direction:column;align-items:center;gap:10px;
  padding:20px 10px;text-align:center;
}
.tech-chip img{width:30px;height:30px;}
.tech-chip span{font-size:0.74rem;color:var(--text-dim);font-family:'JetBrains Mono',monospace;}
.tech-layer-label{
  font-family:'JetBrains Mono',monospace;font-size:0.7rem;letter-spacing:0.12em;
  text-transform:uppercase;color:var(--text-faint);margin-bottom:10px;margin-top:6px;
}

/* ===== Slide 8: AI components ===== */
.ai-card{display:flex;flex-direction:column;}
.ai-card .icon-badge{width:52px;height:52px;font-size:20px;border-radius:14px;}

/* ===== Slide 9: Metrics ===== */
.metric-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:18px;}
.metric-card{text-align:center;padding:32px 18px;}
.metric-value{
  font-family:'Space Grotesk',sans-serif;font-weight:700;
  font-size:clamp(2rem,4vw,2.7rem);
  background:linear-gradient(135deg,var(--blue-bright),var(--emerald));
  -webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;
  margin-bottom:6px;
}
.metric-label{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:0.95rem;margin-bottom:8px;}
.metric-desc{font-size:0.78rem;color:var(--text-dim);line-height:1.5;}

/* ===== Slide 10: Challenges ===== */
.challenge-card{border-color:rgba(251,146,60,0.18);}
.challenge-card .icon-badge{background:rgba(251,146,60,0.13);color:#fb923c;}
.challenge-resolve{
  display:flex;align-items:center;gap:8px;margin-top:14px;font-size:0.78rem;
  color:var(--emerald);font-family:'JetBrains Mono',monospace;
}

/* ===== Slide 11: Lessons ===== */
.lesson-card{text-align:left;position:relative;}
.lesson-quote-mark{
  font-family:'Space Grotesk',sans-serif;font-size:2.6rem;color:rgba(16,217,160,0.25);
  position:absolute;top:10px;right:20px;line-height:1;
}

/* ===== Slide 12: Future ===== */
.roadmap-list{display:flex;flex-direction:column;gap:14px;}
.roadmap-item{
  display:flex;align-items:center;gap:20px;padding:20px 26px;
}
.roadmap-item .icon-badge{margin-bottom:0;flex-shrink:0;}
.roadmap-item h3{font-size:0.95rem;margin-bottom:4px;}
.roadmap-item p{font-size:0.82rem;}

/* ===== Slide 13: Thank you ===== */
#slide-13{background:radial-gradient(circle at 50% 50%, rgba(16,217,160,0.10), transparent 60%), var(--bg);}
.thanks-content{text-align:center;position:relative;}
.thanks-glow{
  position:absolute;top:50%;left:50%;width:520px;height:520px;
  transform:translate(-50%,-50%);
  background:radial-gradient(circle, rgba(16,217,160,0.18), transparent 70%);
  filter:blur(20px);z-index:-1;
  animation:pulseGlow 4s ease-in-out infinite;
}
@keyframes pulseGlow{0%,100%{opacity:0.6;transform:translate(-50%,-50%) scale(1);}50%{opacity:1;transform:translate(-50%,-50%) scale(1.08);}}
.thanks-title{
  font-family:'Space Grotesk',sans-serif;font-weight:700;
  font-size:clamp(2.4rem,5vw,4rem);margin-bottom:18px;
}
.thanks-sub{font-size:1.05rem;color:var(--text-dim);margin-bottom:8px;}
.thanks-team{
  font-family:'JetBrains Mono',monospace;font-size:0.85rem;letter-spacing:0.1em;
  color:var(--emerald);text-transform:uppercase;margin-top:30px;
}

/* counters fade-in on enter */
[data-counter]{display:inline-block;}

/* responsive scaling */
@media (max-width: 900px){
  .grid-3,.feat-grid,.tech-grid,.metric-grid{grid-template-columns:repeat(2,1fr)!important;}
}
</style>
</head>
<body>

<div id="progress-track"><div id="progress-bar"></div></div>
<div class="brand-mark"><span class="dot"></span> CASH&nbsp;FLOW&nbsp;PREDICTOR</div>
<div class="slide-counter"><b id="counter-current">01</b> / <span id="counter-total">14</span></div>

<button class="nav-arrow prev" id="prevBtn" aria-label="Previous slide"><i class="fa-solid fa-chevron-left"></i></button>
<button class="nav-arrow next" id="nextBtn" aria-label="Next slide"><i class="fa-solid fa-chevron-right"></i></button>

<div id="deck">

<!-- ============ SLIDE 0 — HERO ============ -->
<section class="slide active" id="slide-0">
  <div class="hero-bg"></div>
  <div id="particles"></div>
  <div class="hero-content">
    <div class="hero-kicker"><i class="fa-solid fa-bolt"></i> README, REIMAGINED AS A LIVE PITCH</div>
    <h1 class="hero-title">Personal <span class="gradient-text">Cash&nbsp;Flow</span><br>Predictor</h1>
    <p class="hero-tagline">Know your money before it moves<span class="cursor"></span></p>
    <p class="hero-desc">AI-powered forecasting, spending intelligence &amp; savings recommendations — built to turn financial anxiety into financial confidence.</p>
    <div class="hero-badges">
      <span class="hero-badge"><i class="fa-solid fa-circle-check"></i> Status: Active</span>
      <span class="hero-badge"><i class="fa-brands fa-python"></i> Python + React</span>
      <span class="hero-badge"><i class="fa-solid fa-chart-line"></i> Prophet Forecasting</span>
      <span class="hero-badge"><i class="fa-solid fa-users"></i> Team Project</span>
    </div>
  </div>
  <div class="hero-scroll-hint">Use → to begin <i class="fa-solid fa-chevron-down"></i></div>
</section>

<!-- ============ SLIDE 1 — PROJECT OVERVIEW ============ -->
<section class="slide" id="slide-1">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-crosshairs"></i> Project Overview</div>
      <h2 class="slide-title">Most people can't answer<br>one <span class="gradient-text">simple question</span>.</h2>
    </div>
    <p class="overview-quote">"<span class="gradient-text">Will I have enough money next month?</span>" — banking apps show what already happened. Spreadsheets are manual and go stale fast. Nothing connects past transactions to a forward-looking view of cash flow.</p>
    <div class="grid-3">
      <div class="card glass">
        <div class="icon-badge icon-blue"><i class="fa-solid fa-file-arrow-up"></i></div>
        <h3>Upload &amp; Classify</h3>
        <p>Upload a bank statement and the system automatically classifies every transaction.</p>
      </div>
      <div class="card glass">
        <div class="icon-badge icon-emerald"><i class="fa-solid fa-chart-area"></i></div>
        <h3>90-Day Forecast</h3>
        <p>A forward-looking balance forecast is built automatically from your real transaction history.</p>
      </div>
      <div class="card glass">
        <div class="icon-badge icon-amber"><i class="fa-solid fa-lightbulb"></i></div>
        <h3>Plain-Language Insight</h3>
        <p>Surfaces plain-language insights and savings opportunities — closing the gap between data and confidence.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 2 — PROBLEM STATEMENT ============ -->
<section class="slide" id="slide-2">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-triangle-exclamation"></i> Problem Statement</div>
      <h2 class="slide-title">Three gaps that quietly<br>cause <span class="gradient-text">financial anxiety</span>.</h2>
    </div>
    <div class="grid-3">
      <div class="card glass problem-card">
        <div class="icon-badge"><i class="fa-solid fa-money-bill-trend-down"></i></div>
        <h3>No Warning</h3>
        <p>Low-balance surprises arrive before the next paycheck, with no warning.</p>
      </div>
      <div class="card glass problem-card">
        <div class="icon-badge"><i class="fa-solid fa-arrows-spin"></i></div>
        <h3>No Visibility</h3>
        <p>Recurring expenses and spending habits go unnoticed month after month.</p>
      </div>
      <div class="card glass problem-card">
        <div class="icon-badge"><i class="fa-solid fa-rotate-left"></i></div>
        <h3>Reactive, Not Proactive</h3>
        <p>Decisions get made after the money is already gone, not before.</p>
      </div>
    </div>
    <div class="problem-flow">
      <i class="fa-solid fa-arrow-down" style="color:var(--text-faint);font-size:14px;"></i>
      <div class="flow-result"><i class="fa-solid fa-face-frown"></i>&nbsp; Financial Anxiety &amp; Uncertainty</div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 3 — WHY IT MATTERS ============ -->
<section class="slide" id="slide-3">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-star"></i> Why It Matters</div>
      <h2 class="slide-title">Financial stress is rarely<br>about <span class="gradient-text">income alone</span>.</h2>
      <p class="slide-sub">It's about uncertainty. A forward-looking view turns financial anxiety into financial confidence.</p>
    </div>
    <div class="grid-3">
      <div class="card glass principle-card">
        <div class="principle-num">PRINCIPLE — 01</div>
        <div class="icon-badge icon-blue"><i class="fa-solid fa-stopwatch"></i></div>
        <h3>Act Before It's Too Late</h3>
        <p>Forecasting low balances days in advance gives people time to adjust spending, not just react after an overdraft.</p>
      </div>
      <div class="card glass principle-card">
        <div class="principle-num">PRINCIPLE — 02</div>
        <div class="icon-badge icon-emerald"><i class="fa-solid fa-calculator"></i></div>
        <h3>Save Without the Spreadsheet</h3>
        <p>Automated pattern detection finds savings opportunities people would never spot manually.</p>
      </div>
      <div class="card glass principle-card">
        <div class="principle-num">PRINCIPLE — 03</div>
        <div class="icon-badge icon-amber"><i class="fa-solid fa-earth-americas"></i></div>
        <h3>Built for Real Life</h3>
        <p>Supports multiple currencies and real bank statement formats, not just toy demo data.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 4 — FEATURES ============ -->
<section class="slide" id="slide-4">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-rocket"></i> Features</div>
      <h2 class="slide-title">Everything between a<br><span class="gradient-text">statement</span> and a <span class="gradient-text">decision</span>.</h2>
    </div>
    <div class="feat-grid">
      <div class="card glass feat-item">
        <div class="icon-badge icon-blue"><i class="fa-solid fa-file-import"></i></div>
        <div><h3>Multi-format Upload</h3><p>Drag-and-drop CSV, Excel, or PDF bank statements, with instant column validation.</p></div>
      </div>
      <div class="card glass feat-item">
        <div class="icon-badge icon-emerald"><i class="fa-solid fa-tags"></i></div>
        <div><h3>Auto-Classification</h3><p>Every transaction tagged Incoming/Outgoing and sorted into 11 expense categories.</p></div>
      </div>
      <div class="card glass feat-item">
        <div class="icon-badge icon-amber"><i class="fa-solid fa-gauge-high"></i></div>
        <div><h3>Real-time Dashboard</h3><p>KPI cards, inflow vs. outflow charts, and category breakdowns.</p></div>
      </div>
      <div class="card glass feat-item">
        <div class="icon-badge icon-pink"><i class="fa-solid fa-table-list"></i></div>
        <div><h3>Pagination Support</h3><p>Large transaction datasets split into manageable pages for faster, smoother browsing.</p></div>
      </div>
      <div class="card glass feat-item">
        <div class="icon-badge icon-blue"><i class="fa-solid fa-chart-line"></i></div>
        <div><h3>90-Day Forecasting</h3><p>Balance projections with confidence bands, supporting 30/90-day horizons.</p></div>
      </div>
      <div class="card glass feat-item">
        <div class="icon-badge icon-emerald"><i class="fa-solid fa-sliders"></i></div>
        <div><h3>What-If Simulation</h3><p>Sliders to model income changes, expense cuts, or one-time purchases live.</p></div>
      </div>
      <div class="card glass feat-item">
        <div class="icon-badge icon-amber"><i class="fa-solid fa-bell"></i></div>
        <div><h3>Alerts &amp; Recommendations</h3><p>Automatic low-balance warnings and AI-generated savings recommendations.</p></div>
      </div>
      <div class="card glass feat-item">
        <div class="icon-badge icon-pink"><i class="fa-solid fa-globe"></i></div>
        <div><h3>Multi-currency Support</h3><p>INR, USD, and EUR with live conversion.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 5 — DEMO WALKTHROUGH ============ -->
<section class="slide" id="slide-5">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-film"></i> Demo Walkthrough</div>
      <h2 class="slide-title">Six stages, raw statement<br>to <span class="gradient-text">actionable insight</span>.</h2>
    </div>
    <div class="stepper">
      <div class="step-row">
        <div class="step-num">1</div>
        <div class="step-body"><h3>Upload</h3><p>Drag-and-drop a CSV, Excel, or PDF bank statement; columns are validated instantly.</p></div>
      </div>
      <div class="step-row">
        <div class="step-num">2</div>
        <div class="step-body"><h3>Auto-Classify</h3><p>Every transaction is tagged Incoming/Outgoing and sorted into 11 expense categories.</p></div>
      </div>
      <div class="step-row">
        <div class="step-num">3</div>
        <div class="step-body"><h3>Dashboard</h3><p>KPI cards, inflow vs. outflow charts, and a category breakdown update in real time.</p></div>
      </div>
      <div class="step-row">
        <div class="step-num">4</div>
        <div class="step-body"><h3>Forecast</h3><p>A 90-day forecast with confidence bands shows where the balance is headed.</p></div>
      </div>
      <div class="step-row">
        <div class="step-num">5</div>
        <div class="step-body"><h3>What-If</h3><p>Sliders simulate income changes, expense cuts, or one-time purchases live.</p></div>
      </div>
      <div class="step-row">
        <div class="step-num">6</div>
        <div class="step-body"><h3>Alerts &amp; Recommendations</h3><p>Low-balance warnings and AI savings recommendations surface automatically.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 6 — ARCHITECTURE ============ -->
<section class="slide" id="slide-6">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-sitemap"></i> Architecture</div>
      <h2 class="slide-title">A clean pipeline, built on<br><span class="gradient-text">structured data</span>.</h2>
    </div>
    <div class="arch-wrap">
      <div class="arch-svg-box">
        <svg viewBox="0 0 980 230" xmlns="http://www.w3.org/2000/svg" style="width:100%;height:auto;">
          <defs>
            <linearGradient id="archGrad" x1="0%" y1="0%" x2="100%" y2="0%">
              <stop offset="0%" stop-color="#3b82f6"/>
              <stop offset="100%" stop-color="#10d9a0"/>
            </linearGradient>
            <marker id="arrowHead" markerWidth="9" markerHeight="9" refX="6" refY="4" orient="auto">
              <path d="M0,0 L8,4 L0,8 Z" fill="#10d9a0"/>
            </marker>
          </defs>
          <!-- nodes -->
          <g font-family="Space Grotesk, sans-serif" font-size="13" font-weight="600">
            <rect x="10" y="70" width="150" height="90" rx="14" fill="rgba(59,130,246,0.10)" stroke="#3b82f6" stroke-width="1.5"/>
            <text x="85" y="105" fill="#e7ecf7" text-anchor="middle">Upload</text>
            <text x="85" y="124" fill="#8d97b8" font-size="10.5" font-weight="400" text-anchor="middle">CSV / Excel / PDF</text>

            <rect x="195" y="70" width="150" height="90" rx="14" fill="rgba(16,217,160,0.10)" stroke="#10d9a0" stroke-width="1.5"/>
            <text x="270" y="98" fill="#e7ecf7" text-anchor="middle">Classification</text>
            <text x="270" y="116" fill="#e7ecf7" text-anchor="middle">Agent</text>
            <text x="270" y="135" fill="#8d97b8" font-size="10.5" font-weight="400" text-anchor="middle">11 categories</text>

            <rect x="380" y="20" width="150" height="80" rx="14" fill="rgba(251,191,36,0.10)" stroke="#fbbf24" stroke-width="1.5"/>
            <text x="455" y="55" fill="#e7ecf7" text-anchor="middle">Forecasting</text>
            <text x="455" y="73" fill="#e7ecf7" text-anchor="middle">Agent</text>

            <rect x="380" y="130" width="150" height="80" rx="14" fill="rgba(244,114,182,0.10)" stroke="#f472b6" stroke-width="1.5"/>
            <text x="455" y="165" fill="#e7ecf7" text-anchor="middle">Recommendation</text>
            <text x="455" y="183" fill="#e7ecf7" text-anchor="middle">Agent</text>

            <rect x="565" y="70" width="150" height="90" rx="14" fill="rgba(59,130,246,0.10)" stroke="#3b82f6" stroke-width="1.5"/>
            <text x="640" y="98" fill="#e7ecf7" text-anchor="middle">API Layer</text>
            <text x="640" y="116" fill="#e7ecf7" text-anchor="middle">(FastAPI)</text>
            <text x="640" y="135" fill="#8d97b8" font-size="10.5" font-weight="400" text-anchor="middle">collaboration</text>

            <rect x="750" y="70" width="150" height="90" rx="14" fill="rgba(16,217,160,0.10)" stroke="#10d9a0" stroke-width="1.5"/>
            <text x="825" y="98" fill="#e7ecf7" text-anchor="middle">Insight Service</text>
            <text x="825" y="116" fill="#e7ecf7" text-anchor="middle">(AI)</text>
            <text x="825" y="135" fill="#8d97b8" font-size="10.5" font-weight="400" text-anchor="middle">dashboard + alerts</text>
          </g>
          <!-- arrows -->
          <path d="M160,115 L195,115" stroke="url(#archGrad)" stroke-width="2" fill="none" marker-end="url(#arrowHead)"/>
          <path d="M345,100 C360,80 365,70 380,60" stroke="url(#archGrad)" stroke-width="2" fill="none" marker-end="url(#arrowHead)"/>
          <path d="M345,130 C360,150 365,160 380,170" stroke="url(#archGrad)" stroke-width="2" fill="none" marker-end="url(#arrowHead)"/>
          <path d="M530,60 C548,55 550,90 565,100" stroke="url(#archGrad)" stroke-width="2" fill="none" marker-end="url(#arrowHead)"/>
          <path d="M530,170 C548,175 550,130 565,120" stroke="url(#archGrad)" stroke-width="2" fill="none" marker-end="url(#arrowHead)"/>
          <path d="M715,115 L750,115" stroke="url(#archGrad)" stroke-width="2" fill="none" marker-end="url(#arrowHead)"/>
        </svg>
      </div>
    </div>
    <p class="arch-principle"><b>Design principle:</b> classify every transaction (incoming/outgoing + category) automatically on upload, so downstream forecasting and recommendations always operate on clean, structured data. The system follows a <b>multi-agent architecture</b> — specialized agents collaborate through the API layer — and is built using <b>SDD (Spec-Driven Development)</b>, where requirements and behavior are defined before implementation for consistency and scalability.</p>
  </div>
</section>

<!-- ============ SLIDE 7 — TECH STACK ============ -->
<section class="slide" id="slide-7">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-layer-group"></i> Technology Stack</div>
      <h2 class="slide-title">Built on a <span class="gradient-text">production-grade</span> toolchain.</h2>
    </div>
    <div class="tech-layer-label">Frontend</div>
    <div class="tech-grid">
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/react/60a5fa" alt="React"><span>React</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/tailwindcss/10d9a0" alt="Tailwind CSS"><span>Tailwind CSS</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/shadcnui/e7ecf7" alt="shadcn/ui"><span>shadcn/ui</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/lovable/f472b6" alt="Lovable"><span>Lovable.dev</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/postman/fb923c" alt="Postman"><span>Postman</span></div>
    </div>
    <div class="tech-layer-label">Backend &amp; Data</div>
    <div class="tech-grid">
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/python/60a5fa" alt="Python"><span>Python</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/fastapi/10d9a0" alt="FastAPI"><span>FastAPI</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/postgresql/60a5fa" alt="PostgreSQL"><span>PostgreSQL</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/uvicorn/10d9a0" alt="Uvicorn"><span>Uvicorn</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/openai/e7ecf7" alt="OpenAI API"><span>OpenAI API</span></div>
    </div>
    <div class="tech-layer-label">Processing, Testing &amp; Deployment</div>
    <div class="tech-grid">
      <div class="card glass tech-chip"><i class="fa-solid fa-file-pdf" style="font-size:30px;color:#fb923c;"></i><span>PDFPlumber</span></div>
      <div class="card glass tech-chip"><i class="fa-solid fa-chart-line" style="font-size:30px;color:#10d9a0;"></i><span>Prophet</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/playwright/e7ecf7" alt="Playwright"><span>Playwright</span></div>
      <div class="card glass tech-chip"><img src="https://cdn.simpleicons.org/render/46e3b7" alt="Render"><span>Render</span></div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 8 — AI COMPONENTS ============ -->
<section class="slide" id="slide-8">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-robot"></i> AI Components</div>
      <h2 class="slide-title">Four engines behind the<br><span class="gradient-text">intelligence layer</span>.</h2>
    </div>
    <div class="grid-2">
      <div class="card glass ai-card">
        <div class="icon-badge icon-blue"><i class="fa-solid fa-chart-line"></i></div>
        <h3>Forecasting Engine</h3>
        <p>Uses Prophet / ARIMA time-series models to project account balances 30 or 90 days into the future, with confidence bands that widen further out and narrow as new transactions arrive.</p>
      </div>
      <div class="card glass ai-card">
        <div class="icon-badge icon-emerald"><i class="fa-solid fa-comments"></i></div>
        <h3>AI Insight Service</h3>
        <p>Uses OpenAI APIs to generate plain-language explanations of forecasts and personalized savings recommendations, so users understand why a forecast looks the way it does, not just the number itself.</p>
      </div>
      <div class="card glass ai-card">
        <div class="icon-badge icon-amber"><i class="fa-solid fa-tags"></i></div>
        <h3>Transaction Classification</h3>
        <p>Automatically extracts and classifies every transaction into one of 11 expense categories on upload, forming the structured data foundation that forecasting and AI insights are built on.</p>
      </div>
      <div class="card glass ai-card">
        <div class="icon-badge icon-pink"><i class="fa-solid fa-sliders"></i></div>
        <h3>Scenario Simulator</h3>
        <p>Uses natural-language inputs to evaluate "what-if" financial scenarios, generating an updated cash flow forecast, 90-day impact analysis, risk assessment, and actionable recommendations.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 9 — METRICS ============ -->
<section class="slide" id="slide-9">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-chart-simple"></i> Model Performance &amp; Metrics</div>
      <h2 class="slide-title">Forecast accuracy, measured<br>in <span class="gradient-text">four error metrics</span>.</h2>
      <p class="slide-sub">Model performance is evaluated using forecast accuracy, classification quality, prediction confidence intervals, and validation against historical transaction data.</p>
    </div>
    <div class="metric-grid">
      <div class="card glass metric-card">
        <div class="metric-value" data-counter data-target="0" data-suffix="">MAE</div>
        <div class="metric-label">Mean Absolute Error</div>
        <div class="metric-desc">Average magnitude of forecast errors, in the same units as the balance itself.</div>
      </div>
      <div class="card glass metric-card">
        <div class="metric-value">RMSE</div>
        <div class="metric-label">Root Mean Squared Error</div>
        <div class="metric-desc">Penalizes larger forecast misses more heavily than small ones.</div>
      </div>
      <div class="card glass metric-card">
        <div class="metric-value">MSE</div>
        <div class="metric-label">Mean Squared Error</div>
        <div class="metric-desc">Squared error term used internally for model tuning and comparison.</div>
      </div>
      <div class="card glass metric-card">
        <div class="metric-value">MASE</div>
        <div class="metric-label">Mean Absolute Scaled Error</div>
        <div class="metric-desc">Compares forecast error against a naive baseline, making accuracy comparable across users with different spending scales.</div>
      </div>
    </div>
    <div style="margin-top:30px;">
      <svg viewBox="0 0 900 160" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:900px;display:block;margin:0 auto;">
        <defs>
          <linearGradient id="bandGrad" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stop-color="#10d9a0" stop-opacity="0.28"/>
            <stop offset="100%" stop-color="#10d9a0" stop-opacity="0.02"/>
          </linearGradient>
        </defs>
        <path d="M20,120 C150,110 250,80 350,70 C500,55 650,40 880,15 L880,55 C650,80 500,95 350,110 C250,120 150,140 20,150 Z" fill="url(#bandGrad)"/>
        <path d="M20,135 C150,125 250,100 350,90 C500,75 650,60 880,35" stroke="#3b82f6" stroke-width="2" fill="none" stroke-dasharray="5,5" opacity="0.6"/>
        <path d="M20,135 C150,118 250,84 350,75 C500,60 650,42 880,18" stroke="#10d9a0" stroke-width="3" fill="none"/>
        <text x="30" y="20" fill="#8d97b8" font-size="11" font-family="JetBrains Mono, monospace">90-day balance forecast — confidence band</text>
      </svg>
    </div>
    <p class="arch-principle"><b>Evaluation approach:</b> forecast accuracy is validated by comparing predicted vs. actual balances on held-out historical weeks; classification accuracy is checked against manually labeled sample transactions.</p>
  </div>
</section>

<!-- ============ SLIDE 10 — CHALLENGES ============ -->
<section class="slide" id="slide-10">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-mountain"></i> Challenges Faced</div>
      <h2 class="slide-title">Four hard problems,<br><span class="gradient-text">solved deliberately</span>.</h2>
    </div>
    <div class="grid-2">
      <div class="card glass challenge-card">
        <div class="icon-badge"><i class="fa-solid fa-file-circle-exclamation"></i></div>
        <h3>Messy Real-World Statements</h3>
        <p>Bank PDFs vary wildly in layout; parsing had to handle inconsistent columns, merged fields, and OCR-prone formats.</p>
        <div class="challenge-resolve"><i class="fa-solid fa-check"></i> Robust parsing layer</div>
      </div>
      <div class="card glass challenge-card">
        <div class="icon-badge"><i class="fa-solid fa-arrows-rotate"></i></div>
        <h3>Recurring Expense Detection</h3>
        <p>Distinguishing genuine recurring charges (rent, SIP, subscriptions) from coincidentally similar amounts needed careful rule design.</p>
        <div class="challenge-resolve"><i class="fa-solid fa-check"></i> Careful rule design</div>
      </div>
      <div class="card glass challenge-card">
        <div class="icon-badge"><i class="fa-solid fa-chart-line"></i></div>
        <h3>Forecast Uncertainty</h3>
        <p>Short transaction histories early on made early forecasts noisy; confidence intervals had to be wide and clearly communicated.</p>
        <div class="challenge-resolve"><i class="fa-solid fa-check"></i> Wide, clear confidence intervals</div>
      </div>
      <div class="card glass challenge-card">
        <div class="icon-badge"><i class="fa-solid fa-globe"></i></div>
        <h3>Multi-currency Consistency</h3>
        <p>Keeping every KPI, chart, and recommendation in sync across INR, USD, and EUR without mixed symbols took careful state management.</p>
        <div class="challenge-resolve"><i class="fa-solid fa-check"></i> Careful state management</div>
      </div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 11 — WHAT WE LEARNED ============ -->
<section class="slide" id="slide-11">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-graduation-cap"></i> What We Learned</div>
      <h2 class="slide-title">Three takeaways worth<br>carrying into the <span class="gradient-text">next build</span>.</h2>
    </div>
    <div class="grid-3">
      <div class="card glass lesson-card">
        <span class="lesson-quote-mark">"</span>
        <div class="icon-badge icon-blue"><i class="fa-solid fa-broom"></i></div>
        <h3>Clean Data Beats Clever Models</h3>
        <p>Time spent on robust parsing and classification paid off more than tuning the forecasting model itself.</p>
      </div>
      <div class="card glass lesson-card">
        <span class="lesson-quote-mark">"</span>
        <div class="icon-badge icon-emerald"><i class="fa-solid fa-handshake"></i></div>
        <h3>Explainability Builds Trust</h3>
        <p>Users trust a forecast more when it comes with a plain-language reason, not just a number.</p>
      </div>
      <div class="card glass lesson-card">
        <span class="lesson-quote-mark">"</span>
        <div class="icon-badge icon-amber"><i class="fa-solid fa-earth-asia"></i></div>
        <h3>Design for Real Currencies, Not Demos</h3>
        <p>Building multi-currency support from day one avoided a costly retrofit later.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 12 — FUTURE ENHANCEMENTS ============ -->
<section class="slide" id="slide-12">
  <div class="slide-inner">
    <div class="section-header">
      <div class="eyebrow"><i class="fa-solid fa-road"></i> Future Enhancements</div>
      <h2 class="slide-title">What comes after<br>the <span class="gradient-text">first forecast</span>.</h2>
    </div>
    <div class="roadmap-list">
      <div class="card glass roadmap-item">
        <div class="icon-badge icon-blue"><i class="fa-solid fa-comment-dots"></i></div>
        <div><h3>Conversational Financial Assistant</h3><p>Let users ask questions in plain English and get grounded answers from their own data.</p></div>
      </div>
      <div class="card glass roadmap-item">
        <div class="icon-badge icon-emerald"><i class="fa-solid fa-triangle-exclamation"></i></div>
        <div><h3>Anomaly Detection</h3><p>Flag unusual transactions automatically, beyond simple low-balance alerts.</p></div>
      </div>
      <div class="card glass roadmap-item">
        <div class="icon-badge icon-amber"><i class="fa-solid fa-building-columns"></i></div>
        <div><h3>Multi-account Support</h3><p>Aggregate checking, savings, and credit accounts into one unified forecast.</p></div>
      </div>
      <div class="card glass roadmap-item">
        <div class="icon-badge icon-pink"><i class="fa-solid fa-bullseye"></i></div>
        <div><h3>Goal-based Savings Plans</h3><p>Let users set a target (e.g. a trip or down payment) and get a tailored plan to reach it.</p></div>
      </div>
      <div class="card glass roadmap-item">
        <div class="icon-badge icon-blue"><i class="fa-solid fa-rotate"></i></div>
        <div><h3>Subscription Optimization</h3><p>Surface underused subscriptions and suggest cancellations automatically.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ============ SLIDE 13 — THANK YOU ============ -->
<section class="slide" id="slide-13">
  <div class="thanks-content">
    <div class="thanks-glow"></div>
    <div class="hero-kicker"><i class="fa-solid fa-sparkles"></i> END OF README</div>
    <h2 class="thanks-title"><span class="gradient-text">Thank You</span></h2>
    <p class="thanks-sub">Personal Cash Flow Predictor — Team Project</p>
    <p class="hero-desc">Built to turn financial anxiety into financial confidence.</p>
    <div class="thanks-team"><i class="fa-solid fa-star"></i> &nbsp;Know your money before it moves&nbsp; <i class="fa-solid fa-star"></i></div>
  </div>
</section>

</div><!-- /deck -->

<div id="dots"></div>

<script>
(function(){
  const totalSlides = 14;
  let current = 0;
  const slides = [];
  for(let i=0;i<totalSlides;i++){ slides.push(document.getElementById('slide-'+i)); }

  const progressBar = document.getElementById('progress-bar');
  const counterCurrent = document.getElementById('counter-current');
  const counterTotal = document.getElementById('counter-total');
  const dotsWrap = document.getElementById('dots');
  const prevBtn = document.getElementById('prevBtn');
  const nextBtn = document.getElementById('nextBtn');

  counterTotal.textContent = String(totalSlides).padStart(2,'0');

  // build dots
  for(let i=0;i<totalSlides;i++){
    const b = document.createElement('button');
    b.className = 'dot-btn' + (i===0 ? ' active' : '');
    b.setAttribute('aria-label','Go to slide '+(i+1));
    b.addEventListener('click', ()=> goTo(i));
    dotsWrap.appendChild(b);
  }
  const dotEls = Array.from(dotsWrap.children);

  function render(direction){
    slides.forEach((s,i)=>{
      s.classList.remove('active','exit-left','exit-right');
      if(i===current){ s.classList.add('active'); }
    });
    dotEls.forEach((d,i)=> d.classList.toggle('active', i===current));
    progressBar.style.width = ((current+1)/totalSlides*100) + '%';
    counterCurrent.textContent = String(current+1).padStart(2,'0');
    prevBtn.disabled = current===0;
    nextBtn.disabled = current===totalSlides-1;
  }

  function goTo(idx){
    if(idx<0 || idx>=totalSlides || idx===current) return;
    current = idx;
    render();
  }
  function next(){ if(current<totalSlides-1){ current++; render(); } }
  function prev(){ if(current>0){ current--; render(); } }

  nextBtn.addEventListener('click', next);
  prevBtn.addEventListener('click', prev);

  document.addEventListener('keydown', (e)=>{
    if(e.key==='ArrowRight' || e.key==='PageDown'){ next(); }
    else if(e.key==='ArrowLeft' || e.key==='PageUp'){ prev(); }
  });

  // basic swipe support
  let touchStartX = null;
  document.addEventListener('touchstart', e=>{ touchStartX = e.touches[0].clientX; }, {passive:true});
  document.addEventListener('touchend', e=>{
    if(touchStartX===null) return;
    const dx = e.changedTouches[0].clientX - touchStartX;
    if(dx > 60) prev();
    else if(dx < -60) next();
    touchStartX = null;
  }, {passive:true});

  render();

  // floating particles for hero
  const particleField = document.getElementById('particles');
  const particleCount = 38;
  for(let i=0;i<particleCount;i++){
    const p = document.createElement('div');
    p.className = 'particle';
    const size = Math.random()*3 + 1.5;
    p.style.width = size+'px';
    p.style.height = size+'px';
    p.style.left = Math.random()*100 + '%';
    p.style.bottom = (-10 - Math.random()*20) + 'px';
    const duration = 8 + Math.random()*14;
    p.style.animationDuration = duration+'s';
    p.style.animationDelay = (Math.random()*duration)+'s';
    p.style.background = Math.random() > 0.5 ? '#10d9a0' : '#3b82f6';
    particleField.appendChild(p);
  }
})();
</script>
</body>
</html>

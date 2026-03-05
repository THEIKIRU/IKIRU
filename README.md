<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>IKIRU — Type Assessment</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400;1,600&family=Inter:wght@300;400;500&family=Shippori+Mincho:wght@400;600;800&family=Noto+Sans+JP:wght@300;400;500&display=swap" rel="stylesheet">
<style>
/* ── MOBILE VIEWPORT FIX ── */
html, body {
  overflow-x: hidden;
  width: 100%;
}
/* ── Palette ── */
:root {
  /* Background */
  --bg-color:   #F8F5F0;
  --beige:      #F8F5F0;
  --beige-card: #EEEBE4;
  --white:      #FFFFFF;

/* Text */
–text-main:  #2D3436;
–type:       #2D3436;
–text-muted: #718093;
–muted:      #718093;

/* Archetype accents */
–wa:         #708238;
–zen:        #3C4E71;
–katsu:      #8E443D;
–min:        #9B7E4B;

/* Structural */
–deep-navy:  #1A202C;
–navy:       #1A202C;
–border:     rgba(45,52,54,0.11);
–gold:       #9B7E4B;
–gold-lt:    #B8976A;
}

*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; max-width:100%; }
html {
scroll-behavior:smooth;
overflow-x:hidden;
max-width:100vw;
}

body {
overflow-x:hidden;
max-width:100vw;
font-family: ‘Inter’, ‘Noto Sans JP’, sans-serif;
background-color: var(–bg-color);
color: var(–text-main);
min-height: 100vh;
line-height: 1.75;
-webkit-font-smoothing: antialiased;
}

.result-name em, .cta-h em, .intro-h em, .email-h em,
.copy-poetic em, .result-tagline em, .intro-longevity {
font-family: ‘Cormorant Garamond’, ‘Shippori Mincho’, serif;
font-style: italic;
}
.intro-body em {
font-style: italic;
font-size: inherit;
font-family: inherit;
}

body::before {
content:’’;
position:fixed; top:0; left:0;
width:100vw; height:100vh;
background:
radial-gradient(ellipse at 78% 8%,  rgba(184,154,90,.06) 0%,transparent 48%),
radial-gradient(ellipse at 8%  88%, rgba(74,111,165,.05) 0%,transparent 48%);
pointer-events:none; z-index:0;
overflow:hidden;
}

.app {
position:relative; z-index:1;
width:100%; max-width:100vw; overflow-x:hidden; box-sizing:border-box;
}
.screen { display:none; width:100%; box-sizing:border-box; }
.screen.active {
display:block;
animation:fadeUp .55s cubic-bezier(.22,1,.36,1) forwards;
}
@keyframes fadeUp {
from { opacity:0; transform:translateY(16px); }
to   { opacity:1; transform:translateY(0); }
}

.serif { font-family:‘Cormorant Garamond’,serif; }

.eyebrow {
font-size:.58rem; letter-spacing:.34em; text-transform:uppercase;
color:var(–gold); display:flex; align-items:center; gap:.7rem;
margin-bottom:1.5rem;
}
.eyebrow::before {
content:’’; flex:0 0 24px; height:1px;
background:var(–gold); opacity:.5;
}

.rule { width:36px; height:1px; background:var(–gold); opacity:.4; margin:1.5rem 0; }

.c-wa    { color:var(–wa);    }
.c-zen   { color:var(–zen);   }
.c-katsu { color:var(–katsu); }
.c-min   { color:var(–min);   }

.btn-primary {
display: flex; align-items: center; justify-content: center; gap: .7rem;
width: 100%;
padding: 1.2rem 2rem;
background: linear-gradient(110deg, #8B6914 0%, #C4943A 35%, #E8B84B 55%, #C4943A 75%, #8B6914 100%);
background-size: 280% 100%;
background-position: 0% 0;
color: #FDF8EE;
font-family: ‘Cormorant Garamond’, serif;
font-size: 1rem; font-weight: 400;
font-style: italic;
letter-spacing: .1em;
border: none; cursor: pointer;
position: relative; overflow: hidden;
transition: background-position 0.7s ease, transform 0.3s ease, box-shadow 0.3s ease;
box-shadow:
0 4px 20px rgba(155,126,75,0.35),
inset 0 1px 0 rgba(255,255,255,0.2);
animation: goldShimmer 3.5s ease-in-out infinite;
}
/* Shimmer sweep overlay */
.btn-primary::before {
content: ‘’;
position: absolute; top: 0; left: -75%;
width: 50%; height: 100%;
background: linear-gradient(
120deg,
transparent 0%,
rgba(255,255,255,0.18) 50%,
transparent 100%
);
animation: shimmerSweep 3.5s ease-in-out infinite;
pointer-events: none;
}
/* Inner border for luxury feel */
.btn-primary::after {
content: ‘’;
position: absolute; inset: 1px;
border: 1px solid rgba(255,255,255,0.15);
pointer-events: none;
}
.btn-primary:hover {
background-position: 100% 0;
transform: translateY(-2px);
box-shadow:
0 10px 32px rgba(155,126,75,0.5),
inset 0 1px 0 rgba(255,255,255,0.25);
animation: none;
}
.btn-primary:hover::before { animation: none; }
.btn-primary:active { transform: translateY(0px); }

@keyframes goldShimmer {
0%,100% {
box-shadow: 0 4px 20px rgba(155,126,75,0.35), inset 0 1px 0 rgba(255,255,255,0.2);
background-position: 0% 0;
}
50% {
box-shadow: 0 6px 28px rgba(155,126,75,0.55), 0 0 0 4px rgba(155,126,75,0.1), inset 0 1px 0 rgba(255,255,255,0.2);
background-position: 60% 0;
}
}
@keyframes shimmerSweep {
0%   { left: -75%; opacity: 0; }
20%  { opacity: 1; }
60%  { left: 130%; opacity: 0; }
100% { left: 130%; opacity: 0; }
}
.btn-arrow {
display: inline-block;
font-style: normal;
transition: transform 0.35s ease;
}
.btn-primary:hover .btn-arrow { transform: translateX(6px); }
.btn-next {
width:auto !important;
padding:.65rem 1.4rem !important;
font-size:.62rem !important;
font-family:‘Inter’,sans-serif !important;
font-style:normal !important;
letter-spacing:.15em !important;
background: linear-gradient(110deg, #8B6914, #C4943A) !important;
box-shadow: 0 3px 14px rgba(155,126,75,0.35) !important;
animation: none !important;
}
.btn-next:hover {
background: linear-gradient(110deg, #7a5c10, #b8863a) !important;
}
.btn-full  { width:100%; }

.btn-ghost {
background:none; border:1px solid var(–border);
color:var(–muted); padding:.6rem 1.3rem;
font-family:‘Inter’,sans-serif; font-size:.64rem;
letter-spacing:.15em; text-transform:uppercase;
cursor:pointer; transition:all .2s;
}
.btn-ghost:hover { border-color:var(–navy); color:var(–navy); }

/* Quiz screen padding */
#s-quiz.active {
padding: 2rem 1.25rem 3rem;
max-width: 560px;
margin: 0 auto;
}
/* Result screens - no top margin */
#r-wa.active, #r-zen.active, #r-katsu.active, #r-min.active {
padding: 1.25rem 1.25rem 3rem;
max-width: 560px;
margin: 0 auto;
}
#s-intro {
display: none;
width: 100%;
max-width: 480px;
box-sizing: border-box;
}
#s-intro.active {
display: flex;
flex-direction: column;
justify-content: center;
align-items: flex-start;
min-height: 100svh;
padding: 2rem 1.25rem 1.5rem;
max-width: 480px;
margin: 0 auto;
}

.intro-mark {
font-family:‘Cormorant Garamond’,serif;
font-size: clamp(3.2rem, 13vw, 5.5rem);
font-weight:300; line-height:1; letter-spacing:.06em;
color:var(–navy); margin-bottom:.1em;
}
.intro-longevity {
font-family: ‘Cormorant Garamond’, serif;
font-size: clamp(.95rem, 2.8vw, 1.15rem);
font-weight: 300; font-style: italic;
color: var(–gold); letter-spacing: .03em;
margin-bottom: .4rem;
}
.intro-jp {
font-family: ‘Inter’, sans-serif;
font-size: .6rem; letter-spacing: .28em;
color: var(–muted); display: block;
margin-bottom: 1rem; font-weight: 300;
}
.rule { width:32px; height:1px; background:var(–gold); opacity:.4; margin:.9rem 0; }

.intro-lead {
font-family: ‘Inter’, sans-serif;
font-size: .95rem;
font-weight: 400;
color: var(–navy);
line-height: 1.5;
margin-bottom: .65rem;
}

.intro-body {
font-family: ‘Inter’, sans-serif;
font-size: .82rem; line-height: 1.75; font-weight: 300;
color: var(–type); opacity: .75;
margin-bottom: 0;
}
.intro-body strong { font-weight: 500; color: var(–navy); opacity: 1; }

.intro-divider {
width: 100%; height: 1px;
background: var(–border);
margin: .9rem 0;
}

.intro-meta {
font-family: ‘Inter’, sans-serif;
font-size: .75rem;
color: var(–muted);
line-height: 1.75;
font-weight: 300;
margin-bottom: .9rem;
}
.intro-meta strong { color: var(–navy); font-weight: 500; }

.arch-row {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: .4rem;
margin-bottom: .9rem;
}
.arch-chip {
display: flex; align-items: center; justify-content: center; gap: .3rem;
padding: .4rem .3rem;
border: 1px solid var(–border);
background: rgba(255,255,255,.5);
font-family: ‘Inter’, sans-serif;
font-size: .52rem; letter-spacing: .1em;
text-transform: uppercase; color: var(–muted);
white-space: nowrap;
}
.arch-k {
font-family: ‘Cormorant Garamond’, serif;
font-size: .9rem; font-weight: 400;
}

.intro-disclaimer {
font-family: ‘Inter’, sans-serif;
font-size: .58rem;
color: var(–muted);
text-align: center;
margin-top: .6rem;
letter-spacing: .04em;
opacity: .6;
}

/* ── QUIZ ── */
.q-brand {
font-family:‘Cormorant Garamond’,serif;
font-size:.85rem; font-weight:400; letter-spacing:.18em;
text-transform:uppercase; color:var(–gold);
display:block; margin-bottom:1.5rem;
}

.prog-wrap { margin-bottom:2rem; }
.prog-track {
width:100%; height:1px; background:var(–border);
position:relative; margin-bottom:.6rem;
}
.prog-fill {
position:absolute; top:0; left:0; height:100%;
background: linear-gradient(90deg, #8B6914, #C4943A);
transition:width .55s ease;
}
.prog-dots { display:flex; gap:.5rem; }
.prog-dot {
width:5px; height:5px; border-radius:50%;
background:var(–border); transition:background .3s, transform .3s;
}
.prog-dot.done { background:var(–gold); transform:scale(1.2); }

.q-num {
font-size:.57rem; letter-spacing:.28em; text-transform:uppercase;
color:var(–gold); display:block; margin-bottom:.55rem;
}
.q-text {
font-family:‘Cormorant Garamond’,serif;
font-size:clamp(1.35rem,4vw,1.8rem);
font-weight:300; line-height:1.48;
color:var(–navy); margin-bottom:1.75rem;
}

.choices { display:flex; flex-direction:column; gap:.5rem; margin-bottom:1.75rem; }
.choice {
display:flex; align-items:center; gap:1rem;
padding:.92rem 1.1rem;
border:1px solid var(–border);
background:rgba(255,255,255,.6);
cursor:pointer; text-align:left; width:100%;
transition:all .18s ease; position:relative;
}
.choice::before {
content:’’; position:absolute; left:0; top:0; bottom:0; width:2px;
background:var(–gold); transform:scaleY(0);
transform-origin:center; transition:transform .2s;
}
.choice:hover { border-color:rgba(184,154,90,.35); background:rgba(255,255,255,.9); }
.choice:hover::before { transform:scaleY(1); }
.choice.selected { border-color:var(–gold); background:rgba(184,154,90,0.06); }
.choice.selected::before { transform:scaleY(1); background:var(–gold); }

.choice-letter {
font-family:‘Cormorant Garamond’,serif;
font-size:.88rem; font-weight:600;
color:var(–gold); width:18px; flex-shrink:0;
}
.choice.selected .choice-letter { color:var(–gold); }
.choice-text {
font-size:.87rem; line-height:1.55;
color:var(–type); font-weight:300; flex:1;
}
.choice-check {
width:17px; height:17px; border-radius:50%;
border:1px solid var(–border); flex-shrink:0;
display:flex; align-items:center; justify-content:center;
font-size:.58rem; transition:all .18s; color:transparent;
}
.choice.selected .choice-check {
background: linear-gradient(135deg, #8B6914, #C4943A);
border-color:var(–gold); color:#fff;
}
.q-nav { display:flex; justify-content:space-between; align-items:center; }

/* ── EMAIL ── */
.email-h {
font-family:‘Cormorant Garamond’,serif;
font-size:clamp(2rem,6.5vw,3rem);
font-weight:300; line-height:1.2;
color:var(–navy); margin-bottom:1rem;
}
.email-h em { font-style:italic; color:var(–gold); }

.email-body {
font-size:.9rem; line-height:2; font-weight:300;
color:var(–type); opacity:.75; margin-bottom:1.75rem;
}

.quote-box {
border-left:2px solid var(–gold);
padding:.5rem .9rem; margin-bottom:.7rem;
background:rgba(184,154,90,.04);
}
.quote-label {
font-size:.52rem; letter-spacing:.22em; text-transform:uppercase;
color:var(–gold); display:block; margin-bottom:.3rem;
}
.quote-text {
font-family:‘Cormorant Garamond’,serif;
font-size:.88rem; font-style:italic; font-weight:300;
color:var(–navy); line-height:1.55;
}

.field { margin-bottom:.45rem; }
.field label {
display:block; font-size:.55rem; letter-spacing:.2em;
text-transform:uppercase; color:var(–muted); margin-bottom:.35rem;
}
.field input {
width:100%; padding:.7rem .9rem;
border:1px solid var(–border); background:#fff;
font-family:‘Inter’,sans-serif; font-size:16px; font-weight:300;
color:var(–type); outline:none; transition:border-color .2s;
}
.field input:focus { border-color:var(–navy); }
.field input::placeholder { color:#B0B8C4; font-size:16px; }

.privacy {
font-size:.58rem; color:var(–muted); margin-top:.6rem;
line-height:1.55; display:flex; gap:.4rem; align-items:flex-start;
}

/* ── RESULT ── */
.result-hero {
display:flex; align-items:flex-start; gap:1rem; margin-bottom:1.5rem;
width:100%;
}
.result-kanji {
font-family:‘Cormorant Garamond’,serif;
font-size:clamp(5rem,15vw,8.5rem);
font-weight:300; line-height:1; flex-shrink:0;
}
.result-meta { padding-top:.4rem; flex:1; min-width:0; }
.result-archnum {
font-size:.55rem; letter-spacing:.26em; text-transform:uppercase;
color:var(–muted); display:block; margin-bottom:.35rem;
}
.result-name {
font-family:‘Cormorant Garamond’,serif;
font-size:clamp(1.1rem,4vw,2.1rem);
font-weight:300; line-height:1.2;
color:var(–navy); margin-bottom:.3rem;
overflow-wrap:break-word; word-break:break-word;
width:100%; box-sizing:border-box;
}
.result-name em { font-style:italic; color:var(–gold); }
.result-pillar {
font-size:.57rem; letter-spacing:.18em; text-transform:uppercase;
color:var(–muted); display:block; margin-bottom:.65rem;
}
.result-tagline {
font-family:‘Inter’,sans-serif;
font-size:.78rem; font-style:italic; font-weight:300;
color:var(–muted); line-height:1.5;
overflow-wrap:break-word; word-break:break-word;
width:100%; box-sizing:border-box;
display:block;
}

.hr { height:1px; background:var(–border); margin:1.75rem 0; }
.sec-label {
font-size:.55rem; letter-spacing:.26em; text-transform:uppercase;
color:var(–gold); display:block; margin-bottom:.9rem;
}

.copy-poetic {
font-family:‘Inter’,sans-serif;
font-size:.85rem; font-style:italic; font-weight:300;
color:var(–navy); line-height:1.65; margin-bottom:.85rem;
overflow-wrap:break-word; word-break:break-word;
width:100%; box-sizing:border-box;
}
.copy-structural {
font-size:.87rem; line-height:1.95; font-weight:300;
color:var(–type); opacity:.8;
padding-left:1rem; border-left:1px solid var(–border);
margin-bottom:1.25rem;
overflow-wrap:break-word; word-break:break-word;
width:100%; box-sizing:border-box;
}
.copy-structural strong { font-weight:500; color:var(–navy); opacity:1; }

.truth-block {
margin:1.25rem 0; padding:.9rem 1rem;
border-left:2px solid currentColor;
background:rgba(255,255,255,.45);
width:100%; box-sizing:border-box;
}
.truth-label {
font-size:.54rem; letter-spacing:.22em; text-transform:uppercase;
color:inherit; display:block; margin-bottom:.45rem; opacity:.65;
}
.truth-body {
font-family:‘Inter’,sans-serif;
font-size:.88rem; font-style:italic; font-weight:300;
line-height:1.65; color:var(–navy);
}

/* ── SCORE ── */
.score-block {
display:flex; align-items:center; gap:1.2rem;
margin: 1.2rem 0 1.5rem;
padding: 1rem 1.25rem;
background: rgba(28,43,58,.04);
border: 1px solid rgba(184,151,46,.2);
}
.score-label {
font-family:‘Inter’,sans-serif;
font-size:.55rem; letter-spacing:.22em; text-transform:uppercase;
color:var(–muted); display:block; margin-bottom:.3rem;
}
.score-num {
font-family:‘Cormorant Garamond’,serif;
font-size:2rem; font-weight:300; color:var(–navy); line-height:1;
}
.score-num span { font-size:1rem; color:var(–muted); }
.score-bar-wrap {
flex:1; height:4px; background:rgba(184,151,46,.15); border-radius:2px;
}
.score-bar {
height:4px; background:var(–gold); border-radius:2px;
transition: width 1.2s cubic-bezier(.22,1,.36,1);
}
.score-note {
font-size:.78rem; font-style:italic; color:var(–muted);
margin-top:.25rem;
}

/* ── THE GAP ── */
.gap-block {
margin: 1.5rem 0;
padding: 1.1rem 1.25rem;
border-left: 2px solid rgba(184,151,46,.4);
}
.gap-intro {
font-size:.95rem; font-style:italic; color:var(–navy);
line-height:1.65; margin-bottom:.9rem;
}
.gap-drivers {
list-style:none; padding:0; margin:0 0 .9rem;
}
.gap-drivers li {
font-family:‘Inter’,sans-serif;
font-size:.78rem; color:var(–muted);
padding:.3rem 0; border-bottom:1px solid rgba(184,151,46,.1);
display:flex; align-items:center; gap:.6rem;
}
.gap-drivers li:last-child { border-bottom:none; }
.gap-drivers li::before { content:’·’; color:var(–gold); font-size:1.2rem; }
.gap-close {
font-size:.85rem; font-style:italic; color:var(–navy); line-height:1.6;
}

/* ── QUICK RESET ── */
.quick-reset {
margin: 1.25rem 0;
padding: 1rem 1.25rem;
border-left: 2px solid var(–gold);
background: rgba(184,151,46,.06);
}
.qr-label {
font-size:.52rem; letter-spacing:.28em; text-transform:uppercase;
color:var(–gold); display:block; margin-bottom:.75rem;
font-family:‘Inter’,sans-serif;
}
.qr-item {
display:flex; align-items:baseline; gap:.6rem;
font-size:.88rem; line-height:1.6; color:var(–navy);
margin-bottom:.5rem;
}
.qr-item:last-child { margin-bottom:0; }
.qr-item::before { content:‘→’; color:var(–gold); font-size:.75rem; flex-shrink:0; }

/* ── LOCKED ── */
.locked-unit {
position: relative;
margin: 1.25rem 0 0;
}
.locked-content {
position: relative;
user-select: none;
pointer-events: none;
overflow: hidden;
}
/* Gradient fade mask — starts at 45%, fully opaque at bottom */
.locked-content::after {
content: ‘’;
position: absolute;
left: 0; right: 0; bottom: 0;
height: 62%;
background: linear-gradient(to bottom, transparent 0%, var(–beige) 100%);
pointer-events: none;
z-index: 1;
}
.locked-content .lc-label {
font-size:.52rem; letter-spacing:.22em;
text-transform:uppercase; color:var(–gold);
display:block; margin-bottom:.85rem;
}
.lc-item {
display: flex;
align-items: baseline;
gap: .55rem;
margin-bottom: .55rem;
line-height: 1.5;
font-size: .82rem;
color: var(–type);
}
.lc-item::before {
content: ‘✦’;
color: var(–gold);
font-size: .48rem;
flex-shrink: 0;
margin-top: .3rem;
}
.lc-item-inner {
display: flex;
flex-wrap: wrap;
align-items: baseline;
gap: 0 .28rem;
}
.lc-visible { color: var(–type); }
.lc-hidden {
color: var(–type);
user-select: none;
pointer-events: none;
white-space: nowrap;
overflow: hidden;
max-width: 14rem;
}
/* Row 1&2: visible=クリア, hidden=ギリギリ読めないぼかし */
.lc-item:nth-child(2) .lc-visible { opacity: 1 !important; filter: none !important; }
.lc-item:nth-child(2) .lc-hidden  { filter: blur(6px) !important; opacity: .55 !important; }
.lc-item:nth-child(3) .lc-visible { opacity: 1 !important; filter: none !important; }
.lc-item:nth-child(3) .lc-hidden  { filter: blur(6px) !important; opacity: .55 !important; }
/* Row 3: 40%薄く → opacity .55 * 0.6 = .33 */
.lc-item:nth-child(4) .lc-visible { filter: blur(6px) !important; opacity: .33 !important; }
.lc-item:nth-child(4) .lc-hidden  { filter: blur(7px) !important; opacity: .27 !important; }
/* Row 4: 40%薄く → opacity .45 * 0.6 = .27 */
.lc-item:nth-child(5) .lc-visible { filter: blur(6px) !important; opacity: .27 !important; }
.lc-item:nth-child(5) .lc-hidden  { filter: blur(7px) !important; opacity: .21 !important; }
/* Row 5: そのまま */
.lc-item:nth-child(6) .lc-visible { filter: blur(6px) !important; opacity: .45 !important; }
.lc-item:nth-child(6) .lc-hidden  { filter: blur(7px) !important; opacity: .35 !important; }

.locked-fade { display: none; }

.locked-cta {
position: relative;
z-index: 2;
text-align: center;
margin-top: -8rem; /* 💙位置まで上げる */
padding: .25rem 0 .5rem;
background: transparent;
}

.lock-icon { font-size:1.4rem; display:block; margin-bottom:.3rem; margin-top:1rem; }
.lock-msg {
font-family:‘Cormorant Garamond’,serif;
font-size:.95rem; font-style:italic; font-weight:300;
color:var(–navy); line-height:1.55;
margin-bottom:.7rem; display:block;
margin-top:.15rem;
}

.btn-access {
display: block; width: 100%;
background: linear-gradient(110deg, #6B4F10 0%, #B8860B 25%, #E8C44A 50%, #B8860B 75%, #6B4F10 100%);
background-size: 300% 100%;
background-position: 0% 0;
color: #FDF8EE;
text-decoration: none; text-align: center;
padding: 1.35rem 2rem;
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.15rem; font-weight: 400; font-style: italic;
letter-spacing: 0.1em; border: none; cursor: pointer;
position: relative; overflow: hidden;
transition: background-position 0.8s ease, transform 0.3s ease, box-shadow 0.3s ease;
box-shadow:
0 6px 28px rgba(155,126,75,0.45),
0 2px 8px rgba(155,126,75,0.3),
inset 0 1px 0 rgba(255,240,180,0.25);
animation: accessGlow 2.5s ease-in-out infinite;
}
/* Shimmer sweep */
.btn-access::before {
content: ‘’;
position: absolute; top:0; left:-80%;
width: 60%; height: 100%;
background: linear-gradient(120deg, transparent, rgba(255,240,160,0.22), transparent);
animation: accessShimmer 2.5s ease-in-out infinite;
pointer-events: none;
}
/* Inner border */
.btn-access::after {
content: ‘’; position: absolute; inset: 1.5px;
border: 1px solid rgba(255,230,120,0.25); pointer-events: none;
}
.btn-access:hover {
background-position: 100% 0;
transform: translateY(-3px) scale(1.01);
box-shadow:
0 14px 40px rgba(155,126,75,0.6),
0 4px 12px rgba(155,126,75,0.4),
inset 0 1px 0 rgba(255,240,180,0.3);
animation: none;
}
.btn-access:hover::before { animation: none; left: 120%; }
.btn-access:active { transform: translateY(0) scale(1); }
@keyframes accessGlow {
0%,100% {
box-shadow: 0 6px 28px rgba(155,126,75,0.45), 0 2px 8px rgba(155,126,75,0.3), inset 0 1px 0 rgba(255,240,180,0.25);
background-position: 0% 0;
}
50% {
box-shadow: 0 8px 36px rgba(155,126,75,0.65), 0 0 0 5px rgba(184,134,11,0.12), inset 0 1px 0 rgba(255,240,180,0.25);
background-position: 50% 0;
}
}
@keyframes accessShimmer {
0%   { left:-80%; opacity:0; }
15%  { opacity:1; }
65%  { left:120%; opacity:0; }
100% { left:120%; opacity:0; }
}
.btn-access-main {
display:block; font-family:‘Cormorant Garamond’,serif;
font-size:1.15rem; font-style:italic; letter-spacing:.08em;
margin-bottom:.3rem;
}
.btn-access-sub {
display:block; font-family:‘Inter’,sans-serif;
font-size:.58rem; font-style:normal;
letter-spacing:.2em; text-transform:uppercase; opacity:.8;
}

.cta-note {
text-align:center; margin-top:.65rem;
font-size:.6rem; color:var(–muted); letter-spacing:.08em; opacity:.6;
}
.result-email-form { display:flex; flex-direction:column; gap:.5rem; margin-bottom:.1rem; }
.result-email-input {
width:100%; padding:.75rem .9rem;
border:1px solid var(–border); background:#fff;
font-family:‘Inter’,sans-serif; font-size:16px; font-weight:300;
color:var(–type); outline:none; transition:border-color .2s;
box-sizing:border-box;
}
.result-email-input:focus { border-color:var(–gold); }
.result-email-input::placeholder { color:#B0B8C4; }
.result-email-form { display:flex; flex-direction:column; gap:.5rem; }
.result-email-input {
width:100%; padding:.75rem .9rem;
border:1px solid var(–border); background:#fff;
font-family:‘Inter’,sans-serif; font-size:16px; font-weight:300;
color:var(–type); outline:none; transition:border-color .2s;
box-sizing:border-box;
}
.result-email-input:focus { border-color:var(–gold); }
.result-email-input::placeholder { color:#B0B8C4; }

/* ── Pyramid bg ── */
.pyramid-bg {
position:absolute; bottom:0; right:-5%;
width:min(420px, 100vw); opacity:0.07;
pointer-events:none; z-index:0;
}
/* Real pyramid image background for result screens */
.result-pyramid-bg {
position:absolute;
top: 11rem; bottom:0; left:50%; transform:translateX(-50%);
width:min(340px, 75%);
height: calc(100% - 11rem);
opacity:0.12;
pointer-events:none; z-index:0;
object-fit:contain;
object-position:center top;
mask-image: linear-gradient(to bottom,
rgba(0,0,0,0.9) 0%,
rgba(0,0,0,1) 30%,
rgba(0,0,0,1) 75%,
transparent 100%
);
-webkit-mask-image: linear-gradient(to bottom,
rgba(0,0,0,0.9) 0%,
rgba(0,0,0,1) 30%,
rgba(0,0,0,1) 75%,
transparent 100%
);
}

/* Email screen button — calmer version */
.btn-access-calm {
display: block; width: 100%;
background: linear-gradient(110deg, #8B6914 0%, #C4943A 50%, #8B6914 100%);
background-size: 220% 100%;
background-position: 0% 0;
color: #FDF8EE;
text-decoration: none; text-align: center;
padding: 1.1rem 2rem;
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.05rem; font-weight: 400; font-style: italic;
letter-spacing: 0.1em; border: none; cursor: pointer;
position: relative; overflow: hidden;
transition: background-position 0.6s ease, transform 0.25s ease, box-shadow 0.25s ease;
box-shadow: 0 4px 16px rgba(155,126,75,0.28), inset 0 1px 0 rgba(255,240,180,0.15);
}
.btn-access-calm::after {
content: ‘’; position: absolute; inset: 1px;
border: 1px solid rgba(255,230,120,0.15); pointer-events: none;
}
.btn-access-calm:hover {
background-position: 100% 0;
transform: translateY(-1px);
box-shadow: 0 7px 22px rgba(155,126,75,0.4), inset 0 1px 0 rgba(255,240,180,0.2);
}
.btn-access-calm:active { transform: translateY(0); }
#s-intro, #r-wa, #r-zen, #r-katsu, #r-min {
position:relative; overflow:hidden;
}

/* ── Responsive ── */
@media (max-width:600px) {
html { font-size:13px; }
.result-hero { flex-direction:column; gap:.3rem; }
.result-kanji { font-size:2.8rem; }
.result-meta { padding-top:0; width:100%; }
#s-intro.active { padding: 2rem 1rem 1.5rem; }
#s-quiz.active { padding: 1.5rem 1rem 2rem; }
#r-wa.active, #r-zen.active, #r-katsu.active, #r-min.active { padding: 1rem 1rem 2.5rem; }

}

/* ══ LP STYLES ══ */

:root {
–beige:  #F8F5F0;
–navy:   #1C2B3A;
–gold:   #B8972E;
–muted:  #8A9BAA;
–border: #E2DDD6;
–type:   #3A4A58;
}
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { font-size: 15px; }
body {
background: var(–beige);
color: var(–navy);
font-family: ‘Inter’, sans-serif;
font-weight: 300;
line-height: 1.75;
-webkit-font-smoothing: antialiased;
overflow-x: hidden;
}

.wrap {
max-width: 480px;
margin: 0 auto;
padding: 0 1.5rem;
}

/* ── HEADER ── */
.lp-header {
text-align: center;
padding: 2rem 1.5rem 1.5rem;
border-bottom: 1px solid var(–border);
}
.lp-brand {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.1rem;
letter-spacing: .35em;
text-transform: uppercase;
color: var(–gold);
display: block;
}
.lp-brand-jp {
font-size: .6rem;
letter-spacing: .2em;
color: var(–muted);
display: block;
margin-top: .2rem;
}

/* ── SECTIONS ── */
section { padding: 2rem 0; border-bottom: 1px solid var(–border); }
section:last-of-type { border-bottom: none; }

.eyebrow {
font-family: ‘Inter’, sans-serif;
font-size: .52rem;
letter-spacing: .25em;
text-transform: uppercase;
color: var(–gold);
display: block;
margin-bottom: .85rem;
}

/* ── ① HOOK ── */
.hook-type {
font-family: ‘Inter’, sans-serif;
font-size: .6rem;
letter-spacing: .2em;
text-transform: uppercase;
color: var(–muted);
display: block;
margin-bottom: .5rem;
}
.hook-kanji {
font-family: ‘Cormorant Garamond’, serif;
font-size: 3.5rem;
font-weight: 300;
line-height: 1;
display: block;
margin-bottom: .4rem;
}
.hook-headline {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.65rem;
font-weight: 300;
font-style: italic;
line-height: 1.35;
color: var(–navy);
margin-bottom: 1.1rem;
}
.hook-score {
display: inline-flex;
align-items: center;
gap: .6rem;
padding: .5rem .9rem;
border: 1px solid rgba(184,151,46,.3);
background: rgba(184,151,46,.06);
margin-bottom: 1.1rem;
}
.hook-score-label {
font-size: .55rem;
letter-spacing: .15em;
text-transform: uppercase;
color: var(–muted);
}
.hook-score-val {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.2rem;
color: var(–gold);
}
.hook-body {
font-size: .88rem;
color: var(–type);
line-height: 1.75;
margin-bottom: .8rem;
}
.hook-good {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.1rem;
font-style: italic;
color: var(–navy);
line-height: 1.5;
border-left: 2px solid var(–gold);
padding-left: .9rem;
margin-top: 1rem;
}

/* ── ② DIAGNOSIS MIRROR ── */
.mirror-intro {
font-size: .88rem;
color: var(–muted);
font-style: italic;
margin-bottom: .9rem;
}
.mirror-list {
list-style: none;
margin-bottom: 1rem;
}
.mirror-list li {
font-size: .88rem;
color: var(–type);
padding: .45rem 0;
border-bottom: 1px solid var(–border);
display: flex;
gap: .6rem;
align-items: baseline;
}
.mirror-list li::before {
content: ‘·’;
color: var(–gold);
font-size: 1.2rem;
flex-shrink: 0;
line-height: 1;
}
.mirror-close {
font-size: .85rem;
color: var(–type);
font-style: italic;
line-height: 1.65;
}

/* ── ③ REAL PROBLEM ── */
.problem-headline {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.3rem;
font-style: italic;
font-weight: 300;
color: var(–navy);
line-height: 1.4;
margin-bottom: .9rem;
}
.problem-body {
font-size: .88rem;
color: var(–type);
line-height: 1.75;
margin-bottom: .8rem;
}
.problem-result {
padding: .9rem 1rem;
border-left: 2px solid rgba(184,151,46,.4);
background: rgba(184,151,46,.04);
margin: 1rem 0;
}
.problem-result li {
list-style: none;
font-size: .82rem;
color: var(–type);
padding: .2rem 0;
}
.problem-result li::before { content: ’— ’; color: var(–gold); }

/* ── ④ SOLUTION ── */
.solution-label {
font-size: .52rem;
letter-spacing: .28em;
text-transform: uppercase;
color: var(–gold);
display: block;
margin-bottom: 1rem;
}
.solution-name {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.8rem;
font-weight: 300;
color: var(–navy);
line-height: 1.2;
margin-bottom: .25rem;
}
.solution-sub {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1rem;
font-style: italic;
color: var(–muted);
margin-bottom: 1rem;
}
.solution-body {
font-size: .88rem;
color: var(–type);
line-height: 1.75;
margin-bottom: .6rem;
}
.solution-tags {
display: flex;
gap: .5rem;
flex-wrap: wrap;
margin-top: .9rem;
}
.solution-tag {
font-size: .6rem;
letter-spacing: .15em;
text-transform: uppercase;
padding: .3rem .75rem;
border: 1px solid var(–border);
color: var(–muted);
}

/* ── ⑤ WHAT YOU GET ── */
.days-grid { margin-top: .5rem; }
.day-row {
display: flex;
gap: .9rem;
padding: .8rem 0;
border-bottom: 1px solid var(–border);
align-items: baseline;
}
.day-row:last-child { border-bottom: none; }
.day-num {
font-family: ‘Cormorant Garamond’, serif;
font-size: .75rem;
font-style: italic;
color: var(–gold);
min-width: 2.5rem;
flex-shrink: 0;
}
.day-text {
font-size: .82rem;
color: var(–type);
line-height: 1.5;
}

/* ── ⑥ WHY 7 DAYS ── */
.why-body {
font-size: .88rem;
color: var(–type);
line-height: 1.75;
margin-bottom: .8rem;
}
.why-list {
list-style: none;
margin: .8rem 0;
}
.why-list li {
font-size: .85rem;
color: var(–type);
padding: .35rem 0;
display: flex;
gap: .6rem;
}
.why-list li::before {
content: ‘✦’;
color: var(–gold);
font-size: .45rem;
flex-shrink: 0;
margin-top: .4rem;
}
.why-close {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1rem;
font-style: italic;
color: var(–muted);
margin-top: .9rem;
}

/* ── ⑦ OFFER ── */
.offer-section {
text-align: center;
padding: 2rem 0 3rem;
}
.offer-name {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.5rem;
font-weight: 300;
color: var(–navy);
margin-bottom: .25rem;
}
.offer-meta {
display: flex;
justify-content: center;
gap: 1.5rem;
margin: 1rem 0;
}
.offer-meta-item {
text-align: center;
}
.offer-meta-num {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.6rem;
font-weight: 300;
color: var(–navy);
display: block;
line-height: 1;
}
.offer-meta-label {
font-size: .52rem;
letter-spacing: .15em;
text-transform: uppercase;
color: var(–muted);
display: block;
margin-top: .2rem;
}
.offer-price {
font-family: ‘Cormorant Garamond’, serif;
font-size: 2.8rem;
font-weight: 300;
color: var(–navy);
display: block;
margin: 1rem 0 .25rem;
line-height: 1;
}
.offer-price-sub {
font-size: .65rem;
letter-spacing: .12em;
text-transform: uppercase;
color: var(–muted);
display: block;
margin-bottom: 1.5rem;
}
.btn-buy {
display: block;
width: 100%;
background: linear-gradient(110deg, #6B4F10 0%, #B8860B 25%, #E8C44A 50%, #B8860B 75%, #6B4F10 100%);
background-size: 300% 100%;
color: #FDF8EE;
text-align: center;
padding: 1.35rem 2rem;
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.15rem;
font-weight: 400;
font-style: italic;
letter-spacing: .1em;
border: none;
cursor: pointer;
text-decoration: none;
box-shadow: 0 6px 28px rgba(155,126,75,.45);
animation: btnGlow 2.5s ease-in-out infinite;
position: relative;
overflow: hidden;
}
.btn-buy::before {
content: ‘’;
position: absolute;
top: 0; left: -80%;
width: 60%; height: 100%;
background: linear-gradient(120deg, transparent, rgba(255,240,160,.22), transparent);
animation: shimmer 2.5s ease-in-out infinite;
}
@keyframes btnGlow {
0%,100% { box-shadow: 0 6px 28px rgba(155,126,75,.45); background-position: 0% 0; }
50%      { box-shadow: 0 8px 36px rgba(155,126,75,.65); background-position: 50% 0; }
}
@keyframes shimmer {
0%   { left: -80%; opacity: 0; }
15%  { opacity: 1; }
65%  { left: 120%; opacity: 0; }
100% { left: 120%; opacity: 0; }
}
.btn-buy-sub {
display: block;
font-family: ‘Inter’, sans-serif;
font-size: .55rem;
font-style: normal;
letter-spacing: .2em;
text-transform: uppercase;
opacity: .8;
margin-top: .3rem;
}
.offer-note {
font-size: .62rem;
color: var(–muted);
margin-top: .9rem;
letter-spacing: .06em;
}
.offer-divider {
width: 2rem;
height: 1px;
background: var(–border);
margin: 1.25rem auto;
}

/* ── HR ── */
.hr { height: 1px; background: var(–border); margin: 1.5rem 0; }

/* ── FADE IN ── */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(18px); }
to   { opacity: 1; transform: translateY(0); }
}
.wrap > * { animation: fadeUp .6s ease both; }

@media (max-width: 480px) {
html { font-size: 14px; }
}

.lp-wrap { max-width: 100%; padding: 0; }
.lp-header { text-align:center; padding:1.5rem 1rem 1rem; border-bottom:1px solid var(–border); margin-bottom:0; }
#s-lp section { padding: 1.5rem 0; border-bottom: 1px solid var(–border); }
#s-lp { padding: 0 1.5rem 3rem; }
</style>

</head>
<body>
<div class="app">

<!-- ══ INTRO ══ -->

<div class="screen active" id="s-intro">
  <div class="eyebrow">Type Assessment</div>

  <div class="intro-mark">IKIRU</div>
  <p class="intro-longevity">生きる (<em>ikiru</em>) — to live · The Japanese Art of Longevity</p>
  <span class="intro-jp">生 き る · 調 和 と 生 命 力</span>
  <div class="rule"></div>

  <p class="intro-lead">Find out where your balance is off.</p>

  <div class="intro-body">
    Low energy. Trouble focusing. A restlessness you can't quite name.<br><br>
    These aren't random. They follow a pattern —
    and once you know your pattern,
    <strong>the path forward becomes clear.</strong>
  </div>

  <div class="intro-divider"></div>

  <div class="intro-meta">
    5 questions &nbsp;·&nbsp; 2 minutes<br>
    Drawing on Japanese nutritional wisdom and current longevity research,
    IKIRU identifies your imbalance across <strong>4 indicators: Wa · Zen · Katsu · Min.</strong><br><br>
    Your personalised Blueprint — <strong>Founding Edition</strong> — is prepared the moment you finish.
  </div>

  <div class="arch-row">
    <div class="arch-chip"><span class="arch-k c-wa">和</span> Washoku</div>
    <div class="arch-chip"><span class="arch-k c-min">眠</span> Min</div>
    <div class="arch-chip"><span class="arch-k c-katsu">活</span> Katsu</div>
    <div class="arch-chip"><span class="arch-k c-zen">禅</span> Zen</div>
  </div>

<button class="btn-primary" onclick="startQuiz()">Start the 2-Minute Assessment <span class="btn-arrow">→</span></button>

  <p class="intro-disclaimer">Developed by a Japanese Registered Dietitian.</p>
</div>

<!-- ══ QUIZ ══ -->

<div class="screen" id="s-quiz">
  <span class="q-brand">IKIRU — Type Assessment</span>
  <div class="prog-wrap">
    <div class="prog-track">
      <div class="prog-fill" id="prog-fill" style="width:0%"></div>
    </div>
    <div class="prog-dots">
      <div class="prog-dot" id="d0"></div>
      <div class="prog-dot" id="d1"></div>
      <div class="prog-dot" id="d2"></div>
      <div class="prog-dot" id="d3"></div>
      <div class="prog-dot" id="d4"></div>
    </div>
  </div>
  <span class="q-num" id="q-num">Question 1 of 5</span>
  <p class="q-text" id="q-text"></p>
  <div class="choices" id="choices"></div>
  <div class="q-nav">
    <button class="btn-ghost" id="btn-back" onclick="prevQ()" style="visibility:hidden">← Back</button>
    <button class="btn-primary btn-next" id="btn-next" onclick="nextQ()" style="display:none">Continue →</button>
  </div>
</div>

<!-- ══ RESULT: 和 ══ -->

<div class="screen" id="r-wa">

  <div class="eyebrow">Your IKIRU Type</div>
  <div class="result-hero">
    <div class="result-kanji c-wa">和</div>
    <div class="result-meta">
      <span class="result-archnum">ARCHETYPE 01</span>
      <p class="result-name"><em>Wa</em> — Washoku</p>
      <span class="result-pillar">NUTRITION · 栄養 · 和食</span>
      <p class="result-tagline">"You eat. But something is quietly not landing."</p>
    </div>
  </div>
  <div class="hr"></div>

  <div class="score-block">
    <div>
      <span class="score-label">Nourishment Score</span>
      <span class="score-num">45<span> / 100</span></span>
    </div>
    <div style="flex:1">
      <div class="score-bar-wrap"><div class="score-bar" style="width:45%"></div></div>
      <p class="score-note">Your body is fed — but not fully nourished.</p>
      <p class="score-note" style="color:var(--gold);margin-top:.3rem;font-style:italic">Your body shows signs of incomplete nourishment absorption</p>
    </div>
  </div>

<span class="sec-label">What This Means</span>

  <p class="copy-poetic">You eat well enough. But there's a gap between what you're eating and what your body is actually absorbing.</p>
  <p class="copy-poetic">It shows up as low energy after meals. Afternoon heaviness. A body that feels like it's working harder than it should.</p>
  <p class="copy-poetic">The Wa pattern is often linked to timing, combination, and a few specific gaps — not the food itself.</p>
  <p class="copy-poetic">Most people try eating better. That's not usually what's missing.</p>

  <div class="locked-unit">
    <div class="locked-content">
      <span class="lc-label">Inside Your Reset Plan</span>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The hidden absorption pattern quietly</span><span class="lc-hidden">draining your energy — even when you eat well</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">Why your body struggles to convert</span><span class="lc-hidden">food into sustained energy</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The specific mineral gaps most common</span><span class="lc-hidden">in Wa types — and how to close them</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The exact meal timing shift that</span><span class="lc-hidden">restores energy absorption within days</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The 7-day Washoku reset protocol</span><span class="lc-hidden">built for your specific pattern</span></div></div>
    </div>
    <div class="locked-fade"></div>
    <div class="locked-cta">
      <span class="lock-icon">🔒</span>
      <span class="lock-msg">Your full Wa Reset Plan is ready.<br><em>Enter your email to unlock your personal protocol.</em></span>
      <div class="result-email-form" id="email-form-wa">
        <input class="result-email-input" id="email-wa" type="email" placeholder="your@email.com">
        <button class="btn-access" onclick="goToReset('wa')">
          <span class="btn-access-main">See Your Full Reset Plan →</span>
          <span class="btn-access-sub">Enter your email to continue</span>
        </button>
      </div>
      <p class="cta-note" style="margin-top:.55rem">No spam · Unsubscribe anytime</p>
    </div>
  </div>

  </div>

<!-- ══ RESULT: 禅 ══ -->

<div class="screen" id="r-zen">

  <div class="eyebrow">Your IKIRU Type</div>
  <div class="result-hero">
    <div class="result-kanji c-zen">禅</div>
    <div class="result-meta">
      <span class="result-archnum">ARCHETYPE 02</span>
      <p class="result-name"><em>Zen</em> — Stillness</p>
      <span class="result-pillar">STRESS · 回復 · 禅</span>
      <p class="result-tagline">"You haven't switched off in a long time. Your body has been keeping score."</p>
    </div>
  </div>
  <div class="hr"></div>

  <div class="score-block">
    <div>
      <span class="score-label">Clarity Score</span>
      <span class="score-num">49<span> / 100</span></span>
    </div>
    <div style="flex:1">
      <div class="score-bar-wrap"><div class="score-bar" style="width:49%"></div></div>
      <p class="score-note">Your mind is active — but rarely still.</p>
      <p class="score-note" style="color:var(--gold);margin-top:.3rem;font-style:italic">Your nervous system may be stuck in "always-on" mode</p>
    </div>
  </div>

<span class="sec-label">What This Means</span>

  <p class="copy-poetic">Your tiredness isn't just from being busy. It's from a body that never fully gets to rest — even when you're still, even when you sleep.</p>
  <p class="copy-poetic">The switch that should turn off the tension isn't working the way it used to.</p>
  <p class="copy-poetic">The Zen pattern often develops gradually. You adapt. You manage. But underneath, the body is running at a low-level alarm state — and that costs energy.</p>
  <p class="copy-poetic">It's not about doing less. It's about restoring the off switch.</p>

  <div class="locked-unit">
    <div class="locked-content">
      <span class="lc-label">Inside Your Reset Plan</span>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The hidden nervous system pattern</span><span class="lc-hidden">keeping your stress response switched on</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">Why your body struggles to fully relax</span><span class="lc-hidden">— even when you're resting</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The specific nutrients depleted first</span><span class="lc-hidden">by chronic low-level tension</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The daily practice that retrains</span><span class="lc-hidden">your nervous system's default state</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The 7-day Zen reset protocol</span><span class="lc-hidden">for restoring stillness and recovery</span></div></div>
    </div>
    <div class="locked-fade"></div>
    <div class="locked-cta">
      <span class="lock-icon">🔒</span>
      <span class="lock-msg">Your full Zen Reset Plan is ready.<br><em>Enter your email to unlock your personal protocol.</em></span>
      <div class="result-email-form" id="email-form-zen">
        <input class="result-email-input" id="email-zen" type="email" placeholder="your@email.com">
        <button class="btn-access" onclick="goToReset('zen')">
          <span class="btn-access-main">See Your Full Reset Plan →</span>
          <span class="btn-access-sub">Enter your email to continue</span>
        </button>
      </div>
      <p class="cta-note" style="margin-top:.55rem">No spam · Unsubscribe anytime</p>
    </div>
  </div>

  </div>

<!-- ══ RESULT: 活 ══ -->

<div class="screen" id="r-katsu">

  <div class="eyebrow">Your IKIRU Type</div>
  <div class="result-hero">
    <div class="result-kanji c-katsu">活</div>
    <div class="result-meta">
      <span class="result-archnum">ARCHETYPE 03</span>
      <p class="result-name"><em>Katsu</em> — Vitality</p>
      <span class="result-pillar">ENERGY · 活力 · 代謝</span>
      <p class="result-tagline">"Your energy isn't missing. It's leaking."</p>
    </div>
  </div>
  <div class="hr"></div>

  <div class="score-block">
    <div>
      <span class="score-label">Vitality Score</span>
      <span class="score-num">47<span> / 100</span></span>
    </div>
    <div style="flex:1">
      <div class="score-bar-wrap"><div class="score-bar" style="width:47%"></div></div>
      <p class="score-note">Your energy system works — but the rhythm is unstable.</p>
      <p class="score-note" style="color:var(--gold);margin-top:.3rem;font-style:italic">Your system shows signs of unstable metabolic rhythm</p>
    </div>
  </div>

<span class="sec-label">What This Means</span>

  <p class="copy-poetic">You can feel it in the afternoons. In how long it takes to get going in the morning.</p>
  <p class="copy-poetic">In the gap between how much you want to do and how much energy you actually have.</p>
  <p class="copy-poetic">The Katsu pattern is often linked to how the body converts food into usable energy — irregular eating, timing gaps, or the window when your metabolism works best.</p>
  <p class="copy-poetic">The frustrating part: pushing harder usually makes it worse.</p>

  <div class="locked-unit">
    <div class="locked-content">
      <span class="lc-label">Inside Your Reset Plan</span>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The exact metabolic timing mistake</span><span class="lc-hidden">that is draining your energy every day</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">Why your energy crashes at the same time</span><span class="lc-hidden">— and why willpower never fixes it</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The specific foods that destabilise</span><span class="lc-hidden">your blood sugar rhythm daily</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The timing window where Katsu types</span><span class="lc-hidden">lose the most energy — and how to protect it</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The 7-day Katsu reset protocol</span><span class="lc-hidden">for restoring stable metabolic rhythm</span></div></div>
    </div>
    <div class="locked-fade"></div>
    <div class="locked-cta">
      <span class="lock-icon">🔒</span>
      <span class="lock-msg">Your full Katsu Reset Plan is ready.<br><em>Enter your email to unlock your personal protocol.</em></span>
      <div class="result-email-form" id="email-form-katsu">
        <input class="result-email-input" id="email-katsu" type="email" placeholder="your@email.com">
        <button class="btn-access" onclick="goToReset('katsu')">
          <span class="btn-access-main">See Your Full Reset Plan →</span>
          <span class="btn-access-sub">Enter your email to continue</span>
        </button>
      </div>
      <p class="cta-note" style="margin-top:.55rem">No spam · Unsubscribe anytime</p>
    </div>
  </div>

  </div>

<!-- ══ RESULT: 眠 ══ -->

<div class="screen" id="r-min">

  <div class="eyebrow">Your IKIRU Type</div>
  <div class="result-hero">
    <div class="result-kanji c-min">眠</div>
    <div class="result-meta">
      <span class="result-archnum">ARCHETYPE 04</span>
      <p class="result-name"><em>Min</em> — Rest</p>
      <span class="result-pillar">SLEEP · 睡眠 · 回復</span>
      <p class="result-tagline">"You're getting hours of sleep. You're just not recovering during them."</p>
    </div>
  </div>
  <div class="hr"></div>

  <div class="score-block">
    <div>
      <span class="score-label">Recovery Score</span>
      <span class="score-num">43<span> / 100</span></span>
    </div>
    <div style="flex:1">
      <div class="score-bar-wrap"><div class="score-bar" style="width:43%"></div></div>
      <p class="score-note">You're sleeping — but not fully recovering.</p>
      <p class="score-note" style="color:var(--gold);margin-top:.3rem;font-style:italic">Your body shows signs of incomplete sleep recovery</p>
    </div>
  </div>

<span class="sec-label">What This Means</span>

  <p class="copy-poetic">You sleep. You wake up. And somehow you still feel like you never fully rested.</p>
  <p class="copy-poetic">It's not about sleep duration. There's a stage where the body does most of its repair. Something is interrupting it.</p>
  <p class="copy-poetic">It's rarely the obvious causes. It's subtler — patterns in the hours before bed, what you eat, how your body temperature changes overnight.</p>
  <p class="copy-poetic">Left alone, this compounds. Every tired day makes the next one harder.</p>

  <div class="locked-unit">
    <div class="locked-content">
      <span class="lc-label">Inside Your Reset Plan</span>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The hidden sleep stage being disrupted</span><span class="lc-hidden">— and the exact cause for the Min type</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">Why more hours of sleep rarely fixes this</span><span class="lc-hidden">— and what your body actually needs</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The evening habits quietly shortening</span><span class="lc-hidden">your deep recovery every night</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The body temperature and blood sugar shifts</span><span class="lc-hidden">that determine your sleep quality</span></div></div>
      <div class="lc-item"><div class="lc-item-inner"><span class="lc-visible">The 7-day Min reset protocol</span><span class="lc-hidden">for restoring deep recovery</span></div></div>
    </div>
    <div class="locked-fade"></div>
    <div class="locked-cta">
      <span class="lock-icon">🔒</span>
      <span class="lock-msg">Your full Min Reset Plan is ready.<br><em>Enter your email to unlock your personal protocol.</em></span>
      <div class="result-email-form" id="email-form-min">
        <input class="result-email-input" id="email-min" type="email" placeholder="your@email.com">
        <button class="btn-access" onclick="goToReset('min')">
          <span class="btn-access-main">See Your Full Reset Plan →</span>
          <span class="btn-access-sub">Enter your email to continue</span>
        </button>
      </div>
      <p class="cta-note" style="margin-top:.55rem">No spam · Unsubscribe anytime</p>
    </div>
  </div>

  </div>

<!-- /app -->

<script>


function fixOverflow() {
  document.documentElement.style.overflowX = 'hidden';
  document.body.style.overflowX = 'hidden';
  document.body.style.width = '100%';
  document.body.style.maxWidth = '100vw';
}
window.addEventListener('load', fixOverflow);
window.addEventListener('resize', fixOverflow);
fixOverflow();

const QUESTIONS = [
  { text: "Be honest — how do you actually feel most days?", choices: [
    { text: "Tired, even when I've slept. Like rest doesn't reach me.", type: "min" },
    { text: "Wired and anxious. My mind doesn't stop.", type: "zen" },
    { text: "Flat. Low energy. Hard to find motivation.", type: "wa" },
    { text: "Stiff, tense, or physically disconnected from my body.", type: "katsu" }
  ]},
  { text: "Where do you feel most out of balance?", choices: [
    { text: "Food, digestion, energy — my relationship with nourishment.", type: "wa" },
    { text: "Thoughts, focus, emotional waves I cannot settle.", type: "zen" },
    { text: "Posture, movement, tension I carry in my body.", type: "katsu" },
    { text: "Sleep, recovery, the quality of my rest.", type: "min" }
  ]},
  { text: "What drains you most?", choices: [
    { text: "Too many decisions. Too much information. The mind won't stop.", type: "zen" },
    { text: "Moving through life but feeling no physical vitality.", type: "katsu" },
    { text: "Food becomes an afterthought when life accelerates.", type: "wa" },
    { text: "Working too late. The inability to wind down. The cost of it.", type: "min" }
  ]},
  { text: "In health, what feels most missing?", choices: [
    { text: "The quality and intentionality of how I nourish myself.", type: "wa" },
    { text: "Mental stillness. A mind that can simply be quiet.", type: "zen" },
    { text: "Physical strength, posture, and freedom of movement.", type: "katsu" },
    { text: "Deep sleep. The feeling of true restoration.", type: "min" }
  ]},
  { text: "Which feels most true right now?", choices: [
    { text: "Changing how I eat would change almost everything.", type: "wa" },
    { text: "I want — desperately — to stop overthinking.", type: "zen" },
    { text: "I want to inhabit my body with more intention and vitality.", type: "katsu" },
    { text: "I just want to sleep. Deeply. And wake up restored.", type: "min" }
  ]}
];

const L = ['A','B','C','D'];
let cur = 0, answers = [], selected = null;

function show(id) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  const el = document.getElementById(id);
  el.classList.remove('active'); void el.offsetWidth; el.classList.add('active');
  window.scrollTo({ top: 0, behavior: 'instant' });
}


function startQuiz() { cur = 0; answers = []; selected = null; show('s-quiz'); renderQ(); }

function renderQ(showPrev = false) {
  const q = QUESTIONS[cur];
  document.getElementById('q-num').textContent = `Question ${cur + 1} of ${QUESTIONS.length}`;
  document.getElementById('q-text').textContent = q.text;
  document.getElementById('prog-fill').style.width = (cur / QUESTIONS.length * 100) + '%';
  for (let i = 0; i < 5; i++) document.getElementById('d' + i).classList.toggle('done', i <= cur - 1);
  document.getElementById('btn-back').style.visibility = cur === 0 ? 'hidden' : 'visible';
  document.getElementById('btn-next').style.display = 'none';
  const wrap = document.getElementById('choices');
  wrap.innerHTML = ''; // DOMを完全リセット
  q.choices.forEach((c, i) => {
    const btn = document.createElement('button');
    // Backで戻った時だけ前の選択を復元、それ以外は絶対にニュートラル
    const isHighlighted = (showPrev === true) && (answers[cur] === i);
    btn.className = isHighlighted ? 'choice selected' : 'choice';
    btn.innerHTML = `<span class="choice-letter">${L[i]}</span><span class="choice-text">${c.text}</span><span class="choice-check">${isHighlighted ? '✓' : ''}</span>`;
    btn.onclick = () => pick(i);
    wrap.appendChild(btn);
  });
}

function pick(i) {
  answers[cur] = i;
  document.querySelectorAll('.choice').forEach((el, idx) => {
    el.classList.toggle('selected', idx === i);
    el.querySelector('.choice-check').textContent = idx === i ? '✓' : '';
  });
  document.getElementById('btn-next').style.display = 'inline-flex';
}

function nextQ() {
  if (answers[cur] === undefined) return;
  if (cur < QUESTIONS.length - 1) { cur++; renderQ(false); }
  else {
    const map = { wa: 'r-wa', zen: 'r-zen', katsu: 'r-katsu', min: 'r-min' };
    show(map[calcResult()]);
  }
}
function prevQ() { if (cur > 0) { cur--; renderQ(true); } }

function calcResult() {
  const s = { wa: 0, zen: 0, katsu: 0, min: 0 };
  answers.forEach((a, qi) => s[QUESTIONS[qi].choices[a].type]++);
  return Object.entries(s).sort((a, b) => b[1] - a[1])[0][0];
}

function submitEmail() {
  const email = document.getElementById('inp-email').value.trim();
  if (!email || !email.includes('@')) { alert('Please enter a valid email address.'); return; }
  const map = { wa: 'r-wa', zen: 'r-zen', katsu: 'r-katsu', min: 'r-min' };
  show(map[calcResult()]);
}

function goToReset(type) {
  const emailEl = document.getElementById('email-' + type);
  const email = emailEl ? emailEl.value.trim() : '';
  if (!email || !email.includes('@')) {
    emailEl.style.borderColor = '#B8972E';
    emailEl.placeholder = 'Please enter your email first';
    emailEl.focus();
    return;
  }
  localStorage.setItem('ikiru_email', email);
  localStorage.setItem('ikiru_type', type);
  // Show LP screen
  renderLP(type);
  show('s-lp');
}


// ── Type data ──
const LP_TYPES = {
  katsu: {
    kanji: '活',
    name: 'Katsu — Vitality',
    pillar: 'ENERGY · 活力 · 代謝',
    tagline: "Your energy isn't missing. It's leaking.",
    score: 47,
    scoreLabel: 'Vitality Score',
    hookBody: "Your score shows a metabolic rhythm disruption. And the longer that rhythm stays unstable, the harder energy becomes to restore.",
    mirrorIntro: "You probably recognise this pattern:",
    mirrorItems: [
      "Energy drops around the same time each day",
      "Coffee helps — but only briefly",
      "Some days start slow and never fully recover",
      "You push through, but the effort costs more than it should"
    ],
    mirrorClose: "Most people think this means they need more discipline. But that's rarely the real problem.",
    problemHeadline: "Energy isn't about effort. It's about rhythm.",
    problemBody: "When your metabolic timing is disrupted, your body stops producing energy efficiently — no matter how hard you try to fix it.",
    problemItems: ["Unstable energy through the day", "Afternoon crashes that won't clear", "Slow mornings that never fully lift"],
    problemClose: "Fix the rhythm and energy returns quickly.",
    solutionSub: "A 7-day protocol for the Katsu type",
    solutionBody: "Designed around the specific metabolic pattern of Katsu types. One small adjustment per day. Seven days.",
    days: [
      ["Day 1", "Restore morning metabolic activation"],
      ["Day 2", "Stabilise blood sugar rhythm"],
      ["Day 3", "Correct the energy timing window"],
      ["Day 4", "Repair the afternoon crash cycle"],
      ["Day 5", "Support cellular energy production"],
      ["Day 6", "Restore evening recovery rhythm"],
      ["Day 7", "Lock in your stable energy pattern"],
    ],
    whyItems: [
      "Stabilise metabolic timing within 3–4 days",
      "Reduce daily energy crashes noticeably",
      "Restore your natural energy rhythm"
    ],
    whyClose: "Many people feel the difference within the first 3 days."
  },
  min: {
    kanji: '眠',
    name: 'Min — Rest',
    pillar: 'SLEEP · 睡眠 · 回復',
    tagline: "You're getting hours of sleep. You're just not recovering during them.",
    score: 43,
    scoreLabel: 'Recovery Score',
    hookBody: "Your score shows incomplete sleep recovery. This pattern compounds — every tired day makes the next one harder to restore.",
    mirrorIntro: "You probably recognise this:",
    mirrorItems: [
      "Waking up tired even after a full night's sleep",
      "A heaviness that doesn't lift until mid-morning",
      "Sleeping longer doesn't seem to help",
      "Your body feels like it skipped something overnight"
    ],
    mirrorClose: "Most people try sleeping more. But for the Min type, duration is rarely the issue.",
    problemHeadline: "Sleep isn't just hours. It's what happens during them.",
    problemBody: "There's a stage of sleep where the body does most of its repair. For Min types, something is quietly interrupting that stage.",
    problemItems: ["Waking without feeling restored", "Low physical energy through the morning", "Mental fog that takes hours to clear"],
    problemClose: "Restore that stage and everything else shifts.",
    solutionSub: "A 7-day protocol for the Min type",
    solutionBody: "Built around the specific sleep disruption pattern of Min types. One adjustment per evening. Seven days.",
    days: [
      ["Day 1", "Reset your body's sleep signal timing"],
      ["Day 2", "Stabilise blood sugar before bed"],
      ["Day 3", "Optimise your room temperature rhythm"],
      ["Day 4", "Remove the hidden stimulant patterns"],
      ["Day 5", "Restore the deep recovery stage"],
      ["Day 6", "Support overnight cellular repair"],
      ["Day 7", "Lock in your recovery pattern"],
    ],
    whyItems: [
      "Shift the quality — not just duration — of sleep",
      "Reduce morning heaviness within days",
      "Restore genuine overnight recovery"
    ],
    whyClose: "Most people notice a difference in how they wake up within 3 days."
  },
  wa: {
    kanji: '和',
    name: 'Wa — Washoku',
    pillar: 'NUTRITION · 栄養 · 和食',
    tagline: "You eat. But something is quietly not landing.",
    score: 45,
    scoreLabel: 'Nourishment Score',
    hookBody: "Your score shows an absorption imbalance. The gap between what you eat and what your body actually uses widens slowly — and quietly.",
    mirrorIntro: "You probably recognise this:",
    mirrorItems: [
      "Low energy after meals that should feel nourishing",
      "Eating well but not feeling the difference",
      "Afternoon heaviness that food doesn't fix",
      "A body that feels like it's working harder than it should"
    ],
    mirrorClose: "Most people eat better. For the Wa type, that's rarely what's missing.",
    problemHeadline: "Nourishment isn't just what you eat. It's what you absorb.",
    problemBody: "When your absorption patterns are disrupted, even good food fails to reach where it's needed. The gap is subtle — but it compounds.",
    problemItems: ["Energy that doesn't match your intake", "Afternoon heaviness after meals", "A body running below its potential"],
    problemClose: "Correct the absorption pattern and the gap closes quickly.",
    solutionSub: "A 7-day protocol for the Wa type",
    solutionBody: "Rooted in Japanese washoku principles, adapted for the specific absorption pattern of Wa types. One shift per day. Seven days.",
    days: [
      ["Day 1", "Restore morning digestive activation"],
      ["Day 2", "Correct key mineral absorption patterns"],
      ["Day 3", "Introduce washoku food pairing principles"],
      ["Day 4", "Shift meal timing for the Wa rhythm"],
      ["Day 5", "Support gut microbiome restoration"],
      ["Day 6", "Repair the energy-after-meals cycle"],
      ["Day 7", "Lock in your nourishment pattern"],
    ],
    whyItems: [
      "Close the gap between eating and absorbing",
      "Reduce post-meal heaviness noticeably",
      "Restore sustained energy from food"
    ],
    whyClose: "Most people notice improved energy after meals within 2–3 days."
  },
  zen: {
    kanji: '禅',
    name: 'Zen — Stillness',
    pillar: 'STRESS · 回復 · 禅',
    tagline: "You haven't switched off in a long time. Your body has been keeping score.",
    score: 49,
    scoreLabel: 'Clarity Score',
    hookBody: "Your score shows chronic nervous system overactivation. The longer this runs, the harder the off-switch becomes to find.",
    mirrorIntro: "You probably recognise this:",
    mirrorItems: [
      "Tired but unable to fully switch off",
      "A low-level tension that's become normal",
      "Rest that doesn't feel like rest",
      "A mind that keeps running even when you want it to stop"
    ],
    mirrorClose: "Most people try to relax more. For the Zen type, relaxation isn't the missing piece.",
    problemHeadline: "This isn't about stress. It's about a system that forgot how to stop.",
    problemBody: "Your nervous system has been running at low-level alarm for so long that its default state has shifted. Rest doesn't reach deep enough.",
    problemItems: ["Tiredness that sleep doesn't fix", "Tension that doesn't release with rest", "A baseline that feels higher than it should"],
    problemClose: "Retrain the default state and stillness returns.",
    solutionSub: "A 7-day protocol for the Zen type",
    solutionBody: "Drawn from Japanese stillness practices, adapted for the specific nervous system pattern of Zen types. One practice per day. Seven days.",
    days: [
      ["Day 1", "Reset the nervous system's baseline signal"],
      ["Day 2", "Restore key minerals depleted by chronic tension"],
      ["Day 3", "Introduce the Zen breathing pattern"],
      ["Day 4", "Remove hidden overstimulation sources"],
      ["Day 5", "Rebuild the body's recovery window"],
      ["Day 6", "Restore evening stillness rhythm"],
      ["Day 7", "Lock in your new nervous system baseline"],
    ],
    whyItems: [
      "Lower the body's default tension level",
      "Restore genuine rest within days",
      "Rebuild the off-switch that chronic stress erodes"
    ],
    whyClose: "Most people notice a quieter baseline within 3 days."
  }
};

// ── Detect type from URL or localStorage ──
const params = new URLSearchParams(window.location.search);
let type = params.get('type') || localStorage.getItem('ikiru_type') || 'katsu';
if (!LP_TYPES[type]) type = 'katsu';
const T = LP_TYPES[type];

// ── Render ──
function buildLP(type) { const T = LP_TYPES[type] || LP_TYPES['katsu']; return `

<!-- ① HOOK -->
<section>
  <span class="hook-type">${T.pillar}</span>
  <span class="hook-kanji" style="color:var(--gold)">${T.kanji}</span>
  <h1 class="hook-headline">"${T.tagline}"</h1>
  <div class="hook-score">
    <span class="hook-score-label">${T.scoreLabel}</span>
    <span class="hook-score-val">${T.score} / 100</span>
  </div>
  <p class="hook-body">${T.hookBody}</p>
  <div class="hook-good">
    The good news: this pattern can be reset.<br>
    <strong>In 7 days.</strong>
  </div>
</section>

<!-- ② DIAGNOSIS MIRROR -->
<section>
  <span class="eyebrow">Does this sound familiar</span>
  <p class="mirror-intro">${T.mirrorIntro}</p>
  <ul class="mirror-list">
    ${T.mirrorItems.map(i => `<li>${i}</li>`).join('')}
  </ul>
  <p class="mirror-close">${T.mirrorClose}</p>
</section>

<!-- ③ THE REAL PROBLEM -->
<section>
  <span class="eyebrow">The Real Problem</span>
  <h2 class="problem-headline">${T.problemHeadline}</h2>
  <p class="problem-body">${T.problemBody}</p>
  <div class="problem-result">
    <ul>
      ${T.problemItems.map(i => `<li>${i}</li>`).join('')}
    </ul>
  </div>
  <p class="problem-body" style="font-style:italic">${T.problemClose}</p>
</section>

<!-- ④ THE SOLUTION -->
<section>
  <span class="solution-label">The Solution</span>
  <h2 class="solution-name">IKIRU — 7-Day Reset</h2>
  <p class="solution-sub">${T.solutionSub}</p>
  <p class="solution-body">${T.solutionBody}</p>
  <p class="solution-body">Not a course. Not a challenge.</p>
  <div class="hook-good">A reset.</div>
  <div class="solution-tags">
    <span class="solution-tag">7 Days</span>
    <span class="solution-tag">1 Adjustment / Day</span>
    <span class="solution-tag">No Supplements</span>
    <span class="solution-tag">No Apps</span>
  </div>
</section>

<!-- ⑤ WHAT YOU GET -->
<section>
  <span class="eyebrow">Inside the Reset</span>
  <div class="days-grid">
    ${T.days.map(([d, t]) => `
    <div class="day-row">
      <span class="day-num">${d}</span>
      <span class="day-text">${t}</span>
    </div>`).join('')}
  </div>
</section>

<!-- ⑥ WHY 7 DAYS -->
<section>
  <span class="eyebrow">Why 7 Days Works</span>
  <p class="why-body">The body adapts quickly when the right signals return. Seven days is enough to:</p>
  <ul class="why-list">
    ${T.whyItems.map(i => `<li>${i}</li>`).join('')}
  </ul>
  <p class="why-close">${T.whyClose}</p>
</section>

<!-- ⑦ SIMPLE OFFER -->
<section class="offer-section">
  <span class="eyebrow">Start Your Reset</span>
  <h2 class="offer-name">IKIRU — 7-Day ${type.charAt(0).toUpperCase() + type.slice(1)} Reset</h2>
  <div class="offer-divider"></div>
  <div class="offer-meta">
    <div class="offer-meta-item">
      <span class="offer-meta-num">7</span>
      <span class="offer-meta-label">Days</span>
    </div>
    <div class="offer-meta-item">
      <span class="offer-meta-num">1</span>
      <span class="offer-meta-label">Daily shift</span>
    </div>
    <div class="offer-meta-item">
      <span class="offer-meta-num">0</span>
      <span class="offer-meta-label">Supplements</span>
    </div>
  </div>
  <div class="offer-divider"></div>
  <span class="offer-price">$47</span>
  <span class="offer-price-sub">One-time · Instant access</span>
  <a href="#" class="btn-buy">
    Start the 7-Day Reset →
    <span class="btn-buy-sub">Instant access · $47</span>
  </a>
  <p class="offer-note">No subscription · No supplements · Just the protocol</p>
</section>

`; }
function renderLP(type) {
  document.getElementById('lp-content').innerHTML = buildLP(type);
}
</script>

<!-- ══ LP: 7-DAY RESET ══ -->

<div class="screen" id="s-lp">
  <div class="lp-header">
    <span class="lp-brand">IKIRU</span>
    <span class="lp-brand-jp">生きる · The Japanese Art of Longevity</span>
  </div>
  <div class="lp-wrap" id="lp-content"></div>
</div>
</div><!-- /app -->
</body>
</html>

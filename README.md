<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday, Mas Yoga 💙</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Cinzel:wght@400;600&family=Jost:wght@200;300;400&display=swap" rel="stylesheet">
<style>
/* ===== ROOT & RESET ===== */
:root {
  --blue-deep:    #0a1f5c;
  --blue-mid:     #1a4daa;
  --blue-warm:    #2e6dd4;
  --blue-sky:     #5b9ee1;
  --blue-light:   #a8cef5;
  --blue-pale:    #dceeff;
  --blue-soft:    #4a90d9;
  --white:        #ffffff;
  --cream:        #fdfaf4;
  --ink:          #1a1a2e;
  --gold:         #c8a96e;
}
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html, body {
  width: 100%; height: 100%;
  overflow: hidden;
  font-family: 'Jost', sans-serif;
  -webkit-user-select: none;
  user-select: none;
}
/* Fix touch on Android webview */
button, .love-btn, .open-btn, .prayer-btn, .p4-next-btn, .next-letter-btn, .close-btn {
  -webkit-tap-highlight-color: transparent;
  touch-action: manipulation;
  cursor: pointer;
}

/* ===== PAGE SYSTEM ===== */
.page {
  position: fixed;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.8s cubic-bezier(.4,0,.2,1);
  z-index: 1;
}
.page.active {
  opacity: 1;
  pointer-events: all;
  z-index: 10;
}

/* ===== CANVAS (snow / particles) ===== */
canvas {
  position: absolute;
  inset: 0;
  pointer-events: none;
  z-index: 0;
}

/* ==========================================
   PAGE 1 — LANDING
   ========================================== */
#p1 {
  background: radial-gradient(ellipse at 60% 30%, #3a6fc4 0%, #1a3d8f 40%, #0a1f5c 100%);
}
#p1-content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0;
}
.p1-eyebrow {
  font-family: 'Cinzel', serif;
  font-size: clamp(9px, 2vw, 12px);
  letter-spacing: 6px;
  color: var(--blue-light);
  margin-bottom: 32px;
  opacity: .7;
}
.love-btn {
  background: none;
  border: none;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
  padding: 0;
  outline: none;
  -webkit-tap-highlight-color: transparent;
}
.love-btn-inner {
  position: relative;
  width: clamp(110px,28vw,150px);
  height: clamp(110px,28vw,150px);
  display: flex;
  align-items: center;
  justify-content: center;
}
/* Ripple rings */
.love-btn-inner::before,
.love-btn-inner::after {
  content: '';
  position: absolute;
  inset: -10px;
  border-radius: 50%;
  border: 1.5px solid rgba(90,160,230,.5);
  animation: ring 2.4s ease-out infinite;
}
.love-btn-inner::after {
  inset: -22px;
  border-color: rgba(90,160,230,.25);
  animation-delay: 1.2s;
}
@keyframes ring {
  0%   { transform: scale(.85); opacity: 1; }
  100% { transform: scale(1.15); opacity: 0; }
}
.love-circle {
  width: clamp(100px,26vw,140px);
  height: clamp(100px,26vw,140px);
  border-radius: 50%;
  background: radial-gradient(circle at 40% 35%, #2a5dc8, #0a1f5c);
  box-shadow:
    0 0 40px rgba(42,93,200,.6),
    0 0 80px rgba(42,93,200,.3),
    inset 0 1px 0 rgba(255,255,255,.15);
  display: flex;
  align-items: center;
  justify-content: center;
  animation: heartbeat 1.6s ease-in-out infinite;
  transition: transform .15s;
}
.love-btn:active .love-circle { transform: scale(.9); }
@keyframes heartbeat {
  0%,100% { transform: scale(1); box-shadow: 0 0 40px rgba(42,93,200,.6), 0 0 80px rgba(42,93,200,.3), inset 0 1px 0 rgba(255,255,255,.15); }
  14%      { transform: scale(1.14); box-shadow: 0 0 60px rgba(42,93,200,.9), 0 0 120px rgba(42,93,200,.5), inset 0 1px 0 rgba(255,255,255,.15); }
  28%      { transform: scale(1); }
  42%      { transform: scale(1.08); }
}
.love-icon {
  font-size: clamp(44px,11vw,58px);
  line-height: 1;
  color: #a8cef5;
  text-shadow: 0 0 20px rgba(168,206,245,.8);
  user-select: none;
}
.love-label {
  font-family: 'Cinzel', serif;
  font-size: clamp(13px,3.5vw,17px);
  letter-spacing: 5px;
  color: var(--blue-light);
  font-weight: 600;
}
.tap-hint {
  margin-top: 28px;
  font-family: 'Jost', sans-serif;
  font-weight: 200;
  font-size: clamp(10px, 2.4vw, 13px);
  letter-spacing: 4px;
  color: rgba(168,206,245,.6);
  text-transform: lowercase;
  animation: blink 2.4s ease-in-out infinite;
}
@keyframes blink { 0%,100%{opacity:.7} 50%{opacity:.2} }

/* ==========================================
   PAGE 2 — LOADING
   ========================================== */
#p2 {
  background: radial-gradient(ellipse at 50% 50%, #1e4fa8 0%, #0e2d7a 50%, #06144a 100%);
}
#p2-content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 28px;
}
.loader-ring {
  width: 70px;
  height: 70px;
  position: relative;
}
.loader-ring svg {
  width: 100%; height: 100%;
  animation: spin 1.2s linear infinite;
}
@keyframes spin { to { transform: rotate(360deg); } }
.loader-ring svg circle {
  fill: none;
  stroke-width: 3.5;
  stroke-linecap: round;
}
.loader-ring .track { stroke: rgba(168,206,245,.2); }
.loader-ring .fill  { stroke: #a8cef5; stroke-dasharray: 120; stroke-dashoffset: 35; }
.loading-text {
  font-family: 'Cormorant Garamond', serif;
  font-style: italic;
  font-size: clamp(18px,5vw,24px);
  color: var(--blue-light);
  letter-spacing: 2px;
}
.loading-sub {
  font-family: 'Jost', sans-serif;
  font-weight: 200;
  font-size: clamp(10px,2.5vw,13px);
  letter-spacing: 4px;
  color: rgba(168,206,245,.5);
  text-transform: uppercase;
}
.progress-bar-wrap {
  width: clamp(160px,50vw,260px);
  height: 2px;
  background: rgba(168,206,245,.15);
  border-radius: 2px;
  overflow: hidden;
}
.progress-bar-fill {
  height: 100%;
  width: 0%;
  background: linear-gradient(90deg, #4a90d9, #a8cef5);
  border-radius: 2px;
  transition: width .3s ease;
}

/* ==========================================
   PAGE 3 — MESSAGE
   ========================================== */
#p3 {
  background: radial-gradient(ellipse at 40% 40%, #4a8fd4 0%, #2264b8 45%, #1245a0 100%);
}
#p3-content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 36px;
  padding: 20px;
  max-width: 520px;
  width: 100%;
}
.p3-message {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(22px,6.5vw,38px);
  color: var(--white);
  line-height: 1.45;
  text-align: center;
  min-height: 1.45em;
  text-shadow: 0 2px 20px rgba(0,0,0,.25);
  letter-spacing: .5px;
}
.cursor-blink {
  display: inline-block;
  width: 2px;
  height: 1em;
  background: rgba(255,255,255,.8);
  margin-left: 2px;
  vertical-align: middle;
  animation: cursor 0.8s step-end infinite;
}
@keyframes cursor { 0%,100%{opacity:1} 50%{opacity:0} }

.open-btn {
  font-family: 'Cinzel', serif;
  font-size: clamp(12px,3vw,15px);
  letter-spacing: 5px;
  color: var(--blue-deep);
  background: var(--white);
  border: none;
  padding: 16px 42px;
  border-radius: 60px;
  cursor: pointer;
  box-shadow: 0 8px 32px rgba(0,0,0,.25), 0 0 0 0 rgba(255,255,255,.4);
  transition: all .25s;
  opacity: 0;
  transform: translateY(12px);
  pointer-events: none;
}
.open-btn.visible {
  opacity: 1;
  transform: translateY(0);
  pointer-events: all;
  animation: btnGlow 2.5s ease-in-out infinite;
}
@keyframes btnGlow {
  0%,100% { box-shadow: 0 8px 32px rgba(0,0,0,.25); }
  50%      { box-shadow: 0 8px 32px rgba(0,0,0,.25), 0 0 0 8px rgba(255,255,255,.12); }
}
.open-btn:hover { background: #f0f7ff; transform: translateY(-2px); }
.open-btn:active { transform: translateY(1px); }

/* ==========================================
   POPUP / LETTER
   ========================================== */
.overlay {
  position: fixed;
  inset: 0;
  background: rgba(6,20,74,.75);
  backdrop-filter: blur(8px);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 200;
  opacity: 0;
  pointer-events: none;
  transition: opacity .4s;
}
.overlay.show { opacity: 1; pointer-events: all; }

.envelope-wrap {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Envelope body */
.letter-card {
  width: min(88vw, 400px);
  max-height: 75vh;
  background: var(--cream);
  border-radius: 4px 4px 6px 6px;
  padding: 44px 32px 32px;
  position: relative;
  box-shadow: 0 24px 80px rgba(0,0,0,.55);
  animation: letterPop .45s cubic-bezier(.34,1.56,.64,1) both;
  display: flex;
  flex-direction: column;
}
@keyframes letterPop {
  from { transform: scale(.7) translateY(30px); opacity: 0; }
  to   { transform: scale(1)  translateY(0);    opacity: 1; }
}

/* Envelope flap (triangle top) */
.letter-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 0;
  border-left:  calc(min(88vw, 400px)/2) solid transparent;
  border-right: calc(min(88vw, 400px)/2) solid transparent;
  border-top:   46px solid #c8dff8;
  border-radius: 4px 4px 0 0;
}
/* Bottom envelope flap */
.letter-card::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 0;
  border-left:  calc(min(88vw, 400px)/2) solid transparent;
  border-right: calc(min(88vw, 400px)/2) solid transparent;
  border-bottom: 36px solid #d8eafc;
  border-radius: 0 0 6px 6px;
}
/* Wax seal decoration */
.wax-seal {
  position: absolute;
  top: 16px;
  left: 50%;
  transform: translateX(-50%);
  width: 30px;
  height: 30px;
  background: radial-gradient(circle at 40% 35%, #3a6fc4, #0a1f5c);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 13px;
  box-shadow: 0 2px 8px rgba(0,0,0,.3);
  z-index: 5;
}

.letter-body {
  position: relative;
  z-index: 2;
  padding-bottom: 16px;
  overflow-y: auto;
  overflow-x: hidden;
  flex: 1;
  /* Scrollbar styling */
  scrollbar-width: thin;
  scrollbar-color: rgba(26,77,170,.3) transparent;
  -webkit-overflow-scrolling: touch;
}
.letter-body::-webkit-scrollbar { width: 4px; }
.letter-body::-webkit-scrollbar-track { background: transparent; }
.letter-body::-webkit-scrollbar-thumb { background: rgba(26,77,170,.3); border-radius: 4px; }
/* Fade hint at bottom to show scrollable */
.letter-card .scroll-hint {
  position: absolute;
  bottom: 36px;
  left: 0; right: 0;
  height: 40px;
  background: linear-gradient(to bottom, transparent, rgba(253,250,244,.95));
  pointer-events: none;
  z-index: 3;
  border-radius: 0 0 6px 6px;
  transition: opacity .3s;
}
.letter-text {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(14px,3.8vw,18px);
  color: var(--ink);
  line-height: 1.9;
  text-align: center;
  min-height: 2em;
  font-style: italic;
  white-space: pre-wrap;
  word-break: break-word;
}
.letter-line {
  width: 40px;
  height: 1px;
  background: var(--blue-mid);
  margin: 16px auto 0;
  opacity: .3;
}

.close-btn {
  position: absolute;
  top: 10px;
  right: 14px;
  width: 28px; height: 28px;
  border-radius: 50%;
  border: 1px solid rgba(26,77,170,.3);
  background: transparent;
  color: var(--blue-mid);
  font-size: 14px;
  cursor: pointer;
  display: flex; align-items: center; justify-content: center;
  transition: all .2s;
  z-index: 10;
}
.close-btn:hover { background: var(--blue-mid); color: white; }

.next-letter-btn {
  margin-top: 20px;
  font-family: 'Cinzel', serif;
  font-size: clamp(10px,2.5vw,12px);
  letter-spacing: 4px;
  color: white;
  background: var(--blue-mid);
  border: none;
  padding: 13px 32px;
  border-radius: 40px;
  cursor: pointer;
  box-shadow: 0 4px 16px rgba(26,77,170,.4);
  transition: all .2s;
  opacity: 0;
  pointer-events: none;
}
.next-letter-btn.visible { opacity: 1; pointer-events: all; }
.next-letter-btn:hover { background: var(--blue-deep); transform: translateY(-2px); }

/* ==========================================
   PAGE 4 — PRAYERS
   ========================================== */
#p4 {
  background: radial-gradient(ellipse at 50% 20%, #7ab8e8 0%, #3e85c8 40%, #1d5fa8 100%);
}
#p4-content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 32px;
  padding: 20px;
  width: 100%;
  max-width: 400px;
}
.p4-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(19px,5.5vw,28px);
  color: var(--white);
  font-style: italic;
  text-align: center;
  letter-spacing: 1px;
  text-shadow: 0 2px 16px rgba(0,0,0,.2);
}
.p4-title span {
  display: block;
  font-family: 'Cinzel', serif;
  font-style: normal;
  font-size: .55em;
  letter-spacing: 5px;
  color: var(--blue-pale);
  margin-bottom: 6px;
  opacity: .8;
}
.prayer-btns {
  display: flex;
  flex-direction: column;
  gap: 14px;
  width: 100%;
}
.prayer-btn {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 18px 24px;
  background: rgba(255,255,255,.15);
  border: 1px solid rgba(255,255,255,.3);
  border-radius: 14px;
  cursor: pointer;
  backdrop-filter: blur(10px);
  transition: all .25s;
  width: 100%;
  text-align: left;
}
.prayer-btn:hover {
  background: rgba(255,255,255,.28);
  border-color: rgba(255,255,255,.6);
  transform: translateX(4px);
  box-shadow: 0 8px 24px rgba(0,0,0,.15);
}
.prayer-btn:active { transform: translateX(2px) scale(.98); }
.prayer-icon {
  font-size: 26px;
  line-height: 1;
  filter: drop-shadow(0 2px 4px rgba(0,0,0,.2));
  flex-shrink: 0;
}
.prayer-label {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(15px,4vw,19px);
  color: white;
  font-style: italic;
  letter-spacing: .5px;
}
.prayer-sub {
  font-family: 'Jost', sans-serif;
  font-weight: 200;
  font-size: 10px;
  letter-spacing: 3px;
  color: rgba(255,255,255,.6);
  text-transform: uppercase;
  margin-top: 2px;
}
.p4-next-btn {
  font-family: 'Cinzel', serif;
  font-size: clamp(10px,2.5vw,12px);
  letter-spacing: 4px;
  color: var(--blue-deep);
  background: white;
  border: none;
  padding: 14px 36px;
  border-radius: 50px;
  cursor: pointer;
  box-shadow: 0 6px 20px rgba(0,0,0,.2);
  transition: all .2s;
  margin-top: 6px;
}
.p4-next-btn:hover { background: var(--blue-pale); transform: translateY(-2px); }

/* Small prayer popup letter */
#prayer-popup .letter-card {
  padding: 50px 28px 28px;
}
#prayer-popup .letter-text { font-size: clamp(15px,4.5vw,21px); }

/* ==========================================
   PAGE 5 — FINALE
   ========================================== */
#p5 {
  background: radial-gradient(ellipse at 60% 30%, #3a6fc4 0%, #1a3d8f 40%, #0a1f5c 100%);
}
#p5-content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
  padding: 24px;
  text-align: center;
}
.finale-eyebrow {
  font-family: 'Jost', sans-serif;
  font-weight: 200;
  font-size: clamp(10px,2.5vw,12px);
  letter-spacing: 6px;
  color: rgba(168,206,245,.5);
  text-transform: uppercase;
}
.finale-text {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(26px,7.5vw,48px);
  font-weight: 600;
  color: white;
  line-height: 1.3;
  text-shadow: 0 0 40px rgba(90,158,225,.5), 0 2px 20px rgba(0,0,0,.3);
  letter-spacing: 1px;
  min-height: 1.3em;
  max-width: 420px;
}
.finale-sub {
  font-family: 'Cormorant Garamond', serif;
  font-style: italic;
  font-size: clamp(14px,3.8vw,19px);
  color: var(--blue-light);
  letter-spacing: 1px;
  opacity: 0;
  transition: opacity 1.2s;
}
.finale-sub.show { opacity: 1; }
.finale-hearts {
  font-size: clamp(22px,6vw,32px);
  opacity: 0;
  transition: opacity 1s .3s;
  filter: drop-shadow(0 0 10px rgba(168,206,245,.6));
  letter-spacing: 8px;
}
.finale-hearts.show { opacity: 1; }

/* ===== UTILITIES ===== */
.hidden { display: none !important; }

/* ===== BACK BUTTON ===== */
.back-btn {
  position: fixed;
  top: 20px;
  left: 20px;
  z-index: 50;
  background: rgba(255,255,255,.15);
  border: 1px solid rgba(255,255,255,.3);
  color: white;
  width: 42px;
  height: 42px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  backdrop-filter: blur(8px);
  font-size: 18px;
  transition: all .25s;
  opacity: 0;
  pointer-events: none;
  -webkit-tap-highlight-color: transparent;
  touch-action: manipulation;
}
.back-btn.visible {
  opacity: 1;
  pointer-events: all;
}
.back-btn:hover {
  background: rgba(255,255,255,.28);
  border-color: rgba(255,255,255,.6);
  transform: translateX(-2px);
}
.back-btn:active { transform: scale(.9); }

/* ===== MUSIC PLAYER ===== */
#music-btn {
  position: fixed;
  bottom: 22px;
  right: 22px;
  z-index: 9999;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background: rgba(255,255,255,.18);
  border: 1.5px solid rgba(255,255,255,.35);
  color: white;
  font-size: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  backdrop-filter: blur(10px);
  box-shadow: 0 4px 20px rgba(0,0,0,.25);
  transition: all .25s;
  -webkit-tap-highlight-color: transparent;
  touch-action: manipulation;
}
#music-btn:hover {
  background: rgba(255,255,255,.30);
  transform: scale(1.08);
}
#music-btn:active { transform: scale(.92); }
#music-btn.playing {
  animation: musicPulse 2s ease-in-out infinite;
  background: rgba(90,158,225,.35);
  border-color: rgba(168,206,245,.6);
}
@keyframes musicPulse {
  0%,100% { box-shadow: 0 4px 20px rgba(0,0,0,.25), 0 0 0 0 rgba(168,206,245,.4); }
  50%      { box-shadow: 0 4px 20px rgba(0,0,0,.25), 0 0 0 10px rgba(168,206,245,0); }
}
/* Music note animation when playing */
#music-icon { display: inline-block; transition: transform .2s; }
#music-btn.playing #music-icon {
  animation: noteBounce 1.2s ease-in-out infinite alternate;
}
@keyframes noteBounce {
  0%   { transform: rotate(-12deg) scale(1);   }
  100% { transform: rotate( 12deg) scale(1.15); }
}

/* Toast hint on first visit */
#music-toast {
  position: fixed;
  bottom: 82px;
  right: 22px;
  z-index: 9998;
  background: rgba(10,31,92,.88);
  border: 1px solid rgba(168,206,245,.3);
  color: var(--blue-light);
  font-family: 'Jost', sans-serif;
  font-weight: 300;
  font-size: 11px;
  letter-spacing: 2px;
  padding: 8px 14px;
  border-radius: 20px;
  backdrop-filter: blur(10px);
  white-space: nowrap;
  opacity: 0;
  transform: translateY(6px);
  transition: opacity .4s, transform .4s;
  pointer-events: none;
}
#music-toast.show { opacity: 1; transform: translateY(0); }
</style>
</head>
<body>

<!-- BACK BUTTON (global, shown on pages 2-5) -->
<button class="back-btn" id="back-btn">&#8592;</button>

<!-- AUDIO BACKSOUND -->
<audio id="bgMusic" loop preload="auto">
  <source src="Nadhif_Basalamah_-_bergema_sampai_selamanya_Official_Lyric_Video.mp3" type="audio/mpeg">
</audio>

<!-- MUSIC TOGGLE BUTTON -->
<button id="music-btn" title="Play / Pause musik">
  <span id="music-icon">♪</span>
</button>
<div id="music-toast">♪ tap untuk musik</div>

<!-- ===================== PAGE 1 ===================== -->
<div id="p1" class="page active">
  <canvas id="snow-canvas"></canvas>
  <div id="p1-content">
    <div class="p1-eyebrow">untuk seseorang yang istimewa</div>
    <button class="love-btn" id="love-btn">
      <div class="love-btn-inner">
        <div class="love-circle">
          <span class="love-icon">♥</span>
        </div>
      </div>
      <span class="love-label">LOVE</span>
    </button>
    <div class="tap-hint">tap to open</div>
  </div>
</div>

<!-- ===================== PAGE 2 ===================== -->
<div id="p2" class="page">
  <div id="p2-content">
    <div class="loader-ring">
      <svg viewBox="0 0 36 36">
        <circle class="track" cx="18" cy="18" r="15.9"/>
        <circle class="fill"  cx="18" cy="18" r="15.9"/>
      </svg>
    </div>
    <div>
      <div class="loading-text">Loading, please wait...</div>
      <div class="loading-sub" style="margin-top:6px">preparing something special</div>
    </div>
    <div class="progress-bar-wrap">
      <div class="progress-bar-fill" id="progress-fill"></div>
    </div>
  </div>
</div>


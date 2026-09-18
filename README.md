<html lang="id" data-theme="dark">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Daftar Akun — By Fanzxy Modz</title>
<style>
/* ============================================================
   TEMA
============================================================ */
:root[data-theme="dark"] {
  --bg-1:#0b1120; --bg-2:#1e293b;
  --card-bg: rgba(30,41,59,.72);
  --card-border: rgba(96,165,250,.15);
  --text:#f1f5f9; --text-muted:#94a3b8; --text-dim:#64748b;
  --input-bg: rgba(15,23,42,.7);
  --input-border:#334155;
  --input-text:#fff;
  --primary:#3b82f6; --primary-hover:#2563eb;
  --primary-glow: rgba(59,130,246,.5);
  --accent:#8b5cf6;
  --success:#22c55e; --error:#ef4444; --warning:#fbbf24;
  --shadow: 0 20px 60px rgba(0,0,0,.55);
  --shadow-glow: 0 0 40px rgba(59,130,246,.15);
  --overlay: rgba(2,6,23,.82);
  --modal-bg: rgba(30,41,59,.95);
  --modal-border: rgba(96,165,250,.2);
  --divider: rgba(51,65,85,.6);
  --particle: rgba(147,197,253,.5);
}
:root[data-theme="light"] {
  --bg-1:#eff6ff; --bg-2:#dbeafe;
  --card-bg: rgba(255,255,255,.78);
  --card-border: rgba(59,130,246,.18);
  --text:#0f172a; --text-muted:#475569; --text-dim:#64748b;
  --input-bg: rgba(248,250,252,.9);
  --input-border:#cbd5e1;
  --input-text:#0f172a;
  --primary:#2563eb; --primary-hover:#1d4ed8;
  --primary-glow: rgba(37,99,235,.35);
  --accent:#7c3aed;
  --success:#16a34a; --error:#dc2626; --warning:#d97706;
  --shadow: 0 20px 60px rgba(15,23,42,.15);
  --shadow-glow: 0 0 40px rgba(37,99,235,.15);
  --overlay: rgba(15,23,42,.5);
  --modal-bg: rgba(255,255,255,.97);
  --modal-border: rgba(59,130,246,.25);
  --divider: rgba(203,213,225,.7);
  --particle: rgba(37,99,235,.4);
}

/* ============================================================
   BASE
============================================================ */
* { margin:0; padding:0; box-sizing:border-box;
    font-family: system-ui,-apple-system,"Segoe UI",sans-serif;
    -webkit-tap-highlight-color: transparent; }
html, body { height:100%; overflow-x:hidden; }
body {
  min-height: 100vh;
  display:flex; align-items:center; justify-content:center;
  background: radial-gradient(circle at 30% 20%, var(--bg-2), var(--bg-1) 70%);
  color: var(--text);
  padding: 1rem;
  transition: background .8s cubic-bezier(.4,0,.2,1), color .5s ease;
  position: relative;
  perspective: 1200px;
}

/* ============================================================
   AURORA
============================================================ */
.aurora {
  position: fixed; inset:-30%; z-index:0;
  background:
    radial-gradient(circle at 20% 30%, #3b82f6 0%, transparent 45%),
    radial-gradient(circle at 80% 60%, #8b5cf6 0%, transparent 45%),
    radial-gradient(circle at 50% 90%, #06b6d4 0%, transparent 45%);
  filter: blur(90px); opacity:.35;
  animation: auroraFloat 24s ease-in-out infinite;
  pointer-events:none;
}
@keyframes auroraFloat {
  0%,100% { transform: translate(0,0) scale(1) rotate(0deg); }
  33%     { transform: translate(6%,-4%) scale(1.08) rotate(8deg); }
  66%     { transform: translate(-5%,5%) scale(.95) rotate(-6deg); }
}
#particles { position: fixed; inset:0; z-index:1; pointer-events:none; opacity:.7; }
[data-theme="light"] #particles { opacity:.5; }

/* ============================================================
   THEME TOGGLE
============================================================ */
.theme-toggle {
  position: fixed; top: 1rem; right: 1rem;
  width: 52px; height: 52px; border-radius: 50%;
  border: 1px solid var(--card-border);
  background: var(--card-bg);
  backdrop-filter: blur(14px); -webkit-backdrop-filter: blur(14px);
  cursor: pointer;
  display:flex; align-items:center; justify-content:center;
  font-size: 1.4rem; box-shadow: var(--shadow);
  z-index: 200;
  transition: transform .55s cubic-bezier(.34,1.56,.64,1), box-shadow .35s ease;
  overflow:hidden;
}
.theme-toggle:hover { transform: scale(1.12) rotate(180deg); box-shadow: var(--shadow), 0 0 30px var(--primary-glow); }
.theme-toggle:active { transform: scale(.9) rotate(180deg); }
.theme-toggle .icon { position:absolute; transition: transform .6s cubic-bezier(.34,1.56,.64,1), opacity .4s ease; }
.theme-toggle .icon-sun  { transform: rotate(0deg) scale(1); opacity:1; }
.theme-toggle .icon-moon { transform: rotate(-120deg) scale(0); opacity:0; }
[data-theme="light"] .theme-toggle .icon-sun  { transform: rotate(120deg) scale(0); opacity:0; }
[data-theme="light"] .theme-toggle .icon-moon { transform: rotate(0deg) scale(1); opacity:1; }

/* ============================================================
   CARD
============================================================ */
.card-wrap {
  position: relative; z-index: 2;
  width:100%; max-width:440px;
  transform-style: preserve-3d;
  transition: transform .35s cubic-bezier(.2,.8,.2,1);
}
.card {
  position: relative;
  background: var(--card-bg);
  backdrop-filter: blur(24px) saturate(1.4);
  -webkit-backdrop-filter: blur(24px) saturate(1.4);
  padding: 2.25rem 2rem;
  border-radius: 24px; width: 100%;
  box-shadow: var(--shadow), var(--shadow-glow);
  border: 1px solid var(--card-border);
  overflow: hidden;
  animation: cardIn .9s cubic-bezier(.34,1.56,.64,1) both;
}
.card::before {
  content:""; position:absolute; inset:-1px;
  border-radius: 24px; padding: 1px;
  background: linear-gradient(120deg, transparent, var(--accent), var(--primary), transparent);
  background-size: 300% 300%;
  -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
  -webkit-mask-composite: xor; mask-composite: exclude;
  opacity:.7; animation: borderFlow 6s linear infinite;
  pointer-events:none;
}
@keyframes borderFlow { 0% { background-position: 0% 50%; } 100% { background-position: 300% 50%; } }
.card::after {
  content:""; position:absolute; top:-50%; left:-60%;
  width:60%; height:200%;
  background: linear-gradient(105deg, transparent 40%, rgba(255,255,255,.08) 50%, transparent 60%);
  transform: rotate(12deg);
  animation: shine 7s ease-in-out infinite;
  pointer-events:none;
}
@keyframes shine {
  0%,70% { transform: translateX(-100%) rotate(12deg); }
  100%   { transform: translateX(350%) rotate(12deg); }
}
@keyframes cardIn {
  0%   { opacity:0; transform: translateY(40px) scale(.92) rotateX(-10deg); }
  60%  { opacity:1; }
  100% { opacity:1; transform: translateY(0) scale(1) rotateX(0); }
}
.card h1 {
  margin-bottom: .4rem; font-size: 1.75rem; text-align:center;
  background: linear-gradient(120deg, var(--accent), var(--primary), var(--accent));
  background-size: 200% auto;
  -webkit-background-clip: text; background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 800; letter-spacing: -0.5px;
  animation: gradientShift 4s linear infinite, fadeSlide .8s cubic-bezier(.34,1.56,.64,1) .15s both;
}
@keyframes gradientShift { to { background-position: 200% center; } }
@keyframes fadeSlide {
  from { opacity:0; transform: translateY(14px); }
  to   { opacity:1; transform: translateY(0); }
}
.subtitle {
  text-align:center; font-size:.8rem; color: var(--text-dim);
  margin-bottom: 1.5rem;
  animation: fadeSlide .6s ease .25s both;
}

/* ============================================================
   FLOATING LABEL
============================================================ */
.field { position: relative; margin-bottom: 1.1rem; animation: fadeSlide .6s cubic-bezier(.34,1.56,.64,1) both; }
.field:nth-of-type(1) { animation-delay: .2s; }
.field:nth-of-type(2) { animation-delay: .3s; }
.field:nth-of-type(3) { animation-delay: .4s; }
.field input {
  width:100%; padding: 1.15rem 1rem .55rem;
  border-radius: 14px;
  border: 1.5px solid var(--input-border);
  background: var(--input-bg);
  color: var(--input-text);
  font-size: 1rem;
  transition: border-color .35s ease, box-shadow .35s ease, background .35s ease, transform .35s cubic-bezier(.34,1.56,.64,1);
  outline:none;
}
.field input:focus {
  border-color: var(--primary);
  box-shadow: 0 0 0 4px var(--primary-glow);
  transform: translateY(-2px);
}
.field label {
  position:absolute; left: 1rem; top: 50%;
  transform: translateY(-50%);
  color: var(--text-dim); font-size: 1rem;
  pointer-events:none;
  transition: all .35s cubic-bezier(.34,1.56,.64,1);
  padding: 0 .35rem;
}
.field input:focus + label,
.field input:not(:placeholder-shown) + label {
  top: 0; font-size: .72rem; color: var(--primary);
  background: var(--card-bg); border-radius: 6px;
  font-weight: 700; letter-spacing: .5px;
  transform: translateY(-50%) translateX(4px);
}
.hint {
  font-size: .72rem; color: var(--text-dim);
  margin: -0.6rem 0 0.9rem 0.3rem;
  display:flex; align-items:center; gap:.35rem;
  animation: fadeSlide .5s ease .45s both;
}

/* ============================================================
   INFO BOX — Role & Expired otomatis
============================================================ */
.auto-info {
  background: linear-gradient(120deg, rgba(59,130,246,.1), rgba(139,92,246,.1));
  border: 1px solid rgba(139,92,246,.35);
  border-radius: 14px;
  padding: 1rem; margin-bottom: 1.35rem;
  display: grid; grid-template-columns: 1fr 1fr; gap: .75rem;
  animation: fadeSlide .6s cubic-bezier(.34,1.56,.64,1) .5s both;
  position: relative; overflow: hidden;
}
.auto-info::before {
  content:""; position:absolute; inset:0;
  background: linear-gradient(90deg, transparent, rgba(139,92,246,.15), transparent);
  transform: translateX(-100%);
  animation: infoSweep 3.5s ease-in-out infinite;
}
@keyframes infoSweep {
  0%, 60% { transform: translateX(-100%); }
  100%    { transform: translateX(100%); }
}
.auto-item { display:flex; flex-direction:column; gap:.15rem; position: relative; z-index: 1; }
.auto-item .auto-lbl {
  font-size:.68rem; color: var(--text-dim);
  text-transform: uppercase; letter-spacing: .8px; font-weight: 700;
}
.auto-item .auto-val {
  font-size:.9rem; font-weight: 800;
  display:flex; align-items:center; gap:.35rem;
}
.auto-item .role-free {
  color: #22c55e;
  text-shadow: 0 0 12px rgba(34,197,94,.4);
}
.auto-item .exp-days {
  color: var(--warning);
  text-shadow: 0 0 12px rgba(251,191,36,.3);
}

/* ============================================================
   BUTTON REGISTER
============================================================ */
.btn-submit {
  position: relative; width:100%; padding: 1rem;
  border: none; border-radius: 14px; cursor: pointer;
  background: linear-gradient(120deg, var(--accent), var(--primary), var(--accent));
  background-size: 220% auto;
  color:#fff; font-weight: 800; font-size: 1rem; letter-spacing: .5px;
  overflow: hidden;
  display:flex; align-items:center; justify-content:center; gap:.6rem;
  box-shadow: 0 8px 24px rgba(139,92,246,.4);
  transition: transform .4s cubic-bezier(.34,1.56,.64,1), box-shadow .4s ease, filter .3s ease;
  animation: fadeSlide .6s cubic-bezier(.34,1.56,.64,1) .55s both, gradientShift 4s linear infinite;
}
.btn-submit:hover:not(:disabled) {
  transform: translateY(-3px) scale(1.02);
  box-shadow: 0 14px 36px rgba(139,92,246,.6), 0 0 24px rgba(139,92,246,.4);
  filter: brightness(1.1);
}
.btn-submit:active:not(:disabled) { transform: translateY(0) scale(.97); }
.btn-submit:disabled { cursor:not-allowed; opacity:.9; }
.btn-submit::after {
  content:""; position:absolute; top:0; left:-100%;
  width: 60%; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,.35), transparent);
  transform: skewX(-20deg);
  animation: btnShine 3s ease-in-out infinite;
}
@keyframes btnShine { 0%, 60% { left: -100%; } 100% { left: 150%; } }
.spinner {
  width: 18px; height: 18px;
  border: 2.5px solid rgba(255,255,255,.35);
  border-top-color: #fff;
  border-radius: 50%;
  animation: spin .7s linear infinite;
  display:none;
}
@keyframes spin { to { transform: rotate(360deg); } }
.btn-submit.loading .spinner { display:inline-block; }

/* ============================================================
   TOAST
============================================================ */
.msg {
  margin-top: 0; padding: 0 1rem; max-height: 0;
  border-radius: 12px; font-size: .875rem; text-align:center; line-height:1.5;
  opacity:0; transform: translateY(-10px) scale(.95);
  overflow:hidden;
  transition: all .55s cubic-bezier(.34,1.56,.64,1);
  border: 1px solid transparent;
}
.msg.show {
  opacity:1; transform: translateY(0) scale(1);
  max-height: 200px; padding: .95rem 1rem; margin-top: 1rem;
}
.msg.error {
  background: rgba(239,68,68,.14);
  border-color: rgba(239,68,68,.5);
  color:#fca5a5;
  box-shadow: 0 0 24px rgba(239,68,68,.15);
}
[data-theme="light"] .msg.error { color:#b91c1c; }
.msg.success {
  background: rgba(34,197,94,.14);
  border-color: rgba(34,197,94,.5);
  color:#86efac;
  box-shadow: 0 0 24px rgba(34,197,94,.15);
}
[data-theme="light"] .msg.success { color:#15803d; }
.msg.info {
  background: rgba(59,130,246,.14);
  border-color: rgba(59,130,246,.5);
  color:#93c5fd;
}
[data-theme="light"] .msg.info { color:#1d4ed8; }

/* ============================================================
   BOTTOM LINK
============================================================ */
.bottom-link {
  text-align:center; margin-top: 1.4rem;
  font-size: .875rem; color: var(--text-dim);
  animation: fadeSlide .6s ease .65s both;
}
.bottom-link a {
  color: var(--primary); text-decoration:none; font-weight: 700;
  transition: all .3s ease; position: relative;
}
.bottom-link a:hover { color: var(--accent); }
.bottom-link a::after {
  content:""; position:absolute;
  left:0; bottom:-2px; width: 100%; height: 2px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  transform: scaleX(0); transform-origin: left;
  transition: transform .35s cubic-bezier(.34,1.56,.64,1);
  border-radius: 2px;
}
.bottom-link a:hover::after { transform: scaleX(1); }
.info-footer {
  margin-top: 1rem; font-size: .72rem;
  color: var(--text-dim); text-align:center;
}
.info-footer b {
  background: linear-gradient(120deg, var(--primary), var(--accent));
  -webkit-background-clip: text; background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 800;
}

/* ============================================================
   MODAL SUKSES
============================================================ */
.modal-overlay {
  position: fixed; inset:0;
  background: var(--overlay);
  display:flex; align-items:center; justify-content:center;
  padding: 1rem; z-index: 999;
  opacity:0; pointer-events:none;
  backdrop-filter: blur(0px); -webkit-backdrop-filter: blur(0px);
  transition: opacity .45s ease, backdrop-filter .45s ease;
}
.modal-overlay.show {
  opacity:1; pointer-events:auto;
  backdrop-filter: blur(8px); -webkit-backdrop-filter: blur(8px);
}
.modal {
  background: var(--modal-bg);
  border: 1px solid rgba(34,197,94,.35);
  border-radius: 24px;
  width:100%; max-width:420px;
  padding: 2rem 1.75rem;
  box-shadow: var(--shadow), 0 0 60px rgba(34,197,94,.25);
  transform: scale(.7) translateY(40px) rotateX(20deg);
  opacity:0;
  transition: transform .6s cubic-bezier(.34,1.56,.64,1), opacity .35s ease;
  position: relative; overflow:hidden;
  text-align: center;
}
.modal-overlay.show .modal { transform: scale(1) translateY(0) rotateX(0); opacity:1; }
.modal .check {
  width: 76px; height: 76px;
  margin: 0 auto 1rem;
  border-radius: 50%;
  background: linear-gradient(135deg, #16a34a, #22c55e);
  display:flex; align-items:center; justify-content:center;
  font-size: 2.2rem;
  box-shadow: 0 0 40px rgba(34,197,94,.5);
  animation: checkPop .8s cubic-bezier(.34,1.56,.64,1) .2s both;
}
@keyframes checkPop {
  0%   { transform: scale(0) rotate(-180deg); }
  60%  { transform: scale(1.15) rotate(10deg); }
  100% { transform: scale(1) rotate(0); }
}
.modal h2 {
  font-size: 1.2rem; margin-bottom: .5rem;
  color: #22c55e; font-weight: 800;
  animation: fadeSlide .6s ease .3s both;
}
.modal p {
  font-size: .875rem; color: var(--text-muted);
  margin-bottom: 1.25rem;
  animation: fadeSlide .6s ease .4s both;
}
.modal .detail {
  background: rgba(34,197,94,.08);
  border: 1px solid rgba(34,197,94,.25);
  border-radius: 12px;
  padding: .9rem; margin-bottom: 1.25rem;
  text-align: left;
  animation: fadeSlide .6s ease .5s both;
}
.modal .detail-row {
  display:flex; justify-content:space-between;
  padding: .35rem 0; font-size: .85rem;
}
.modal .detail-row span:first-child { color: var(--text-muted); }
.modal .detail-row span:last-child  { color: var(--text); font-weight: 700; }
.modal .btn-ok {
  width: 100%; padding: .95rem;
  border-radius: 14px; border: none;
  background: linear-gradient(120deg, #16a34a, #22c55e, #16a34a);
  background-size: 200% auto;
  color: #fff; font-weight: 800; font-size: .95rem; cursor: pointer;
  letter-spacing: .8px;
  box-shadow: 0 8px 24px rgba(34,197,94,.4);
  transition: transform .4s cubic-bezier(.34,1.56,.64,1), box-shadow .35s ease;
  animation: gradientShift 3s linear infinite, fadeSlide .6s ease .6s both;
}
.modal .btn-ok:hover {
  transform: translateY(-3px) scale(1.02);
  box-shadow: 0 14px 36px rgba(34,197,94,.6);
}

/* ============================================================
   RESPONSIVE
============================================================ */
@media (max-width: 420px) {
  .card { padding: 2rem 1.5rem; border-radius: 20px; }
  .card h1 { font-size: 1.5rem; }
  .modal { padding: 1.75rem 1.25rem; }
  .theme-toggle { width: 46px; height: 46px; font-size: 1.2rem; top:.75rem; right:.75rem; }
}
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: .01ms !important;
    transition-duration: .01ms !important;
  }
}
</style>
</head>
<body>

<div class="aurora"></div>
<canvas id="particles"></canvas>

<button class="theme-toggle" id="themeToggle" aria-label="Ganti tema">
  <span class="icon icon-sun">☀️</span>
  <span class="icon icon-moon">🌙</span>
</button>

<div class="card-wrap" id="cardWrap">
  <div class="card">
    <h1>📝 Daftar Akun</h1>
    <p class="subtitle">Buat akun baru dalam hitungan detik</p>

    <form id="registerForm" autocomplete="on">
      <div class="field">
        <input id="regUsername" name="username" required autocomplete="username" placeholder=" " minlength="3" maxlength="20" />
        <label for="regUsername">Username</label>
      </div>
      <div class="hint">💡 3–20 karakter, huruf/angka/underscore</div>

      <div class="field">
        <input id="regPassword" name="password" type="password" required autocomplete="new-password" placeholder=" " minlength="4" />
        <label for="regPassword">Password</label>
      </div>

      <div class="field">
        <input id="regConfirm" name="confirm" type="password" required autocomplete="new-password" placeholder=" " minlength="4" />
        <label for="regConfirm">Konfirmasi Password</label>
      </div>

      <div class="auto-info">
        <div class="auto-item">
          <span class="auto-lbl">Role Otomatis</span>
          <span class="auto-val role-free">🆓 Free</span>
        </div>
        <div class="auto-item">
          <span class="auto-lbl">Masa Aktif</span>
          <span class="auto-val exp-days">⏳ 2 Hari</span>
        </div>
      </div>

      <button type="submit" id="btnRegister" class="btn-submit">
        <span class="spinner"></span>
        <span class="btn-text">Daftar Sekarang</span>
      </button>
    </form>

    <div id="msg" class="msg"></div>

    <div class="bottom-link">
      Sudah punya akun? <a href="index.html">Login di sini</a>
    </div>

    <div class="info-footer">By <b>Fanzxy Modz</b></div>
  </div>
</div>

<div class="modal-overlay" id="successModal">
  <div class="modal">
    <div class="check">✅</div>
    <h2>AKUN BERHASIL DIBUAT!</h2>
    <p>Silakan login dengan akun baru Anda</p>

    <div class="detail">
      <div class="detail-row">
        <span>Username</span>
        <span id="okUsername">-</span>
      </div>
      <div class="detail-row">
        <span>Role</span>
        <span style="color:#22c55e;">Free</span>
      </div>
      <div class="detail-row">
        <span>Expired</span>
        <span id="okExpired">-</span>
      </div>
    </div>

    <button class="btn-ok" id="btnOk">KE HALAMAN LOGIN</button>
  </div>
</div>

<script>
/* ============================================================
   TEMA
============================================================ */
const THEME_KEY = "login_theme";
const htmlEl = document.documentElement;
function applyTheme(t) {
  htmlEl.setAttribute("data-theme", t);
  localStorage.setItem(THEME_KEY, t);
}
(function initTheme() {
  const saved = localStorage.getItem(THEME_KEY);
  if (saved) applyTheme(saved);
  else applyTheme(window.matchMedia("(prefers-color-scheme: light)").matches ? "light" : "dark");
})();
document.getElementById("themeToggle").addEventListener("click", () => {
  const cur = htmlEl.getAttribute("data-theme");
  applyTheme(cur === "dark" ? "light" : "dark");
});

/* ============================================================
   PARTICLE BACKGROUND
============================================================ */
(function initParticles() {
  const canvas = document.getElementById("particles");
  const ctx = canvas.getContext("2d");
  let W, H, particles = [];

  function resize() {
    W = canvas.width  = window.innerWidth;
    H = canvas.height = window.innerHeight;
    const count = Math.min(60, Math.floor(W * H / 22000));
    particles = Array.from({ length: count }, () => ({
      x: Math.random()*W, y: Math.random()*H,
      r: Math.random()*2.2+0.6,
      vx: (Math.random()-.5)*0.35,
      vy: (Math.random()-.5)*0.35,
      a: Math.random()*0.5+0.2
    }));
  }
  function color() {
    return getComputedStyle(htmlEl).getPropertyValue("--particle").trim() || "rgba(147,197,253,.5)";
  }
  function draw() {
    ctx.clearRect(0,0,W,H);
    const c = color();
    particles.forEach((p,i) => {
      p.x += p.vx; p.y += p.vy;
      if (p.x<0||p.x>W) p.vx *= -1;
      if (p.y<0||p.y>H) p.vy *= -1;
      ctx.beginPath();
      ctx.arc(p.x, p.y, p.r, 0, Math.PI*2);
      ctx.fillStyle = c;
      ctx.globalAlpha = p.a;
      ctx.fill();
      for (let j=i+1; j<particles.length; j++) {
        const q = particles[j];
        const dist = Math.hypot(p.x-q.x, p.y-q.y);
        if (dist < 110) {
          ctx.beginPath();
          ctx.moveTo(p.x, p.y); ctx.lineTo(q.x, q.y);
          ctx.strokeStyle = c;
          ctx.globalAlpha = (1 - dist/110) * 0.15;
          ctx.lineWidth = 0.6;
          ctx.stroke();
        }
      }
    });
    ctx.globalAlpha = 1;
    requestAnimationFrame(draw);
  }
  resize();
  window.addEventListener("resize", resize);
  draw();
})();

/* ============================================================
   3D TILT
============================================================ */
(function initTilt() {
  const wrap = document.getElementById("cardWrap");
  if (matchMedia("(hover: none)").matches) return;
  document.addEventListener("mousemove", (e) => {
    const cx = window.innerWidth/2, cy = window.innerHeight/2;
    const rx = (e.clientY-cy)/cy * -6;
    const ry = (e.clientX-cx)/cx *  6;
    wrap.style.transform = `rotateX(${rx}deg) rotateY(${ry}deg)`;
  });
  document.addEventListener("mouseleave", () => {
    wrap.style.transform = "rotateX(0) rotateY(0)";
  });
})();

/* ============================================================
   API
============================================================ */
const API_BASE = "https://dbcraft-central.preview.emergentagent.com/api/v1/db/9afe8ebc-4df6-462e-8bf4-01edf71e2ef7/records";
const API_KEY  = "azf_Eaco1rTkqpGwWcdhEpu32Fiy5Dw3LZYPDKeldxPlV70";
const HEADERS  = { "Content-Type": "application/json", "x-api-key": API_KEY };

/* ============================================================
   HELPER
============================================================ */
const $ = (s) => document.querySelector(s);
const msgEl = $("#msg");

function showMsg(text, type = "error") {
  msgEl.innerHTML = text;
  msgEl.className = "msg " + type;
  void msgEl.offsetWidth;
  msgEl.classList.add("show");
}
function hideMsg() { msgEl.classList.remove("show"); }

function deepFindArray(obj, depth = 0) {
  if (depth > 5 || !obj) return null;
  if (Array.isArray(obj)) return (obj.length && typeof obj[0] === "object") ? obj : null;
  if (typeof obj === "object") {
    for (const k of ["records","data","items","results","rows","users"]) {
      if (Array.isArray(obj[k]) && obj[k].length) return obj[k];
    }
    for (const k of Object.keys(obj)) {
      if (Array.isArray(obj[k]) && obj[k].length && typeof obj[k][0] === "object") return obj[k];
    }
    for (const k of Object.keys(obj)) {
      const f = deepFindArray(obj[k], depth+1);
      if (f) return f;
    }
  }
  return null;
}

function pick(rec, names) {
  const srcs = [rec?.data, rec];
  for (const src of srcs) {
    if (!src || typeof src !== "object") continue;
    for (const n of names) {
      const v = src[n];
      if (v !== undefined && v !== null && v !== "") return v;
    }
  }
  return undefined;
}

function fmtDate(d) {
  if (!d) return "-";
  const dt = new Date(d);
  if (isNaN(dt.getTime())) return String(d);
  return dt.toLocaleString("id-ID", {
    day:"2-digit", month:"short", year:"numeric",
    hour:"2-digit", minute:"2-digit"
  });
}

/* ============================================================
   REGISTER
============================================================ */
$("#registerForm").addEventListener("submit", async (e) => {
  e.preventDefault();
  hideMsg();

  const username = $("#regUsername").value.trim();
  const password = $("#regPassword").value;
  const confirm  = $("#regConfirm").value;

  if (!username || !password || !confirm) return showMsg("⚠️ Semua kolom wajib diisi", "error");
  if (!/^[a-zA-Z0-9_]+$/.test(username)) return showMsg("⚠️ Username hanya boleh huruf, angka, dan underscore", "error");
  if (username.length < 3 || username.length > 20) return showMsg("⚠️ Username harus 3–20 karakter", "error");
  if (password.length < 4) return showMsg("⚠️ Password minimal 4 karakter", "error");
  if (password !== confirm) return showMsg("⚠️ Password dan konfirmasi tidak cocok", "error");

  const btn = $("#btnRegister");
  const btnText = btn.querySelector(".btn-text");
  btn.disabled = true;
  btn.classList.add("loading");
  btnText.textContent = "Memproses...";
  showMsg("🔄 Membuat akun...", "info");

  try {
    /* 1) Cek username sudah dipakai belum */
    const res = await fetch(API_BASE, { method:"GET", headers: HEADERS });
    if (!res.ok) throw new Error(`HTTP ${res.status} ${res.statusText}`);

    const json = await res.json();
    const records = deepFindArray(json) || [];

    const exists = records.some(r => {
      const u = pick(r, ["username","user_name","user","name"]);
      return u && String(u).toLowerCase() === username.toLowerCase();
    });
    if (exists) return showMsg("❌ Username sudah digunakan, coba yang lain", "error");

    /* 2) Data akun baru — role Free, expired +2 hari */
    const now = new Date();
    const expiredAt = new Date(now.getTime() + 2 * 24 * 60 * 60 * 1000);

    const payload = {
      data: {
        username:      username,
        password:      password,
        role:          "Free",
        created_at:    now.toISOString(),
        expired_at:    expiredAt.toISOString(),
        last_login_at: null
      }
    };

    /* 3) POST ke DBCraft */
    const postRes = await fetch(API_BASE, {
      method: "POST",
      headers: HEADERS,
      body: JSON.stringify(payload)
    });
    if (!postRes.ok) {
      const errTxt = await postRes.text().catch(() => "");
      throw new Error(`Gagal daftar (HTTP ${postRes.status})${errTxt ? " — " + errTxt.slice(0,100) : ""}`);
    }

    /* 4) Sukses */
    hideMsg();
    $("#okUsername").textContent = username;
    $("#okExpired").textContent  = fmtDate(expiredAt);
    $("#successModal").classList.add("show");
    $("#registerForm").reset();

  } catch (err) {
    console.error(err);
    showMsg("❌ Error: " + err.message, "error");
  } finally {
    btn.disabled = false;
    btn.classList.remove("loading");
    btnText.textContent = "Daftar Sekarang";
  }
});

/* ============================================================
   MODAL SUKSES
============================================================ */
$("#btnOk").addEventListener("click", () => {
  window.location.href = "index.html";
});
$("#successModal").addEventListener("click", (e) => {
  if (e.target.id === "successModal") {
    window.location.href = "index.html";
  }
});
</script>
</body>
</html>

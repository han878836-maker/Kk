<!doctype html>
<html lang="vi">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Menu Cài Đặt Aim (Prototype)</title>
<style>
  :root {
    --bg: #0f1724;
    --panel: #0b1220cc;
    --accent: #00d1ff;
    --muted: #94a3b8;
    --glass: rgba(255,255,255,0.03);
  }
  body {
    margin:0;
    font-family: Inter, system-ui, sans-serif;
    background: linear-gradient(180deg,#061021 0%, #072034 100%);
    color: #e6eef6;
    height:100vh;
    display:flex;
    align-items:flex-start;
    justify-content:flex-start;
    padding:24px;
    gap:24px;
  }

  /* Panel */
  .panel {
    width:320px;
    background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));
    border-radius:12px;
    padding:16px;
    box-shadow: 0 6px 20px rgba(2,6,23,0.6);
    border:1px solid rgba(255,255,255,0.04);
  }
  h2 { margin:0 0 12px 0; font-size:18px; letter-spacing:0.2px; }
  .row { display:flex; align-items:center; justify-content:space-between; gap:12px; padding:8px 0; border-bottom:1px dashed rgba(255,255,255,0.02); }
  .row:last-child { border-bottom: none; }
  label { font-size:14px; color:var(--muted); }
  .small { font-size:12px; color:#9fb6c7; }

  /* Toggle */
  .toggle {
    --w:44px;
    --h:24px;
    position:relative;
    width:var(--w);
    height:var(--h);
    background: rgba(255,255,255,0.06);
    border-radius:999px;
    padding:3px;
    cursor:pointer;
    transition: all .18s ease;
  }
  .toggle.on { background: linear-gradient(90deg,var(--accent), #36f0b4); box-shadow: 0 6px 16px rgba(0,209,255,0.12); }
  .toggle .dot {
    width:18px;
    height:18px;
    background:white;
    border-radius:50%;
    transform:translateX(0);
    transition: transform .18s ease;
  }
  .toggle.on .dot { transform:translateX(20px); }

  /* Slider */
  .slider {
    width:140px;
  }
  input[type="range"] {
    -webkit-appearance:none;
    width:100%;
    height:6px;
    background: rgba(255,255,255,0.06);
    border-radius:6px;
    outline:none;
  }
  input[type="range"]::-webkit-slider-thumb {
    -webkit-appearance:none;
    width:14px; height:14px; border-radius:50%;
    background:var(--accent);
    box-shadow:0 2px 10px rgba(0,209,255,0.18);
  }

  /* Canvas area (preview) */
  .preview {
    flex:1;
    min-height:480px;
    border-radius:12px;
    background: linear-gradient(180deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01));
    border:1px solid rgba(255,255,255,0.03);
    padding:12px;
    position:relative;
    overflow:hidden;
  }
  canvas { width:100%; height:100%; display:block; }
  .note { position:absolute; right:12px; bottom:12px; font-size:12px; color:var(--muted); background:var(--glass); padding:8px 10px; border-radius:8px; }
</style>
</head>
<body>

<div class="panel" id="menuPanel">
  <h2>Menu Cài Đặt Aim — Prototype</h2>

  <div class="row">
    <div>
      <label>Aim Assist</label>
      <div class="small">Hiển thị trợ giúp mục tiêu (an toàn)</div>
    </div>
    <div class="toggle" id="toggleAssist" role="switch" aria-checked="false">
      <div class="dot"></div>
    </div>
  </div>

  <div class="row">
    <div>
      <label>Aim Lock (Prototype)</label>
      <div class="small">Chỉ phát sự kiện; KHÔNG tự động điều khiển chuột</div>
    </div>
    <div class="toggle" id="toggleLock" role="switch" aria-checked="false">
      <div class="dot"></div>
    </div>
  </div>

  <div class="row">
    <div>
      <label>Aim Head</label>
      <div class="small">Tham số hiển thị vùng ưu tiên</div>
    </div>
    <div style="width:48px;text-align:right; color:var(--muted);" id="headMode">Mid</div>
  </div>

  <div class="row">
    <div>
      <label>Strength</label>
      <div class="small">Cường độ trợ giúp (chỉ hiển thị)</div>
    </div>
    <div class="slider">
      <input type="range" id="strength" min="0" max="100" value="40">
    </div>
  </div>

  <div class="row">
    <div>
      <label>Target Radius</label>
      <div class="small">Kích thước vùng ưu tiên (px trong preview)</div>
    </div>
    <div class="slider">
      <input type="range" id="radius" min="10" max="200" value="60">
    </div>
  </div>

  <div style="padding-top:10px; display:flex; gap:8px;">
    <button id="resetBtn" style="flex:1; padding:8px 10px; border-radius:8px; border:none; background:#143047;">Reset</button>
    <button id="exportBtn" style="padding:8px 10px; border-radius:8px; border:none; background:var(--accent); color:#002533;">Export</button>
  </div>
</div>

<div class="preview">
  <canvas id="previewCanvas"></canvas>
  <div class="note">
    Preview: minh họa trợ giúp mục tiêu — không tự động điều khiển.
  </div>
</div>

<script>
/* --- UI logic: toggle classes and dispatch events --- */
function makeToggle(el) {
  el.addEventListener('click', () => {
    const on = !el.classList.toggle('on');
    // Actually toggle 'on' class; update aria
    const isOn = el.classList.contains('on');
    el.setAttribute('aria-checked', String(isOn));
    // dispatch custom event for external game logic to listen to
    window.dispatchEvent(new CustomEvent('menu:change', {
      detail: {
        id: el.id,
        value: isOn
      }
    }));
  });
}
makeToggle(document.getElementById('toggleAssist'));
makeToggle(document.getElementById('toggleLock'));

const headModes = ['Head', 'Mid', 'Body'];
let headIdx = 1;
document.getElementById('headMode').addEventListener('click', () => {
  headIdx = (headIdx + 1) % headModes.length;
  document.getElementById('headMode').textContent = headModes[headIdx];
  window.dispatchEvent(new CustomEvent('menu:change', { detail: { id: 'headMode', value: headModes[headIdx] } }));
});

const strength = document.getElementById('strength');
const radius = document.getElementById('radius');
[strength, radius].forEach(el => {
  el.addEventListener('input', () => {
    window.dispatchEvent(new CustomEvent('menu:change', { detail: { id: el.id, value: el.value } }));
  });
});

document.getElementById('resetBtn').addEventListener('click', () => {
  document.getElementById('toggleAssist').classList.remove('on');
  document.getElementById('toggleLock').classList.remove('on');
  strength.value = 40;
  radius.value = 60;
  headIdx = 1;
  document.getElementById('headMode').textContent = headModes[headIdx];
  window.dispatchEvent(new CustomEvent('menu:reset'));
});

document.getElementById('exportBtn').addEventListener('click', () => {
  const config = {
    aimAssist: document.getElementById('toggleAssist').classList.contains('on'),
    aimLock: document.getElementById('toggleLock').classList.contains('on'),
    headMode: document.getElementById('headMode').textContent,
    strength: Number(strength.value),
    radius: Number(radius.value)
  };
  const txt = JSON.stringify(config, null, 2);
  // For demo: download config file
  const a = document.createElement('a');
  a.href = URL.createObjectURL(new Blob([txt], {type:'application/json'}));
  a.download = 'aim_config.json';
  a.click();
});

/* --- Preview canvas (visual aid only) --- */
const canvas = document.getElementById('previewCanvas');
const ctx = canvas.getContext('2d');

function resize() {
  canvas.width = canvas.clientWidth * devicePixelRatio;
  canvas.height = canvas.clientHeight * devicePixelRatio;
  ctx.setTransform(devicePixelRatio,0,0,devicePixelRatio,0,0);
}
window.addEventListener('resize', resize);
resize();

// Mock targets for visualization
const targets = [
  {x:100, y:80},
  {x:280, y:180},
  {x:420, y:120},
  {x:360, y:320},
  {x:140, y:320}
];

function draw() {
  ctx.clearRect(0,0,canvas.width, canvas.height);
  // background grid
  ctx.fillStyle = '#061726';
  ctx.fillRect(0,0,canvas.width,canvas.height);

  // draw targets
  for (const t of targets) {
    ctx.beginPath();
    ctx.fillStyle = '#f25f5c';
    ctx.arc(t.x, t.y, 8, 0, Math.PI*2);
    ctx.fill();
  }

  // read UI state
  const assistOn = document.getElementById('toggleAssist').classList.contains('on');
  const lockOn = document.getElementById('toggleLock').classList.contains('on');
  const rad = Number(radius.value);
  const str = Number(strength.value)/100;

  // mock "visual assist" only: draw soft circle around each target,
  // intensity scales with "strength"; does NOT move cursor or inputs.
  if (assistOn) {
    for (const t of targets) {
      const grad = ctx.createRadialGradient(t.x, t.y, 0, t.x, t.y, rad);
      grad.addColorStop(0, `rgba(0,209,255,${0.18 * str})`);
      grad.addColorStop(0.6, `rgba(0,209,255,${0.06 * str})`);
      grad.addColorStop(1, `rgba(0,209,255,0)`);
      ctx.fillStyle = grad;
      ctx.beginPath();
      ctx.arc(t.x, t.y, rad, 0, Math.PI*2);
      ctx.fill();
    }
  }

  // if lock is on: highlight closest target (visual only)
  if (lockOn) {
    // mock player center
    const px = canvas.clientWidth / 2;
    const py = canvas.clientHeight / 2;
    // find closest
    let best = null;
    let bestDist = Infinity;
    for (const t of targets) {
      const dx = t.x - px, dy = t.y - py;
      const d = Math.hypot(dx,dy);
      if (d < bestDist) { bestDist = d; best = t; }
    }
    if (best) {
      ctx.strokeStyle = 'rgba(255,215,0,0.95)';
      ctx.lineWidth = 2;
      ctx.beginPath();
      ctx.arc(best.x, best.y, 16, 0, Math.PI*2);
      ctx.stroke();
      ctx.fillStyle = 'rgba(255,215,0,0.06)';
      ctx.beginPath();
      ctx.arc(best.x, best.y, rad, 0, Math.PI*2);
      ctx.fill();
    }
  }

  // draw player crosshair in center (user-controlled in real game)
  const cx = canvas.clientWidth / 2;
  const cy = canvas.clientHeight / 2;
  ctx.strokeStyle = '#e6eef6';
  ctx.lineWidth = 2;
  ctx.beginPath();
  ctx.moveTo(cx-12, cy);
  ctx.lineTo(cx+12, cy);
  ctx.moveTo(cx, cy-12);
  ctx.lineTo(cx, cy+12);
  ctx.stroke();

  requestAnimationFrame(draw);
}
requestAnimationFrame(draw);

/* --- Example: how game code could listen (safe) --- */
window.addEventListener('menu:change', (e) => {
  // e.detail = { id: 'strength' | 'toggleAssist' | etc, value: ... }
  console.log('[Menu event]', e.detail);
  // Example: game engine can read config and decide what to do.
  // IMPORTANT: do not implement automatic input control without user's consent and single-player context.
});

window.addEventListener('menu:reset', () => {
  console.log('[Menu reset]');
});
</script>

</body>
</html>

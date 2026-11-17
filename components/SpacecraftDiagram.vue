<script setup>
import { ref } from 'vue'
import { onSlideEnter } from '@slidev/client'

// Replay the build-up sequence every time the slide is entered
const runKey = ref(0)
onSlideEnter(() => { runKey.value++ })

// Deterministic pseudo-random
const rnd = (i, n) => ((Math.sin(i * 12.9898 + n * 78.233) * 43758.5453) % 1 + 1) % 1

const stars = Array.from({ length: 90 }, (_, i) => ({
  x: rnd(i, 1) * 860, y: rnd(i, 2) * 300, s: 0.35 + rnd(i, 3) * 1.1, d: 2 + rnd(i, 4) * 4, o: 0.2 + rnd(i, 5) * 0.6,
}))

// Earth limb: centre (560,760), rx 600, ry 420
const limbY = (x) => 760 - 420 * Math.sqrt(Math.max(0, 1 - ((x - 560) / 600) ** 2))
const lights = Array.from({ length: 70 }, (_, i) => {
  const x = 300 + rnd(i, 7) * 300
  return { x, y: limbY(x) + 5 + rnd(i, 8) * 34, r: 0.5 + rnd(i, 9) * 0.9, d: rnd(i, 10) * 3 }
})

// Solar cells, each delayed by distance from the bus so power "flows inward"
const cols = 6, rows = 4
const cells = []
for (const side of ['L', 'R']) {
  const x0 = side === 'L' ? 200 : 510
  for (let c = 0; c < cols; c++) for (let r = 0; r < rows; r++) {
    const fromBus = side === 'L' ? cols - 1 - c : c
    cells.push({ key: side + c + r, x: x0 + c * 25 + 1, y: 96 + r * 18.5 + 1, delay: -(cols - fromBus) * 0.22 })
  }
}
const leds = Array.from({ length: 15 }, (_, i) => ({ x: 418 + (i % 5) * 6, y: 122 + Math.floor(i / 5) * 12, d: rnd(i, 11) * 1.4, dur: 0.6 + rnd(i, 12) * 1.2 }))
</script>

<template>
<svg :key="runKey" viewBox="0 0 860 360" role="img" aria-label="Sunlight powers a compute satellite; laser links carry data to a relay and Earth; a coolant loop carries heat to radiators that emit infrared into space" class="sd">
  <defs>
    <radialGradient id="sd-sun"><stop offset="0" stop-color="#fff6e0"/><stop offset=".3" stop-color="#ffcf87"/><stop offset=".65" stop-color="#ff9d4a" stop-opacity=".3"/><stop offset="1" stop-color="#ff9d4a" stop-opacity="0"/></radialGradient>
    <radialGradient id="sd-earth" cx=".62" cy="0" r="1"><stop offset="0" stop-color="#2f93bf"/><stop offset=".2" stop-color="#14496b"/><stop offset=".55" stop-color="#081c2e"/><stop offset="1" stop-color="#030810"/></radialGradient>
    <linearGradient id="sd-night" x1="0" x2="1"><stop offset="0" stop-color="#02060c" stop-opacity=".85"/><stop offset=".45" stop-color="#02060c" stop-opacity=".55"/><stop offset=".7" stop-color="#02060c" stop-opacity="0"/></linearGradient>
    <linearGradient id="sd-atmo" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#6ce9ff" stop-opacity=".6"/><stop offset="1" stop-color="#6ce9ff" stop-opacity="0"/></linearGradient>
    <linearGradient id="sd-cell" x1="0" y1="0" x2="1" y2="1"><stop offset="0" stop-color="#1d4f8c"/><stop offset=".5" stop-color="#0d2a52"/><stop offset="1" stop-color="#183f73"/></linearGradient>
    <linearGradient id="sd-glint" x1="0" x2="1"><stop offset="0" stop-color="#fff" stop-opacity="0"/><stop offset=".5" stop-color="#bfefff" stop-opacity=".6"/><stop offset="1" stop-color="#fff" stop-opacity="0"/></linearGradient>
    <linearGradient id="sd-radh" x1="1" x2="0"><stop offset="0" stop-color="#ff4d24"/><stop offset=".45" stop-color="#ff9d4a"/><stop offset="1" stop-color="#5a2412"/></linearGradient>
    <linearGradient id="sd-sheen" x1="0" x2="1"><stop offset="0" stop-color="#ffd9a0" stop-opacity="0"/><stop offset=".5" stop-color="#ffe7c4" stop-opacity=".55"/><stop offset="1" stop-color="#ffd9a0" stop-opacity="0"/></linearGradient>
    <linearGradient id="sd-scan" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#6ce9ff" stop-opacity="0"/><stop offset="1" stop-color="#6ce9ff" stop-opacity=".35"/></linearGradient>
    <radialGradient id="sd-core"><stop offset="0" stop-color="#e9fdff"/><stop offset=".4" stop-color="#6ce9ff"/><stop offset="1" stop-color="#6ce9ff" stop-opacity="0"/></radialGradient>
    <radialGradient id="sd-flare"><stop offset="0" stop-color="#ffcf87" stop-opacity=".5"/><stop offset="1" stop-color="#ffcf87" stop-opacity="0"/></radialGradient>
    <filter id="sd-glow" x="-50%" y="-50%" width="200%" height="200%"><feGaussianBlur stdDeviation="3" result="b"/><feMerge><feMergeNode in="b"/><feMergeNode in="SourceGraphic"/></feMerge></filter>
    <filter id="sd-bigglow" x="-100%" y="-100%" width="300%" height="300%"><feGaussianBlur stdDeviation="8"/></filter>
    <clipPath id="sd-wingL"><rect x="200" y="96" width="150" height="74" rx="2"/></clipPath>
    <clipPath id="sd-wingR"><rect x="510" y="96" width="150" height="74" rx="2"/></clipPath>
    <clipPath id="sd-radclip"><rect x="320" y="206" width="216" height="38" rx="2"/></clipPath>
    <clipPath id="sd-below"><rect x="0" y="246" width="860" height="200"/></clipPath>
    <clipPath id="sd-hud"><rect x="190" y="84" width="480" height="172"/></clipPath>
    <clipPath id="sd-earthclip"><ellipse cx="560" cy="760" rx="600" ry="420"/></clipPath>
    <path id="sd-sunpath" d="M70 70 L270 133"/>
    <path id="sd-sunpath2" d="M70 70 L300 105"/>
    <path id="sd-up" d="M452 90 L770 40"/>
    <path id="sd-down" d="M468 145 L735 358"/>
    <path id="sd-hot" d="M440 166 V194 H520 V206"/>
    <path id="sd-cold" d="M340 206 V194 H420 V166"/>
  </defs>

  <!-- stars -->
  <circle v-for="(s,i) in stars" :key="i" :cx="s.x" :cy="s.y" :r="s.s" fill="#cfe9ff" :opacity="s.o" class="twinkle" :style="{animationDuration:s.d+'s',animationDelay:-i*0.37+'s'}"/>

  <!-- ============ Earth ============ -->
  <g class="st" style="--d:0s">
    <ellipse cx="560" cy="760" rx="630" ry="445" fill="url(#sd-atmo)" opacity=".55" filter="url(#sd-bigglow)"/>
    <ellipse cx="560" cy="760" rx="600" ry="420" fill="url(#sd-earth)"/>
    <ellipse cx="560" cy="760" rx="600" ry="420" fill="none" stroke="#9ff3ff" stroke-opacity=".8" stroke-width="1.2"/>
    <ellipse cx="560" cy="760" rx="605" ry="425" fill="none" stroke="#6ce9ff" stroke-opacity=".22" stroke-width="7"/>
    <text x="852" y="378" class="lbl" text-anchor="end" opacity=".6">EARTH</text>
  </g>

  <!-- ground station -->
  <g class="st" style="--d:1.5s">
    <g transform="translate(735 358)">
      <circle r="6" fill="none" stroke="#6ce9ff" class="ping"/>
      <path d="M-8 0 L0 -11 L8 0Z" fill="#9fdcef"/><circle cy="-12" r="2.6" fill="#e9fdff" filter="url(#sd-glow)" class="blink"/>
    </g>
    <text x="750" y="350" class="lbl tiny">GROUND STATION</text>
  </g>

  <!-- ============ Sun ============ -->
  <g class="st" style="--d:0s">
    <circle cx="58" cy="62" r="100" fill="url(#sd-sun)" class="corona"/>
    <circle cx="58" cy="62" r="24" fill="#fff4dc" filter="url(#sd-glow)"/>
    <text x="20" y="132" class="lbl sun">SUNLIGHT</text>
  </g>

  <!-- photon streams -->
  <g class="st" style="--d:.35s">
    <g stroke="#ffbc72" stroke-linecap="round">
      <path d="M78 68 L300 104" stroke-opacity=".16" stroke-width="22" class="beamwide"/>
      <path d="M78 68 L250 160" stroke-opacity=".11" stroke-width="18" class="beamwide"/>
    </g>
    <g fill="#ffe2b0" filter="url(#sd-glow)">
      <circle v-for="k in 6" :key="'p'+k" r="2.4"><animateMotion dur="1.6s" :begin="(-k*0.27)+'s'" repeatCount="indefinite"><mpath href="#sd-sunpath2"/></animateMotion></circle>
      <circle v-for="k in 6" :key="'q'+k" r="2"><animateMotion dur="1.9s" :begin="(-k*0.32)+'s'" repeatCount="indefinite"><mpath href="#sd-sunpath"/></animateMotion></circle>
    </g>
  </g>

  <!-- ============ Laser links ============ -->
  <g class="st" style="--d:1.4s">
    <g filter="url(#sd-glow)" fill="none">
      <use href="#sd-up" stroke="#6ce9ff" stroke-width="1.4" stroke-opacity=".8" pathLength="1" class="lead slow"/>
      <use href="#sd-down" stroke="#6ce9ff" stroke-width="1.4" stroke-opacity=".6" pathLength="1" class="lead slow"/>
      <use href="#sd-up" stroke="#e9fdff" stroke-width="2.2" class="pulse-dash"/>
      <use href="#sd-down" stroke="#e9fdff" stroke-width="2.2" class="pulse-dash rev"/>
    </g>
    <g fill="#e9fdff" filter="url(#sd-glow)">
      <rect v-for="k in 4" :key="'d'+k" x="-5" y="-1.4" width="10" height="2.8" rx="1.4"><animateMotion dur="1.4s" :begin="(-k*0.35)+'s'" repeatCount="indefinite" rotate="auto"><mpath href="#sd-up"/></animateMotion></rect>
      <rect v-for="k in 4" :key="'e'+k" x="-5" y="-1.4" width="10" height="2.8" rx="1.4"><animateMotion dur="1.8s" :begin="(-k*0.45)+'s'" repeatCount="indefinite" rotate="auto" keyPoints="1;0" keyTimes="0;1" calcMode="linear"><mpath href="#sd-down"/></animateMotion></rect>
    </g>
  </g>

  <!-- relay satellite -->
  <g class="st" style="--d:1.6s">
    <g transform="translate(775 38)">
      <g class="bob2">
        <circle r="10" fill="none" stroke="#6ce9ff" class="ping"/>
        <rect x="-30" y="-6" width="18" height="12" fill="url(#sd-cell)" stroke="#6ce9ff88" stroke-width=".6"/>
        <rect x="12" y="-6" width="18" height="12" fill="url(#sd-cell)" stroke="#6ce9ff88" stroke-width=".6"/>
        <path d="M-12 0H12" stroke="#8da1b6" stroke-width="2"/>
        <rect x="-8" y="-8" width="16" height="16" rx="1.5" fill="#c8d6e0"/><circle r="3" fill="#6ce9ff" class="blink"/>
      </g>
    </g>
    <text x="775" y="16" class="lbl" text-anchor="middle">RELAY</text>
  </g>

  <!-- ============ main spacecraft ============ -->
  <g class="bob">
    <!-- solar wings -->
    <g class="st" style="--d:.6s">
      <g v-for="side in ['L','R']" :key="side">
        <rect :x="side==='L'?200:510" y="96" width="150" height="74" rx="2" fill="url(#sd-cell)" stroke="#6ce9ff" stroke-opacity=".7"/>
        <g :clip-path="`url(#sd-wing${side})`">
          <rect :x="side==='L'?200:510" y="90" width="50" height="90" fill="url(#sd-glint)" class="glint" transform="skewX(-20)"/>
        </g>
      </g>
      <!-- trusses -->
      <path d="M350 133H400 M460 133H510" stroke="#8da1b6" stroke-width="4"/>
      <path d="M350 128L400 138 M350 138L400 128 M460 128L510 138 M460 138L510 128" stroke="#8da1b6" stroke-width=".8" opacity=".7"/>
      <path d="M350 133H400" stroke="#ffd9a0" stroke-width="1.6" class="flow-dash" filter="url(#sd-glow)"/>
      <path d="M510 133H460" stroke="#ffd9a0" stroke-width="1.6" class="flow-dash" filter="url(#sd-glow)"/>
    </g>

    <!-- bus / compute core -->
    <g class="st" style="--d:1s">
      <circle cx="430" cy="135" r="34" fill="url(#sd-core)" class="core" filter="url(#sd-bigglow)"/>
      <rect x="400" y="100" width="60" height="66" rx="3" fill="#b9c9d4"/>
      <rect x="400" y="100" width="60" height="8" rx="2" fill="#e3edf3"/>
      <rect x="410" y="114" width="40" height="42" rx="2" fill="#06111d" stroke="#6ce9ff"/>
      <g stroke="#6ce9ff" stroke-width=".6" stroke-opacity=".7">
        <rect v-for="n in 3" :key="'rack'+n" x="414" :y="116+(n-1)*12" width="32" height="9" rx="1" fill="#0b2a3a"/>
      </g>
      <circle v-for="(l,i) in leds" :key="'led'+i" :cx="l.x" :cy="l.y" r="1.2" fill="#9ff3ff" class="led" :style="{animationDelay:-l.d+'s',animationDuration:l.dur+'s'}"/>
      <!-- laser terminals -->
      <rect x="446" y="92" width="10" height="8" fill="#8da1b6"/><circle cx="452" cy="90" r="2.8" fill="#e9fdff" filter="url(#sd-glow)"/>
      <rect x="460" y="140" width="8" height="10" fill="#8da1b6"/><circle cx="468" cy="145" r="2.8" fill="#e9fdff" filter="url(#sd-glow)"/>
    </g>

    <!-- coolant loop + radiator -->
    <g class="st" style="--d:1.8s">
      <use href="#sd-hot" fill="none" stroke="#3a1a0e" stroke-width="5.5" stroke-linejoin="round"/>
      <use href="#sd-cold" fill="none" stroke="#1a1d3a" stroke-width="5.5" stroke-linejoin="round"/>
      <use href="#sd-hot" fill="none" stroke="#ff6a3d" stroke-width="2.4" stroke-linejoin="round" class="coolant" filter="url(#sd-glow)"/>
      <use href="#sd-cold" fill="none" stroke="#8f9cff" stroke-width="2.4" stroke-linejoin="round" class="coolant"/>
      <text x="472" y="189" class="lbl tiny warm">HOT →</text>
      <text x="348" y="189" class="lbl tiny cool">← COOLED</text>

      <rect x="320" y="206" width="216" height="38" rx="2" fill="#140e0b" stroke="#ffbc72" stroke-opacity=".8"/>
      <rect x="320" y="206" width="216" height="38" rx="2" fill="url(#sd-radh)" class="radglow"/>
      <g clip-path="url(#sd-radclip)">
        <rect x="320" y="206" width="70" height="38" fill="url(#sd-sheen)" class="sheen"/>
        <path v-for="f in 21" :key="'f'+f" :d="`M${320+f*10} 208V242`" stroke="#1f120b" stroke-width="1.2"/>
      </g>
    </g>
  </g>

  <!-- infrared emission -->
  <g class="st" style="--d:2.2s">
    <g fill="none" stroke="#ff9a5a" stroke-width="1.5" stroke-linecap="round">
      <path v-for="w in 6" :key="'w'+w" :d="`M${336+(w-1)*36} 252 q5 7 0 14 q-5 7 0 14 q5 7 0 14`" class="ir" :style="{animationDelay:(-w*0.37)+'s'}"/>
    </g>
  </g>

  <!-- ============ callouts ============ -->
  <g class="callout st" style="--d:.9s">
    <path d="M275 96 L250 52 H200" pathLength="1" class="lead"/><circle cx="275" cy="96" r="2.5"/>
    <text x="200" y="44" class="lbl">① SOLAR ARRAYS · ELECTRICITY</text>
  </g>
  <g class="callout st" style="--d:1.25s">
    <path d="M425 100 L425 22 H470" pathLength="1" class="lead"/><circle cx="425" cy="100" r="2.5"/>
    <text x="476" y="26" class="lbl">② COMPUTE CORE</text>
  </g>
  <g class="callout st" style="--d:1.7s">
    <text x="548" y="64" class="lbl cyan" transform="rotate(-8.9 548 64)">③ LASER LINKS · DATA</text>
  </g>
  <g class="callout warm st" style="--d:2.1s">
    <path d="M320 225 H296 L278 268" pathLength="1" class="lead"/><circle cx="320" cy="225" r="2.5"/>
    <text x="272" y="276" class="lbl warm" text-anchor="end">④ COOLANT LOOP → RADIATORS</text>
    <text x="272" y="292" class="lbl warm dim" text-anchor="end">INFRARED OUT</text>
  </g>
</svg>
</template>

<style scoped>
.sd { width: 100%; height: 330px; overflow: visible; }
.lbl { font-family: var(--slidev-code-font-family, ui-monospace, monospace); font-size: 10.5px; letter-spacing: .14em; fill: #c9dbea; }
.lbl.tiny { font-size: 7.5px; letter-spacing: .18em; opacity: .75; }
.lbl.sun { fill: #ffcf87; }
.lbl.cyan { fill: #6ce9ff; }
.lbl.warm { fill: #ffbc72; }
.lbl.cool { fill: #a9b3ff; }
.lbl.dim { opacity: .65; font-size: 9px; }
.callout path { fill: none; stroke: #c9dbea; stroke-opacity: .55; stroke-width: .8; }
.callout circle { fill: #c9dbea; }
.callout.warm path { stroke: #ffbc72; } .callout.warm circle { fill: #ffbc72; }
.hud .lead { fill: none; stroke: #6ce9ff; stroke-opacity: .45; stroke-width: 1.2; }

/* build-up sequence (replays on slide enter) */
.st { animation: stIn .9s cubic-bezier(.2,.7,.2,1) var(--d, 0s) both; }
@keyframes stIn { from { opacity: 0; } }
.lead { stroke-dasharray: 1; animation: draw .9s cubic-bezier(.3,.7,.2,1) var(--d, 0s) both; }
.lead.slow { animation-duration: 1.1s; }
@keyframes draw { from { stroke-dashoffset: 1; } to { stroke-dashoffset: 0; } }

/* ambient motion */
.twinkle { animation: tw ease-in-out infinite alternate; }
@keyframes tw { to { opacity: .08; } }
.corona { animation: corona 4s ease-in-out infinite alternate; transform-origin: 58px 62px; }
@keyframes corona { to { transform: scale(1.08); opacity: .8; } }
.rays { animation: spin 60s linear infinite; }
@keyframes spin { to { transform: rotate(360deg); } }
.flare { animation: flare 5s ease-in-out infinite alternate; }
@keyframes flare { from { opacity: .5; } to { opacity: 1; } }
.beamwide { animation: beam 3s ease-in-out infinite alternate; }
@keyframes beam { to { stroke-opacity: .26; } }
.bob { animation: bob 7s ease-in-out infinite; }
@keyframes bob { 50% { transform: translateY(-4px); } }
.bob2 { animation: bob 5s ease-in-out infinite reverse; }
.glint { animation: glint 4.5s ease-in-out infinite; }
@keyframes glint { 0% { transform: translateX(-80px) skewX(-20deg); } 60%,100% { transform: translateX(220px) skewX(-20deg); } }
.cell { opacity: 0; animation: cell 1.6s ease-in-out infinite; }
@keyframes cell { 0%,100% { opacity: 0; } 30% { opacity: .28; } }
.core { animation: core 2.2s ease-in-out infinite alternate; transform-origin: 430px 135px; }
@keyframes core { from { opacity: .3; transform: scale(.85); } to { opacity: .85; transform: scale(1.15); } }
.led { animation: led steps(2) infinite; }
@keyframes led { 50% { opacity: .15; } }
.corescan { animation: corescan 1.8s ease-in-out infinite; }
@keyframes corescan { 0% { transform: translateY(0); opacity: 0; } 15% { opacity: .55; } 85% { opacity: .55; } 100% { transform: translateY(39px); opacity: 0; } }
.flow-dash { stroke-dasharray: 3 7; animation: dash .5s linear infinite; }
.coolant { stroke-dasharray: 8 7; animation: dash 1.1s linear infinite; }
@keyframes dash { to { stroke-dashoffset: -15; } }
.pulse-dash { stroke-dasharray: 2 40; animation: dash2 1s linear infinite; opacity: .6; }
.pulse-dash.rev { animation-direction: reverse; }
@keyframes dash2 { to { stroke-dashoffset: -42; } }
.radglow { animation: radglow 2.6s ease-in-out infinite alternate; }
@keyframes radglow { from { opacity: .3; } to { opacity: .7; } }
.sheen { animation: sheen 2.4s linear infinite; }
@keyframes sheen { from { transform: translateX(216px); } to { transform: translateX(-70px); } }
.ring { transform-box: fill-box; transform-origin: center; animation: ring 3.2s ease-out infinite; opacity: 0; }
@keyframes ring { 0% { opacity: .8; transform: scale(1, 1); } 100% { opacity: 0; transform: scale(1.7, 7); } }
.ir { opacity: 0; animation: ir 2.2s ease-out infinite; }
@keyframes ir { 0% { opacity: 0; transform: translateY(0); } 20% { opacity: .9; } 100% { opacity: 0; transform: translateY(42px); } }
.scan { animation: scan 5s ease-in-out infinite; }
@keyframes scan { 0% { transform: translateY(0); opacity: 0; } 10% { opacity: 1; } 80% { opacity: 1; } 100% { transform: translateY(180px); opacity: 0; } }
.ping { transform-box: fill-box; transform-origin: center; animation: ping 2s ease-out infinite; }
@keyframes ping { from { opacity: .9; transform: scale(.6); } to { opacity: 0; transform: scale(3); } }
.city { animation: city 3s ease-in-out infinite alternate; }
@keyframes city { from { opacity: .35; } to { opacity: 1; } }
.clouds { animation: clouds 30s linear infinite alternate; }
@keyframes clouds { to { transform: translateX(-40px); } }
.blink { animation: blink 1.4s steps(2) infinite; }
@keyframes blink { 50% { opacity: .2; } }
@media (prefers-reduced-motion: reduce) { * { animation: none !important; } }
</style>

<script setup>
import { computed } from 'vue'
import { useSlideContext } from '@slidev/client'
const { $clicks } = useSlideContext()
const temps=[300,330,360]
const temp=computed(()=>temps[Math.min($clicks.value,2)])
const flux=computed(()=>.9*5.670374419e-8*temp.value**4)
const area=computed(()=>1e6/flux.value)
const path=computed(()=>Array.from({length:61},(_,i)=>{const t=280+i*2;return `${i?'L':'M'}${70+(t-280)*2.6},${295 - 0.2 * 0.9 * 5.670374419e-8 * t**4}`}).join(' '))
const x=computed(()=>70+(temp.value-280)*2.6)
const y=computed(()=>295 - 0.2 * flux.value)
</script>
<template><div class="lab"><div><svg viewBox="0 0 445 300" role="img" aria-label="Radiated power per square metre rises as the fourth power of radiator temperature" style="width:100%;height:278px">
<path d="M70 25V245H405" stroke="#6e8299" fill="none"/>
<g v-for="f in [400,600,800,1000,1200]" :key="f"><path :d="`M70 ${295 - 0.2 * f}H405`" stroke="#ffffff12"/><text x="12" :y="299 - 0.2 * f" class="flow-label">{{f}}</text></g>
<text x="4" y="18" class="flow-label">W/m²</text><text v-for="t in [280,300,330,360,400]" :key="t" :x="70+(t-280)*2.6" y="266" text-anchor="middle" class="flow-label">{{t}}</text><text x="215" y="294" class="flow-label">RADIATOR TEMPERATURE / K</text>
<path :d="path" stroke="#6ce9ff" fill="none" stroke-width="3"/>
<path :d="`M${x} 245V${y}`" stroke="#ffbc72" stroke-dasharray="4 5" style="transition:all .7s"/><circle :cx="x" :cy="y" r="7" fill="#ffbc72" style="transition:all .7s"/>
</svg></div><div class="panel"><div class="mono small muted">IDEAL RADIATOR / 1 MW HEAT</div><div class="temperature">{{temp}}<span>K</span></div><div class="lab-metrics"><div><strong>{{Math.round(flux)}}</strong><span>W/m² emitted</span></div><div><strong>{{Math.round(area).toLocaleString()}}</strong><span>m² emitting area</span></div></div><div class="presets"><span v-for="t in temps" :key="t" :class="{selected:t===temp}">{{t}} K</span></div></div></div></template>
<style scoped>.lab{display:grid;grid-template-columns:1.12fr 1fr;gap:35px}.temperature{font-size:80px;letter-spacing:-5px;line-height:1.25;color:#6ce9ff}.temperature span{font-size:25px;letter-spacing:0;margin-left:10px}.lab-metrics{display:flex;gap:30px}.lab-metrics strong{font-size:29px;font-weight:500;display:block}.lab-metrics span{font:10px monospace;color:#96a9be}.presets{display:flex;gap:12px;margin-top:20px}.presets span{padding:4px 9px;border:1px solid #ffffff25;font:10px monospace;color:#96a9be}.presets .selected{border-color:#ffbc72;color:#ffbc72}</style>

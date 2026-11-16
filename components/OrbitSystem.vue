<script setup>
defineProps({ mode: {default:'network'} })
</script>
<template>
<svg viewBox="0 0 850 320" role="img" :aria-label="mode==='solar'?'Sunlight, Earth shadow, and an illustrative satellite orbit':'Solar energy enters a compute satellite, data travels by laser, infrared heat leaves by radiator'" style="width:100%;height:310px">
<defs><radialGradient :id="`earth-${mode}`"><stop stop-color="#1b6181"/><stop offset=".8" stop-color="#12334d"/><stop offset="1" stop-color="#06111d"/></radialGradient><linearGradient :id="`shadow-${mode}`"><stop stop-color="#01050b00"/><stop offset="1" stop-color="#01050b"/></linearGradient><pattern :id="`cells-${mode}`" width="15" height="12" patternUnits="userSpaceOnUse"><rect width="14" height="11" fill="#112f59" stroke="#42719a" stroke-width=".3"/></pattern></defs>
<g v-if="mode==='solar'">
<circle cx="67" cy="157" r="35" fill="#ffbd72" opacity=".95"/><circle cx="67" cy="157" r="49" fill="none" stroke="#ffbd7233" class="pulse"/>
<path d="M115 105H330 M115 157H330 M115 209H330" stroke="#ffbd72" class="beam"/>
<path d="M450 88L820 30V290L450 230Z" :fill="`url(#shadow-${mode})`"/>
<circle cx="435" cy="158" r="71" :fill="`url(#earth-${mode})`" stroke="#6ce9ff" stroke-width="1"/>
<ellipse cx="435" cy="158" rx="139" ry="119" fill="none" stroke="#6ce9ff66" class="orbit-line"/>
<g><animateMotion dur="18s" repeatCount="indefinite" path="M574 158 A139 119 0 1 1 296 158 A139 119 0 1 1 574 158"/><rect x="-7" y="-7" width="14" height="14" fill="#e8f9ff"/><path d="M-27 -9H-9V9H-27Z M9 -9H27V9H9Z" fill="#2a6d9b" stroke="#6ce9ff"/></g>
<text x="30" y="247" class="flow-label">SUNLIGHT</text><text x="390" y="163" class="flow-title">EARTH</text><text x="643" y="163" class="flow-label">ECLIPSE ZONE</text><text x="305" y="309" class="flow-label">ORDINARY LEO ORBIT · SCHEMATIC</text>
</g>
<g v-else>
<path d="M38 72L256 124" stroke="#ffbc72" stroke-width="3" class="beam"/><circle cx="31" cy="68" r="20" fill="#ffbc72"/><text x="10" y="28" class="flow-label">SUNLIGHT</text>
<g class="float"><path d="M265 88H365V154H265Z M484 88H584V154H484Z" :fill="`url(#cells-${mode})`" stroke="#6ce9ff99"/><path d="M365 120H484" stroke="#8da1b6" stroke-width="5"/><rect x="397" y="98" width="54" height="48" fill="#b6c7d2"/><rect x="410" y="109" width="28" height="26" fill="#07111f" stroke="#6ce9ff"/><path d="M424 147V180" stroke="#ffbc72" stroke-width="4"/><path d="M302 182H547V225H302Z" fill="#1a2936" stroke="#c3d4e5"/><path v-for="i in 19" :key="i" :d="`M${306+i*12} 183V224`" stroke="#8fa3b5" stroke-width=".5"/>
<path d="M324 230V279 M370 230V279 M416 230V279 M462 230V279 M508 230V279" stroke="#ffbc72" class="beam"/>
</g>
<path d="M452 117L723 85" stroke="#6ce9ff" stroke-width="2" class="beam"/><rect x="725" y="73" width="23" height="23" fill="#37536b" stroke="#6ce9ff"/><path d="M738 98L774 200" stroke="#6ce9ff88" class="beam"/>
<path d="M669 290Q740 182 835 237" fill="#14364c" stroke="#6ce9ff66"/>
<text x="285" y="65" class="flow-label">SOLAR ARRAYS · ELECTRICITY</text><text x="334" y="170" class="flow-label">COMPUTE + COOLANT LOOP</text><text x="335" y="309" class="flow-label" style="fill:#ffbc72">RADIATORS · INFRARED OUT</text><text x="625" y="48" class="flow-label">LASER LINKS · DATA</text><text x="719" y="274" class="flow-label">EARTH</text>
</g>
</svg>
</template>

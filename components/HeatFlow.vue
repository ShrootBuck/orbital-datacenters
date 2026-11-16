<template><svg viewBox="0 0 850 250" role="img" aria-label="Heat travels from chips through a cold plate and sealed coolant loop to radiator panels, then radiates as infrared photons" style="width:100%;height:260px">
<defs><pattern id="fins" width="12" height="10" patternUnits="userSpaceOnUse"><path d="M0 0V10" stroke="#86a3b6" stroke-width="2"/></pattern></defs>
<rect x="15" y="65" width="125" height="110" rx="8" fill="#271e18" stroke="#ffbc72"/><rect x="47" y="92" width="60" height="55" fill="#111820" stroke="#ffbc72"/><path v-for="i in 6" :key="i" :d="`M${45+i*9} 83V91 M${45+i*9} 148V157`" stroke="#ffbc72"/>
<path d="M142 105H265V65H475V104H563 M563 151H475V203H265V151H142" fill="none" stroke="#173b52" stroke-width="13"/><path d="M142 105H265V65H475V104H563" fill="none" stroke="#ffbc72" stroke-width="3" class="beam"/><path d="M563 151H475V203H265V151H142" fill="none" stroke="#6ce9ff" stroke-width="3" class="beam"/>
<circle cx="370" cy="203" r="17" fill="#102333" stroke="#6ce9ff"/><path d="M360 203H380M370 193V213" stroke="#6ce9ff"/>
<rect x="563" y="52" width="121" height="146" fill="#1c2b36" stroke="#92b3c9"/><rect x="569" y="58" width="109" height="134" fill="url(#fins)"/>
<path v-for="i in 5" :key="i" :d="`M693 ${55+i*27}q15 -13 30 0t30 0t30 0`" stroke="#ffbc72" fill="none" class="beam"/>
<text x="14" y="27" class="flow-label">01 / CHIP → COLD PLATE</text><text x="280" y="27" class="flow-label">02 / SEALED COOLANT LOOP</text><text x="565" y="27" class="flow-label">03 / RADIATOR → PHOTONS</text><text x="11" y="226" class="flow-title">Conduction</text><text x="286" y="145" class="flow-title">Fluid transport</text><text x="704" y="226" class="flow-title">Radiation</text>
</svg></template>

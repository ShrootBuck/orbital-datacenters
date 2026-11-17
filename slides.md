---
theme: default
title: Orbital Datacenters — The Physics of a SpaceX Bet
author: Zayd Krunz
info: A classroom investor pitch investigating the physical and economic viability of orbital AI compute.
colorSchema: dark
canvasWidth: 1100
aspectRatio: 16/9
fonts:
  provider: none
transition: launch
class: hero
layout: default
duration: 10min
timer: countdown
presenter: true
mdc: true
drawings:
  enabled: false
---

<img class="hero-bg" src="/images/orbital-concept.png" alt="Generated concept of a compute satellite with solar arrays and radiators above Earth" />
<div class="hero-shade" />
<h1>Intelligence.<br>Beyond <span>Earth.</span></h1>
<p class="lede">Orbital data centers.<br>The next infrastructure frontier?</p>
<div class="tag">Zayd Krunz · Capstone: Quantum Mechanics</div>

<!--
Mr. Lee, imagine that our next AI data center has no address, no connection to the power grid, and no cooling tower. It circles Earth. Today, I’m pitching a SpaceX approach to orbital computing. The product is intelligence powered by sunlight. The engineering question is whether we can get rid of the heat. That question decides whether this is infrastructure or an extremely expensive space heater.
-->

---
transition: slide-left
---

# AI growth has a physical bottleneck.

<div class="grid2" style="margin-top:35px">
<div>
<div class="big cyan">945<span style="font-size:30px;letter-spacing:0"> TWh</span></div>
<p class="lede" style="margin-top:14px">Projected global data center electricity demand in 2030.</p>
<div class="tag" style="margin-top:22px">IEA base case · all data centers</div>
</div>
<div>
<div class="track"><div class="index">01</div><div><h2>Power</h2><p>More chips require more electricity.</p></div></div>
<div class="track"><div class="index">02</div><div><h2>Heat</h2><p>That electricity becomes a cooling problem.</p></div></div>
<div class="track"><div class="index">03</div><div><h2>Land + water</h2><p>Zoning fights. Land disputes. “AI water!”</p></div></div>
</div>
</div>
<div class="source">[1] IEA, Energy and AI / 2025 base-case projection. A forecast, not measured 2030 demand.</div>

<!--
AI feels like software, but scaling it is a construction project. The International Energy Agency projects about nine hundred forty-five terawatt-hours of data center electricity demand in twenty thirty. That includes all data centers, not just AI.

Then come the land disputes, zoning fights, and people yelling “AI water!” So, why fight with the neoliberal luddites when you can go to space and ignore those morons?

That’s the sales pitch. Water use depends on the cooling system, and orbit still needs permits. But avoiding local grid and siting bottlenecks is a serious opportunity.
-->

---

# Why SpaceX?

<div class="grid3" style="margin-top:32px">
<div class="panel"><div class="mono small cyan">01 / STARSHIP</div><h2 style="margin-top:25px">Transport</h2><p class="muted">Potential to lower the cost of deploying massive hardware.</p></div>
<div class="panel"><div class="mono small cyan">02 / STARLINK</div><h2 style="margin-top:25px">Connectivity</h2><p class="muted">Satellite operations, manufacturing, and optical networking.</p></div>
<div class="panel"><div class="mono small cyan">03 / xAI</div><h2 style="margin-top:25px">Demand</h2><p class="muted">AI models, customers, and experience operating compute.</p></div>
</div>
<div class="callout" style="margin-top:25px">The thesis: integrate all three into an orbital compute platform.</div>
<div class="source">[2] SpaceX, June 2026 SEC-filed materials: xAI acquisition and orbital AI strategy. Cost advantage is a company expectation.</div>

<!--
SpaceX has a compelling combination. Starship is the potential transport system. Starlink contributes manufacturing, satellite operations, and laser networking. And xAI supplies workloads and experience running AI infrastructure. SpaceX acquired xAI in February twenty twenty-six, so this is a real corporate strategy. The investment thesis is vertical integration: control the whole chain from launch to useful computation.
-->

---
transition: scan
---

# A data center becomes a spacecraft.

<SpacecraftDiagram />
<div class="source">[3] FCC public notice: SpaceX applied for up to one million orbital data-center satellites. Diagram is a conceptual architecture.</div>

<!--
Here is the machine, and it only does three jobs. [Point to the sun and the blue panels, label one.] First, electricity in: sunlight hits the solar panels, and the glowing dots on the arms are that power flowing to the center. [Point to the box in the middle, label two.] Second, the computer: the chips in that box turn electricity into computation, and every watt they use ends up as heat. [Point to the two blue lines, label three.] Third, data in and out: there are no cables in orbit, so lasers send data up to a relay satellite and down to a ground station on Earth. [Point to the orange panel, label four.] And here is the hard part, waste heat out. Space has no air to blow heat away, so a liquid loop carries hot coolant from the computer to this radiator, which glows it off as infrared light, the wavy lines, and the cooled liquid returns. SpaceX applied for up to one million satellites.
-->

---


# Sunlight is abundant.<br><span class="amber">Continuous power takes orbital design.</span>

<div class="grid2" style="grid-template-columns:1.25fr 1fr;gap:20px">
<OrbitSystem mode="solar" />
<div style="padding-top:20px">
<div class="metric-row" style="margin-top:0"><div><strong>1,361</strong><span>W/m² SUNLIGHT AT 1 AU</span></div><div><strong>30%</strong><span>ASSUMED PANEL EFFICIENCY</span></div></div>
<div class="rule" />
<p style="font-size:23px">1 MW ÷ 408 W/m²<br><span class="cyan">≈ 2,450 m² of solar cells</span></p>
<p class="muted small" style="margin-top:14px">Ideal, normal incidence. Before losses, degradation, spacecraft loads, or eclipse storage.</p>
</div>
</div>
<div class="source">[4] NASA solar irradiance. Array sizing is our calculation. Near-continuous sunlight requires a suitable orbit and seasonal analysis.</div>

<!--
At Earth’s distance from the Sun, sunlight supplies about thirteen hundred sixty-one watts per square meter. Assume thirty percent efficient solar cells: that gives about four hundred eight watts of electricity per square meter. One megawatt therefore needs roughly twenty-four hundred fifty square meters of cells, even before losses. Ordinary low Earth orbits pass through Earth’s shadow. A dawn-dusk sun-synchronous orbit can reduce eclipses, but its actual illumination needs analysis. Sunlight is free. Reliable power still requires panels, pointing, and sometimes batteries.
-->

---
transition: fade
class: vacuum
---

<img class="thermal-bg" src="/images/thermal-concept.png" alt="Generated cutaway concept of compute hardware and radiator panels" />
<div class="thermal-shade" />

# Space is cold.<br><span class="amber">Your computer can still overheat.</span>

<div class="grid3" style="margin-top:38px">
<div class="panel" style="opacity:.6"><div class="mono small muted">CONDUCTION</div><h2 style="margin-top:25px">Needs contact.</h2><p class="muted">No ground beneath the spacecraft to conduct heat into.</p></div>
<div class="panel" style="opacity:.6"><div class="mono small muted">CONVECTION</div><h2 style="margin-top:25px">Needs fluid.</h2><p class="muted">Almost no surrounding air to carry heat away.</p></div>
<div class="panel" style="border-color:#ffbc7270"><div class="mono small amber">RADIATION</div><h2 style="margin-top:25px">Needs photons.</h2><p class="muted">The final escape route for waste heat in vacuum.</p></div>
</div>
<div class="source">[5, 6] NASA thermal-control references. Internal conduction and coolant transport still work inside the spacecraft.</div>

<!--
Here is the trap. A cold environment is useful only if heat can actually reach it. On Earth, air or water carries heat away. In vacuum, there is almost no surrounding fluid for convection. Conduction works inside the spacecraft, but there is no solid connection to a cold external reservoir. The final step must be radiation: emitting photons. Space is an excellent destination for those photons. It does not magically pull heat out of the chip.
-->

---
transition: scan
---


# Move the heat.<br>Then launch it as light.

<HeatFlow />
<div class="grid2" style="gap:22px;margin-top:7px">
<div class="callout">≈ 1 MW of electrical load → ≈ 1 MW of heat</div>
<div class="callout warning">Liquid cooling moves heat. Radiators reject it.</div>
</div>
<div class="source">[5, 6] NASA thermal-control engineering. Near-total electrical-to-heat conversion is the system-level approximation used here.</div>

<!--
We still use a cooling system. Heat conducts from the chip into a cold plate. A sealed coolant loop carries it to large radiator panels. Those panels emit infrared light into space. The coolant recirculates in a sealed system. For our estimate, essentially every watt of electrical load becomes heat, so one megawatt in means roughly one megawatt out. Pumps and supporting electronics add heat too. The radiator is not an accessory. It sets the sustainable computing power.
-->

---
clicks: 2
---


# Hotter radiators. Smaller spacecraft.

<div class="equation" style="padding:0 0 8px">

$P \approx \varepsilon \sigma A \color{#6ce9ff}{T^{4}}$

</div>
<RadiationLab />
<div class="source">[6] Stefan–Boltzmann law. ε = 0.90; σ = 5.670374419 × 10⁻⁸ W·m⁻²·K⁻⁴. Ideal deep-space view; absorbed external heat omitted.</div>

<!--
The governing equation is the Stefan–Boltzmann law. Radiated power equals emissivity, times a constant, times emitting area, times absolute temperature to the fourth power. Emissivity describes how effectively the surface emits infrared. We assume zero point nine. At three hundred kelvin, a one-megawatt heat load needs about twenty-four hundred square meters.
[click]
At three hundred thirty kelvin, that falls to about sixteen hundred fifty.
[click]
At three hundred sixty kelvin, about eleven hundred seventy. Higher temperature helps dramatically, but the radiator must remain cooler than the chips driving heat into it. We cannot simply choose any temperature we like.
-->

---

# Cooling area becomes launch mass.

<div class="grid2" style="margin-top:30px;grid-template-columns:1fr 1.1fr">
<div>
<div class="mono small cyan">ILLUSTRATIVE 1 MW MODULE / 330 K</div>
<div class="equation" style="font-size:31px;margin-top:12px">

$1{,}650\,\mathrm{m^2} \times 5\,\mathrm{kg/m^2}$

</div>
<div class="big" style="font-size:76px">8.3<span style="font-size:25px;letter-spacing:0"> tonnes</span></div>
<p class="muted" style="margin-top:14px">Radiator subsystem assumption only.<br>Before compute, solar arrays, batteries, shielding, and structure.</p>
</div>
<div class="panel">
<div class="mono small amber">LAUNCH-ONLY SENSITIVITY / NOT A QUOTE</div>
<div class="evidence-row" style="grid-template-columns:1fr 1fr"><span>$100/kg</span><strong class="cyan">$0.83M</strong></div>
<div class="evidence-row" style="grid-template-columns:1fr 1fr"><span>$1,000/kg</span><strong class="cyan">$8.3M</strong></div>
<p class="muted small" style="margin-top:18px">Compare total cost per useful compute-hour over realistic hardware life.</p>
</div>
</div>
<div class="source">Our sensitivity model: 5 kg per m² of emitting area is a scenario, not a measured SpaceX specification. Launch prices are hypothetical.</div>

<!--
Now cooling becomes an investment problem. Assume five kilograms of radiator subsystem per square meter of emitting area. That is an illustrative assumption, not a SpaceX specification. Our ideal one-megawatt radiator then weighs about eight tonnes. At a hypothetical hundred dollars per kilogram, launching just that subsystem costs about eight hundred thousand dollars. At a thousand dollars per kilogram, it costs over eight million. Everything else still needs a ride. The correct comparison is total cost per useful compute-hour, including hardware life, failures, networking, and replacement.
-->

---
transition: launch
class: hero
---

<img class="hero-bg" src="/images/deployment-concept.png" alt="Generated concept of a reusable spacecraft deploying compute satellites" style="object-position:70% center" />
<div class="hero-shade" style="background:linear-gradient(90deg,#02070df5,#02070dde 48%,#02070d33)" />
<h1 style="font-size:61px;margin-top:43px;max-width:640px">Invest in the<br><span>first mission.</span></h1>
<div style="max-width:540px;margin-top:28px">
<div class="track"><div class="index">01</div><div><h2>Fund the prototype.</h2><p>Build and launch a working orbital compute module.</p></div></div>
<div class="track"><div class="index">02</div><div><h2>Prove the economics.</h2><p>Measure cooling, uptime, and cost per useful compute-hour.</p></div></div>
<div class="track"><div class="index">03</div><div><h2>Unlock the next round.</h2><p>Scale when performance and cost targets are met.</p></div></div>
</div>
<div class="hero-credit">OUR PROPOSED INVESTMENT GATES · NOT SPACEX GUIDANCE</div>

<!--
We are asking you to fund the first orbital compute mission. Your investment pays for a prototype, its cooling system, launch, and the measurements that tell us whether this business can scale. First, we prove that the system can sustain useful computation in orbit. Then we measure its uptime and total cost per useful compute-hour against terrestrial alternatives. If the results meet our targets, we raise the next round and expand. The physics says we can radiate the heat. Your investment helps us prove we can do it profitably. Thank you.
-->

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
<div class="kicker">SpaceX / a physics investment thesis</div>
<h1>Intelligence.<br>Beyond <span>Earth.</span></h1>
<p class="lede">Orbital data centers.<br>The next infrastructure frontier?</p>
<div class="tag">Zayd Krunz · Investor briefing</div>
<div class="hero-credit">GENERATED CONCEPT ART · CLASSROOM PITCH · 15 NOV 2026</div>

<!--
Mr. Lee, imagine that our next AI data center has no address, no connection to the power grid, and no cooling tower. It circles Earth. Today, I’m pitching a SpaceX approach to orbital computing. The product is intelligence powered by sunlight. The engineering question is whether we can get rid of the heat. That question decides whether this is infrastructure or an extremely expensive space heater.
-->

---
transition: slide-left
---

<div class="kicker">01 / The opportunity</div>

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

Then come the land disputes, zoning fights, and people yelling “AI water!” So,

why fight with the neoliberal luddites when you can go to space and ignore those morons?

That’s the sales pitch. Water use depends on the cooling system, and orbit still needs permits. But avoiding local grid and siting bottlenecks is a serious opportunity.
-->

---
---

<div class="kicker">02 / Why SpaceX</div>

# Own the route. Own the network.<br><span class="cyan">Bring the workload.</span>

<div class="grid3" style="margin-top:32px">
<div class="panel"><div class="mono small cyan">01 / STARSHIP</div><h2 style="margin-top:25px">Transport</h2><p class="muted">Potential to lower the cost of deploying massive hardware.</p></div>
<div class="panel"><div class="mono small cyan">02 / STARLINK</div><h2 style="margin-top:25px">Connectivity</h2><p class="muted">Satellite operations, manufacturing, and optical networking.</p></div>
<div class="panel"><div class="mono small cyan">03 / xAI</div><h2 style="margin-top:25px">Demand</h2><p class="muted">AI models, customers, and experience operating compute.</p></div>
</div>
<div class="callout" style="margin-top:25px">The thesis: integrate all three into an orbital compute platform.</div>
<div class="source">[2] SpaceX, June 2026 SEC-filed materials: xAI acquisition and orbital AI strategy. Cost advantage is a company expectation.</div>

<!--
SpaceX has a compelling combination. Starship is the potential transport system. Starlink contributes manufacturing, satellite operations, and laser networking. And xAI supplies workloads and experience running AI infrastructure. SpaceX acquired xAI in February twenty twenty-six, so this is a real corporate strategy. The investment thesis is vertical integration: control the whole chain from launch to useful computation. The claim we still have to prove is that this combination can deliver useful compute more cheaply than an equivalent system on Earth.
-->

---
transition: scan
---

<div class="kicker">03 / The product</div>

# A data center becomes a spacecraft.

<OrbitSystem />
<div style="display:flex;gap:12px;justify-content:center"><span class="pill">Electricity in</span><span class="pill">Data in + out</span><span class="pill">Waste heat out</span></div>
<div class="source">[3] FCC public notice: SpaceX applied for up to one million orbital data-center satellites. Diagram is a conceptual architecture.</div>

<!--
Here is the machine. Solar panels generate electricity. Processors turn that electricity into computation and heat. Laser links move data between satellites and toward Earth. Radiators release the waste heat. SpaceX applied for up to one million satellites. That is a requested scale, not a deployed fleet. Our classroom proposal starts with one module, because a million copies of an unproven cooling system is a very efficient way to multiply your problems.
-->

---
---

<div class="kicker">04 / The energy advantage</div>

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
<div class="kicker">05 / The thermal trap</div>

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

<div class="kicker">06 / The cooling architecture</div>

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

<div class="kicker">07 / The law that sets the footprint</div>

# Hotter radiators. Smaller spacecraft.

<div class="equation" style="padding:0 0 8px">P <span class="muted">≈</span> εσA<span class="cyan">T<sup>4</sup></span></div>
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
---

<div class="kicker">08 / Put the numbers on the table</div>

# A megawatt needs wings.

<AreaScale />
<div class="grid2" style="margin-top:10px;gap:22px">
<div class="panel" style="padding:20px"><div class="mono small cyan">330 K / ABOUT 57°C</div><p style="font-size:24px;margin-top:9px">≈ 41 m × 41 m</p><p class="muted small" style="margin-top:5px">Equivalent square of total emitting surface.</p></div>
<div class="panel" style="padding:20px"><div class="mono small amber">SCALE TO 1 GW</div><p style="font-size:24px;margin-top:9px">≈ 1.65 km²</p><p class="muted small" style="margin-top:5px">Ideal emitting area. Hardware makes it harder.</p></div>
</div>
<div class="source">Our Stefan–Boltzmann calculation. A counts emitting faces: two clear faces can halve panel footprint, not required emitting area.</div>

<!--
At three hundred thirty kelvin, our ideal radiator area is equivalent to a square about forty-one meters on each side. That is for one megawatt. At a gigawatt, emitting area reaches about one point six five square kilometers. These are emitting areas, not necessarily the panel’s footprint. Two unobstructed faces can both radiate, reducing footprint. But structure, fluid lines, deployment, and obstructed views add difficulty. The physics allows the heat to escape. The engineering challenge is building enough lightweight, reliable surface to do it.
-->

---
transition: scan
---

<div class="kicker">09 / Real orbit, real heat inputs</div>

# The radiator needs a good view.

<div class="grid2" style="grid-template-columns:1.1fr 1fr">
<ThermalEnvironment />
<div style="padding-top:25px">
<p class="statement">Keep sunlight out.<br>Keep deep space in view.</p>
<div class="rule" />
<p class="muted" style="font-size:17px">Direct sunlight + reflected sunlight + Earth infrared all reduce net cooling.</p>
<div class="callout warning" style="margin-top:22px">Example: +200 W/m² absorbed<br>→ required area rises by ≈49%.</div>
</div>
</div>
<div class="source">[5, 6] NASA. Example: 605 − 200 ≈ 405 W/m² net at 330 K; 1 MW / 405 ≈ 2,468 m². 200 W/m² is illustrative.</div>

<!--
Our first calculation gave the radiator a perfect view of deep space. Real satellites also see sunlight, sunlight reflected by Earth, and Earth’s infrared emission. All three can add heat. Suppose our radiator absorbs an additional two hundred watts per square meter. Its net cooling falls from about six hundred five to four hundred five watts per square meter. The required area grows by roughly forty-nine percent. That is why orientation, shielding, and coatings matter. A surface should reflect sunlight while still emitting infrared efficiently.
-->

---
---

<div class="kicker">10 / The investment equation</div>

# Cooling area becomes launch mass.

<div class="grid2" style="margin-top:30px;grid-template-columns:1fr 1.1fr">
<div>
<div class="mono small cyan">ILLUSTRATIVE 1 MW MODULE / 330 K</div>
<div class="equation" style="font-size:31px;margin-top:12px">1,650 m² × 5 kg/m²</div>
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
---

<div class="kicker">11 / The evidence and the risks</div>

# Computing in orbit is real.<br><span class="cyan">Winning at scale is the test.</span>

<div class="evidence-row"><span>Starcloud</span><span>H100 launched; company reports in-orbit AI operation.</span><span class="status">DEMONSTRATED</span></div>
<div class="evidence-row"><span>Google</span><span>Reports a TPU response from its Suncatcher prototype.</span><span class="status">DEMONSTRATED</span></div>
<div class="evidence-row"><span>Our SpaceX thesis</span><span>Integrated launch + network + AI → economical scale.</span><span class="status future">TO PROVE</span></div>
<div style="display:flex;gap:10px;margin-top:30px"><span class="pill">Radiation damage</span><span class="pill">Laser bandwidth</span><span class="pill">Chip replacement</span><span class="pill">Debris + astronomy</span></div>
<div class="source">[7, 8, 9] Starcloud; Google prototype update, Oct 2026; Google Suncatcher research. Demonstrations do not establish commercial competitiveness.</div>

<!--
Competitors make this more credible. Starcloud launched an H100 and reports running AI in orbit. Google reports a response from a TPU on its Suncatcher prototype. Those demonstrations establish that computation in space is possible. They do not establish cheap industrial scale. Radiation can damage electronics. Distributed training needs extremely fast communication. Failed chips are difficult to replace. Debris and astronomy impacts also matter. Our first workload should be independent inference or satellite-data processing, where we do not need an entire constellation to behave like one tightly connected supercomputer.
-->

---
transition: launch
class: hero
---

<img class="hero-bg" src="/images/deployment-concept.png" alt="Generated concept of a reusable spacecraft deploying compute satellites" style="object-position:70% center" />
<div class="hero-shade" style="background:linear-gradient(90deg,#02070df5,#02070dde 48%,#02070d33)" />
<div class="kicker">12 / The ask</div>
<h1 style="font-size:61px;margin-top:43px;max-width:640px">Fund the proof.<br><span>Then scale.</span></h1>
<div style="max-width:540px;margin-top:28px">
<div class="track"><div class="index">01</div><div><h2>Prove thermal performance.</h2><p>Hold full compute load through real orbital conditions.</p></div></div>
<div class="track"><div class="index">02</div><div><h2>Measure useful economics.</h2><p>Compare complete lifecycle cost with terrestrial compute.</p></div></div>
<div class="track"><div class="index">03</div><div><h2>Earn the next deployment.</h2><p>Scale only after reliability, safety, and cost gates pass.</p></div></div>
</div>
<div class="hero-credit">OUR PROPOSED INVESTMENT GATES · NOT SPACEX GUIDANCE</div>

<!--
Our ask is funding for a staged demonstration. First, sustain full computing power while measuring thermal performance across real orbital conditions. Second, demonstrate reliable communication and useful computation. Third, compare complete lifecycle economics against a terrestrial alternative, with a credible disposal plan. If those gates pass, scale. My verdict: orbital data centers are physically plausible. Commercial superiority remains conditional. SpaceX has a compelling combination of capabilities, but the winning product is not just a chip in space. It is a complete system that can afford to radiate every watt it consumes. Thank you.
-->

---
layout: end
---

<!--
-->

---
---

<div class="kicker">Appendix A / Technical backup</div>

# The full heat balance.

<div class="equation" style="font-size:37px">P<sub>internal</sub> + Q<sub>absorbed</sub> = P<sub>emitted</sub></div>
<div class="grid2">
<div class="panel"><h2>Idealized sink model</h2><p style="font-size:22px;margin-top:20px">P<sub>net</sub> = εσA(T⁴ − T<sub>sink</sub>⁴)</p><p class="muted small" style="margin-top:15px">A uniform effective sink is a simplification. Real Earth and Sun geometry requires view factors and spectral properties.</p></div>
<div class="panel"><h2>Our baseline assumptions</h2><p class="muted" style="line-height:1.9">P = 1 MW waste heat<br>ε = 0.90, uniform panel temperature<br>T = 330 K; ideal deep-space view<br>Emitting area ≈ 1,652 m²</p></div>
</div>
<div class="callout warning" style="margin-top:23px">Chip temperature &gt; coolant temperature &gt; radiator temperature. Raising T consumes thermal margin.</div>
<div class="source">[5, 6] NASA thermal-control references. Geometry and environmental inputs are omitted from the baseline, not from an eventual design.</div>

---
---

<div class="kicker">Appendix B / Source register</div>

# Announcements & demonstrations.

<div class="refs">
<div><a href="https://www.iea.org/reports/energy-and-ai/executive-summary">[1] IEA · Energy and AI</a><p>2025 report. 945 TWh total data center demand in 2030, base case.</p></div>
<div><a href="https://www.sec.gov/Archives/edgar/data/1181412/000162828026041013/japanfwp_06042026.htm">[2] SpaceX · SEC-filed materials</a><p>June 2026. xAI acquisition; integrated orbital AI strategy and execution risks.</p></div>
<div><a href="https://docs.fcc.gov/public/attachments/DA-26-113A1.pdf">[3] FCC · DA 26-113 public notice</a><p>Application for up to one million satellites. Filing is distinct from deployment.</p></div>
<div><a href="https://www.starcloud.com/starcloud-1">[7] Starcloud · Starcloud-1</a><p>Company report of H100 launch and in-orbit AI operation.</p></div>
<div><a href="https://blog.google/innovation-and-ai/models-and-research/google-research/project-suncatcher-satellite-response/">[8] Google · Suncatcher prototype</a><p>October 2026 report of a TPU-generated response in orbit.</p></div>
<div><a href="https://research.google/blog/exploring-a-space-based-scalable-ai-infrastructure-system-design/">[9] Google Research · Project Suncatcher</a><p>November 2025 research: optical links, radiation, and cost sensitivities.</p></div>
</div>
<div class="source">Sources checked 15 November 2026. Company reports are attributed; our proposal is a classroom exercise.</div>

---
---

<div class="kicker">Appendix C / Physics & art</div>

# Reproducible physics. Original art.

<div class="refs">
<div><a href="https://earth.gsfc.nasa.gov/climate/projects/solar-irradiance/science">[4] NASA · Solar irradiance science</a><p>Approximately 1,361 W/m² at Earth’s orbital distance.</p></div>
<div><a href="https://www.nasa.gov/smallsat-institute/sst-soa/thermal-control/">[5] NASA · Small spacecraft thermal control</a><p>Radiation, solar absorptivity, infrared emissivity, and orbital heat inputs.</p></div>
<div><a href="https://ntrs.nasa.gov/api/citations/20230013900/downloads/NASA%20Thermal%20Control%20Engineering%20Guidebook%20v4.pdf">[6] NASA · Thermal Control Engineering Guidebook</a><p>Stefan–Boltzmann relation and thermal design principles.</p></div>
<div><h2 style="font-size:18px;color:var(--cyan)">Generated concept artwork</h2><p>Created for this presentation with OpenAI image generation. Illustrative hardware; no claim to depict an existing SpaceX design. Infrared is visualized symbolically in diagrams.</p></div>
</div>
<div class="callout" style="margin-top:36px">Calculations, assumptions, and source links: <span class="mono">SOURCES.md</span><br>Read-aloud script and pacing: <span class="mono">SCRIPT.md</span></div>
<div class="source">SpaceX themed educational pitch by Zayd Krunz. No official affiliation or investment offering.</div>

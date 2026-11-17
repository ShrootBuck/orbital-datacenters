# Sources and numerical assumptions

Research checked November 15, 2026. Company reports are attributed as such. The presentation is a classroom proposal, not a representation of an existing SpaceX thermal design.

## Source register

1. **International Energy Agency, Energy and AI (2025), executive summary.** https://www.iea.org/reports/energy-and-ai/executive-summary — Base-case projection: global electricity consumption of all data centers reaches about 945 TWh in 2030. This is not an AI-only figure or a measurement of future demand.
2. **SpaceX, June 2026 SEC-filed company materials.** https://www.sec.gov/Archives/edgar/data/1181412/000162828026041013/japanfwp_06042026.htm — Supports the February 2026 xAI acquisition and SpaceX's stated thesis combining launch, satellite networking, and AI. The orbital cost and scale advantages are company expectations, not independently established results. Relevant sections: orbital AI compute and risk factors.
3. **FCC Space Bureau public notice, DA 26-113.** https://docs.fcc.gov/public/attachments/DA-26-113A1.pdf — Describes SpaceX's January 30, 2026 application for up to one million orbital data-center satellites. An application is not a deployed fleet. The deck makes no claim about the ultimate approved or deployed count.
4. **NASA Goddard, Solar Irradiance Science.** https://earth.gsfc.nasa.gov/climate/projects/solar-irradiance/science — Approximately 1,361 W/m² of total solar irradiance at Earth's distance, normal to incoming sunlight.
5. **NASA Small Spacecraft Systems Virtual Institute, State of the Art: Thermal Control.** https://www.nasa.gov/smallsat-institute/sst-soa/thermal-control/ — Heat transport and rejection mechanisms, environmental heating, solar absorptivity, infrared emissivity, and radiator design.
6. **NASA Passive Thermal Control Engineering Guidebook (2023).** https://ntrs.nasa.gov/api/citations/20230013900/downloads/NASA%20Thermal%20Control%20Engineering%20Guidebook%20v4.pdf — Radiative heat exchange and thermal design principles.
7. **Starcloud, Starcloud-1 mission page.** https://www.starcloud.com/starcloud-1 — Company reports November 2025 launch with an NVIDIA H100 and subsequent in-orbit AI operation. The deck avoids claiming a specific model identity because the company's naming differs from some contemporary reporting.
8. **Google, Project Suncatcher prototype response update (October 2026).** https://blog.google/innovation-and-ai/models-and-research/google-research/project-suncatcher-satellite-response/ — Company report of an AI response from a TPU in orbit after its October 1 prototype launch.
9. **Google Research, Exploring a space-based, scalable AI infrastructure system design (November 4, 2025).** https://research.google/blog/exploring-a-space-based-scalable-ai-infrastructure-system-design/ — Explores optical interconnects, radiation effects, orbital design, and launch-cost sensitivity. Its economic scenarios are not proof of current commercial superiority.

## Baseline radiation calculation

All values below are our idealized calculations, not measured SpaceX hardware specifications.

Stefan–Boltzmann constant: σ = 5.670374419 × 10⁻⁸ W m⁻² K⁻⁴.

For a gray radiator viewing an ideal cold sink:

`P = ε σ A (T⁴ − Tsink⁴) ≈ ε σ A T⁴`

Assume ε = 0.90, P = 1,000,000 W, uniform radiator surface temperature, a clear view to deep space, and no absorbed environmental heating.

| Radiator temperature | Celsius | Emitted flux | Required emitting area | Equivalent square side |
| --- | --- | --- | --- | --- |
| 300 K | 26.85°C | 413.37 W/m² | 2,419 m² | 49.2 m |
| 330 K | 56.85°C | 605.22 W/m² | 1,652 m² | 40.6 m |
| 360 K | 86.85°C | 857.16 W/m² | 1,167 m² | 34.2 m |

Emitting area counts the radiating faces. Two faces can halve footprint only when both have effective cold-sink views; they do not halve the total emitting surface required. The squares illustrate equivalent emitting area, not a finalized deployable panel geometry. At 1 GW and the same temperature and emissivity, the ideal emitting area is approximately 1.652 km².

A chip's junction temperature must exceed the radiator temperature to drive passive heat flow through the thermal resistances. 360 K is a sensitivity case, not an assertion that a particular processor/coolant assembly can tolerate that radiator temperature. Active refrigeration would add power and reject additional heat.

## Environmental heating example

A full model includes direct sunlight, albedo, Earth infrared, mutual view factors, spectral properties, nonuniform temperatures, degradation, eclipse cycling, and design margin.

At 330 K, assume **200 W/m² of absorbed external heat**. This is an illustrative heat input, not a universal orbital value. Net flux becomes `605.22 − 200 = 405.22 W/m²`, requiring about `2,468 m²`. Relative to the ideal baseline, area increases by approximately **49.4%**.

Solar absorptivity and infrared emissivity refer to different wavelength bands. A surface can reflect visible sunlight efficiently while emitting thermal infrared efficiently. A visually white radiator can therefore be a useful design choice; visible blackness is not a reliable proxy for infrared emissivity.

## Solar power example

`1,361 W/m² × 0.30 = 408.3 W/m² electrical output`

`1,000,000 W / 408.3 W/m² = 2,449 m² active cell area`

30% efficiency is an assumption. This ideal value excludes conversion losses, packing factor, pointing error, solar-cell temperature effects, degradation, spacecraft loads, and storage. It assumes normal incidence. A larger physical array and/or power derating would be required in a practical design. Ordinary LEO can eclipse. Near-continuous sunlight requires an appropriate dawn-dusk sun-synchronous orbit and a seasonal eclipse analysis; it is not true of every orbit.

## Illustrative mass and launch sensitivity

Use **5 kg per m² of emitting area** for the radiator subsystem. This is a scenario for reasoning, not a validated technology specification, and its definition must be held consistent when comparing one-sided and two-sided panels.

`1,652 m² × 5 kg/m² ≈ 8,260 kg`

At hypothetical launch prices of $100/kg and $1,000/kg, radiator launch costs alone are approximately $0.83 million and $8.3 million. Neither is a current SpaceX price quote or a prediction. These omit radiator manufacturing, solar arrays, compute, spacecraft structure, power systems, batteries, shielding, integration, operations, failures, financing, and disposal. Hardware obsolescence and utilization matter. No revenue forecast, valuation, or investment return is fabricated.

The proposed investment gates are our classroom recommendation: sustained thermal performance, useful workload and network reliability, complete lifecycle economics, and safe end-of-life disposal. Start with independent inference or processing of space-origin data; tightly synchronized large-scale training imposes harder interconnect demands.

## Earth orbit versus heliocentric training concept

Added November 17, 2026. SpaceX’s filed system operates in Earth orbit, including sun-synchronous orbits, at 500–2,000 km altitude: [FCC DA 26-113](https://docs.fcc.gov/public/attachments/DA-26-113A1.pdf). Sun-synchronous describes an Earth orbit whose plane precesses to maintain approximately the same orientation relative to the Sun. Heliocentric describes an orbit about the Sun.

The Earth-orbit inference / heliocentric batch-training split is our proposed longer-term architecture, not a claim about SpaceX’s announced deployment or an exclusive technical requirement. Both workloads can run in Earth orbit. Training still needs compact, fast internal interconnects; Google's [Suncatcher research](https://research.google/blog/exploring-a-space-based-scalable-ai-infrastructure-system-design/) supports that networking constraint, not the heliocentric proposal.

For an illustrative Earth-to-cluster distance of 1,000,000 km, the one-way light-time is distance / c = 1,000,000 / 299,792.458 ≈ 3.34 seconds; round-trip propagation alone is about 6.67 seconds. Distance depends on the chosen trajectory and changes over time; solar orbit does not imply a fixed delay. Batch training may tolerate this delay to Earth if data and tightly coupled computation remain local to the cluster. Dataset and checkpoint transfer bandwidth also matter.

Avoiding Earth eclipses requires a suitable trajectory and geometry. At the same distance from the Sun, irradiance is approximately the same; going heliocentric does not inherently increase available sunlight. Radiative heat rejection remains necessary. Deployment, communications, stationkeeping, radiation exposure, and servicing require an independent engineering analysis before this concept could be funded as a deployment program.

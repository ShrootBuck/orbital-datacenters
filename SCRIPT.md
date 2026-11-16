# Orbital Datacenters — read-aloud script

Read the paragraphs verbatim. Bracketed cues are stage directions, not spoken words. Advance once between slides. Slide 8 has two additional clicks marked in the script. Stop after slide 13; the appendix is for questions only.

**Spoken words:** 1082. **Target pace:** 125 words per minute. Speech alone is approximately 8.7 minutes; allow 35–45 seconds total for transitions and pauses. Target a 9:15–9:30 finish. Rehearse to establish your actual reading time.

## Slide 1 — Intelligence. Beyond Earth.

Target: about 35 seconds; cumulative 0:35.

Mr. Lee, imagine that our next AI data center has no address, no connection to the power grid, and no cooling tower. It circles Earth. Today, I’m pitching a SpaceX approach to orbital computing. The product is intelligence powered by sunlight. The engineering question is whether we can get rid of the heat. That question decides whether this is infrastructure or an extremely expensive space heater.

## Slide 2 — The physical bottleneck

Target: about 48 seconds; cumulative 1:23.

AI feels like software, but scaling it is a construction project. The International Energy Agency projects about nine hundred forty-five terawatt-hours of data center electricity demand in twenty thirty. That includes all data centers, not just AI.

Then come the land disputes, zoning fights, and people yelling “AI water!” So,

why fight with the neoliberal luddites when you can go to space and ignore those morons?

That’s the sales pitch. Water use depends on the cooling system, and orbit still needs permits. But avoiding local grid and siting bottlenecks is a serious opportunity.

## Slide 3 — Why SpaceX

Target: about 41 seconds; cumulative 2:04.

SpaceX has a compelling combination. Starship is the potential transport system. Starlink contributes manufacturing, satellite operations, and laser networking. And xAI supplies workloads and experience running AI infrastructure. SpaceX acquired xAI in February twenty twenty-six, so this is a real corporate strategy. The investment thesis is vertical integration: control the whole chain from launch to useful computation. The claim we still have to prove is that this combination can deliver useful compute more cheaply than an equivalent system on Earth.

## Slide 4 — The spacecraft architecture

Target: about 38 seconds; cumulative 2:42.

Here is the machine. Solar panels generate electricity. Processors turn that electricity into computation and heat. Laser links move data between satellites and toward Earth. Radiators release the waste heat. SpaceX applied for up to one million satellites. That is a requested scale, not a deployed fleet. Our classroom proposal starts with one module, because a million copies of an unproven cooling system is a very efficient way to multiply your problems.

## Slide 5 — Solar power and orbit

Target: about 42 seconds; cumulative 3:24.

At Earth’s distance from the Sun, sunlight supplies about thirteen hundred sixty-one watts per square meter. Assume thirty percent efficient solar cells: that gives about four hundred eight watts of electricity per square meter. One megawatt therefore needs roughly twenty-four hundred fifty square meters of cells, even before losses. Ordinary low Earth orbits pass through Earth’s shadow. A dawn-dusk sun-synchronous orbit can reduce eclipses, but its actual illumination needs analysis. Sunlight is free. Reliable power still requires panels, pointing, and sometimes batteries.

## Slide 6 — The thermal trap

Target: about 39 seconds; cumulative 4:03.

Here is the trap. A cold environment is useful only if heat can actually reach it. On Earth, air or water carries heat away. In vacuum, there is almost no surrounding fluid for convection. Conduction works inside the spacecraft, but there is no solid connection to a cold external reservoir. The final step must be radiation: emitting photons. Space is an excellent destination for those photons. It does not magically pull heat out of the chip.

## Slide 7 — The cooling architecture

Target: about 40 seconds; cumulative 4:43.

We still use a cooling system. Heat conducts from the chip into a cold plate. A sealed coolant loop carries it to large radiator panels. Those panels emit infrared light into space. The coolant recirculates in a sealed system. For our estimate, essentially every watt of electrical load becomes heat, so one megawatt in means roughly one megawatt out. Pumps and supporting electronics add heat too. The radiator is not an accessory. It sets the sustainable computing power.

## Slide 8 — The radiation law

Target: about 50 seconds; cumulative 5:33.

The governing equation is the Stefan–Boltzmann law. Radiated power equals emissivity, times a constant, times emitting area, times absolute temperature to the fourth power. Emissivity describes how effectively the surface emits infrared. We assume zero point nine. At three hundred kelvin, a one-megawatt heat load needs about twenty-four hundred square meters.
[click]
At three hundred thirty kelvin, that falls to about sixteen hundred fifty.
[click]
At three hundred sixty kelvin, about eleven hundred seventy. Higher temperature helps dramatically, but the radiator must remain cooler than the chips driving heat into it. We cannot simply choose any temperature we like.

## Slide 9 — Radiator scale

Target: about 43 seconds; cumulative 6:16.

At three hundred thirty kelvin, our ideal radiator area is equivalent to a square about forty-one meters on each side. That is for one megawatt. At a gigawatt, emitting area reaches about one point six five square kilometers. These are emitting areas, not necessarily the panel’s footprint. Two unobstructed faces can both radiate, reducing footprint. But structure, fluid lines, deployment, and obstructed views add difficulty. The physics allows the heat to escape. The engineering challenge is building enough lightweight, reliable surface to do it.

## Slide 10 — Environmental heat inputs

Target: about 44 seconds; cumulative 7:00.

Our first calculation gave the radiator a perfect view of deep space. Real satellites also see sunlight, sunlight reflected by Earth, and Earth’s infrared emission. All three can add heat. Suppose our radiator absorbs an additional two hundred watts per square meter. Its net cooling falls from about six hundred five to four hundred five watts per square meter. The required area grows by roughly forty-nine percent. That is why orientation, shielding, and coatings matter. A surface should reflect sunlight while still emitting infrared efficiently.

## Slide 11 — Mass and economics

Target: about 44 seconds; cumulative 7:44.

Now cooling becomes an investment problem. Assume five kilograms of radiator subsystem per square meter of emitting area. That is an illustrative assumption, not a SpaceX specification. Our ideal one-megawatt radiator then weighs about eight tonnes. At a hypothetical hundred dollars per kilogram, launching just that subsystem costs about eight hundred thousand dollars. At a thousand dollars per kilogram, it costs over eight million. Everything else still needs a ride. The correct comparison is total cost per useful compute-hour, including hardware life, failures, networking, and replacement.

## Slide 12 — Evidence and risks

Target: about 46 seconds; cumulative 8:30.

Competitors make this more credible. Starcloud launched an H100 and reports running AI in orbit. Google reports a response from a TPU on its Suncatcher prototype. Those demonstrations establish that computation in space is possible. They do not establish cheap industrial scale. Radiation can damage electronics. Distributed training needs extremely fast communication. Failed chips are difficult to replace. Debris and astronomy impacts also matter. Our first workload should be independent inference or satellite-data processing, where we do not need an entire constellation to behave like one tightly connected supercomputer.

## Slide 13 — The investment ask

Target: about 48 seconds; cumulative 9:18.

Our ask is funding for a staged demonstration. First, sustain full computing power while measuring thermal performance across real orbital conditions. Second, demonstrate reliable communication and useful computation. Third, compare complete lifecycle economics against a terrestrial alternative, with a credible disposal plan. If those gates pass, scale. My verdict: orbital data centers are physically plausible. Commercial superiority remains conditional. SpaceX has a compelling combination of capabilities, but the winning product is not just a chip in space. It is a complete system that can afford to radiate every watt it consumes. Thank you.

# Orbital Datacenters — read-aloud script

Read the speaker notes verbatim. Bracketed directions are not spoken. Present all 11 slides. Slide 9 has two extra clicks, marked in the script.

Spoken words: 1047. Target: approximately nine minutes, including transitions and pointing. At 125 words per minute, speech takes 8.4 minutes; allow about 45 seconds for transitions, pointing, and pauses. The requested window is 8–10 minutes. Rehearse once to check actual delivery.

## Slide 1 — Opening pitch

Cumulative target: 0:36

Mr. Lee, imagine that our next AI data center has no address, no connection to the power grid, and no cooling tower. It circles Earth. Today, I’m pitching a SpaceX approach to orbital computing. The product is intelligence powered by sunlight. The engineering question is whether we can get rid of the heat. That question decides whether this is infrastructure or an extremely expensive space heater.

## Slide 2 — The physical bottleneck

Cumulative target: 1:25

AI feels like software, but scaling it is a construction project. The International Energy Agency projects about nine hundred forty-five terawatt-hours of data center electricity demand in twenty thirty. That includes all data centers, not just AI.

Then come the land disputes, zoning fights, and people yelling “AI water!” So, why fight with the neoliberal luddites when you can go to space and ignore those morons?

That’s the sales pitch. Water use depends on the cooling system, and orbit still needs permits. But avoiding local grid and siting bottlenecks is a serious opportunity.

## Slide 3 — Why SpaceX?

Cumulative target: 1:56

SpaceX has a compelling combination. Starship is the potential transport system. Starlink contributes manufacturing, satellite operations, and laser networking. And xAI supplies workloads and experience running AI infrastructure. SpaceX acquired xAI in February twenty twenty-six, so this is a real corporate strategy. The investment thesis is vertical integration: control the whole chain from launch to useful computation.

## Slide 4 — Spacecraft architecture

Cumulative target: 3:04

Here is the machine, and it does four jobs. [Point to the sun and the blue panels, label one.] First, electricity in: sunlight hits the solar panels, and the glowing dots on the arms are that power flowing to the center. [Point to the box in the middle, label two.] Second, the computer: the chips in that box turn electricity into computation, and every watt they use ends up as heat. [Point to the two blue lines, label three.] Third, data in and out: there are no cables in orbit, so lasers send data up to a relay satellite and down to a ground station on Earth. [Point to the orange panel, label four.] And here is the hard part, waste heat out. Space has no air to blow heat away, so a liquid loop carries hot coolant from the computer to this radiator, which glows it off as infrared light, the wavy lines, and the cooled liquid returns. SpaceX applied for up to one million satellites.

## Slide 5 — Solar power

Cumulative target: 3:47

At Earth’s distance from the Sun, sunlight supplies about thirteen hundred sixty-one watts per square meter. Assume thirty percent efficient solar cells: that gives about four hundred eight watts of electricity per square meter. One megawatt therefore needs roughly twenty-four hundred fifty square meters of cells, even before losses. Ordinary low Earth orbits pass through Earth’s shadow. A dawn-dusk sun-synchronous orbit can reduce eclipses, but its actual illumination needs analysis. Sunlight is free. Reliable power still requires panels, pointing, and sometimes batteries.

## Slide 6 — Earth orbit versus Sun orbit

Cumulative target: 5:14

Here is the distinction: sun-synchronous means going around Earth while keeping a consistent orientation relative to the Sun. Heliocentric means going around the Sun itself. SpaceX’s filed proposal is Earth orbit, five hundred to two thousand kilometers up.

For our investment strategy, Earth orbit is the starting point for interactive inference: answering users with a short communication path. Our longer-term concept puts a compact training cluster in solar orbit. With suitable positioning, it could avoid Earth’s recurring shadow and crowded Earth orbits. Staying near Earth’s solar distance gives similar sunlight per square meter. Upload the dataset, run the job locally, and send back model checkpoints. At a million kilometers from Earth, light takes about three seconds each way. That can be manageable for scheduled training; it is terrible for a live conversation.

But the training chips still need fast links to each other. And solar orbit brings harder deployment and servicing. Training can also happen around Earth. This is a proposed division of workloads, not a physical requirement or SpaceX’s announced solar-orbit plan.

## Slide 7 — The thermal trap

Cumulative target: 5:54

Here is the trap. A cold environment is useful only if heat can actually reach it. On Earth, air or water carries heat away. In vacuum, there is almost no surrounding fluid for convection. Conduction works inside the spacecraft, but there is no solid connection to a cold external reservoir. The final step must be radiation: emitting photons. Space is an excellent destination for those photons. It does not magically pull heat out of the chip.

## Slide 8 — Cooling architecture

Cumulative target: 6:35

We still use a cooling system. Heat conducts from the chip into a cold plate. A sealed coolant loop carries it to large radiator panels. Those panels emit infrared light into space. The coolant recirculates in a sealed system. For our estimate, essentially every watt of electrical load becomes heat, so one megawatt in means roughly one megawatt out. Pumps and supporting electronics add heat too. The radiator is not an accessory. It sets the sustainable computing power.

## Slide 9 — Radiation law

Cumulative target: 7:26

The governing equation is the Stefan–Boltzmann law. Radiated power equals emissivity, times a constant, times emitting area, times absolute temperature to the fourth power. Emissivity describes how effectively the surface emits infrared. We assume zero point nine. At three hundred kelvin, a one-megawatt heat load needs about twenty-four hundred square meters.
[click]
At three hundred thirty kelvin, that falls to about sixteen hundred fifty.
[click]
At three hundred sixty kelvin, about eleven hundred seventy. Higher temperature helps dramatically, but the radiator must remain cooler than the chips driving heat into it. We cannot simply choose any temperature we like.

## Slide 10 — Mass and launch economics

Cumulative target: 8:11

Now cooling becomes an investment problem. Assume five kilograms of radiator subsystem per square meter of emitting area. That is an illustrative assumption, not a SpaceX specification. Our ideal one-megawatt radiator then weighs about eight tonnes. At a hypothetical hundred dollars per kilogram, launching just that subsystem costs about eight hundred thousand dollars. At a thousand dollars per kilogram, it costs over eight million. Everything else still needs a ride. The correct comparison is total cost per useful compute-hour, including hardware life, failures, networking, and replacement.

## Slide 11 — Investment ask

Cumulative target: 9:06

We are asking you to fund the first mission in Earth orbit. Your investment pays for a prototype, its cooling system, launch, and the measurements that tell us whether this business can scale. First, we prove that the system can sustain useful computation in orbit. Then we measure its uptime and total cost per useful compute-hour against terrestrial alternatives. If the results meet our targets, we raise the next round and expand. Start with useful inference near Earth. Prove the platform, then pursue larger training clusters. The physics says we can radiate the heat. Your investment helps us prove we can do it profitably. Thank you.

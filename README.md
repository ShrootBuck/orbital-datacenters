# Orbital Datacenters

A cinematic, SpaceX themed classroom investor pitch by Zayd Krunz about the physics and viability of orbital AI computing. The central question: can a spacecraft reject enough waste heat, with sufficiently little mass, to make the economics work?

## Run with Bun

```sh
bun install --frozen-lockfile
bun run dev
```

Open http://localhost:3030 for the presentation or http://localhost:3030/presenter for the script, next slide, and timer. Press **F** for fullscreen, **Space** or **Right** to advance, and **Left** to go back.

The dev command uses polling to avoid macOS file watcher limits. Dependencies are locked in `bun.lock`. The font and all artwork are stored locally; once installed, presenting does not need to fetch external images or fonts.

## Timing and delivery

- Present all **11 slides**, ending with the investment ask.
- Speaker notes are the verbatim script; [SCRIPT.md](SCRIPT.md) provides a standalone copy with pacing.
- Target approximately **nine minutes**, including transitions and pointing, at about 125 words per minute. Rehearse to confirm an 8–10 minute delivery.
- Slide **6** distinguishes Earth orbit from solar orbit. Earth-orbit inference is the proposed starting point; heliocentric batch training is our longer-term concept, not SpaceX’s filed plan.
- Slide **9** has two extra clicks: 300 K → 330 K → 360 K, marked in the script.
- Diagrams animate automatically; advance without waiting for a full animation loop.

## Build

```sh
bun run build
```

The static site is written to `dist/`. For an optional PDF export, install the official exporter dependency with `bun add -d playwright-chromium`, then run `bun run export`. The live Slidev version preserves motion and presenter features.

## Project files

- `slides.md` — slides and verbatim speaker notes
- `SCRIPT.md` — standalone script with pacing
- `SOURCES.md` — references, numerical assumptions, and reproducible calculations
- `ART_DIRECTION.md` — generated image prompts and provenance
- `components/` — animated orbital, heat-flow, and radiation visuals
- `style.css` — typography, visual system, transitions, and motion

Company statements are attributed. Numerical design examples are explicitly labeled as our assumptions. This is an educational pitch, not an official SpaceX presentation.

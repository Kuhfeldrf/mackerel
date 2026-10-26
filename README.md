# mackerel – chub mackerel throw flasher

A 3D-printable spearfishing throw flasher shaped and patterned like a Pacific chub mackerel (*Scomber japonicus*), weighted to sink like a dead or wounded baitfish.

**Live 3D viewer and sink test:** https://kuhfeldrf.github.io/mackerel/

**Sink test video:** [files/mackerel_sink_test_headdown.mp4](files/mackerel_sink_test_headdown.mp4) – the head-down design with 36 g of tungsten in the head, simulated down to 10 m.

## Head-down slow spiral (default design)

The goal is a slow, head-first spiral with a little flutter, the way a dying baitfish sinks.

| | Simulated with 36 g head charge |
|---|---|
| Attitude | Head down about 24° |
| Flutter | Rocks about ±13° |
| Spiral | One turn every ~2.3 s, within a ~25 cm circle |
| Sink rate | ~0.38 m/s, 10 m in ~25 s |

### Weighting and design strategy

1. **Put the weight in the head.** A 9 cc head cavity, open on both halves' flat faces, takes tungsten putty packed hard against the snout end. The rest of the cavity is filled with epoxy. Head weight is what tips the fish nose-down.
2. **Make the rear body light, like a deflated swim bladder.** Two sealed air voids (about 22 cc in total) are printed inside the back and belly halves, behind the gut. They take mass out of the rear without changing the outside shape, which moves the balance point well forward while keeping the weight in water small (about 27 g).
3. **Keep the weight in water low.** A heavy, head-weighted flat body glides like a paper plane. A light one with its balance far forward sinks head-first. Head-first alone is streamlined and drops fast, though, so the sweet spot is a moderate tilt with the flank partly facing the water. That gives the slow fall and the flash.
4. **Kick the tail 20°.** The bent tail acts like a rudder. In the downward flow it turns the fish, which turns the fall into a spiral. The flattened flanks rock as it turns, which is the flutter.
5. **Leave the gut as epoxy.** Tungsten in the gut cavity makes the simulated fish glide level instead of tipping head-down.

### Tuning (pool-test before diving)

| Head charge | Simulated fall |
|---|---|
| 25 g | Steeper head-down (~39°), more flutter, faster |
| 30 g | Head-down ~32°, lively flutter |
| **36 g** | **Head-down ~24°, light flutter, slow spiral – start here** |
| 40 g | Flatter (~19°), slower, gentle |
| 50 g | Nearly level, slow, wide circles |

Add or remove putty 2–3 g at a time. Packing it further forward tips the head down more.

### Build notes

- Print both halves flat face down at 100% infill with at least 3 perimeters. The air voids are enclosed inside each half, so the slicer bridges their roofs. Check that no top-skin gaps are left over them.
- Before gluing, hold each half under warm water: bubbles mean a leaky void.
- Put the wire through the channel, pack the head cavity with putty and epoxy, fill the gut cavity with epoxy, set the pins, then glue the halves. Keep epoxy out of the air voids. They are sealed off from the wire channel by a 4 mm web.

## S-curve option

The same head-and-air weighting in an S-shaped body: a 95° front curve and a 120° rear curve the other way, nearly as deep as the U-curl but open. Footprint is 173 × 111 mm. It prints as back and belly halves like the others.

With 25 g of tungsten in the head it falls a steady ~50° head-down. It turns very slowly (about one turn every 17 s) within a ~10 cm circle and sinks at ~0.36 m/s, with almost no flutter. Charges from 15 g (slowest, ~0.25 m/s) to 36 g (faster) are simulated in the viewer.

## All four designs

| | Head-down (default) | S-curve | U-curl | Straight |
|---|---|---|---|---|
| Shape | Straight body, 20° tail kick | Two opposing curves (95° / 120°) | Curled 230° | 250 × 61 mm flattened body |
| Halves | Back / belly | Back / belly | Back / belly | Left / right flank |
| Ballast | 36 g tungsten in head + sealed air | 25 g tungsten in head + sealed air | Tungsten in chamber C | Tungsten in chamber B |
| Simulated fall | Head-down spiral with light flutter | Steep head-down, very slow turn, no flutter | U-down, rocking | Level, rocking flutter |
| Pattern | Engraved lines, airbrush + wash | Engraved lines, airbrush + wash | Engraved lines, airbrush + wash | Waterslide decal over chrome |

## Sink simulation

The viewer's **Sink test** plays a precomputed 6-DOF simulation for every ballast setup. It models buoyancy, pressure drag on each surface facet, skin friction, added mass with the Munk moment, and quasi-steady circulation lift on the flanks. It is a simplified model meant for comparing setups, not for exact numbers.

## Files

- `files/wounded_mackerel_BACK_half.stl`, `files/wounded_mackerel_BELLY_half.stl` – head-down design
- `files/scurve_mackerel_BACK_half.stl`, `files/scurve_mackerel_BELLY_half.stl` – S-curve
- `files/curled_mackerel_DORSAL_half.stl`, `files/curled_mackerel_VENTRAL_half.stl` – U-curl
- `files/mackerel_flasher_LEFT_half.stl`, `files/mackerel_flasher_RIGHT_half.stl` – straight
- `files/chub_mackerel_flasher_decals_and_build_sheet.pdf` – decals and build steps (straight version)
- `files/mackerel_sink_test_headdown.mp4`, `files/mackerel_sink_test_curl.mp4` – simulated sink videos
- `files/mackerel_flasher_source.zip` – parametric Python source, including the simulator

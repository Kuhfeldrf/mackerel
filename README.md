# mackerel – chub mackerel throw flasher

A 3D-printable spearfishing throw flasher shaped and patterned like a Pacific chub mackerel (*Scomber japonicus*), weighted to sink like a dead or wounded baitfish.

**Live 3D viewer and sink test:** https://kuhfeldrf.github.io/mackerel/

**Sink test video:** [files/mackerel_sink_test_headdown.mp4](files/mackerel_sink_test_headdown.mp4) – the head-down design with its default weighting, simulated down to 10 m.

## One-piece PLA prints (OSU Valley Library)

The library prints PLA only (one material and colour, no multi-material). Files must be STL under 5 MB, and it charges 16¢ per gram. Every design below prints as **one piece**, so there are no halves to glue. Each file is oriented upright (back up) so the body bend lies flat in the print plane, and only the belly needs supports.

| File | What it is | Size (L × W × H) | PLA | Cost |
|---|---|---|---|---|
| `files/onepiece/headdown_onepiece.stl` | **Head-down slow spiral**: 35° bend, 10° tail kick, sealed air voids printed inside, 10 mm bore between the eyes for lead | 222 × 97 × 61 mm | ~72 g | ~$12 |
| `files/onepiece/headdown_kick0_onepiece.stl`, `…kick20…` | Same, with 0° / 20° tail kick (spiral tuning) | similar | ~72 g | ~$12 |
| `files/onepiece/scurve_onepiece.stl` | S-curve, solid plastic: no lead, no air | 173 × 111 × 61 mm | ~100 g | ~$16 |
| `files/onepiece/ucurl_onepiece.stl`, `straight_onepiece.stl` | U-curl and straight, solid plastic (not tuned for head-first) | – | ~100 g | ~$16 |

Supports add a few grams.

**Print request settings**

| Field | Value |
|---|---|
| Dimensions | From the table above; the height (Z) is 61.3 mm for all |
| Quality | Slow (0.12 mm) for the engraved pattern and tight walls; Standard (0.2 mm) also works |
| Infill | **100% (solid)**. The simulation assumes solid plastic. The head-down file's air voids are designed into the model and stay hollow at 100% infill |
| Colour | Silver or grey if you'll chrome/paint it |
| Comments | "Print as oriented (back up) with tree/organic supports under the belly only. Do not scale. headdown_onepiece.stl contains two enclosed internal voids by design: please keep them (multiple shells are intentional)." |

**After printing**

1. Tie the line through the 2.2 mm hole running top to bottom through the head. There is no steel wire.
2. **Head-down only:** push about 10 g of lead into the 10 mm bore between the eyes (cut lead rod, or flattened split shot). Pack it in and seal both ends with epoxy, then stick the 12 mm 3D eyes over the holes.
3. Paint or chrome, then add a thin epoxy topcoat. This also seals the PLA so water can't reach the air voids.
4. Test in a tub before diving. The head-down version weighs only ~2–7 g in the water, so the paint matters. If it floats or sinks too slowly, add a little lead or epoxy in the bore. If it sinks too fast or levels out, use less lead.

**Simulated behaviour** (robustness check, 12 runs with varied water-force coefficients, PLA density 1.18–1.25, paint 3–9 g, lead ±1 g and toss attitude)

| | Head-down one-piece (35° / 10° / 10 g lead) | S-curve one-piece (solid PLA) |
|---|---|---|
| Head-first | 12 / 12 (median 57°) | 12 / 12 (median 61°) |
| Slow (≤ 0.45 m/s) | 11 / 12 (0.22–0.35 m/s) | 11 / 12 (0.19–0.22 m/s) |
| Light flutter | 8 / 12 (median ±5°) | 10 / 12 (median ±14°) |
| Spiral | 6 / 12, median one turn every ~8 s (uncertain: use the kick variants) | barely turns: wanders sideways instead |

Plastic alone (no lead, no air) can't make a slow head-down **spiral**: solid PLA weighs ~20 g in the water, so the bent bodies drop fast and spin. The S-curve in solid PLA does give a reliable slow, head-first, fluttering fall. The sealed air voids, which print inside the single piece, are what let the head-down design sink slowly.

## Two-piece versions (PETG, glued halves, tungsten ballast)

### Head-down slow spiral

The goal is a slow, head-first spiral with a light flutter, the way a dying baitfish sinks.

The default body has a gentle 30° body bend, a 20° tail kick, 12 g of tungsten in the head and sealed air in the rear. The robustness check ran it 12 times with varied water-force coefficients, putty amount (±2 g), putty position, topcoat (3–9 g) and toss attitude:

| | Range over the 12 runs (10th / median / 90th percentile) |
|---|---|
| Head-first | in all 12 runs: head down 51° / 54° / 61° |
| Slow | in all 12 runs: 0.26 / 0.28 / 0.32 m/s |
| Light flutter | in all 12 runs: rocking about ±5° / ±7° / ±20° |
| Spiral | one turn every 1.3 / 6 / 18 s – the uncertain part (see tuning) |

### Weighting and design strategy

1. **Put a small weight in the head (12 g), packed against the snout end of the 9 cc head cavity.** Fill the rest with epoxy. This tips the nose down.
2. **Make the rear body light, like a deflated swim bladder.** Two sealed air voids (~22 cc) in the back and belly halves behind the gut keep the weight in water tiny (~5 g) while moving the balance point far forward. A light, nose-heavy body sinks slowly and head-first.
3. **Bend the body 30°.** A straight head-down fish is streamlined and drops fast (~0.7–0.9 m/s in the model). The bend presents part of the flank to the water, which slows it to ~0.3 m/s and makes it rock.
4. **Kick the tail 20°.** The tail fin works like a rudder in the head-to-tail flow and turns the fall into a spiral.
5. **Leave the gut cavity as epoxy.** Tungsten in the gut makes the fish glide level instead of tipping head-down.

### Tuning kit (pool-test before diving)

How fast it spirals depends on how much lift the real tail fin makes, and no lab data pins that down. So three tail-kick versions are included:

| Tail kick | Use when the 20° version… |
|---|---|
| 10° (`wounded_kick10_*`) | spins faster than one turn every ~2 s |
| **20° (default)** | – |
| 30° (`wounded_kick30_*`) | barely turns |

Other adjustments:

- **Head charge:** 8–16 g. Less sinks slower and steeper; more sinks faster and flatter. Change it 1–2 g at a time.
- **Tail trim:** the PETG tail can be heat-bent a few degrees (hair dryer or heat gun on low) for fine adjustment.

### How the simulation works and how far to trust it

- **Model:** the viewer's sink test cuts the fish into slices along its length. Each slice gets the drag, lift, added-mass and rotational-damping model from falling-plate experiments ([Andersen, Pesavento & Wang 2005](https://dragonfly.tam.cornell.edu/publications/2005_JFM_Andersen_Pesavento_Wang_a.pdf)). The tail fin also gets lift when water flows from head to tail. All slice added masses combine into the full 6-DOF equations, so curved and kicked bodies get the correct turning moments.
- **Validation:** run on the paper's measured aluminium plates, the model reproduces the fluttering plate's drift and descent within ~12%, and the thick plate tumbles as measured. Plates near the flutter/tumble boundary are less reliable. Results are in `files/validation/`.
- **What to trust:** the type of fall and the sink speed are the most reliable outputs. The spiral rate is the least reliable, which is why the tuning kit exists.

## S-curve option

The same head-and-air weighting in an S-shaped body: a 95° front curve and a 120° rear curve the other way, nearly as deep as the U-curl but open. Footprint is 173 × 111 mm. It prints as back and belly halves like the others.

With 25 g of tungsten in the head, the calibrated model has it sink very slowly (~0.21 m/s) and steeply head-first (~65°), turning once every ~10 s within a ~5 cm circle. Its two opposing curves make it very stable, so it does not flutter: it is the steady option. Use the head-down design for flutter. Charges from 15 g (slowest, ~0.14 m/s) to 36 g (~0.26 m/s) are simulated in the viewer.

## All four designs

| | Head-down (default) | S-curve | U-curl | Straight |
|---|---|---|---|---|
| Shape | 30° body bend, 20° tail kick | Two opposing curves (95° / 120°) | Curled 230° | 250 × 61 mm flattened body |
| Halves | Back / belly | Back / belly | Back / belly | Left / right flank |
| Ballast | 12 g tungsten in head + sealed air | 25 g tungsten in head + sealed air | Tungsten in chamber C | Tungsten in chamber B |
| Simulated fall | Head-down (~52°), light flutter, spiral, ~0.3 m/s | Steep head-down (~65°), slow turn, no flutter, ~0.2 m/s | U-down, rocking ±25°, ~0.2 m/s | Head-first, rocking, fast (~0.9 m/s) |
| Pattern | Engraved lines, airbrush + wash | Engraved lines, airbrush + wash | Engraved lines, airbrush + wash | Waterslide decal over chrome |

## Sink simulation

The viewer's **Sink test** plays the calibrated strip-model simulation (see above) for every ballast setup of all four designs. The default head-down setup also shows its robustness-check result. The U-curl and straight bodies use the same model, but they were not re-tuned for the head-first target.

## Files

- `files/wounded_mackerel_BACK_half.stl`, `files/wounded_mackerel_BELLY_half.stl` – head-down design (20° tail kick)
- `files/wounded_kick10_mackerel_*`, `files/wounded_kick30_mackerel_*` – tail-kick tuning variants
- `files/scurve_mackerel_BACK_half.stl`, `files/scurve_mackerel_BELLY_half.stl` – S-curve
- `files/curled_mackerel_DORSAL_half.stl`, `files/curled_mackerel_VENTRAL_half.stl` – U-curl
- `files/mackerel_flasher_LEFT_half.stl`, `files/mackerel_flasher_RIGHT_half.stl` – straight
- `files/chub_mackerel_flasher_decals_and_build_sheet.pdf` – decals and build steps (straight version)
- `files/mackerel_sink_test_headdown.mp4`, `files/mackerel_sink_test_curl.mp4` – simulated sink videos
- `files/mackerel_flasher_source.zip` – parametric Python source, including the simulator

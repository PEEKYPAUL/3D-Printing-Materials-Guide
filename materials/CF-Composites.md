# Carbon Fibre & Glass Fibre Composite Filaments

> **Difficulty:** ⭐⭐⭐ Advanced | **Category:** Composite | **Key Requirement:** Hardened steel nozzle — mandatory for both CF and GF

---

## Overview

CF (Carbon Fibre) and GF (Glass Fibre) composite filaments are standard base polymers — PLA, PETG, Nylon, PC, PEEK — with **short-chopped reinforcement fibres** blended in at 10–30% by weight. The fibres dramatically change how the material behaves: increasing stiffness, improving dimensional stability, and giving a distinctive surface finish that hides layer lines.

These are not the same as continuous fibre systems (Markforged etc.) — the fibres are chopped short and randomly distributed. Parts are still printed layer-by-layer and still have anisotropic strength. What you gain is **significantly stiffer, more dimensionally stable parts** from the same base polymer.

> ⚠️ **Both CF and GF filaments are highly abrasive.** A standard brass nozzle will be destroyed within 200–500g of material. A hardened steel nozzle is mandatory before you start.

---

## CF vs GF — What's the Difference?

| Property | Carbon Fibre (CF) | Glass Fibre (GF) |
|---|---|---|
| **Stiffness increase** | Very high (+100–300% modulus) | High (+60–150% modulus) |
| **Tensile strength increase** | Moderate (+10–40%) | Moderate (+10–30%) |
| **Impact resistance** | Lower than base (more brittle) | Better than CF — closer to base polymer |
| **Weight** | Slightly lighter than base | Similar to base or slightly heavier |
| **Surface finish** | Matte, dark, hides layer lines well | Matte, often grey/white tint |
| **Abrasiveness** | High | High |
| **Cost** | Higher | Lower than CF — more affordable |
| **Electrical conductivity** | Slightly conductive (carbon) | Non-conductive |
| **Best use case** | Maximum stiffness, structural rigidity | Stiffness + impact resistance, lower cost |

**In short:** CF is the choice when you need maximum stiffness and a premium finish. GF is the better choice when you need a balance of stiffness and impact resistance at a lower cost.

---

## Strength Statistics by Material Variant

The tables below compare approximate mechanical properties of base filaments versus their CF and GF reinforced equivalents. Values are drawn from published manufacturer datasheets and represent printed parts — not moulded specimens.

> 📊 All values are **approximate** and vary between brands. Use these as a guide for material selection, not for engineering calculations. Always refer to the specific datasheet for your filament.

### Tensile Strength (MPa) — Resistance to pulling force

| Base Material | Standard | + CF | + GF | CF Gain | GF Gain |
|---|---|---|---|---|---|
| PLA | 50 MPa | 65 MPa | 55 MPa | +30% | +10% |
| PETG | 50 MPa | 60 MPa | 62 MPa | +20% | +24% |
| ABS | 42 MPa | 55 MPa | 52 MPa | +31% | +24% |
| Nylon PA12 | 48 MPa | 90 MPa | 85 MPa | +88% | +77% |
| Nylon PA6 | 55 MPa | 110 MPa | 100 MPa | +100% | +82% |
| PC | 65 MPa | 78 MPa | 72 MPa | +20% | +11% |
| PEEK | 100 MPa | 160 MPa | 140 MPa | +60% | +40% |

### Stiffness / Young's Modulus (GPa) — Resistance to bending and deflection

*This is where CF and GF make the biggest difference — parts flex and deform far less under load.*

| Base Material | Standard | + CF | + GF | CF Gain | GF Gain |
|---|---|---|---|---|---|
| PLA | 3.5 GPa | 7.0 GPa | 4.5 GPa | +100% | +29% |
| PETG | 2.1 GPa | 5.5 GPa | 3.5 GPa | +162% | +67% |
| ABS | 2.2 GPa | 5.0 GPa | 3.8 GPa | +127% | +73% |
| Nylon PA12 | 1.8 GPa | 8.0 GPa | 6.0 GPa | +344% | +233% |
| Nylon PA6 | 2.8 GPa | 10.0 GPa | 7.5 GPa | +257% | +168% |
| PC | 2.3 GPa | 6.0 GPa | 5.0 GPa | +161% | +117% |
| PEEK | 4.5 GPa | 15.0 GPa | 10.0 GPa | +233% | +122% |

### Heat Deflection Temperature (°C) — Temperature at which the part deforms under load

*Fibres raise the temperature at which parts lose their shape — especially significant for Nylon.*

| Base Material | Standard | + CF | + GF |
|---|---|---|---|
| PLA | 52°C | 60°C | 56°C |
| PETG | 72°C | 82°C | 79°C |
| ABS | 98°C | 110°C | 105°C |
| Nylon PA12 | 55°C | 130°C | 120°C |
| Nylon PA6 | 75°C | 185°C | 170°C |
| PC | 130°C | 145°C | 140°C |
| PEEK | 250°C | 280°C+ | 270°C+ |

### Key Takeaways from the Data

- **Stiffness is where fibres shine** — CF nearly doubles or triples the modulus of most base materials
- **Nylon gains the most from CF/GF** — PA-CF is the standout option for functional engineering parts, with stiffness gains of over 300%
- **GF gives better impact resistance than CF** — the right choice when parts might be dropped or subject to shock loads
- **Tensile strength gains are real but modest** — fibres alone won't make a poorly designed part strong
- **HDT improvement is significant** — CF/GF-Nylon can operate in environments where plain Nylon would creep and deform

---

## Common CF & GF Composite Families

| Material | Stiffness | Heat Resistance | Difficulty | Best For |
|---|---|---|---|---|
| PLA-CF | ⭐⭐⭐ High | ❌ Low (60°C HDT) | Easy | Rigid display parts, cosmetic panels, jigs |
| PETG-CF | ⭐⭐⭐ High | ⭐ Moderate (82°C) | Intermediate | Brackets, enclosures, functional parts |
| PETG-GF | ⭐⭐ Moderate | ⭐ Moderate (79°C) | Intermediate | Impact-resistant structural parts |
| ABS-CF | ⭐⭐⭐ High | ⭐ Moderate (110°C) | Intermediate | Automotive interior, enclosures |
| PA6-CF / PA12-CF | ⭐⭐⭐⭐ Very high | ⭐⭐ Good (130–185°C) | Advanced | **Best all-round functional CF choice** |
| PA6-GF / PA12-GF | ⭐⭐⭐ High | ⭐⭐ Good (120–170°C) | Advanced | Structural parts needing impact resistance |
| PC-CF | ⭐⭐⭐⭐ Very high | ⭐⭐ High (145°C) | Advanced | High-temp structural engineering |
| PEEK-CF | ⭐⭐⭐⭐⭐ Extreme | ⭐⭐⭐ Very high (280°C+) | Expert | Aerospace, motorsport, extreme environments |

---

## Nozzle Requirements — Mandatory

> ⚠️ **Never print CF or GF filaments with a standard brass nozzle.** Both are highly abrasive and will wear a 0.4mm brass nozzle to a rounded, oversize opening within 200–500g of filament, causing under-extrusion and inconsistent prints.

| Nozzle Type | Durability | Cost | Recommended? |
|---|---|---|---|
| Hardened steel | ⭐⭐⭐ Good | Low–moderate | ✅ Best everyday choice |
| Tungsten carbide | ⭐⭐⭐⭐⭐ Extreme | High | ✅ Long-term / heavy use |
| Ruby-tipped brass | ⭐⭐⭐⭐ Excellent | High | ✅ Premium option |
| Nickel-plated brass | ⭐ Minimal | Low | ⚠️ Short-term workaround only |
| Standard brass | ❌ None | — | ❌ Do not use |

**Nozzle size:** Use 0.4mm minimum — 0.6mm is often ideal for CF/GF. Smaller orifices are prone to partial clogs from fibre bundles.

---

## Settings Reference

Use the corresponding base material guide as your starting point, then apply these adjustments:

| Parameter | Adjustment | Reason |
|---|---|---|
| Nozzle Temp | +5–10°C above base | Fibres increase melt viscosity |
| Print Speed | -15–25% below base | CF/GF is less forgiving of speed |
| Retraction | Reduce slightly (0.5–1mm less) | Fibres can jam at the retraction point |
| Cooling | Match base material | No change needed |
| Flow Ratio | 1.02–1.05 | Fibres restrict flow slightly — tune up if under-extruding |
| Layer Height | 0.15–0.25mm | Avoid very thin layers |
| Wall Count | 4–6 perimeters | Fibres provide the most benefit aligned in walls |

---

## Tips & Tricks

### Getting the Most Stiffness
- **Fibres align with the print direction** — they are most effective running along wall perimeters.
- Increasing **wall count (4–6 perimeters)** gives far more benefit than increasing infill.
- Parts with high wall counts and moderate infill often outperform solid-infill standard filament parts.

### Surface Finish
- CF composites produce a **matte, technical surface finish** that naturally hides layer lines — popular for cosmetic panels and professional-looking enclosures.
- GF typically produces a lighter grey/cream tint depending on the base polymer.
- Neither sands or post-processes easily — plan your surface finish into the design.

### Moisture
- **CF/GF does not eliminate the base polymer's moisture sensitivity.**
- CF-Nylon is just as hygroscopic as standard Nylon — dry it at the same temperature and duration.
- CF-PLA and CF-PETG are less sensitive but still benefit from drying before long prints.

### Safety
- Both CF and GF generate **fine abrasive dust** during printing — a respiratory irritant.
- Print in an **enclosed printer** and consider a HEPA-filtered exhaust.
- Never sand CF or GF parts without a well-fitting dust mask.
- GF dust is a known irritant to skin, eyes, and lungs — handle with care.

### Design Considerations
- CF/GF composites are **stiffer but more brittle** than the base polymer — avoid sharp internal corners under load.
- They are **not ideal for impact resistance** — plain Nylon or PC will absorb shock loads far better.
- Excellent for: brackets, frames, levers, jigs, fixtures, structural ribs, stiff housings.

---

## When to Choose CF vs GF vs Standard

| Scenario | Best Choice |
|---|---|
| Maximum stiffness, lowest deflection | CF variant |
| Stiffness + some impact resistance | GF variant |
| Impact / shock resistance is the priority | Standard Nylon or PC |
| Cosmetic panel, professional look | PLA-CF or PETG-CF |
| High-temp functional engineering | PA6-CF or PA12-CF |
| Extreme performance (aerospace etc.) | PEEK-CF |
| Budget-conscious composite | GF variant |
| Electrical insulation required | GF variant (CF is slightly conductive) |

---

## Popular CF & GF Products

| Product | Type | Base | Notes |
|---|---|---|---|
| Bambu PA12-CF | CF | PA12 | Excellent AMS compatibility, well-tuned profiles |
| Polymaker PolyMide PA6-CF | CF | PA6 | High stiffness, widely available |
| Prusament PLA-CF | CF | PLA | Easy to print, great surface finish |
| 3DXTech CarbonX PA12-CF | CF | PA12 | High quality, US-made |
| 3DXTech CarbonX PEEK-CF | CF | PEEK | Aerospace-grade performance |
| Fiberlogy PETG CF15 | CF | PETG | 15% CF loading, good value |
| Polymaker PolyMide PA612-GF | GF | PA612 | Good stiffness and impact balance |
| 3DXTech GlassX PA12-GF | GF | PA12 | Non-conductive, cost-effective |

---

## Continuous Carbon Fibre (Different Technology)

**Markforged** and similar dedicated systems embed **continuous carbon fibre strands** into a Nylon matrix during printing — not chopped fibres. This is a fundamentally different process producing parts that can approach aluminium-level strength-to-weight ratios. These systems require dedicated printers, specialist software, and significantly higher investment. This guide covers chopped-CF and chopped-GF composites only.

---

*← [Back to README](../README.md)*

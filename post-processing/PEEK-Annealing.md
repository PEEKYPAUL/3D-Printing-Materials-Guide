# PEEK Annealing

> Annealing transforms a printed PEEK part from a strong, amorphous structure into a fully semi-crystalline component with dramatically improved heat resistance, stiffness, and long-term dimensional stability. Done correctly, it is one of the most impactful post-processing steps available for high-performance engineering parts.

---

## Why Anneal PEEK?

When PEEK is printed, it cools rapidly after deposition. This rapid cooling locks the polymer chains in a partially amorphous state — the part is strong, but it has not reached the full crystallinity that PEEK is capable of.

Annealing holds the part at a controlled elevated temperature for an extended period, giving the polymer chains time to reorganise into a semi-crystalline structure. The difference in performance is significant:

| Property | As-Printed (Amorphous) | After Annealing (Semi-Crystalline) |
|---|---|---|
| Heat Deflection Temp | ~140°C | **250°C+** |
| Tensile Strength | ~90 MPa | ~100–110 MPa |
| Young's Modulus | ~3.6 GPa | ~4.5 GPa |
| Long-term Creep Resistance | Moderate | Excellent |
| Chemical Resistance | Excellent | Outstanding |
| Dimensional Change | Baseline | ~0.1–0.5% (account for in design) |

> 💡 If your PEEK part will be exposed to temperatures above 100°C, operating under sustained load, or immersed in aggressive chemicals — annealing is not optional. It is the step that makes PEEK what it is.

---

## The Sand Burial Method

The biggest challenge with annealing PEEK is warping. As the part heats and the polymer chains relax, internal stresses from printing are released — and without external support, this can cause significant distortion, particularly on flat faces, thin walls, and long spans.

The solution is **sand burial** — embedding the part fully in fine quartz sand before annealing. The sand:
- Provides uniform, gentle pressure on all surfaces simultaneously
- Transfers heat evenly to the entire part without hotspots
- Prevents distortion as the polymer relaxes by holding geometry in place
- Allows controlled, even cooling when the oven is switched off

The sand used must be **refined quartz sand, 0.1mm grain size**. Coarser sand can leave surface impressions. Play sand and building sand contain impurities and inconsistent grain size — do not use them.

---

## What You Need

- Convection oven or laboratory furnace with accurate temperature control
- **Refined quartz sand — 0.1mm grain size** (sufficient to fully bury the part with margin on all sides)
- A metal container or baking tray with tall sides — deep enough to bury the part with at least 20–30mm of sand above it
- Digital thermometer or oven probe to verify actual chamber temperature
- Heat-resistant gloves

---

## Step-by-Step Process

### Step 1 — Prepare the Part

- Remove all support material fully before annealing — supports cannot be removed cleanly after crystallisation
- Clean the part of any loose debris or contamination
- If the part has critical mating faces or tolerances, measure it before annealing — expect 0.1–0.5% shrinkage, predominantly in the Z axis

---

### Step 2 — Prepare the Sand Bed

![Both annealed and unannealed PEEK parts positioned inside the oven before burial](../images/peek-annealing-01-parts-in-oven.jpg)

*Both the unannealed part (left) and a previously annealed reference part (right) shown inside the oven before the sand burial process begins. Note the colour difference — the annealed part has a slightly more opaque, crystalline appearance.*

Pour a base layer of quartz sand into your metal container — at least 30mm deep. Level it off. This forms the support bed the part will sit on.

---

### Step 3 — Bury the Part

![Creating a deep cavity in the quartz sand for the part](../images/peek-annealing-02-sand-cavity.jpg)

*A deep hole pressed into the quartz sand to seat the part. The cavity should conform closely to the part geometry with no unsupported overhangs — every surface that could distort must be supported by sand.*

Press a cavity into the sand that matches the part's geometry. Lower the part in carefully and ensure it is seated level. Then pour sand slowly over and around the part, working from the sides inward to avoid displacing it. Continue until the part is covered by at least 20–30mm of sand above its highest point.

---

### Step 4 — Compress and Level

![Part fully buried and sand compressed and levelled](../images/peek-annealing-03-sand-compressed.jpg)

*The part is fully buried and the sand has been gently compressed by hand to remove air pockets. A flat, level sand surface indicates even coverage. The container is now ready to go into the oven.*

Gently compress the sand by pressing down evenly with your palm — this removes air pockets and ensures the sand is in full contact with all part surfaces. Level the top surface. Do not over-compress — firm even contact is all that is needed.

---

### Step 5 — Anneal

Place the container into a **cold oven**. Do not place it into a pre-heated oven — a sudden thermal shock can cause immediate warping before the sand has a chance to provide support.

**Annealing cycle:**

| Stage | Temperature | Rate | Duration |
|---|---|---|---|
| Ramp up | Ambient → 200°C | ~2°C/min (slow ramp) | ~90 minutes |
| Hold | 200°C | Stable | **2–4 hours** |
| Ramp down | 200°C → ambient | Oven off — door closed | 4–8 hours minimum |

> ⚠️ **The hold duration matters.** 2 hours is the minimum for small, simple parts. For large, thick, or structurally complex parts — hold for 3–4 hours to ensure the core of the part reaches full crystallinity, not just the outer surfaces.

> ⚠️ **The slow ramp is critical.** Heating too fast creates a temperature differential between the part surface and core, which generates internal stress and risks cracking or warping even inside the sand. 2°C/min is a safe ramp rate.

---

### Step 6 — Cool Down — Do Not Rush This

The cooling phase is just as important as the annealing hold. Rapid cooling quenches the crystalline structure and can reintroduce internal stresses, partially reversing the annealing benefit and causing warping as the part contracts unevenly.

**Correct procedure:**
1. When the hold is complete, switch the oven off
2. **Leave the door fully closed** — do not open it
3. Allow the oven and sand mass to cool naturally to below 50°C before opening — this typically takes 4–8 hours depending on oven size and insulation
4. Once below 50°C, open the oven door slightly and allow to equilibrate to room temperature before removing the container
5. Unbury the part carefully from the sand

> 💡 The large thermal mass of the sand works in your favour during cooling — it acts as a buffer that slows the rate of heat loss and keeps the part cooling evenly on all sides simultaneously. This is why sand burial produces better results than annealing parts in open air or on a rack.

---

### Step 7 — Inspect

![Uncovering the part after the full annealing cycle](../images/peek-annealing-04-uncovering.jpg)

*The part being uncovered from the quartz sand after the annealing cycle and full cool-down. The sand brushes away cleanly from the surface. No distortion is visible — the geometry has been held true throughout.*

Brush the sand away and inspect the part. A successfully annealed PEEK part will often have a slightly more opaque, matte surface finish compared to the as-printed state — this is normal and is a visible indicator of crystallinity. The part may also feel slightly different in the hand — denser, more rigid.

Check critical dimensions if tolerances are important. Expect small changes (0.1–0.5%) — primarily Z-axis shrinkage. Design-in allowance if you need annealed parts to hit tight tolerances.

---

## Annealed vs Unannealed — Side by Side

![Close-up comparison of unannealed and annealed PEEK parts photographed in a light box](../images/peek-annealing-05-comparison-lightbox.jpg)

*Detailed side-by-side comparison of unannealed (left) and annealed (right) PEEK parts, photographed in a light box to reveal surface and structural differences. The annealed part shows a slightly more opaque finish and improved surface uniformity — the result of the polymer achieving its semi-crystalline state.*

---

## Common Problems

| Problem | Likely Cause | Fix |
|---|---|---|
| Part warped after annealing | Ramp too fast, sand not fully compacted, or cooling too rapid | Slow the ramp to 2°C/min, compress sand more thoroughly, ensure oven cools with door closed |
| Surface impressions from sand | Sand grain too coarse | Switch to 0.1mm refined quartz sand only |
| Part cracked during ramp | Thermal shock from placing in hot oven | Always start in a cold oven and ramp slowly |
| Part still soft above 140°C after annealing | Insufficient hold time or temperature too low | Extend hold to 3–4 hours at 200°C |
| Dimensional change too large | Normal annealing shrinkage | Design with 0.3–0.5% Z-axis allowance for annealed parts |
| Surface discolouration / yellowing | Oven temperature exceeded 220°C | Verify oven temperature with a probe — calibrate or adjust set point |

---

## Tips

- **Verify your oven temperature** — consumer ovens can run 10–20°C hotter than their dial setting. Use an independent probe to confirm the actual chamber temperature before committing a finished part to the cycle.
- **Use a metal container with tall sides** — a standard baking tray is too shallow. A deep metal loaf tin or steel container gives you room to bury the part with adequate sand coverage above.
- **Anneal before final machining** — if you plan to drill, tap, or machine the part, anneal first. Dimensional changes after machining are much harder to account for.
- **Do not anneal parts with metal inserts already installed** — differential thermal expansion between PEEK and the insert can crack the part or distort the insert bore. Install inserts after annealing.
- **Label your container** — if you have multiple annealing runs in progress, mark the container with what's inside. Sand looks the same whether there's a part in it or not.

---

*Back to [Post-Processing Guides](../README.md#-post-processing-guides) | [README](../README.md)*

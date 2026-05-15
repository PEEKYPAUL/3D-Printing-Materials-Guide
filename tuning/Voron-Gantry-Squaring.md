# Voron V2 Gantry Squaring

> **Applies to:** Voron 2.4 | **Difficulty:** ⭐⭐⭐ Intermediate | **Do this:** On initial build, after any gantry disassembly, or when first layer consistency is unexpectedly poor

---

## Why This Matters

The Voron 2.4 has four independently driven Z motors that run Quad Gantry Level (QGL) to bring the gantry into a flat plane before every print. What QGL cannot fix is a gantry that is fundamentally mis-squared — where the extrusions and joints aren't sitting in alignment with each other in the first place.

A mis-squared gantry causes:
- Inconsistent first layers that QGL can't fully compensate for
- Z belts rubbing against the gantry printed parts, causing wear and noise
- X-axis racking — the X extrusion is at a different angle at the front versus the back, which causes shifting and layer inconsistency

This process squares the gantry mechanically so that QGL is correcting small thermal variation rather than fighting a structural misalignment.

---

## Before You Start

- **Allow 20–30 minutes** for the squaring steps, plus 1.5–2 hours heat soak time at the end
- The printer needs to be on a **reasonably level surface** — if it's sitting on an uneven bench, the gantry can swing to one side when the Z joints are released
- Have a phone with a belt frequency app ready for Step 11 (e.g. Gates Carbon Drive app)
- Watch Nero3D's de-racking video before Step 10 — it covers the X-axis racking correction that pairs with this process

---

## Step 1 — Prevent Motor Timeout

The stepper motors need to stay energised throughout this process. Set the idle timeout to a very large value so Klipper doesn't disable them mid-procedure:

```gcode
SET_IDLE_TIMEOUT TIMEOUT=99999
```

---

## Step 2 — Home and Level

Run a full home and QGL to get the gantry into a known good starting position:

```gcode
G28
QUAD_GANTRY_LEVEL
```

---

## Step 3 — Park the Gantry at Centre

Move the gantry to the centre of the build volume — this gives you clear access to both the top and bottom of the gantry from all four sides. Do this from the Mainsail/Fluidd interface or with:

```gcode
G0 X175 Y175 Z175 F6000
```

Adjust the XY values to match your printer's build volume centre.

---

## Step 4 — Disable X and Y Motors

With the gantry at centre height, disable the X and Y steppers so the gantry can move freely in the horizontal plane. The Z motors stay energised:

```gcode
SET_STEPPER_ENABLE STEPPER=stepper_x ENABLE=0
SET_STEPPER_ENABLE STEPPER=stepper_y ENABLE=0
```

---

## Step 5 — Back Off A/B Belt Tension

Fully back off the A and B belt tensioners so there is no tension pulling on the gantry. The gantry should be free to shift in X and Y without resistance from the belts.

> ⚠️ If the idlers are fully backed off but tension remains, the belt ends in the X carriage may need to be temporarily released. Any remaining belt tension will fight the squaring process and prevent the gantry from settling naturally.

---

## Step 6 — Remove the Side Panels

Remove both side panels to give you unobstructed access to the Z joints and extrusion connections on both sides.

---

## Step 7 — Drop the Lower Z Joints

![Lower Z joint shown fully lowered away from the gantry extrusion](../images/gantry-squaring-01-z-joints-lowered.jpg)

Unscrew and drop all four lower Z joints completely away from the gantry. With the joints dropped, the gantry is now floating and supported only by the Z belts — free to self-align.

> ⚠️ Make sure the printer is on a level surface before doing this. A tilted printer will cause the gantry to drift to one side under its own weight.

---

## Step 8 — Loosen the Extrusion Connection Bolts

This is the step most people under-do. Every bolted connection between the gantry extrusions and their printed joints needs to be loosened enough that the parts can slide freely against each other. Too tight and the gantry can't self-align; too loose on the Z belt clamps and you'll drop a belt.

![Bolt locations on gantry extrusions — X/Y joints, A/B joints, and front idlers highlighted](../images/gantry-squaring-02-bolt-locations.jpg)

Loosen the following on **both sides**, both top and bottom bolts at each location:

- **X/Y joints** (rear corners) — fully loosen to allow free movement
- **A/B joints** (the belt-path joints) — loosen enough to slide, but **do not overdo the Z belt clamp bolts** — just enough to allow adjustment, not enough to release the belt
- **Front idlers** — loosen to allow free X movement, don't overdo it

> 💡 A good test: push each extrusion gently by hand. If you feel resistance or binding at any joint, that bolt needs to come out another half turn.

---

## Step 9 — Align the Gantry

![Z joint sliding freely in the channel — flush on both sides indicates correct alignment](../images/gantry-squaring-03-z-joint-flush.jpg)

With everything loose and the Z joints dropped, physically move the gantry extrusions into alignment. The target for each side is:

**The Z joint slides up and down in the side channel without touching the sides.**

Pick up each lower Z joint and raise it manually into the channel. It should glide smoothly without resistance. If it binds or hits the side of the channel, the extrusion above it is shifted — nudge the gantry left or right (rear extrusion) or forward or backward (side extrusions) until the joint drops in flush.

Do this for all four corners.

> ⚠️ **Watch your A/B joint rotation.** As you shift the extrusions, it's easy to accidentally rotate the A/B joints — twisting them slightly out of their correct plane. Check that both A/B joints are sitting flat and parallel with the belt path, not angled.

![Correct A/B joint orientation vs inadvertently rotated](../images/gantry-squaring-04-ab-joint-rotation.jpg)

*Left: correct A/B joint sitting flat in plane. Right: inadvertently rotated during adjustment — this will cause belt wear and tracking issues. Check this after every adjustment.*

---

## Step 10 — Retighten the Extrusion Bolts

Once all four Z joints slide freely and flush, tighten all the extrusion bolts back up — **except the X/Y joint bolts**, which stay loose for Step 12.

After tightening, re-check each Z joint. The act of tightening can shift things slightly — if a joint no longer slides freely, back the relevant bolt off a little and recheck before tightening again.

---

## Step 11 — Reinstall the Z Joints (Loosely)

Slide all four lower Z joints back up into position and fix them with M5 bolts — but only lightly. They should be secure enough not to fall, but the joint still needs to be able to articulate freely. They get fully tightened later in the process, while hot.

---

## Step 12 — De-rack the X Axis

With the X/Y joint bolts still loose, follow Nero3D's de-racking procedure to square the X extrusion in the Y axis. This corrects X-axis racking — where the X rail is at a different angle front-to-back.

**[Nero3D De-racking Video — watch before this step](https://www.youtube.com/watch?v=cOn6u9kXvy0)**

Once de-racking is complete, tighten the X/Y joint bolts fully.

---

## Step 13 — Re-tension the A/B Belts

With the gantry now squared and de-racked, tension the A and B belts back up. Target frequency is **110Hz measured over a 15cm span**.

Use a phone app (Gates Carbon Drive or similar) to measure belt frequency. Pluck the belt like a guitar string at the 15cm point and read the frequency shown by the app.

![Belt frequency measurement — phone app showing 110Hz target](../images/gantry-squaring-05-belt-tension.jpg)

Match both belts as closely as possible — uneven tension between A and B will cause CoreXY motion artefacts even with perfect gantry alignment.

> 💡 Refer to the Voron documentation or community guides for the correct tension procedure for your specific belt tensioner design — the method varies slightly between versions.

---

## Step 14 — Heat Soak

Reinstall the side panels and heat soak the printer fully before continuing:

- Set bed to **110°C**
- Set hotend to **150°C**
- Run the enclosure for a minimum of **1.5–2 hours**

This brings the frame, gantry, and belts to thermal equilibrium. The final tightening step must be done hot — doing it cold means everything shifts when it heats up, undoing the alignment.

---

## Step 15 — Run QGL Multiple Times

Once fully heat-soaked, run QGL repeatedly to let the gantry settle:

```gcode
QUAD_GANTRY_LEVEL
QUAD_GANTRY_LEVEL
QUAD_GANTRY_LEVEL
```

Run it 3–5 times. The values should converge and the corrections should get progressively smaller with each run. If you're seeing retry errors or the values aren't converging, the Z joints may be slightly too loose — snug them up a fraction and try again.

---

## Step 16 — Final Z Joint Tightening (Do This While Hot)

With the printer fully at temperature and QGL settled, fully tighten all four lower Z joint M5 bolts.

This step does two things:

1. **Locks in the QGL correction at thermal equilibrium** — the gantry is in its fully-expanded hot state when the joints are fixed, so cold-to-hot expansion doesn't shift things as much. First layer consistency across the build plate improves noticeably.

2. **Stiffens the gantry** — loose Z joints allow the gantry to rock slightly during fast direction changes, which shows up as ringing and layer consistency issues. Tight joints at the correct position eliminate this.

> ⚠️ **Do not skip the heat soak before this step.** Tightening cold means the bolts are pulling the joints into a position that shifts once the printer warms up. The whole benefit of this step depends on the printer being at print temperature when you tighten.

---

## Step 17 — Reset and Verify

Reset the idle timeout back to normal:

```gcode
RESTART
```

Run one final QGL and check the reported correction values. After a properly squared gantry and correctly tightened Z joints, QGL corrections should be small and consistent — typically under 0.5mm across all four corners on a well-built machine.

---

## Do I Need to Redo This?

| Situation | Redo? |
|---|---|
| Initial build | ✅ Yes — always do this before first print |
| After replacing Z belts | ✅ Yes |
| After frame disassembly or significant hardware changes | ✅ Yes |
| QGL corrections are suddenly large or inconsistent | ✅ Yes |
| Z belt rubbing noise appeared | ✅ Yes |
| After moving the printer | ⚠️ Check — re-run QGL first and see if corrections are still reasonable |
| Routine maintenance | ❌ Not needed |

---

*Back to [Tuning Guides](../README.md#-tuning-guides) | [README](../README.md)*

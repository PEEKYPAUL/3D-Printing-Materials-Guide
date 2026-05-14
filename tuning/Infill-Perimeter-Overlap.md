# Infill / Perimeter Overlap

> **Difficulty:** ⭐⭐ Beginner | **Applies to:** PrusaSlicer · SuperSlicer · Orca Slicer | **Do this after:** Flow rate and pressure advance are dialled

---

## What Is This Fixing?

After tuning flow ratio and pressure advance, you may notice small gaps — pinholes — where the top infill meets the inner perimeter walls. The infill lines are landing just short of making full contact with the perimeter, leaving a tiny void at the junction.

![Pinholes at infill-perimeter junction before and after overlap adjustment](../images/infill-overlap-01-pinholes.jpg)

*Left: pinholes visible at the border between infill and inner perimeter wall. Right: adjusted overlap value closes the gap. These holes are not always visible from above — they show most clearly on translucent or single-colour top surfaces.*

This is a minor fine-tuning step — it doesn't indicate that your flow or pressure advance settings are wrong. It's just the slicer's default overlap value not quite matching your specific setup.

---

## The Preferred Fix — Disconnected Top Infill

Before reaching for the overlap slider, try this first: set your **top infill type to "not connected"** (SuperSlicer) or **"not connected to perimeters"** (Orca Slicer).

This separates the top surface infill from the perimeters so they're generated independently. The pinholes disappear because the junction geometry changes — and as a bonus, you often get a better top surface quality overall since the infill lines aren't being constrained by their attachment points.

**In Orca Slicer:**
Print Settings → Top solid infill → **Infill combination** → set to Not connected

**In SuperSlicer:**
Print Settings → Infill → **Top infill** → Not connected

Try this before adjusting overlap values. Many users find it solves the problem entirely with no further tweaking.

---

## Adjusting Overlap (If Needed)

If disconnected top infill isn't available or doesn't fully solve the problem, adjust the overlap setting directly:

| Slicer | Setting Name | Location |
|---|---|---|
| Orca Slicer | Infill/wall overlap | Print Settings → Quality |
| PrusaSlicer | Infill/perimeters overlap | Print Settings → Advanced |
| SuperSlicer | Infill/perimeters encroachment | Print Settings → Infill |

**Starting point:** Most slicers default to 25%. Try increasing to **35–45%** and print a single-wall calibration square with solid top infill to see the result.

![Infill overlap comparison at 25%, 35%, and 45%](../images/infill-overlap-02-comparison.jpg)

*Overlap at 25% (left), 35% (centre), 45% (right). The gap closes progressively. Setting too high causes the infill to visibly push into the perimeter and create a raised ridge.*

> ⚠️ **Don't over-correct.** Too much overlap pushes filament into the perimeter wall, causing a visible raised line at the junction and potential over-extrusion along the inner wall. Aim for the lowest value that closes the pinholes.

---

## When This Is Not the Problem

Pinholes and gaps at the infill-perimeter boundary can also be caused by:

| Cause | How to Tell | Fix |
|---|---|---|
| Under-extrusion (flow too low) | Gaps visible throughout the top surface, not just at edges | Re-run flow rate calibration |
| Pressure advance too high | Gaps at the start of infill lines, not at perimeter junctions specifically | Reduce PA value |
| Perimeter width narrower than infill width | Consistent gap on one side only | Check line width settings — perimeter and infill should use matching widths |

Overlap adjustment is specifically for the junction gap that appears **only where infill meets the inner perimeter**, after flow and pressure advance are already correct.

---

*Back to [Tuning Guides](../README.md#-tuning-guides) | [README](../README.md)*

# Contributing to the 3D Printing Ultimate Guide

Thank you for taking the time to contribute. This guide is built on real-world printing experience and community knowledge — corrections, additions, and improvements from people actively printing are what keep it accurate and useful.

---

## What We Welcome

- **Corrections** — factual errors, outdated settings, wrong temperature ranges, broken links
- **Improvements** — clearer explanations, better tips, additional context
- **New material guides** — following the existing format in `/materials/`
- **New tuning or troubleshooting guides** — following the structure in `/tuning/` or `/troubleshooting/`
- **Hardware additions** — toolheads, probes, extruders with verified compatibility info
- **Typos and formatting fixes**

## What We Do Not Accept

- Settings or recommendations you have not personally tested
- Brand or product promotion without objective technical basis
- Guides copy-pasted or closely adapted from other sources without attribution
- Content that contradicts established, sourced technical data without evidence

---

## How to Contribute

### Reporting an Error

If you spot incorrect information — wrong temperature, outdated tool recommendation, broken link — please open an issue using the **Incorrect or Outdated Information** template. Include:

- Which file and section the error is in
- What the current content says
- What the correct information should be
- Source or evidence if applicable (link to manufacturer spec, research paper, etc.)

### Suggesting New Content

Open an issue using the **Content Suggestion** template before writing anything. This avoids duplicated effort and allows discussion of scope and format before a pull request is opened.

### Submitting a Pull Request

1. **Fork** the repository
2. **Create a branch** from `main` — name it descriptively (e.g. `fix-petg-temp-range` or `add-pa12-nylon-guide`)
3. **Make your changes** — follow the formatting and structure of existing files
4. **Test your links** — ensure any internal links point to real files
5. **Open a pull request** using the provided template — fill in all sections

---

## Style Guidelines

### Markdown Formatting

- Use `##` for main sections, `###` for subsections
- Use tables for settings references and comparisons — follow the existing table style
- Use `> 💡` for tips and `> ⚠️` for warnings — keep these concise
- Code blocks (` ``` `) for all G-code, config snippets, and terminal commands
- Keep line length reasonable — one sentence per line in prose sections makes diffs cleaner

### Content Standards

- Write for someone who knows what they're doing but hasn't used this specific material or technique before — not a complete beginner, but not an expert either
- Be specific with numbers: temperatures, speeds, percentages, layer heights
- If a recommendation is experience-based rather than sourced, that's fine — label it clearly (e.g. "In practice..." or "From experience...")
- If you cite research or manufacturer data, link to it

### File Naming

- Use `Title-Case-With-Hyphens.md` — e.g. `PA12-Carbon-Fibre.md`
- Images go in `/images/` — name them descriptively: `peek-annealing-01-sand-burial.jpg`
- New folders should match the existing structure: `materials/`, `tuning/`, `troubleshooting/`, `post-processing/`, `hardware/`, `klipper/`

---

## Adding a New Material Guide

Copy the structure from an existing material file (e.g. `materials/PETG.md` for standard materials, `materials/PEEK.md` for high-temp). Every material guide should include:

- Difficulty rating and category in the front matter callout
- Overview section
- Settings reference table (nozzle, bed, chamber, speed, cooling, flow ratio, nozzle type)
- Hardware requirements table
- Bed surfaces and adhesion
- Material properties table
- Tips and tricks
- Common problems table
- Recommended brands (with links)
- Back link to README

Once written, add the material to the README in:
1. The materials table of contents
2. The Temperature Quick Reference bar chart
3. The Flow Rate & Fan Speed quick reference table

---

## Licence

By submitting a contribution, you agree that your contribution will be licensed under the same **Creative Commons Attribution 4.0 International (CC BY 4.0)** licence as the rest of this repository.

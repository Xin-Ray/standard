# Claude Slides Generation Guide

This file is an **execution contract** for AI assistants (including Claude Code) working on academic slide decks. It is a project instruction file, not a Figma requirement.

## Source of truth (read in order)

1. [Slides standard](README.md): narrative and presentation quality rules.
2. [Design tokens](design-tokens.json): colors, typography, sizing, semantic chart colors, motion defaults.
3. [Slide patterns](slide-patterns.json): repeatable layouts and reveal steps.
4. [Paper standard](../papers/README.md), when the source material is a scientific paper.

## Required workflow

1. Extract scientific context: audience, talk duration, research question, contributions, experiments, caveats. Do not invent results, citations, sample counts, significance, or images.
2. Produce a slide-by-slide **outline** with `title`, `singleMessage`, `patternId`, `visual`, `evidence`, `revealSteps`, and `speakerNotes`. A result slide must point to the supplied evidence.
3. Choose a `patternId` from `slide-patterns.json`. Apply the exact design-token values and semantic meanings consistently across all slides. Deviations should be explicitly documented.
4. Build the deck via a programmable PPTX or other supported export workflow. Map JSON values into the generator's native styles. Token JSON itself cannot create PPTX files.
5. Prefer editable shapes/charts to flattened screenshots. Add visual sources/credits as appropriate. Charts must show axis names, units, sample sizes and uncertainty where applicable.
6. Implement progressive disclosure only if the chosen renderer/exporter actually supports it. Otherwise, create progressive **duplicate slides** per logical step or clearly indicate that native click animations need manual work. Never assert that a fade animation exists without verifying the output.
7. Export PPTX and, when requested, PDF. Inspect rendered slides for overflow, broken fonts, legibility, content clipping, visual consistency, and research accuracy.
8. Deliver editable output and note any constraints or skipped animation requirements.

## Non-negotiable visual rules

- Use 16:9, light canvas and semantic colors from the tokens unless the user explicitly overrides them.
- One core message per slide; use assertion-style titles.
- Prioritize documentary/context images in the opening when they clarify the research setting; avoid decorative images and protect patient identity.
- Keep font hierarchy and margins stable across all slides.
- Method blue, baseline gray, component teal, highlight amber. Use text/legend in addition to color.
- Prefer a single dominant visual; keep charts faithful and uncertainty visible.
- Click-to-reveal is recommended, not mandatory when it would impair usability or accessibility.
- Keep content understandable in a static PDF.

## Acceptance checklist

- [ ] Opening frames make the research scenario understandable to a non-specialist.
- [ ] Titles alone tell a coherent scientific story.
- [ ] Every slide follows a declared pattern and uses token values.
- [ ] Each major claim is supported by a figure/table or clearly marked as preliminary.
- [ ] Baselines and outcome metrics are transparent; no unsupported biomedical or causal interpretation.
- [ ] Reveal steps match speaking order and survive PDF export.
- [ ] No overcrowding, overflow, microscopic legends, unexpected colors or fonts.
- [ ] Limitations, sources and design deviations are explicitly captured.

## Claude prompt example

> Read `standards/slides/CLAUDE.md`, `standards/slides/README.md`, `standards/slides/design-tokens.json` and `standards/slides/slide-patterns.json`. Turn the attached research paper into a 10-minute academic PPTX. First outline the slide narrative, then generate a deck using the design tokens and patterns. Reveal complex diagrams stepwise where technically possible and ensure the PDF fallback is readable. Do not fabricate metrics, statistical significance or citations. Verify output visually.

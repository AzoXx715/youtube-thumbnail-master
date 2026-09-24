# youtube-thumbnail-master

An autonomous, model-agnostic YouTube Thumbnail Master Skill.

## Goal

The intended user experience is deliberately simple:

> Give the AI a YouTube URL or a file. The Skill handles the rest.

The Skill is designed to infer the task from the supplied source and run the complete workflow: ingest the source, understand the video, audit current packaging, research comparable thumbnails when possible, generate multiple concepts, select a strategic direction, produce an exact thumbnail specification, generate or edit the image when supported, run mobile and technical QA, create controlled variants, and define a testing plan.

## Repository structure

- `skill.md` — core behavior, autonomous intake and decision rules.
- `workflows/create-thumbnail.md` — create a thumbnail from a video/source brief.
- `workflows/analyze-thumbnail.md` — audit an existing thumbnail.
- `workflows/optimize-thumbnail.md` — diagnose weaknesses and create controlled variants.
- `workflows/audience-thumbnail.md` — audience-specific packaging.
- `workflows/competitor-analysis.md` — competitor research and hypothesis generation.
- `workflows/prepublish-audit.md` — final release gate.
- `references/` — specialized knowledge modules covering hierarchy, mobile, branding, competition, AI workflows, audience, faces/gaze, typography, analytics, trends, source-frame editing, and legal/trust.

## Zero-friction mode

A user should not need to know which workflow to invoke.

### URL

If given a YouTube URL, the AI should inspect available metadata, title, channel, current thumbnail, description, transcript/captions when accessible, format, topic clues and relevant competitive context. It should then complete the thumbnail workflow.

### File

If given an image, audit and optimize it. If given a video, inspect representative frames when supported and build from the strongest truthful visual evidence. If given a script, transcript or document, extract the strongest visual opportunities and create the thumbnail strategy.

### Multiple inputs

Combine them. Prefer direct evidence over assumptions. Label uncertain conclusions as inference or hypothesis.

## Core principle

Do not optimize for beauty alone.

Optimize the whole chain:

**impression → attention → comprehension → curiosity → click → expectation → viewer satisfaction**

A thumbnail is a visual hypothesis that should be designed intentionally and validated with real-world data.

## Deployment

For AI systems with persistent instructions, use `skill.md` as the behavioral/system layer and upload the most relevant files from `references/` and `workflows/` as knowledge/context.

For systems with limited file slots, prioritize:
1. `skill.md`
2. `references/testing-and-diagnostics.md`
3. `references/visual-hierarchy.md`
4. `references/mobile-optimization.md`
5. the workflow matching the task

When possible, enable web access for URL/competitor research and image generation/editing for final production.

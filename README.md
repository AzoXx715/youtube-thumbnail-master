# youtube-thumbnail-master

An autonomous, model-agnostic YouTube Thumbnail Master Skill.

## The goal

The intended user experience is deliberately simple:

> Give the AI a YouTube URL or a file. The Skill handles the rest.

The system can ingest a video URL, thumbnail image, video file, script, title, or a combination; extract the useful evidence; understand the video's promise and audience; audit existing packaging; research comparable thumbnails when tools permit; generate multiple concepts; select a strategic direction; produce an image-generation/editing specification; run mobile and technical QA; create controlled variants; and define a measurement plan.

## Architecture

- `skill.md` — core behavior and decision rules.
- `workflows/` — detailed task procedures.
- `references/` — specialized knowledge modules.
- `portable/` — compact bundles for AI products that cannot ingest the whole repository.
- `adapters/` — setup instructions for ChatGPT, Claude, Grok and similar systems.
- `MASTER_PROMPT.md` — single-file universal prompt for systems that accept only one instruction/file.

## Zero-friction mode

When an AI receives only a URL or file, it should not ask the user to choose between analysis, optimization and creation unless the input is genuinely ambiguous. It should infer the most useful complete workflow.

### URL → complete workflow

1. Inspect URL and metadata.
2. Extract title, channel, description, transcript when available, current thumbnail and visual context.
3. Understand topic, audience, promise, emotional angle and curiosity gap.
4. Audit the existing thumbnail when available.
5. Research comparable recent thumbnails when web access is available.
6. Generate 5–8 materially different concepts.
7. Select the strongest strategic direction.
8. Produce or edit the thumbnail when the AI has image capabilities.
9. Run mobile-first and technical QA.
10. Create 2–3 controlled variants.
11. Return the final result and a testing plan.

### File → complete workflow

The same pipeline applies to images, videos, scripts and documents, using the strongest available evidence and clearly marking anything that is inferred.

## Portable deployment

For ChatGPT, put `skill.md` or the compact master instructions in Instructions and use the portable knowledge bundles as Knowledge. OpenAI's current guidance separates behavioral instructions from reference knowledge. urlOpenAI GPT configuration guidancehttps://help.openai.com/fr-fr/articles/8554397

For Claude, create a Project, put the master instructions in Project Instructions and the knowledge bundles in Project Knowledge. Claude documents this separation and supports expanded project knowledge with RAG on eligible paid plans. urlClaude Projects documentationhttps://support.claude.com/fr/articles/9519177-comment-creer-et-gerer-des-projets

## Core principle

Do not optimize for beauty alone.

Optimize the whole chain:

**impression → attention → comprehension → curiosity → click → expectation → viewer satisfaction**

A thumbnail is a visual hypothesis that should be designed intentionally and validated with real-world data.

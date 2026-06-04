# Samartha Astro-AI 2.0 Project Handover

## Purpose

This document is the handover summary for continuing the Samartha Astro-AI 2.0 work in a new chat window. The current project state is a spec-first architecture in which core behavior is defined by markdown control files, with implementation intended to happen in VS Code using Continue Dev and Qwen 2.5. [cite:58][cite:61]

## Current status

The main documentation scaffold has been created and organized, including the calculation architecture, system rules, gochara master logic, gochara test cases, and gochara output template files. The visible project structure also includes canonical schema, formula registry, cautions, module boundaries, questionnaire pipeline, runtime fallbacks, and canonical content JSON. [cite:58][cite:61]

The gochara documentation layer is considered structurally complete for now. `GOCHARA_ENGINE_MASTER.md` is the authoritative logic file, while `GOCHARA_TEST_CASES.md` defines validation structure and `GOCHARA_OUTPUT_TEMPLATES.md` defines rendering expectations. [cite:58][cite:61]

## Core operating model

The project is being run as a spec-driven system, not as a freeform coding exercise. The architecture file defines formulas, modular calculation flow, timeline logic, micro-pada gochara behavior, and output sequencing, while the system rules file defines global restrictions that must be enforced during every code-generation and execution loop. [cite:58][cite:61]

The intended implementation workflow is:
- Perplexity prepares prompts, task framing, and execution guidance.
- Qwen 2.5 in VS Code/Continue Dev generates or edits code.
- The user reviews, pastes, applies, tests, and commits the resulting files. [cite:58][cite:61]

## Files already discussed as important

The following files are central to continuation:

| File | Role |
|---|---|
| `CALCULATION_ENGINE_ARCH_V2.md` | Master calculation architecture, formulas, modular engine structure, gochara logic anchor. [cite:58] |
| `SYSTEM_RULES_CORE.md` | Global runtime rules, DD.MM.YYYY formatting, dynamic input rules, output suppression, print/PWA restrictions. [cite:61] |
| `GOCHARA_ENGINE_MASTER.md` | Authoritative gochara logic source discussed as already created and filled. [cite:58] |
| `GOCHARA_TEST_CASES.md` | Validation and verification structure for gochara engine behavior. [cite:58] |
| `GOCHARA_OUTPUT_TEMPLATES.md` | PDF/PWA/UI output structure for gochara-related rendering. [cite:61] |
| `raju_canonical_content.json` | Large canonical content file already present in the project folder. [cite:58] |

## Non-negotiable rules to preserve

The computational layer must accept dynamic user profile input and must not hardcode native identity values into downstream calculation logic. The rules file explicitly states that fixed testing profiles are only for verification and must not become baked into production calculations. [cite:61]

All final user-facing dates must be formatted as `DD.MM.YYYY`, and raw machine date strings like `YYYY-MM-DD` must not appear in final UI or report output. The rules file also requires JSON-ready structured outputs for decoupled engine compatibility and future PWA use. [cite:61]

Certain content blocks are explicitly suppressed and must not be reintroduced in compiled report output: Avakahada Chakra, Ghata Chakra, Panchadha Maitri Chakra, Jaimini Karakas, and Jaimini Arudhas. [cite:61]

## Gochara implementation direction

The agreed next implementation direction after document completion was to begin actual engine coding, starting with a focused Python file rather than trying to build the whole system in one pass. The safest initial sequence is to implement birth-profile ingestion, natal Moon calculation, and Saturn transit computation first, then validate those pieces before moving into belt mapping, zone logic, Elinati Shani cycle scanning, dasha overlap, and full gochara output. [cite:58][cite:61]

The gochara-related execution order discussed is:
1. Birth profile ingestion.
2. Natal Moon calculator.
3. Saturn transit fetch/calculation.
4. 27-pada Moon-centric belt mapping.
5. Zone detection.
6. Zone score calculation.
7. Elinati Shani cycle builder.
8. MD/AD/PD overlap mapping.
9. Present full gochara output.
10. JSON output builder. [cite:58][cite:61]

## Prompting precautions for VS Code and Qwen 2.5

Prompts sent to Qwen 2.5 should stay narrow and modular. One prompt should request one function, one file section, or one clearly bounded edit, because the architecture is modular and the rules file requires strict compliance across all generated code. [cite:58][cite:61]

Large mixed prompts should be avoided. Instead of asking for multiple engine layers in one request, each prompt should anchor to the exact source file and section it must follow, and it should specify the required output shape, such as function signature, class name, JSON keys, or test block. [cite:58][cite:61]

A safe prompt pattern is:
- Context file.
- Section name.
- Applicable system rules.
- One task only.
- Expected input/output.
- No extra assumptions. [cite:58][cite:61]

## Continue Dev working style

Continue Dev in VS Code should be used as a controlled executor, not as an autonomous architect. The best pattern is to attach the relevant file context such as `@CALCULATION_ENGINE_ARCH_V2.md` and `@SYSTEM_RULES_CORE.md`, then ask Qwen for one tightly scoped generation or edit request. [cite:58][cite:61]

A practical loop for every coding step is:
1. Prepare prompt in Perplexity.
2. Paste into Continue Dev with relevant `@file` attachments.
3. Generate or edit one file/function only.
4. Review manually.
5. Run one test immediately.
6. Fix only the failed part.
7. Commit once stable. [cite:58][cite:61]

## File creation guidance

Qwen 2.5 can generate the contents of Python, HTML, JSON, and Markdown files, but file naming and project structure should be intentionally controlled by the user instead of letting the model freely invent folders and filenames. For this project, a safer pattern is to pre-create the target file or explicitly state the target path before asking Qwen to generate content into it. [cite:58][cite:61]

Recommended style:
- User decides file name and folder.
- Perplexity drafts the exact prompt.
- Qwen writes only the requested content.
- The result is tested before moving to the next module. [cite:58][cite:61]

## Suggested first coding targets in the new chat

The new chat should begin with one of these narrowly scoped implementation tasks:
- Create `gochara_engine.py` skeleton with imports, profile object, and placeholder methods.
- Implement only natal Moon calculation from birth data.
- Implement only Saturn current transit resolver.
- Build one minimal JSON output contract for the first completed function. [cite:58][cite:61]

The best first executable milestone is: input native profile in, compute natal Moon details out, using dynamic input and compliant date formatting. [cite:58][cite:61]

## Handover note for new chat

<<<<<<< HEAD
In the new chat window, the GitHub repo or file bundle can be provided as the fresh source of truth. This handover document is meant to re-establish the working model quickly so the next session can start directly from implementation rather than re-discussing structure. [cite:58][cite:61]
=======
In the new chat window, the GitHub repo or file bundle can be provided as the fresh source of truth. This handover document is meant to re-establish the working model quickly so the next session can start directly from implementation rather than re-discussing structure. [cite:58][cite:61]
>>>>>>> 0b0fa04 (initial commit)

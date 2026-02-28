# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

This repository is a structured prompt framework for generating intelligence briefings from Australian Senate committee hearing transcripts. It is designed for DCCEEW (Department of Climate Change, Energy, the Environment and Water) SES staff covering the Environment Protection Reform Bill 2025 inquiry cycle.

This is a document/prompt engineering project — there are no build tools, tests, or runnable code.

## Key files

- `prompt.md` — The operational prompt. Copy from "Role and context" through "Tone and quality standards", fill bracketed fields, append a Hansard/transcript, and submit to Claude. This is the primary deliverable.
- `DCCEEW_Senate_Briefing_UserGuide.md` — Design rationale for the five-layer intelligence model and output structure. Read this to understand *why* the prompt is structured the way it is.
- `DCCEEW_Briefing_OutputTemplate.docx` — Word template for the final briefing output format.
- `sources/` — Hansard PDFs and other source transcripts used as inputs.

## Architecture

### Five-layer intelligence model

Every section in Part B of a briefing applies five sequential layers, each answering a distinct question. **Analytical separation between layers is the core design principle** — factual, policy, and political analysis must never bleed across layers.

| Layer | Purpose | Key constraint |
|-------|---------|---------------|
| L1 – The Record | Factual account of what happened | No interpretation; cross-reference Hansard pages |
| L2 – Legislative & Policy Signal | Map testimony to bill provisions | Must stay free of political framing |
| L3 – Political Intelligence | Senator intent, dynamics, signals | Must stay free of policy assessment |
| L4 – Risk & Exposure | Action items, commitments on notice, official exposure | Direct and unsparing; log commitments with senator/question/witness/due date |
| L5 – Forward Look | Predictive assessment of trajectory | Genuinely predictive, not hedged |

### Output structure

The briefing has three parts:
- **Part A** – Executive briefing (standalone for time-poor readers): hearing significance, priority flags, political temperature, forward look
- **Part B** – Section briefings grouped flexibly (by bill / witness bloc / theme / hybrid) with fixed five-layer anatomy per section. Top-level numbering is continuous across all sections.
- **Part C** – Quick reference tables: commitments on notice, key quotes, forward action items

### Conventions when editing the prompt

- Bracketed fields `[like this]` are user-fill placeholders — preserve them.
- `///slashed paragraphs///` are instruction placeholders that guide Claude's output — they are not content and should not appear in the final briefing.
- `[TRANSCRIPT QUALITY – VERIFY]` flags are an active quality control mechanism for auto-generated transcripts, not disclaimers.
- Use en-dashes with spaces ( – ), never em-dashes (—).
- Follow the Australian Government Style Manual for formatting decisions.

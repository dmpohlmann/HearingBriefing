# HearingBriefing – Claude Code project instructions

This file tells Claude Code how to operate within this repository. Read it in full before taking any action.

---

## What this project does

This repository contains the tools, templates and prompt for generating **senate committee hearing intelligence briefings** for Senior Executive Service staff at the Department of Climate Change, Energy, the Environment and Water (DCCEEW).

The system takes a Hansard transcript or auto-generated transcript as input and produces a structured intelligence briefing populated into a branded DOCX output template.

The intended audience is SES Band 1 and above. The product must meet the standards of a trusted senior colleague's analysis – not a transcription or summary service.

---

## Repository structure

```
HearingBriefing/
├── sources/                          # Input transcripts (Hansard or auto-generated)
├── .claude/                          # Claude Code configuration
├── .git/
├── CLAUDE.md                         # This file – Claude Code reads this first
├── README.md                         # Human-facing project overview
├── prompt.md                         # The operational briefing prompt
├── DCCEEW_Briefing_OutputTemplate.docx  # DOCX template to populate
├── DCCEEW_Senate_Briefing_UserGuide.md # Design rationale and usage guidance
└── [output files]                    # Completed briefings – see naming convention below
```

### Output file naming convention

```
[COMMITTEE]_HIB_[NNN]_[YYYYMMDD].docx
```

- `[COMMITTEE]` – committee acronym, e.g. `ECLC` for Environment and Communications Legislation Committee
- `HIB` – Hearing Intelligence Briefing (fixed)
- `[NNN]` – zero-padded sequence number, e.g. `001`, `002`
- `[YYYYMMDD]` – hearing date, not production date

Example: `ECLC_HIB_002_20251114.docx`

---

## How to generate a briefing

### Inputs required

1. A transcript file in `sources/` – Hansard (preferred) or auto-generated
2. The operational prompt from `prompt.md`
3. The output template `DCCEEW_Briefing_OutputTemplate.docx`

### Process

1. Read `prompt.md` in full before doing anything else
2. Read the transcript from `sources/`
3. Apply the five-layer analytical framework to produce the briefing content (see below)
4. Populate `DCCEEW_Briefing_OutputTemplate.docx` with the output – do not respond in chat
5. Save the completed briefing using the naming convention above

### Critical: populate the DOCX directly

Do not produce the briefing as a chat response. Populate the output template DOCX, preserving:
- All existing styles and heading hierarchy
- Table structures (cover metadata table, section metadata tables, appendix tables)
- Header and footer content – update `[Insert inquiry name]` and `[Insert hearing date]` fields
- Classification markings ("OFFICIAL Sensitive")
- The AI disclosure table on the cover page

When writing list content, use the correct L1/L2/L3: Dot points styles (see DOCX template styles section below).

Section metadata uses a two-row table (Hansard pages / Timestamps, Witnesses) – not italic text.

Replace all `[bracketed placeholder fields]` with real content. Replace all `///slashed instruction blocks///` with actual content in the appropriate L1/L2/L3 styles. Remove any empty rows from Part C tables before saving.

---

## The five-layer analytical framework

Every section in Part B must apply all five layers in order. This is the core analytical structure – do not collapse or skip layers.

| Layer | Name | Core question | Key constraint |
|-------|------|---------------|----------------|
| L1 | The record | What actually happened? | Factual only – no interpretation |
| L2 | Legislative and policy signal | What does this mean for the bills? | Flag provision numbers |
| L3 | Political intelligence | What are senators actually doing? | Must stay strictly separate from L2 |
| L4 | Risk and exposure | What should DCCEEW be watching? | Log every commitment on notice individually |
| L5 | Forward look | What is coming? | Be genuinely predictive – do not hedge |

**The most important design principle:** L2 and L3 must never bleed into each other. Political framing must not colour a policy assessment, and policy analysis must not carry a political interpretation. If L3 has low signal in a section, state that explicitly – do not pad.

---

## Formatting rules

These are non-negotiable for this project.

- **Use the three named list styles** (L1: Dot points, L2: Dot points, L3: Dot points) for all briefing content – fewer levels is better. Do not use paragraphs in briefing content unless a specific instruction says otherwise.
- **En-dashes with a space either side ( – )** – never em-dashes (—).
- **Sentence case for all headings** – never title case.
- **No ampersands** – always write "and".
- **Australian Government Style Manual** conventions apply to all formatting decisions.
- **Author-date referencing** where references are needed (Style Manual compliant).
- **L1: Dot points numbering is continuous** across all layers and sections in Part B – do not restart at each new section or layer.
- **One witness per line** in the section metadata table.
- **Referencing rule** – include a Hansard page (e.g. "Hansard p. 5") or approximate timestamp only when a point directly cites a specific moment. Do not add references to summarised or synthesised points. Use Hansard pages for Hansard sources; approximate timestamps for auto-generated transcripts.

---

## DOCX template styles

The template uses three list styles. Apply the correct style for each level:

- **L1: Dot points** — numbered (1. 2. 3.) — top-level content points
- **L2: Dot points** — lettered (a) b) c)) — sub-points that expand on or detail an L1 point
- **L3: Dot points** — bullet — third-level detail under an L2 point (use sparingly)

Top-level numbering (L1) continues across all layers and sections within Part B. Do not restart numbering at each new section or layer. Do not flatten multi-part content into a single L1 point — use L2 and L3 wherever a top-level point needs elaboration.

---

## Accuracy requirements

**Names, organisations and roles must be accurate and correctly associated.** Misattribution in an SES product is a serious credibility risk. Double-check every attribution before including it.

This applies especially to:
- Witness names, titles and organisations
- Senators and their party affiliations
- Which senator asked which question
- Which witness gave which answer

---

## Transcript quality flagging

When using an auto-generated transcript (not Hansard), apply the flag `[TRANSCRIPT QUALITY – VERIFY]` wherever the source text creates genuine analytical uncertainty. Pay particular attention to:

- Provision numbers – a single character changes the legal meaning
- Proper nouns – names and organisations are frequently mangled
- Technical environmental or legal terminology
- Internally inconsistent passages or missing answers

Never silently smooth over ambiguity. Surface it with the flag.

When using Hansard, omit the quality flag section entirely.

---

## Part A – Priority flags structure

Part A uses four named categories (not emoji traffic lights). Populate each with dot points. Write 'Nil' if a category has no items – do not leave it blank.

1. **Urgent action** – commitments on notice with imminent deadlines, significant reputational risk
2. **Significant risks or exposures** – near-term attention items
3. **Legislative or policy signals** – strategic importance
4. **Forward preparations** – upcoming hearings or reporting

---

## Section grouping logic

Choose the grouping that best serves analytical clarity for DCCEEW readers for this specific hearing. Document the choice in the Section grouping note before the first section.

| Grouping | When to use |
|----------|-------------|
| By bill | Senators direct inquiry at specific bills |
| By witness bloc | Insights cluster by witness type rather than bill |
| By theme | Cross-cutting issues run across multiple bills and witnesses |
| Hybrid | Distinct government witness bloc plus thematic bill discussion |

---

## What this project is not

- Not an Estimates briefing system – the framework is calibrated for legislative inquiry committees
- Not suitable for classified material – use only public Hansard or auto-generated transcripts
- Not a summarisation tool – the five-layer model produces intelligence, not summary

---

## Files not to modify during briefing generation

- `DCCEEW_Briefing_OutputTemplate.docx` – this is the canonical template; copy it for each output, do not edit it in place
- `prompt.md` – treat as read-only during briefing generation; updates to the prompt itself go through the development process

---

## Suggested workflow for a new hearing

```
1. Confirm transcript is in sources/ and note whether it is Hansard or auto-generated
2. Read prompt.md
3. Note the hearing date and committee for the output filename
4. Generate the briefing content applying the five-layer framework
5. Populate a copy of DCCEEW_Briefing_OutputTemplate.docx
6. Save as [COMMITTEE]_HIB_[NNN]_[YYYYMMDD].docx in the repo root
7. Verify: all placeholders replaced, all /// blocks removed, empty table rows deleted,
   header/footer fields updated, witness names verified
```

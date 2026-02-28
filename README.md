# HearingBriefing

AI-assisted intelligence briefing system for Senate committee hearings.

Developed by the Digital Enablement and Transformation team, Environment Information Strategy and Policy Branch, DCCEEW.

---

## Purpose

This repository contains the prompt, output template and supporting documentation for generating structured intelligence briefings from Senate committee hearing transcripts.

The system is calibrated for the Environment and Communications Legislation Committee's inquiry into the Environment Protection Reform Bill 2025 and related bills. It is designed for SES Band 1 and above staff who need a complete analytical picture of proceedings without watching hearings in person.

---

## Files

| File | Purpose |
|------|---------|
| `prompt.md` | Operational prompt – copy and use for each hearing |
| `DCCEEW_Briefing_OutputTemplate.docx` | Branded DOCX template – copy for each output, do not edit in place |
| `DCCEEW_Senate_Briefing_UserGuide.md` | Design rationale, usage guidance and limitations |
| `CLAUDE.md` | Claude Code project instructions |
| `sources/` | Place input transcripts here before running |

---

## Quick start

1. Place the Hansard or auto-generated transcript in `sources/`
2. Open a Claude Code session in this repository
3. Claude Code will read `CLAUDE.md` automatically
4. Provide the transcript and instruct Claude to generate the briefing
5. The output will be saved as `[COMMITTEE]_HIB_[NNN]_[YYYYMMDD].docx`

For detailed usage guidance including design decisions and limitations, see `DCCEEW_Senate_Briefing_UserGuide.md`.

---

## Output naming convention

```
[COMMITTEE]_HIB_[NNN]_[YYYYMMDD].docx
```

Example: `ECLC_HIB_003_20260214.docx`

---

## Classification

Outputs are marked **OFFICIAL Sensitive**. Do not distribute externally.

---

## Contact

Digital Enablement and Transformation  
Environment Information Strategy and Policy Branch  
Department of Climate Change, Energy, the Environment and Water  
DCCEEW.gov.au

# User Guide: Senate Committee Hearing Intelligence Briefing Framework

**DCCEEW Internal | Environment and Communications Legislation Committee**
Version 1.0 | February 2026

---

## What this tool is

This framework is a structured prompt for Claude (the AI assistant at claude.ai) that transforms a Senate committee hearing transcript into a comprehensive intelligence briefing for SES staff.

The output is designed to replace the experience of watching a hearing in person — not simply summarise it. That distinction shapes every design decision in the framework.

The prompt file (`prompt.md`) contains everything you need to run a briefing. The reference document (`DCCEEW_Briefing_OutputTemplate.docx`) explains the reasoning behind the design and provides output templates as a quality-check guide.

---

## Quick start

1. Open the prompt file (`prompt.md`)
2. Copy the entire prompt (from **ROLE AND CONTEXT** to the end of **TONE AND QUALITY STANDARDS**)
3. Fill in the three bracketed fields at the top: committee name, hearing date, and transcript source
4. If using an auto-generated transcript rather than Hansard, keep the **TRANSCRIPT QUALITY FLAG** section; if using Hansard, delete it
5. Paste or upload the Hansard/transcript immediately after the final instruction
6. Submit to Claude

A typical hearing transcript will produce a complete briefing in one response. For very long hearings, you may need to split the transcript and ask Claude to integrate the results.

---

## Inputs: Hansard vs auto-generated transcripts

**Always prefer Hansard.** It is the official parliamentary record and the only source that should be used to verify commitments on notice or quotes that may be cited in minister briefings. Hansard is available from the Parliament of Australia website, usually within 3–5 business days of a hearing.

**Auto-generated transcripts** are acceptable when a quick turnaround is required. The framework includes a quality flagging system — any passage where the transcript quality may affect reliability is flagged with `[TRANSCRIPT QUALITY — VERIFY]` so that the reader knows to check the Hansard before acting on it.

The most common error types in auto-generated committee transcripts are: provision numbers (critical — a single digit changes the legal meaning), witness and organisation names, and technical environmental and legal terminology.

---

## The five intelligence layers: design rationale

The framework structures every section of a briefing through five sequential layers. Here is why each layer exists and why the design choices were made.

### Why five layers rather than a conventional summary?

A conventional summary answers "what happened." That is necessary but insufficient for SES staff in a legislative inquiry context. The five-layer model is designed to answer five different questions simultaneously — moving from objective record to forward-looking assessment — without conflating them.

The most important design principle is **analytical separation**: factual content, policy analysis, and political analysis are deliberately kept in different layers. This prevents the most common failure mode in committee briefings, which is political framing contaminating a policy assessment (or vice versa). A statement that a particular provision was attacked politically is different from an assessment that the provision is legally vulnerable — and a briefing that blurs those two things is actively dangerous for decision-makers.

### L1 — The Record

The evidentiary foundation. It exists because everything else in the briefing depends on it being accurate. If L1 is wrong, the policy analysis in L2 is based on a false premise, the risk assessment in L4 may miss a genuine commitment on notice, and the forward look in L5 will be pointing in the wrong direction.

The instruction to cross-reference Hansard page numbers is deliberate: it makes the briefing auditable.

### L2 — Legislative & Policy Signal

In a legislative inquiry committee (as distinct from Estimates), the committee is actively constructing a legislative record. Every line of testimony has the potential to inform committee recommendations that could reshape the bills. L2 exists to make this operationally visible — mapping testimony to specific provisions so that the policy teams working on each bill can identify what has shifted.

The instruction to flag provision numbers wherever possible comes from experience: without this anchor, the policy significance of a piece of testimony is impossible to assess quickly.

### L3 — Political Intelligence

This layer is kept strictly separate from L2 for a specific reason: the analytical needs are different and the risks of mixing them are real. An SES officer reading a briefing needs to be able to distinguish between "this provision is legally problematic" and "this provision is being used as a political pressure point" — because the response to each is different. L3 exists to surface the political dynamics cleanly, without those dynamics distorting the policy analysis.

The instruction to explicitly note "low signal" when political dynamics are thin is also important: it prevents the layer from being padded with generic observations about senate committee process, which would reduce the signal-to-noise ratio for readers who need to act quickly.

### L4 — Risk & Exposure Read

This is the action layer — the one that most directly drives what DCCEEW needs to do after a hearing. It is placed fourth (after the factual and analytical layers) because risk assessment without an evidentiary foundation and policy analysis to anchor it tends to be either alarmist or superficial.

The commitment on notice logging format (senator / question / witness / due date) is prescribed because incomplete logging of commitments is a common and consequential failure mode. If a commitment is logged without the senator who asked or the due date, it cannot be reliably actioned.

The instruction to note officials who appeared to struggle under questioning "with appropriate sensitivity" is a deliberate calibration for SES audience. The briefing should be honest — an SES reader needs to know if there is a reputational risk to manage — but it should be professional and proportionate.

### L5 — Forward Look

This layer was included after recognising that the value of a committee briefing extends beyond understanding what happened: SES staff need to know what to prepare for. The instruction that L5 should be "genuinely predictive, not a hedge" is the most demanding calibration instruction in the framework — it asks the analyst (AI or human) to commit to an assessment rather than producing a balanced list of possibilities. A forward look that says "the committee may or may not pursue this line" is not useful.

---

## Output structure: design rationale

### Why executive briefing first?

The Executive Briefing is placed first because time-poor SES readers may read only this section. It must therefore be complete enough to stand alone. The priority flags with traffic light indicators provide a fast triage function — readers who have 90 seconds can read the flags and know whether they need to read further.

The political temperature read is written to be potentially shared with or paraphrased for the Minister. This is a deliberate calibration: it encourages plain English and avoids the insider jargon that sometimes characterises briefings circulated only within a department.

### Why flexible section grouping with a fixed internal anatomy?

The section grouping — by bill, witness bloc, theme, or hybrid — is made flexible because the right grouping varies by hearing. A hearing dominated by a single witness bloc of peak environment groups is best analysed by witness; a hearing that sweeps across three bills is better grouped by bill so policy teams can find their material.

But within each section, the anatomy is fixed. This is important for two reasons: consistency (readers who use the framework regularly know exactly where to find each type of information) and quality control (a fixed anatomy makes it easier to check whether the AI has applied all five layers or skipped one).

The requirement for a section grouping note at the top of Part B serves a transparency function: it explains the analytical choice made for this hearing and allows the reader to disagree with or query it.

### Why a Quick Reference Appendix?

The three appendix tables — commitments on notice, key quotes, and forward action items — exist because the most operationally critical information in a hearing often needs to be extracted and acted on without re-reading the full briefing. The appendix functions as a task list and reference document that can be shared with action officers without sharing the full intelligence briefing.

---

## Transcript quality flagging: why it matters

The `[TRANSCRIPT QUALITY — VERIFY]` flag is not a disclaimer — it is an active quality control mechanism. Its purpose is to prevent auto-transcription errors from propagating into actions.

The most dangerous category of error is provision numbers. If an auto-transcript renders "Section 23B" as "Section 23D," and a briefing based on that transcript tells an SES officer that Section 23D was questioned, and an SES officer briefs a minister that Section 23D is at risk — the downstream effects of a single character error can be significant.

The instruction to "not silently smooth over ambiguous passages" is equally important. An AI system that smooths over ambiguity to produce a coherent-sounding briefing is actively misleading the reader. The framework is designed to surface uncertainty rather than conceal it.

---

## Limitations and when not to use this framework

**Very long hearings (full-day or multi-day).** The framework is designed for a single hearing session. For multi-day hearings, process each session separately and ask Claude to produce an integrated summary across sessions at the end.

**Confidential or classified material.** Do not paste classified material into claude.ai. If a hearing involves material at a level above the system's handling capability, produce the briefing from the public Hansard only and add classified context separately in a secure environment.

**Estimates.** This framework is calibrated for legislation committee inquiries. Estimates proceedings have a different structure and different intelligence priorities (the risk of a minister's commitment slipping through, budget-related admissions, etc.). A separate Estimates prompt is recommended.

**Real-time use.** The framework is designed for post-hearing analysis from a transcript, not for real-time note-taking during a hearing.

---

## Maintenance and review

This framework should be reviewed and updated:

- After the committee tables its report — to assess whether the Forward Look predictions were accurate and calibrate accordingly
- When new bills are referred to the committee — update the bill reference in the prompt
- After significant feedback from SES users
- When major changes occur to the transcription infrastructure

Version history should be maintained in the reference document. The prompt file is the operational document — it should always reflect the current approved version.

---

## About the design process

This framework was developed through a structured design process that began with a requirements analysis focused on the specific needs of DCCEEW SES staff in a legislative inquiry context, rather than adapting a generic briefing template.

The key design insights that shaped the framework were:

**The committee is building a legislative record.** This is the central difference between a legislation committee inquiry and Estimates. The intelligence priorities are different, and a framework calibrated only for Estimates would miss the most important analytical work.

**Factual and political analysis must be separated.** This is not conventional in most briefing formats, but it is essential for a senior audience that needs to distinguish between legal vulnerability and political pressure.

**The forward look must be predictive.** Most briefing templates end with "issues to watch" lists. This framework pushes further — it asks for genuine assessment of trajectory, preparation advice, and emerging recommendations signals.

**Analytical honesty about low-signal layers is more valuable than padding.** A layer that has low signal in a given section should say so. A briefing that pads thin analysis to maintain apparent consistency is actively misleading.

**The audience calibration must be explicit.** The instruction that the political temperature read "may be shared with or paraphrased for the Minister" changes how it is written. Making that calibration explicit in the prompt produces consistently better output.

---

*DCCEEW Internal — Not for external distribution*
*Framework developed for the Environment Protection Reform Bill 2025 inquiry cycle*

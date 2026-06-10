---
name: brooklet-ro-assessment
description: Assess whether a proposed individual is preliminarily suitable to act as a Responsible Officer for an SFC licence application, especially for Type 1, Type 4 and Type 9 cases. Use this skill whenever the user asks for an RO assessment, wants to compare RO candidates, asks whether someone meets the RO hard requirements, provides a CV together with an SFC licence record, or needs a client-facing preliminary RO conclusion plus internal supporting notes. This skill should also be used when the user asks to cross-check CV job history against SFC licence history, review relevant industry experience over the past 6 years, or check whether the exam / exemption position is actually proven rather than assumed from a public licence record.
---

# Brooklet RO Assessment

Assess whether a proposed individual is preliminarily suitable to act as a Responsible Officer (RO) for an SFC licence application.

This skill produces two deliverables:

1. **Client-facing preliminary reply** (`.docx`, Brooklet Word style) — short, commercially presentable conclusion.
2. **Internal supporting note** (`.docx`, Brooklet Word style) — evidence pack with full cross-check tables.

Main focus: **Type 1 / Type 4 / Type 9** RO cases.

Do not generate MIC allocation unless the user separately asks for it after RO suitability has been preliminarily established.

## Use this skill when

The user:
- asks whether a person is suitable to act as an RO;
- asks whether a candidate meets the RO hard requirements;
- wants to compare 2 or more RO candidates;
- provides a CV and an SFC licence record for cross-checking;
- asks for a client-facing preliminary RO conclusion;
- asks for internal supporting notes;
- asks whether relevant industry experience is sufficient over the past 6 years; or
- asks whether the current exam / exemption position is actually proven (not just inferred from a public licence record).

## Reference files

Always consult these reference files before drafting. They contain the canonical rules — do not invent alternatives.

| Reference | When to read |
|---|---|
| `references/intake-checklist.md` | Always read at the start, before drafting anything. |
| `references/sfc-exam-framework.md` | Read whenever you need to determine the exam / exemption position. **Do not work from memory** — the agent has gotten paper combinations wrong in the past. |
| `references/client-output-template.md` | Read when drafting the client-facing reply. |
| `references/internal-note-template.md` | Read when drafting the internal supporting note. |

The `brooklet-word-document-style` skill governs Word formatting for both deliverables.

## Workflow

### Step 0 — Intake

Before producing any output, run the intake checklist (`references/intake-checklist.md`). Confirm at minimum:

1. Applicant entity name
2. Application type
3. Proposed RA(s) and role
4. Client name / salutation *(never guess — ask or use `[CLIENT]` placeholder)*
5. **Client document language** — if CV is in Chinese, ask 中文/英文; if CV is in English, default to English but state the assumption.
6. Number of candidates and CE numbers
7. Output file format *(default `.docx`; only use `.md` if explicitly requested)*

Do not skip Step 0. Most rework in past sessions came from defaulting language, salutation, or format without asking.

### Step 1 — Confirm scope

Identify and document:
- proposed candidate(s);
- proposed RA(s);
- proposed role (RO unless stated otherwise);
- proposed principal / business; and
- available source documents.

If the proposed RA or business scope is unclear, mark TBC and avoid over-committing.

### Step 2 — Look up the SFC Public Register

For each candidate, retrieve the SFC Public Register record using the CE number:
`https://apps.sfc.hk/publicregWeb/indi/[CE_NO]/details`

Capture from the register:
- Date of licence (formal SFO licence grant date)
- Date of first accreditation to a principal *(may pre-date the formal licence date — both matter)*
- Each RA × role × principal × period
- Any conditions
- Any disciplinary record

Use the formal **legal entity name** plus **CE number** of each principal, and record both Chinese and English names where available.

### Step 3 — Assess relevant industry experience (past 6 years)

For each proposed RA, build a table of experience over the past 6 years and label each row:
- **Direct** — substance squarely within the RA scope
- **Partial** — substance-dependent; bridgeable with evidence
- **Indirect** — control function, supporting function, related but not core
- **Not regulated-activity experience** — outside / non-financial roles

Conclude with a one-sentence italic verdict: `Type [X] view: direct experience ~ [N] years. [Satisfied / likely gap / TBC]`.

The benchmark is **3 years of direct experience within the past 6 years.** Do not over-include general background.

### Step 4 — Assess management experience (≥ 2 years)

Assess separately whether the candidate has at least 2 years of hands-on supervision/management of essential regulated functions, projects, or staff relevant to the proposed business.

Senior title alone is **not** proof. Look for substance.

### Step 5 — Check exam / exemption position

**Use `references/sfc-exam-framework.md` for every exam call.** That file contains the canonical RA → paper map and the 6 exemption pathways (3 RIQ + 3 LRP, plus re-entrant, conditional 1–4, etc.).

Use only one of these labels:
- **satisfied** — required papers demonstrably passed (or covered by an applicable exemption)
- **not proven** — evidence not on file
- **likely gap** — required papers clearly not all met
- **possible exemption** — exemption pathway available but conditions need confirmation

**Common Brooklet trap (Type 9):** Holding T9 LR proves Paper 1, 7, 12 only. T9 RO additionally needs Paper 6. Do **not** conclude exam satisfied without reading the framework file.

**Re-entrant 3–8 year window:** state both halves — no re-exam, but CPT top-up required (5 hours per RA per year out, ≥50% local).

State the conclusion in **one sentence** following the format in `references/sfc-exam-framework.md` §5 Step D.

### Step 6 — Assess practical feasibility

Cover:
- current employment;
- joining timeline;
- availability (any sole-RO restrictions, conditions);
- outside roles, directorships, shareholdings;
- PEP screening triggers;
- recency / lapse considerations.

### Step 7 — CV ↔ SFC cross-check

Compare the CV and SFC record line by line. Apply the rules in `references/internal-note-template.md` §"Table 2".

Common errors to avoid:
- Confusing "Date of licence" with "Date of first accreditation" — these can differ by weeks.
- Mis-stating dates from memory. **Always verify against the SFC Public Register page or a cited subagent extraction.**
- Using mixed entity names (e.g. "BOCOM IAM" in one row, "BOCOM International Asset Management Limited" in another). Pick one short form, define it in the Naming conventions section, and use it consistently.

### Step 8 — Draft and deliver

Produce the two deliverables in this order:

1. **Internal supporting note** first — it forces evidence discipline. Follow `references/internal-note-template.md` for structure, language rules, and the acronym discipline ("full term (acronym)" on first occurrence).

2. **Client-facing reply** — distil the internal note into the unified structure in `references/client-output-template.md`. Both Chinese and English versions use the **same layout**: salutation + opening line, then one short paragraph per candidate, then a single closing block combining a pairing thesis / overall recommendation with a numbered 「其他事项 / Other matters」 list, then a sign-off line. Length target: 600–900 字 (Chinese) or 400–600 words (English).

Both deliverables go out as `.docx`. Render to PDF + JPG previews and **visually QA** before sharing — past errors include broken table wrapping, wrong dates, and bare abbreviations.

## Drafting prohibitions

Do not:
- invent project details, AUM, supervisory scope, exam history, or exemption basis;
- assume that a strong historical licence record solves the current exam requirement;
- treat T9 LR as proof of T9 RO papers;
- include internal warnings or evidence trails inside the client-facing paragraph;
- silently default the output language away from the user's working language;
- guess the client salutation;
- deliver `.md` when the user expects `.docx`;
- introduce an abbreviation without first-occurrence expansion;
- mix multiple short forms for the same entity within one document.

## Quality bar

Before sharing either file, run the checklist in `references/internal-note-template.md` §"Quality checklist before delivery". Do not skip the visual QA step — render to PDF/JPG and read every page.

## Default prompt wrapper

When applying this skill, structure the response as:

> "Applying the Brooklet RO Assessment skill. Intake summary: [list confirmed items]. Pending items: [TBCs]. Producing (i) internal supporting note in `.docx` and (ii) client-facing preliminary reply in `.docx`. Internal note: English-primary with bilingual entity names. Client reply: [language] in [一/二/其他事项 | per-candidate paragraph] format. Cross-checking SFC Public Register record against CV. Exam position to be assessed against `references/sfc-exam-framework.md`."

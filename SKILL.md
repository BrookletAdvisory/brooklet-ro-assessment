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
| `references/templates/MIC-Organisational-Chart-Template.pptx` | **Canonical PPT template for MIC org chart.** When generating MIC allocation, open this file and replace text placeholders — never recreate layout from scratch. |
| `references/templates/MIC-Acknowledgement-Form-Template.docx` | **Canonical Word template for MIC Acknowledgement Form.** When generating per-RO acknowledgement forms, open this file and fill Part A + signature line — never modify formatting. |

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

### Step 9 — MIC Allocation (only when user explicitly requests)

When the user asks for Management-in-Charge (MIC) allocation after RO suitability has been preliminarily established, produce two deliverables: (i) a **PowerPoint (.pptx) MIC Organisational Chart** and (ii) **one MIC Acknowledgement Form (.docx) per RO**.

---

### Step 9A — MIC Organisational Chart (.pptx)

**Template:** `references/templates/MIC-Organisational-Chart-Template.pptx`

**Method:** Open the template, replace text placeholders (names, job titles, MIC function labels) **without modifying shapes, positions, connectors, or formatting.** Every GROUP shape in the template already contains MIC function labels and name/title placeholders — only replace the text content.

**How the template is structured:**
- Each MIC function has a **name-label GROUP** positioned above the function box. Inside the GROUP: a MIC label (e.g. "MIC of Risk Management"), an RO name box, and a title box ("Responsible Officer").
- The KBL section has a **joint-responsibility** name box (contains both ROs' names side by side, label reads "Responsible Officers" plural).
- The bottom row shows all core functions (Finance, IT, Compliance, Risk, Operations, Sales & Marketing). Some are assigned to named ROs; unassigned functions are covered by a note: *"As part of its commitment to enhanced corporate governance and the principle of segregation of duties, the Company will seek additional suitable candidates to assume the role of Manager-in-Charge for these core functions."*
- A "Supported by" box lists external support: law firm, compliance consulting firm, fund administrator.
- Company name appears in the title header — replace the placeholder `[NAME OF LICENCE APPLICANT]` with the actual company name. **Brackets must be removed together with placeholder text.**
- Board of Directors box (top): Primary RO's name goes here.

**Binding Brooklet MIC conventions:**

| Convention | Rule |
|---|---|
| **All KBL functions are joint** | Key Business Line — Investment Management and Sales & Marketing are **always jointly held by two ROs**. The KBL name box shows both names; the label uses "Responsible Officers" (plural). |
| **OCR to operational RO** | Operational Control & Review goes to the more operationally hands-on RO. |
| **OMO to senior RO** | Overall Management Oversight goes to the most senior RO. |
| **RM to RO with risk credentials** | Risk Management goes to the RO with the stronger risk background. |
| **Compliance to RO with compliance background** | Compliance & AML/CTF goes to the RO who has directly managed a compliance department or held regulatory/AML roles. |
| **F&A / IT to senior RO** | Finance & Accounting and Information Technology default to the senior RO. |
| **Board → Primary RO** | The Board of Directors box carries the Primary RO's name. Joint RO is not on the Board unless explicitly instructed. |
| **External support annotation** | The template includes a "Supported by" box — keep this as standard disclosure. |

**Company name rule:** Replace the entire placeholder `[NAME OF LICENCE APPLICANT]` or text containing brackets with the actual company name. Output must not contain any brackets.

**Save as:** `[Applicant]-MIC-Organisational-Chart.pptx`

---

### Step 9B — MIC Acknowledgement Form (.docx), one per RO

**Template:** `references/templates/MIC-Acknowledgement-Form-Template.docx`

**Method:** Open the template, fill Part A personal particulars and the signature line at the document end. **Do not modify any formatting, styles, table structures, or layout.** Only replace text content.

**Part A fields to fill:**

| Field | Source |
|---|---|
| Full name in English | From CV / SFC record |
| Full name in Chinese | From CV / SFC record (if available) |
| HKID No. | **Ask user to provide.** If not provided, leave blank — the client fills this in themselves. Do not guess or invent. |
| Passport No. | Leave blank (HK PR uses HKID) |
| CE No. | From SFC Public Register |
| Place of residence | From Information Request List |
| Job title | From Information Request List / MIC allocation |
| Mobile No. | From Information Request List |
| Personal email address | From Information Request List |
| Report to | Senior RO / Board / CEO (confirm with user) |

**Opening paragraph (Part A — Acknowledgement):** Fill in the RO's name and MIC function(s) on the blank lines in paragraph [2]:
- `I,___[RO Name]___, holder of the HKID Card / Passport No.___[leave blank]___, hereby acknowledge and accept my appointment as Manager-in-Charge of___[MIC function(s)]___ of [Company Name]...`

**Signature line (end of document):** Fill in the RO's name on the "Name" line in Table 3. Leave "Signature" and "Date" blank for the RO to complete.

**Save as:** `[Applicant]-MIC-Acknowledgement-Form-[ROName].docx`

**HKID rule:** Always ask the user: "Please provide the RO's HKID number, or I will leave it blank for the client to fill in." Never invent an HKID. If the user does not provide it, leave the field blank.

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

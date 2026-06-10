# Brooklet RO Assessment

A Claude Code skill for preliminary assessment of Responsible Officer (RO) suitability for SFC licence applications.

Focus: **Type 1** (Dealing in Securities), **Type 4** (Advising on Securities), **Type 9** (Asset Management).

## What it does

This skill guides your coding agent through a systematic 8-step assessment that produces two deliverables:

1. **Client-facing preliminary reply** (`.docx`) — short, commercially presentable conclusion
2. **Internal supporting note** (`.docx`) — full evidence pack with cross-check tables

### Assessment steps

| Step | Description |
|------|-------------|
| 0 — Intake | Confirm applicant entity, RA scope, client language, CE numbers |
| 1 — Scope | Identify proposed candidates, RAs, roles, and available documents |
| 2 — SFC Register | Retrieve and capture the SFC Public Register record for each candidate |
| 3 — Relevant experience | Assess past-6-year industry experience (Direct / Partial / Indirect) |
| 4 — Management experience | Assess ≥2 years supervision/management |
| 5 — Exam / exemption | Check paper requirements against SFC Guidelines on Competence |
| 6 — Feasibility | Current employment, availability, PEP screening, outside roles |
| 7 — CV ↔ SFC cross-check | Line-by-line comparison with gap analysis |
| 8 — Draft & deliver | Produce internal note first, then client-facing reply |

## Installation

### Claude Code (Official Marketplace)

```bash
/plugin install brooklet-ro-assessment@claude-plugins-official
```

### Manual Installation

Copy this repository into your `.claude/plugins/` directory:

```bash
git clone https://github.com/BrookletAdvisory/brooklet-ro-assessment.git
```

Or register as a custom marketplace:

```bash
/plugin marketplace add BrookletAdvisory/brooklet-ro-assessment-marketplace
/plugin install brooklet-ro-assessment@brooklet-ro-assessment-marketplace
```

## Dependencies

This skill works best alongside [Superpowers](https://github.com/obra/superpowers) and expects:

- **`brooklet-word-document-style`** — governs `.docx` formatting (Candara 12pt, A4, 1-inch margins, Brooklet house style)
- Internet access to query the [SFC Public Register](https://apps.sfc.hk/publicregWeb/)

## Usage

Simply provide your coding agent with the candidate's CV and SFC CE number, and ask:

> "Assess whether [candidate name] is suitable to act as an RO for [applicant entity] in connection with Type [X] + Type [Y] regulated activities."

The skill activates automatically when you:
- Ask whether a candidate meets RO requirements
- Provide a CV with an SFC licence record for cross-checking
- Request a client-facing preliminary RO conclusion
- Ask to compare multiple RO candidates
- Ask whether exam/exemption positions are proven

## How it works

The skill contains a canonical SFC exam framework covering:

- RA 1 / RA 4 / RA 9 paper requirements for RO and LR
- 6 exemption pathways (3 RIQ + 3 LRP, plus re-entrant and conditional)
- Decision logic for reading a candidate's licence record into a paper position
- Common Brooklet traps (e.g., T9 LR ≠ T9 RO papers)

Agents are instructed to **always consult reference files** rather than working from memory — the exam framework has specific paper combinations that agents frequently get wrong otherwise.

## Skill structure

```
brooklet-ro-assessment/
├── SKILL.md                              # Main skill definition
├── references/
│   ├── intake-checklist.md               # Mandatory pre-drafting checklist
│   ├── sfc-exam-framework.md             # Authoritative exam requirements
│   ├── client-output-template.md         # Client-facing reply structure
│   └── internal-note-template.md         # Internal evidence pack structure
├── .claude-plugin/
│   └── plugin.json                       # Claude Code plugin manifest
├── LICENSE
└── README.md
```

## Philosophy

- **Evidence over assumption** — every exam position, date, and licence line must be traceable to a cited source
- **Systematic over ad-hoc** — the 8-step workflow prevents skipping steps that cause rework
- **Client-ready output** — the internal note forces evidence discipline; the client doc distills it commercially
- **Don't guess** — client salutation, document language, and output format are confirmed before drafting

## Contributing

This skill is maintained by [Brooklet Advisory Limited](https://github.com/BrookletAdvisory). If you find issues or have suggestions, please open an issue on the repository.

## License

MIT — see [LICENSE](LICENSE) file for details.

# Intake Checklist — Ask Before Drafting

Before producing any client-facing or internal output, the agent **must** confirm the following items with the user. Missing any of these is a frequent cause of rework.

If the user has already provided an item in the conversation, do **not** ask again — re-state your understanding and proceed. If unsure, ask.

## Mandatory intake items

| # | Item | What to ask |
|---|---|---|
| 1 | **Applicant entity name** | Exact legal / commercial name of the SFC licensee or applicant for whom the RO is being assessed. *(e.g. "Wise Delta")* Used in titles and the opening line of the client doc. |
| 2 | **Application type** | New licence application / adding RA / replacing RO / appointing additional RO. Affects substance assumptions. |
| 3 | **Proposed RA(s) and role** | Confirm RA list (e.g. RA 1, RA 4, RA 9) and role (RO / LR). Default in Brooklet practice: RO. |
| 4 | **Client name / salutation** | The contact person to be addressed in the client doc. **Never guess.** Either ask or insert the placeholder `[CLIENT]` to be filled in. Example past use: 「伊总」, 「Albert」, 「Mr. Chan」. |
| 5 | **Client document language** | Default logic: if **CV is in Chinese**, ask the user "中文还是英文". If **CV is in English**, default to English (still confirm if uncertain). Never silently default the language away from the user's working language. |
| 6 | **Internal note language** | Default: English-primary, with **bilingual (Chinese + English)** entity names for any former or current Hong Kong / Mainland China employer. CV Chinese-original phrasing may be retained for cross-reference. |
| 7 | **Number of candidates** | If >1, also ask whether the user wants individual notes or a comparative pairing thesis. |
| 8 | **CVs and SFC CE numbers** | Required documents. If only the name is given, ask for CE number (or offer to look it up on the SFC Public Register). |
| 9 | **Output file format** | Default: **.docx for both client doc and internal note** (Brooklet Word style). Only use `.md` if the user explicitly asks. |

## Suggested concise intake message (Chinese)

When intake is incomplete, send something like:

> 在开始评估前，需要先跟你确认以下信息：
> 1. 申请实体（公司）名称：________
> 2. 客户称呼（开头要怎样称呼）：________
> 3. 客户文件输出语言：中文 / 英文 / 双语？
> 4. 候选人 CE 编号（如果只给了姓名）：________
> 其余信息（牌照类型、角色 RO/LR、是否对比多人）我从你的描述里已经理解为：…… 如有偏差请指正。

Adapt to English if the user is conversing in English.

## Do **not** ask if already known

Skip the question if the user has already supplied the answer earlier in the same thread, or if a prior task in the same Space established a default (e.g. internal note language was already agreed).

## Defaults to assume silently (only when truly safe)

| Item | Safe default |
|---|---|
| Output file format | `.docx` |
| Internal note format style | Brooklet Word style — Candara 12pt, table-based, A4, 1-inch margins |
| Internal note language | English-primary with bilingual entity names |
| Client doc structure | 一/二/其他事项 segmented Chinese paragraphs *(if Chinese)* OR per-candidate paragraph *(if English)* |
| Source for SFC licence record | SFC Public Register — agent to look up if CE number provided |

If a default is applied without asking, **state it clearly** in the response so the user can override.

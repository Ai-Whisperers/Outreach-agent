# Email history

Store a **durable, searchable** record of outreach email **sent and received**. Use this when CRM or inbox search is not enough for the team or for agent context.

## Where to put files

Put material under **[`threads/`](threads/README.md)**—one **thread** (one conversation / one counterparty) per file or per subfolder.

## Naming (recommended)

Pick one style and stay consistent:

| Style | Example |
|-------|---------|
| **Single file per thread** | `threads/2026-06-08–wesley-vandecamp–discovery-followup.md` |
| **Folder per thread** | `threads/wesley-vandecamp/2026-06-08-outbound.md` + `2026-06-10-inbound.md` |

Use **ISO date** prefix so lists sort chronologically. Slug = lowercase, hyphens, no secrets in the filename.

## Log format (markdown)

For hand-pasted logs, a minimal block per message:

```markdown
## 2026-06-08 15:30 CET — OUTBOUND — subject line

From: you@example.com  
To: lead@example.com  

(body)

---

## 2026-06-09 09:12 PY — INBOUND — Re: subject line

(body)
```

For **raw** `.eml` exports, keep one file per message or per thread in a thread folder and add a one-line `README.md` in that folder describing who / what campaign.

## Privacy and OPSEC

* **Do not** commit live **passwords**, **magic links**, **unsubscribe tokens**, or **full** payment / government IDs. Redact or replace with `[REDACTED]`.
* Assume this repo may be **cloned or shared**; treat every file as **internal but not ultra-secret**.
* If a thread is legally or commercially sensitive, keep it **out of git** (local only) or use a private annex and document the pointer here without the body.

## Language (internal vs client)

Follow **`rule.outreach.language-locale.v1`**: **English** for thread summaries, headings, and checklists; **Dutch** (or the lead’s locale) **only** inside the fenced client e-mail / message draft. See `outreach-language-locale-rule.mdc` under `.cursor/rules/outreach/`.

## Linking to leads

In the thread file or folder, add a line near the top:

```markdown
**Lead briefing:** `../../Leads/Briefings/Europe/Lead Briefing – …`
```

Adjust the relative path to match where the briefing lives.

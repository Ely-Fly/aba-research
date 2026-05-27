---
name: aba-research
description: Research assistant for BCBAs and ABA practitioners. Use this skill whenever the user asks for research, papers, updates, or findings on any ABA or autism-related clinical topic — including early intervention, verbal behavior, AAC, BACB ethics and supervision, Medicaid billing, or new medications/therapies for autism. Trigger even if the user phrases it casually ("find me something on X", "what's new with Y", "any recent studies on Z") where X/Y/Z relates to ABA, autism, or behavioral therapy. This skill searches authoritative, peer-reviewed sources, filters strictly for recency and credibility, and produces a clean, shareable HTML report. Use it proactively any time the user is hunting for clinical evidence, regulatory updates, or practice guidance in the ABA/autism space.
---

## Who you're helping

A BCBA working in a pediatric clinic with children ages 0–10. They need clinically relevant, peer-reviewed information they can act on and share with colleagues. Credibility and efficiency matter — they don't have time to sift through blogs, outdated studies, or non-credentialed commentary.

## Priority Topics

When selecting among results, favor findings in these areas (match to the user's query):
- Early intervention for autism (ages 0–6)
- Verbal behavior and AAC (Augmentative and Alternative Communication)
- BACB ethics, supervision standards, and certification updates
- Medicaid billing changes in Virginia
- New medications and therapies relevant to autism/ABA

## Approved Sources

Search and cite only from these:
1. **PubMed** — always include; prioritize peer-reviewed studies
2. **BACB.com** — ethics, supervision, and certification updates
3. **Autism Speaks** (autismspeaks.org) — organization-backed resources
4. **Credentialed researchers/physicians on X (Twitter)** — only accounts with MD, PhD, or BCBA credentials; skip anonymous or non-credentialed accounts

**Never cite**: WebMD, Healthline, Psychology Today blogs, parent blogs, general news sites, opinion pieces, or non-credentialed commentary.

## Recency Filter

Only include results published within the last 3 years. If you cannot confirm the publication date, exclude the result.

## Research Process

1. Search the approved sources for the user's topic
2. For each candidate result, verify: Is it peer-reviewed or from an authoritative org? Is it within the last 3 years? Is it clinically relevant to ABA/autism practice?
3. Select the **top 5 most relevant** results — no more than 5; fewer only if fewer than 5 credible results exist
4. For each result, collect:
   - Title with working URL
   - Source name
   - Publication date
   - A 2-sentence plain-language summary focused on clinical relevance
   - One topic tag from: Early Intervention, AAC, Ethics, Medicaid, Medication, Verbal Behavior, Supervision, Other

## Output

Write results to an HTML file named `aba-research-<topic-slug>-<YYYY-MM-DD>.html` in the current working directory.

No preamble, no synthesis paragraph, no introduction — go straight to the results.

---

## HTML Template

The file must be self-contained (no external CSS/JS). Clean, professional, printable — suitable for sharing with colleagues.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ABA Research Report — {TOPIC}</title>
  <style>
    body { font-family: Georgia, serif; max-width: 860px; margin: 40px auto; padding: 0 24px; color: #1a1a1a; background: #fafafa; }
    header { border-bottom: 2px solid #2c5f8a; padding-bottom: 16px; margin-bottom: 32px; }
    h1 { font-size: 1.6rem; color: #2c5f8a; margin: 0 0 6px; }
    .meta { font-size: 0.85rem; color: #666; }
    .card { background: #fff; border: 1px solid #dde4ec; border-radius: 8px; padding: 20px 24px; margin-bottom: 20px; box-shadow: 0 1px 3px rgba(0,0,0,0.06); }
    .card h2 { font-size: 1.05rem; margin: 0 0 6px; }
    .card h2 a { color: #2c5f8a; text-decoration: none; }
    .card h2 a:hover { text-decoration: underline; }
    .card-meta { font-size: 0.82rem; color: #777; margin-bottom: 10px; }
    .summary { font-size: 0.95rem; line-height: 1.6; margin: 0 0 12px; }
    .tag { display: inline-block; padding: 3px 10px; border-radius: 12px; font-size: 0.75rem; font-weight: 600; text-transform: uppercase; letter-spacing: 0.04em; }
    .tag-early-intervention { background: #e8f4e8; color: #2e7d32; }
    .tag-aac                { background: #e3f2fd; color: #1565c0; }
    .tag-ethics             { background: #fce4ec; color: #880e4f; }
    .tag-medicaid           { background: #fff8e1; color: #e65100; }
    .tag-medication         { background: #f3e5f5; color: #6a1b9a; }
    .tag-verbal-behavior    { background: #e0f7fa; color: #006064; }
    .tag-supervision        { background: #fbe9e7; color: #bf360c; }
    .tag-other              { background: #f5f5f5; color: #424242; }
    @media print { body { background: white; } .card { box-shadow: none; border: 1px solid #ccc; } }
  </style>
</head>
<body>
  <header>
    <h1>ABA Research Report: {TOPIC}</h1>
    <p class="meta">Generated: {DATE} &nbsp;·&nbsp; Sources: PubMed, BACB.com, Autism Speaks, X (credentialed)</p>
  </header>

  <!-- Repeat for each of the 5 results -->
  <div class="card">
    <h2><a href="{URL}" target="_blank">{TITLE}</a></h2>
    <div class="card-meta">{SOURCE} &nbsp;·&nbsp; {DATE}</div>
    <p class="summary">{SENTENCE 1} {SENTENCE 2}</p>
    <span class="tag tag-{SLUG}">{TAG LABEL}</span>
  </div>

</body>
</html>
```

**Tag slug mapping:**
| Label | Slug |
|---|---|
| Early Intervention | `early-intervention` |
| AAC | `aac` |
| Ethics | `ethics` |
| Medicaid | `medicaid` |
| Medication | `medication` |
| Verbal Behavior | `verbal-behavior` |
| Supervision | `supervision` |
| Other | `other` |

---

## When done

Tell the user the filename written and how many results were included.

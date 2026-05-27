# ABA Research

A Claude Code skill for BCBAs and ABA practitioners to quickly surface the latest peer-reviewed research on autism and ABA topics — and deliver it as a clean, shareable HTML report.

---

## What this skill does

When you ask for research on any ABA or autism-related topic, the skill searches authoritative sources, filters for recency and credibility, and writes a polished HTML report file directly to your working directory. No synthesis paragraphs, no fluff — just the top 5 results, ready to share with colleagues.

## Why use it

Clinical literature moves fast. This skill cuts through the noise by enforcing strict source and recency standards — so every result you get is peer-reviewed, actionable, and up to date. Designed specifically for BCBAs who need reliable information quickly, without wading through blogs or outdated studies.

---

## What's included / excluded

**Searches these sources only:**
- PubMed (peer-reviewed studies, always included)
- BACB.com (ethics, supervision, and certification updates)
- Autism Speaks (autismspeaks.org)
- Credentialed researchers on X/Twitter (MD, PhD, or BCBA accounts only)

**Automatically excludes:**
- Anything published more than 3 years ago
- WebMD, Healthline, Psychology Today blogs
- Parent blogs, opinion pieces, non-credentialed commentary

---

## How to install

1. Download `aba-research.skill` from the [Releases](../../releases) page (or clone this repo)
2. In Claude Code, run:
   ```
   /plugin install path/to/aba-research.skill
   ```
3. Reload plugins:
   ```
   /reload-plugins
   ```

---

## How to use

Just ask naturally — the skill triggers automatically on any ABA/autism research request:

```
Find me recent studies on AAC for nonverbal toddlers with autism
What are the latest BACB ethics updates for supervisors?
Any new research on early intervention outcomes for kids under 3?
What's new on Medicaid billing for ABA in Virginia?
```

---

## Output

An HTML file written to your current working directory, named:

```
aba-research-<topic>-<YYYY-MM-DD>.html
```

Each report contains up to 5 result cards. Every card includes a clickable title, source and date, a plain-language 2-sentence clinical summary, and a color-coded topic badge (Early Intervention, AAC, Ethics, Medicaid, Medication, Verbal Behavior, Supervision). The file is self-contained, print-ready, and suitable for sharing with colleagues.


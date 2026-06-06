# ABA Research

A Claude Code skill that finds the latest autism and ABA research from trusted sources and generates a clean, shareable HTML report in seconds.

---

## What this skill does

When you ask for research on any ABA or autism-related topic, the skill searches authoritative sources, filters for recency and credibility, and generates a shareable HTML report with the top 5 most relevant sources. 

## Why use it

Clinical literature moves fast. This skill cuts through the noise by enforcing strict source and recency standards — so every result is sourced from trusted clinical, academic, or professional sources and filtered for recency and relevance. Designed specifically for researchers who need reliable information quickly, without wading through blogs or outdated studies.

---

## What's included / excluded

**Searches these sources only:**
- PubMed (peer-reviewed studies, always included)
- BACB.com (ethics, supervision, and certification updates)
- Autism Speaks (autismspeaks.org)
- Credentialed researchers on X/Twitter (used for recent commentary, study releases, and professional insights; not as a substitute for peer-reviewed literature)

**Automatically excludes:**
- Anything published more than 3 years ago
- WebMD, Healthline, Psychology Today blogs
- Parent blogs, opinion pieces, non-credentialed commentary

---

## How to use

Just ask naturally — the skill triggers automatically on any ABA/autism research request:

```
Find me recent studies on AAC for nonverbal toddlers with autism
What are the latest BACB ethics updates for supervisors?
Any new research on early intervention outcomes for kids under 3?
```

---

## Output

An HTML file written to your current working directory, named:

```
aba-research-<topic>-<YYYY-MM-DD>.html
```

Each report contains up to 5 result cards. Every card includes a clickable title, source and date, a plain-language 2-sentence clinical summary, and a color-coded topic badge (Early Intervention, AAC, Ethics, Medicaid, Medication, Verbal Behavior, Supervision). The file is self-contained, print-ready, and suitable for sharing with colleagues.

### Example Output 
<img width="806" height="990" alt="image" src="https://github.com/user-attachments/assets/3f0d64b6-99b7-47ed-ae34-c2a997636c7a" />

---

## How to install (Claude Code)

1. Clone this repo and open Claude Code from inside the folder:
   ```
   git clone https://github.com/Ely-Fly/aba-research.git
   ```
2. Run `/reload-plugins` in Claude Code

---

## Using with Claude AI (claude.ai)

No installation needed — just upload the skill file directly into any Claude AI conversation:

1. Download the skill file: [SKILL.md](https://raw.githubusercontent.com/Ely-Fly/aba-research/main/.claude/skills/aba-research/SKILL.md) (right-click → Save As)
2. Open [claude.ai](https://claude.ai) and start a new chat
3. Upload the file and ask your question:

```
Using the instructions in the uploaded SKILL.md, find me recent studies on AAC for nonverbal toddlers with autism
```

Claude will follow the skill's source and recency rules and return the results as an HTML code block — copy it, save it as a `.html` file, and open it in your browser.

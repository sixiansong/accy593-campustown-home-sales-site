# Agent log

Add a dated entry each time you work with your AI coding agent, with the newest entry at the bottom. Each entry records what you asked the agent, what it produced, and what you checked or changed. Paste your key prompts in exactly as you typed them. Include at least one time the agent got something wrong, and how you caught it.

Copy this outline for each entry:

```markdown
## YYYY-MM-DD: What you worked on

- **Asked:** "Paste your prompt here."
- **Agent produced:** What it made or changed.
- **Checked or changed:** How you checked it, and what you fixed.
```

## 2026-11-10: Built the city sales table page and filled in the README

- **Asked:** "Read AGENTS.md and docs/data_description_sheet.md first. Then replace the placeholder index.html with a simple page titled “College-Town Home Sales” that shows a table of the number of sales and the median sale price for each city, computed from data/college_town_home_sales.csv. Leave out sales under $10,000 and state that rule on the page. Round prices to whole dollars."
- **Asked (second task):** "Read AGENTS.md, docs/data_description_sheet.md and the outlines in README.md and AGENT_LOG.md first. In README.md: (1) replace the title with "College-Town Home Sales"; (2) delete the whole "Start here" section, including its file table; (3) "What this site is for": a short description of what the page currently shows (number of sales and median sale price for each of the 18 cities) and who it is for; (4) "Live site": the real URL above; (5) "Data notes": the rule that sales under $10,000 are left out (40 rows) and why medians are used instead of means (the 31 sales over $5,000,000), how each figure is defined, and one line on each of the "Five things that will bite you" saying whether it affects the current page; (6) "Tools we used": Claude Code (Haiku 5.5) on the web, plain HTML/CSS/JavaScript, GitHub Pages; (7) keep the Citation; (8) delete "Who did what" because I worked alone. In AGENT_LOG.md, add an entry for today (2026-11-10) following its outline, covering both tasks so far: building the city table page and filling in the README. Do not edit anything in data/. Open a pull request into main when done."
- **Agent produced:** A single `index.html` that reads the CSV in the browser and builds a table of sales count and median sale price for each of the 18 cities, with the under-$10,000 rule stated on the page. Then a rewritten `README.md` with the sections the prompt listed, and this log entry. Nothing in `data/` was changed. The page went live through PR #1.
- **Checked or changed:** The agent ran the page's calculation code in Node, and separately computed the same table in Python. All 18 cities matched, and both excluded 40 rows. The agent counted the 31 sales over $5,000,000 and the mean ($509,951) and median ($410,000) across kept sales from the CSV, and used them in the README. The agent did not view the page in a browser. Wrong turn: after `git push` was refused with a 403, the agent tried the GitHub connector to create the branch. That also returned a 403. The agent stopped and asked the user to install the Claude GitHub App with access to the repository, and pushed only after that.

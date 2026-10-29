# KU Project Risk Navigator — Static Edition (v1.1)

A small, browser-based technical project risk register, calculator, and heat map. No server, Docker, database, package installation, or API keys required.

## Features
- Multiple locally saved projects
- Add and edit risks, rationale, mitigation, owner, and target date
- Automatic 1–25 risk scoring and configurable-in-code classification
- Heat map and risk register with priority filter
- CSV risk-register export and full JSON backup/restore
- Printable risk assessment and mitigation report (browser Print → Save as PDF)
- Report fields for team, course, project scope, executive summary, and conclusions
- Report includes risk table, heat map, top-three risks, owner/mitigation matrix, and exercise completeness checks
- Preloaded fictional cloud-payroll project

## Run locally
Double-click `index.html` in a modern web browser.

## Publish with GitHub Pages
1. Create a new public repository on GitHub (for example `ku-project-risk-navigator`).
2. Upload `index.html` and this `README.md` to the repository's main branch at its root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select **main** and **/(root)**, then **Save**.
6. Open the published link after GitHub reports the site is live. It normally has the form `https://YOUR-USERNAME.github.io/ku-project-risk-navigator/`.

No build step is needed. Other static hosts (Netlify, Cloudflare Pages) can serve the same file.

## Data and security limitations
- Data is saved in the current browser's `localStorage`, not in GitHub or a shared database.
- Different people/devices will **not** see the same saved projects.
- A browser clear/reset, private browsing, or storage limits may remove local data. Export JSON backups regularly.
- JSON import replaces the current browser's projects.
- No login, account separation, permissions, auditing, shared instructor dashboard, encrypted storage, or server-side validation.
- Anyone with the public URL can view and use the app in their own browser. Do not store sensitive information in this prototype.
- CSV exports include spreadsheet formula-injection protection for fields beginning with special characters.

## Scoring methodology
Risk score = likelihood × impact (both 1–5). Low 1–4; Medium 5–9; High 10–14; Critical 15–25. This is an illustrative, qualitative prioritization policy, not a prescribed NIST formula. Threats and vulnerabilities inform the likelihood rationale. Risk treatments require reassessment; the app does not automatically reduce scores.

## Subsequent enhancement
For true multiuser collaboration, instructor dashboards, and centralized persistence, add a managed backend such as Supabase (database, Auth, row-level security) or a dedicated API. Such features are **not** present in this static edition.

## Assessment Report Generator (v1.1)
1. Choose a project and add or edit its risks.
2. Click **Generate Assessment Report** above the risk register.
3. Fill in the team, course, project scope, executive assessment, and conclusion.
4. Click **Open printable report**.
5. In the new tab, click **Print / Save as PDF**, and choose your browser PDF printer.
6. The report includes a check for 3–5 risks in each technical, security, and compliance category, matching the provided classroom exercise. The seeded demonstration project does **not** satisfy this count; add risks before submitting.

Report details are saved with each project in local browser storage and exported in JSON backups. Reports are generated entirely on the device, without a server. The generator does not create a PDF file directly; it uses the browser Print/Save as PDF workflow.

# Bridget Walker — Case Evidence Site

Private Jekyll site supporting LGSCO investigation ref **25 019 572**.

## Case references
- Council ref: 30000912
- LGSCO ref: 25 019 572
- ICB ref: BC70014
- Investigator: Paul Gyan-Apenteng

## Site structure
This is a Jekyll static site hosted on GitHub Pages (private repo).

- `_data/` — YAML data files. All content lives here; pages loop over them.
  - `timeline.yml` — chronological events
  - `issues.yml` — 47-item issue register
  - `parties.yml` — key parties
  - `dst.yml` — DST domain analysis
  - `integrity.yml` — document integrity table
- `_layouts/default.html` — single layout used by all pages
- `assets/css/style.css` — all styles (CSS variables, tables, timeline)
- `index.md` — summary / homepage
- `dst.md`, `parties.md`, `evidence.md`, `status.md` — individual pages (repo root)
- `timeline/index.md`, `issues/index.md`, `document-integrity/index.md` — may be in subfolders

## When adding new issues or timeline entries
Edit the relevant file in `_data/`. Pages loop over the data automatically — no need to touch the page files.

## Key facts for context
- Mrs Bridget Penelope Walker, DOB 08/10/1950, NHS 4883762742
- Residents at Palmerston House, Palmerston Road, Westcliff-on-Sea SS0 7TA (CQC loc 1-156343233)
- Attorneys: Mark Walker (son, joint LPA both domains) and Kira Walker (daughter, joint LPA both domains)
- Complaint against Southend-on-Sea City Council Adult Social Care
- LGSCO investigation active as of June 2026

## Privacy requirement
This site contains highly sensitive personal and medical data. Do not:
- Add raw evidence files (PDFs, emails, audio) to the repo
- Commit anything to a public branch
- Add any new pages or data without checking they don't introduce unredacted personal data beyond what is already present

## Do not modify
- The confidential banner in `_layouts/default.html`
- The `meta-robots: noindex, nofollow` tag

# Pentester Portfolio — Starter

This is a ready-to-publish GitHub Pages site for documenting your penetration testing write-ups and projects, using Jekyll (GitHub Pages builds this automatically — no local build step required).

## Setup (5-10 minutes)

1. **Create the repo.** On GitHub, create a new repository named exactly:
   `your-username.github.io` (replace `your-username` with your actual GitHub username).
   This exact naming makes GitHub Pages serve it at the root domain automatically.

2. **Push these files.**
   ```bash
   cd pentester-portfolio
   git init
   git add .
   git commit -m "Initial portfolio site"
   git branch -M main
   git remote add origin https://github.com/your-username/your-username.github.io.git
   git push -u origin main
   ```

3. **Enable GitHub Pages.**
   Go to your repo → Settings → Pages → under "Build and deployment," set Source to "Deploy from a branch," branch `main`, folder `/ (root)`. Save.

4. **Wait 1-2 minutes**, then visit `https://your-username.github.io`. Your site is live.

## Customize before publishing

- [ ] Edit `_config.yml` — replace title/description
- [ ] Edit `index.md` — your name, bio, contact links
- [ ] Delete or replace `writeups/2026-01-01-example-writeup.md` once you have a real entry
- [ ] Update `projects/index.md` as you complete Phase 5/6 projects

## Adding a new write-up

1. Copy `writeups/_TEMPLATE.md`
2. Rename it `writeups/YYYY-MM-DD-short-title.md`
3. Fill in every section — don't skip the Remediation or Lessons Learned sections, they're what differentiate a report from a walkthrough
4. Set `status: published` in the front matter when ready, commit, and push — it appears automatically on your `/writeups/` page

## Notes

- `_TEMPLATE.md` starts with an underscore so Jekyll ignores it as a collection item (it won't show up as a public page).
- The `writeup` layout (`_layouts/writeup.html`) automatically displays your tags and CVSS score at the top of each post — just fill in the front matter.
- Keep every write-up to the same structure. Consistency across 15-20 write-ups is what reads as professional to a hiring manager, more than any single polished one.

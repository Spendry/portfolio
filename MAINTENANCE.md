# Maintenance Guide

How to add a new project, a certificate, or a screenshot to this portfolio without breaking the linking model. Written for future me, a collaborator, or an AI assistant doing the work.

The model, in one line: **profile repo (Spendry/Spendry) → hub (this repo) → one repo per project**, with every link running both directions so a visitor can climb back out of any page.

---

## Questions to answer before adding anything

Answer these first. They decide everything below.

1. **Is it a project or an artifact?** A project gets its own repo: something with its own README that a reviewer could open, read, or run. An artifact goes in the `assets/` folder of the repo it supports: a single image, PDF, or document backing an existing entry.
2. **Which section does it belong to?** AI Engineering, Data and Analytics, Systems and Algorithms, or Frameworks and Writing. Pick the one section where a hiring reviewer gains the most from seeing it.
3. **What are the three facts a reviewer needs?** What it is (one sentence), what it demonstrates (name skills rather than adjectives), and one concrete anchor: a number, a benchmark, a screenshot. If you can't produce all three, it isn't ready to add yet.
4. **Does anything need credit?** Datasets, courses, templates, themes. Credit is one plain line naming the source with a link. State the source and move on.
5. **Do the stats hold up?** Only state a number in the exact scope it comes from. A figure that holds in one drill-through view is not a headline claim for the whole project.
6. **Is anything private in it?** No employer data, internal screenshots, real names, or keys. When unsure, leave it out and describe the capability in prose instead; the note at the bottom of [projects/data-analytics.md](projects/data-analytics.md) shows the pattern.
7. **Can it be shown live?** GitHub READMEs can't embed iframes or scripts, so screenshots are the standard. A live link (Power BI publish-to-web, GitHub Pages, a hosted demo) is an optional extra, added as a plain link. Check what publishing exposes before using it.
8. **Is it worth a slot?** Curate hard. Five legible projects with clean READMEs beat forty items in a drawer. If adding it means the section table stops fitting on one screen, consider what to remove.
9. **Do the skills lines have sign-off?** Before adding or updating any "Shows:" line, or any other claim about skills used or learned, check with Sam first. A project sometimes needs a clarification he hasn't given yet, and a published skills claim is a resume claim.

## Adding a new project (its own repo)

1. Create a local folder with a lowercase-hyphen name (`job-postings-dashboard`, not `Jobs Dashboard`).
2. Give it this shape:

   ```
   project-name/
   ├── README.md
   ├── .gitignore        (copy this repo's)
   ├── assets/           (screenshots: lowercase-hyphen names, under ~1 MB each)
   └── ...project files
   ```

3. README skeleton. The back-link on top is mandatory:

   ```markdown
   # Project Name

   > Part of my [portfolio](https://github.com/Spendry/portfolio).

   One-paragraph summary with the strongest concrete number in bold.

   ![Main screenshot](assets/overview.png)

   ## What it answers (or: What it does)
   ## Open it yourself (or: How to run it)
   ## Credit          (only if something needs crediting; one line)
   ```

4. Create the repo on GitHub, public and empty (no README, license, or gitignore, so nothing collides), then push:

   ```
   cd project-name
   git init -b main
   git add -A
   git commit -m "Project Name: first public version"
   git remote add origin https://github.com/Spendry/project-name.git
   git push -u origin main
   ```

5. Fill in the repo description on GitHub; it shows in search results and on pinned cards.

## Wiring it into the hub (this repo)

Two edits, then commit:

1. **README.md**: add a row to the matching section's table:

   ```
   | Project Name | What it is | What it shows | [repo](https://github.com/Spendry/project-name) |
   ```

2. **projects/&lt;section&gt;.md**: add a block:

   ```markdown
   ## Project Name

   Two or three sentences on what it is and why it matters.

   - **Repo:** https://github.com/Spendry/project-name
   - **Shows:** the skills, comma-separated.
   ```

   Optional: put one screenshot in this repo's `assets/` and embed it from the case-study file with `![alt](../assets/project-name-view.png)`.

3. Commit and push:

   ```
   git add .
   git commit -m "Add Project Name to the index"
   git push
   ```

## Updating the profile page

If the new project belongs in the shop window, edit the README in `Spendry/Spendry`: add or swap a row in the "A few things I've built" table. Rows without a live repo stay plain text, marked "(repo coming soon)", so the table holds no dead links. Then check the pinned repos on the profile: six slots, strongest and widest range first.

## Adding a certificate

Edit [certificates/README.md](certificates/README.md): add a table row, newest first, with the **issuer's verification URL** in the verify cell. Only add the PDF itself when a local copy matters; the verification link carries the weight.

## Verify before walking away

- Click the new hub table row and confirm it lands on the project repo.
- Click the project's back-link and confirm it lands back on this hub.
- Confirm images render on GitHub (paths are case-sensitive: `assets/Overview.png` is not `assets/overview.png`).
- Confirm no `_link_` placeholders or `(#)` stubs remain in any file you touched.
- Confirm nothing private or uncredited went out.

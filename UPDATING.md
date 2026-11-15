# Updating your website

Everything below can be done directly on GitHub in your browser: open the file, click the pencil icon (✏️) to edit, then click **Commit changes**. To upload a file, open the folder, click **Add file → Upload files**, then commit.

Every commit to `main` republishes the site automatically, usually within about two minutes. If something doesn't appear, open the repository's **Actions** tab: a red ✗ means the build failed, and clicking it shows why (most often a YAML indentation slip).

A note on YAML files (`data/*.yaml`, `hugo.yaml`): indentation matters. Use spaces, never tabs, and line new entries up exactly with the existing ones. Put text that contains a colon inside double quotes.

---

## 1. Add a new paper

1. If you have a PDF, upload it to `static/files/` (e.g. `static/files/Ma_new-paper.pdf`).
2. Open `data/papers.yaml` and add an entry where you want it to appear (papers show in the order listed):

```yaml
- title: "Title of the New Paper"
  coauthors: ["First Coauthor", "Second Coauthor"]   # or [] if solo
  version: "December 2026"                            # optional
  status: "working paper"
  venue: ""
  pdf: "files/Ma_new-paper.pdf"                       # or "" if no PDF yet
  link: ""                                            # optional: SSRN, NBER, DOI
  job_market_paper: false
  abstract: >-
    One-paragraph abstract goes here. It can run over
    several lines as long as each line is indented.
```

Status options: `published`, `accepted`, `revise and resubmit`, `under review`, `working paper`, `work in progress`.

## 2. Add a PDF to an existing paper

Upload the PDF to `static/files/`, then set that paper's `pdf:` line in `data/papers.yaml`, e.g. `pdf: "files/Ma_foreign-dollar-bonds.pdf"`. The paper's title becomes a link and a **Paper** button appears.

## 3. Update your job market paper

Upload the new version to `static/files/Ma_JMP.pdf` (same name, so the link doesn't change), then update `title:` and `abstract:` on the entry with `job_market_paper: true` if they changed. To show a "Latest version: …" line under the title, add `version: "Month Year"` to that entry.

## 4. Mark a paper as published

In `data/papers.yaml`, change its `status` to `"published"` (or `"accepted"`), fill in `venue: "Journal Name"` and `year: 2027`, and add the journal link under `link:`. Published papers move to a **Publications** heading automatically.

## 5. Update your bio

Edit `content/_index.md`. Everything below the second `---` line is the text at the top of the homepage. Write **bold** with double asterisks and links as `[text](https://example.com)`.

## 6. Update your CV

Upload the new file to `static/files/` with the name `cv.pdf` (replacing the old one). Keep the same name so every link keeps working.

## 7. Add or change your photo

Upload a headshot (JPEG, roughly 600 × 750 pixels) as `static/images/photo.jpg`, then in `hugo.yaml` set:

```yaml
  photo: "images/photo.jpg"
```

To remove the photo, set it back to `photo: ""`.

## 8. Change your email or links

- Email, LinkedIn, title, institution: `hugo.yaml` under `params:`
- Add Google Scholar or GitHub: add `scholar: "https://..."` or `github: "https://..."` under `params:` in `hugo.yaml`; a button appears in the sidebar.

## 9. Add a new section or a blog post

The simplest route is to ask your AI assistant, e.g. "Add a Teaching section to my site with these courses: …" or "Add a blog post titled … with this text: …". By hand, a blog post is a new file `content/blog/your-post-slug/index.md` starting with:

```yaml
---
title: "Post Title"
date: 2026-12-01
description: "One-sentence summary."
---
```

## 10. Change the site address

If you rename the repository to `<your-username>.github.io` or add a custom domain, change the single `baseURL:` line at the top of `hugo.yaml` to the new `https://` address.

## 11. Change the look of the site

Colors and fonts are set at the top of `assets/css/style.css` (the `:root` block holds the palette). For a full redesign, ask your assistant to run the design quest at https://gking.harvard.edu/mysite/files/QUEST_DESIGN.md and show you three previews. The current look is recorded in `hugo.yaml` under `params.mysite.design`.

## 12. Footer credit and invisible marker

Both are currently off (`credit: false`, `discovery: false` under `params.mysite` in `hugo.yaml`). Set either to `true` to turn it on.

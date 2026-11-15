# John Zijian Ma — personal website

Source for my academic website, built with [Hugo](https://gohugo.io/) and published by GitHub Pages.

- **Live site:** the address set as `baseURL` in `hugo.yaml`
- **How to make changes:** see [UPDATING.md](UPDATING.md)

## What lives where

| What | File |
|------|------|
| Name, title, email, links | `hugo.yaml` |
| Bio (top of the homepage) | `content/_index.md` |
| Papers | `data/papers.yaml` |
| CV and paper PDFs | `static/files/` |
| Photo | `static/images/` |
| Colors, fonts, layout | `assets/css/style.css` |
| Page templates | `layouts/` |

Every push to `main` rebuilds and republishes the site through `.github/workflows/deploy.yml`.

## Preview locally (optional)

Install Hugo extended (`brew install hugo` on macOS), then run `hugo server` in this folder and open http://localhost:1313.

The Lato font files in `static/fonts/` are under the SIL Open Font License (`static/fonts/OFL-LICENSE.txt`).

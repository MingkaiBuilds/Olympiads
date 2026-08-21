# Olympiads

IMO and IPhO problem-solving in public. Daily puzzles live on the board.

Live site (GitHub Pages project site): [https://mingkaibuilds.github.io/Olympiads/](https://mingkaibuilds.github.io/Olympiads/)

This repository *is* the website. It is not a page on the personal hub, autonoetics, Frontiers, or Thinking.

## What is here

- **Home** — states IMO and IPhO; shows the current board
- **Board** — two slots, Mathematics / IMO and Physics / IPhO, structured so a problem can be posted later
- **Math** and **Physics** — track pages
- **Archive** — empty until the first problem is posted
- **How** — a problem is posted; a writeup appears later only if it earns one

The shell does not invent problem statements, answers, or writeups. Empty slots stay empty.

## Base path

All asset and navigation links are rooted at `/Olympiads/` so they resolve on the project Pages URL, the same pattern as Frontiers at `/Frontiers`.

## Deploy

Static HTML and CSS. A GitHub Actions workflow (`.github/workflows/deploy.yml`) builds an artifact and deploys it with GitHub Pages.

On the first merge to `main`, the workflow should register the Pages site (`configure-pages` + `deploy-pages`). If the site is not live after that:

1. Repo **Settings → Pages**
2. Source: **GitHub Actions**
3. Re-run the **Deploy Olympiads to GitHub Pages** workflow

## Local preview

Serve the files under the `/Olympiads/` prefix:

```bash
mkdir -p /tmp/olympiads-preview/Olympiads
cp -a index.html 404.html favicon.svg assets board math physics archive how /tmp/olympiads-preview/Olympiads/
python3 -m http.server --directory /tmp/olympiads-preview 8080
```

Then open `http://127.0.0.1:8080/Olympiads/`.

## Posting a problem later

Fill the reserved slot on `board/index.html` (and the matching track page). Move the previous current problem into `archive/index.html`. Do not add a writeup unless the problem earns one.

## Author

Mikail Stewart / Mingkai / 明凯 · Princeton CS ’27

Optional contact: [ms3554@princeton.edu](mailto:ms3554@princeton.edu) · [GitHub/MingkaiBuilds](https://github.com/MingkaiBuilds)

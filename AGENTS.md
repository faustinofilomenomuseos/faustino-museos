# AGENTS

## Repo shape (verified)
- This repo is a plain static site with only two HTML files: `index.html` and `louvre.html`.
- There is no package manager, build step, test suite, lint config, CI workflow, or task runner in the repo.
- All styling and JavaScript are inline inside each HTML file (no shared CSS/JS files).

## Safe way to run/check
- Serve locally with any static server from repo root (for example `python -m http.server 8000`) and open `http://localhost:8000/`.
- Prefer browser/manual verification after edits; there are no automated checks to rely on.

## Coupling and gotchas
- `index.html` renders the museum cards from the inline `MUSEOS` array and links each card to `museos/${id}.html`.
- `louvre.html` currently lives at repo root and its nav links use `../index.html` and `../index.html#museos`, which only work if the page is actually under a `museos/` subfolder.
- If you add or move museum pages, keep `index.html` link generation and each detail page back-links in sync.
- `index.html` fetches YouTube data with an inline API key (`YT_KEY`); do not rotate/remove casually unless also updating the fallback behavior.

## Editing conventions already in use
- Site content is Spanish (`lang="es"`); keep new copy and UI text in Spanish unless explicitly asked otherwise.
- Preserve existing visual direction (color variables, Playfair/DM Sans/Bebas Neue typography, gold/cream/black palette) unless a redesign is requested.

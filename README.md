# Nashim Rahman — Personal Portfolio

A static, retro academic-style personal homepage (HTML/CSS/vanilla JS, no build step, no backend).

## Run it locally

No build tools needed. Either:

- Just double-click `index.html` to open it in a browser, **or**
- Run a tiny local server (recommended, avoids some browser file:// quirks):

  ```bash
  cd portfolio
  python3 -m http.server 8000
  ```

  Then open http://localhost:8000 in your browser.

## Deploy

**GitHub Pages**
1. Push this folder to a GitHub repo.
2. Repo Settings → Pages → set source to the `main` branch, root folder.
3. Your site will be live at `https://<username>.github.io/<repo>/`.

**Vercel**
1. `vercel` CLI: run `vercel` inside this folder and follow the prompts.
2. Or import the GitHub repo at vercel.com/new — no build command needed, it's static.

## Files you need to edit

| What | File | What to change |
|---|---|---|
| Profile photo | `assets/profile.jpg` | Replace with your own photo (square works best) |
| Email | `index.html` | Search for `your.email@example.com` (appears in sidebar + Contact section) |
| LinkedIn | `index.html` | Search for `your-linkedin-url` and the `href="#"` next to it |
| Resume | add `resume.pdf` at the project root | The "Download Resume" link already points to `/resume.pdf` |
| Project links | `index.html` | GitHub / Live Demo links are already filled in under Projects |

All of the above are also marked with `<!-- EDIT HERE -->` comments directly in `index.html`.

## Notes on what was built

- Seven separate HTML pages (`index.html`, `about.html`, `skills.html`, `projects.html`, `education.html`, `certifications.html`, `contact.html`), each a full page load rather than an in-page anchor.
- The sidebar, top navigation, and footer are repeated on every page (plain HTML — no templating), so each page is self-contained and works if opened directly.
- The current page's nav link gets an `active` class (a slightly heavier underline) as a subtle "you are here" indicator — no color or background change.
- One shared `style.css` keeps the look consistent: lime-green background, dark green headings/nav, thin gray rules, no cards/gradients/shadows.
- `script.js` is intentionally minimal — with separate pages there's no scroll-triggered behavior left to do in JS; it's kept as a place to add small touches later.
- On mobile/tablet the sidebar stacks above the content instead of switching to a different visual style.

## If you'd rather not repeat the sidebar in 7 files

Right now each page's sidebar/nav/footer is duplicated HTML, which is the simplest possible static setup and matches what was asked for. If later you'd prefer a single source of truth (so editing your email once updates all 7 pages), that would mean adding a tiny build step or a JS include — happy to set that up if you want it, but it wasn't part of this version on purpose.

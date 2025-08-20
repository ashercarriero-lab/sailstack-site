# Sailstack — AI Agent Consulting for Realtors

Static one-page site built with Tailwind via CDN and Font Awesome icons.

## Files
- `index.html` — your site (drop-in ready for GitHub Pages)
- `.gitignore` — ignores common local files

## Local preview
Just open `index.html` in your browser.

## Publish to GitHub
1. Create a new empty GitHub repo (e.g., `sailstack-site`).
2. In a terminal:
   ```bash
   cd path/to/sailstack-site
   git init
   git add .
   git commit -m "Initial commit: Sailstack static site"
   git branch -M main
   git remote add origin https://github.com/<YOUR-USERNAME>/sailstack-site.git
   git push -u origin main
   ```

## Enable GitHub Pages (optional)
- On GitHub: Settings → Pages → Build and deployment → Source: **Deploy from a branch** → Branch: **main** / **root**.
- The site will be served at the Pages URL GitHub shows.

## Notes
- Contact form currently uses a `mailto:` action, which opens the user’s email client.
- Tailwind and Font Awesome are loaded from CDNs; no build step required.

# moiz_ai_website

Static website (plain HTML/CSS/JS, no build step), deployed with GitHub + Cloudflare Pages.

- English: `/index.html`, `platform.html`, `use-cases.html`, `pricing.html`, `contact.html`
- English: the same pages under `/en/`
- Shared design kit: `/assets`

## Local preview
```
python3 -m http.server 8000
```
Open http://localhost:8000 (Dutch, the default) or http://localhost:8000/en/index.html (English).

## Deploy (Cloudflare Pages + GitHub)
1. `git push origin main`
2. Cloudflare dashboard → Workers & Pages → Create → Pages → Connect to Git → `moiz_ai_website`, branch `main`.
3. Framework preset: None · Build command: empty · Build output directory: `/`.
4. Every push to `main` redeploys. Custom domain: project → Custom domains.

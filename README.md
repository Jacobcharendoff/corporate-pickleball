# Corporate Pickleball — Marketing Site

White-glove pickleball events for Bay Street, built across the GTA.
Static three-page marketing site. Pure HTML/CSS/JS. No build step.

## Pages

- `index.html` — home / landing
- `toronto-open.html` — flagship event page (The Bay Street Cup)
- `book.html` — booking configurator with live pricing

## Imagery

Hero and SKU imagery is rendered on demand via Pollinations.ai Flux URLs
embedded directly in `<img>` tags. First page-view triggers generation
(10–30s per image). Cached by deterministic seed thereafter.

To swap any image for a real photograph, replace the `src` URL on the
relevant `<img>` tag — no other changes needed.

## Local preview

Just open `index.html` in a browser, or run a tiny static server:

```sh
python3 -m http.server 8000
# → http://localhost:8000
```

## Deploy (Vercel)

```sh
npx vercel        # preview deploy
npx vercel --prod # production deploy
```

`vercel.json` is configured for clean URLs (`/book` instead of `/book.html`).

## Custom domain

Buy a domain (Namecheap / Cloudflare / Porkbun), then in Vercel:
**Project → Settings → Domains → Add**. Point a single A record at Vercel
per the instructions they show. SSL provisions automatically.

Suggested domains: `cp.club`, `corporatepickleball.club`, `corporatepickleball.ca`.

# Witch Hat Atelier Fan Merch Showcase

This is a simple static site showcasing fan-picked Witch Hat Atelier merch.

Files added/updated:
- `index.html` — homepage (fan-curated picks)
- `database.html` — a searchable and filterable database page for merch
- `styles.css` — styles (updated theme to white/black/teal/yellow)
- `data/products.json` — sample product data used by `database.html` (includes `type` and `characters` fields)

How to test locally (recommended):

PowerShell (Windows):

```powershell
# from the project root
python -m http.server 8000; # then open http://localhost:8000 in your browser
```

Or using Node's http-server:

```powershell
npx http-server -p 8000
```

Notes:
- `database.html` fetches `data/products.json` client-side, so you should serve the site via a local server to avoid file CORS limitations.
- Add or edit entries in `data/products.json` to update the database. Each product should include: id, name, type, characters (array of names), price, image, description, note, buy_link.
 - The `database.html` page supports filtering by `type` and by `characters` (e.g., Qifrey, Olruggio, Coco, Agott, Richeh, Knights Moralis, Brimmed Hats, Others). You can add these to products in `data/products.json`.

Troubleshooting: JSON changes don't appear on the site
- If you edit `data/products.json` and the site doesn't show your changes, try the following steps:
	1. Ensure you pushed the commit to the branch that your site uses (for GitHub Pages, usually the `main` branch or `gh-pages`).
	2. Wait for deployment to finish if your hosting uses a build step; GitHub Pages or Netlify may take a minute.
	3. Hard-refresh the page (Ctrl+F5) or open in a private/incognito window to bypass browser cache.
	4. If your host caches static assets (CDN), try adding a query parameter to the file path (or use the reload button on the database page).
	5. The database page includes a "Reload Data" button which fetches `data/products.json` with a cache-busting timestamp (this helps bypass CDN/browser caches for quick testing).

If you still don't see updates after these steps, tell me which hosting service you use and I can help investigate further (CI build logs, branch settings, or cache rules).

If you'd like, I can:
- Add categories or advanced filters (price ranges, in-stock), or
- Wire the page to a small CMS or create a simple admin interface to update the JSON.

Enjoy — let me know what to add next!
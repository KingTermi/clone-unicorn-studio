# unicorn.studio

Static website for **unicorn.studio** — multi-page site, fully autonomous (offline-capable), agency-grade structure.

> Cloned from [https://unicorn.studio](https://unicorn.studio) — see `_meta.json` for the manifest.

## 🚀 Quick start

```bash
# Local dev server
npm run dev
# → http://localhost:4242

# Or any static server
python3 -m http.server 4242
npx serve -l 4242 .
```

## 📁 Structure

```
.
├── index.html              Homepage
├── 404.html                Error page
├── robots.txt              SEO crawler directives
├── sitemap.xml             SEO sitemap (0 URLs)
├── favicon.ico             Site icon
├── package.json            NPM scripts (dev, deploy)
├── netlify.toml            Netlify config (cache headers, redirects)
├── vercel.json             Vercel config (clean URLs, headers)
├── .editorconfig           Editor consistency
├── .prettierrc             Code formatting
├── .gitignore
│
├── <page>/index.html       Top-level pages (clean URLs: /pricing/, /about/)
├── <section>/<page>/index.html  Nested pages (auth/login/, blog/post-slug/)
│
├── images/                 PNG, JPG, SVG, WebP, AVIF, ICO
├── fonts/                  WOFF2, WOFF, TTF, OTF
├── styles/                 CSS files (with rebased asset URLs)
├── scripts/                JS runtime (jQuery, GSAP, Webflow, etc.)
├── media/                  MP4, WebM, MP3
└── docs/                   PDF
```

## 🌐 Deploy

### Netlify
```bash
npm run deploy:netlify
```

### Vercel
```bash
npm run deploy:vercel
```

### GitHub Pages
Settings → Pages → Source: `main` branch, root folder.

### Any other host (S3, Cloudflare Pages, Render, Fly, etc.)
Just upload the entire folder. All paths are **relative**.

## ✅ What's preserved

- ✅ Full multi-page navigation with **clean URLs** (`/auth/login/` → `auth/login/index.html`)
- ✅ Runtime JS for **dropdowns, carrousels, animations** (jQuery, GSAP, Swiper, etc.)
- ✅ All **fonts and images locally** (offline-capable)
- ✅ **CSS rebased** to use local asset paths
- ✅ **JSON-LD** preserved for SEO

## 🚫 What's stripped

- ❌ Trackers and analytics (GTM, GA, Facebook Pixel, PostHog, etc.)
- ❌ `integrity` and `crossorigin` (CSS/JS modified, hash mismatch)
- ❌ `<base>`, CSP, meta-refresh (would break offline)
- ❌ `hreflang` (not relevant for static clone)

## 📊 Stats

- **0** pages
- **1** errors (see `_meta.json`)

## Notes

- Iframes tiers (vidéos embed, consent banners) restent online — pas téléchargeables.
- Pour personnaliser le rendu : éditer les fichiers HTML directement, ou les CSS dans `styles/`.

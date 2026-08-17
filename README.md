# ION Orchard Dine Directory — Doraemon Edition

A single-page, Doraemon-themed food directory for ION Orchard (Singapore), with cuisine + price filters, sample Google-style ratings, Google Maps links, one-tap reservation calling, and two "4D Pocket" randomiser buttons for picking a restaurant (or cuisine) at random.

## What's in this folder
- `public/index.html` — the entire site (HTML/CSS/JS, no build step, no dependencies)
- `vercel.json` — Vercel config (static site served from `public/`)
- `package.json` — minimal metadata so Vercel recognizes it as a static project

## Deploy: GitHub → Vercel

### 1. Push this folder to GitHub
```bash
cd ion-dine-directory
git init
git add .
git commit -m "Initial commit: ION Orchard dine directory"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```
(Create the empty repo on GitHub first at https://github.com/new — don't initialize it with a README, since this folder already has one.)

### 2. Import into Vercel
1. Go to https://vercel.com/new
2. Click **Import Git Repository** and select the repo you just pushed
3. Framework preset: choose **Other**
4. Output Directory: `public` (already set via `vercel.json`, but double-check in Project Settings → Build & Development Settings if it still fails)
5. Click **Deploy**

Vercel will give you a live URL like `https://your-repo-name.vercel.app` within seconds.

### If you hit "No Output Directory named X found"
Go to your Vercel project → **Settings → Build & Development Settings → Output Directory**, toggle **Override** on, and set it to `public` (matching this repo's structure). Then redeploy.

### 3. (Optional) Custom domain
In the Vercel project → **Settings → Domains**, add your own domain and follow the DNS instructions shown.

## Local preview
No build tools needed — just open `public/index.html` in a browser, or run:
```bash
npx serve public
```

## Notes on the data
Store list, units, and cuisines were compiled from ION Orchard's public directory and dining guides for illustrative purposes. Ratings/review counts are styled sample placeholders (not live Google data) — to pull real reviews, connect the Google Places API (Place Details request, `reviews` field) server-side and swap the static `stores` array in `index.html` for a fetch to your own API route.

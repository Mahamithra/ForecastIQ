# ForecastIQ Dashboard — Vercel-ready

This is `ForecastIQ.jsx` from the hackathon submission, wrapped in a real,
buildable Vite + React project so it deploys on Vercel with zero config.

## What changed from the original file
- Added the missing project scaffold: `package.json`, `vite.config.js`,
  `index.html`, `src/main.jsx`.
- Added Tailwind via the CDN script in `index.html` (the component uses
  Tailwind utility classes for layout).
- Replaced the `window.storage` calls (a Claude-artifact-only API that
  doesn't exist in a real browser) with `localStorage`, so login/signup
  works as a local, browser-only demo auth. This is **not** a real backend —
  accounts live only in each visitor's own browser. Swap `dbGetUser` /
  `dbSaveUser` in `src/App.jsx` for real API calls if you want shared,
  server-side accounts.

Note: this is the "bonus" dashboard only — it shows mock/demo data, not
live output from `src/predict.py`. The Python pipeline (`run.sh`) is a
separate, non-web batch script and isn't wired into this frontend.

## Deploy on Vercel

**Option A — Vercel dashboard**
1. Push this folder to a GitHub repo.
2. Go to vercel.com → New Project → import the repo.
3. Vercel auto-detects Vite. Leave defaults (Build: `npm run build`,
   Output: `dist`) and click Deploy.

**Option B — Vercel CLI**
```bash
npm i -g vercel
cd forecastiq-vercel
vercel        # preview deploy
vercel --prod # production deploy
```

## Run locally
```bash
npm install
npm run dev
```

# Sentiment Analyzer — B.Tech AI/ML Project

Sentiment classification app (TF-IDF + Logistic Regression, trained on SST-2 via Hugging Face Datasets).
Model weights are embedded in `src/App.jsx` — all inference runs client-side, no backend required.

## Run locally

```
npm install
npm run dev
```

Opens at `http://localhost:5173`.

## Build for production

```
npm run build
```

Output goes to `dist/`.

## Deploy — Vercel (recommended, easiest)

1. Push this folder to a GitHub repository.
2. Go to [vercel.com](https://vercel.com), sign in with GitHub.
3. Click **Add New → Project**, select this repo.
4. Framework preset: Vite (auto-detected). Leave build settings as default.
5. Click **Deploy**. Live in about a minute at `your-project.vercel.app`.

## Deploy — Netlify (alternative)

1. Push this folder to GitHub.
2. Go to [netlify.com](https://netlify.com) → **Add new site → Import an existing project**.
3. Connect the repo. Build command: `npm run build`. Publish directory: `dist`.
4. Deploy.

## Deploy — GitHub Pages

1. Install the GH Pages helper: `npm install --save-dev gh-pages`
2. Add to `package.json` scripts: `"deploy": "vite build && gh-pages -d dist"`
3. In `vite.config.js`, add `base: "/your-repo-name/"` inside `defineConfig({ ... })`.
4. Run `npm run deploy`. Site goes live at `https://your-username.github.io/your-repo-name/`.

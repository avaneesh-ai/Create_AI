# Create_AI — GitHub Pages deploy

These are the exact files to push to a GitHub repo to put the site live.

## Files here
- `index.html`       — entry point
- `assets/`          — compiled CSS + JS
- `.nojekyll`        — tells GitHub Pages to serve all files as-is (don't delete)

## Steps (web, no terminal needed)
1. On github.com, create a new repository (e.g. `create-ai`). Make it Public.
2. Click **Add file → Upload files**, drag in `index.html`, the `assets` folder, and `.nojekyll`, then **Commit**.
3. Go to **Settings → Pages**.
4. Under **Source**, choose **Deploy from a branch**. Branch: **main**, folder: **/ (root)**. Click **Save**.
5. Wait ~1 minute. Your site is live at:
   `https://<your-username>.github.io/<repo-name>/`

Asset paths are relative, so it works at that sub-path automatically.

## Steps (terminal, if you prefer)
```
git init
git add .
git commit -m "Create_AI site"
git branch -M main
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin main
```
Then enable Pages as in step 3–4 above.

## Important: the AI features
GitHub Pages only hosts static files — it CANNOT run the `/api/messages` backend,
so the Chatbot and App Builder will show an error on Pages. The login/UI all work.

To enable AI, host just the backend somewhere that runs functions (Vercel free tier),
then rebuild the site with that URL:
  `VITE_API_URL=https://your-backend.vercel.app/api/messages npm run build`
and push the new `dist` files. (Ask me and I'll set this up for you.)

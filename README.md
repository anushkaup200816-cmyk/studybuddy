# Pixel Study Buddy — Preview & Deploy

This repo contains a tiny static site in `public/` (public/index.html).

Local preview
1. Install http-server (no global install required):
   - Run: `npm install` (not strictly required, we use npx)
2. Start preview server:
   - `npm start`
3. Open: http://localhost:5000

Deploy to GitHub Pages (production)
- The workflow `.github/workflows/deploy.yml` runs on push to `main` and publishes the `public/` folder to the `gh-pages` branch.
- After the first successful run, your Pages site will be available at:
  `https://<your-github-username>.github.io/<your-repo>/`

Enable PR preview deploys (recommended)
- For automatic preview URLs for every pull request use Vercel:
  1. Create an account at https://vercel.com and connect your GitHub account.
  2. Import your repo.
  3. Set the build settings:
     - Framework Preset: Other (static)
     - Build Command: (leave blank)
     - Output Directory: `public`
  4. Vercel will create a preview deploy for every PR and deploy to production when you merge to main.

Notes
- If you later add a bundler (Vite/Next/etc.), update the workflow to run the build step and publish the build output directory instead of `public`.
- To use a custom domain, add the domain in GitHub Pages settings or in Vercel settings as needed.
# asdforge.com

Landing page for ASD Forge — a studio by Jared Arnold, Ian Switzer, and Joshua Devine. Built with [Astro](https://astro.build) and deployed to GitHub Pages.

## Development

```bash
npm install
npm run dev       # http://localhost:4322
```

Other commands:

```bash
npm run build     # production build → dist/
npm run preview   # preview production build locally
npm run lint      # eslint
npm run format    # prettier
```

## Deploying to GitHub Pages

Deployment is automatic via GitHub Actions on every push to `main`. The workflow (`.github/workflows/deploy.yml`) lints, builds, and uploads the `dist/` directory as a Pages artifact.

To enable it on a new repository:

1. Go to **Settings → Pages**
2. Set **Source** to **GitHub Actions**
3. Push to `main` — the site will deploy automatically

## Custom Domain

The `public/CNAME` file is set to `asdforge.com`. To activate it:

1. Go to **Settings → Pages → Custom domain** and enter `asdforge.com`
2. Add the following DNS records with your registrar:

   **Apex domain (`asdforge.com`)** — add all four A records:
   ```
   A  @  185.199.108.153
   A  @  185.199.109.153
   A  @  185.199.110.153
   A  @  185.199.111.153
   ```

   **www subdomain** — add a CNAME record:
   ```
   CNAME  www  asdforge.com
   ```

3. Wait for DNS to propagate (minutes to a few hours)
4. Check **Enforce HTTPS** in Settings → Pages once the domain is verified

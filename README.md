# mynegy-site

Marketing landing page and hosted legal pages for **Mynegy**, served via GitHub Pages at
`https://mynegy.com`.

## Structure

```
index.html          Landing page
styles.css          Shared styles
privacy/index.html  Privacy Policy   -> https://mynegy.com/privacy
terms/index.html    Terms & EULA     -> https://mynegy.com/terms
CNAME               Custom domain (mynegy.com)
.nojekyll           Serve files as-is (no Jekyll processing)
```

The legal pages live in folders (`privacy/index.html`) so they resolve at clean, extensionless URLs
(`/privacy`, `/terms`) — these are the URLs to enter in App Store Connect / Google Play Console.

## Deploy (GitHub Pages)

1. Create a GitHub repo (e.g. `mynegy-site`) and push these files to the default branch.
2. Repo **Settings → Pages** → Source: *Deploy from a branch* → branch `main` / root.
3. Under **Custom domain** enter `mynegy.com` (the `CNAME` file already sets this).
4. At your DNS provider, point the apex `mynegy.com` at GitHub Pages:
   - A records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - (optional) `CNAME` for `www` → `<your-username>.github.io`
5. Wait for DNS + enable **Enforce HTTPS** in the Pages settings.

## Editing

- Keep the hosted Privacy Policy in sync with the in-app copy at `app/legal/privacy.tsx` in the
  Mynegy app repo, and the Terms in sync with `app/legal/terms.tsx`.
- Update the "Get Mynegy" / App Store links in `index.html` once store listings are live.

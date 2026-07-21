# Gemr — Legal & Support site

Static pages for the App Store submission: Privacy Policy, Terms of Use (EULA), and Support. Plain HTML, no build step.

## Files

- `index.html` — hub linking to the three pages
- `privacy.html` — Privacy Policy (中文 + English)
- `terms.html` — Terms of Use / EULA (中文 + English)
- `support.html` — Support page + FAQ (中文 + English)
- `.nojekyll` — tells GitHub Pages to serve the files as-is

## Publish on GitHub Pages (web UI, ~3 minutes)

1. Go to <https://github.com/new> and create a **public** repository named **`gemr-legal`** (public is required so Apple and users can open the URLs; private-repo Pages needs a paid plan).
2. On the new repo page, click **uploading an existing file**, then drag in all files from this folder (`index.html`, `privacy.html`, `terms.html`, `support.html`, `.nojekyll`, `README.md`). Commit.
3. Go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**. Set **Branch = `main`**, **Folder = `/ (root)`**, then **Save**.
5. Wait ~1 minute, then reload the Pages settings screen — it will show **"Your site is live at …"**.

### Your URLs (username `ctwu95-hub`, repo `gemr-legal`)

- Home: `https://ctwu95-hub.github.io/gemr-legal/`
- **Privacy Policy:** `https://ctwu95-hub.github.io/gemr-legal/privacy.html`
- **Terms of Use (EULA):** `https://ctwu95-hub.github.io/gemr-legal/terms.html`
- **Support:** `https://ctwu95-hub.github.io/gemr-legal/support.html`

> If you use a different repo or username, adjust the URLs to match — and tell me, because the same two URLs are hard-coded into the app's paywall (`PaywallView.termsURL` / `PaywallView.privacyURL`). They must match exactly.

## Publish via git CLI (alternative)

```bash
cd gemr-legal
git init
git add .
git commit -m "Gemr legal & support pages"
git branch -M main
git remote add origin https://github.com/ctwu95-hub/gemr-legal.git
git push -u origin main
# then enable Pages in Settings → Pages as in step 3–4 above
```

## Before you submit — verify

- [ ] Open all three URLs in a browser; each loads and shows both 中文 and English.
- [ ] The two URLs in `PaywallView.swift` (`termsURL`, `privacyURL`) exactly match the live Pages URLs.
- [ ] In the app's upgrade screen, the **使用條款 (EULA)** and **隱私政策** links open these pages.

Full submission steps are in **`../Gemr-AppStoreConnect-Guide.md`**.

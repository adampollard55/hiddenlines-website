# Go Live Checklist — hiddenlines.app

When you're ready to submit the app to the App Store, follow these steps to make the website live.

## Before going live

- [ ] App Store screenshots added to `website/screenshots/` (1.png, 2.png, etc.)
- [ ] Screenshot `<img>` tags uncommented in `website/index.html`
- [ ] App Store URL replaced in CTA button (`href="#"` → real URL)
- [ ] Copy review session completed (all text finalized)

## Enable GitHub Pages

1. Go to **github.com → climbing-app repo → Settings → Pages**
2. Under **Source**, select **GitHub Actions**
3. Under **Custom domain**, enter `hiddenlines.app`
4. Click **Save**

## Configure DNS (GoDaddy)

Add these DNS records at your domain registrar:

### A Records (point apex domain to GitHub Pages)

| Type | Name | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

### CNAME Record (point www to GitHub Pages)

| Type | Name | Value |
|------|------|-------|
| CNAME | www | adampollard55.github.io |

## After DNS propagation (~30 minutes)

1. Go back to **Settings → Pages** in the repo
2. Check **Enforce HTTPS** (should be available once DNS is verified)
3. Push any change to `website/` to trigger the deploy workflow
4. Visit `https://hiddenlines.app` to verify

## Verify

- [ ] `https://hiddenlines.app` loads with HTTPS
- [ ] `https://hiddenlines.app/privacy/` loads correctly
- [ ] App Store CTA button links to the real listing
- [ ] Screenshots display correctly
- [ ] OG tags work (paste URL into Discord/Slack to check preview)

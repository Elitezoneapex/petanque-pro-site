# Deploying the Pétanque Pro support site

You have three pages ready to host: `index.html`, `privacy.html`, `support.html` + `styles.css`. Pick whichever option you like — all are free and Apple-acceptable.

---

## Option A — Netlify Drop (fastest, ~2 minutes)

No account, no git, no CLI.

1. Go to https://app.netlify.com/drop
2. Drag the entire `AppStore/site/` folder onto the page
3. Netlify gives you a URL like `https://random-name-12345.netlify.app`
4. (Optional) Sign up for free to claim the site and rename it to e.g. `petanque-pro.netlify.app`

**Your URLs become:**
- Privacy: `https://YOUR-SITE.netlify.app/privacy.html`
- Support: `https://YOUR-SITE.netlify.app/support.html`

---

## Option B — GitHub Pages (~10 minutes, free, your domain)

1. Create a new public repo on GitHub, e.g. `petanque-pro-site`
2. From this directory:
   ```bash
   cd "AppStore/site"
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/petanque-pro-site.git
   git push -u origin main
   ```
3. On GitHub: Settings → Pages → Source: `main` branch, `/ (root)` folder → Save
4. Wait ~1 minute. Your site is live at `https://YOUR_USERNAME.github.io/petanque-pro-site/`

**Your URLs become:**
- Privacy: `https://YOUR_USERNAME.github.io/petanque-pro-site/privacy.html`
- Support: `https://YOUR_USERNAME.github.io/petanque-pro-site/support.html`

---

## Option C — Custom domain (later, $10-15/yr)

If you own `elitezoneapex.com` or want to buy it:

1. Buy from Namecheap/Cloudflare/Porkbun
2. Point DNS to Netlify or GitHub Pages (instructions on each platform)
3. URLs become e.g. `elitezoneapex.com/petanque/privacy`

This can wait until after launch — Apple is fine with any of the above.

---

## After deploying

1. Open both URLs in a browser to confirm they load and the FR/EN toggle works
2. Save the URLs in a note — you'll paste them into App Store Connect:
   - **App Information → Privacy Policy URL** (REQUIRED)
   - **App Information → Support URL** (REQUIRED)
   - **App Information → Marketing URL** (optional — use the index.html)
3. Update `01_descriptions.md` — replace any `[YOUR URL]` placeholders with real URLs

---

## Editing later

The pages are plain HTML. Edit `privacy.html` or `support.html`, redeploy (drag again on Netlify, or `git push` for GitHub Pages). Apple does NOT need a new app submission for content changes — they re-fetch the URLs.

If you change the privacy policy materially, bump the "Last updated" date inside the HTML.

# GitHub Pages site for TikTokClipperBot

This static site exists so TikTok can verify a domain you control, and so your
Privacy Policy / Terms / OAuth redirect live on a real HTTPS URL.

Live URL once published: **https://marvin-gomez-tech.github.io/**

| File           | Serves at                                            | Used in TikTok as     |
|----------------|------------------------------------------------------|-----------------------|
| `index.html`   | `https://marvin-gomez-tech.github.io/`               | Website URL + verify  |
| `privacy.html` | `https://marvin-gomez-tech.github.io/privacy.html`   | Privacy Policy URL    |
| `terms.html`   | `https://marvin-gomez-tech.github.io/terms.html`     | Terms of Service URL  |
| `callback.html`| `https://marvin-gomez-tech.github.io/callback.html`  | Redirect URI          |

## Publish it (one time)

1. Create a **new public repo** named exactly `marvin-gomez-tech.github.io`.
2. Push these four files to its `main` branch. From this folder:
   ```powershell
   git init
   git add .
   git commit -m "TikTokClipperBot site: policies, callback, domain verification"
   git branch -M main
   git remote add origin https://github.com/marvin-gomez-tech/marvin-gomez-tech.github.io.git
   git push -u origin main
   ```
3. On GitHub: repo → **Settings → Pages** → Source = `Deploy from a branch`,
   Branch = `main` / `/ (root)` → Save. Wait ~1–2 min, then open
   `https://marvin-gomez-tech.github.io/` to confirm it's live.

## Verify the domain with TikTok

On TikTok's **Verify URL** screen, pick whichever method it offers:

- **Meta tag:** copy the `content` value TikTok shows, paste it over
  `REPLACE_WITH_TIKTOK_CODE` in `index.html`, commit + push, wait for Pages to
  redeploy, then click **Verify**.
- **File:** download the `tiktokXXXX.txt` file TikTok gives you, drop it in this
  folder, commit + push, then click **Verify**.

## Then, in the TikTok app form

- Website URL  → `https://marvin-gomez-tech.github.io/`
- Privacy URL  → `https://marvin-gomez-tech.github.io/privacy.html`
- Terms URL    → `https://marvin-gomez-tech.github.io/terms.html`
- Redirect URI → `https://marvin-gomez-tech.github.io/callback.html`
  (already set as `TIKTOK_REDIRECT_URI` in the bot's `.env`)

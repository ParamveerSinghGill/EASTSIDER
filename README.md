# EASTSIDER app – put it online (free, about 10 minutes)

This folder is the **installable phone app**. It works on phones signed into several Google accounts (the normal Apps Script link breaks in that case). Your data still goes to the same Google Sheet and Drive.

## 1. Update the Apps Script (once)
1. In Apps Script, replace **Code.gs** with the new `Code.gs`. App.html, Styles.html and Index.html haven't changed.
2. **Deploy → Manage deployments → ✏️ Edit → Version: New version → Deploy.** Keep *Execute as: Me* and *Who has access: Anyone*.
3. Copy the **Web app URL**. It ends in `/exec`.

## 2. Put in your link
Open **config.js** in this folder with Notepad (or any text editor) and replace `PASTE_YOUR_EXEC_LINK_HERE` with your `/exec` link. Keep the quotes:
```js
window.CREWTRACK_API = 'https://script.google.com/macros/s/AKfycb.../exec';
```

## 3. Host it on GitHub Pages (free)
1. Create a free account at **github.com**.
2. Click **+ → New repository**. Name it `crewtrack`, choose **Public**, and click **Create repository**.
3. On the next page, click **"uploading an existing file"**. Drag in **all the files inside this `web` folder** (not the folder itself): `index.html`, `config.js`, `manifest.webmanifest`, `sw.js` and the 4 `.png` icons. Click **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: main**, **/(root)**, then click **Save**.
5. After 1–2 minutes your app is live at:
   **`https://YOUR-GITHUB-NAME.github.io/crewtrack/`**

Send that link to your employees. It's the only link they need.

## 4. Install it on phones
- **Android (Chrome):** open the link. Chrome shows an **"Install app"** banner. If it doesn't, tap **⋮ → Install app** (or **Add to Home screen**).
- **iPhone (Safari):** open the link, tap **Share ↑ → Add to Home Screen → Add**.

EASTSIDER then opens full-screen from its own icon, like any other app.

## Good to know
- The code on GitHub is public, but it contains **no data and no passwords**. Everything stays in your Google Drive, and every screen needs an Employee ID and password.
- **When I send you a code update:** upload the new files to the same GitHub repository (they replace the old ones) and, if Code.gs changed, deploy a new version in Apps Script. Phones pick up the update automatically.
- The original Apps Script link still works too, for example on your own computer.

# 💰 Personal Budget App

A personal savings and budget tracker — PWA installable on iPhone/Android.

---

## 🚀 Deploy to GitHub Pages (5 minutes)

### Step 1 — Push these files to your repo

Make sure your repo contains:
```
index.html
manifest.json
sw.js
icon-192.png
icon-512.png
README.md
```

From your terminal:
```bash
git clone https://github.com/jmedayil/personal-budget-app.git
cd personal-budget-app
# copy all the files here, then:
git add .
git commit -m "Initial budget app"
git push origin main
```

---

### Step 2 — Enable GitHub Pages

1. Go to your repo on GitHub: `github.com/jmedayil/personal-budget-app`
2. Click **Settings** (top tab)
3. Scroll to **Pages** in the left sidebar
4. Under **Source**, select **Deploy from a branch**
5. Set branch to **main**, folder to **/ (root)**
6. Click **Save**

GitHub will give you a URL like:
```
https://jmedayil.github.io/personal-budget-app/
```
(takes ~60 seconds to go live)

---

### Step 3 — Fix the service worker path (important!)

Because GitHub Pages serves from a subdirectory (`/personal-budget-app/`), open `sw.js` and update the ASSETS line:

```js
const ASSETS = [
  "/personal-budget-app/",
  "/personal-budget-app/index.html",
  "/personal-budget-app/manifest.json"
];
```

Also update `manifest.json`:
```json
"start_url": "/personal-budget-app/"
```

Then commit and push again:
```bash
git add sw.js manifest.json
git commit -m "Fix GitHub Pages paths"
git push
```

---

### Step 4 — Install on iPhone as an app

1. Open Safari on your iPhone
2. Go to `https://jmedayil.github.io/personal-budget-app/`
3. Tap the **Share** button (box with arrow pointing up)
4. Scroll down and tap **"Add to Home Screen"**
5. Name it **Budget** → tap **Add**

It will appear on your home screen as a full-screen app with no browser chrome. ✅

---

### Android Install

1. Open Chrome
2. Go to your GitHub Pages URL
3. Tap the **⋮ menu** → **"Add to Home screen"**
4. Tap **Install**

---

## 📱 Features

- **Overview** — accounts, CC balances, Amazon tracker, savings goals
- **Expenses** — log by card (Prime CC, Citi, Chase, Cash) + category
- **Statements** — monthly CC statement with utilization & category breakdown
- **Insights** — smart alerts for Amazon overspending, savings rate, Ally targets

## 💾 Data

All data is stored in your browser's `localStorage` — it stays on your device, never sent anywhere. Data persists between sessions on the same device/browser.

> **Tip:** Don't clear your browser data or you'll lose your history. If you want a backup, use your browser's export/developer tools.

---

## 🔄 Updating the App

When you want to add features, just edit `index.html` and push to GitHub. The service worker will auto-update on next visit.

```bash
git add index.html
git commit -m "Add feature X"
git push
```

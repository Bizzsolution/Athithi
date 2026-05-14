# 🏨 AtithiBook — Single HTML File Edition

**BillBlitz-style simple deployment.** No build, no terminal, no npm. Just upload to GitHub Pages.

---

## 🚀 Quick Deploy (5 minutes)

### STEP 1: Upload to GitHub

1. Go to your `Athithi` repo on GitHub
2. Click **"Add file"** → **"Upload files"**
3. Drag-drop **both files**: `index.html` + `manifest.json`
4. Commit message: `Deploy AtithiBook HTML version`
5. Click **"Commit changes"**

### STEP 2: Enable GitHub Pages

1. In repo, go to **Settings** (top right tab)
2. Left sidebar → **Pages**
3. Source → **Deploy from a branch**
4. Branch → **main** → **/ (root)** → **Save**
5. Wait 1-2 minutes
6. URL appears at top: `https://bizzsolution.github.io/Athithi/`

### STEP 3: Done!

Open the URL on your phone:
- App loads
- Login: `admin` / `admin123`
- Test Aadhaar OCR scanning
- Test all features

### STEP 4: Install on Phone

- Open URL in Chrome
- Menu (3 dots) → **"Add to Home screen"**
- App icon banegi home screen pe

---

## 📂 Files in This Package

| File | Purpose |
|---|---|
| `index.html` | Complete app (React + UI + logic) |
| `manifest.json` | PWA install metadata |

That's it. **2 files total.**

---

## 🛠️ How It Works

This file uses:
- **React 18** loaded from unpkg.com CDN
- **Babel Standalone** transpiles JSX in your browser
- **Tesseract.js** for Aadhaar OCR (also from CDN)

Initial load: ~3-5 seconds (CDN scripts download). After that — fast (cached).

---

## 🔄 Updating the App

To update:
1. Edit `index.html` (e.g. via GitHub web editor)
2. Commit changes
3. GitHub Pages auto-deploys in 30 seconds

No build, no terminal. Same as BillBlitz workflow.

---

## ⚠️ Limitations vs Vite Version

| Feature | This Version | Vite Version |
|---|---|---|
| Setup time | 5 min | 30 min |
| Build step | ❌ None | ✅ Required |
| Initial load | ~3-5 sec | ~1 sec |
| Production performance | Good | Excellent |
| Customer-facing? | ✅ Yes (great for MVP) | ✅ Yes (better for scale) |

For 1-50 hotels, this version is **perfect**. For 100+ scale, migrate to Vite later.

---

## 🔧 Customization

Open `index.html` in any text editor, find these sections:

**Hotel details** (search for `const HOTEL`):
```javascript
const HOTEL = {
  name: "Your Hotel Name",
  addr: "Your Address",
  phone: "+91 XXXXX XXXXX",
  // ...
};
```

**Demo users** (search for `LOGIN_USERS`):
```javascript
{u:"admin", p:"admin123", name:"Rajesh Kumar", role:"Manager"},
```

Edit, save, commit → live in 30 seconds.

---

## 🎯 Default Login

| Role | Username | Password |
|---|---|---|
| Manager | `admin` | `admin123` |
| Front Desk | `front` | `front123` |

---

## ⚡ Tech Stack (in browser, no install)

- React 18
- Babel Standalone (JSX transpiler)
- Tesseract.js (OCR engine)
- Custom CSS
- localStorage (data persistence)

All loaded from CDNs. Your single HTML file = ~96 KB.

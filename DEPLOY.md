# 🚀 AtithiBook — Deployment Steps

Sab files ready hain. Bas yeh commands run karo:

---

## STEP 1 — Extract & Install

```bash
# Extract the zip somewhere (e.g. Desktop)
cd Desktop/atithibook

# Install dependencies (will take 2-3 min, ~200 MB)
npm install
```

---

## STEP 2 — Test Locally

```bash
npm run dev
```

Browser open hoga → http://localhost:5173

Test karo:
- Login: `admin` / `admin123`
- Aadhaar photo upload → OCR auto-fill check karo
- Sab features test karo

`Ctrl + C` press karke server stop karo.

---

## STEP 3 — GitHub Pe Push

### 3a. GitHub repo banao
1. https://github.com/new pe jao
2. Repository name: `atithibook`
3. **Private** select karo (recommended)
4. Don't initialize with README (already hai)
5. "Create repository" click karo

### 3b. Local git setup
```bash
# atithibook folder mein hi ho
git init
git branch -M main
git add .
git commit -m "Initial AtithiBook release"
```

### 3c. Push to GitHub
```bash
# <your-username> apna actual replace karna
git remote add origin https://github.com/<your-username>/atithibook.git
git push -u origin main
```

Password ki jagah **Personal Access Token** maangega:
- https://github.com/settings/tokens
- "Generate new token (classic)"
- Scope: `repo` check karo
- Generate → copy token → paste karo when asked

✅ Code GitHub pe live!

---

## STEP 4 — Firebase Setup

### 4a. Firebase project banao
1. https://console.firebase.google.com/
2. "Add project" click karo
3. Name: `atithibook` (or your choice)
4. Google Analytics: **Disable** (zaroori nahi)
5. "Create project"

### 4b. Firebase CLI install
```bash
npm install -g firebase-tools
firebase login
```

Browser open hoga → Google account se login → "Allow" karo.

### 4c. Firebase init
```bash
# atithibook folder mein
firebase init hosting
```

Prompts:
- **Use an existing project** → atithibook select karo
- **Public directory** → `dist`
- **Configure as SPA** → `y` (Yes)
- **Set up GitHub deploys** → `n` (No)
- **Overwrite index.html** → `n` (No — DON'T overwrite)

`firebase.json` already hai, isliye warning aaye toh "Yes overwrite" → "No" press karo. Original wala better hai.

---

## STEP 5 — Deploy 🚀

```bash
npm run deploy
```

Yeh command:
1. Production build banata hai (`npm run build`)
2. Firebase pe upload karta hai

2-3 minute baad URL milegi:
```
✔  Deploy complete!
Hosting URL: https://atithibook.web.app
```

---

## STEP 6 — Phone Pe Install

1. Phone pe URL kholo: `https://atithibook.web.app`
2. Chrome menu (3 dots) → "Add to Home screen"
3. App icon home screen pe ban jayega
4. Like a native app open karo

---

## 🔄 Future Updates Workflow

Code change karne ke baad:

```bash
# 1. Test locally
npm run dev

# 2. GitHub pe push (history rakhne ke liye)
git add .
git commit -m "Description of changes"
git push

# 3. Production deploy
npm run deploy
```

---

## 🚨 Troubleshooting

### `npm install` fails
```bash
rm -rf node_modules package-lock.json
npm install
```

### `npm run build` fails
- Check `src/App.jsx` mein syntax errors
- Make sure Tesseract.js import line 2 pe hai

### Firebase deploy fails: "Permission denied"
```bash
firebase logout
firebase login
```

### Site khulti hai but blank screen
- Browser console open karo (F12)
- Red errors check karo
- Probably `App.jsx` import issue ya CSS path

### OCR pehli baar slow
- Normal hai — Tesseract language data download hota hai (~10s)
- Doosri baar fast hoga (cached)

---

## 📝 What Was Changed for Production

Original AtithiBook.jsx mein **2 changes** kiye gaye:

1. **Tesseract.js import added** (line 2)
2. **scanAadhaar function** — Claude Vision API → Tesseract.js OCR

Sab kuch baaki same hai. Original artifact se 1:1 features.

---

## 💡 Next Steps (Optional)

- **Custom domain** — Firebase Hosting console mein add karo (~₹800/year)
- **Firestore backend** — Multi-device sync ke liye
- **WhatsApp integration** — Invoice WhatsApp pe send karne ke liye
- **Multi-tenant** — Multiple hotels ek hi deployment se manage karne ke liye

Inme se kuch chahiye toh bolna — specific guide de dunga.

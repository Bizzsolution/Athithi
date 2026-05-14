# 🏨 AtithiBook — Hotel Management PWA

Mobile-first hotel management Progressive Web App for Indian hotels, lodges, and guest houses.

**Built with**: React 18 + Vite + Tesseract.js (browser OCR) + Firebase Hosting

---

## ✨ Features

- 📊 **Dashboard** — Live room stats, revenue, check-out alerts
- 🛏️ **Room Management** — 15 rooms across 3 floors, editable name/category/rate/photos
- ✅ **Guest Check-In** — Full form with Aadhaar OCR auto-fill
- 🪪 **Aadhaar Scanning** — Front + Back photos with one-click Tesseract.js OCR
- ✍️ **Digital Signature** — Canvas-based finger signature, embedded in invoice
- 💰 **Billing & Invoice** — 12% GST (SAC 9963), print-to-PDF invoices
- 🗂️ **Document Vault** — Search guests, view stored Aadhaar + signature, download
- 👤 **Owner Profile** — Editable name, hotel tagline, logo, dashboard banner
- 📱 **Installable PWA** — Add to Home Screen on mobile

---

## 🚀 Quick Start

### Local Development

```bash
# Install dependencies
npm install

# Run dev server
npm run dev
# → http://localhost:5173

# Build for production
npm run build
# → outputs to dist/
```

### Demo Login

| Role | Username | Password |
|---|---|---|
| Manager (Admin) | `admin` | `admin123` |
| Front Desk | `front` | `front123` |

---

## 🔥 Firebase Deployment

### One-time setup

```bash
# Install Firebase CLI globally
npm install -g firebase-tools

# Login to Firebase
firebase login

# Initialize (use existing project, public dir = dist, SPA = yes)
firebase init hosting
```

### Every deployment

```bash
npm run deploy
```

That's it. App goes live at `https://<your-project>.web.app`

---

## 📦 Project Structure

```
atithibook/
├── public/
│   ├── manifest.json    # PWA manifest
│   └── icon.svg         # App icon
├── src/
│   ├── App.jsx          # Main app (all components)
│   └── main.jsx         # Entry point
├── index.html           # Root HTML with PWA meta
├── vite.config.js       # Vite build config
├── firebase.json        # Firebase hosting config
└── package.json
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Framework | React 18 |
| Build tool | Vite 6 |
| OCR | Tesseract.js (browser-side, no API needed) |
| Storage | localStorage (per-device) |
| Hosting | Firebase Hosting (free tier) |
| Styling | Inline + injected CSS (no CSS framework) |

---

## 💡 Key Design Decisions

1. **Single JSX file** — All components in `App.jsx` for easy maintenance
2. **localStorage only** — No backend needed for single-hotel use. Add Firestore for multi-tenant.
3. **Browser OCR** — Tesseract.js works offline, no API keys, no per-scan cost
4. **PWA** — Installable on Android/iOS via "Add to Home Screen"
5. **GST built-in** — 12% rate (SAC 9963 for accommodation services)

---

## 🎨 Customization

### Change Hotel Details
Edit the `HOTEL` constant in `src/App.jsx`:

```javascript
const HOTEL = {
  name: "Your Hotel Name",
  addr: "Your Address",
  phone: "+91 XXXXX XXXXX",
  email: "info@yourhotel.com",
  gstin: "YOUR_GSTIN",
  tagline: "Your Tagline"
};
```

### Change Rooms
Edit the `initRooms()` function to add/remove/modify default rooms.

### Change Colors
Search for `--navy`, `--gold`, `--cream` in App.jsx CSS section.

---

## 📊 Cost

| Service | Free Tier | Sufficient for |
|---|---|---|
| Firebase Hosting | 10 GB storage, 360 MB/day bandwidth | 1-5 small hotels |
| Tesseract.js OCR | Unlimited (runs in browser) | Any scale |
| Custom domain | ~₹800/year (optional) | — |

---

## 🐛 Common Issues

| Issue | Solution |
|---|---|
| Camera doesn't open | Site must be HTTPS (Firebase URL works, localhost doesn't) |
| OCR slow first time | Tesseract downloads language data (~10-20s once) |
| Build fails | Delete `node_modules` and run `npm install` again |
| Photo upload not working | Check browser permissions for camera/files |

---

## 🚧 Roadmap (Future)

- [ ] Firestore backend for multi-device sync
- [ ] WhatsApp invoice sharing
- [ ] Multi-property support
- [ ] Tax reports (monthly GST CSV)
- [ ] Voice booking via Web Speech API
- [ ] Service worker for offline mode

---

## 📄 License

Private — Built by Dharamveer for hotel management automation.

---

## 🙏 Credits

Built with the help of Claude (Anthropic AI).

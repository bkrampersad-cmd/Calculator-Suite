# Beeran's Calculator Suite — Web App

## 🚀 GitHub Pages Setup (one-time)

### Step 1 — Create the repo
1. Go to [github.com/new](https://github.com/new)
2. Repository name: `calculator-suite` (or any name you like)
3. Set to **Public** (required for free GitHub Pages)
4. Click **Create repository**

### Step 2 — Upload the files
**Option A — Web upload (no git required):**
1. On the repo page click **Add file → Upload files**
2. Drag and drop ALL files from this folder:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon.svg`
3. Click **Commit changes**

**Option B — Git command line:**
```bash
cd path/to/this/folder
git init
git add .
git commit -m "Initial release — Beeran's Calculator Suite v1.0.0"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/calculator-suite.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages
1. Go to your repo → **Settings** → **Pages** (left sidebar)
2. Under **Source** → select **Deploy from a branch**
3. Branch: **main** · Folder: **/ (root)**
4. Click **Save**
5. Wait ~60 seconds — your site will be live at:
   `https://YOUR_USERNAME.github.io/calculator-suite`

---

## 📱 Installing as a PWA (phone/desktop)

**Android (Chrome):**
- Visit the site → tap the menu (⋮) → **Add to Home Screen**

**iOS (Safari):**
- Visit the site → tap **Share** → **Add to Home Screen**

**Windows/Mac (Chrome or Edge):**
- Visit the site → click the install icon in the address bar

---

## 🔧 Adding More Calculators

Each calculator follows the same pattern in `index.html`:

```javascript
CALCS['Calculator Name'] = {
  html() {
    return `<h1 class="page-title">Name</h1>
    <!-- your HTML layout here -->`;
  },
  init() {
    // bind events, wire up calculations
    window.myCalc = () => { /* ... */ };
  }
};
```

Then add the name to `IMPLEMENTED` set so it gets routed:
```javascript
const IMPLEMENTED = new Set([
  'Basic Calculator', 'Area', ... , 'Your New Calculator'
]);
```

---

## 📁 File Structure

```
/
├── index.html       ← entire app (HTML + CSS + JS)
├── manifest.json    ← PWA config (name, icons, colors)
├── sw.js            ← service worker (offline support)
├── icon.svg         ← app icon (works as fallback)
├── icon-192.png     ← PWA icon (generate from icon.svg)
└── icon-512.png     ← PWA icon (generate from icon.svg)
```

### Generating PNG icons
Open `generate-icons.html` in a browser, right-click each canvas, save as `icon-192.png` and `icon-512.png`, then upload to the repo.

---

## 🌐 Custom Domain (optional)
1. Buy a domain (e.g. `calculatorsuite.com`)
2. Repo → Settings → Pages → **Custom domain** → enter your domain
3. Follow GitHub's DNS instructions for your registrar

# Quick Start Guide

## View the Site Locally (Right Now!)

### Option 1: Just Open in Browser (Easiest - 10 seconds)

1. **Navigate to the folder:**
   ```
   C:\Users\Nitsan\work\FullProof
   ```

2. **Double-click `index.html`**
   - It will open in your default browser
   - You can view the full landing page immediately

3. **Test responsiveness:**
   - Press `F12` to open Developer Tools
   - Click the device toolbar icon (or press `Ctrl+Shift+M`)
   - Select iPhone/iPad/responsive view to see mobile version

### Option 2: Run Local Server (Better - 30 seconds)

**Why use a server?** Some features work better with a proper HTTP server.

**Using Python (if installed):**
```bash
cd C:\Users\Nitsan\work\FullProof
python -m http.server 8000
```

**Using Node.js (if installed):**
```bash
cd C:\Users\Nitsan\work\FullProof
npx http-server -p 8000
```

**Then open:** http://localhost:8000 in your browser

---

## What to Test First

### 1. Desktop View (1-2 minutes)
- ✅ Scroll through all 9 sections
- ✅ Click navigation links (should smooth scroll)
- ✅ Click FAQ questions (should expand/collapse)
- ✅ Hover over buttons (should change color)
- ✅ Verify Hebrew text displays correctly

### 2. Mobile View (1-2 minutes)
- ✅ Resize browser to narrow width (< 768px)
- ✅ Click hamburger menu icon (☰) - menu should slide down
- ✅ Click navigation link - menu should close and scroll to section
- ✅ Check all sections stack vertically
- ✅ Buttons become full-width

### 3. Interactive Features (30 seconds)
- ✅ Click any FAQ question → Answer expands
- ✅ Click same question again → Answer collapses
- ✅ Click different question → First closes, new one opens
- ✅ Click "התחל חינם" button → Should go to signup page

---

## Quick Edits to Try

### Change Color Scheme
**File:** `styles.css`
**Line:** 2-5

Replace:
```css
--primary-color: #1E3A8A;  /* Deep Blue */
--accent-color: #10B981;    /* Bright Green */
```

With:
```css
--primary-color: #7C3AED;  /* Purple */
--accent-color: #FCD34D;    /* Yellow */
```

Save and refresh browser to see new colors!

### Update Main Headline
**File:** `index.html`
**Line:** 41

Change to your own headline, then save and refresh.

### Change Pricing
**File:** `index.html`
**Lines:** 236-331

Edit the pricing amounts or features, save and refresh.

---

## Replace Placeholder Images

### Hero Animation
**File:** `index.html`
**Line:** 73-78

Replace:
```html
<div class="animation-placeholder">
    <p>אנימציה בקרוב</p>
</div>
```

With:
```html
<img src="assets/images/hero-animation.gif" alt="דוגמה">
```

(First add `hero-animation.gif` to `assets/images/` folder)

### Dashboard Screenshot
**File:** `index.html`
**Line:** 190

Replace:
```html
<img src="https://placehold.co/1200x800/1e3a8a/ffffff?text=דשבורד+מורה+בעברית" alt="דשבורד מורה">
```

With:
```html
<img src="assets/images/dashboard.png" alt="דשבורד מורה">
```

(First add `dashboard.png` to `assets/images/` folder)

### Add Logo
**File:** `index.html`
**Line:** 28

Replace:
```html
<div class="logo">Full Proof</div>
```

With:
```html
<img src="assets/icons/logo.svg" alt="Full Proof" class="logo">
```

Then add to `styles.css` after line 307:
```css
.logo img {
    height: 40px;
    width: auto;
}
```

---

## Common Issues & Fixes

### Hebrew text looks wrong
**Problem:** Font not loading
**Fix:** Check internet connection (Heebo loads from Google Fonts)

### Mobile menu not working
**Problem:** JavaScript not running
**Fix:** Open browser console (F12), check for errors

### Images not showing
**Problem:** Wrong file path
**Fix:** Ensure images are in `assets/images/` folder, check spelling

### Buttons not linking
**Problem:** Need to update URLs
**Fix:** Edit `index.html` lines with `href="https://app.fullproof.com/signup"`

---

## Next Steps

1. ✅ **Test locally** (you are here)
2. 📸 **Replace placeholders** with real images
3. ✏️ **Proofread** all Hebrew text
4. 📱 **Test on real phone** (not just browser resize)
5. 🚀 **Deploy** to Netlify (see DEPLOYMENT.md)

---

## File Structure Reference

```
C:\Users\Nitsan\work\FullProof\
│
├── index.html              ← Main file - All content here
├── styles.css              ← All styling - Colors, layout, responsive
├── script.js               ← Interactivity - Menu, FAQ, scroll
│
├── README.md               ← Project overview
├── DEPLOYMENT.md           ← How to deploy to Netlify/Vercel
├── IMPLEMENTATION_SUMMARY.md ← Detailed implementation notes
├── QUICKSTART.md           ← This file
│
└── assets/
    ├── images/             ← Put screenshots, diagrams, animations here
    └── icons/              ← Put logo.svg and favicon.png here
```

---

## Quick Commands Cheat Sheet

**Open file in VS Code:**
```bash
code C:\Users\Nitsan\work\FullProof
```

**Start local server (Python):**
```bash
cd C:\Users\Nitsan\work\FullProof
python -m http.server 8000
```

**Start local server (Node):**
```bash
cd C:\Users\Nitsan\work\FullProof
npx http-server -p 8000
```

**Deploy to Netlify (CLI):**
```bash
cd C:\Users\Nitsan\work\FullProof
netlify deploy --prod
```

---

## Getting Help

- **Browser won't show changes?** Hard refresh: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)
- **FAQ not working?** Check browser console (F12) for JavaScript errors
- **RTL layout broken?** Ensure `<html dir="rtl">` is in index.html line 2
- **Fonts look wrong?** Make sure you have internet (Google Fonts needs to load)

---

## Pro Tips

💡 **Edit and see changes instantly:**
- Keep browser window next to code editor
- Save file (`Ctrl+S`)
- Refresh browser (`F5`)
- See changes immediately

💡 **Test on real phone:**
- Both local and deployed sites can be tested on phone
- For local: Both devices must be on same WiFi
- Find your computer's IP: `ipconfig` (Windows) or `ifconfig` (Mac)
- On phone, visit: `http://YOUR_IP:8000`

💡 **Browser extensions to try:**
- **Lighthouse** - Performance testing
- **WAVE** - Accessibility checker
- **WhatFont** - See which fonts are loading

---

**Time to Launch:** You're about 1-2 hours away from a live website!

1. Replace 4 placeholder images (30 min)
2. Test on phone (15 min)
3. Proofread content (15 min)
4. Deploy to Netlify (5 min)

**Let's go! 🚀**

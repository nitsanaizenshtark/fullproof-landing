# Deployment Guide - FullProof Landing Page

## Quick Start (< 5 minutes)

### Option 1: Netlify (Recommended - Easiest)

1. **Create Account**
   - Go to https://netlify.com
   - Sign up with GitHub, GitLab, or email

2. **Deploy**
   - Drag and drop the entire `FullProof` folder to Netlify dashboard
   - Or use Netlify CLI:
     ```bash
     npm install -g netlify-cli
     netlify deploy --dir=C:\Users\Nitsan\work\FullProof --prod
     ```

3. **Done!**
   - Site is live with HTTPS
   - Gets a URL like: `https://fullproof-landing.netlify.app`

4. **Custom Domain (Optional)**
   - In Netlify dashboard: Domain settings → Add custom domain
   - Follow DNS instructions

### Option 2: Vercel

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Deploy**
   ```bash
   cd C:\Users\Nitsan\work\FullProof
   vercel --prod
   ```

3. **Follow Prompts**
   - Link to your Vercel account
   - Site will be deployed

### Option 3: GitHub Pages

1. **Create GitHub Repository**
   ```bash
   cd C:\Users\Nitsan\work\FullProof
   git init
   git add .
   git commit -m "Initial commit: FullProof landing page"
   ```

2. **Push to GitHub**
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/fullproof-landing.git
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to repository Settings → Pages
   - Source: Deploy from branch `main`
   - Folder: `/` (root)
   - Save

4. **Access Site**
   - URL: `https://YOUR_USERNAME.github.io/fullproof-landing/`

## Pre-Deployment Checklist

### 1. Replace Placeholder Content

**Update these in `index.html`:**
- [ ] Change placeholder images to real screenshots
- [ ] Add actual logo to navigation (line 28)
- [ ] Verify all email links go to correct address
- [ ] Update signup URLs if different from `https://app.fullproof.com/signup`

**Add real assets:**
- [ ] Hero animation GIF/video → Place in `/assets/images/hero-animation.gif`
- [ ] Dashboard screenshot → `/assets/images/dashboard.png`
- [ ] Problem/solution images → `/assets/images/`
- [ ] Logo SVG → `/assets/icons/logo.svg`
- [ ] Favicon → `/assets/icons/favicon.png`

### 2. Update Links

Check these links work:
- [ ] `https://app.fullproof.com/signup` (Free signup)
- [ ] `https://app.fullproof.com/school-login` (School login)
- [ ] `https://app.fullproof.com/signup?plan=professional` (Professional signup)
- [ ] `support@fullproof.com` (Support email)

### 3. Test Locally

**Open in browser:**
```bash
# Simple HTTP server (Python)
cd C:\Users\Nitsan\work\FullProof
python -m http.server 8000

# Or use Node.js
npx http-server -p 8000
```

Then open: `http://localhost:8000`

**Test:**
- [ ] All sections display correctly
- [ ] Mobile menu works (resize to < 768px)
- [ ] FAQ accordion expands/collapses
- [ ] All links clickable
- [ ] Smooth scroll works
- [ ] Hebrew text displays properly

### 4. Performance Check

**Before deployment:**
- [ ] Optimize images (use https://tinypng.com or similar)
- [ ] Compress any videos
- [ ] Target: Page load < 3 seconds

**After deployment:**
- [ ] Test speed at https://pagespeed.web.dev
- [ ] Check mobile performance
- [ ] Verify HTTPS is working

### 5. SEO & Social Sharing

**Add to `index.html` if not already present:**
```html
<!-- Favicon -->
<link rel="icon" type="image/png" href="assets/icons/favicon.png">

<!-- Open Graph for social sharing -->
<meta property="og:image" content="https://YOUR-DOMAIN.com/assets/images/og-image.jpg">
<meta property="og:url" content="https://YOUR-DOMAIN.com">

<!-- Google Analytics (optional) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## Post-Deployment

### 1. Test Live Site

- [ ] Open on desktop browser
- [ ] Open on mobile device (iPhone + Android)
- [ ] Test all CTA buttons
- [ ] Verify RTL layout
- [ ] Check FAQ accordion
- [ ] Test contact email links
- [ ] Verify smooth scrolling

### 2. Browser Testing

Test on:
- [ ] Chrome (desktop + mobile)
- [ ] Safari (desktop + mobile)
- [ ] Firefox
- [ ] Edge

### 3. Share Preview Link

Test how it looks when shared:
- [ ] WhatsApp
- [ ] Facebook
- [ ] LinkedIn
- [ ] Twitter/X

### 4. Analytics (Optional)

If using Google Analytics:
1. Create GA4 property at https://analytics.google.com
2. Get measurement ID (e.g., `G-XXXXXXXXXX`)
3. Add tracking code to `index.html` (see SEO section above)

## Updating the Site

### Quick Updates

1. **Edit files locally**
2. **Re-deploy:**
   - **Netlify**: Just drag-and-drop updated folder again
   - **Vercel**: Run `vercel --prod` again
   - **GitHub Pages**: `git add . && git commit -m "Update" && git push`

### Content Updates

Common updates you might make:
- Testimonials: Edit HTML in `index.html` lines 509-535
- Pricing: Update `index.html` lines 364-461
- FAQ: Add/edit questions in `index.html` lines 574-682
- Trust bar numbers: Update line 90

## Troubleshooting

### Site not loading
- Check if files are in correct location
- Verify no build errors in deployment logs
- Check browser console for errors (F12)

### RTL layout broken
- Ensure `<html lang="he" dir="rtl">` is present
- Check CSS has logical properties (margin-inline, etc.)
- Verify Heebo font is loading

### Mobile menu not working
- Check `script.js` is linked in HTML
- Open browser console to check for JavaScript errors
- Verify mobile-menu-toggle button exists in HTML

### Images not showing
- Check file paths are correct
- Ensure images are in `/assets/images/` folder
- Verify image URLs don't have spaces (use hyphens instead)

## Custom Domain Setup

### Netlify
1. Domain settings → Add custom domain
2. Add DNS records provided by Netlify
3. Wait for DNS propagation (up to 48 hours)

### Vercel
1. Project settings → Domains
2. Add domain
3. Configure DNS with provided records

### GitHub Pages
1. Add CNAME file to repository root:
   ```
   www.fullproof.co.il
   ```
2. Configure DNS:
   - CNAME record: `www` → `YOUR_USERNAME.github.io`
   - A records for apex domain to GitHub IPs

## Support

**Deployment Issues:**
- Netlify: https://docs.netlify.com
- Vercel: https://vercel.com/docs
- GitHub Pages: https://docs.github.com/pages

**Site Issues:**
- Check README.md for testing checklist
- Review browser console for errors
- Verify all files are uploaded correctly

---

**Quick Reference URLs:**
- Netlify: https://netlify.com
- Vercel: https://vercel.com
- GitHub Pages: https://pages.github.com
- Page Speed Test: https://pagespeed.web.dev
- Image Optimizer: https://tinypng.com

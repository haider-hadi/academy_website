# GitHub Pages Deployment Guide

## 🚀 Quick Start

If you've already uploaded to GitHub and the website is not showing responsive design, follow these steps:

### Step 1: Verify Files Are Uploaded
```
✅ Your repository should have these files visible:
- index.html
- courses.html
- about.html
- contact.html
- css/ (folder with style.css)
- js/ (folder with script.js)
```

### Step 2: Force Refresh Browser Cache

**Windows:**
- Press `Ctrl + Shift + Delete` simultaneously
- Select "All time" → "Cookies and other site data" → Clear data

**Mac:**
- Press `Cmd + Option + E` (Safari)
- Or use Chrome: `Cmd + Shift + Delete`

**Or Hard Refresh:**
- Press `Ctrl + Shift + R` (Windows/Linux)
- Press `Cmd + Shift + R` (Mac)

### Step 3: Wait 2-3 Minutes
GitHub Pages may take 1-2 minutes to deploy changes. If still not working:

### Step 4: Check GitHub Pages Settings
1. Go to your GitHub repository
2. Click **Settings**
3. Scroll down to **Pages** section
4. Make sure:
   - Source is set to `main` branch (or `master`)
   - Folder is set to `/ (root)`
5. It should say "Your site is live at: https://yourusername.github.io/academy_website/"

### Step 5: Verify CSS File
1. Visit your site URL
2. Open DevTools (Right-click → Inspect or press F12)
3. Go to **Network** tab
4. Reload the page
5. Look for `style.css` in the list
6. It should show status **200** (not 404)
7. Size should be **~55KB** or larger

---

## 🔧 If CSS Still Not Loading

### Issue: CSS returns 404 error

**Solution A: Check file path in HTML**
- Open `index.html`
- Look for this line: `<link rel="stylesheet" href="css/style.css">`
- Make sure it's exactly as shown (case-sensitive on GitHub)

**Solution B: Re-upload CSS file**
1. Delete the `css` folder from GitHub
2. Upload it again with the `style.css` file inside
3. Wait 2 minutes
4. Hard refresh browser (Ctrl+Shift+R)

**Solution C: Check GitHub repository structure**
```
academy_website/
├── index.html
├── css/
│   └── style.css          ← Make sure this path is correct
├── js/
│   └── script.js
└── ...
```

---

## 📊 Verify CSS Size and Content

The CSS file should be approximately:
- **File size**: 50-60 KB
- **Total lines**: 1348+
- **Includes**: Media queries for 768px and 480px breakpoints

To check:
1. Open DevTools (F12)
2. Go to **Network** tab
3. Look at the size of `style.css`
4. Should be 50KB+

---

## 🌐 Test Responsive Design

### Method 1: Chrome DevTools
1. Open your site
2. Press `F12` to open DevTools
3. Click the device toggle (📱 icon) in top-left corner
4. Select device:
   - **iPhone SE** (375px width)
   - **iPhone 12 Pro** (390px width)
   - **iPad** (768px width)
   - **Galaxy S5** (360px width)
5. Navigation should wrap and stack on mobile

### Method 2: Real Mobile Device
1. Visit: `https://yourusername.github.io/academy_website/`
2. Should see navigation wrapping on mobile
3. Should NOT have horizontal scrollbar
4. Content should be readable without zooming

### Method 3: Browser Resize
1. Maximize browser window
2. Slowly drag right edge of window to left
3. At 768px width: Layout should change
4. At 480px width: Mobile layout should activate

---

## 📱 Expected Responsive Behavior

### Desktop (> 768px)
- ✅ Full navigation menu visible horizontally
- ✅ Multiple column grids
- ✅ Large hero section with full content
- ✅ All features visible

### Tablet (480-768px)
- ✅ Navigation wraps slightly
- ✅ Single/double column layouts
- ✅ Reduced padding and margins
- ✅ Adjusted font sizes

### Mobile (< 480px)
- ✅ Navigation stacks in 2 columns
- ✅ Logo centered above menu
- ✅ All grids single column
- ✅ Full-width buttons
- ✅ Reduced padding
- ✅ Smaller fonts

---

## ⚠️ Common Issues & Solutions

| Issue | Solution |
|-------|----------|
| Website shows only content | Clear browser cache (Ctrl+Shift+Delete) |
| CSS not loading (404) | Check `css/style.css` file path is correct |
| Layout not changing on mobile | Open DevTools (F12) → check style.css loaded |
| GitHub says site not ready | Wait 2-3 minutes, then hard refresh |
| Font too large on mobile | CSS media queries working, no action needed |
| Horizontal scroll on mobile | Check for missing `overflow-x: hidden` in CSS |

---

## 🔄 How to Fix Common Problems

### Problem: "I pushed changes but website still looks old"

**Step 1:** Hard refresh your browser
```
Ctrl + Shift + R (Windows/Linux)
Cmd + Shift + R (Mac)
```

**Step 2:** Clear all cache
```
Ctrl + Shift + Delete (Windows/Linux)
Cmd + Shift + Delete (Mac)
```

**Step 3:** Wait 2-3 minutes for GitHub Pages to rebuild

**Step 4:** Open in private/incognito window (skips cache)
```
Ctrl + Shift + N (Windows/Linux)
Cmd + Shift + N (Mac)
```

---

### Problem: "Styles are completely missing"

Check that:
1. ✅ `css/` folder exists in repository
2. ✅ `style.css` file is inside `css/` folder
3. ✅ File is not empty (should be 50KB+)
4. ✅ HTML file has correct link: `<link rel="stylesheet" href="css/style.css">`

---

### Problem: "Mobile view doesn't change"

1. Open DevTools (F12)
2. Go to **Network** tab
3. Reload page
4. Check if `style.css` loads (status 200)
5. If status is 404, file path is wrong
6. If file loads but styles don't apply, CSS may have syntax error

---

## 📋 Final Checklist

Before declaring success:

- [ ] Can access website at GitHub Pages URL
- [ ] Desktop view looks good (> 768px)
- [ ] Tablet view works (480-768px)
- [ ] Mobile view responsive (< 480px)
- [ ] Navigation wraps on mobile
- [ ] No horizontal scrollbar on mobile
- [ ] All links work
- [ ] Contact form appears
- [ ] Footer loads
- [ ] No 404 errors in DevTools

---

## 📞 Debugging Commands

In DevTools Console, run these to check if CSS is loaded:

```javascript
// Check if stylesheet is loaded
console.log(document.styleSheets);

// Check computed styles
console.log(window.getComputedStyle(document.body));

// Check media query support
console.log(window.matchMedia("(max-width: 768px)").matches);
```

---

## ✨ You're All Set!

If you've followed these steps and CSS is loading correctly, your website should be fully responsive!

**Questions?** Check:
1. README.md (project overview)
2. RESPONSIVE-DESIGN.md (design details)
3. This document (deployment help)

---

**Last Updated**: January 29, 2026
**Version**: Complete Responsive Design
**CSS Lines**: 1348+
**File Size**: ~55KB

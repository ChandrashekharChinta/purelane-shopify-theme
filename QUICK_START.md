# 🚀 Quick Start Guide - Purelane Shopify Theme

## Option 1: Upload to Shopify (Easiest - No Coding Required)

### Step 1: Download & Extract
1. Download `purelane-shopify-theme-complete.zip`
2. Extract the zip file on your computer
3. You'll see a folder called `Assesment-Ai`

### Step 2: Upload to Shopify Admin
1. Go to your **Shopify Admin** (admin.shopify.com)
2. Navigate to **Online Store > Themes**
3. Click **"Add theme"** (top right)
4. Click **"Upload file"**
5. Select the **`Assesment-Ai` folder** (or zip the `theme` folder inside it)
6. Wait for upload to complete ✅

### Step 3: Customize the Theme
1. On the **Themes** page, find your newly uploaded theme
2. Click **"Customize"** (eye icon or button)
3. You'll see the Shopify Theme Editor with sections listed on the left

### Step 4: Edit Sections
**Example: Change Hero Heading**
1. Click **"Hero"** section in the left panel
2. Edit fields:
   - **Heading line 1**: Change to your text
   - **Heading line 2**: Change to your text
   - **Heading highlight**: This text turns lime green
   - **Description**: Main copy
3. Changes save automatically
4. Click **"Save"** (top right)

**Example: Add Products**
1. Click **"Featured products"** section
2. Click **"Add block"**
3. Select a product from dropdown OR enter fallback title/price
4. Repeat to add more products
5. Save

**Example: Edit Announcement Ticker**
1. Click **"Announcement bar"**
2. Edit or add announcements
3. Example: "Free shipping" + highlight "on every bundle"
4. Repeats automatically for scrolling effect

### Step 5: Go Live
1. On the **Themes** page, click the **"..."** menu on your theme
2. Click **"Publish"**
3. Your theme is now live! 🎉

---

## Option 2: Local Development with Shopify CLI (For Developers)

### Prerequisites
- **Node.js** (v16+) installed on your computer
- **Git** installed
- Shopify store access
- Mac/Windows/Linux terminal knowledge

### Step 1: Install Shopify CLI
```bash
# Mac (using Homebrew)
brew tap shopify/shopify
brew install shopify-cli

# Windows (using Chocolatey)
choco install shopify-cli

# Or download from: https://shopify.dev/themes/tools/cli/installation
```

### Step 2: Navigate to Theme Folder
```bash
cd path/to/Assesment-Ai/theme
```

### Step 3: Log In to Shopify
```bash
shopify login --store your-store-name.myshopify.com
```
- Opens browser, log in with your Shopify account
- Returns to terminal when done

### Step 4: Create or Develop Locally
```bash
# Option A: Push to existing theme
shopify theme push --theme [THEME_ID]

# Option B: Create new theme
shopify theme push
# Asks if you want to create a new theme
# Confirms when uploaded

# Option C: Develop with live preview
shopify theme dev
# Opens localhost:3000 with live preview
# Changes auto-sync to Shopify
# Press Ctrl+C to stop
```

### Step 5: Push to Store
```bash
shopify theme push
# Uploads all files to your theme
# Ready to publish in admin
```

---

## Option 3: Edit Files Locally (Advanced)

### Edit Files Without Uploading
1. Extract the zip
2. Navigate to `Assesment-Ai/theme/`
3. Edit files in your code editor:
   - **Sections**: `/sections/*.liquid`
   - **Styles**: `/assets/purelane.css`
   - **JavaScript**: `/assets/purelane.js`
   - **Snippets**: `/snippets/*.liquid`

### Upload Your Changes
**Via Shopify CLI:**
```bash
shopify theme push
```

**Via Shopify Admin:**
1. Go to **Online Store > Themes > Edit code**
2. Find the file you changed
3. Copy/paste your updated content
4. Save

---

## 📝 Common Tasks

### Add a New Product
1. **Customize** your theme
2. Click **Featured products** section
3. Click **"Add block"**
4. Select product from dropdown
5. Click **Save**

### Change Colors
1. Click **"Announcement bar"** or any section
2. Look for **Color** settings
3. Click color picker, choose new color
4. Saves automatically

### Edit Newsletter Text
1. Click **"Newsletter"** section
2. Edit:
   - Heading
   - Description
   - Button text
   - Privacy disclaimer
3. Save

### Add Testimonials
1. Click **"Testimonials"** section
2. Click **"Add block"**
3. Fill in:
   - **Title**: E.g., "Best dishwash ever"
   - **Quote**: Customer testimonial
   - **Author**: Customer name
4. Repeat for more testimonials

### Change Footer Links
1. Click **"Footer"** section
2. Add/edit columns with:
   - Column title (e.g., "Shop")
   - Links (comma-separated URLs)
3. Save

---

## 🎨 Customization Guide

### Brand Colors
Edit `/assets/purelane.css` line 1-20 (CSS variables):
```css
:root {
  --ink: #17102b;           /* Dark text */
  --brand: #4b3a8f;         /* Purple primary */
  --accent: #f0a03c;        /* Gold/lime accent */
  --surface: #faf7fd;       /* Light background */
  /* ... more colors ... */
}
```

### Typography
Edit `/assets/purelane.css` section `TYPE`:
```css
.d1 {
  font-size: clamp(48px, 8.6vw, 112px);  /* Responsive heading */
  font-family: 'Outfit', sans-serif;
  /* ... */
}
```

### Section Spacing
Edit `/assets/purelane.css` line 17:
```css
--sec-y: 34px;  /* Change spacing between sections */
```

### Water Animation
In `/assets/purelane.js`, section "WATER CINEMATICS" controls:
- Drift speed
- Opacity
- Wave patterns
- Blending modes

### Scene Backgrounds
Edit `/assets/purelane.css` section "SCENES":
- `.s1` through `.s4` define 4 gradient backgrounds
- Triggered by scroll position via JavaScript

---

## 🔧 Troubleshooting

### Theme not showing sections in editor
**Fix:**
1. Ensure theme folder structure is correct
2. Check all files are in right folders
3. Try uploading again
4. Hard refresh browser (Ctrl+Shift+R)

### Styles not applying
**Fix:**
1. Check `/assets/purelane.css` uploaded correctly
2. Clear Shopify cache: Settings > Clear cache
3. Hard refresh page (Ctrl+Shift+R)
4. Check browser DevTools for CSS conflicts

### Products not appearing
**Fix:**
1. Add real products via dropdown selector
2. Or enter fallback title/price manually
3. Ensure product images are uploaded

### Animation not working
**Fix:**
1. Check `/assets/purelane.js` uploaded
2. Verify `data-scene="X"` on sections
3. Check browser console for errors
4. Test on different browser

### Can't log in via CLI
**Fix:**
```bash
shopify logout
shopify login --store your-store.myshopify.com
```

---

## 📚 File Structure Explained

```
theme/
├── assets/              # CSS & JavaScript (loaded globally)
├── config/              # Theme settings & defaults
├── layout/              # Master HTML template (used by all pages)
├── locales/             # Translations (currently English only)
├── sections/            # Editable sections (customers drag these around)
├── snippets/            # Reusable components (included in sections)
└── templates/           # Page templates (index = homepage)
```

**Key Concept:**
- **Sections** = Big blocks customers see in editor (hero, products, etc.)
- **Snippets** = Small reusable components (icon, button, badge)
- **Assets** = Global CSS/JS loaded once
- **Layout** = Wraps all pages with header/footer

---

## ✅ Launch Checklist

- [ ] Theme uploaded to Shopify
- [ ] Homepage customized with your products
- [ ] Hero heading changed to your brand messaging
- [ ] Testimonials added (or section removed)
- [ ] Newsletter form set up
- [ ] Footer links configured
- [ ] Announcement ticker updated
- [ ] Social links added (settings)
- [ ] Colors customized to match your brand
- [ ] Tested on mobile (iPhone, Android)
- [ ] Tested on desktop
- [ ] Water animation smooth on target devices
- [ ] Theme published (marked as live)
- [ ] Domain pointing to Shopify store

---

## 🚀 You're Ready!

Your Shopify theme is:
✅ Production-ready
✅ Fully responsive
✅ Merchant-editable
✅ No coding required for content changes
✅ Animated & modern design

**Next Steps:**
1. Upload theme to Shopify
2. Customize homepage in editor
3. Add your products
4. Publish to go live!

---

## 📞 Need Help?

**For Shopify-specific questions:**
- https://shopify.dev/themes
- https://community.shopify.com/c/shopify-design/

**For theme code questions:**
- Check `/README.md` in the theme folder
- Review section schemas in `/sections/*.liquid`
- Inspect CSS variables in `/assets/purelane.css`

**To modify code:**
- Download Shopify CLI for local editing
- Or use Shopify Admin's built-in code editor
- Push changes back to store

---

Happy selling! 🎉

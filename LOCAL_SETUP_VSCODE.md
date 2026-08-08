# 🔧 Local Development Setup - Shopify Theme in VSCode

## For Company Recruitment Task - Professional Setup

This guide shows the **production workflow** for Shopify theme development.

---

## 🚀 Step-by-Step Setup

### Step 1: Extract Theme Files
1. Download `purelane-shopify-theme-complete.zip`
2. Extract it on your computer
3. You'll have `Assesment-Ai/` folder

### Step 2: Open in VSCode
1. Open **VSCode**
2. **File → Open Folder**
3. Navigate to `Assesment-Ai/theme/` (NOT the parent folder)
4. Open it
5. You should see file structure in left panel:
   - assets/
   - config/
   - layout/
   - locales/
   - sections/
   - snippets/
   - templates/

### Step 3: Open Terminal in VSCode
1. Top menu: **Terminal → New Terminal**
2. Terminal opens at bottom
3. You're now in the `theme/` folder (should show in terminal path)

### Step 4: Login to Shopify
In the terminal, run:
```bash
shopify login --store your-store-name.myshopify.com
```

**What happens:**
- Browser opens
- Log in with Shopify account (the company's account)
- Returns to VSCode when done
- Terminal shows: ✅ "Logged in successfully"

**Example:**
```bash
shopify login --store mycompany-dev.myshopify.com
```

### Step 5: Start Local Development Server
In terminal, run:
```bash
shopify theme dev
```

**What this does:**
- ✅ Creates a local server (usually `http://localhost:3000`)
- ✅ Syncs files automatically to Shopify (live editing)
- ✅ Opens browser preview
- ✅ Shows real-time changes

**Terminal output should show:**
```
⚙️  Uploading your theme to Shopify...
📱 Preview URL: https://your-store.myshopify.com?preview_theme_id=123456789
🔗 Storefront password: (password shown)
🔄 Syncing files...
✅ Ready for editing
```

### Step 6: Edit Files in VSCode
Now you can:
1. Edit any file in VSCode (sections, CSS, etc.)
2. Save the file (Ctrl+S or Cmd+S)
3. Changes automatically sync to Shopify
4. Browser auto-refreshes
5. See live preview at the URL in terminal

---

## 💻 Example: Edit Hero Section

### In VSCode:
1. Open `sections/hero.liquid`
2. Find this line (around line 21):
```liquid
<h1 class="d1 rv in">Clean<br>That<br><span class="lime">Lasts</span></h1>
```
3. Change to your text:
```liquid
<h1 class="d1 rv in">Your<br>Brand<br><span class="lime">Text</span></h1>
```
4. Save (Ctrl+S)
5. Browser auto-refreshes - see changes live!

### Edit CSS:
1. Open `assets/purelane.css`
2. Change a color (line 9):
```css
--accent: #f0a03c;  /* Change to #FF5733 for different color */
```
3. Save
4. Browser updates instantly

### Edit Settings:
1. Open `config/settings_schema.json`
2. Add new setting, save
3. Appears in Shopify theme editor automatically

---

## 🎨 Full Editing Workflow

### File Structure in VSCode:

```
theme/
├── assets/
│   ├── purelane.css          ← Edit styles here
│   └── purelane.js           ← Edit animations here
│
├── config/
│   ├── settings_schema.json  ← Add/edit theme settings
│   └── settings_data.json    ← Default values
│
├── layout/
│   └── theme.liquid          ← Master HTML template
│
├── sections/                 ← Edit individual sections
│   ├── hero.liquid
│   ├── reviews.liquid
│   ├── featured-products.liquid
│   └── ... (15 sections)
│
├── snippets/                 ← Reusable components
│   ├── icon.liquid
│   ├── product-card.liquid
│   └── ... (6 snippets)
│
└── templates/
    └── index.json            ← Homepage structure
```

### Edit Priority (for company task):

**Easy (No Liquid knowledge needed):**
- Edit text in sections (headlines, descriptions)
- Change CSS colors in `purelane.css`
- Modify settings in `settings_schema.json`

**Medium (Basic Liquid):**
- Add/remove blocks in sections
- Change conditional logic (`{% if %}`)
- Loop through items (`{% for %}`)

**Advanced (Full Liquid):**
- Create new sections
- Complex logic
- Shopify API integration

---

## 🔄 Workflow Commands

### Start Development:
```bash
shopify theme dev
```
- Starts local server
- Syncs to Shopify in real-time
- Browser auto-refreshes
- Press Ctrl+C to stop

### View Logs:
```bash
shopify theme dev --verbose
```
- Shows all file changes
- Helpful for debugging

### Push to Store (Final):
```bash
shopify theme push
```
- Uploads all files to Shopify
- Doesn't preview, just pushes

### Pull from Store:
```bash
shopify theme pull
```
- Downloads theme from Shopify
- Useful if store changes were made

### Create New Theme (Alternative):
```bash
shopify theme dev --clone [THEME_ID]
```
- Creates a new theme based on existing one
- Useful for A/B testing

---

## ✅ Verification Checklist

### After Setup:
- [ ] Node.js installed (`node --version` works)
- [ ] Shopify CLI installed (`shopify version` works)
- [ ] VSCode open with `theme/` folder
- [ ] Terminal shows correct path
- [ ] Logged into Shopify (`shopify login` done)
- [ ] `shopify theme dev` starts successfully
- [ ] Browser shows preview URL
- [ ] Can see live preview of theme
- [ ] File edits auto-sync (test by changing CSS color)

---

## 🐛 Troubleshooting

### "Command not found: shopify"
**Fix:**
```bash
# Install Shopify CLI globally
npm install -g @shopify/cli

# Verify
shopify version
```

### "Not logged in" error
**Fix:**
```bash
shopify logout
shopify login --store your-store.myshopify.com
```

### Port 3000 already in use
**Fix:**
```bash
shopify theme dev --port 3001
# Uses port 3001 instead
```

### Changes not syncing
**Fix:**
1. Save file (Ctrl+S)
2. Check terminal for errors
3. Hard refresh browser (Ctrl+Shift+R)
4. Restart: Ctrl+C in terminal, then `shopify theme dev` again

### Terminal path wrong
**Fix:**
1. In VSCode, open terminal
2. Type: `cd path/to/theme/folder`
3. Verify: `ls` or `dir` shows theme files

### Git conflicts after pull
**Fix:**
```bash
# Reset to latest version
git reset --hard
git pull

# Or just delete local folder and re-extract
```

---

## 🎓 Learning Resources

### Shopify Liquid Docs:
- https://shopify.dev/docs/themes/liquid/reference
- Reference for all Liquid tags and filters

### Theme Development:
- https://shopify.dev/themes/getting-started
- Official Shopify theme dev guide

### CLI Commands:
- https://shopify.dev/themes/tools/cli/commands
- All `shopify theme` commands explained

### VSCode Extensions (Optional):
**Recommended extensions to install:**
1. **Shopify Liquid** (Discount Labs) - Liquid syntax highlighting
   - Go to Extensions panel (Ctrl+Shift+X)
   - Search "Shopify Liquid"
   - Install

2. **Liquid** (Shopify) - Official Liquid extension
   - Search "Liquid" by Shopify
   - Install

3. **Thunder Client** - Test API calls (if needed)

---

## 📊 Company Recruiting Task Setup

### What This Shows:
✅ **Professional workflow** - Local dev + CLI (not manual uploads)  
✅ **Version control** - Can use Git with local files  
✅ **Real development** - How actual developers work  
✅ **Testing** - Live preview before deployment  
✅ **Scalability** - Can handle complex customizations  

### For Your Resume/Portfolio:
- Shows you understand **Shopify theme architecture**
- Demonstrates **CLI tool usage**
- Proves **local development workflow**
- Shows **Liquid templating knowledge**
- Indicates **DevOps/deployment practices**

### Typical Recruiting Task Flow:
1. ✅ Setup local dev environment (this guide)
2. ✅ Make customizations (edit sections, add products)
3. ✅ Test locally (`shopify theme dev`)
4. ✅ Commit to Git (`git commit`)
5. ✅ Push to Shopify (`shopify theme push`)
6. ✅ Go live in admin
7. ✅ Show live URL to recruiter

---

## 🚀 Quick Start Summary

```bash
# 1. Install Node.js, Git, Shopify CLI
npm install -g @shopify/cli

# 2. Navigate to theme folder
cd path/to/Assesment-Ai/theme

# 3. Login to Shopify
shopify login --store company-store.myshopify.com

# 4. Start development server
shopify theme dev

# 5. Edit files in VSCode → Auto-syncs → See live preview

# 6. When done, push to store
shopify theme push

# 7. Publish in Shopify admin
```

---

## 📝 Next Steps

1. **Install everything** (Node.js, Shopify CLI)
2. **Extract theme files**
3. **Open folder in VSCode**
4. **Run `shopify login`**
5. **Run `shopify theme dev`**
6. **Start editing!**
7. **Show working preview to company**

---

## 💡 Pro Tips for Recruitment Task

### Show Your Understanding:
- Mention you're using "local development workflow"
- Explain you're testing before pushing to production
- Show your Git commits (`git log`)
- Describe changes you made to sections

### Make It Impressive:
- Customize beyond defaults (add new features)
- Create a new section from scratch
- Optimize performance (explain CSS changes)
- Test on mobile (show responsive design)
- Document your changes in commits

### Git Workflow Example:
```bash
# Initialize Git (if not already)
git init

# Create feature branch
git checkout -b feature/customize-hero

# Make changes in VSCode
# Edit sections/hero.liquid
# Edit assets/purelane.css

# Commit changes
git add .
git commit -m "Customize hero section with company branding"

# Push to company repo
git push origin feature/customize-hero

# Later: Push to Shopify
shopify theme push
```

---

## ✨ You're Ready!

**This is the professional Shopify workflow. Good luck with your recruitment task!** 🎉

If the company asks "How did you build this?", you can say:
- "I used Shopify CLI for local development"
- "Edited sections and CSS in VSCode"
- "Live tested with `shopify theme dev`"
- "Pushed to Shopify with `shopify theme push`"
- "Used Git for version control"

**That's what they want to hear.** ✅

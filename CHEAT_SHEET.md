# ⚡ Shopify Theme CLI - Quick Reference

## Installation (One-time)

### Mac:
```bash
brew tap shopify/shopify
brew install shopify-cli
```

### Windows:
```bash
choco install shopify-cli
```

### Any OS (using npm):
```bash
npm install -g @shopify/cli
shopify version
```

---

## Essential Commands

### 1️⃣ Login to Shopify
```bash
shopify login --store your-store.myshopify.com
```
Example:
```bash
shopify login --store mycompany-dev.myshopify.com
```

### 2️⃣ Start Development Server (MAIN COMMAND)
```bash
shopify theme dev
```
- Starts local server (http://localhost:3000)
- Auto-syncs files to Shopify
- Browser auto-refreshes
- **Press Ctrl+C to stop**

### 3️⃣ Start with Custom Port
```bash
shopify theme dev --port 3001
```
- If port 3000 is busy

### 4️⃣ Start with Verbose Logging
```bash
shopify theme dev --verbose
```
- Shows all file changes
- Good for debugging

### 5️⃣ Push Files to Shopify (Final Deploy)
```bash
shopify theme push
```
- Uploads all files to store
- Creates new theme or updates existing

### 6️⃣ Pull from Shopify
```bash
shopify theme pull
```
- Downloads theme from store to local

### 7️⃣ Logout
```bash
shopify logout
```

---

## Typical Workflow

```bash
# Step 1: Navigate to theme folder
cd path/to/theme

# Step 2: Login (first time only)
shopify login --store company-store.myshopify.com

# Step 3: Start development server
shopify theme dev
# → Opens browser with preview
# → Ctrl+C to stop

# Step 4: Edit files in VSCode
# → Files auto-sync
# → Browser auto-refreshes

# Step 5: When done, push to Shopify
shopify theme push

# Step 6: Publish in Shopify admin (go live)
```

---

## Git Commands (For Version Control)

### Initialize repository (first time):
```bash
git init
```

### Check status:
```bash
git status
```

### Stage all changes:
```bash
git add .
```

### Commit changes:
```bash
git commit -m "Your message here"
```

### View commit history:
```bash
git log
```

### Create feature branch:
```bash
git checkout -b feature/hero-customization
```

### Switch branches:
```bash
git checkout main
```

### Merge branch:
```bash
git merge feature/hero-customization
```

---

## VSCode Shortcuts

| Action | Mac | Windows |
|--------|-----|---------|
| Open Terminal | Ctrl+` | Ctrl+` |
| Save File | Cmd+S | Ctrl+S |
| Find/Replace | Cmd+H | Ctrl+H |
| Go to File | Cmd+P | Ctrl+P |
| Comment Line | Cmd+/ | Ctrl+/ |
| Format Doc | Shift+Opt+F | Shift+Alt+F |
| Open Extensions | Cmd+Shift+X | Ctrl+Shift+X |

---

## Quick Problem Fixes

### Theme dev not working?
```bash
# Logout and login again
shopify logout
shopify login --store your-store.myshopify.com
shopify theme dev
```

### Port 3000 already in use?
```bash
# Use different port
shopify theme dev --port 3001
```

### Changes not syncing?
```bash
# Save file (Ctrl+S)
# Hard refresh browser (Ctrl+Shift+R)
# If still broken:
# Ctrl+C to stop
# shopify theme dev  (restart)
```

### Check Shopify CLI version:
```bash
shopify version
shopify theme --help
```

---

## Common Paths

### On Mac/Linux:
```bash
cd ~/Desktop/Assesment-Ai/theme
```

### On Windows:
```bash
cd C:\Users\YourName\Desktop\Assesment-Ai\theme
```

### Anywhere (using full path):
```bash
cd /full/path/to/Assesment-Ai/theme
```

---

## File Locations (Common Edits)

```
theme/
├── assets/purelane.css          ← Edit styles
├── assets/purelane.js           ← Edit animations
├── sections/hero.liquid         ← Edit hero
├── sections/featured-products.liquid  ← Edit products
├── config/settings_schema.json  ← Edit settings
└── templates/index.json         ← Edit homepage structure
```

---

## Environment Check

Verify everything is installed:

```bash
# Check Node
node --version

# Check npm
npm --version

# Check Shopify CLI
shopify version

# Check Git (if using)
git --version
```

All should return version numbers ✅

---

## Terminal Navigation

```bash
# Current folder
pwd

# List files
ls              # Mac/Linux
dir             # Windows

# Change folder
cd foldername
cd ..           # Go up one level

# Create folder
mkdir foldername

# Clear terminal
clear           # Mac/Linux
cls             # Windows
```

---

## Emergency Commands

### Kill port (if stuck):
```bash
# Mac/Linux:
lsof -ti:3000 | xargs kill -9

# Windows:
netstat -ano | findstr :3000
taskkill /PID [PID] /F
```

### Reset everything:
```bash
# Logout
shopify logout

# Remove node_modules (if exists)
rm -rf node_modules

# Reinstall
npm install

# Login again
shopify login --store your-store.myshopify.com

# Start fresh
shopify theme dev
```

---

## Success Indicators

✅ `shopify theme dev` shows:
```
⚙️  Uploading...
📱 Preview URL: https://your-store.myshopify.com?preview_theme_id=123456789
🔄 Syncing files...
✅ Ready for editing
```

✅ Browser opens automatically with preview

✅ Edit a file → Save → Browser auto-refreshes

---

## Show to Company

When recruiter asks "How did you do this?":

**Answer:**
```
"I set up a local development environment using:
- Shopify CLI for theme development
- VSCode for editing Liquid/CSS
- shopify theme dev for live preview
- Git for version control

Changes were tested locally before pushing to Shopify 
with 'shopify theme push' and published in the admin."
```

**That's professional.** ✅

---

## Keep This Handy!

Bookmark this file. You'll reference it constantly during development.

**Most common commands:**
```bash
shopify login --store [STORE]
shopify theme dev
shopify theme push
shopify logout
```

That's 90% of what you'll do. 🚀

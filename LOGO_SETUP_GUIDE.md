# How to Add Your Logo to the Sailstack Website

Your website is now configured to display your logo. Follow one of these methods to upload your logo file to GitHub.

---

## 🎨 Logo Requirements

Before uploading, make sure your logo file meets these specifications:

- **File name:** `logo.png` (exactly this name)
- **Format:** PNG (recommended) with transparent background
  - Alternative formats: JPG, SVG, or WebP (update the filename in index.html if using these)
- **Recommended size:** 400px wide × 100-200px tall
- **Max file size:** Under 500KB for optimal loading speed
- **Background:** Transparent (PNG) works best for light/dark themes

---

## Method 1: Upload via GitHub Web Interface (Easiest)

This method requires no command line knowledge.

### Step-by-Step Instructions:

1. **Go to your repository on GitHub**
   - Visit: `https://github.com/ashercarriero-lab/sailstack-site`
   - Make sure you're on the `claude/sailstack-website-refurbish-011CUJvcfVvcV9JKZKXNVPJK` branch
   - You can switch branches using the branch dropdown (top left, near the file list)

2. **Navigate to the root folder**
   - You should see files like `index.html`, `FORM_SETUP.md`, etc.
   - This is where your logo needs to go

3. **Click "Add file" → "Upload files"**
   - Located in the top right of the file list
   - Or use the direct link: `https://github.com/ashercarriero-lab/sailstack-site/upload/claude/sailstack-website-refurbish-011CUJvcfVvcV9JKZKXNVPJK`

4. **Drag and drop your logo file**
   - Make sure it's named exactly: `logo.png`
   - Or use the "choose your files" link to browse

5. **Commit the upload**
   - Scroll down to the commit section
   - Commit message: `Add Sailstack logo`
   - Description (optional): `Upload company logo for header and footer`
   - Click **"Commit changes"**

6. **Deploy your website**
   - If you're using GitHub Pages, Netlify, or Vercel, the site will auto-deploy
   - Otherwise, pull the changes to your hosting server

---

## Method 2: Upload via Command Line (Git)

If you're comfortable with the command line, this method is faster.

### Prerequisites:
- Git installed on your computer
- Repository cloned to your local machine

### Step-by-Step Instructions:

1. **Make sure you're on the correct branch**
   ```bash
   cd /path/to/sailstack-site
   git status
   ```
   You should see: `On branch claude/sailstack-website-refurbish-011CUJvcfVvcV9JKZKXNVPJK`

   If not, switch to it:
   ```bash
   git checkout claude/sailstack-website-refurbish-011CUJvcfVvcV9JKZKXNVPJK
   ```

2. **Copy your logo file to the repository root**
   ```bash
   cp /path/to/your/logo.png /path/to/sailstack-site/logo.png
   ```

   Or on Windows:
   ```cmd
   copy C:\path\to\your\logo.png C:\path\to\sailstack-site\logo.png
   ```

3. **Add the logo to Git**
   ```bash
   git add logo.png
   ```

4. **Commit the change**
   ```bash
   git commit -m "Add Sailstack logo"
   ```

5. **Push to GitHub**
   ```bash
   git push origin claude/sailstack-website-refurbish-011CUJvcfVvcV9JKZKXNVPJK
   ```

6. **Verify the upload**
   - Go to your repository on GitHub
   - You should see `logo.png` in the file list
   - Click on it to preview

---

## Method 3: Upload via GitHub Desktop (Mac/Windows)

If you use GitHub Desktop, this is the most visual approach.

### Step-by-Step Instructions:

1. **Open GitHub Desktop**
   - Make sure your repository is selected
   - Switch to branch: `claude/sailstack-website-refurbish-011CUJvcfVvcV9JKZKXNVPJK`

2. **Copy logo to repository folder**
   - Right-click the repository in GitHub Desktop
   - Click "Open in Finder" (Mac) or "Open in Explorer" (Windows)
   - Copy your `logo.png` file to this folder

3. **Commit the change**
   - GitHub Desktop will automatically detect the new file
   - You'll see `logo.png` listed in the "Changes" tab
   - Add a commit message: `Add Sailstack logo`
   - Click **"Commit to claude/sailstack-website-refurbish-011CUJvcfVvcV9JKZKXNVPJK"**

4. **Push to GitHub**
   - Click **"Push origin"** button (top right)

---

## Testing Your Logo

After uploading, test that it appears correctly:

1. **View on GitHub**
   - Navigate to your repository
   - Click on `logo.png` to preview it

2. **View on your website**
   - Visit your deployed website
   - The logo should appear in:
     - Top left of navigation bar (next to "Sailstack")
     - Footer (next to "Sailstack")
   - If it doesn't appear immediately, try hard-refreshing: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)

3. **Check both locations**
   - The logo appears twice on every page:
     - **Header:** Top left navigation
     - **Footer:** Bottom center

---

## Troubleshooting

### Logo doesn't appear on the website

**Possible causes:**

1. **Wrong filename**
   - Make sure it's named exactly: `logo.png` (lowercase)
   - No spaces, no special characters

2. **Wrong location**
   - Logo must be in the root folder (same folder as index.html)
   - NOT in a subfolder like `images/` or `assets/`

3. **File not deployed**
   - If using hosting service, make sure changes were deployed
   - Check hosting dashboard for deployment status

4. **Browser cache**
   - Hard refresh: `Ctrl+Shift+R` or `Cmd+Shift+R`
   - Or clear browser cache

5. **Different file format**
   - If your logo is `logo.jpg` or `logo.svg`, update line 132 in index.html:
     ```html
     <img src="logo.jpg" alt="Sailstack Logo" class="logo-img" onerror="this.style.display='none'">
     ```

### Logo appears but looks blurry or pixelated

- Upload a higher resolution version
- Recommended minimum: 400px wide
- For retina displays: 800px wide

### Logo is too big or too small

Edit the CSS in index.html (line 34-37):

```css
.logo-img {
    height: 40px;  /* Change this value */
    width: auto;
}
```

Try different heights: 30px, 50px, 60px, etc.

---

## Alternative: Using a Different Logo Format

If you want to use SVG, JPG, or WebP instead of PNG:

1. **Upload your file** (e.g., `logo.svg`)
2. **Update index.html** on lines 132 and 458:

   Change:
   ```html
   <img src="logo.png" alt="Sailstack Logo" class="logo-img" onerror="this.style.display='none'">
   ```

   To:
   ```html
   <img src="logo.svg" alt="Sailstack Logo" class="logo-img" onerror="this.style.display='none'">
   ```

---

## What Happens if No Logo is Uploaded?

The website is designed to work with or without a logo:

- **With logo:** Shows logo image + "Sailstack" text
- **Without logo:** Shows only "Sailstack" text with gradient styling
- The `onerror="this.style.display='none'"` attribute hides the broken image icon if logo.png doesn't exist

---

## Design Tips for Your Logo

For the best appearance on the website:

1. **Transparent background** (PNG format)
   - Looks professional on both light and dark sections
   - No white/colored box around your logo

2. **Horizontal orientation**
   - Works best in the navigation bar
   - Aim for 3:1 or 4:1 width-to-height ratio

3. **Simplified design**
   - Small details may not be visible at 40px height
   - Bold, clear shapes work best

4. **Color contrast**
   - Ensure logo is visible on white background
   - If you have a light-colored logo, add a subtle stroke/outline

---

## Need Help?

If you run into issues:

1. **Check the filename:** Must be exactly `logo.png`
2. **Check the location:** Must be in root folder (same as index.html)
3. **Check file format:** PNG recommended
4. **Clear your browser cache:** Hard refresh with `Ctrl+Shift+R`

If problems persist, you can:
- Temporarily use the gradient "Sailstack" text (looks great!)
- Reach out for technical support
- Use Method 1 (GitHub web interface) which is the most reliable

---

## Quick Reference

| Task | Command/Action |
|------|----------------|
| Upload via web | GitHub → Add file → Upload files → Drag logo.png |
| Upload via CLI | `git add logo.png && git commit -m "Add logo" && git push` |
| Test deployment | Visit website, check header and footer |
| Change logo size | Edit `.logo-img` height in index.html (line 34) |
| Use different format | Update `src="logo.png"` in index.html (lines 132, 458) |

---

**Your website now has a clean, modern AI startup aesthetic with logo support!**

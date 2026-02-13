# Portfolio Setup Guide: GitHub Pages

## What You're Creating

A professional portfolio website hosted on GitHub Pages (completely free) that showcases your technical writing samples. Your site will be live at: `https://yourusername.github.io`

---

## Part 1: Setting Up GitHub Pages (First Time)

### Step 1: Create a GitHub Account
1. Go to https://github.com
2. Click "Sign up"
3. Choose a professional username (e.g., mandyhathaway, mandy-hathaway)
   - This will be part of your portfolio URL
   - Keep it simple and professional

### Step 2: Create Your Portfolio Repository
1. Once logged in, click the "+" icon in the top right
2. Select "New repository"
3. **Repository name**: `yourusername.github.io`
   - Replace `yourusername` with YOUR actual GitHub username
   - Example: If your username is "mandyhathaway", name it "mandyhathaway.github.io"
4. **Description**: "Technical Writing Portfolio"
5. Select "Public"
6. Check "Add a README file"
7. Click "Create repository"

### Step 3: Upload Your Portfolio Files

**Option A: Using GitHub's Web Interface (Easier for Beginners)**

1. In your new repository, click "Add file" → "Upload files"
2. Drag and drop these files:
   - `index.html`
   - `style.css`
   - `sample-style.css`
3. In the commit message box, type: "Initial portfolio setup"
4. Click "Commit changes"

5. Click "Add file" → "Create new file"
6. In the name field, type: `samples/python-functions.html`
   - The forward slash creates a folder automatically
7. Copy and paste the content from `python-functions.html`
8. Commit the file

**Option B: Using Git (Command Line) - More Professional**

```bash
# 1. Navigate to where you want to store your portfolio
cd ~/Documents

# 2. Clone your repository
git clone https://github.com/yourusername/yourusername.github.io.git
cd yourusername.github.io

# 3. Copy your portfolio files into this folder
# (Copy index.html, style.css, sample-style.css, and the samples folder)

# 4. Add all files to git
git add .

# 5. Commit the files
git commit -m "Initial portfolio setup with Python functions sample"

# 6. Push to GitHub
git push origin main
```

### Step 4: Enable GitHub Pages
1. In your repository, click "Settings" (top right)
2. Scroll down to "Pages" in the left sidebar
3. Under "Source", select "Deploy from a branch"
4. Under "Branch", select "main" and "/root"
5. Click "Save"
6. Wait 2-3 minutes
7. Your site will be live at: `https://yourusername.github.io`

---

## Part 2: Customizing Your Portfolio

### Update Your Information

**In `index.html`:**

Find and replace:
- Line 11: Change the title if desired
- Line 16: Your name (already correct!)
- Line 17: Update tagline if you want
- Lines 28-29: Update the "About Me" section with your own words
- Lines 69-71: Update contact links:
  ```html
  <a href="mailto:Hathaway.MandyL@gmail.com" class="contact-btn">Email Me</a>
  <a href="https://linkedin.com/in/YOUR-PROFILE" class="contact-btn">LinkedIn</a>
  <a href="https://github.com/YOUR-USERNAME" class="contact-btn">GitHub</a>
  ```

**Colors/Design (Optional):**
In `style.css`, line 28-29, you can change the header gradient colors:
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

Try these color combinations:
- Blue: `#667eea 0%, #4299e1 100%`
- Green: `#48bb78 0%, #38a169 100%`
- Teal: `#38b2ac 0%, #319795 100%`

---

## Part 3: Adding More Writing Samples

When you create your next portfolio piece, follow these steps:

### Step 1: Write Your Content in Markdown First

Create your content in a `.md` file (like the Python functions example). This makes it easier to draft and edit.

Example structure:
```markdown
# Title of Your Document

## Overview
Brief introduction...

## Section 1
Content...

## Section 2
Content...
```

### Step 2: Convert to HTML

Use this template for new samples:

1. Copy `samples/python-functions.html` 
2. Rename it (e.g., `samples/api-documentation.html`)
3. Update the content between `<article class="documentation">` tags
4. Update the `<title>` tag
5. Update the breadcrumb and footer links

### Step 3: Add to Your Portfolio Homepage

In `index.html`, add a new sample card in the `<section id="portfolio">` section:

```html
<div class="sample-card">
    <h3>Your New Sample Title</h3>
    <p class="sample-type">Document Type (Tutorial, API Docs, How-To, etc.)</p>
    <p>Brief description of what this sample demonstrates.</p>
    <div class="sample-meta">
        <span class="audience">Audience: Who it's for</span>
        <span class="length">Length: ~X words</span>
    </div>
    <a href="samples/your-new-sample.html" class="btn">Read Sample</a>
</div>
```

### Step 4: Upload to GitHub

**Web Interface:**
1. Navigate to your repository
2. Go to the `samples` folder
3. Click "Add file" → "Upload files"
4. Upload your new HTML file
5. Commit

**Git Command Line:**
```bash
cd ~/path/to/yourusername.github.io
git add samples/your-new-sample.html
git commit -m "Add new writing sample: [Sample Name]"
git push origin main
```

Wait 1-2 minutes for GitHub Pages to update.

---

## Sample Ideas for Your Next Portfolio Pieces

### Sample 2: Tutorial (Step-by-Step)
**Good topics for you:**
- "Getting Started with Scratch: Create Your First Animation"
- "Building Your First Website with HTML and CSS"
- "Python Basics: Variables and Data Types"
- "How to Set Up a Development Environment for Python"

**Structure:**
1. What you'll build/learn
2. Prerequisites
3. Step 1, 2, 3... (numbered, detailed)
4. Testing/verification
5. Next steps

### Sample 3: How-To Guide (Task-Based)
**Good topics:**
- "How to Debug Common Python Errors"
- "How to Use Git and GitHub for Version Control"
- "How to Create Interactive Elements in Scratch"
- "How to Organize Your Code with Functions"

**Structure:**
1. Goal statement
2. Prerequisites
3. Steps to complete the task
4. Troubleshooting section
5. Related tasks

### Sample 4: API Documentation
**Options:**
- Document a public API (OpenWeatherMap, GitHub API)
- Create mock API documentation for a fictional service
- Document Scratch's API (if available)

**Structure:**
1. Overview
2. Authentication
3. Endpoints (with request/response examples)
4. Error codes
5. Rate limits

### Sample 5: Reference Documentation
**Good topics:**
- "Python String Methods Reference"
- "Scratch Blocks Reference Guide"
- "HTML Tags Quick Reference"

**Structure:**
- Organized by category
- Each item: name, description, syntax, parameters, examples
- Clear, scannable format

---

## Portfolio Growth Strategy

### Phase 1: 3 Core Samples (First Month)
1. ✅ Conceptual doc (Python Functions) - Done!
2. Tutorial or How-To (your choice)
3. API documentation or Reference guide

### Phase 2: Expand (Months 2-3)
4. Advanced tutorial
5. Another doc type you haven't done
6. Real-world example (contribute to open source, document actual software)

### Phase 3: Specialize (Month 3+)
Focus on the type of technical writing you want to do:
- **Developer documentation**: More API docs, SDK guides
- **Educational content**: More tutorials, learning paths
- **User documentation**: User guides, help articles

---

## Tips for Creating Strong Samples

### 1. Choose Real Tools/Technologies
Document actual software, even if it's a tutorial. This shows you can research and understand real products.

### 2. Include Code Examples
Every technical writing sample should have code blocks showing actual, working code.

### 3. Add Screenshots/Diagrams
- Use screenshot tools (macOS: Cmd+Shift+4, Windows: Snipping Tool)
- Save as .png files
- Create an `images` folder in your repository
- Reference in HTML: `<img src="../images/screenshot.png" alt="Description">`

### 4. Test Everything
If you're writing a tutorial, actually follow your own steps. Code examples should work.

### 5. Get Feedback
- Post in Write the Docs Slack
- Ask developer friends to review
- Share with other technical writers

### 6. Show Different Styles
Vary your samples to show you can write for different audiences:
- One for complete beginners
- One for intermediate users
- One for developers

---

## Maintaining Your Portfolio

### Regular Updates
- Add new samples every 2-4 weeks while job searching
- Update existing samples if you learn better techniques
- Keep your GitHub commit history active (shows you're engaged)

### Tracking Changes
Every time you update:
```bash
git add .
git commit -m "Descriptive message about what changed"
git push origin main
```

Good commit messages:
- "Add tutorial: Getting Started with Python"
- "Update Python functions doc with more examples"
- "Fix typos in API documentation sample"

---

## Common Issues and Solutions

### Issue: Changes Don't Show Up
**Solution:** GitHub Pages can take 1-5 minutes to update. Clear your browser cache or try an incognito window.

### Issue: Broken Links
**Solution:** Check file paths. From `index.html`, samples are at `samples/filename.html`. From inside `samples/`, go back with `../index.html`.

### Issue: Formatting Looks Wrong
**Solution:** Make sure CSS files are linked correctly:
- In `index.html`: `<link rel="stylesheet" href="style.css">`
- In sample pages: `<link rel="stylesheet" href="../sample-style.css">`

### Issue: Can't Push to GitHub
**Solution:** You might need to set up authentication:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

---

## Next Steps After Portfolio is Live

1. **Add to resume**: Include your portfolio URL prominently
2. **Update LinkedIn**: Add portfolio link to your profile
3. **Share on social media**: Post about your new portfolio (shows initiative)
4. **Get feedback**: Share in Write the Docs community
5. **Keep building**: One new sample every 2-3 weeks

---

## Quick Reference: File Structure

Your final portfolio should look like this:

```
yourusername.github.io/
├── index.html                    (Homepage)
├── style.css                     (Homepage styles)
├── sample-style.css              (Sample page styles)
├── samples/
│   ├── python-functions.html
│   ├── api-documentation.html   (your next sample)
│   ├── tutorial-scratch.html    (another sample)
│   └── ...more samples
├── images/                       (optional, for screenshots)
│   ├── screenshot1.png
│   └── diagram1.png
└── README.md                     (GitHub repository description)
```

---

## Resources

- **GitHub Pages Documentation**: https://pages.github.com/
- **Markdown Guide**: https://www.markdownguide.org/
- **HTML Reference**: https://developer.mozilla.org/en-US/docs/Web/HTML
- **Git Tutorial**: https://try.github.io/

---

You're ready to launch your portfolio! 🚀

Once it's live, you'll have a professional portfolio that:
- Shows your technical writing abilities
- Demonstrates you can use Git/GitHub
- Proves you can create and publish web content
- Gives hiring managers something tangible to review

**Remember**: Your portfolio is never "finished." Start with your Python functions sample, get it live, then keep adding to it as you learn and grow.

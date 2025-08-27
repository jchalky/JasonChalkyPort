# Jason Chalky Portfolio Website

Personal portfolio website for Jason Chalky (Program Analyst) built with Bootstrap, HTML5, CSS3, and JavaScript. Deployed via GitHub Pages using Jekyll.

**Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.**

## Working Effectively

### Bootstrap and Run the Site
- **Install Jekyll and dependencies:**
  ```bash
  gem install --user-install jekyll bundler
  export PATH="$PATH:/home/runner/.local/share/gem/ruby/3.2.0/bin"
  ```
  
- **OPTION 1 - Jekyll Development Server (Recommended):**
  ```bash
  jekyll serve --port 4000
  ```
  - **Timing:** Starts in ~2 seconds. NEVER CANCEL.
  - **Access:** http://localhost:4000
  - **Auto-rebuild:** Watches for file changes

- **OPTION 2 - Simple Python HTTP Server:**
  ```bash
  python3 -m http.server 8000
  ```
  - **Timing:** Starts immediately. 
  - **Access:** http://localhost:8000
  - **Note:** No auto-rebuild, manual refresh needed

### Build the Site
- **Jekyll build:**
  ```bash
  jekyll build
  ```
  - **Timing:** Completes in ~0.35 seconds. NEVER CANCEL. Set timeout to 60+ seconds.
  - **Output:** Creates `_site/` directory with generated static files
  - **Note:** `_site/` is ignored by git via `.gitignore`

### Validation and Quality Assurance
- **Install validation tools:**
  ```bash
  npm install -g htmlhint jshint
  ```
  - **Timing:** Takes ~5 seconds. NEVER CANCEL.

- **Validate HTML:**
  ```bash
  htmlhint index.html
  ```
  - **Timing:** ~0.11 seconds
  - **Expected:** May show 1 tag-pair warning (existing, non-critical)

- **Validate JavaScript:**
  ```bash
  jshint js/scripts.js
  ```
  - **Timing:** ~0.11 seconds
  - **Expected:** ES6 syntax warnings (existing, non-critical)

## Validation Scenarios

**ALWAYS manually validate any new code changes with these complete end-to-end scenarios:**

### Scenario 1: Basic Navigation Test
1. Start the development server using Jekyll or Python
2. Navigate to http://localhost:4000 or http://localhost:8000
3. **Verify homepage loads:** Check that Jason Chalky's photo, name, and "Program Analyst - Web Developer - Power Apps" tagline display
4. **Test navigation:** Click "Portfolio" and "About" links to verify smooth scrolling
5. **Check sections:** Verify Portfolio section shows FIT Testing, Inventory, and HRO project cards
6. **Verify About section:** Confirm Army Veteran bio and resume download link display

### Scenario 2: Resume Download Test
1. Navigate to the About section
2. Click "My Resume" button
3. **Verify:** Browser initiates download of `ChalkyResumeNew.docx` file

### Scenario 3: Responsive Design Test
1. Resize browser window to mobile width (320px)
2. **Verify:** Navigation collapses to hamburger menu
3. **Verify:** Layout remains functional and readable

### Scenario 4: External Links Test
1. Navigate to footer section
2. Click LinkedIn link
3. **Verify:** Link points to `www.linkedin.com/in/jason-chalkyVA` (may not load due to external redirect)

## Deployment

The site automatically deploys to GitHub Pages via the Jekyll workflow in `.github/workflows/jekyll-gh-pages.yml`:

- **Trigger:** Push to `main` branch
- **Build time:** ~2-3 minutes on GitHub Actions. NEVER CANCEL.
- **Live site:** Available at GitHub Pages URL after successful deployment
- **Workflow:** Uses `actions/jekyll-build-pages@v1` for building

## Common Tasks

### Repository Structure
```
/home/runner/work/JasonChalkyPort/JasonChalkyPort/
├── .github/
│   ├── workflows/jekyll-gh-pages.yml    # GitHub Pages deployment
│   └── copilot-instructions.md          # This file
├── assets/                              # Images, resume, favicon
│   ├── MyPic.png                       # Profile photo
│   ├── ChalkyResumeNew.docx            # Resume download
│   └── img/portfolio/                  # Portfolio project images
├── css/styles.css                      # Bootstrap + custom styles (11,045 lines)
├── js/scripts.js                       # JavaScript functionality (54 lines)
├── index.html                          # Main portfolio page (434 lines)
├── .gitignore                          # Excludes _site/ and build artifacts
└── README.md                           # Project description
```

### File Sizes and Content
- **index.html:** 434 lines - Main portfolio page with all content
- **css/styles.css:** 11,045 lines - Bootstrap CSS + custom theme styles
- **js/scripts.js:** 54 lines - Navbar behavior and Bootstrap ScrollSpy
- **Total project:** Small, focused portfolio site

### Making Content Changes
- **Update bio:** Edit the About section in `index.html`
- **Add portfolio items:** Add new portfolio project sections in the Portfolio area
- **Update contact info:** Modify footer section in `index.html`
- **Change styling:** Edit `css/styles.css` (careful with Bootstrap overrides)

### Key Dependencies
- **Bootstrap:** Loaded via CDN for UI components and responsive grid
- **Font Awesome:** Icons loaded via CDN
- **Google Fonts:** Montserrat and Lato fonts via CDN
- **Jekyll:** For GitHub Pages deployment only

## Important Notes

- **External resources:** Some CDN resources may be blocked in certain environments (FontAwesome, Google Fonts) but site remains functional
- **Bootstrap modals:** Portfolio item modals require Bootstrap JavaScript to function properly
- **GitHub Pages:** Site automatically rebuilds and deploys when changes are pushed to main branch
- **Jekyll compatibility:** Site works as both static HTML and Jekyll site
- **No backend:** Pure frontend site with no server-side processing required

## Troubleshooting

- **Jekyll build fails:** Ensure Ruby and Jekyll are properly installed
- **Images not loading:** Check file paths in `assets/` directory
- **Styling issues:** Verify `css/styles.css` loads correctly
- **JavaScript errors:** Check browser console for CDN loading issues
- **Performance:** Site should load quickly as it's primarily static content
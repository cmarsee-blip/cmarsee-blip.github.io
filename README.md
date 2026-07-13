# Personal site

A static portfolio + blog, no build step required. Plain HTML/CSS/JS, ready for GitHub Pages.

```
personal-site/
├── index.html                          Homepage (hero, projects, about, blog teaser)
├── blog/
│   ├── index.html                      Blog listing
│   ├── why-i-rebuilt-my-site.html      Sample post
│   └── notes-on-shipping-side-projects.html
├── css/style.css
├── js/main.js
└── .nojekyll
```

## 1. Personalize it

Everything is placeholder content for "Cody Marsee" — find and replace with your own:

- **Name & title** — `<title>` tags, the logo in the header, hero heading, footer copyright
- **Bio** — the About section in `index.html`
- **Projects** — the three `.entry` blocks under `#projects` in `index.html`
- **Skills** — the `.skill-list` tags in the About section
- **Social links** — `mailto:`, GitHub, LinkedIn, X links in the footer (appears on every page)
- **Blog posts** — edit the two sample posts or delete them and duplicate the file structure for new ones (copy a post file, change the title/content, then link it from both `index.html`'s blog teaser and `blog/index.html`)

A quick way to catch most of it:

```
grep -rn "Cody Marsee\|yourusername\|example.com" .
```

## 2. Preview locally

No server needed — just open `index.html` in a browser. All links are relative, so this works identically before and after it's on GitHub.

## 3. Put it on GitHub

You said you've already got a GitHub account with other repos — here's the part that's specific to this site:

1. **Create a new repository.**
   - Name it `yourusername.github.io` (using your actual GitHub username) if you want the site at the root of that domain — this is the only name that gets that behavior.
   - Any other name (e.g. `personal-site`) also works, but the site will live at `yourusername.github.io/repo-name/` instead.
2. **Push these files to it:**
   ```bash
   cd personal-site
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/yourusername/REPO-NAME.git
   git push -u origin main
   ```
3. **Enable Pages:** in the repo, go to _Settings → Pages_, set **Source** to "Deploy from a branch", pick the `main` branch and `/ (root)` folder, and save.
4. GitHub gives you a URL (usually live within a minute or two) — either `https://yourusername.github.io` or `https://yourusername.github.io/repo-name/`.

### Optional: custom domain

If you own a domain, add a `CNAME` file at the repo root containing just your domain (e.g. `yourname.com`), then point your DNS at GitHub's Pages IPs / `yourusername.github.io` per [GitHub's custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site). Settings → Pages will also prompt you for this once Pages is enabled.

## Notes

- Fonts (Fraunces, Inter, IBM Plex Mono) load from Google Fonts via CDN — no local font files to manage.
- The `.nojekyll` file stops GitHub from running its default Jekyll build, so the site is served exactly as-is.
- No JS framework, no npm install, no build step — editing HTML/CSS directly is the workflow.

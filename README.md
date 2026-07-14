# cmarsee-blip.github.io

My personal portfolio and blog — built as a static site, no framework or build step.

**Live:** [cmarsee-blip.github.io](https://cmarsee-blip.github.io)

## About this site

A portfolio covering my TripleTen software engineering projects and a blog where I write about the switch from sports and construction into software. The design has a running baseball motif throughout — projects and posts are numbered as "innings," and section dividers use an alternating stitch pattern styled after baseball seams.

## Structure

```
├── index.html                                 Homepage — hero, projects, about, blog teaser
├── blog/
│   ├── index.html                              Blog listing
│   └── my-path-into-software-engineering.html  First post
├── css/style.css
├── js/main.js
└── .nojekyll
```

## Tech stack

Plain HTML, CSS, and vanilla JavaScript. No build tools, no dependencies to install — editing a file and pushing is the whole workflow. Fonts (Fraunces, Inter, IBM Plex Mono) load from Google Fonts via CDN.

## Editing locally

Open `index.html` directly in a browser — all links are relative, so it works fully offline, no server required.

## Adding a new blog post

1. Duplicate an existing post file in `blog/` and rename it.
2. Update the `<title>`, date, read time, and content inside.
3. Add a matching entry (with the next "Inning" number) to `blog/index.html` and, if it should show on the homepage teaser, to `index.html` as well.
4. Commit and push:
   ```bash
   git add .
   git commit -m "Add new post: <title>"
   git push
   ```

## Adding a new project

Copy one of the `.entry` blocks under `#projects` in `index.html`, update the title, description, tags, and links, and give it the next sequential inning number.

# AIDMS Static Website for GitHub Pages

This folder contains a complete static website. Every main page is a separate HTML file:

- `index.html` - Home
- `research.html`
- `people.html`
- `projects.html`
- `publications.html`
- `teaching.html`
- `gallery.html`
- `news.html`
- `join.html`
- `contact.html`

Shared presentation files are in `assets/style.css` and `assets/site.js`.

## Option A — Publish from the GitHub website (easiest)

1. Sign in at GitHub and select **New repository**.
2. Enter a repository name such as `aidms-lab-website`, select **Public**, and click **Create repository**.
3. Keep this folder named `docs`. Upload the whole `docs` folder—with every HTML file and its `assets` subfolder—to the repository.
4. Commit the uploaded files to the default `main` branch.
5. Open **Settings → Pages** in the repository.
6. Under **Build and deployment**, choose **Deploy from a branch**.
7. Select branch `main`, select folder `/docs`, and click **Save**.
8. Wait for GitHub’s deployment message, then open the URL shown in Pages settings. It will normally resemble `https://USERNAME.github.io/REPOSITORY/`.

No compilation is required. GitHub Pages serves the HTML, CSS, and JavaScript directly.

## Option B — Publish with Git on your computer

After installing Git, create an empty GitHub repository and run these commands from the folder that contains `docs`:

```bash
git init
git add docs
git commit -m "Add AIDMS laboratory website"
git branch -M main
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```

Then enable GitHub Pages using steps 5–8 in Option A.

## Preview locally before publishing

Double-clicking `index.html` usually works. For a more accurate local preview, open a terminal in `docs` and run:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`. Stop the server with **Ctrl+C**.

## Edit content

Open the relevant `.html` file in a text editor. Search for square-bracket placeholders such as `[REPLACE]`, `[CONFIRM]`, and `[ADD]`. Replace them only with verified information.

The page-to-file mapping is direct: edit `research.html` for Research, `people.html` for People, and so on. Site-wide colors and layout are in `assets/style.css`; mobile-menu behavior is in `assets/site.js`.

### Change the navigation-tab font size

Open `docs/assets/style.css` and search for `.nav a`. The desktop navigation currently uses `font-size: 13px`; the narrower-laptop rule uses `11.5px`, and the mobile-menu rule uses `15px`. Change those three values together if you want the Research, People, Projects, Publications, Teaching, and other menu labels to be larger or smaller. Preview the Home page and one interior page before committing the change.

Before launch, search all files for:

- `[REPLACE` — required contact or identity information
- `[CONFIRM` — details that should be verified before publishing
- `[ADD` — optional files, links, photographs, or content still needed

## Add photographs

1. Create `docs/assets/images/` if it does not already exist.
2. Add compressed `.jpg`, `.png`, or `.webp` photographs. Use lowercase descriptive filenames without spaces.
3. In `gallery.html`, replace a placeholder block with:

```html
<img src="assets/images/descriptive-name.jpg" alt="Factual description of the photograph">
```

Add a factual caption, date, and credit. Confirm permission before publishing identifiable student photographs.

For the PI photograph, replace the placeholder in `people.html` with an image using the same pattern. Always include meaningful `alt` text.

## Update the site later

1. Open the file on GitHub.
2. Select the pencil icon to edit it.
3. Make the change and choose **Commit changes**.
4. GitHub Pages will rebuild the public site automatically.

Keep a copy of the previous text before major edits. For larger changes, create a new branch and merge it after review.

## Custom domain

After GitHub Pages is working, configure a custom domain under **Settings → Pages**. Follow GitHub's current DNS instructions for the selected domain. Add a `CNAME` file to this folder only after the domain is confirmed.

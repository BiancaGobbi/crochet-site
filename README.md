# Learn to Crochet

A one-page beginner's guide to crochet. It covers the tools you need, yarn weights and hook sizes, the five basic stitches, how to read pattern abbreviations, and a hand-picked list of free resources.

It's plain HTML and CSS, with no build step and no JavaScript:

- `index.html` holds all the content, including the stitch symbols, which are drawn as inline SVG.
- `styles.css` holds all the styling. The light and dark colour palettes are the variables at the top of the file.
- `tests/` holds automated checks. You don't need to upload this folder, but uploading it does no harm.

## Editing the resource links

The links are at the bottom of `index.html`, inside `<section id="resources">`, split into three groups: Video tutorials, Free patterns and Communities. To add a link, copy one `<li>` line in the right group and change the address, the name and the note:

```html
<li><a href="https://example.com/" target="_blank" rel="noopener">Site name</a> — one line on why it's good.</li>
```

Keep between 8 and 12 links in total. The checks below enforce that range.

## Running the checks

You need Python 3, which is already installed on macOS. Run these from this folder:

```bash
python3 -m unittest discover -s tests -v
```

```bash
python3 tests/check_links.py
```

The first command checks the page structure and content. The second visits every resource link and prints `OK`, `WARN` or `FAIL` for each. `WARN` means the site blocked the automated check, so open that link in your browser to confirm it works.

To preview the page, open `index.html` in your browser. Alternatively, run `python3 -m http.server` and visit http://localhost:8000.

## Deploying

### GitHub Pages

1. Create a new repository on GitHub. For a site at `https://<username>.github.io/`, name it `<username>.github.io`; any other name gives you `https://<username>.github.io/<repo>/`.
2. Push this folder to it:

   ```bash
   git remote add origin https://github.com/<username>/<repo>.git
   ```

   ```bash
   git push -u origin main
   ```

3. In the repository, go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, then branch `main` and folder `/ (root)`, and save. The site is live within a minute or two.

### Netlify

Go to https://app.netlify.com/drop and drag this folder onto the page. Netlify gives you a live URL straight away. You can rename the site in its settings.

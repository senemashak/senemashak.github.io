# Senem Işık — academic website

This folder contains an editable static website prepared for **senemashak.github.io**. There is no build command, package manager, database, or ChatGPT connection to maintain. Your text is in `index.html`; the appearance is in `styles.css`.

## 1. Preview the files

Extract the ZIP first, then open `index.html` in a web browser. Keep `styles.css`, both favicon files, and the `assets` folder next to it. The full-resolution photo is `assets/photo.png`.

Click any flower heading — Research, News, Experience, Teaching, or Expository — to show or hide that section. All five start closed. The page has no navigation menu; the headings themselves are the navigation.

## 2. Put the site on GitHub Pages

1. Sign in to your **senemashak** GitHub account. Create a repository named **`senemashak.github.io`**. Select **Public** and initialize it with a README so it has a `main` branch. If that repository already exists, review and back up its current contents before replacing anything. [1]
2. In the repository, choose **Add file → Upload files**. Upload the **contents of the extracted folder**, not the ZIP and not the outer folder. Include the `assets` folder itself so the photo stays at `assets/photo.png`. `index.html` must appear at the repository's top level. [2]
3. Save the upload with a commit message such as “Add academic website.” Commit to `main` when that option is available. If GitHub offers a new branch and pull request instead, merge that pull request into `main` before publishing. [2]
4. Open **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, select **`main`** and **`/ (root)`**, then click **Save**. [3]
5. Wait for the deployment to finish. The website will be at **https://senemashak.github.io/** after successful publication. GitHub notes that publication can take up to 10 minutes. The repository's **Actions** tab is useful for checking deployment progress or errors. [1, 3]

There is no need to connect GitHub to ChatGPT. This publishes a separate GitHub-hosted copy; it does **not** automatically change or synchronize the existing `chatgpt.site` address.

### Files to upload

```text
index.html             All website text, research entries, and links
styles.css             Fonts, colors, spacing, and responsive layout
favicon.svg            Flower used in the tab and Expository toggle
favicon.ico            Browser fallback for the same flower
assets/
  photo.png            Original 898 × 1282 photograph, unchanged
.nojekyll              Tells GitHub Pages to serve the static files directly
README.md              These setup and editing instructions
PROVENANCE.md          Reconstruction notes and items to review
.gitignore             Keeps common computer-generated files out of Git
```

Files beginning with a dot may be hidden by your computer. If `.nojekyll` does not upload, create it in GitHub using **Add file → Create new file**, name it `.nojekyll`, and put `Static HTML website` inside. Its presence is what matters. The `.gitignore` file is optional for browser-only editing.

Do not select a GitHub Pages theme, add a `_config.yml`, or configure an npm build for this package. The supplied `index.html` already defines the complete page.

## 3. Maintain it in GitHub's website

Open the file to change, click the **pencil / Edit** button, make the change, and click **Commit changes**. When the change reaches the publishing branch (`main`), GitHub Pages republishes the site. [3, 4]

### Change text or links

Edit `index.html` and search for the exact sentence to update. Leave the surrounding HTML tags in place. A link looks like this:

```html
<a href="https://example.org/">Visible words</a>
```

Change the quoted URL to change its destination. Change `Visible words` to change the label. For a literal ampersand in text, write `&amp;` (as in `MS&amp;E`). Keep the file in UTF-8 so **Işık**, **Türkiye**, and the pronunciation retain their characters.

### Add a news item

Find `<!-- NEWS` in `index.html`. Copy one complete `<li> ... </li>` block and paste it just after `<ol class="news-list">` for a newest-first update. Change the date in both places: the machine-readable `datetime="2026-06"` and the visible `Jun 2026`. Edit the paragraph and links. Do not create a second News section.

### Add a paper

Find `<!-- RESEARCH` and copy one complete `<article class="paper"> ... </article>` block. Update its title, authors, status, venues, and resources. Use `<strong>SI</strong>` for your name. Keep conference/workshop names inside `<em> ... </em>` to retain italics. Author and resource links automatically match their surrounding text; awards use `class="award"`.

### Update Experience, Teaching, or Expository

Each has an uppercase HTML comment to help you find it. Copy the appropriate complete `article` block for a new entry, keeping it inside that section's `<div class="toggle-content">`.

### Open or close a section by default

Research, News, Experience, Teaching, and Expository are each a `<details class="toggle">` element whose flower heading opens and closes it. All five start collapsed, so the page opens to the introduction, the photograph, and the five headings. To make one start expanded, add the word `open` to its opening tag, as in `<details id="research" class="section toggle" open>`; delete that word to collapse it again.

### Change the picture

Replace `assets/photo.png` with a new PNG of the same filename. The site shows the whole image without cropping. If its dimensions differ, update the image's `width` and `height` attributes in `index.html` so the browser can reserve the correct proportions while loading.

### Change colors or font sizes

The palette is at the top of `styles.css`. The page and titles use the same serif font family. The root `font-size: 84%` scales the text; changing that value changes the overall text size. Specific heading sizes are defined lower down. The photograph's width is set by the `160px` column in `.page-grid` and the matching `max-width` on `.portrait img`.

## 4. Check an update

Review the site on a wide screen and on your phone. Check the intro/photo divider, the email, a paper resource link, the flower toggle, and any URLs you changed. If the GitHub site still shows an old version, check that the deployment finished, then refresh the page.

The website itself has no analytics, third-party scripts, font downloads, or embedded credentials. Its one script, at the bottom of `index.html`, does a single thing: when someone arrives at an address ending in `#research` or another section name, it opens that section. With JavaScript switched off, every heading still opens by being clicked. The paper PDFs, posters, slides, and pronunciation audio are **external links**, not files included in this ZIP. Check the sharing permissions of those linked documents before relying on public access.

## Official GitHub instructions

[1] GitHub Pages quickstart: https://docs.github.com/en/pages/quickstart

[2] Upload files: https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

[3] Configure the publishing branch and folder: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

[4] Edit files in the browser: https://docs.github.com/en/repositories/working-with-files/managing-files/editing-files

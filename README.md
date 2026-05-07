# Personal Homepage

Single-page academic homepage for OpenReview. Plain HTML and CSS, no build step.

## Files

- `index.html` &mdash; the page
- `style.css` &mdash; styles
- `assets/photo.jpg` &mdash; headshot
- `assets/cv.pdf` &mdash; CV (optional, see below)

## Local preview

```bash
cd "$(dirname "$0")"
python3 -m http.server 8000
```

Open http://localhost:8000.

## Deploy on GitHub Pages

1. Create a new public repository named `<username>.github.io` (replace `<username>` with your GitHub login).
2. Push the contents of this folder to the `main` branch:
   ```bash
   git init
   git add .
   git commit -m "Initial homepage"
   git branch -M main
   git remote add origin https://github.com/<username>/<username>.github.io.git
   git push -u origin main
   ```
3. In the repository on GitHub, go to **Settings &rarr; Pages** and confirm "Deploy from a branch", branch `main`, folder `/ (root)`.
4. Wait a few minutes. The site appears at `https://<username>.github.io`.

## After deploy: register on OpenReview

1. Sign in to https://openreview.net.
2. Go to **Profile &rarr; Edit Profile**.
3. Add the deployed URL to the **Homepage** field.
4. Recommended: also add your institutional `.ac.kr` email as a secondary email so the profile is associated with the institution.

## Customization checklist

Before publishing, edit `index.html`:

- [ ] If you want to expose your CV, drop the file at `assets/cv.pdf` and uncomment the CV line under **Links**.
- [ ] Update the "Last updated" date in the footer.
- [ ] Add a Google Scholar link under **Links** once a profile exists.

## Things to leave out until after the review cycle

To stay clear of review-time anonymity concerns, do not announce specific paper submissions on this page while a paper is in double-blind review (e.g., wording like "currently in review at \[venue\]"). After acceptance, add a `Publications` section with the citation and a link to OpenReview.

## Adding a publications section later

Insert a new `<section>` in `index.html` between `Research Interests` and `Education`:

```html
<section>
  <h2>Publications</h2>
  <article class="entry">
    <div class="entry-head">
      <span class="entry-title">Title of the paper</span>
      <span class="entry-meta">Venue, Year</span>
    </div>
    <div class="entry-sub">Authors</div>
  </article>
</section>
```

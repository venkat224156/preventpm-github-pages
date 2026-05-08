# Prevent Pest Management Static Site

This project recreates `https://preventpm.com/` as a static HTML/CSS/JS website suitable for GitHub Pages.

## Files

- `index.html`
- `about.html`
- `services.html`
- `residential-services.html`
- `commercial-services.html`
- `contact.html`
- `404.html`
- `css/style.css`
- `js/script.js`
- `images/`

## Local Testing

1. Open a terminal in the project folder.
2. Start a simple local server:

```bash
python3 -m http.server 8000
```

3. Visit:

```text
http://localhost:8000/
```

4. Check all pages:

```text
http://localhost:8000/about.html
http://localhost:8000/services.html
http://localhost:8000/residential-services.html
http://localhost:8000/commercial-services.html
http://localhost:8000/contact.html
```

## GitHub Push Commands

Initialize and push the repo:

```bash
git init
git add .
git commit -m "Initial Prevent Pest Management static site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

If the remote already exists:

```bash
git add .
git commit -m "Update site"
git push origin main
```

## GitHub Pages Setup

1. Push the repository to GitHub.
2. Open the repo on GitHub.
3. Go to `Settings` -> `Pages`.
4. Under `Build and deployment`, choose:
   - `Source`: `Deploy from a branch`
   - `Branch`: `main`
   - `Folder`: `/ (root)`
5. Save the settings.
6. Wait for GitHub Pages to publish the site.
7. Confirm the published URL loads the home page and internal pages.

## DNS Cutover From SiteSwan To GitHub Pages

1. In GitHub Pages settings, add your custom domain if you will keep the same domain.
2. Create or update the `CNAME` file only if you are using a custom domain on GitHub Pages.
3. In your DNS provider:
   - Update the `A` records for the apex domain to GitHub Pages IPs.
   - Or point `www` with a `CNAME` record to `YOUR_USERNAME.github.io`.
4. Lower DNS TTL before cutover if possible.
5. After DNS changes propagate, verify:
   - The site loads over HTTPS
   - All page paths work
   - Form submissions post to Formspree correctly
6. Remove or disconnect the SiteSwan domain mapping only after GitHub Pages is confirmed live.

## Notes

- All paths in the site use relative links for GitHub Pages compatibility.
- Replace `https://formspree.io/f/YOUR_FORM_ID` with your real Formspree endpoint before launch.

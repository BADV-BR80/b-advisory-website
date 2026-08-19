# B Advisory website

A lightweight, single-page website for B Advisory. The site uses plain HTML and CSS with no build step, JavaScript, analytics, cookies, or external dependencies.

## Project structure

| File | Purpose |
| --- | --- |
| `index.html` | Main single-page website, content, metadata, and links |
| `styles.css` | Responsive layout, typography, color, and interaction styles |
| `favicon.svg` | Scalable browser icon |
| `404.html` | GitHub Pages–compatible not-found page |

## Preview locally

From the repository root, start any static file server. Python is one simple option:

```sh
python3 -m http.server 8000
```

Then visit [http://localhost:8000](http://localhost:8000). Because all assets use relative paths, opening `index.html` directly also works.

## Replace the link placeholders

Before publishing, replace every instance of these placeholders in `index.html`:

- `[BOOKING_URL]` — the full URL for the scheduling page
- `[LINKEDIN_URL]` — the full LinkedIn profile or company URL

They are intentionally repeated in the HTML so each link works without JavaScript. Find them quickly with:

```sh
rg '\[(BOOKING|LINKEDIN)_URL\]' index.html
```

Do not remove the surrounding quotation marks when replacing the values.

## Publish with GitHub Pages

1. Push the repository to GitHub.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the publishing branch and the `/ (root)` folder, then save.
5. Wait for GitHub Pages to report the temporary project URL and verify the site there.

No build action or custom workflow is required. The canonical metadata already points to `https://b-advisory.net`, but this repository does not configure or publish a custom domain. Add the domain separately only when its DNS is ready.

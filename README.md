# laplacegroup.io

Static website for [Laplace Group](https://laplacegroup.io), hosted with GitHub
Pages.

## Pages and URLs

- `/` — homepage (`index.html`).
- `/privacy/` — privacy policy (`privacy/index.html`).
- `/terms/` — terms of service (`terms/index.html`).

Use directory URLs with a trailing slash for page links and canonical URLs.
GitHub Pages serves each directory's `index.html`, so public links do not need
an `.html` suffix. The existing `.nojekyll` keeps publishing buildless; no
framework, Jekyll configuration or server rewrite rules are needed.

`privacy.html` is retained as a static redirect to `/privacy/`, with a visible
fallback link. It uses an HTML meta refresh, not an HTTP 301 redirect.
`motion-test.html` remains an unlinked diagnostic copy of the landing page.

The policy pages cover this website and email enquiries. Products and
services with different data practices need their own notices and agreements.
The privacy policy uses general language for technical data, cookies and
analytics; naming a possible use does not implement that feature. Keep it
aligned with actual practices as the website changes.

## Local preview

From the repository root, run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Visit `http://127.0.0.1:8000/`, `/privacy/` and `/terms/`. Check the footer links
and confirm that `/privacy.html` forwards to `/privacy/`. Both policy pages
and the redirect work without JavaScript.

## Publishing

GitHub Pages publishes the root of the `main` branch. DNS for the apex domain
and `www` is managed in Porkbun.

Pushing changes to `main` publishes the site automatically. After publishing,
check the homepage links, both policy URLs and the legacy privacy redirect.

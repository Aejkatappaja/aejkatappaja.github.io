# ~/aejkatappaja

A personal portfolio built on the web platform. One HTML file, no build step, no framework.

`no npm install` · `no build` · `single file` · `~64 KB` · `vanilla HTML/CSS/JS`

> Live: https://aejkatappaja.com · [GitHub](https://github.com/Aejkatappaja) · [LinkedIn](https://www.linkedin.com/in/frkj)

<!-- screenshot: drop a hero shot here, e.g. ./assets/preview.png -->

## Why no framework

Framework-agnostic by default: pick the right tool for the job. A static one-page portfolio has no router, no shared state and no server rendering, so it ships as a single HTML file and deploys by copying it. If it grew into many routes or shared UI, a framework would earn its place; for one page it would only add weight.

## What's inside

Vanilla here does not mean primitive. Most of the work is done by things the platform now ships natively.

- **Modern CSS, no preprocessor.** `oklch()` color tokens, `color-mix()` for derived tones and glows, cascade layers for predictable precedence. No Sass, no PostCSS.
- **Accessible by construction.** Semantic landmarks and labelled regions, a skip link, `aria-*` states (`aria-busy`, `aria-expanded`), `:focus-visible` rings, `prefers-reduced-motion`, and real `<time>`, `<dl>`, `<article>`, `<h1>`-`<h3>` structure.
- **~150 lines of JavaScript, JSDoc-typed.** Keyboard navigation (`1`-`6` jump to sections, `g/l/x/d/e` open links), a scroll-spy breadcrumb, a timezone clock, and live GitHub star counts.
- **Responsive**, with a terminal theme ("Sora").

## Dependencies

No build step and no npm dependencies. Nothing to install, nothing to audit.

The one network call at runtime is an optional `fetch` to the public GitHub API for live star counts. It is progressive enhancement: with JavaScript off, each star badge is a plain link to the repo's stargazers labelled `stars`; with JavaScript on, it fills in the live number, or shows `?` if the request is rate-limited or fails. Nothing else depends on it.

## Run

```sh
open index.html
```

Or serve the folder with any static server:

```sh
python3 -m http.server
```

## Deploy

Any static host works. For GitHub Pages: push the repo, enable Pages on the branch, done. After deploying, set the real URL in three places in `index.html` (`<link rel="canonical">`, `og:url`, and the JSON-LD `url`).

## Structure

```
index.html      # everything: <head> meta + JSON-LD, <style>, markup, <script>
assets/
  avatar.webp   # profile image
  og.png        # social share card (1200x630)
CNAME           # custom domain for GitHub Pages
README.md
```

## Stack

HTML, CSS, JavaScript.

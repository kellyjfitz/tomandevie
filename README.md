# Tom and Evie

This repository is now a lightweight SvelteKit site for Tom and Evie.

It is focused on:

- Photo display
- Simple gallery layouts
- Embedded videos

## Quick Start

```bash
npm install
npm run dev
```

Then open http://localhost:5173.

## Project Focus

- Main page content: `src/routes/+page.svelte`
- Global layout and styles: `src/routes/+layout.svelte`, `src/app.scss`
- Media components: `src/lib/components/Media/`
- Slide gallery components: `src/lib/components/MultimediaGallery/`

## Deploying to GitHub Pages

Push to `main` and the workflow in `.github/workflows/deploy.yml` builds and deploys the static site.

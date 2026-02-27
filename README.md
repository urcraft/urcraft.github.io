# urcraft.github.io (build output)

This repo hosts the generated Quartz static site that is served via GitHub Pages. Never edit this repo directly except for deploying new builds.

## Purpose
- `public/` build artifacts from `urcraft_website_source` are mirrored here.
- Files are committed to `master` branch and served from the repository root via GitHub Pages.
- Use this repo only when pushing `npx quartz build` output (HTML, CSS, JS, assets).

## Refresh workflow

1. In `urcraft_website_source`, run `npx.cmd quartz build`.
2. Copy `public/` into this repository (`site-build`) while keeping `.git`.
3. Commit the updated files with a message like `Publish Quartz build output`.
4. Push to `origin master`; the Pages workflow will redeploy.

## Troubleshooting

- If Pages fails, ensure `.github/workflows/deploy.yml` (in the source repo) runs and pushes to this repo.
- Use `robocopy /MIR <source>/public . /XD .git` to keep the repository clean before committing.
- Always verify the preview at `https://urcraft.github.io/` after pushing.

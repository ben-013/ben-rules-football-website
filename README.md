# Ben Rules Football

A static blog built with [Eleventy](https://www.11ty.dev/) and deployed to GitHub Pages.

## Project structure

- `src/posts/` - one Markdown file per post.
- `src/_includes/layouts/` - shared page layouts.
- `src/index.njk` - homepage template; automatically lists posts.
- `src/assets/` - styles, scripts, and images copied into the published site.
- `.github/workflows/deploy-pages.yml` - builds and deploys the site to GitHub Pages.
- `_site/` - generated website output; never edit or commit it.

## Requirements

Install the current Node.js LTS release before working on the site. Node includes npm, which installs and runs the project's development tools.

## Working locally

Install dependencies once, then start the local preview server:

```powershell
npm install
npm run start
```

Open the local address printed in the terminal (normally `http://localhost:8080`). The server rebuilds the site when you save a source file.

To create a production build locally:

```powershell
npm run build
```

This writes the published files to `_site/`.

## Adding a post

Create `src/posts/YYYY-MM-DD-post-slug.md`, copy the front matter from the existing post, and write the body in Markdown. The homepage and individual post page are generated automatically.

## Publishing

GitHub Pages is deployed by the `Deploy site to GitHub Pages` workflow. Every push to `main` builds and publishes the site automatically, so the normal publishing process is to merge a pull request into `main`.

Use **Actions -> Deploy site to GitHub Pages -> Run workflow** only to manually retry or redeploy the current `main` branch. In **Settings -> Pages**, the publishing source must remain set to **GitHub Actions**.

The deployment workflow sets the repository path prefix needed for GitHub Pages. Keep internal stylesheet, homepage, and post links path-prefix aware by using Eleventy's `url` filter (for example, `{{ '/assets/styles/main.css' | url }}`) rather than hard-coding a root-relative URL.

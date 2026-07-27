# Ben Rules Football

A static blog built with [Eleventy](https://www.11ty.dev/).

## Project structure

- `src/posts/` — one Markdown file per post.
- `src/_includes/layouts/` — shared page layouts.
- `src/index.njk` — homepage template; automatically lists posts.
- `src/assets/` — styles, scripts, and images copied into the published site.
- `_site/` — generated website output; never edit or commit it.

## Working locally

Install dependencies once, then start the local preview server:

```powershell
npm install
npm run start
```

Open the local address printed in the terminal (normally `http://localhost:8080`). Build production files with `npm run build`.

## Adding a post

Create `src/posts/YYYY-MM-DD-post-slug.md`, copy the front matter from the existing post, and write the body in Markdown. The homepage and individual post page are generated automatically.

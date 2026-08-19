# Josie's Log

Personal blog at [josiehong.github.io/blog](https://josiehong.github.io/blog/), built with [Hugo](https://gohugo.io/) and a small custom theme (`layouts/` + `static/`) that reuses the styles of [josiehong.github.io](https://josiehong.github.io) so the blog matches the homepage.

## Writing a new post

### 1. Create it

```bash
hugo new content posts/2026-08-19-my-post-title/index.md
```

Use the `YYYY-MM-DD-slug` folder naming — it becomes the URL (`/blog/posts/2026-08-19-my-post-title/`). The `index.md` is pre-filled from the template in `archetypes/posts.md`.

### 2. Write it

The post is plain Markdown. In the front matter:

- `categories` — one of `["Project"]` (blue chip), `["Study Notes"]` (gray chip), or `["Wild Thoughts"]` (yellow chip). A new category name also works and gets a default gray chip; to give it its own color, add a `.blog-tag--<slug>` rule in `static/blog.css`.
- `tags` — free-form, e.g. `tags: ["python", "mass-spec"]`. They appear on the post, on the Tags page, and in search.
- `summary` — one sentence, used for SEO/link previews.
- `draft: true` — keeps the post out of the published site. Delete the line (or set `false`) when it's ready.

In the body:

- **Images**: drop them in the same folder as `index.md` and reference them as `![caption](figure.png)`.
- **Math**: KaTeX renders everywhere — `$E = mc^2$` inline, `$$ ... $$` for display equations.
- **Code**: fenced blocks with a language (` ```python `) work as usual.
- Raw HTML is allowed if Markdown isn't enough (e.g. Gist embeds).

### 3. Preview

```bash
hugo server -D        # -D includes drafts; serves at http://localhost:1313/blog/
```

### 4. Publish

```bash
git add -A && git commit -m "New post" && git push
```

GitHub Actions rebuilds and deploys on every push to `main`; the post appears on the site, in Archive, Tags, and the search index within a minute or two.

## Keeping the style in sync

`static/main.css` is a copy of the homepage's `main.css`. After changing styles in the homepage repo, re-sync it:

```bash
cp ../josiehong.github.io/main.css static/main.css
```

Blog-only styles (post pages, search box, tag cloud) live in `static/blog.css`.

## Setup on a new machine

```bash
git clone git@github.com:josiehong/blog.git
brew install hugo
```

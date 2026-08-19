# Josie's Log

Personal blog at [josiehong.github.io/blog](https://josiehong.github.io/blog/), built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

## Writing a new post

```bash
hugo new content posts/2026-08-19-my-post-title/index.md
```

This creates a folder with an `index.md` pre-filled from the template. Write the post in Markdown; put images in the same folder and reference them as `![caption](image.png)`.

LaTeX math renders via KaTeX everywhere: `$E = mc^2$` inline, `$$ ... $$` for display equations.

Set `draft: false` (or delete the line) in the front matter when the post is ready.

## Previewing locally

```bash
hugo server -D        # -D includes drafts; serves at http://localhost:1313/blog/
```

## Publishing

```bash
git add -A && git commit -m "New post" && git push
```

GitHub Actions builds and deploys automatically on every push to `main`.

## Setup on a new machine

```bash
git clone --recurse-submodules git@github.com:josiehong/blog.git
brew install hugo
```

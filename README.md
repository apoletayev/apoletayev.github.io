# Andrey Poletayev

Personal site and blog. Hosted on GitHub Pages.

## Architecture

Single-page app with no build step. `index.html` is the shell — it handles client-side hash routing (`#/`, `#/posts`, `#/post/<slug>`) and renders all views.

Blog posts are plain Markdown files in `posts/`. When a post is visited, the browser fetches the `.md` file and renders it on the fly using [marked.js](https://github.com/markedjs/marked).

### Structure

```
index.html          SPA shell (routing + rendering logic)
style.css           Styles
posts/
  index.json        Post manifest (slug, title, date, description)
  *.md              Blog posts in Markdown
libs/
  marked.js         Client-side Markdown parser
```

### Adding a post

1. Write a `.md` file in `posts/`
2. Add an entry to `posts/index.json`

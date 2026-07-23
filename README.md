# Personal site starter

A Quarto website scaffold styled with a warm cream / navy / rust palette
(inspired by Silvia Canelón's homepage layout and Andrew Heiss's blog/listing
style), applied to a research grid and a blog listing.

## Structure

```
_quarto.yml          site config, navbar, theme
styles.scss           color/type tokens + custom CSS for nav, about page, listings
index.qmd             homepage (Quarto "trestles" about-page template)
research.qmd          research listing page (grid style, like a projects gallery)
research/*.qmd        6 example project write-ups
blog.qmd              blog listing page (default style, no year sidebar)
blog/*.qmd            3 example posts
images/                placeholder art generated for this scaffold — swap these out
```

## Rendering locally

```bash
quarto render
# or, to preview with live reload:
quarto preview
```

## Things to swap out

- `images/profile.jpg` — replace with a real headshot (crop close to square/portrait)
- `images/research/*.jpg` and `images/blog/*.jpg` — replace with real project/post images
- All `href`s pointing to `github.com/yourusername`, LinkedIn, and `you@example.com`
- `site-url` in `_quarto.yml` once you have a real domain
- The placeholder project/post copy — it's written to be realistic so you can see
  how titles, tags, and descriptions wrap, but it's not your real content

## Notes on the theming

- Colors and fonts are defined once at the top of `styles.scss` (`$cream`, `$navy`,
  `$rust`, etc.) — change those to retheme the whole site.
- The research page uses Quarto's built-in `grid` listing type (that's what powers
  the card layout); the blog page uses the `default` listing type. Both read their
  metadata straight from each page's YAML front matter (`title`, `description`,
  `date`, `categories`, `image`), so adding a new project or post is just adding a
  new `.qmd` file to the folder — no manual index-page edits needed.
- `categories: false` on both listings turns off the sidebar filter/cloud (that's
  the "year list" you didn't want) while still showing each item's own tags inline.

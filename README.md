# tomb.io

Source for <https://tomb.io>, a Hugo static site for notes about software, programming, operations, and tools.

## Stack

- Hugo static site generator
- Custom layouts in `layouts/`
- Site CSS in `static/css/theme.css`
- Content in `content/`
- GitHub Pages deployment via `.github/workflows/hugo.yml`

## Requirements

Use `mise` to install the pinned Hugo version:

```sh
mise install
```

The pinned local version is in `mise.toml`. The GitHub Actions workflow installs its own Hugo version for deployment.

## Development

Run a local server:

```sh
hugo server --buildDrafts
```

Build the site into `public/`:

```sh
hugo --gc --minify
```

Create a new note:

```sh
hugo new content/notes/my-note.md
```

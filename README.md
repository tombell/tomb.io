# tomb.io

Source for <https://tomb.io>, a Hugo static site for notes about software, programming, operations, and tools.

## Stack

- Hugo static site generator
- Custom layouts in `layouts/`
- Site CSS in `static/css/theme.css`
- Content in `content/`
- GitHub Pages deployment via `.github/workflows/hugo.yml`

## Requirements

### Nix

With Nix installed and flakes enabled, enter the development shell:

```sh
nix develop
```

The shell provides Hugo on macOS and Linux (Apple Silicon/ARM64 and x86-64). Its version is pinned by `flake.lock` and may differ from mise and CI. Run the development commands below inside the shell, or directly with `nix develop --command hugo server --buildDrafts`.

To update the pinned Nix packages, run `nix flake update`.

### mise

Alternatively, use `mise` to install the pinned Hugo version:

```sh
mise install
```

The pinned mise version is in `.mise.toml`. The GitHub Actions workflow installs its own Hugo version for deployment.

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

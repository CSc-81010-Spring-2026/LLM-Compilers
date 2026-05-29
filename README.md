# LLMs in Compiler Construction

Lecture slides for CSc 81010 (Compiler Construction), CUNY Graduate Center, Spring 2026.

## Viewing

Open `llm_compilers.html` in any web browser. The deck uses [Slidy](https://www.w3.org/Talks/Tools/Slidy2/): advance with the arrow keys (or space), or by clicking; press `c` or the "Contents" button for the table of contents.

> **Note:** diagrams are rendered client-side with [Mermaid](https://mermaid.js.org) loaded from a CDN, so an internet connection is needed the first time you open the deck for the diagrams to appear. The text and navigation work offline.

## Building from Source

The slides are written in Pandoc Markdown (`llm_compilers.md`) and built with [Pandoc](https://pandoc.org) (version 2.11 or newer, which bundles both the `slidy` writer and `citeproc`, so no extra installs are needed):

```bash
make                  # build llm_compilers.html
make self-contained   # single-file HTML (for distribution)
```

Equivalently, without `make`:

```bash
pandoc --shift-heading-level-by=-1 -t slidy -s -H header.html --citeproc -M link-citations=true --bibliography=refs.bib llm_compilers.md -o llm_compilers.html
```

Source files:

- `llm_compilers.md` — the slide content (edit this); diagrams are written inline as [Mermaid](https://mermaid.js.org) code blocks
- `refs.bib` — bibliography, rendered via citeproc
- `header.html` — CSS and JavaScript (including Mermaid setup) injected into the document `<head>`

The `make deploy` target is for the author's own web host and relies on an ssh alias (`compsci`) defined in `~/.ssh/config`; adopters can ignore it.

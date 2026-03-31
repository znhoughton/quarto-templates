# Quarto Templates

Quarto PDF templates for academic linguistics and NLP submissions.

## Templates

| Template | Venue | Bibliography | Modes |
|---|---|---|---|
| [`acl`](acl/) | ACL and \*ACL conferences | natbib | `review` / `final` / `preprint` |
| [`colm`](colm/) | COLM 2026 | natbib authoryear | `submission` / `preprint` / `final` |
| [`glossapsycho`](glossapsycho/) | Glossa Psycholinguistics | biblatex (APA 7) | single mode + masked review |

See each template's folder for usage details, key YAML fields, and special features.

## Setup

Each template lives in its own subdirectory as a Quarto extension. To use a template in a new project, install it from this repo:

```bash
# From your new project directory:
quarto add "path/to/Quarto Templates/acl"
quarto add "path/to/Quarto Templates/colm"
quarto add "path/to/Quarto Templates/glossapsycho"
```

This copies the `_extensions/` folder into your project. After that, reference the format in your `.qmd` YAML header.

See the [`Examples/`](Examples/) folder for ready-to-render `.qmd` files for each template.

## Common notes

- All templates require **pdflatex** (not xelatex or lualatex).
- Use `bibliography: [file1.bib, file2.bib]` for multiple bib files.
- Figures and tables work with standard Quarto markdown syntax.
- Raw LaTeX can be included with ```` ```{=latex} ```` blocks when needed.

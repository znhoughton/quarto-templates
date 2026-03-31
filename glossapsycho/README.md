# glossapsycho

Quarto PDF template for Glossa Psycholinguistics journal submissions.

## Usage

```bash
quarto add "path/to/Quarto Templates/glossapsycho"
```

```yaml
format:
  glossapsycho-pdf: default
```

## Key YAML fields

```yaml
title: "Your Paper Title"
shorttitle: "Short Title"        # used in running headers
shortauthor: "Smith & Jones"     # used in running headers

author:
  - name: "Jane Smith"
    affiliations:
      - name: "University of Example"
    email: jane.smith@example.edu
    orcid: 0000-0000-0000-0000

abstract: |
  Your abstract here.

keywords: [keyword1, keyword2, keyword3]

bibliography: references.bib

masked: false    # set true for double-blind review (hides authors, shows word count)
```

## Special features

- **Interlinear glosses** via `\gll` / `\glt` commands (cgloss.sty):
  ```latex
  \gll Das Kind schläft. \\
       the child sleeps \\
  \glt `The child sleeps.'
  ```
- **Automatic word count** — the Lua filter counts words and injects the total into the header. When `masked: true`, the word count appears in place of author info.
- **Double-blind review** — `masked: true` suppresses all author and affiliation information.
- **APA 7 citations** via biblatex: `@Smith2020`, `[@Smith2020]`, etc.

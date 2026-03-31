# colm

Quarto PDF template for the Conference on Language Modeling (COLM 2026).

## Usage

```bash
quarto add "path/to/Quarto Templates/colm"
```

```yaml
format:
  colm-pdf: default
```

## Key YAML fields

```yaml
title: "Your Paper Title"

author:
  - name: "Jane Smith"
    affiliations:
      - name: "University of Example"
    email: jane.smith@example.edu

abstract: |
  Your abstract here.

bibliography: references.bib

colm-mode: submission    # submission | preprint | final
```

## Modes

| Mode | Authors shown | Line numbers | Header text |
|---|---|---|---|
| `submission` (default) | No (anonymous) | Yes | *(none)* |
| `preprint` | Yes | No | "Preprint. Under review." |
| `final` | Yes | No | "Published as a conference paper at COLM 2026" |

## Special features

- **Palatino font** (tgpagella + mathpazo) for body text and math.
- **natbib authoryear** citations with round brackets.
- **Mode-specific page headers** injected automatically.

# acl

Quarto PDF template for ACL, EMNLP, NAACL, and other \*ACL affiliated conferences.

## Usage

```bash
quarto add "path/to/Quarto Templates/acl"
```

```yaml
format:
  acl-pdf: default
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

acl-mode: review      # review | final | preprint
```

## Modes

| Mode | Authors shown | Line numbers | Page numbers |
|---|---|---|---|
| `review` (default) | No (anonymous) | Yes | No |
| `final` | Yes | No | No |
| `preprint` | Yes | No | Yes |

## Special features

- **Two-column layout** enforced by acl.sty.
- **natbib citations**: `\citet{Smith2020}` → Smith et al. (2020); `\citep{Smith2020}` → (Smith et al., 2020). In Quarto markdown: `@Smith2020` and `[@Smith2020]`.
- **Line numbers in review mode** for easy reviewer reference.

# Quarto Templates

Three Quarto PDF templates for academic linguistics and NLP submissions.

---

## Templates

| Template | Venue | Bibliography | Modes |
|---|---|---|---|
| [`glossapsycho`](#glossapsycho) | Glossa Psycholinguistics | biblatex (APA 7) | single mode + masked review |
| [`acl`](#acl) | ACL and *ACL conferences | natbib | `review` / `final` / `preprint` |
| [`colm`](#colm) | COLM 2026 | natbib authoryear | `submission` / `preprint` / `final` |

---

## Setup

Each template lives in its own subdirectory as a Quarto extension. To use a template in a new project, install it from this directory:

```bash
# From your new project directory:
quarto add "path/to/Quarto Templates/glossapsycho"
quarto add "path/to/Quarto Templates/acl"
quarto add "path/to/Quarto Templates/colm"
```

This copies the `_extensions/` folder into your project. After that, reference the format in your `.qmd` YAML header.

See the [`Examples/`](Examples/) folder for ready-to-render `.qmd` files for each template.

---

## glossapsycho

**Format for Glossa Psycholinguistics journal submissions.**

### Usage

```yaml
format:
  glossapsycho-pdf: default
```

### Key YAML fields

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

### Special features

- **Interlinear glosses** via `\gll` / `\glt` commands (cgloss.sty):
  ```latex
  \gll Das Kind schläft. \\
       the child sleeps \\
  \glt `The child sleeps.'
  ```
- **Automatic word count** — the Lua filter counts words and injects the total into the header. When `masked: true`, the word count appears in place of author info.
- **Double-blind review** — `masked: true` suppresses all author and affiliation information.
- **APA 7 citations** via biblatex: `@Smith2020`, `[@Smith2020]`, etc.

---

## acl

**Format for ACL, EMNLP, NAACL, and other *ACL affiliated conferences.**

### Usage

```yaml
format:
  acl-pdf: default
```

### Key YAML fields

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

### Modes

| Mode | Authors shown | Line numbers | Page numbers |
|---|---|---|---|
| `review` (default) | No (anonymous) | Yes | No |
| `final` | Yes | No | No |
| `preprint` | Yes | No | Yes |

### Special features

- **Two-column layout** enforced by acl.sty.
- **natbib citations**: `\citet{Smith2020}` → Smith et al. (2020); `\citep{Smith2020}` → (Smith et al., 2020). In Quarto markdown: `@Smith2020` and `[@Smith2020]`.
- **Line numbers in review mode** for easy reviewer reference.

---

## colm

**Format for the Conference on Language Modeling (COLM 2026).**

### Usage

```yaml
format:
  colm-pdf: default
```

### Key YAML fields

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

### Modes

| Mode | Authors shown | Line numbers | Header text |
|---|---|---|---|
| `submission` (default) | No (anonymous) | Yes | *(none)* |
| `preprint` | Yes | No | "Preprint. Under review." |
| `final` | Yes | No | "Published as a conference paper at COLM 2026" |

### Special features

- **Palatino font** (tgpagella + mathpazo) for body text and math.
- **natbib authoryear** citations with round brackets.
- **Mode-specific page headers** injected automatically.

---

## Common notes

- All templates require **pdflatex** (not xelatex or lualatex).
- Use `bibliography: [file1.bib, file2.bib]` for multiple bib files.
- Figures and tables work with standard Quarto markdown syntax.
- Raw LaTeX can be included with ```` ```{=latex} ```` blocks when needed.

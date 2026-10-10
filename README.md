# LaTeX Snippets

Copy-paste LaTeX snippets for quick reuse.

## Contents

1. [Page geometry (A4 margins)](#1-page-geometry-a4-margins)

---

## 1. Page geometry (A4 margins)

Sets A4 paper with a 171.9 mm text width, 253.8 mm text height, a 19.05 mm left margin and a 21.59 mm top margin. One size plus one margin per axis, so the layout is not over-constrained.

```latex
\usepackage[a4paper, width=171.9mm, left=19.05mm, height=253.8mm, top=21.59mm]{geometry}
```

**Notes**

- Put it in the preamble, after `\documentclass`.
- If your class already loads `geometry`, don't load it twice. Use this instead:

  ```latex
  \geometry{reset, a4paper, width=171.9mm, left=19.05mm, height=253.8mm, top=21.59mm}
  ```

- Don't use this with journal or conference templates that fix their own margins. Overriding them can get a paper returned.

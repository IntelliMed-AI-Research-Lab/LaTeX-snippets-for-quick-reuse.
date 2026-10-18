# LaTeX Snippets

Copy-paste LaTeX snippets for quick reuse.

## Contents

1. [Page geometry (A4 margins)](#1-page-geometry-a4-margins)
2. [Check and cross marks (`\okmark`, `\nomark`)](#2-check-and-cross-marks-okmark-nomark)

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

---

## 2. Check and cross marks (`\okmark`, `\nomark`)

Defines two shortcuts: `\okmark` prints a dark green check mark (✓) and `\nomark` prints a dark red cross (✗). Handy for comparison tables and feature checklists.

```latex
% in the PREAMBLE, before \begin{document}
\usepackage{xcolor}   % for \textcolor and the green!50!black color mixing
\usepackage{pifont}   % for \ding

\newcommand{\okmark}{\textcolor{green!50!black}{\ding{51}}}
\newcommand{\nomark}{\textcolor{red!60!black}{\ding{55}}}
```

**Usage**

```latex
\begin{tabular}{lcc}
  Feature   & A         & B         \\
  Fast      & \okmark   & \nomark   \\
  Free      & \nomark   & \okmark   \\
\end{tabular}
```

**Notes**

- Put it in the preamble, before `\begin{document}`.
- `\textcolor` needs `xcolor` (or `color`). If your class or another package already loads it, you can drop that line. Don't load it with conflicting options.
- `\ding{51}` is a check mark and `\ding{55}` is a cross, both from the `pifont` (Dingbats) font.
- Change the colors by editing the `green!50!black` / `red!60!black` mixes (e.g. `red!70!black` for a lighter red).

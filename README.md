# LaTeX Snippets

Copy-paste LaTeX snippets for quick reuse.

## Contents

1. [Page geometry (A4 margins)](#1-page-geometry-a4-margins)
2. [Check and cross marks (`\okmark`, `\nomark`)](#2-check-and-cross-marks-okmark-nomark)
3. [Change all red revision text from one place](#3-change-all-red-revision-text-from-one-place)

---

## 1. Page geometry (A4 margins)

(keep your existing section 1 unchanged)

---

## 2. Check and cross marks (`\okmark`, `\nomark`)

(keep your existing section 2 unchanged)

---

## 3. Change all red revision text from one place

Revision text is often marked with `\textcolor{red}{...}`, `\color{red}`, or `\begingroup\color{red}`. Instead of editing each one, define a single color and point everything at it. Change one line later to recolor (or un-highlight) all revision text.

```latex
% in the PREAMBLE, after \usepackage{xcolor}
\definecolor{revcolor}{HTML}{000000}   % change this one line to recolor ALL revision text
```

Then find and replace in your `.tex` file:

| Find | Replace with |
|---|---|
| `\textcolor{red}` | `\textcolor{revcolor}` |
| `\color{red}` | `\color{revcolor}` |

**Usage**

```latex
\textcolor{revcolor}{This sentence was added in the revision.}

\begingroup\color{revcolor}
\paragraph{New paragraph.} Whole revised blocks use the same color.
\endgroup
```

**Common colors (HTML codes)**

| Color | Code |
|---|---|
| Black (no highlight) | `000000` |
| Blue | `0000FF` |
| Dark blue | `1F3A93` |
| Dark green | `006400` |
| Cyan | `2ACAEA` |

**Shortcut (no find-and-replace)**

Override the built-in `red` itself, so every existing `\textcolor{red}` and `\color{red}` changes automatically:

```latex
% after \usepackage{xcolor}
\definecolor{red}{HTML}{000000}
```

**Notes**

- Put it in the preamble, after `\usepackage{xcolor}` and before `\begin{document}`.
- The shortcut also changes `red!60!black`, so the `\nomark` cross from section 2 would change color too. If you want `\nomark` to stay red, use the `revcolor` method (find-and-replace) instead of the shortcut.
- To remove the highlight completely, set the color to black (`000000`). The `\begingroup ... \endgroup` wrappers are harmless and can stay.

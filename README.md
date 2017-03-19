# LaTeX-for-Bookkeeping

## 二重線 cline

```
\newcommand{\ccline}[1]{\cline{#1} \noalign{\vspace{1pt}} \cline{#1}}
```

## 空白線

```
\tikz [baseline=0] \draw (1,0.3) -- (0,-0.2) -- (2.5,-0.2) ;
```

# LaTeX-for-Bookkeeping

## 概要

- 本 sty ファイルの内容
    - 合計線 (二重の cline)
    - 空白線

## ディレクトリ構造

```
.
├── README.md
├── bktools.sty
└── example
    ├── tabultest.aux
    ├── tabultest.dvi
    ├── tabultest.log
    ├── tabultest.pdf
    └── tabultest.tex

1 directory, 7 files
```

## ファイルの内容

- bktools.sty
    - 関数 ccline および mcr を定義したファイル
- example/tabultest.tex example/tabultest.pdf
    - bktools.sty の使用例

## 空白線の表現方法

bktools で定義した、mcr 関数の中で tikz 等で記述する。例えば 2 行分の空白行を表現する場合、以下のとおり。

```
\mcr{2}{\tikz [baseline=0] \draw (0, 1) -- (-1, -0.1) -- (1.5, -0.1);}
```

関数 mcr は、第 1 引数が行数の指定、第 2 引数が描画内容。

## 二重線の表現方法

bktools で定義した、ccline 関数を使用。使い方は cline と同様。

## bktools.sty の内容

### ccline

```
\newcommand{\ccline}[1]{
    \cline{#1}
    \noalign{\vspace{1.4pt}}
    \cline{#1}
    \noalign{\vspace{-1.4pt}}}
```

## mcr

```
\newcommand{\mcr}[2]{\multicolumn{2}{r}{\multirow{#1}{*}{#2}}}
```

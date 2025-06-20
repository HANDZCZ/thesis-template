---
papersize: a4
author: ""
# open bookmarks tab
bookmarksopen: true
# bookmarks tab expand level
bookmarkopenlevel: 1
pdfcreator: LaTeX via pandoc, made with care and extra sugar on top
title-meta: ""
keywords: []
subject: ""
colorlinks: true
# default: Maroon
linkcolor: Maroon
# default: Maroon
filecolor: Maroon
# default: Blue
citecolor: Blue
# default: Blue
urlcolor: Blue
# Defaults to linkcolor
toccolor: Black

header-includes: |
    ```{=latex}
    % force figures to be placed exactly where they are defined
    \usepackage{float}
    \let\origfigure\figure
    \let\endorigfigure\endfigure
    \renewenvironment{figure}[1][2] {
        \expandafter\origfigure\expandafter[H]
    } {
        \endorigfigure
    }

    % include pdfs
    \usepackage{pdfpages}

    % indent first line of paragraph
    \usepackage{indentfirst}

    % break long lines that would overflow
    \usepackage{fvextra}
    \DefineVerbatimEnvironment{Highlighting}{Verbatim}{breaklines,commandchars=\\\{\}}

    % get rid of single letters at the end of line
    \usepackage[nosingleletter]{impnattypo}

    % support for emoji
    \newfontfamily\emojifont[Renderer=Harfbuzz]{Noto Color Emoji}
    \DeclareTextFontCommand{\emoji}{\emojifont}

    % color every other row
    \usepackage{etoolbox}
    \AtBeginEnvironment{longtable}{\rowcolors{2}{gray!15}{}}
    \apptocmd{\toprule}{\hiderowcolors}{}{}
    \apptocmd{\endhead}{\showrowcolors}{}{}
    \apptocmd{\endfirsthead}{\showrowcolors}{}{}
    % set the color to stick out
    \setlength{\tabcolsep}{3pt}

    % landscape pages
    \usepackage{pdflscape}
    \newcommand{\blandscape}{\begin{landscape}}
    \newcommand{\elandscape}{\end{landscape}}
    ```

includes-before-document: |
    ```{=latex}
    % set minted style
    \usemintedstyle{tomorrow}
    % prevent italics in the `minted` environment.
    %\AtBeginEnvironment{minted}{\let\itshape\relax}
    % prevent italics in the `\mintinline` command.
    %\usepackage{xpatch}
    %\xpatchcmd{\mintinline}{\begingroup}{\begingroup\let\itshape\relax}{}{}
    % set line numbers size
    \renewcommand{\theFancyVerbLine}{\sffamily \textcolor[rgb]{0.0,0.0,0.0}{\tiny \oldstylenums{\arabic{FancyVerbLine}}}}
    ```

lang: cs-CZ
pagestyle: empty
plot-configuration: plot-config.yaml

fontsize: 12pt
mainfont: DejaVu Serif Condensed
mainfontoptions:
- Scale=1.0
- BoldFont=* Bold
- ItalicFont=* Italic
- BoldItalicFont=* BoldItalic
monofont: JetBrainsMono Nerd Font
monofontoptions:
- Scale=1.0
sansfont: DejaVu Sans Condensed
sansfontoptions:
- Scale=1.0
- BoldFont=* Bold
- ItalicFont=* Oblique
- BoldItalicFont=* BoldOblique
#mathfont: TeXGyreDejaVuMath-Regular
mathfont: DejaVu Serif Condensed
mathfontoptions:
- Scale=1.0

geometry:
- top=20mm
- right=20mm
- left=35mm
- bottom=20mm
toc-depth: 6
# add all bib
#nocite: '@*'
# add hyperinks to citations
link-citations: true
csquotes: true

numbersections: true
autoEqnLabels: true
codeBlockCaptions: true
figPrefix:
  - "obrázek"
  - "obrázky"
tblPrefix:
  - "tabulka"
  - "tabulky"
lstPrefix:
  - "kód"
  - "kódy"
secPrefix:
  - "sekce"
  - "sekce"

lofTitle: Seznam obrázků
lotTitle: Seznam tabulek
lolTitle: Seznam kódů
listingTitle: Kód
tableTitle: Tabulka
figureTitle: Obrázek
# Defaults to linkcolor
lotcolor: Black
# Defaults to linkcolor
lofcolor: Black
linestretch: 1.5
---
\hyphenpenalty=10000
\widowpenalties 1 10000
\raggedbottom

<!-- Table of contents -->
\toc
\newpage

<!-- Set page style -->
\pagestyle{plain}
\parindent 1,25cm
\parskip 12pt
\setcounter{page}{1}

``` {.include}
```

# Seznam použité literatury

::: {#refs}
:::

\newpage

# Seznam obrázků, tabulek a kódů

\lof
\lot
\lol

\newpage

\pagestyle{empty}


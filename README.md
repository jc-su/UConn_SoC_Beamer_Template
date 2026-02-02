# UConn School of Computing Beamer Theme

A custom Beamer theme for the University of Connecticut School of Computing. Features navy/white color scheme, red accent styling, and UConn branding.

## Preview

| Title Slide | Content Slide | Thank You Slide |
|:-----------:|:-------------:|:---------------:|
| Navy background, white logo box | White background, navy footer | Navy background, white logo box |

## Quick Start

```latex
\documentclass[aspectratio=169]{beamer}
\usetheme{UConn}

\footlinetext{Your Presentation Title}
\footlineevent{Conference'26}

\title{Your Title}
\author{Your Name}
\institute{University of Connecticut}

\begin{document}
\titleslide

\begin{frame}{Slide Title}
    Your content here.
\end{frame}

\thankyouslide[Your Name \quad\texttt{email@uconn.edu}]
\end{document}
```

## Files

```
beamerthemeUConn.sty   % Theme file (put in same directory or TEXMF tree)
uconn-logo_top.pdf     % Logo for title/closing slides
uconn-logo_foot.pdf    % Logo for footer bar
example.tex            % Example presentation
```

## Features

### Slide Commands

| Command | Description |
|---------|-------------|
| `\titleslide` | Navy title slide with logo on white background |
| `\thankyouslide[contact]` | Navy closing slide with "Thank You!" |
| `\questionsslide[contact]` | Navy closing slide with "Questions?" |

### Footer Configuration

```latex
\footlinetext{Presentation title shown in footer}
\footlineevent{CONF'26}
```

The footer is a navy bar with three sections: logo (left), title (center), event (right).

### Logo Customization

Default logos are set in the theme. Override if needed:

```latex
\logo{\includegraphics[height=1.5cm]{your-logo.pdf}}
\footlinelogo{\includegraphics[height=2.5ex]{your-footer-logo.pdf}}
```

### Text Styling

```latex
\accenttext{Red bold text}     % For key numbers/results
\emphtext{Red text}            % For emphasis without bold
\alert{Alert text}             % Standard Beamer alert
```

### Custom Box Environments

```latex
% Problem statement box (red-accented title)
\begin{challengebox}
    Describe the problem here.
\end{challengebox}

% Solution/key idea box (red-accented title, custom label)
\begin{keyideabox}[Solution:]
    Describe your approach here.
\end{keyideabox}
```

### Dark Frame

```latex
\begin{darkframe}{Title}
    White text on navy background.
\end{darkframe}
```

### Speaker Notes

```latex
\setbeameroption{show notes on second screen=right}

\begin{frame}{Title}
    Slide content.
\end{frame}
\note{Speaker transcript for this slide.}
```

### TikZ

The theme pre-loads TikZ with libraries: `shapes.geometric`, `arrows.meta`, `positioning`, `decorations.pathreplacing`. Theme colors (`UConnNavy`, `UConnAccent`, etc.) are available in TikZ drawings.

## Colors

| Name | Hex | PANTONE | Usage |
|------|-----|---------|-------|
| `UConnNavy` | `#000E2F` | 289 | Primary color, backgrounds, headers |
| `UConnWhite` | `#FFFFFF` | — | Text on dark backgrounds |
| `UConnGray` | `#7C878E` | 430 | Secondary text |
| `UConnAccent` | `#CC0000` | — | Red accent, alerts, underlines |
| `UConnDarkBlue` | `#1A2959` | — | Title, thank you, questions slide backgrounds |
| `UConnRoyalBlue` | `#013ECD` | 2728 | Royal Blue, available for custom use |
| `UConnLightGray` | `#F0F1F2` | — | Block body background |
| `UConnBlack` | `#222222` | — | Body text |

## Building

```bash
pdflatex example.tex
```

Requires a standard TeX Live or MiKTeX installation.

# Shibui Beamer Theme (渋い)

A minimalist Beamer presentation theme embodying the Japanese aesthetic principle of **Shibui**: simple, subtle, and unobtrusive beauty through refined restraint.

## Features

- **9 Color Schemes**: light (default), dark, solarizedlight, solarizeddark, solarizedosaka, nord, gruvboxlight, gruvboxdark, autumn
- **5 Font Options**: sans (Fira Sans, default), serif (ET Book/Palatino), garamond (EB Garamond), charter (Charter), mono (Fira Mono)
- **Flexible Navigation**: Optional navbar with clickable section names, with or without navigation circles
- **Progress Indicators**: Three modes - continuous bar (default), section-based segments, or page numbers only
- **Clean Typography**: Generous whitespace, elegant fonts, and minimal visual clutter
- **Special Features**:
  - Optional kanji logo (渋い) in footer
  - Custom accent color commands for easy highlighting
  - Automatic styling for code listings and algorithms
  - Custom `shibuiframe` environment for highlighted content
  - Proper handling of frame breaks with continuation numbers

## Installation

1. Copy all `.sty` files to your LaTeX project directory, or install to your local texmf tree
2. Use the theme in your Beamer presentation:

```latex
\documentclass{beamer}
\usetheme{Shibui}
```

## Usage

### Basic Usage

```latex
\documentclass[aspectratio=169]{beamer}
\usetheme{Shibui}

\title{Your Presentation Title}
\author{Your Name}
\date{\today}

\begin{document}
\maketitle

\section{Introduction}
\begin{frame}{Frame Title}
  Your content here
\end{frame}

\end{document}
```

### Theme Options

**Color Schemes:**
```latex
\usetheme[light]{Shibui}           % Light cream background (default)
\usetheme[dark]{Shibui}            % Dark background
\usetheme[solarizedlight]{Shibui}  % Solarized Light
\usetheme[solarizeddark]{Shibui}   % Solarized Dark
\usetheme[solarizedosaka]{Shibui}  % Solarized Osaka (deep blue)
\usetheme[nord]{Shibui}            % Nord (arctic blue)
\usetheme[gruvboxlight]{Shibui}    % Gruvbox Light (warm retro)
\usetheme[gruvboxdark]{Shibui}     % Gruvbox Dark (warm retro)
\usetheme[autumn]{Shibui}          % Autumn (warm earthy tones)
```

**Font Options:**
```latex
\usetheme[sans]{Shibui}      % Fira Sans (default)
\usetheme[serif]{Shibui}     % ET Book or Palatino
\usetheme[garamond]{Shibui}  % EB Garamond
\usetheme[charter]{Shibui}   % Charter
\usetheme[mono]{Shibui}      % Fira Mono (for code-heavy presentations)
```

**Layout Options:**
```latex
\usetheme[navontop]{Shibui}              % Show navigation bar (default)
\usetheme[navontop,navcircles]{Shibui}   % Navigation bar with circles
\usetheme[nosectionheader]{Shibui}       % Hide section name from header (default)
\usetheme[nosub]{Shibui}                 % Hide subsections in table of contents
```

**Progress Bar Options:**
```latex
\usetheme[progressbar=basic]{Shibui}      % Continuous progress bar (default)
\usetheme[progressbar=segmented]{Shibui}  % Section-based segments
\usetheme[progressbar=none]{Shibui}       % Page numbers only
```

**Special Options:**
```latex
\usetheme[kanjilogo]{Shibui}  % Show "渋い" kanji in footer
```

**Combining Options:**
```latex
\usetheme[nord,garamond,navontop,progressbar=segmented]{Shibui}
```

### Custom Footer Text

Add custom text above the progress bar:

```latex
\footertext{Conference 2024 -- Paris, France}
```

### Custom Accent Commands

The theme provides commands for applying accent colors:

```latex
\acccolor{text}      % Apply accent color only
\accentb{text}       % Accent color + bold
\accentit{text}      % Accent color + italic
\accentemph{text}    % Accent color + emphasis
```

### Custom Frame Environment

Use the `shibuiframe` environment for highlighted content boxes:

```latex
\begin{shibuiframe}{Title}
  Your content here
\end{shibuiframe}
```

### Code and Algorithms

The theme automatically styles code listings and algorithms with proper background colors:

```latex
\begin{frame}[fragile]{Code Example}
  \begin{lstlisting}[language=Python]
  def hello():
      print("Hello, World!")
  \end{lstlisting}
\end{frame}

\begin{frame}{Algorithm Example}
  \begin{algorithm}[H]
    \caption{Your Algorithm}
    \begin{algorithmic}[1]
      \State Your pseudocode here
    \end{algorithmic}
  \end{algorithm}
\end{frame}
```

### Frame Breaks

The theme properly handles multi-page frames with continuation numbers:

```latex
\begin{frame}[allowframebreaks]{Long Content}
  % Content that spans multiple slides
  % Will show "Long Content", "Long Content I", "Long Content II", etc.
\end{frame}
```

### Navigation

The navigation bar (when `navontop` is enabled) shows:
- **Section names**: Clickable links to jump to each section
- **Circles** (optional with `navcircles`): Show slides within current section
- Current section is highlighted in accent color

## Color Definitions

The following colors are available for custom styling:

- `shibuibg` - Background color
- `shibuitext` - Main text color
- `shibuiaccent` - Accent/highlight color
- `shibuigray` - UI elements (light)
- `shibuidarkgray` - Secondary text
- `shibuicodebg` - Code/box background

Use with `\textcolor{shibuiaccent}{text}` or `\color{shibuiaccent}`.

## Requirements

- LaTeX with Beamer class
- TikZ package
- tcolorbox package
- Font packages (automatically loaded based on font option):
  - FiraSans (for sans option)
  - FiraMono (for mono option)
  - ebgaramond (for garamond option)
  - mathdesign with charter (for charter option)
  - ETbb or mathpazo (for serif option)
- Optional: CJKutf8 (for kanjilogo option)
- Optional: listings, algorithm, algpseudocode, pgfplots (for examples)

## Design Philosophy

Shibui embodies Japanese minimalist design principles:

- **Clarity through simplicity** - No unnecessary decorations
- **Generous whitespace** - Content room to breathe
- **Elegant typography** - Readable, beautiful fonts
- **Subtle navigation** - Present but unobtrusive
- **Focus on content** - Design serves the message

The aesthetic aims for restrained elegance, where beauty emerges from simplicity and attention to detail rather than ornamentation.

## Compilation

```bash
pdflatex example.tex
pdflatex example.tex  # Run twice for navigation

# Or use latexmk
latexmk -pdf example.tex
```

## Examples

See `example.tex` for a comprehensive demonstration of all theme features including:
- Multiple color schemes
- Typography options
- Code listings and algorithms
- Mathematics
- TikZ diagrams and PGFPlots
- Custom boxes and blocks
- Navigation features

## License

MIT License - Feel free to use and modify for your presentations.

## Credits

Inspired by the Japanese aesthetic concept of Shibui (渋い) and designed for clear, effective academic and professional presentations.

# Tufte Beamer Theme

A minimalist Beamer presentation theme inspired by Edward Tufte's design principles and the [tufte-css](https://edwardtufte.github.io/tufte-css/) project.

## Features

- **Tufte-CSS Color Palette**: Warm cream background (`#FFFFF8`) with dark, readable text (`#111111`) and dark red accents (`#A00000`)
- **Elegant Typography**: Uses ET Book font (with Palatino as fallback) for beautiful serif presentation
- **Minimal Navigation**: Clean headline with navigation squares for sections
- **Flush Bottom Progress Bar**: Visual progress indicator with page numbers on the same line, no space below
- **Rule of Thirds Title Page**: Left-aligned title page with decorative line and hierarchical layout
- **Clean Section Pages**: Centered section slides without header/footer
- **Generous Whitespace**: Following Tufte's principle of clarity through simplicity
- **Rich Content Support**: Mathematics, code listings, algorithms, TikZ diagrams, and PGFPlots

## Installation

### Option 1: Local Installation

1. Clone or download this repository
2. Place all `.sty` files in your LaTeX project directory
3. Use `\usetheme{Tufte}` in your document preamble

### Option 2: System-wide Installation

Copy all `.sty` files to your local texmf tree:

```bash
# Linux/macOS
cp *.sty ~/texmf/tex/latex/beamer/

# Refresh TeX file database
texhash ~/texmf
```

On Windows, copy to: `C:\Users\<username>\texmf\tex\latex\beamer\`

## Usage

### Basic Example

```latex
\documentclass[aspectratio=169]{beamer}

\usetheme{Tufte}

\title{Your Presentation Title}
\subtitle{Optional Subtitle}
\author{Your Name}
\institute{Your Institution}
\date{\today}

\begin{document}

\maketitle

\begin{frame}{First Slide}
  Content goes here
\end{frame}

\section{First Section}

\begin{frame}{Section Content}
  More content
\end{frame}

\end{document}
```

### Aspect Ratios

The theme works with both widescreen and traditional formats:

```latex
% Widescreen (16:9)
\documentclass[aspectratio=169]{beamer}

% Traditional (4:3)
\documentclass[aspectratio=43]{beamer}
```

### Section Slides

You can manually insert section title slides:

```latex
\section{New Section}
\sectionframe  % Creates a centered section title slide
```

Or enable automatic section slides by uncommenting in `beamerthemeTufte.sty`:

```latex
\AtBeginSection[]{
  \sectionframe  % Uncomment this line
}
```

## Design Elements

### Colors

The theme defines several colors from the tufte-css palette:

- `tuftebg`: Cream background (`#FFFFF8`)
- `tuftetext`: Near black text (`#111111`)
- `tufteaccent`: Dark red accent (`#A00000`)
- `tuftegray`: Light gray for UI elements
- `tuftedarkgray`: Dark gray for secondary text

Use them in your presentation:

```latex
\textcolor{tufteaccent}{emphasized text}
```

### Typography

The theme attempts to use ET Book font. If not available, it falls back to Palatino (mathpazo package). Both provide excellent readability for presentations.

### Navigation

- **Squares in headline**: Show slides within the current section only (filled square = current slide)
- **Section name**: Displayed in the headline
- **Slide title**: Appears in the headline (compact layout)
- **Progress bar**: Visual indicator that fills from left to right
- **Page numbers**: Format: "3 / 12" (current / total)

## Customization

### Adjusting Margins

Modify text margins in `beamerinnerthemeTufte.sty`:

```latex
\setbeamersize{text margin left=1cm,text margin right=1cm}
```

### Changing Colors

Edit color definitions in `beamercolorthemeTufte.sty`:

```latex
\definecolor{tufteaccent}{HTML}{A00000}  % Change accent color
```

### Font Sizes

Adjust font sizes in `beamerfontthemeTufte.sty`:

```latex
\setbeamerfont{frametitle}{size=\large,series=\bfseries}
```

## Philosophy

This theme follows Edward Tufte's design principles:

1. **Show the data**: Minimal decoration, maximum content
2. **Reduce noise**: Every element serves a purpose
3. **Integrate text and graphics**: Unified visual presentation
4. **Respect your audience**: Clear, honest communication

The design emphasizes:

- Generous whitespace for visual calm
- High contrast for readability
- Subtle navigation that doesn't distract
- Typography that aids comprehension

## Tips for Best Results

1. **Keep it simple**: One main idea per slide
2. **Use whitespace**: Add vertical space with `\vspace{1em}`
3. **Minimize bullets**: Consider prose or numbered lists instead
4. **High-quality figures**: Match the theme's clean aesthetic
5. **Consistent colors**: Stick to the defined color palette

## Requirements

- LaTeX with Beamer class
- TikZ package (for progress bar and diagrams)
- PGFPlots package (for plots, optional)
- mathpazo or ETbb package (for fonts)
- listings package (for code, optional)
- algorithm and algpseudocode packages (for algorithms, optional)

## Example

See `example.tex` for a complete demonstration of the theme's features, including:

- Rule of thirds title page layout with decorative line
- Section slides (centered, minimal)
- Various content types (lists, blocks, quotes)
- Mathematical equations (inline and display)
- Code listings with syntax highlighting
- Algorithm pseudocode
- TikZ diagrams (graphs, flowcharts)
- PGFPlots (function plots)
- Typography examples and best practices

Compile with:

```bash
pdflatex example.tex
pdflatex example.tex  # Run twice for navigation

# Or use latexmk for automatic reruns
latexmk -pdf -shell-escape example.tex
```

## License

MIT License - feel free to use and modify for your presentations.

## Credits

- Inspired by Edward Tufte's *The Visual Display of Quantitative Information*
- Color palette from [tufte-css](https://edwardtufte.github.io/tufte-css/) by Dave Liepmann
- ET Book font by Dmitry Krasny, Bonnie Scranton, and Edward Tufte

## Contributing

Suggestions and improvements are welcome! Please ensure any changes maintain the minimalist, Tufte-inspired aesthetic.

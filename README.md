# Minimalist CV/Resume Template in LaTeX

A clean, professional CV template optimized for both human readers and Applicant Tracking Systems (ATS). Features a modular design that separates content from formatting, making it highly reusable and easy to customize for different job applications.

## ✨ Features

- **Clean Typography**: Minimalist design focused on readability
- **ATS-Friendly**: No photos, simple structure for machine parsing
- **Modular Architecture**: Content separated from template formatting
- **Simple Customization**: Comment out sections you don't need
- **Comprehensive Sections**: Bio, Experience, Education, Skills, Publications, Awards
- **Easy to Use**: Edit only one file (`cv-content.tex`) for all your information

## 🚀 Quick Start

### Prerequisites

You need a LaTeX distribution installed:
- **Linux**: `sudo apt-get install texlive-full`
- **macOS**: Install [MacTeX](https://www.tug.org/mactex/)
- **Windows**: Install [MiKTeX](https://miktex.org/) or [TeX Live](https://www.tug.org/texlive/)

### Compilation

```bash
# Compile the CV
pdflatex cv-template.tex

# Or use latexmk for automatic compilation
latexmk -pdf cv-template.tex
```

## 📝 How to Use

### Step 1: Edit Your Information

Open `cv-content.tex` and update with your personal information:

```latex
% Personal details
\name{Your}{Name}
\title{Your Job Title}
\email{your.email@example.com}
\phone{+1~(234)~567~890}

% Update each section with your information
\newcommand{\userbio}{
  Your professional summary here...
}

\newcommand{\userexperience}{
  \cventry{2021--Present}{Job Title}{Company}{Location}{}{
    \begin{itemize}
      \item Achievement 1
      \item Achievement 2
    \end{itemize}
  }
}

% ... and so on for other sections
```

### Step 2: Hide/Show Sections

To hide a section, simply comment it out in `cv-content.tex`:

```latex
% Comment out sections you don't want
% \newcommand{\userawards}{%
%   \cvitem{2024}{Outstanding Paper Award, NeurIPS 2024}
%   ...
% }
```

Or comment out entire sections in `cv-template.tex`:

```latex
% \section{Additional Information}
% \useradditional
```

### Step 3: Compile

```bash
pdflatex cv-template.tex
```

Your CV will be generated as `cv-template.pdf`.

---


# an-ats

An Applicant Tracking Systems (ATS) friendly minimalist CV/resume template in LaTeX.

## Features

- **Minimalist Design**: Clean, neat typography that's easy on the eyes
- **ATS-Optimized**: Simple structure for reliable parsing by applicant tracking systems
- **Machine & Human Friendly**: Works well for both automated systems and human readers
- **No Photos**: Focus on content, not appearance
- **Decoupled Architecture**: Template and content are separated for easy reuse
- **Flexible Sections**: Toggle sections on/off to optimize for specific job applications
- **Comprehensive Sections**: Bio, Experience, Education, Awards, Skills, Publications

## Quick Start

### Prerequisites

You need a LaTeX distribution installed on your system:

- **Windows**: [MiKTeX](https://miktex.org/) or [TeX Live](https://www.tug.org/texlive/)
- **macOS**: [MacTeX](https://www.tug.org/mactex/)
- **Linux**: TeX Live (usually available via package manager)

```bash
# Ubuntu/Debian
sudo apt-get install texlive-latex-base texlive-latex-extra

# Fedora
sudo dnf install texlive-scheme-basic

# macOS (with Homebrew)
brew install --cask mactex
```

### Usage

1. **Clone or download** this repository
2. **Edit** `cv-content.tex` with your personal information
3. **Toggle** sections on/off as needed for your target job
4. **Compile** the template:

```bash
pdflatex cv-template.tex
```

Your CV will be generated as `cv-template.pdf`.

## File Structure

```
.
├── cv-template.tex    # Main template file (DO NOT edit for content)
├── cv-content.tex     # Your content file (EDIT THIS)
└── README.md          # This file
```

## Customization Guide

### Editing Your Content

Open `cv-content.tex` and edit the following sections:

#### 1. Toggle Sections

Turn sections on/off by changing `true` to `false`:

```latex
\renewcommand{\togglebio}{true}           % Show bio
\renewcommand{\toggleexperience}{true}    % Show experience
\renewcommand{\toggleeducation}{true}     % Show education
\renewcommand{\toggleawards}{false}       % Hide awards
\renewcommand{\toggleskills}{true}        % Show skills
\renewcommand{\togglepublications}{false} % Hide publications
```

**Tip**: Create different versions of `cv-content.tex` for different job applications (e.g., `cv-content-software.tex`, `cv-content-research.tex`).

#### 2. Personal Information

```latex
\newcommand{\cvname}{Your Full Name}
\newcommand{\cvcontact}{%
    Email: your.email@example.com \contactsep
    Phone: +1 (123) 456-7890 \contactsep
    LinkedIn: linkedin.com/in/yourprofile \contactsep
    GitHub: github.com/yourusername
}
```

**Note**: Use `\contactsep` for separators between contact items. This ensures consistent spacing.

#### 3. Bio/Professional Summary

Optimize this for each job application:

```latex
\newcommand{\cvbio}{%
    Your professional summary here. Keep it concise and relevant
    to the position you're applying for.
}
```

#### 4. Experience

Use the `\cventry` command for each position:

```latex
\cventry{Job Title}{Date Range}{Company Name}{%
    \begin{itemize}
        \item Achievement or responsibility
        \item Another achievement with metrics
        \item Use action verbs and quantify results
    \end{itemize}
}
```

#### 5. Education

Use the `\cvsimpleentry` command:

```latex
\cvsimpleentry{Degree Name}{Graduation Date}{
    University Name, Location -- Additional info (GPA, honors, etc.)
}
```

#### 6. Awards & Honors

```latex
\cvsimpleentry{Award Name}{Date}{Organization or Details}
```

#### 7. Skills

Organize skills by category:

```latex
\textbf{Category:} Skill1, Skill2, Skill3\\[4pt]
\textbf{Another Category:} More skills here
```

#### 8. Publications

Format according to your field's citation style:

```latex
\cvpublication{%
    \textbf{Your Name}, Co-Author. ``Paper Title.''
    \textit{Conference/Journal}, Year.
}
```

## Tips for ATS Optimization

1. **Use Standard Section Headings**: Experience, Education, Skills, etc.
2. **Include Keywords**: Match keywords from the job description
3. **Avoid Complex Formatting**: Keep it simple (no tables, columns, or graphics)
4. **Use Standard Fonts**: The template uses standard LaTeX fonts
5. **Save as PDF**: Most ATS systems handle PDFs well
6. **Plain Text Works**: The simple structure ensures good text extraction

## Customizing the Template

If you want to modify the template design itself (fonts, spacing, colors), edit `cv-template.tex`. Key areas to customize:

- **Margins**: Line 10: `\usepackage[margin=0.75in]{geometry}`
- **Font Size**: Line 5: `\documentclass[11pt,a4paper]{article}`
- **Section Styling**: Lines 33-36: `\newcommand{\cvsection}`
- **Spacing**: Lines 29-30: Adjust spacing parameters

## Multiple CV Versions

For different job applications, create multiple content files:

```bash
cp cv-content.tex cv-content-software-engineer.tex
cp cv-content.tex cv-content-data-scientist.tex
```

### Method 1: Command Line (Recommended)

Compile with a specific content file without modifying the template:

```bash
pdflatex "\def\contentfile{cv-content-software-engineer.tex}\input{cv-template.tex}"
```

This is the easiest way to maintain multiple CV versions!

### Method 2: Edit Template

Alternatively, edit `cv-template.tex` and change the input line (around line 71):

```latex
\input{cv-content-software-engineer.tex}
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This template is released into the public domain. Feel free to use it for any purpose.

## Acknowledgments

Designed with simplicity and ATS compatibility in mind for job seekers who want to focus on content, not formatting.

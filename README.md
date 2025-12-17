# Comprehensive LaTeX CV for Fabio J. Fehr

A minimalist LaTeX CV template using moderncv with clean typography that is ATS-friendly. 
This template is initialized with your basic information from your website and LinkedIn.

## Quick Start

Your CV is already set up with basic information! Now you need to fill in complete details.

### 1. View Current CV

```bash
cd /home/fabio/Projects/cv-template
xdg-open cv-template.pdf  # View the current PDF
```

### 2. Fill In Missing Information

**READ THE GUIDE FIRST:** Open `FILL-IN-GUIDE.md` for detailed step-by-step instructions!

```bash
cat FILL-IN-GUIDE.md  # or open in your editor
```

The guide tells you:
- What information to add
- Where to find it (your website's YAML files)
- How to format it properly

### 3. Edit Your Content

Edit `cv-content.tex` to fill in the TODOs:

```bash
nano cv-content.tex  # or use your preferred editor
```

**What's Already Done:**
- ✅ Name: Fabio J. Fehr
- ✅ Website: fjfehr.github.io
- ✅ LinkedIn: fabio-j-fehr
- ✅ GitHub: FJFehr
- ✅ Basic bio from your website
- ✅ Structure for Oxford postdoc and Amazon internship
- ✅ Placeholders for PhD and Master's details

**What You Need To Do:**
- 📝 Update email address
- 📝 Add Google Scholar ID
- 📝 Fill in complete work experience from `timeline.yaml`
- 📝 Fill in complete education details from `timeline.yaml`
- 📝 Add ALL publications from `publications.yaml`
- 📝 Add awards and honors
- 📝 Expand skills section
- 📝 Complete additional information

### 4. Compile After Editing

```bash
pdflatex cv-template.tex
pdflatex cv-template.tex  # Run twice for proper formatting
```

### 5. View Updated PDF

```bash
xdg-open cv-template.pdf
```

## Where To Find Your Data

All your information is in your website repository:

```bash
# Clone your website if you haven't already:
cd /home/fabio/Projects/
git clone https://github.com/FJFehr/fjfehr.github.io.git

# Then view your data files:
cat fjfehr.github.io/content/timeline/timeline.yaml        # Experience & Education
cat fjfehr.github.io/content/publications/publications.yaml  # Publications
cat fjfehr.github.io/content/site/config.yaml              # Email & Social Links
```

## Structure

- `cv-template.tex` - Main template file (DO NOT EDIT)
- `cv-content.tex` - Your personal information (EDIT THIS)
- `FILL-IN-GUIDE.md` - **READ THIS FIRST** - Detailed instructions
- `.gitignore` - Excludes LaTeX build artifacts
- `README.md` - This file

## Customizing for Specific Jobs

The template is designed to be **comprehensive** - include everything. Then:

1. Open `cv-content.tex`
2. Comment out sections you don't need (add `%` at start of lines)
3. Adjust the bio for the specific position
4. Recompile

### Example: Hide Additional Information Section

```latex
% \section{Additional Information}
% \useradditional
```

## Tips for Academic CVs

1. **Be comprehensive** - Include everything (unlike a resume)
2. **Bold your name** in publications - Use `\textbf{Fehr, F. J.}`
3. **Order chronologically** - Most recent first in each section
4. **Be specific** - Exact dates, advisor names, institutions
5. **Quantify** - "Published 5 papers at top venues" vs "Published papers"
6. **Keep current** - Update after each achievement

## Features

- ✨ Clean, minimalist design (Apple-inspired)
- 📄 No photo (ATS-friendly, cleaner look)
- 🎯 Decoupled template and content
- 🔧 Easy customization by commenting sections
- 📚 Professional typography for readability
- 🤖 ATS-compatible formatting

## Need Help?

- **Content questions**: Check `FILL-IN-GUIDE.md`
- **LaTeX issues**: See moderncv documentation
- **Your data**: Check your website's YAML files at `fjfehr.github.io/content/`

---

**Remember:** The goal is to create a **verbose, comprehensive CV** with ALL your accomplishments. 
You can always create shorter versions by commenting out sections for specific job applications!

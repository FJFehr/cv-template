# Quick Start Guide

Get your professional CV ready in 5 minutes!

## Step 1: Install LaTeX

If you don't have LaTeX installed:

**Ubuntu/Debian:**
```bash
sudo apt-get install texlive-latex-base texlive-latex-extra
```

**macOS:**
```bash
brew install --cask mactex
```

**Windows:**
Download and install [MiKTeX](https://miktex.org/download)

## Step 2: Edit Your Content

Open `cv-content.tex` in any text editor and fill in your information:

1. **Toggle sections** - Set to `true` or `false`:
   ```latex
   \renewcommand{\togglebio}{true}           % Show
   \renewcommand{\toggleawards}{false}       % Hide
   ```

2. **Add your name and contact info**:
   ```latex
   \newcommand{\cvname}{Your Full Name}
   ```

3. **Write your bio** (optimize for each job):
   ```latex
   \newcommand{\cvbio}{Your professional summary...}
   ```

4. **Fill in your experience, education, etc.**

## Step 3: Compile

```bash
pdflatex cv-template.tex
```

Your CV is now `cv-template.pdf`!

## Pro Tips

### Multiple Versions

Create different versions for different jobs:

```bash
cp cv-content.tex cv-content-software.tex
cp cv-content.tex cv-content-research.tex
```

Edit each for specific roles, then use the command line:
```bash
pdflatex "\def\contentfile{cv-content-software.tex}\input{cv-template.tex}"
```

Or edit line 76 in `cv-template.tex` to change the default content file.

### Toggle Strategy

- **Software Engineer**: Hide awards/publications, show experience/skills
- **Research Position**: Show publications/awards, de-emphasize industry work
- **Entry Level**: Hide publications, emphasize education/projects
- **Leadership Role**: Emphasize experience, may hide education details

### View Examples

Check out the example files:
- `cv-content-example-software.tex` - Industry software role
- `cv-content-example-research.tex` - Academic/research position

Compile them to see different layouts:
```bash
# Use command line to compile with different content
pdflatex "\def\contentfile{cv-content-example-software.tex}\input{cv-template.tex}"
```

## Troubleshooting

**Error: "pdflatex: command not found"**
- LaTeX is not installed. Follow Step 1.

**Error: "File 'cv-content.tex' not found"**
- Make sure you're in the correct directory
- The `.tex` files should be in the same folder

**PDF looks wrong:**
- Try compiling twice: `pdflatex cv-template.tex` (run it again)
- Check for typos in your `cv-content.tex`

## Need Help?

- Read the full [README.md](README.md) for detailed instructions
- Check the example files for reference
- Open an issue on GitHub

Happy job hunting! 🚀

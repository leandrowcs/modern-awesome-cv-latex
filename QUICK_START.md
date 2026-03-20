# Quick Start Guide

Get your CV ready in 5 minutes!

## 1. Prerequisites

Ensure you have:
- **LuaTeX** or **XeTeX** installed
- **Perl** (for optional `latexmk` support)

### Quick Install

**Windows:**
```bash
# Install MiKTeX: https://miktex.org/
# Install Strawberry Perl: https://strawberryperl.com/
```

**macOS:**
```bash
brew install basictex
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get install texlive-latex-base texlive-fonts-recommended texlive-latex-extra
```

## 2. Clone the Repository

```bash
git clone https://github.com/leandrowcs/modern-awesome-cv-latex.git
cd modern-awesome-cv-latex
```

## 3. Update Your Information

Edit `cv.tex` with your details:

```latex
\name{Your}{Name}
\tagline{Your Professional Title and Short Summary}
\socialinfo{
    \linkedin{your-linkedin-id}
    \github{your-github-id}
    \smartphone{+1 XXX XXX XXXX}
    \email{your-email@example.com}
    \address{City, Province, Country}
}
```

## 4. Update Sections

Each section is in a separate file:

| File | Purpose |
|------|---------|
| `section_01_headline.tex` | Professional summary |
| `section_02_competences.tex` | Skills and technologies |
| `section_03_experience.tex` | Work experience |
| `section_04_formation.tex` | Education |
| `section_05_certifications.tex` | Certifications |
| `section_06_languages_and_expertise.tex` | Languages & expertise |

## 5. Compile Your CV

### Option A: LuaTeX (Recommended)
```bash
lualatex cv.tex
```

### Option B: XeTeX
```bash
xelatex cv.tex
```

### Option C: Automatic (with latexmk)
```bash
latexmk -lualatex cv.tex
```

## 6. View Your CV

Open `cv.pdf` - Done! ✨

## Customization Tips

### Change Color Theme

In `cv.tex`, modify the `\documentclass` line:

```latex
\documentclass[localFont,alternative,green]{modern-awesome-cv}
```

Available colors:
- `green` (default)
- `red`
- `indigo`
- `orange`
- `monochrome`

### Add Experience

In `section_03_experience.tex`:

```latex
\experience
  {Current}{Job Title}{Company}{City, Country}
  {Start Date}
  {
    \begin{itemize}
      \item Achievement or responsibility
      \item Key technology or skill used
    \end{itemize}
  }
  {TECH1, TECH2, TECH3}
```

### Add Certification

In `section_05_certifications.tex`:

```latex
\scholarshipentry{YEAR}
{Certification Name | Credential ID XXXXX}
```

### Add Skill

In `section_02_competences.tex`:

```latex
\keywordsentry{Category}{\textbf{Skill1}, \textbf{Skill2}, {Skill3}}
```

## Troubleshooting

| Problem | Solution |
|---------|----------|
| `fontspec requires XeTeX or LuaTeX` | Use `lualatex` instead of `pdflatex` |
| `perl` script engine not found | Install Strawberry Perl (Windows) or perl module (Linux/macOS) |
| Font not found | Remove `localFont` option or add fonts to `fonts/` directory |
| PDF not updating | Delete `.aux`, `.log`, `.out` files and recompile |

## VS Code Integration

1. Install [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
2. Open `cv.tex`
3. Press `Ctrl+Alt+B` to build
4. PDF updates automatically on save

## Next Steps

- ✏️ Update all sections with your information
- 🎨 Choose your favorite color theme
- 🔄 Test different layouts with the `alternative` option
- 📤 Push to your GitHub
- 📌 Add to your portfolio

## Need Help?

- Check [README.md](README.md) for detailed documentation
- Review example entries in each section file
- Open a GitHub issue

---

Happy CV building! 🚀

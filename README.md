# Modern LaTeX CV Template

A customized, modern LaTeX CV template tailored for QA and Tech Professionals.

## Overview

This project provides a clean, professional CV template built with LaTeX. The template emphasizes clarity, readability, and modern design principles, making it ideal for sharing across LinkedIn, job applications, and professional networks.

## Features

- 🎨 **Modern Design**: Clean layout with accent colors and section-based organization
- 📱 **Responsive Layout**: Works well for both digital and print formats
- 🔧 **Easy Customization**: Simple file structure with modular sections
- 🌐 **Multilingual Support**: Built-in support for multiple languages (English, French, Portuguese)
- ⚡ **LuaTeX/XeTeX Compatible**: Advanced typography features for professional documents
- 🏷️ **Font Awesome Icons**: Beautiful icons for visual hierarchy

## Project Structure

```
.
├── fonts/                                 # Local font files
├── cv.pdf                                 # Generated PDF output
├── cv.tex                                 # Main CV document
├── modern-awesome-cv.cls                  # LaTeX class file (main template)
├── README.md                              # This file
├── section_01_headline.tex                # Professional summary/headline
├── section_02_competences.tex             # Skills and competencies
├── section_03_experience.tex              # Professional experience
├── section_04_formation.tex               # Education and training
├── section_05_certifications.tex          # Certifications and credentials
├── section_06_languages_and_expertise.tex # Languages and expertise areas
```

## Prerequisites

### Required Software

1. **LaTeX Distribution with LuaTeX or XeTeX**
   - Windows: [MiKTeX](https://miktex.org/) or [TeX Live](https://www.tug.org/texlive/)
   - macOS: [MacTeX](https://www.tug.org/mactex/) or [TeX Live](https://www.tug.org/texlive/)
   - Linux: [TeX Live](https://www.tug.org/texlive/) via package manager

2. **Perl** (required for `latexmk`)
   - Windows: [Strawberry Perl](https://strawberryperl.com/) or [ActivePerl](https://www.activestate.com/products/perl/)
   - macOS/Linux: Usually pre-installed; install via Homebrew or package manager if needed

3. **Git** (optional, for version control)

### Font Requirements

The template uses **Source Sans Pro** font. If using the `localFont` option, ensure font files are present in the `fonts/` directory. Otherwise, the system fonts are used.

## Installation

### Option 1: Using Git Clone

```bash
git clone https://github.com/leandrowcs/modern-awesome-cv-latex.git
cd modern-awesome-cv-latex
```

### Option 2: Manual Download

1. Download the repository as a ZIP file
2. Extract to your desired location
3. Open `cv.tex` in your LaTeX editor

## Usage

### Compiling the CV

#### Using LuaTeX (Recommended)
```bash
lualatex cv.tex
```

#### Using XeTeX
```bash
xelatex cv.tex
```

#### Using latexmk (Automatic)
```bash
latexmk -lualatex cv.tex
```

**Note:** For automatic compilation on save in VS Code, install the [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension.

### Output

The compiled PDF will be generated as `cv.pdf` in the same directory.

## Customization

### Personal Information

Edit `cv.tex` to update:

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

### Updating Sections

Each section is in a separate file for easy management:

- **`section_01_headline.tex`**: Professional summary (2-3 paragraphs)
- **`section_02_competences.tex`**: Skills organized by category
- **`section_03_experience.tex`**: Work experience with responsibilities and technologies
- **`section_04_formation.tex`**: Education and training
- **`section_05_certifications.tex`**: Professional certifications
- **`section_06_languages_and_expertise.tex`**: Languages, industry experience, and specializations

### Editing Experience Entries

Template for adding experience in `section_03_experience.tex`:

```latex
\experience
  {End Date}
  {Job Title}{Company Name}{Location}
  {Start Date}
  {
    \begin{itemize}
      \item Key responsibility 1
      \item Key responsibility 2
      \item Key responsibility 3
    \end{itemize}
  }
  {TECHNOLOGY1, TECHNOLOGY2, TECHNOLOGY3}
```

### Color Customization

The template supports multiple color themes. In `cv.tex`, modify:

```latex
\documentclass[localFont,alternative,blue]{modern-awesome-cv}  % Change 'blue' to:
% - green
% - red
% - indigo
% - orange
% - monochrome
```

### Template Options

In `cv.tex`, the `\documentclass` accepts these options:

- `localFont`: Use local font files from the `fonts/` directory
- `alternative`: Alternative layout style
- `blue|green|red|indigo|orange|monochrome`: Color theme selector (default: blue)
- `showLinks`: Display hyperlinks visibly (for digital PDF)

## Adding Content

### Add New Certification

In `section_05_certifications.tex`:

```latex
\scholarshipentry{YEAR}
{Certification Title | Credential ID XXXXX}
```

### Add New Skill

In `section_02_competences.tex`:

```latex
\keywordsentry{Category Name}{\textbf{Skill1}, \textbf{Skill2}, {Skill3}, {Skill4}}
```

### Add Education Entry

In `section_04_formation.tex`:

```latex
\scholarshipentry{START-END}
{Degree Title at Institution Name}
```

## Troubleshooting

### Error: Script engine 'perl' not found

**Solution**: Install Perl (see Prerequisites section)

### Error: fontspec requires XeTeX or LuaTeX

**Solution**: Use `lualatex` or `xelatex` instead of `pdflatex`

### Missing Font Errors

**Solution**: Either:
1. Place font files in the `fonts/` directory and use the `localFont` option
2. Remove the `localFont` option to use system fonts

### PDF Not Updating

**Solution**: Delete auxiliary files and recompile:

```bash
rm -f cv.aux cv.log cv.out  # Linux/macOS
del cv.aux cv.log cv.out    # Windows Command Prompt
```

## Supported Commands

### Personal Info

- `\name{FirstName}{LastName}` - Set author name
- `\tagline{tagline text}` - Set professional summary
- `\linkedin{username}` - Add LinkedIn profile
- `\github{username}` - Add GitHub profile
- `\email{email@example.com}` - Add email
- `\smartphone{+1 XXX XXX XXXX}` - Add phone number
- `\address{Location}` - Add address

### Section Commands

- `\sectionTitle{Title}{Icon}` - Create a section header
- `\cvtag{tag text}` - Create inline skill tag

### Environments

- `keywords` - For organizing skills by category
- `scholarship` - For education and certifications
- `experiences` - For professional experience
- `twocolumnsection` - For two-column layouts

## Credits

- **Original Template**: [YAAC: Another Awesome CV](https://github.com/darwiin/yaac-another-awesome-cv) by Christophe Roger (Darwiin)
- **Customizations**: Leandro Wanderley Couto (leandrowcs)

This customized template maintains the core design philosophy of the original while tailoring it for modern tech and QA professionals.

## License

This work is distributed under the [LaTeX Project Public License (LPPL)](http://www.latex-project.org/lppl.txt), version 1.3c or later.

The customizations and documentation are also shared under the same license to maintain consistency with the original template.

## Contributing

To improve this template:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit with clear messages
5. Push to the branch
6. Create a Pull Request

## Contact & Support

- **LinkedIn**: [@leandrowcs](https://www.linkedin.com/in/leandrowcs/)
- **GitHub**: [@leandrowcs](https://github.com/leandrowcs)

For issues or suggestions, please open a GitHub issue or contact directly.

---

**Last Updated**: March 2026  
**Version**: 1.0

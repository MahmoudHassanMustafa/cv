# CV

A LaTeX-based curriculum vitae with automated PDF compilation and deployment. This repository provides a professional, maintainable CV template with continuous integration via GitHub Actions.

## 📋 Overview

This CV is built using LaTeX for professional typography and is organized into modular sections for easy maintenance. Every push to the `main` branch automatically:
- Compiles the LaTeX document to PDF
- Deploys the PDF to GitHub Pages
- Creates downloadable artifacts with timestamps

## 📁 Project Structure

```
cv/
├── cv.tex                 # Main LaTeX document
├── sections/              # Modular CV sections
│   ├── summary.tex        # Professional summary
│   ├── skills.tex         # Technical skills
│   ├── experience.tex     # Work experience
│   └── education.tex      # Educational background
├── .github/
│   └── workflows/
│       └── build-cv.yml   # CI/CD workflow
└── README.md
```

## 🚀 Getting Started

### Prerequisites

To compile this CV locally, you'll need:

- **LaTeX Distribution**: 
  - TeX Live (Linux/Mac)
  - MiKTeX (Windows)
- **Required LaTeX Packages**:
  - `geometry`, `titlesec`, `tabularx`, `xcolor`, `enumitem`
  - `fontawesome5`, `hyperref`, `paracol`, `changepage`
  - `sourcesanspro` font

### Local Compilation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/MahmoudHassanMustafa/cv.git
   cd cv
   ```

2. **Compile the PDF**:
   ```bash
   pdflatex cv.tex
   # Or use latexmk for better handling:
   latexmk -pdf cv.tex
   ```

3. **View the output**:
   The compiled PDF will be generated as `cv.pdf` in the root directory.

## 🔄 Automated Workflow

The repository includes a GitHub Actions workflow (`.github/workflows/build-cv.yml`) that:

### Triggers
- **Automatic**: Runs on push to `main` branch when CV files are modified
- **Manual**: Can be triggered manually via GitHub Actions UI

### Actions Performed
1. ✅ Compiles LaTeX document using `latex-action`
2. 📦 Creates timestamped artifacts for each build
3. 🔗 Deploys PDF to GitHub Pages for easy sharing
4. 📊 Retains artifacts for 30-90 days

### Accessing the Deployed PDF

After a successful build, your CV will be available at:
```
https://mahmoudhassanmustafa.github.io/cv/cv.pdf
```

**Note**: Ensure GitHub Pages is enabled in your repository settings:
- Settings → Pages → Source: Deploy from branch → `gh-pages` → `/ (root)`

**Repository Visibility & GitHub Pages**:
- **Public repository**: Free GitHub Pages with public site (recommended for CVs)
- **Private repository**: Requires paid GitHub plan (Pro/Team/Enterprise), but Pages site can still be public and shareable

💡 *Tip*: For CV repositories, keeping the repo public is common practice since the CV content is already meant to be shared, and it showcases your version control and automation skills.

## ✏️ Customization

### Updating Content

Edit the relevant section files in `sections/`:
- `summary.tex`: Professional summary
- `skills.tex`: Technical skills and tools
- `experience.tex`: Work experience entries
- `education.tex`: Educational background

### Modifying Styling

The main document (`cv.tex`) contains:
- **Color scheme**: Primary color defined as `primaryColor` (line 16)
- **Typography**: Uses Source Sans Pro font family
- **Layout**: Custom environments for one/two/three column entries
- **Header**: Personal information and contact details

### Adding New Sections

1. Create a new `.tex` file in `sections/`
2. Define the section using `\section{Section Name}`
3. Import it in `cv.tex` using `\input{sections/yourfile}`

## 📦 LaTeX Packages

Key packages used in this template:
- `geometry`: Page margins and layout
- `titlesec`: Custom section formatting
- `paracol`: Multi-column layouts for entries
- `hyperref`: PDF metadata and clickable links
- `fontawesome5`: Icons for contact information
- `xcolor`: Color customization
- `changepage`: Flexible page adjustments

## 🛠️ Maintenance

### Version Control
- Use Git to track changes to your CV
- Commits automatically trigger PDF builds
- Compare PDF artifacts to review changes

### Best Practices
- Keep sections modular and focused
- Use consistent formatting across entries
- Test compilation locally before pushing
- Review generated PDFs after major changes

## 📄 License

This project is open source and available under the MIT License (or your preferred license).

## 🔗 Resources

- [LaTeX Documentation](https://www.latex-project.org/)
- [Overleaf LaTeX Guide](https://www.overleaf.com/learn)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

---

**Last Updated**: See commit history for latest changes  
**PDF Build Status**: ![Build Status](https://github.com/MahmoudHassanMustafa/cv/workflows/Build%20CV%20PDF/badge.svg)

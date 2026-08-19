# Technical & Engineering LaTeX Report Template

Welcome! This repository is configured as a modular LaTeX workspace tailored for writing professional engineering and technical reports with **IEEE citation styling**, executive summary, automatic table of contents, lists of figures and tables, and structured appendices.

---

## 📁 Project Directory Structure

```text
ers-report/
├── main.tex                    # Master LaTeX document (compiles into final PDF)
├── references.bib              # BibTeX database (IEEE styled references)
├── .latexmkrc                  # Build configuration file for latexmk
├── README.md                   # Project overview & usage instructions
│
├── sections/                   # Chapter & content files (modular)
│   ├── 00_executive_summary.tex
│   ├── 01_introduction.tex
│   ├── 02_background.tex
│   ├── 03_methodology.tex
│   ├── 04_results_analysis.tex
│   ├── 05_discussion.tex
│   └── 06_conclusion.tex
│
├── figures/                    # Subfolder for diagrams, plots, and images
│   └── README.md
│
└── appendices/                 # Appendices (code listings, supplementary data)
    ├── appendix_a_code.tex
    └── appendix_b_data.tex
```

---

## 🛠️ How to Compile to PDF

### Option A: Local Compilation (Recommended tools)
1. **MiKTeX / TeX Live + VS Code (LaTeX Workshop extension)**:
   - Install [MiKTeX](https://miktex.org/) or [TeX Live](https://www.tug.org/texlive/).
   - Open this directory in VS Code with the **LaTeX Workshop** extension installed.
   - Simply press `Ctrl + Alt + B` or save `main.tex` to automatically build the PDF.

2. **Command Line (`latexmk`)**:
   ```bash
   latexmk -pdf main.tex
   ```

### Option B: Online Compilation (Overleaf)
- Zip this entire folder.
- Go to [Overleaf.com](https://www.overleaf.com), select **New Project** $\rightarrow$ **Upload Project**, and upload the zip file.
- Set compiler to **pdfLaTeX** and main document to **`main.tex`**.

---

## 📝 How We Will Work Together

1. **Section-by-Section Writing**: You can give me text, raw notes, bullet points, or instructions for any section, and I will format and write it directly into the relevant `.tex` file in `sections/`.
2. **Adding Figures**: Place your image files into the `figures/` folder. Give me the image filename and where it should go, and I'll generate the LaTeX figure code with proper captions and label references.
3. **Citations (IEEE)**: Add reference details (DOIs, paper titles, authors) to `references.bib` or just paste them here in chat, and I will format them into BibTeX and cite them in your text (e.g. `\cite{key}`).
4. **Tables & Math**: Give me raw table data or equations, and I will format clean publication-quality LaTeX tables (`booktabs`/`tabularx`) and math blocks.

# CV — LaTeX source files

This folder contains four variants of Camilo Ovalle's CV in LaTeX format:

| File | Focus | Language |
|---|---|---|
| `cv-software-dev-en.tex` | Software Engineer / Full Stack Developer | English |
| `cv-software-dev-es.tex` | Ingeniero de Software / Full Stack Developer | Spanish |
| `cv-hybrid-en.tex` | Full Stack Dev + IT Operations Specialist | English |
| `cv-hybrid-es.tex` | Desarrollador Full Stack + Especialista IT | Spanish |

All four files share the `cv-style.sty` style package — **do not delete it**.

---

## How to compile

### Option A — Overleaf (easiest, no install needed)
1. Go to [overleaf.com](https://www.overleaf.com) and create a free account.
2. Click **New Project → Upload Project**.
3. Upload all files from this folder as a `.zip`.
4. Open the `.tex` file you want and click **Compile**.
5. Download the PDF.

### Option B — Local (requires a LaTeX distribution)

**Install LaTeX if you don't have it:**
```bash
# Ubuntu / WSL (Debian-based)
sudo apt install texlive-full
# or a lighter install:
sudo apt install texlive texlive-latex-extra texlive-fonts-extra
```

**Compile a single file:**
```bash
cd cv/
pdflatex cv-software-dev-en.tex    # generates cv-software-dev-en.pdf
```

Run `pdflatex` **twice** if hyperlinks or references look wrong on the first pass.

**Compile all four in one go:**
```bash
cd cv/
for f in cv-software-dev-en cv-software-dev-es cv-hybrid-en cv-hybrid-es; do
  pdflatex "$f.tex"
done
```

---

## Required LaTeX packages

All packages are included in `texlive-full`. If using a minimal install, ensure these are available:

- `geometry` · `titlesec` · `enumitem` · `hyperref`
- `fontawesome5` · `xcolor` · `parskip` · `microtype`
- `lmodern` · `babel` (for Spanish variants) · `array` · `tabularx`

---

## ATS compatibility

These CVs are intentionally **single-column, text-only** — no tables for content, no images,
no complex headers. This makes the PDF fully text-selectable so Applicant Tracking Systems
(ATS) can parse every keyword correctly.

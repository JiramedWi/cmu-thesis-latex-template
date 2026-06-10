# CMU Thesis LaTeX Template

A ready-to-use LaTeX template for Master's thesis at **Chiang Mai University (CMU)**.

This template is designed so that other students can create their thesis document **easily** by editing only the content files. All formatting, page layout, and document structure are handled automatically by `CMUThesis.cls`.

---

## Quick Start

### 1. Requirements

- **LaTeX Engine**: XeLaTeX (required for Thai font support)
- **Fonts**: The `font/` folder contains the Thai font (Angsa). Do NOT delete it.
- **Editor**: Any LaTeX editor (Overleaf, TeXstudio, VS Code + LaTeX Workshop, etc.)

### 2. How to Compile

Run the following commands **from the template folder**:

```bash
xelatex MainPage.tex
bibtex MainPage
xelatex MainPage.tex
xelatex MainPage.tex
```

Or if your editor supports it, simply set the compiler to **XeLaTeX** and build.

> **Note**: You must run `xelatex` and `bibtex` multiple times to resolve all cross-references and citations.

---

## File Structure

```
CMU_Thesis_Template/
|-- MainPage.tex              <-- Main document (compile this)
|-- CMUThesis.cls             <-- Document class (DO NOT EDIT)
|-- ThesisInfo.tex            <-- Your thesis info (title, name, advisors, etc.)
|-- ApprovalPage.tex          <-- Approval page (usually no edit needed)
|-- Acknowledgement.tex       <-- Your acknowledgement
|-- Abstract_English.tex      <-- English abstract
|-- Abstract_Thai.tex         <-- Thai abstract
|-- Chap1_Introduction.tex    <-- Chapter 1: Introduction
|-- Chap2_LiteratureReview.tex <-- Chapter 2: Literature Review
|-- Chap3_Methodology.tex     <-- Chapter 3: Methodology
|-- Chap4_ResultsAndDiscussion.tex <-- Chapter 4: Results and Discussion
|-- Chap5_Conclusion.tex      <-- Chapter 5: Conclusion
|-- CurriculumVitae.tex       <-- Your CV
|-- library.bib               <-- Bibliography database
|-- font/                     <-- Thai fonts (DO NOT DELETE)
|   |-- Angsa.ttf
|   |-- Angsab.ttf
|   |-- Angsai.ttf
|   |-- Angsabi.ttf
|-- Images/                   <-- Put your images here
```

---

## What to Edit (Step-by-Step)

### Step 1: Thesis Information (`ThesisInfo.tex`)

This is the **most important file**. Fill in all the placeholder values:

| Command | What to fill |
|---------|-------------|
| `\ThesisTitle{...}` | Your thesis title in English |
| `\ThesisTitleForSubmitted{...}` | Same title, use `\\` for line breaks if needed |
| `\TitleForAbstract{...}` | Title for the abstract page |
| `\TitleInThai{...}` | Thai title, wrap in `\textthai{...}` |
| `\NamePrefix{...}` | `Mister`, `Miss`, or `Mrs.` |
| `\NamePrefixInThai{...}` | `\textthai{นาย}`, `\textthai{นางสาว}`, etc. |
| `\Author{...}` | Your full name in English |
| `\AuthorInThai{...}` | Your full name in Thai |
| `\DateOfBirth{...}` | Your date of birth |
| `\PlaceOfBirth{...}` | Your place of birth |
| `\Degree{...}` | e.g., `Master of Science` |
| `\DegreeInThai{...}` | e.g., `\textthai{วิทยาศาสตรมหาบัณฑิต}` |
| `\Program{...}` | e.g., `in Software Engineering` |
| `\ProgramInThai{...}` | e.g., `\textthai{วิศวกรรมซอฟต์แวร์}` |
| `\Date{...}` / `\Month{...}` / `\Year{...}` | Examination date (year in Buddhist era) |
| `\Advisor{...}` / `\AdvisorInThai{...}` | Your primary advisor |
| `\CoadvisorA{...}` / `\CoadvisorAInThai{...}` | Your co-advisor |
| `\Chairman{...}` | Committee chairman |
| `\CommitteeA{...}` to `\CommitteeC{...}` | Committee members |

### Step 2: Abstracts

- **`Abstract_English.tex`** - Write your English abstract (1-2 pages recommended)
- **`Abstract_Thai.tex`** - Write your Thai abstract (wrap Thai text in `\textthai{...}`)

### Step 3: Chapter Content

Edit each chapter file with your own content:

| File | Content |
|------|---------|
| `Chap1_Introduction.tex` | Background, objectives, scope |
| `Chap2_LiteratureReview.tex` | Related work and theoretical foundations |
| `Chap3_Methodology.tex` | Your research methodology |
| `Chap4_ResultsAndDiscussion.tex` | Results and analysis |
| `Chap5_Conclusion.tex` | Summary, findings, limitations, future work |

### Step 4: Supporting Content

| File | Content |
|------|---------|
| `Acknowledgement.tex` | Your acknowledgement |
| `CurriculumVitae.tex` | Your education, publications, experiences |
| `library.bib` | BibTeX entries for your references |

### Step 5: Images

Place all your images in the `Images/` folder and reference them like:

```latex
\begin{figure}[ht!]
    \centering
    \includegraphics[width=0.7\textwidth]{Images/your_image.png}
    \caption{Your figure caption}
    \label{fig:your_label}
\end{figure}
```

### Step 6: Bibliography

Add your BibTeX entries to `library.bib`:

```bibtex
@article{key2024,
  author  = {Author Name},
  title   = {Paper Title},
  journal = {Journal Name},
  year    = {2024}
}
```

Then cite in your chapters with `\cite{key2024}`.

---

## Optional Features

### Dedication Page

Uncomment in `ThesisInfo.tex`:
```latex
\Dedication{Your dedication message}
```

And uncomment in `MainPage.tex`:
```latex
\DedicationPage
```

### Publications Page

Create a `ListPublications.tex` file and uncomment in `MainPage.tex`:
```latex
\include{ListPublications}
```

### Appendices

Uncomment in `MainPage.tex`:
```latex
\appendix
\input{Appendix_A}
\include{Appendix_B}
\include{Appendix_C}
```

### Co-Advisor B (if applicable)

Uncomment in `ThesisInfo.tex`:
```latex
\CoadvisorB{Title.\,Name Surname}
\CoadvisorBInThai{\textthai{ตำแหน่ง ชื่อ นามสกุล}}
```

---

## Useful LaTeX Tips

### Tables

```latex
\begin{table}[h!]
    \centering
    \caption{Your Table Caption}
    \label{tab:your_label}
    \begin{tabular}{|l|r|}
        \hline
        \textbf{Column 1} & \textbf{Column 2} \\ \hline
        Data 1 & 100 \\ \hline
    \end{tabular}
\end{table}
```

### Cross-References

```latex
% Reference a table/figure/section
As shown in Table~\ref{tab:your_label} and Figure~\ref{fig:your_label}.
See Section~\ref{chapter2:section:topic1}.
```

### Math

```latex
Inline math: $E = mc^2$

Display math:
\[
\Delta = \text{Count}(\text{closed}) - \text{Count}(\text{opened})
\]
```

### Lists

```latex
% Bullet list
\begin{itemize}
    \item First item
    \item Second item
\end{itemize}

% Numbered list
\begin{enumerate}
    \item First item
    \item Second item
\end{enumerate}
```

---

## Editor Setup

### VS Code (Recommended Setup)

If you're using **VS Code**, you need to install the **LaTeX Workshop** extension and configure it to use XeLaTeX.

#### Step 1: Install prerequisites

1. Install a TeX distribution:
   - **macOS**: [MacTeX](https://www.tug.org/mactex/) (or `brew install --cask mactex`)
   - **Windows**: [MiKTeX](https://miktex.org/) or [TeX Live](https://www.tug.org/texlive/)
   - **Linux**: `sudo apt install texlive-full` (Debian/Ubuntu) or `sudo dnf install texlive` (Fedora)

2. Install the **LaTeX Workshop** extension in VS Code:
   - Open VS Code → Extensions (`Cmd+Shift+X` / `Ctrl+Shift+X`)
   - Search for **"LaTeX Workshop"** by James Yu
   - Click **Install**

#### Step 2: Configure LaTeX Workshop for XeLaTeX

Open VS Code settings (`Cmd+,` / `Ctrl+,`), click the `{}` icon (Open Settings JSON), and add:

```json
{
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": ["%DOCFILE%"]
        }
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "xelatex -> bibtex -> xelatex*2",
            "tools": [
                "xelatex",
                "bibtex",
                "xelatex",
                "xelatex"
            ]
        }
    ],
    "latex-workshop.latex.recipe.default": "first"
}
```

#### Step 3: Build your thesis

- Open `MainPage.tex` in VS Code
- Save the file → LaTeX Workshop will **auto-build** on save
- Or press `Cmd+Option+B` / `Ctrl+Alt+B` to build manually
- View the PDF with `Cmd+Option+V` / `Ctrl+Alt+V`

> **Tip**: If the PDF preview doesn't update, press `Cmd+Shift+P` → type "LaTeX Workshop: Build with recipe" → select the `xelatex -> bibtex -> xelatex*2` recipe.

### Overleaf (Online, No Setup)

1. Upload the entire template folder as a `.zip` to [Overleaf](https://www.overleaf.com)
2. Go to **Menu** → **Compiler** → select **XeLaTeX**
3. That's it! Overleaf handles the rest.

### Terminal (No Editor)

```bash
# From the template directory:
xelatex MainPage.tex
bibtex MainPage
xelatex MainPage.tex
xelatex MainPage.tex
```

---

## Prerequisites Before You Start

Before writing your thesis, make sure you have these ready:

| Item | Why you need it |
|------|----------------|
| Your thesis title (English + Thai) | Needed in `ThesisInfo.tex` |
| Advisor and committee names (English + Thai) | Needed in `ThesisInfo.tex` |
| Examination date | Needed in `ThesisInfo.tex` |
| Your BibTeX references (`library.bib`) | Collect papers early, cite as you write |
| Your images/figures (PNG, JPG, PDF) | Put them in `Images/` folder |
| CMU thesis formatting guidelines | Check your faculty's specific requirements |
| Your photo for CV page | Save as `Images/your_photo.jpg` |

> **Reference**: Check the [CMU Graduate School website](https://grad.cmu.ac.th/) for the latest thesis formatting rules and submission guidelines.

---

## AI-Assisted Writing (Recommended)

Writing a thesis in LaTeX can be tedious. Here are some tools that can help:

### Claude Code (Highly Recommended)

**[Claude Code](https://claude.ai/code)** is an AI coding assistant by Anthropic that works directly in your terminal and editor. It can:

- Write and edit LaTeX content for you
- Fix compilation errors automatically
- Generate tables, figures, and formatting
- Help structure your chapters
- Manage your bibliography

```bash
# Install Claude Code
npm install -g @anthropic-ai/claude-code

# Navigate to your thesis folder
cd your-thesis-folder

# Start Claude Code
claude
```

Once running, you can ask it things like:
- "Add a new section about machine learning in Chap2"
- "Fix the table formatting in Chap4"
- "Help me write the abstract"
- "Why is my LaTeX not compiling?"

> **Fun fact**: This template was cleaned up and documented with the help of Claude Code. So it's already proven to work for thesis writing.

### Other AI Tools

| Tool | Best for |
|------|----------|
| [Claude](https://claude.ai) | General writing, research, brainstorming |
| [ChatGPT](https://chat.openai.com) | General writing assistance |
| [Overleaf AI](https://www.overleaf.com) | Inline LaTeX editing assistance |

> **Important**: Always review and verify AI-generated content. Your thesis is your own work. Use AI as a helper, not a replacement for your thinking.

---

## Common Issues

| Problem | Solution |
|---------|----------|
| Thai text not rendering | Make sure the `font/` folder is in the same directory as `MainPage.tex` |
| Missing references | Run `bibtex` then `xelatex` twice |
| Font "Times New Roman" not found | Install it on your system, or change the font in `MainPage.tex` |
| Page numbers wrong | Make sure you compile multiple times |
| Images not found | Put images in `Images/` folder and use correct path |

---

## Credits

- **Original template**: Wanchai Tapanyo, Mathematics Department, Faculty of Science, CMU (2017)
- **Templated & maintained by**: [Jiramed Withunsapphasiri](https://github.com/JiramedWi) (2025)
- **AI-assisted documentation**: This template was cleaned, documented, and tested with [Claude Code](https://claude.ai/code) by Anthropic

---

## License

This template is shared freely for academic use. Please retain the original credits in `CMUThesis.cls`.

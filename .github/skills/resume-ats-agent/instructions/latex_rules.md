# LaTeX Generation Rules

## Golden Rule: Template Fidelity

The output `.tex` file MUST be structurally and visually identical to `templates/sample-resume.tex`.
Copy the **entire preamble verbatim** — every `\usepackage`, `\geometry`, `\titleformat`, and custom `\newcommand`. Do NOT simplify, substitute, or omit any preamble line.

---

## Mandatory Preamble (copy exactly)

```latex
\documentclass[letterpaper,10.5pt]{article}

\usepackage{latexsym}
\usepackage[empty]{fullpage}
\usepackage{titlesec}
\usepackage[usenames,dvipsnames]{color}
\usepackage{enumitem}
\usepackage[hidelinks]{hyperref}
\usepackage[english]{babel}
\usepackage{geometry}

\geometry{top=0.42in, bottom=0.42in, left=0.5in, right=0.5in}

\pagestyle{empty}
\urlstyle{same}
\raggedbottom
\raggedright
\setlength{\tabcolsep}{0in}

\titleformat{\section}{
  \vspace{-5pt}\scshape\raggedright\large
}{}{0em}{}[\color{black}\titlerule\vspace{-5pt}]

\newcommand{\resumeItem}[1]{
  \item\small{#1\vspace{-2pt}}
}

\newcommand{\resumeSubheading}[4]{
  \vspace{-2pt}\item
    \begin{tabular*}{0.97\textwidth}[t]{l@{\extracolsep{\fill}}r}
      \textbf{#1} & \small #2 \\
      \textit{\small#3} & \textit{\small #4} \\
    \end{tabular*}\vspace{-6pt}
}

\newcommand{\resumeProjectHeading}[2]{
  \item
    \begin{tabular*}{0.97\textwidth}{l@{\extracolsep{\fill}}r}
      \small#1 & \small #2 \\
    \end{tabular*}\vspace{-6pt}
}

\newcommand{\resumeSubHeadingListStart}{\begin{itemize}[leftmargin=0.15in, label={}]}
\newcommand{\resumeSubHeadingListEnd}{\end{itemize}}
\newcommand{\resumeItemListStart}{\begin{itemize}[leftmargin=0.2in]\vspace{-2pt}}
\newcommand{\resumeItemListEnd}{\end{itemize}\vspace{-4pt}}
```

---

## Section Structure (follow exactly)

### Header

```latex
\begin{center}
  {\LARGE \textbf{Prateek Verma}} \\[4pt]
  \small <Role Title> \\[4pt]
  +91 7877123418 \;$|$\; \href{mailto:...}{...} \;$|$\; \href{...}{...} \;$|$\; Bangalore, India
\end{center}
```

### Section Divider

Use `\section{Section Name}` — never `\subsection`, `\textbf{}`, or manual `\hrule`.

### Experience Entry

```latex
\resumeSubHeadingListStart
  \resumeSubheading
    {Company Name}{City, Country}
    {Job Title}{Mon YYYY -- Mon YYYY}
    \resumeItemListStart
      \resumeItem{Bullet text here.}
    \resumeItemListEnd
\resumeSubHeadingListEnd
```

### Project Entry

```latex
\resumeSubHeadingListStart
  \resumeProjectHeading
    {\textbf{Project Name} $|$ \textit{Tech, Stack, Here}}{}
    \resumeItemListStart
      \resumeItem{Bullet text here.}
    \resumeItemListEnd
\resumeSubHeadingListEnd
```

### Skills Section

```latex
\begin{itemize}[leftmargin=0.15in, label={}, itemsep=-1pt]
  \small{
    \item \textbf{Category:} skill1, skill2, skill3
  }
\end{itemize}
```

### Education Entry

```latex
\resumeSubHeadingListStart
  \resumeSubheading
    {University Name}{City, Country}
    {Degree \textnormal{$|$ GPA: X.XX / 10}}{Mon YYYY -- Mon YYYY}
\resumeSubHeadingListEnd
```

### Certifications Section

```latex
\begin{itemize}[leftmargin=0.15in, label={}, itemsep=0pt]
  \small{\item Certification Name}
\end{itemize}
```

---

## Bullet Formatting Rules

- Each `\resumeItem{}` must be a **single line** in the source — no line breaks inside the braces
- Max ~105 characters per bullet (including the `\resumeItem{}` wrapper)
- Use `$\rightarrow$` for arrows (e.g., `400ms $\rightarrow$ 340ms`)
- Escape special characters: `&` → `\&`, `%` → `\%`, `#` → `\#`, `_` → `\_`
- Never use raw `—` or `–`; use `--` for en-dash in date ranges

## Forbidden LaTeX Patterns

- No `\begin{tabular}` outside the macros defined above
- No `\columnwidth`, `\minipage`, `\multicols`, or any column-layout construct
- No `\textcolor{}`, `\colorbox{}`, or any colored text
- No `\vspace{}` or `\hspace{}` outside the template macros
- No `\begin{table}`, `\begin{figure}`, or floating environments
- No custom font commands (`\fontsize`, `\selectfont`, `\setmainfont`)
- No additional `\usepackage{}` lines beyond what the preamble specifies

## File Output

- Write the complete `.tex` file — preamble through `\end{document}`
- File path: `tailored-resumes/Prateek_${CompanyName}.tex`
- `${CompanyName}` = company name from the JD with spaces replaced by underscores, no special characters

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

Teaching materials for the **Simulación de Sistemas y Procesos** course at Universidad Anáhuac México (Facultad de Ingeniería), taught by Prof. DSc. BARSEKH-ONJI Aboud. All content is in LaTeX Beamer format.

## Identity
- Professor at the Faculty of Engineering, Universidad Anáhuac México
- Researche Topics: Evolutionary Computatio, Many Objectives Optimization, Fuzzy Substractive Clustering, hybrid models (Fuzzy Logic, PSO/MOPSO, LSTM Deep and Machine Learning Algorithms)

## Students Profil
- Students of Fac. of Enineernig (industrial Engin), 50% of developpement in the career (have info about Diff. Ecuation, and mathematical probability).
## Technical environment
- OS: Ubuntu 24.04, ThinkPad T14
- Python: conda env `research` (Python 3.11)
  - NEVER use venv/virtualenv, always conda
  - Interpreter: /home/aboudonji/miniforge3/envs/research/bin/python
- MATLAB: R2025b (main language)
- LaTeX: pdflatex by default, xelatex as fallback

## Delivery rules
- Academic documents: Markdown or LaTeX/Beamer (Berlin theme, 16:9)
- Presentations: Beamer, NOT PowerPoint
- Skills available in: ~/.config/claude/skills/

## Language
- Respond in the language in which the question is asked (ES/EN/AR)
## Compile Commands

```bash
# Standard compilation (most slides)
pdflatex <file>.tex

# Slides using biblatex/biber (APA bibliography)
pdflatex <file>.tex && biber <file> && pdflatex <file>.tex && pdflatex <file>.tex

# Slides in Simulation Conferences (modular structure with sections/)
cd "Simulation Conferences/Simulation (N)/" && pdflatex main.tex
```

## Repository Structure

Two parallel hierarchies, both containing Beamer slides:

**`Process Simulation/`** — standalone `.tex` files, one per topic:
- `Simulación de procesos (1)/` — Intro to systems (Berkeley theme, English, biblatex/biber)
- `Simulación de procesos (2) (Eventos Discretos)/` — Discrete events
- `Simulación de procesos (3) (Stateflow)/` — MATLAB Stateflow
- `Simulación de procesos (4) (Regression_Models)/` — Regression models
- `Simulación de procesos (5) (Series Temportales)/` — Time series
- `Simulación de procesos (6) (Simulación MonteCarlo)/` — Monte Carlo
- `Simulación Sistemas dinámicos/` — State space / block algebra (Berlin theme, TikZ diagrams)
- `PID controller/` — PID control (Berlin theme, Spanish)

**`Simulation Conferences/`** — modular structure per session:
```
Simulation (N)/
├── main.tex          # preamble + \input{sections/}
├── config/
│   └── code_langs.tex  # listings styles (Python, MATLAB, C, C++, R, Java)
└── sections/
    ├── section00.tex   # title/TOC frames
    ├── section01.tex   # content section 1
    ├── section02.tex   # content section 2
    └── section03.tex   # content section 3
```

## Two Beamer Templates in Use

**Berlin theme (main template)** — used in `Simulation Conferences/` and most `Process Simulation/` files:
- `\documentclass[aspectratio=169,xcolor=dvipsnames]{beamer}`
- `\usetheme{Berlin}`
- MATLAB listings style (`MATLABStyle`) defined inline
- `config/code_langs.tex` provides Python/C/C++/R/Java listing environments

**Berkeley theme** — used in older `Simulación de procesos (1)` and `(2)` files:
- `\documentclass{beamer}` (no aspectratio)
- `\usetheme{Berkeley}`
- Custom footline with ORCID: `BARSEKH-ONJI Aboud, ORCID: 0009-0004-5440-8092`
- Requires `biber` for bibliography

**SimpleDarkBlue theme** — standalone `.sty` files in `Simulación de procesos (1)/`; not used in active slides.

## Standard Header (Berlin template)

```latex
\documentclass[aspectratio=169,xcolor=dvipsnames]{beamer}
\usetheme{Berlin}
\usepackage[spanish]{babel}  % or [english]
\institute{\textbf{Universidad Anáhuac México}\\ {Facultad de Ingeniería}}
\author{\textbf{Prof. DSc. BARSEKH-ONJI Aboud}}
```

## Topics Covered (by session number)

1. Introduction to Systems — classification, modeling process
2. Discrete-time systems — SimEvents concepts
3–5. SimEvents examples (MATLAB)
6–7. Stateflow (finite state machines in MATLAB/Simulink)
8. PID Controllers
9. Stateflow examples

Process simulation modules add: regression models, time series, Monte Carlo simulation, state space / block diagram algebra.

# Data Mining: Lecture Notes

Typeset lecture notes for **Data Mining**, University of Pisa, academic year
2024/25. The notes cover the two-part course: Data Mining I lays the foundations
(data understanding, clustering, classification, regression, pattern and rule
mining), and Data Mining II moves to advanced tabular and time-series methods
(imbalanced learning, dimensionality reduction, outlier detection, gradient
descent, logistic regression, SVM, neural and deep networks, ensembles,
explainability, and the full time-series pipeline through similarity, clustering,
and classification).

> ⚠️ **Disclaimer.** Derived from the *Data Mining* course materials (Academic
> Year 2024/2025), MSc in Data Science & Business Informatics, University of
> Pisa.
>
> These notes are open educational content created by a student. They are **not
> an academic source** and may contain inaccuracies. You may freely share,
> modify, and reuse this material for educational and non-commercial purposes
> with appropriate attribution. The content is my personal interpretation of the
> professor's course materials and should not replace official teaching
> resources. I assume no responsibility for any errors or misinterpretations.
>
> These notes were produced with an **AI-in-the-middle** workflow: a first human
> pass, then **Claude Code** to support formulation, understanding, and
> rewriting, followed by a final human review.
>
> If you find errors, have suggestions, or spot unintentionally included
> copyrighted material (which I will promptly remove on notification), contact me
> at `sclfnc@proton.me`.

This course is part of the [MSc Data Science lecture notes](https://github.com/sclfnc/unipi-ds-notes) collection (University of Pisa), one repository per course. Clone the whole set with `git clone --recursive`.

## Layout

- `main.tex`: entry point, in the folder root; identical across the whole
  notes collection (it only loads the shared preamble and the course file).
- `src/housestyle.tex`, shared house style: geometry, colors, section and ToC
  formatting, running heads, and the math environments (theorem, definition, …).
- `src/common-preamble.tex`: the shared package set, identical across courses.
- `src/course.tex`, everything specific to this course: title metadata, the
  two `\part` groups, custom itemize/enumerate bullets, the `Rcode` listings
  environment (syntax-highlighted R snippets), `hyperref`, and the
  `\input{sec/...}` list.
- `sec/*.tex`: section files (the body of the notes), pulled in by `course.tex`;
  named `A_*`–`F_*` for Data Mining I and `00_*`–`14_*` for Data Mining II.
- `img/`: bitmap figures (lecture-slide screenshots and hand-drawn photos)
  included via `\includegraphics`; most other diagrams are native TikZ.
- `dm-notes.pdf`: the compiled notes, in the folder root.
- No bibliography: the notes carry no `.bib` file and use no `\cite`.

## Build

Build from the folder root:

```bash
latexmk main.tex
```

`latexmk` runs pdflatex as many times as needed. The compiled PDF is named
`dm-notes.pdf`; it and all auxiliary files (`.aux`, `.log`, `.toc`, `.bcf`,
`.bbl`, …) land in the folder root and are git-ignored (listed in
`.gitignore`). A `.latexmkrc` in the folder sets this up (it names the output
via `$jobname`). To do it by hand instead:

```bash
pdflatex -jobname=dm-notes main && pdflatex -jobname=dm-notes main
```

The second pass resolves the table of contents and cross-references. Requires a
standard TeX Live installation. Alternatively, upload the folder to
[Overleaf](https://www.overleaf.com) (New Project → Upload Project), set
`main.tex` as the main document, and compile.

## Credits

Written by **Francesco Secoli**, revised with the help of
[Claude Code](https://claude.com/claude-code): the course slides and lectures
were transcribed and refined into LaTeX, then reworked into standalone notes.
Based on the *Data Mining* course (a.y. 2024/25), University of Pisa.
Contributions welcome: open an issue or a pull request.

## Contents

The notes are twenty-one sections across two parts, in reading order:

| # | Part | Section | Topics |
|---|------|---------|--------|
| 1 | DM I | Data manipulation and understanding | Data visualization, data preparation, normalization, similarity and distance measures |
| 2 | DM I | Clustering | Cluster validity, K-Means and variants (bisecting, X-Means), model-based EM, hierarchical linkage, density-based DBSCAN / OPTICS / HDBSCAN |
| 3 | DM I | Classification | K-NN, Naïve Bayes, model evaluation and comparison, decision trees (splitting measures, pruning, regression trees), model selection |
| 4 | DM I | Linear regression | Least squares, alternative fitting methods, model evaluation, extensions |
| 5 | DM I | Pattern and association rule mining | Association rules, Apriori, interestingness measures, FP-Growth, special frequent patterns |
| 6 | DM I | Rule-based models | Rule-set properties, direct and indirect rule extraction, model characteristics |
| 7 | DM II | Imbalanced learning | Undersampling (Tomek, ENN, CNN), oversampling (SMOTE, ADASYN), class weights and threshold adjustment |
| 8 | DM II | Dimensionality reduction | Feature selection (variance, univariate), feature projection (RSP, PCA, SVD, MDS, Sammon, ISOMAP, t-SNE) |
| 9 | DM II | Outlier detection | Naive (IQR, HBOS), statistical, deviation-, depth-, proximity-, clustering-, high-dimensional, ensemble- and model-based approaches |
| 10 | DM II | Gradient descent, MLE and odds | Gradient descent (including for linear regression), maximum likelihood estimation, odds and log-odds |
| 11 | DM II | Logistic regression | The logit function, likelihood, recovering probabilities from log-odds |
| 12 | DM II | Support vector machines | Hard-margin (primal / dual), soft margin, kernel mapping, multiclass strategies, advantages and limitations |
| 13 | DM II | Neural network | Artificial neurons and perceptrons, learning rules, activation functions, MLPs, backpropagation, training issues and regularization |
| 14 | DM II | Deep neural networks | Activation functions, training and backpropagation, objective functions, tips and tricks, CNNs and RNNs |
| 15 | DM II | Ensemble learning | Bagging, boosting (AdaBoost, stumps), random forests, gradient boosting (XGBoost, LightGBM, CatBoost, EBM) |
| 16 | DM II | Explainability | TREPAN, LIME, LORE, SHAP, integrated gradients, instance-based explanations |
| 17 | DM II | Transactional clustering | K-Modes, ROCK, CLOPE, TX-Means |
| 18 | DM II | Sequential pattern mining | Generalized Sequential Patterns (candidate generation, pruning, support counting), time constraints |
| 19 | DM II | Time series | Visualization, missing values, anomalies, normalization techniques, components, models, decomposition |
| 20 | DM II | Similarity | Structural-based and shape-based similarity measures (including DTW) |
| 21 | DM II | Time-series clustering and classification | Similarity-based clustering, motif and discord discovery (matrix profile), classification and shapelet extraction |

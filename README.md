# Social Comparison and Self-Esteem in Adults

A statistical analysis of the relationship between social comparison, learned helplessness, and self-esteem in an adult sample.

![Python](https://img.shields.io/badge/Python-3.14-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![License](https://img.shields.io/badge/License-MIT-green)

---

## Overview

This project analyzes survey data from **135 adult respondents** collected via an online questionnaire (Porsline). The study tests whether **learned helplessness / negative attribution style** mediates the relationship between **social comparison** and **self-esteem**.

## Research Hypotheses

1. Social comparison is negatively associated with self-esteem.
2. Learned helplessness mediates the relationship between social comparison and self-esteem.
3. Gender, age, and education level predict self-esteem.

## Key Results

| Relationship | Statistic | Interpretation |
|---|---|---|
| Social Comparison ↔ Self-Esteem | r = **-0.32** (p < .001) | Moderate negative correlation |
| Helplessness ↔ Self-Esteem | r = **-0.64** (p < .001) | Strong negative correlation |
| Regression model | R² = **0.46**, F(4, 128) = 27.69, p < .001 | Model explains 46% of variance |
| Mediation (indirect effect) | **-0.41** (p < .001) | Full mediation by helplessness |
| Gender (independent t-test) | t(133) = 2.23, p = .030 | Men score higher than women |
| Education (one-way ANOVA) | F = 0.34, p = .71 | No significant difference |

**Central finding:** Learned helplessness fully mediates the relationship between social comparison and self-esteem. The direct effect of social comparison on self-esteem is not significant after controlling for the mediator.

## Project Structure

```
.
├── data/
│   └── selfsteem.xlsx              # Raw survey data
├── notebooks/
│   └── analysis.ipynb              # Full analysis pipeline
├── output/
│   ├── cleaned_analysis.xlsx       # Cleaned dataset
│   └── figures/                    # Plots and charts
├── requirements.txt
├── LICENSE
└── README.md
```

## Variables

### Instruments

| Scale | Items | Format | Cronbach's α |
|---|---|---|---|
| Social Comparison (SC) | 11 | 7-point Likert | 0.47 |
| Helplessness / Attribution (MID) | 27 | 7-point Likert | 0.81 |
| Rosenberg Self-Esteem (SE) | 10 | Binary (agree/disagree) | 0.84 |

### Demographics

- **Gender**: Female (n = 101), Male (n = 34)
- **Age**: M = 28.23, SD = 7.98, range = 16–66
- **Education**: Bachelor's+ (107), Diploma+ (20), PhD (8)

## Statistical Methods

- Descriptive statistics and frequency distributions
- Cronbach's alpha for internal consistency
- Pearson correlation matrix
- Independent-samples t-test and one-way ANOVA
- Multiple linear regression (OLS)
- Mediation analysis with bootstrapping (5,000 resamples) via `pingouin`
- Assumption checks: VIF, Durbin-Watson, Omnibus, Jarque-Bera

## Getting Started

### Prerequisites

```bash
pip install -r requirements.txt
```

### Run the Analysis

```bash
jupyter notebook notebooks/analysis.ipynb
```

## Key Libraries

| Library | Purpose |
|---|---|
| `pandas`, `numpy` | Data manipulation |
| `scipy.stats` | Statistical tests |
| `statsmodels` | Regression modeling |
| `pingouin` | Mediation analysis |
| `matplotlib`, `seaborn` | Visualization |

## Limitations

1. The self-esteem scale was administered as a binary (agree/disagree) format rather than the standard 4-point Rosenberg scale, limiting variance and sensitivity.
2. Cronbach's alpha for the social comparison scale is below the acceptable threshold (α = 0.47), suggesting possible multidimensionality requiring further factor-analytic work.
3. Male subsample (n = 34) is substantially smaller than female subsample (n = 101), limiting statistical power for gender comparisons.
4. Convenience sampling via an online platform restricts generalizability.

## Skills Demonstrated

- **Data cleaning**: Persian numeral conversion, Likert mapping, reverse-coding, missing-data handling
- **Psychometric analysis**: Reliability estimation, item-level inspection
- **Inferential statistics**: t-test, ANOVA, correlation, OLS regression
- **Advanced modeling**: Bootstrapped mediation analysis
- **Assumption diagnostics**: VIF, Durbin-Watson, normality tests
- **Reproducible workflow**: Jupyter notebook, modular code
- **Data visualization**: Correlation heatmaps, regression plots, distribution plots

## Author

**psysta_coder**

- GitHub: [@psysta_coder](https://github.com/psysta_coder)

## Citation

If you use this code or data, please cite:

```bibtex
@misc{socialcomparison_selfesteem,
  title  = {Social Comparison and Self-Esteem in Adults},
  author = {psysta\_coder},
  year   = {2025},
  note   = {GitHub repository},
  url    = {https://github.com/psysta_coder/socialcomparison-selfesteem}
}
```

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## Acknowledgments

Data collected via Porsline. Analyses conducted in Python 3.14 with Jupyter.
MIT License

Copyright (c) 2025 psysta_coder

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
git init
git branch -M main
git add .
git commit -m "Initial commit: analysis pipeline and results"
git remote add origin https://github.com/psysta_coder/socialcomparison-selfesteem.git
git push -u origin main

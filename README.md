# LLMs for Quantitative Analysis

Teaching materials for a short lesson on using large language models to help
with quantitative data analysis in R. Built around a single case study: a
(simulated) Qualtrics survey on the wellbeing of university students.

The exercise has two tasks:

1. **Data cleaning** — take the raw Qualtrics export and fix the 10 problems in
   it (5 with rows, 5 with data entry) to get an analysis-ready dataset.
2. **Data analysis** — describe the cleaned data, identify trends, and answer
   three research questions.

## Download the data

**Task 1 — raw data (to be cleaned):**

- Download page: https://github.com/alexiamhe93/llm-quant-analysis/blob/main/data/cultural_wellbeing_study.csv
- Direct link: https://raw.githubusercontent.com/alexiamhe93/llm-quant-analysis/main/data/cultural_wellbeing_study.csv

**Task 2 — cleaned data (for the analysis):**

- Aggregate scores (recommended for the analysis task):
  - Download page: https://github.com/alexiamhe93/llm-quant-analysis/blob/main/data/cultural_wellbeing_study_analysis.csv
  - Direct link: https://raw.githubusercontent.com/alexiamhe93/llm-quant-analysis/main/data/cultural_wellbeing_study_analysis.csv
- Item-level clean (all individual items + composites):
  - Download page: https://github.com/alexiamhe93/llm-quant-analysis/blob/main/data/cultural_wellbeing_study_clean.csv
  - Direct link: https://raw.githubusercontent.com/alexiamhe93/llm-quant-analysis/main/data/cultural_wellbeing_study_clean.csv

> On a download page, click the **Download raw file** button (top-right of the
> file view). The direct links open the CSV in the browser — right-click → Save.

## The notebook

`LLM_Quant_Analysis.Rmd` is the worked solution covering **both** tasks with all
the R code: every cleaning step (problem → detection → fix, with running row
counts) and the full analysis (ANOVA, correlation, regression, plots).

To run it, open in RStudio and **Knit**, or:

```r
install.packages(c("rmarkdown", "readr", "dplyr", "stringr", "ggplot2", "effectsize"))
rmarkdown::render("LLM_Quant_Analysis.Rmd")
```

## Files

| File | What it is |
|---|---|
| `data/cultural_wellbeing_study.csv` | Raw Qualtrics export (Task 1 input) |
| `data/cultural_wellbeing_study_analysis.csv` | Cleaned: aggregate scores + demographics |
| `data/cultural_wellbeing_study_clean.csv` | Cleaned: all items + composites |
| `LLM_Quant_Analysis.Rmd` | Worked-solution notebook (cleaning + analysis) |

## The dataset (cleaned, N = 299)

Three student groups (UK / EU / International) and three scales:

- **Wellbeing** (7 items, 1–5; items w4 & w6 reverse-worded)
- **Belonging** (5 items, 1–7)
- **Discrimination** (4 items, 1–5)

plus demographics (age, gender, nationality, year of study) and an open-text
response.
